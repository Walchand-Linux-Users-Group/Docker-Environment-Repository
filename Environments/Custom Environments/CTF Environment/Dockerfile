FROM ubuntu:24.04

RUN apt-get update && apt-get install -y bash sudo tree curl wget && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash player

COPY blocked_commands.txt /etc/blocked_commands.txt

RUN set -eux; \
    for cmd in $(cat /etc/blocked_commands.txt); do \
        for dir in /bin /usr/bin /usr/local/bin /sbin /usr/sbin; do \
            if [ -f "$dir/$cmd" ]; then \
                echo "Removing $dir/$cmd"; \
                rm -f "$dir/$cmd"; \
            fi; \
        done; \
    done

USER player
WORKDIR /home/player

CMD ["/bin/bash"]
