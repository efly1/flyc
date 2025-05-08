### [👉👉👉♥♥点此进入♥观看入口👈👈👈](http://a.d44k.cc/jm.html)
<br></br><br></br><br></br>
    def plot_time_series(self, columns=None, title=None, figsize=(12, 6)):
        """
        绘制时间序列图
        参数:
            columns: 要绘制的列名列表
            title: 图表标题
            figsize: 图表大小
        """
        if self.processed_data is None:
            print("没有可绘制的数据")
            return False
        
        if columns is None:
            # 如果没有指定列，尝试绘制所有数值列
            numeric_cols = self.processed_data.select_dtypes(include=[np.number]).columns
            if len(numeric_cols) == 0:
                print("没有数值型数据可绘制")
                return False
            columns = numeric_cols
        
        plt.figure(figsize=figsize)
        for col in columns:
            plt.plot(self.processed_data.index, self.processed_data[col], label=col)
        
        plt.title(title if title else "时间序列分析")
        plt.xlabel("日期")
        plt.ylabel("值")
        plt.legend()
        plt.tight_layout()
        plt.show()
        return True
    
