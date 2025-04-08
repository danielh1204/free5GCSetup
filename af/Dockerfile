FROM debian:bullseye-slim

RUN apt update && apt install -y bash wget net-tools nmap
WORKDIR /root
RUN mkdir ./configs
RUN mkdir /etc/certs
COPY ./configs/ ./configs
COPY ./af .
COPY ./entrypoint.sh .
COPY  ./root-ca-cert.pem  ./root-ca-cert.srl  ./root-ca-key.pem  ./server-cert.pem  ./server-key.pem  ./server-request.csr /etc/certs
RUN chmod +x ./af ./entrypoint.sh
CMD ["./entrypoint.sh"]

