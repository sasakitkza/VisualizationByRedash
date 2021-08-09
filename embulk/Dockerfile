FROM java:latest

# Install embulk
RUN curl -k --create-dirs -o /usr/local/bin/embulk -L "https://dl.embulk.org/embulk-latest.jar" \
    && chmod +x /usr/local/bin/embulk

# Ignoring SSL certification
RUN echo ":ssl_verify_mode: 0" >> /root/.gemrc

RUN embulk gem install embulk-input-http \
    && embulk gem install embulk-filter-timestamp_format \
    && embulk gem install embulk-filter-add_time \
    && embulk gem install embulk-filter-column \
    && embulk gem install embulk-filter-row \
    && embulk gem install embulk-filter-eval \
    && embulk gem install embulk-filter-kuromoji \
    && embulk gem install embulk-parser-jsonl \
    && embulk gem install embulk-parser-json \
    && embulk gem install embulk-parser-jsonpath \
    && embulk gem install embulk-input-mongodb \
    && embulk gem install embulk-output-mongodb \
    && embulk gem install embulk-input-command

WORKDIR /work

ENTRYPOINT ["java", "-jar", "/usr/local/bin/embulk"]
