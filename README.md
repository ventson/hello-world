# hello-world
Test the functions and usages of github

Uh, I think Warriors didn't do their best at G4.

Yeah, here I added something new.

# cut fastq header to sequence
awk -F':' 'NR % 4 == 1 {seq=$NF} NR % 4 == 2 { $0=$0 seq}1' R1test.fq > R1test_new.fq

# filter non-CB tag in BAM file
nohup samtools view possorted_genome_bam.bam -h | awk '/^@/ || /CB:/' | samtools view -h -b > possorted_genome_bam.clean.bam &
