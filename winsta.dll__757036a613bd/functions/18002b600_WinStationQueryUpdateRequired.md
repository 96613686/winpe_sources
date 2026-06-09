# WinStationQueryUpdateRequired

- ea: `0x18002b600`
- end: `0x18002b627`
- name: `WinStationQueryUpdateRequired`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b61a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b61a`

## string_xrefs

- `0x18002b604`: `!!! WinStationQueryUpdateRequired deprecated`

## pseudocode

```c
char WinStationQueryUpdateRequired()
{
  _DbgPrintMessage(4, "!!! WinStationQueryUpdateRequired deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b600  sub     rsp, 28h
0x18002b604  lea     rdx, aWinstationquer_14; "!!! WinStationQueryUpdateRequired depre"...
0x18002b60b  mov     ecx, 4; int
0x18002b610  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b615  mov     ecx, 1; dwErrCode
0x18002b61a  call    cs:__imp_SetLastError
0x18002b620  xor     al, al
0x18002b622  add     rsp, 28h
0x18002b626  retn
```
