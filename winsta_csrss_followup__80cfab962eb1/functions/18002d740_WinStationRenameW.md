# WinStationRenameW

- ea: `0x18002d740`
- end: `0x18002d76e`
- name: `WinStationRenameW`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d75a`

## string_xrefs

- `0x18002d744`: `!!! WinStationRenameW deprecated`

## pseudocode

```c
char WinStationRenameW()
{
  _DbgPrintMessage(4, "!!! WinStationRenameW deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002d740  sub     rsp, 28h
0x18002d744  lea     rdx, aWinstationrena_1; "!!! WinStationRenameW deprecated"
0x18002d74b  mov     ecx, 4; int
0x18002d750  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d755  mov     ecx, 1; dwErrCode
0x18002d75a  call    cs:__imp_SetLastError
0x18002d761  nop     dword ptr [rax+rax+00h]
0x18002d766  xor     al, al
0x18002d768  add     rsp, 28h
0x18002d76c  retn
```
