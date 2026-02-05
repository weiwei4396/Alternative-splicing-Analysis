# Alternative-splicing-Analysis
Long-read RNA-seq analysis

## 1.NanoPlot
<details>
<summary> </summary>


</details>

## 2.fastplong
<details>
<summary> </summary>


</details>

## 3.Coverage
<details>
<summary> </summary>


</details>

## 4.Transcript Identification and Quantification
#### 4.1 IsoQuant and Spl-IsoQuant
<details>
<summary> </summary>


</details>

#### 4.2 [Sicelore-2.1](https://github.com/ucagenomix/sicelore-2.1)
<details>
<summary> </summary>


</details>

#### 4.3 Isosceles
<details>
<summary> </summary>


</details>


## 5.SUPPA Alternative splicing events
只需要给定更新后的gtf(可以用BroCOLI识别后更新的GTF, 或者初始给定的GTF), [SUPPA](https://github.com/comprna/SUPPA) 就可以从gtf中得到可变剪切事件;

<details>
<summary> </summary>

```shell
python /data/workdir/panw/softwares/SUPPA2.3/suppa.py generateEvents -i updated_annotations.gtf -o HIPP_MX -f ioe -e MX --pool-genes
```
- i: 输入的gtf文件, 从这个文件中找可变剪切事件;
- o: 输出文件的名称;
- f: ioi表示转录本的可变剪切事件; ioe表示局部可变剪切事件, ioe才可以定义e参数;
- e: 表示具体类型的可变剪切事件, 如MX表示互斥外显子; SE, RI, FL(AF,AL), SS(A3,A5); 
- --pool-genes：这个参数可以充分利用novel的转录本, 因为novel转录本的gene_id命名并不是十分精确, 有些novel转录本应该与注释的是相同基因, 可能是由于开头和结尾部分超过基因范围导致命名写为NA, 而这个参数可以根据位置更精确地确定可变剪切事件;

</details>












