# _WinStationReInitializeSecurity

- ea: `0x18002b990`
- end: `0x18002b9b7`
- name: `_WinStationReInitializeSecurity`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9aa`

## string_xrefs

- `0x18002b994`: `!!! _WinStationReInitializeSecurity deprecated`

## pseudocode

```c
char WinStationReInitializeSecurity()
{
  _DbgPrintMessage(4, "!!! _WinStationReInitializeSecurity deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b990  sub     rsp, 28h
0x18002b994  lea     rdx, aWinstationrein_0; "!!! _WinStationReInitializeSecurity dep"...
0x18002b99b  mov     ecx, 4; int
0x18002b9a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b9a5  mov     ecx, 1; dwErrCode
0x18002b9aa  call    cs:__imp_SetLastError
0x18002b9b0  xor     al, al
0x18002b9b2  add     rsp, 28h
0x18002b9b6  retn
```
