FROM ipython/scipystack

MAINTAINER IPython Project <ipython-dev@scipy.org>

RUN useradd -m -s /bin/bash ipynb

USER ipynb
ENV HOME /home/ipynb
ENV SHELL /bin/bash
ENV USER ipynb

WORKDIR /home/ipynb/

# You can mount your own SSL certs as necessary here
ENV PEM_FILE /home/ipynb/key.pem

# $PASSWORD will get `unset` within notebook.sh, turned into an IPython style hash
ENV PASSWORD DontKeepTheDefault

ADD notebook.sh /home/ipynb/notebook.sh

EXPOSE 8888

CMD ["bash", "/home/ipynb/notebook.sh"]
