<template>
    <div>
        <!--왼쪽 목록-->
        <div style="float: left;height: 100% ;width:14%;background-color:white ; border-top: 1.9px solid gray; margin-left: 2%;">
            <div class="list_head">
                FASHION
            </div>
            <div class="content">
                <ul>
                    <li>스크랩/컬렉션</li>
                    <li>악세서리</li>
                    <li>패션정보</li>
                    <li>일상/여행</li>
                    <li>예쁜코디</li>
                </ul>
            </div>
            <div class="list_head">
                LIFE
            </div>
            <div class="content">
                <ul>
                    <li>음악</li>
                    <li>영화/드라마</li>
                    <li>맛집/카페</li>
                    <li>향수</li>
                    <li>운동</li>
                </ul>
            </div>
            <div class="list_head">
                FASHION
            </div>
            <div class="content">
                <ul>
                    <li>스크랩/컬렉션</li>
                    <li>악세서리</li>
                    <li>패션정보</li>
                    <li>일상/여행</li>
                    <li>예쁜코디</li>
                </ul>
            </div>
        </div>
        <!--배경사진-->
        <div style="float:right;height: 100%;">
            <div style="height: 50%;">
                <b-carousel id="carousel-fade" style="text-shadow: 0px 0px 2px #000" fade indicators img-width="824"
                    img-height="440">
                    <b-carousel-slide caption="Edit your fit" img-src="https://picsum.photos/1024/480/?image=345">
                    </b-carousel-slide>
                </b-carousel>
            </div>
        </div>

    </div>
</template>

<style scoped>
.list_head{
    font-weight: 600;
    border-top: 2px solid darkgray;
    border-bottom: 2px solid darkgray;
}
.content{
    font-size: small;
}
</style>