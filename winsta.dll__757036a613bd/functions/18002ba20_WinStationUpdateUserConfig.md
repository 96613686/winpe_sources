# _WinStationUpdateUserConfig

- ea: `0x18002ba20`
- end: `0x18002ba47`
- name: `_WinStationUpdateUserConfig`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba3a`

## string_xrefs

- `0x18002ba24`: `!!! _WinStationUpdateUserConfig deprecated`

## pseudocode

```c
char WinStationUpdateUserConfig()
{
  _DbgPrintMessage(4, "!!! _WinStationUpdateUserConfig deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002ba20  sub     rsp, 28h
0x18002ba24  lea     rdx, aWinstationupda_3; "!!! _WinStationUpdateUserConfig depreca"...
0x18002ba2b  mov     ecx, 4; int
0x18002ba30  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba35  mov     ecx, 1; dwErrCode
0x18002ba3a  call    cs:__imp_SetLastError
0x18002ba40  xor     al, al
0x18002ba42  add     rsp, 28h
0x18002ba46  retn
```
