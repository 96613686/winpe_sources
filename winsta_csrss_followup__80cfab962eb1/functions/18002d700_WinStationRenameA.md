# WinStationRenameA

- ea: `0x18002d700`
- end: `0x18002d72e`
- name: `WinStationRenameA`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d71a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d71a`

## string_xrefs

- `0x18002d704`: `!!! WinStationRenameA deprecated`

## pseudocode

```c
char WinStationRenameA()
{
  _DbgPrintMessage(4, "!!! WinStationRenameA deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002d700  sub     rsp, 28h
0x18002d704  lea     rdx, aWinstationrena_2; "!!! WinStationRenameA deprecated"
0x18002d70b  mov     ecx, 4; int
0x18002d710  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d715  mov     ecx, 1; dwErrCode
0x18002d71a  call    cs:__imp_SetLastError
0x18002d721  nop     dword ptr [rax+rax+00h]
0x18002d726  xor     al, al
0x18002d728  add     rsp, 28h
0x18002d72c  retn
```
