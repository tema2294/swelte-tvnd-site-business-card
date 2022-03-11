<script>
    import {tnvd_data} from "./data/tnvd";
    import {formatNumber} from "./tools/format-number";
    import {Link} from "svelte-routing";
    import {onMount} from "svelte";

    let isOpen = false

    const defaultSort = 'Сортировка'
    const asc = 'По возврастанию'
    const desc = 'По убыванию'

    let sortValue = defaultSort


    const handleSelect = (e) => {
        sortValue = e.target?.innerText
        isOpen = !isOpen
    }
    const descFunction = (a, b) => a.price - b.price
    const ascFunction = (a, b) => b.price - a.price
    $: isActiveSort = sortValue !== defaultSort
    $: sortFunction = sortValue === asc ? descFunction : ascFunction
    $: data = isActiveSort ? tnvd_data.sort(sortFunction) : tnvd_data
    onMount(()=>window.scroll(0,0))
</script>
<main>
    <header>
        <nav class="nav-container">
            <Link to="/">
                <svg class="arrow-back-svg" version="1.0" xmlns="http://www.w3.org/2000/svg"
                     width="40px" height="40px" viewBox="0 0 1280.000000 1280.000000"
                     preserveAspectRatio="xMidYMid meet">
                    <g transform="translate(0.000000,1280.000000) scale(0.100000,-0.100000)"
                       fill="#fff" stroke="none">
                                        <path d="M7556 10480 c-384 -61 -686 -316 -799 -676 -88 -278 -46 -583 115
                -832 40 -62 200 -228 806 -834 l756 -758 -3289 -3 -3290 -2 -83 -23 c-412
                -110 -696 -437 -742 -850 -50 -453 224 -878 662 -1028 166 -57 -15 -54 3503
                -54 l3240 0 -756 -757 c-470 -471 -772 -781 -796 -818 -266 -399 -218 -911
                117 -1245 186 -187 417 -282 685 -283 169 -1 295 28 445 103 168 85 66 -15
                2024 1955 l1441 1450 52 95 c196 364 159 787 -98 1104 -32 39 -772 785 -1646
                1657 -1369 1367 -1600 1594 -1674 1643 -157 102 -315 153 -504 160 -60 3 -137
                1 -169 -4z"/>
                    </g>
                </svg>

            </Link>
            <a>ТНВД 76</a>

            <a class="nav-info" href="tel:+79066359997">
                <div class="nav-info_work-time">Пн-Вс 10:00 - 21:00</div>
                <div class="nav-info_work-number">+ 7 906 635 9997</div>
            </a>
        </nav>

    </header>
    <div class="item-section">
        <div class="action-options">
            <div>
                <div class="select">
                    <input class="select__input" type="hidden" name="">
                    <div on:click={()=>isOpen = !isOpen}
                         class={isOpen ? "select__head open" : "select__head"}>{sortValue}</div>
                    <ul class={isOpen ? "select__list open" : "select__head d-none"}>
                        <li on:click={handleSelect} class="select__item">{asc}</li>
                        <li on:click={handleSelect} class="select__item">{desc}</li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="item-container">
            {#each data as item (item.name)}

                <div class="item-card">
                    <div class="img-container">
                        <img src={item.img}/>
                    </div>
                    <div class="info-container">
                        <div class="header-card">
                            <div>{item.name}</div>
                            <div>{formatNumber(item.price)} руб</div>
                        </div>
                        <div class="info"></div>
                        <div class="action-card-container">
                            <div class="btn">
                                <svg class="MuiSvgIcon-root MuiSvgIcon-fontSizeMedium css-vubbuv" focusable="false"
                                     aria-hidden="true" viewBox="0 0 24 24" data-testid="AddShoppingCartIcon">
                                    <path d="M11 9h2V6h3V4h-3V1h-2v3H8v2h3v3zm-4 9c-1.1 0-1.99.9-1.99 2S5.9 22 7 22s2-.9 2-2-.9-2-2-2zm10 0c-1.1 0-1.99.9-1.99 2s.89 2 1.99 2 2-.9 2-2-.9-2-2-2zm-9.83-3.25.03-.12.9-1.63h7.45c.75 0 1.41-.41 1.75-1.03l3.86-7.01L19.42 4h-.01l-1.1 2-2.76 5H8.53l-.13-.27L6.16 6l-.95-2-.94-2H1v2h2l3.6 7.59-1.35 2.45c-.16.28-.25.61-.25.96 0 1.1.9 2 2 2h12v-2H7.42c-.13 0-.25-.11-.25-.25z"></path>
                                </svg>
                                купить
                            </div>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</main>


<style>
    .d-none {
        display: none;
    }

    a {
        cursor: pointer;
    }

    .arrow-back-svg {
        transform: rotate(180deg) !important;
    }

    .nav-container {

    }

    .item-card {
        display: flex;
        flex-direction: column;
        width: 100%;
        background-color: rgb(255, 255, 255);
        color: rgba(0, 0, 0, 0.87);
        transition: box-shadow 300ms cubic-bezier(0.4, 0, 0.2, 1) 0ms;
        border-radius: 4px;
        box-shadow: rgb(0 0 0 / 20%) 0px 2px 1px -1px, rgb(0 0 0 / 14%) 0px 1px 1px 0px, rgb(0 0 0 / 12%) 0px 1px 3px 0px;
        overflow: hidden;
    }

    .action-card-container {
        width: 100%;
        display: flex;
        align-content: center;
        height: 30px;
    }

    .info-container {
        padding: 16px 16px 0;
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 30%;


    }

    .header-card {
        font-weight: 400;
        line-height: 1.334;
        letter-spacing: 0em;
        display: flex;
        justify-content: space-between;
        width: 100%;
        font-size: 22px;
    }

    .img-container {
        height: 70%;
        overflow: hidden;
        border-bottom: 3px solid black;
    }

    .img-container > img {
        width: 100%;
        display: block;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center center;
        object-fit: cover;
    }

    header {
        position: relative;
    }

    .nav-container {
        background: black;
    }

    .item-section {
        display: flex;
        flex-direction: column;
        width: 100%;
    }

    .action-options {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        border: 1px solid black;
        border-radius: 10px;
        height: fit-content;
        padding: 20px 40px;
    }

    .item-container {
        display: grid;
        justify-content: space-around;
        grid-template-columns: repeat(auto-fill, 300px);
        align-content: center;
        gap: 30px;
        margin-top: 20px;
        border: 1px solid black;
        border-radius: 10px;
        padding: 20px 40px;

    }

    .item-section {
        padding: 50px 15vw 0;

    }

    .select {
        position: relative;
        display: block;
        min-width: 220px;
        width: 100%;
        max-width: 400px;
    }

    .select__head {
        width: 100%;
        max-width: 100%;
        box-shadow: 0 0 4px rgba(0, 0, 0, 0.2);
        border-radius: 10px;
        padding: 14px 15px;
        font-size: 14px;
        line-height: 18px;
        color: rgba(66, 67, 72, 0.8);
        cursor: pointer;
    }

    .select__head::after {
        width: 10px;
        height: 6px;
        background: #FFF url("data:image/svg+xml,%3Csvg width='10' height='6' viewBox='0 0 10 6' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M4.50495 5.78413L0.205241 1.25827C-0.0684138 0.970375 -0.0684138 0.503596 0.205241 0.215836C0.478652 -0.0719461 0.922098 -0.071946 1.19549 0.215837L5.00007 4.22052L8.80452 0.215953C9.07805 -0.0718292 9.52145 -0.0718292 9.79486 0.215953C10.0684 0.503736 10.0684 0.970492 9.79486 1.25839L5.49508 5.78425C5.35831 5.92814 5.17925 6 5.00009 6C4.82085 6 4.64165 5.928 4.50495 5.78413Z' fill='%23ED266A'/%3E%3C/svg%3E%0A") no-repeat center / cover;
        position: absolute;
        right: 20px;
        bottom: 50%;
        transform: translateY(50%);
        content: '';
        display: block;
        transition: .2s ease-in;
    }

    .select__head.open::after {
        transform: translateY(50%) rotate(180deg);
    }

    .select__list {
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: #fff;
        box-shadow: 0 0 4px rgba(0, 0, 0, 0.2);
        border-radius: 10px;
        margin-top: 5px;
        max-height: 205px;
        overflow-x: hidden;
        overflow-y: auto;
        z-index: 100;
        margin: 0;
        padding: 0;
        font-size: 14px;
        color: #424348;
        scrollbar-color: dark;
        scrollbar-width: thin;
        overscroll-behavior: contain;
    }

    .select__list::-webkit-scrollbar {
        width: 7px;
        background-color: #F8F9FA;
        padding: 5px;
    }

    .select__list::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background-color: #D9D9D9;
    }

    .select__list .select__item {
        position: relative;
        border-top: 1px solid rgba(224, 229, 231, 0.5);
        padding: 10px 15px;
        cursor: pointer;
        list-style-type: none;
    }

    .select__list .select__item:hover {
        background-color: rgba(224, 229, 231, 0.5);
    }

    @media (max-width: 800px) {
        .item-container {
            display: grid;
            justify-content: center;
            grid-template-columns: repeat(auto-fill, 300px);
            align-content: center;
            gap: 30px;
            padding: 30px 5vw 0;
        }
    }
</style>