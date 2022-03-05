<script>
    import {Link} from "svelte-routing";
</script>
<div class="category-list">
    <div class="card">
        <img height="140" class="card-img" src="https://автостанция63.рф/img/catalog34.png"/>

        <div class="content-card">
            <span class="header-card">Тнвд</span>
            <!--            <div class="header-text">Ящерицы — это широко распространенная группа чешуйчатых рептилий, насчитывающая-->
            <!--                более 6000 видов на всех континентах, кроме Антарктиды.-->
            <!--            </div>-->
        </div>
        <div class="actions-container">

        </div>
    </div>
    <div class="card">
        <img height="140" class="card-img" src="https://diesel-exp.ru/upload/iblock/96c/96c252f19a43a8c4309559b87e9142e5.jpg"/>
        <div class="content-card">
            <span class="header-card">Плунжерные пары</span>
        </div>
        <div class="actions-container">
        </div>
    </div>
    <div class="card">
        <img height="140" class="card-img" src="https://dizelstore.ru/image/cache/catalog/tovar/%20%D0%90%D0%97%D0%9F%D0%98-500x500.jpg"/>
        <div class="content-card">
            <span class="header-card">Распылители</span>
        </div>
        <div class="actions-container">
        </div>
    </div>
    <div class="card">
        <img height="140" class="card-img" src="https://www.enisey-servis.ru/upload/resize_cache/iblock/04e/244_172_1/04e023ef096d5b495bc204e2b5dc01d0.jpg"/>
        <div class="content-card">
            <span class="header-card">ТННД</span>
        </div>
        <div class="actions-container">
        </div>
    </div>
    <div class="card">
        <img height="140" class="card-img" src="https://cdn-icons-png.flaticon.com/512/64/64722.png"/>
        <div class="content-card">
            <span class="header-card">Другое</span>
        </div>
        <div class="actions-container">
        </div>
    </div>
</div>
<style>


    .card {
        transition: box-shadow 300ms cubic-bezier(0.4, 0, 0.2, 1) 0ms;
        border-radius: 4px;
        box-shadow: 0px 2px 1px -1px rgb(0 0 0 / 20%), 0px 1px 1px 0px rgb(0 0 0 / 14%), 0px 1px 3px 0px rgb(0 0 0 / 12%);
        width: 300px;
        background-color: #fff !important;
        flex-shrink: 0;
        overflow: hidden;
    }

    .card-img {
        width: 100%;
        object-fit: contain;
    }

    .header-card {
        font-family: "Roboto", "Helvetica", "Arial", sans-serif;
        font-weight: 400;
        font-size: 1.5rem;
        line-height: 1.334;
        letter-spacing: 0em;
        margin-bottom: 0.35em;
    }

    .header-text {
        margin: 0;
        font-family: "Roboto", "Helvetica", "Arial", sans-serif;
        font-weight: 400;
        font-size: 0.875rem;
        line-height: 1.43;
        letter-spacing: 0.01071em;
        color: black !important;
        white-space: normal;

    }

    .content-card {
        padding: 16px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: center;
        width: 100%;
    }


</style>