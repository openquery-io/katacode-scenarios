# Creating a Synthetic Database

Now that we have our Synth container - let's create a synthetic database.

You'll only need the `synth` which is pre-installed in the container. `synth` needs read-only access to your database and will always communicate the data which it's going to extract and ship from your database.

In this example we've got a database for you!

To run `synth` simply type:

```bash
synth train --database postgres \
            --host todo:5432 \
            --username user \
            --schema tpch \
			--deploy
```

Now you'll be prompted for the password (if you're scripting you can specify it using the `--password` flag)

`synth` is now training a model on our TPCH schema - understading it's relations and distributions and classifying PII which will be marked as sensitive.

Data which is marked as PII will never leave your infrastrucutre, `synth` uses bespoke data generators to populate the synthetic database. Data which is not marked as PII will be sampled from and used in the synthetic database.

And believe it or not, that's it!

Your database should now be reachable.
