# nix-store

> Manipulate or query the Nix store.
> See also: `nix store.3`.
> More information: <https://nixos.org/manual/nix/stable/command-ref/nix-store.html>.

- Collect garbage, such as removing unused paths:

`nix-store --gc`

- Hard-link identical files together to reduce space usage:

`nix-store --optimise`

- Delete a specific store path (must be unused):

`nix-store --delete /nix/store/{{checksum-package-version.ext}}`

- Show all dependencies of a store path (package), in a tree format:

`nix-store {{[-q|--query]}} --tree /nix/store/{{checksum-package-version.ext}}`

- Calculate the total size of a certain store path with all the dependencies:

`du {{[-cLsh|--total --dereference --summarize --human-readable]}} $(nix-store {{[-q|--query]}} --references /nix/store/{{checksum-package-version.ext}})`

- Show all dependents of a particular store path:

`nix-store {{[-q|--query]}} --referrers /nix/store/{{checksum-package-version.ext}}`
