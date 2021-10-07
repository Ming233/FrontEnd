Path: https://www.bilibili.com/video/BV1Xy4y1v7S2?p=1

贪吃蛇游戏在chapter2 part2，思路不错，但是调头那一部分写的比较繁琐，可以优化。

Question:
        try{
            this.snake.X = X;
            this.snake.Y = Y;
        }catch (e:? unknown){
            // 进入到catch，说明出现了异常，游戏结束，弹出一个提示信息
            alert(e.message+' GAME OVER!');
            // 将isLive设置为false
            this.isLive = false;
        }