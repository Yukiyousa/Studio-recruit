<template>
<div class="home-container">
<el-container >
    <!-- main -->
    <el-main>
        <div class="rank-table">
            <div class="content">
                <div class="rank_font"><i class="el-icon-s-data"></i>Rank</div>
                    <div class="v-divider">
                        <el-divider></el-divider>
                    </div>
                <!-- rank table -->
                <el-tabs v-model="activeName" @tab-click="handleClick">
                    <el-tab-pane label="Total" name="first">
                        <el-table :data="tableData" style="width: 100%" class="rank-list"  stripe>
                            <!-- 后端返回数据已被排序 -->
                            <el-table-column type="index" :index="indexMethod"></el-table-column>
                            <!-- 后端返回数据未被排序但中有名次信息 --><!-- <el-table-column prop="rank" label="Rank" width="300px"></el-table-column> -->
                            <el-table-column prop="id" label="Id" width="240px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="240px"></el-table-column>
                            <el-table-column prop="scores" label="Scores" width="240px"></el-table-column>
                            <el-table-column prop="direction" label=" Direction" ></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="Web" name="second">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="Java" name="third">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="Security" name="fourth">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="Android" name="fifth">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="Machine Learning" name="sixth">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                    <el-tab-pane label="UI" name="seventh">
                        <el-table style="width: 100%" class="rank-list"  stripe>
                            <el-table-column type="index" :index="indexMethod"></el-table-column>                          
                            <el-table-column prop="id" label="Id" width="370px"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="370px"></el-table-column>
                            <el-table-column prop="scores" label="Scores"></el-table-column>
                        </el-table>
                    </el-tab-pane>
                </el-tabs> 
            </div>
            <div class="page">
                <el-pagination background layout="prev, pager, next" :total="total" @current-change="findPage" ></el-pagination>
            </div>
        </div>
    </el-main>
    <!-- footer -->
    <el-footer>
        <div class="footer">
			<span> Copyright (C) </span>
		    <span> 2019-2020 </span>
        </div>
    </el-footer>
</el-container>
</div>
</template>

<script>
export default {
    data() {
      return {
        activeName: 'first',
        total:100,//需后端返回的排名总人数
        //测试用例
        tableData: [{
            id:'测试用户1',
            solved:'20',
            direction:'Web',
            scores:'200'
        },
        {
            id:'测试用户2',
            solved:'19',
            direction:'Web',
            scores:'192'
        },
        {
            id:'测试用户3',
            solved:'19',
            direction:'Java',
            scores:'187'
        },
        {
            id:'测试用户4',
            solved:'19',
            direction:'UI',
            scores:'166'
        },
        {
            id:'测试用户5',
            solved:'19',
            direction:'Java',
            scores:'161'
        },
        {
            id:'测试用户6',
            solved:'19',
            direction:'Android',
            scores:'156'
        },
        {
            id:'测试用户7',
            solved:'18',
            direction:'Java',
            scores:'154'
        },
        {
            id:'测试用户8',
            solved:'17',
            direction:'Web',
            scores:'145'
        },
        {
            id:'测试用户9',
            solved:'16',
            direction:'Android',
            scores:'134'
        },
        {
            id:'测试用户10',
            solved:'16',
            direction:'UI',
            scores:'129'
        }],
      }
    },
    methods: {
        indexMethod(index){//排名函数
            return index+1;
        },
        findPage(page){//换页函数
            console.log(page);
        },
        handleClick(tab, event) {
            console.log(tab, event);
        }
    }
};
</script>

<style>
.home-container{
    height: 100vh;
    margin: 0;
    padding: 0;
}
.el-container{
    min-height: 100%;
}
.el-main {
    background-color: whitesmoke;
    color: #333;
    text-align: center;
    height: 100%;
}

.el-footer {
    background-color: whitesmoke;
    color: #333;
    text-align: center;
}

.rank-table{
    margin: auto;
    margin-top: 30px;
    width: 75%;
    box-sizing: inherit;
    background-color: #fff;
    border: 1px solid #ebeef5;
    border-radius: 2px;
    box-shadow: 0 1px 3px rgba(26,26,26,.1);
    border-radius: 2px;
    overflow: hidden;
}
.content{
    padding: 10px;
}
.rank-list{
    margin-top: 0px;
}
.rank-table:hover{
    box-shadow: 0px 0px 3px gray;
    transition: 0.3s;
}
.footer{
    padding: 20px;
}
.rank_font{
    font-size:30px;
    margin: 0px 10px 10px 10px;
    float: left;
}
.v-divider{
    margin-top: 50px;
    margin-bottom: 0px;
}
.el-divider{
    margin-bottom: 0px;
}
.page{
    margin-bottom: 20px;
    padding: 0;
}
.link{
    text-decoration: none;
    color: black;
}
</style>
