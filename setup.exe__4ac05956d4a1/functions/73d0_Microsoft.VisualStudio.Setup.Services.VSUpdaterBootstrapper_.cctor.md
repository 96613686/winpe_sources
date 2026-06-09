# Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::.cctor

- ea: `0x73d0`
- end: `0x73f4`
- name: `Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::.cctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x73d0`: `https://aka.ms/vs/setup/vsupdater`
- `0x73df`: `Automatically Update VS`
- `0x73e9`: `\Microsoft\VisualStudio\Updates`

## pseudocode

```c

```

## disassembly

```asm
0x73d0  ldstr    aHttpsAkaMsVsSe// "https://aka.ms/vs/setup/vsupdater"
0x73d5  newobj   instance void [System]System.Uri::.ctor(string)
0x73da  stsfld   class [System]System.Uri Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::DownloadUri
0x73df  ldstr    aAutomaticallyU// "Automatically Update VS"
0x73e4  stsfld   string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::VSUpdaterTaskName
0x73e9  ldstr    aMicrosoftVisua// "\\Microsoft\\VisualStudio\\Updates"
0x73ee  stsfld   string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::VSUpdaterTaskDirectory
0x73f3  ret
```
