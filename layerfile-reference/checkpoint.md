# CHECKPOINT 

`CHECKPOINT (name)` or `CHECKPOINT disabled`

The `CHECKPOINT` instruction allows you to control exactly when webapp.io will take snapshots of the pipeline.

On future runs, if no files or instructions have changed since the snapshot was taken, the runner will restore the snapshot instead of repeating work.

`CHECKPOINT` is not usually required, it's advised not to use it unless you are using the API or there is measurable performance benefit to doing so.

### Examples

- Use `CHECKPOINT disabled` to disable checkpointing from that point onwards
- Use `CHECKPOINT deploy` to create a checkpoint named "deploy", which can be triggered as a lambda from [our api](/docs/api#create-a-ci-job-for-a-given-repository)
- Use `CHECKPOINT` to expliticly take a checkpoint at a specific point (which happens automatically by default), or re-enable checkpointing after `CHECKPOINT disabled`

See [the tuning performance documentation](/docs/tuning-performance) for more details.
