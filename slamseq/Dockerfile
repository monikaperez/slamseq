FROM nfcore/slamseq:latest
LABEL authors="Tobias Neumann" \
      description="Docker image containing all software requirements for the nf-core/slamseq pipeline"

ENV PATH /opt/conda/envs/nf-core-slamseq-1.0.0/bin:$PATH

# Dump the details of the installed packages to a file for posterity
RUN conda env export --name nf-core-slamseq-1.0.0 > nf-core-slamseq-1.0.0.yml &&\
      conda activate &&\
      pip uninstall slamdunk -y &&\
      conda config --add channels bioconda &&\
      conda config --add channels conda-forge &&\
      conda install nextgenmap &&\
      pip install git+https://github.com/monikaperez/slamdunk.git --upgrade &&\


# installing samtools wget https://github.com/samtools/samtools/releases/download/1.11/samtools-1.11.tar.bz2 && bzip2 -d samtools-1.11.tar.bz2 && tar xf samtools-1.11.tar && rm samtools-1.11.tar && cd samtools-1.11 && ./configure --enable-plugins && make && make install && cd ..
RUN wget https://github.com/samtools/samtools/releases/download/1.11/samtools-1.11.tar.bz2 &&\
      bzip2 -d samtools-1.11.tar.bz2 &&\
      tar xf samtools-1.11.tar &&\
      rm samtools-1.11.tar &&\
      cd samtools-1.11 &&\
      ./configure --enable-plugins &&\
      make &&\
      make install &&\
      cd .. &&\
      # echo "export PATH=/samtools-1.11/bin:$PATH" >> ~/.bashrc &&\

# installing bedtools wget https://github.com/arq5x/bedtools2/releases/download/v2.29.2/bedtools-2.29.2.tar.gz && tar -xzf bedtools-2.29.2.tar.gz && rm bedtools-2.29.2.tar.gz && cd bedtools2 && make && make install && cd .. 
      wget https://github.com/arq5x/bedtools2/releases/download/v2.29.2/bedtools-2.29.2.tar.gz &&\
      tar -xzf bedtools-2.29.2.tar.gz &&\
      rm bedtools-2.29.2.tar.gz &&\
      cd bedtools2 &&\
      make &&\
      make install &&\
      cd ..
