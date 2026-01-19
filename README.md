## About

SPHA is a fully automated tool suite that assesses and communicates all aspects
of software product quality. It does so by combining data about your projects
from sources like ticketing systems, and static analysis tools. For more details
see [software-product.health](https://www.software-product.health).

## Usage

This action wraps the [SPHA CLI](https://github.com/Fraunhofer-IEM/spha)
and allows you to run it in your GitHub Actions workflows. For the most current usage examples see the CLI documentation.

Basic usage:
```github-actions
 spha:
    needs: [toolA, toolB] # replace with your tool stages
    runs-on: ubuntu-latest
    steps:
      - name: Download scanner results
        uses: actions/download-artifact@latest
      - name: Display structure of downloaded files
        run: ls -R

      - name: Run SPHA Calculate
        uses: fraunhofer-iem/spha-action/spha-calculate-action@latest
        with:
         version: latest
         args: analyze --toolResultDir . --output kpis.json
```

## License

Copyright (C) Fraunhofer IEM.
Software Product Health Assistant (SPHA) and all its components are published under the MIT license.
