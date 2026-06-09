# WinStationRenameA

- ea: `0x18002b660`
- end: `0x18002b687`
- name: `WinStationRenameA`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b67a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b67a`

## string_xrefs

- `0x18002b664`: `!!! WinStationRenameA deprecated`

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
0x18002b660  sub     rsp, 28h
0x18002b664  lea     rdx, aWinstationrena_2; "!!! WinStationRenameA deprecated"
0x18002b66b  mov     ecx, 4; int
0x18002b670  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b675  mov     ecx, 1; dwErrCode
0x18002b67a  call    cs:__imp_SetLastError
0x18002b680  xor     al, al
0x18002b682  add     rsp, 28h
0x18002b686  retn
```
