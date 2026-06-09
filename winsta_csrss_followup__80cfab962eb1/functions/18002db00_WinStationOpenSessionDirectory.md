# _WinStationOpenSessionDirectory

- ea: `0x18002db00`
- end: `0x18002db2e`
- name: `_WinStationOpenSessionDirectory`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db1a`

## string_xrefs

- `0x18002db04`: `!!! _WinStationOpenSessionDirectory deprecated`

## pseudocode

```c
char WinStationOpenSessionDirectory()
{
  _DbgPrintMessage(4, "!!! _WinStationOpenSessionDirectory deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002db00  sub     rsp, 28h
0x18002db04  lea     rdx, aWinstationopen_4; "!!! _WinStationOpenSessionDirectory dep"...
0x18002db0b  mov     ecx, 4; int
0x18002db10  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db15  mov     ecx, 1; dwErrCode
0x18002db1a  call    cs:__imp_SetLastError
0x18002db21  nop     dword ptr [rax+rax+00h]
0x18002db26  xor     al, al
0x18002db28  add     rsp, 28h
0x18002db2c  retn
```
