# _WinStationUpdateClientCachedCredentials

- ea: `0x18002db80`
- end: `0x18002dbae`
- name: `_WinStationUpdateClientCachedCredentials`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db9a`

## string_xrefs

- `0x18002db84`: `!!! _WinStationUpdateClientCachedCredentials deprecated`

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
0x18002db80  sub     rsp, 28h
0x18002db84  lea     rdx, aWinstationupda_2; "!!! _WinStationUpdateClientCachedCreden"...
0x18002db8b  mov     ecx, 4; int
0x18002db90  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db95  mov     ecx, 1; dwErrCode
0x18002db9a  call    cs:__imp_SetLastError
0x18002dba1  nop     dword ptr [rax+rax+00h]
0x18002dba6  xor     al, al
0x18002dba8  add     rsp, 28h
0x18002dbac  retn
```
