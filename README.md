# Alternative-splicing-Analysis
Long-read RNA-seq analysis




## NanoPlot
<details>
<summary>Click</summary>


</details>






## fastplong
<details>
<summary>Click</summary>


</details>





## Coverage
<details>
<summary>Click</summary>


</details>



## SUPPA Alternative splicing events
<details>
<summary>Click</summary>

只需要给定更新后的gtf(可以用BroCOLI识别后更新的GTF, 或者初始给定的GTF或者其他), SUPPA就可以从gtf中得到可变剪切事件;

```shell
python /data/workdir/panw/softwares/SUPPA2.3/suppa.py generateEvents -i updated_annotations.gtf -o HIPP_MX -f ioe -e MX --pool-genes
```
- i：输入的gtf文件，从这个文件中找可变剪切事件；
- o: o：输出文件的名称；

</details>












