ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG=C.UTF-8
ENV HOME=/app

RUN mkdir -p $HOME
WORKDIR ${HOME}

# Python + pip
RUN apk add --no-cache python3 py3-pip

# Copy add-on files
COPY ./ ${HOME}/

# Install Python deps (PEP 668 compatible)
RUN pip3 install --no-cache-dir --break-system-packages -r requirements.txt

# Ensure run script is executable
RUN chmod a+x "$HOME/run.sh"

CMD [ "/app/run.sh" ]
