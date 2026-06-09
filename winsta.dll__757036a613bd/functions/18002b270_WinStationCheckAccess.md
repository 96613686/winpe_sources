# WinStationCheckAccess

- ea: `0x18002b270`
- end: `0x18002b297`
- name: `WinStationCheckAccess`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b28a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b28a`

## string_xrefs

- `0x18002b274`: `!!! WinStationCheckAccess deprecated`

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
0x18002b270  sub     rsp, 28h
0x18002b274  lea     rdx, aWinstationchec_4; "!!! WinStationCheckAccess deprecated"
0x18002b27b  mov     ecx, 4; int
0x18002b280  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b285  mov     ecx, 1; dwErrCode
0x18002b28a  call    cs:__imp_SetLastError
0x18002b290  xor     al, al
0x18002b292  add     rsp, 28h
0x18002b296  retn
```
