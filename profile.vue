<template>
<div class="home-container">
    <el-container>
        <!-- main -->
        <el-main>
            <!-- user -->
            <div class="center_header">
                <div class="content">
                    <div class="user_id"><i class="el-icon-user"></i>Username</div>
                    <div class="v-divider">
                        <el-divider></el-divider>
                    </div>
                </div>
            </div>
            <!-- summary -->
            <div class="center_summary">
                <div class="content">
                    <div class="summary"><i class="el-icon-document"></i><span class="summary_font">Summary</span></div>
                    <el-divider class="el-dicider"></el-divider>
                    <div class="summary_show">
                        <el-table :data="totalData" stripe style="width: 100%">
                            <el-table-column prop="direction" label="Direction" width="300"></el-table-column>
                            <el-table-column prop="solved" label="Solved" width="300"></el-table-column>
                            <el-table-column prop="rank" label="Rank"></el-table-column>
                        </el-table>
                    </div>
                </div>
            </div>
            <!-- solved -->
            <div class="center_solved">
                <div class="content">
                    <div class="solved"><i class="el-icon-s-flag"></i><span class="solved_font">Solved</span></div>
                    <el-divider class="el-dicider"></el-divider>
                    <div class="solved_show">
                        <el-tabs v-model="activeName" @tab-click="handleClick">
                            <el-tab-pane label="Web" name="first">
                                <el-table :data="tableData_web" stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                            <el-tab-pane label="Java" name="second">
                                <el-table :data="tableData_java" stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                            <el-tab-pane label="Security" name="third">
                                <el-table  stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                            <el-tab-pane label="Android" name="fourth">
                                <el-table  stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                            <el-tab-pane label="Machine Learning" name="fifth">
                                <el-table  stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                            <el-tab-pane label="UI" name="sixth">
                                <el-table  stripe style="width: 100%">
                                <el-table-column prop="problem" label="Problem" width="300"></el-table-column>
                                <el-table-column prop=direction label="Direction" width="300"></el-table-column>
                                <el-table-column prop="scores" label="Scores"></el-table-column></el-table>
                            </el-tab-pane>
                        </el-tabs>
                    </div>
                </div>
            </div>
        </el-main>
        <!-- footer -->
        <el-footer>
            <div class="footer">
				<span> Copyright (C) </span>
			    <span> 2020-2021 </span>
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
        totalData: [{
            direction:'Web',
            rank:'3',
            solved:'3'
        },{
            direction:'Java',
            rank:'10',
            solved:'1'
        },{
            direction:'Security',
            rank:'17',
            solved:'1'
        },{
            direction:'Android',
            rank:'21',
            solved:'2'
        },{
            direction:'Machine Learning',
            rank:'20',
            solved:'0'
        },{
            direction:'UI',
            rank:'10',
            solved:'2'
        }],
        tableData_web: [{
            problem: '1',
            direction: 'Web',
            scores: '90'
        }, {
            problem: '8',
            direction: 'Web',
            scores: '80'
        }, {
            problem: '39',
            direction: 'Web',
            scores: '85'
        }],
        tableData_java: [{
            problem: '5',
            direction: 'Java',
            scores: '90'
        }]
      }
    },
    methods: {
      handleClick(tab, event) {
        console.log(tab, event);
      }
    }
};
</script>

<style >
.home-container{
    height: 100vh;
    background-color: whitesmoke;
    margin: 0;
    padding: 0;
}
.el-container{
    min-height: 100%;
}
.el-main{
    background-color: whitesmoke;
    color: #333;
    text-align: center;
}
.center_header{
    margin: auto;
    margin-top: 20px;
    width: 60%;
    height: 100px;
    background-color: #fff;
    border: 1px solid #ebeef5;
    box-shadow: 0 1px 3px rgba(26,26,26,.1);
    border-radius: 2px;
    overflow: hidden;
}
.center_header:hover,.center_summary:hover,.center_solved:hover{
    box-shadow: 0px 0px 3px gray;
    transition: 0.3s;
}
.center_summary,.center_solved{
    margin: auto;
    margin-top: 30px;
    width: 60%;
    background-color: #fff;
    border: 1px solid #ebeef5;
    box-shadow: 0 1px 3px rgba(26,26,26,.1);
    border-radius: 2px;
    overflow: hidden;
}
.content{
    padding: 12px;
}
.user_id{
    font-size:30px;
    margin: 0px 10px 10px 10px;
    float: left;
}
.summary,.solved{
    font-size:20px;
    margin: 0px 10px 0px 10px;
    float: left;
}
.solved_show,.summary_show,.profile_show{
    margin-top: 0px;
    padding: 10px;
}
.summary_font,.solved_font{
    margin-left: 5px;
}
.v-divider{
    margin-top: 50px;
}
.el-dicider{
    margin-bottom: 0px;
    margin-top: 30px;
}
</style>
