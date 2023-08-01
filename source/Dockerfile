FROM archmachina/ansible-base:0.1.2

COPY --chown=ansible:ansible ./playbook/ /work

ARG BUILD_VERSION
RUN echo "$BUILD_VERSION" > /version.txt

RUN /work/exec/exec ansible_setup /work

ENTRYPOINT [ "/work/entrypoint" ]
