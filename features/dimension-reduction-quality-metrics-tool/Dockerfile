FROM polusai/bfio:2.3.6

# environment variables defined in polusai/bfio
ENV EXEC_DIR="/opt/executables"
ENV POLUS_IMG_EXT=".ome.tif"
ENV POLUS_TAB_EXT=".feather"
ENV POLUS_LOG="INFO"

# Work directory defined in the base container
WORKDIR ${EXEC_DIR}

# TODO: Change the tool_dir to the tool directory
ENV TOOL_DIR="features/dimension-reduction-quality-metrics-tool"

# Copy the repository into the container
RUN mkdir tabular-tools
COPY . ${EXEC_DIR}/tabular-tools

# Install the tool
RUN pip3 install "${EXEC_DIR}/tabular-tools/${TOOL_DIR}" --no-cache-dir

# Set the entrypoint
# TODO: Change the entrypoint to the tool entrypoint
ENTRYPOINT ["python3", "-m", "polus.tabular.features.dimension_reduction_quality_metrics"]
CMD ["--help"]
