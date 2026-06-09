# _WinStationUpdateClientCachedCredentials

- ea: `0x18002b9c0`
- end: `0x18002b9e7`
- name: `_WinStationUpdateClientCachedCredentials`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9da`

## string_xrefs

- `0x18002b9c4`: `!!! _WinStationUpdateClientCachedCredentials deprecated`

## pseudocode

```c
char WinStationUpdateClientCachedCredentials()
{
  _DbgPrintMessage(4, "!!! _WinStationUpdateClientCachedCredentials deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b9c0  sub     rsp, 28h
0x18002b9c4  lea     rdx, aWinstationupda_2; "!!! _WinStationUpdateClientCachedCreden"...
0x18002b9cb  mov     ecx, 4; int
0x18002b9d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b9d5  mov     ecx, 1; dwErrCode
0x18002b9da  call    cs:__imp_SetLastError
0x18002b9e0  xor     al, al
0x18002b9e2  add     rsp, 28h
0x18002b9e6  retn
```
