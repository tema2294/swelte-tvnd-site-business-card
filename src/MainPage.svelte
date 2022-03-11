<script>
    import Category from "./Category-cards.svelte";
    import {Link} from "svelte-routing";


    function customScroll(type) {
        const sections = document.querySelector(type);
        console.log(sections)
        return sections.scrollIntoView({behavior: 'smooth', block: 'center'})
    }

    function downloadFile() {
        const link = document.createElement('a');
        link.setAttribute('href', '/Microsoft Excel Worksheet.xlsx');
        link.setAttribute('download', 'price.xlsx');
        link.click();
        return false;
    }

    let isOpen = false;

</script>

<main>
    <header>
        <nav class="nav-container">
            <a>ТНВД 76</a>
            <div on:click={()=> isOpen = !isOpen} class="{!isOpen ? 'burger_menu' : 'burger_menu burger_menu-open'}">
                <span></span>
                <span></span>
            </div>
            <ul class="{!isOpen ? 'nav-list' : 'nav-list nav-list-open'}">
                <li on:click={()=>customScroll('.info-section')}>О нас</li>
                <li on:click={()=>customScroll('.advantages-section')}>Преимущества</li>
                <li on:click={()=>customScroll('.address-section')}>Контакты</li>
                <li on:click={()=>customScroll('.map-section')}>Как добраться</li>
            </ul>
            <a class="nav-info" href="tel:+79066359997">
                <div class="nav-info_work-time">Пн-Вс 10:00 - 21:00</div>
                <div class="nav-info_work-number">+ 7 906 635 9997</div>
            </a>
        </nav>

    </header>
    <section class="main-section">
        <div class="info-container">
            <div class="info-container_title">Дизель центр в Ярославле,<br/> качество и гарантия!</div>
            <div class="info-container_text">Ремонт и продажа Тнвд и комплектующих</div>
            <div on:click={downloadFile} class="info-container_btn">Скачать прайс</div>
        </div>
    </section>
    <section class="category">
        <div class="category-header">Категории</div>

                   <Category></Category>

    </section>
    <section class="info-section">
        <div class="info-section_header">О нас</div>
        <div class="info-section_main">
            <p>
                Интернет магазин новых и б/у запчастей.У нас вы можете купить запчасти по всей России. Команда
                профессионалов специализируется на подборе и доставке запчастей для ремонта и обслуживания ТНВД.
            </p>
            <p>Мы делаем полный спектр ремонтных работ , от диагностики до замены любой
                запчасти. Вы всегда получаете качественную работу от наших профессионалов и полную гарантию на все виды
                работ.
            </p>
            <!--            <p>Мы ремонтируем марки автомобилей: <b>Toyota, Honda, Subaru, Nissan, Suzuki, Mazda, Mitsubishi</b></p>-->
        </div>
    </section>
    <section class="advantages-section">
        <div class="advantages-section_title">
            Наши преимущества
        </div>

        <div class="advantages-section_list">
            <div class="card">
                <img class="card_img" src="img/vote-icon-19.png" alt=""/>
                <div class="card_title">Наличие</div>
                <div class="card_text">Большой перечень запчастей в наличие</div>
            </div>
            <div class="card">
                <img class="card_img" src="img/342-3426164_5-year-f.png" alt=""/>
                <div class="card_title">Гарантия</div>
                <div class="card_text">Полное гарантийное обслуживание на всю продукцию</div>
            </div>
            <div class="card">
                <img class="card_img" src="img/png-clipart-computer.png" alt=""/>
                <div class="card_title">Обязательства</div>
                <div class="card_text">выполнения любого объема работы в срок</div>
            </div>
        </div>
    </section>
    <section class="address-section">
        <div class="address-card">
            <div class="address-section_title">
                <span>Наш телефон:</span> <span>+7 906 635 9997</span>
            </div>
            <hr/>
            <div class="address-section_text">
                Москва СЗАО ул. Максимова, д. 28. Метро Горки
                Мы находимся в большом ангарном помещении на северо-западе города. Подъезд со стороны Зеленой улицы.
                <br>
                <br>
                Пн-Вс: 10:00–21:00
            </div>
        </div>

    </section>
    <section class="map-section">
        <script type="text/javascript" charset="utf-8" async
                src="https://api-maps.yandex.ru/services/constructor/1.0/js/?um=constructor%3A76f664072c8f87f0f18db2865e6b49de92288d0f01ace595715ad5b457ea3076&amp;width=100%&amp;height=100%&amp;lang=ru_RU&amp;scroll=true">
        </script>
    </section>
</main>

<style>
</style>