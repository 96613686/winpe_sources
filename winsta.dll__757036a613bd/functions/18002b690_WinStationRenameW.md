# WinStationRenameW

- ea: `0x18002b690`
- end: `0x18002b6b7`
- name: `WinStationRenameW`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b6aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b6aa`

## string_xrefs

- `0x18002b694`: `!!! WinStationRenameW deprecated`

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
0x18002b690  sub     rsp, 28h
0x18002b694  lea     rdx, aWinstationrena_1; "!!! WinStationRenameW deprecated"
0x18002b69b  mov     ecx, 4; int
0x18002b6a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b6a5  mov     ecx, 1; dwErrCode
0x18002b6aa  call    cs:__imp_SetLastError
0x18002b6b0  xor     al, al
0x18002b6b2  add     rsp, 28h
0x18002b6b6  retn
```
