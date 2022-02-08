# TERN Ontology

The TERN Ontology is an OWL Ontology with SHACL profiles to facilitate the exchange of ecological survey data between different systems.

Online Documentation: https://linkeddata.tern.org.au/information-models/tern-ontology

## Source files

Source files are maintained as N-Triples files and they are located in the [docs/](docs/) directory as files ending in `.nt`.

> Only edit the source files directly using TopBraid Composer. Other RDF serializations will be generated by ontotools, a CLI app.

## Version control

The main branch (master) is the working branch of the TERN Ontology. Changes must be made in another branch along with a GitHub pull request to merge into the main branch.

Each push to a branch will trigger GitHub Actions to run validations and tests. These validations and tests must pass before the branch can be merged into the main branch.

## Releases

The TERN Ontology makes GitHub Releases for each version. See [TERN Ontology releases](https://github.com/ternaustralia/ontology_tern/releases) for a list of releases.

## Editing the TERN Ontology

We use ontotools, a Python command line application to normalize the source files and generate the other RDF serializations from it.

Ensure the following instructions are performed whenever edits are made to the source files.

### Create a Python 3 virtual environment

```bash
python3 -m venv venv
```

### Activate the virtual environment

```bash
source venv/bin/activate
```

### Install the required packages

```bash
pip install -r requirements.txt
```

### Change into the docs directory

```bash
cd docs
```

### Run ontotools to normalize the source file for TERN Ontology

This will normalize the `tern.nt` file and generate the other RDF serializations.

```bash
ontotools file normalize tern.nt --generate-formats
```

### Run ontotools to normalize the source file for TERN Ontology TERN Ontology SHACL shapes

This will normalize the `tern.shacl.nt` file and generate the other RDF serializations.

```bash
ontotools file normalize tern.shacl.nt --generate-formats
```

## Making modifications

- Bump the version number in the ontology, the version information, and the modified date.
- Enter the new changes into `CHANGELOG.md` following the conventions of semantic versioning.

Each version should:

- List its release date in the above format.
- Group changes to describe their impact on the project, as follows:
- `Added` for new features.
- `Changed` for changes in existing functionality.
- `Deprecated` for once-stable features removed in upcoming releases.
- `Removed` for deprecated features removed in this release.
- `Fixed` for any bug fixes.
- `Security` to invite users to upgrade in case of vulnerabilities.

## Contact

**Edmond Chuc**  
e.chuc@uq.edu.au
