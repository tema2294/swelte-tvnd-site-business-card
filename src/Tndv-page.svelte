<script>
    import {tnvd_data} from "./data/tnvd";
</script>
<main>
    <header>
        <nav class="nav-container">
            <a>ТНВД 76</a>

            <a class="nav-info" href="tel:+79066359997">
                <div class="nav-info_work-time">Пн-Вс 10:00 - 21:00</div>
                <div class="nav-info_work-number">+ 7 906 635 9997</div>
            </a>
        </nav>

    </header>
    <div class="item-section">
        <div class="action-options">

        </div>
        <div class="item-container">
            {#each tnvd_data as item (item.name)}

            <div class="item-card">
                <div class="img-container">
                    <img src={item.img}/>
                </div>
                <div class="info-container">
                    <div class="header-card">
                        <div>{item.name}</div>
                        <div>{item.price} руб</div>
                    </div>
                    <div class="info"></div>
                    <div class="action-card-container">
                        <div class="btn">
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

    .action-container {
        display: flex;
        justify-content: flex-start;
        align-items: center;
    }

    .item-container {
        display: grid;
        justify-content: center;
        grid-template-columns: repeat(auto-fill, 300px);
        align-content: center;
        gap: 30px;
        padding: 50px 15vw 0;
    }

    .card {
        background: black;
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