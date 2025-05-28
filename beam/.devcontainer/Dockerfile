FROM pytorch/pytorch:2.7.0-cuda12.8-cudnn9-devel

RUN apt-get update && apt-get install -y --no-install-recommends git \
    && rm -rf /var/lib/apt/lists/*

RUN mamba install -y pandas matplotlib ultralytics=8.3.143 \
    && conda clean --all --yes \
    && rm -rf /root/.cache/conda

RUN mkdir -p /root/.config/Ultralytics && chmod 777 /root/.config/Ultralytics

CMD ["bash"]
