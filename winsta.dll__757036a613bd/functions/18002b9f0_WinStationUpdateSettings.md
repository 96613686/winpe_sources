# _WinStationUpdateSettings

- ea: `0x18002b9f0`
- end: `0x18002ba17`
- name: `_WinStationUpdateSettings`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba0a`

## string_xrefs

- `0x18002b9f4`: `!!! _WinStationUpdateSettings deprecated`

## pseudocode

```c
char WinStationUpdateSettings()
{
  _DbgPrintMessage(4, "!!! _WinStationUpdateSettings deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b9f0  sub     rsp, 28h
0x18002b9f4  lea     rdx, aWinstationupda_4; "!!! _WinStationUpdateSettings deprecate"...
0x18002b9fb  mov     ecx, 4; int
0x18002ba00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba05  mov     ecx, 1; dwErrCode
0x18002ba0a  call    cs:__imp_SetLastError
0x18002ba10  xor     al, al
0x18002ba12  add     rsp, 28h
0x18002ba16  retn
```
