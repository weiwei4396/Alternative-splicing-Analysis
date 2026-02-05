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
#### 4.1 [IsoQuant](https://github.com/ablab/IsoQuant) and [Spl-IsoQuant](https://github.com/algbio/spl-IsoQuant)
<details>
<summary> </summary>


</details>

#### 4.2 [Sicelore-2.1](https://github.com/ucagenomix/sicelore-2.1)
用来做长读长单细胞数据的定量
<details>
<summary> </summary>
- 扫描Nanopore的reads, 分配cell barcode;
这一步扫描文库生成的cDNA序列, 对Nanopore fastq reads扫描polyA(T)和adaptor, 将其归类为pass; 扫描polyA(T)的长度参数大于等于15nt, A(T)≥75%, 在两端100nt以内, 找到polyA之后在下游找adaptor; 在得到第一次的pass的reads后, 使用cellranger生成的barcode list来分配barcode, 在给定barcode list的条件下, 99%的都会分配正确, 有正确barcode信息的归类于pass, 其余的为fail.
```shell

```

</details>

#### 4.3 [Isosceles](https://github.com/Genentech/Isosceles)
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












