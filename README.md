## Hi there!

```nix
{ pkgs ? import <nixpkgs> {} }: let
  user = {
    name = "Glauber Santana";
    role = "Software Engineer";
    spokenLanguages = ["English" "Portuguese" "French"];
    spokenLanguagesString = builtins.concatStringsSep ", " user.spokenLanguages;
    desc = "Self taught Software Engineer, DevOps enthusiast learning how to [Go] in the [Nix] way";
  };
in
  with pkgs;
  writeTextFile {
    name = "README.md";
    text = ''
      Name: ${user.name}
      Description: ${user.desc}
      Role: ${user.role}
      Spoken Languages: ${user.spokenLanguagesString}
    '';
    # I'm sure you've learnt some amazing stuff today. Feel free to share it.
  }
```
