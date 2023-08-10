FROM archmachina/ansible-base:0.1.3

COPY --chown=ansible:ansible "./playbook/requirements.txt" "./playbook/requirements.yml" \
  "./playbook/ansible.cfg"  /work/
COPY --chown=ansible:ansible ./playbook/exec/ /work/exec/
RUN /work/exec/exec ansible_setup /work

COPY --chown=ansible:ansible ./playbook/ /work

ARG BUILD_VERSION
RUN echo "$BUILD_VERSION" > /version.txt

ENTRYPOINT [ "/work/entrypoint" ]
