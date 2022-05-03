# pre-commit-hooks
Pre commit hooks


Motivation by (https://werner-dijkerman.nl/2021/06/24/write-your-own-pre-commit-hooks/)

Copied from Werner:

- no-commit-on-branch.sh

### R-specific stuff

Copied bump_r_package_version from Robert M Flight (github.com/rmflight)

Caveat: In the [pre-commit version](https://github.com/pre-commit/pre-commit/commit/764a0db68e0ef52a4fc08898347a6ea8da204ee3) used with Python 3.7, Rscript was not located properly, see also (https://github.com/pre-commit/pre-commit/issues/2300). This took me quite some time. And I still have to add `.exe` by myself...


    def _rscript_exec() -> str:
      r_home = os.environ.get('R_HOME')
      if r_home is None:
          return 'Rscript'
      else:
          return os.path.join(r_home, 'bin', 'Rscript.exe')
