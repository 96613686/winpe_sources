# WinStationCheckAccess

- ea: `0x18002d1c0`
- end: `0x18002d1ee`
- name: `WinStationCheckAccess`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d1da`

## string_xrefs

- `0x18002d1c4`: `!!! WinStationCheckAccess deprecated`

## pseudocode

```c
char WinStationCheckAccess()
{
  _DbgPrintMessage(4, "!!! WinStationCheckAccess deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002d1c0  sub     rsp, 28h
0x18002d1c4  lea     rdx, aWinstationchec_4; "!!! WinStationCheckAccess deprecated"
0x18002d1cb  mov     ecx, 4; int
0x18002d1d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d1d5  mov     ecx, 1; dwErrCode
0x18002d1da  call    cs:__imp_SetLastError
0x18002d1e1  nop     dword ptr [rax+rax+00h]
0x18002d1e6  xor     al, al
0x18002d1e8  add     rsp, 28h
0x18002d1ec  retn
```
