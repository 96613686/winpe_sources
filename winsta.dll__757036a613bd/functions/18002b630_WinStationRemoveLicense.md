# WinStationRemoveLicense

- ea: `0x18002b630`
- end: `0x18002b657`
- name: `WinStationRemoveLicense`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b64a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b64a`

## string_xrefs

- `0x18002b634`: `!!! WinStationRemoveLicense deprecated`

## pseudocode

```c
char WinStationRemoveLicense()
{
  _DbgPrintMessage(4, "!!! WinStationRemoveLicense deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b630  sub     rsp, 28h
0x18002b634  lea     rdx, aWinstationremo_0; "!!! WinStationRemoveLicense deprecated"
0x18002b63b  mov     ecx, 4; int
0x18002b640  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b645  mov     ecx, 1; dwErrCode
0x18002b64a  call    cs:__imp_SetLastError
0x18002b650  xor     al, al
0x18002b652  add     rsp, 28h
0x18002b656  retn
```
