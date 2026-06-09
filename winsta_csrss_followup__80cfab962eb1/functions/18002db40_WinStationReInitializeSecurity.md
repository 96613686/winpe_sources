# _WinStationReInitializeSecurity

- ea: `0x18002db40`
- end: `0x18002db6e`
- name: `_WinStationReInitializeSecurity`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002db5a`

## string_xrefs

- `0x18002db44`: `!!! _WinStationReInitializeSecurity deprecated`

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
0x18002db40  sub     rsp, 28h
0x18002db44  lea     rdx, aWinstationrein_0; "!!! _WinStationReInitializeSecurity dep"...
0x18002db4b  mov     ecx, 4; int
0x18002db50  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db55  mov     ecx, 1; dwErrCode
0x18002db5a  call    cs:__imp_SetLastError
0x18002db61  nop     dword ptr [rax+rax+00h]
0x18002db66  xor     al, al
0x18002db68  add     rsp, 28h
0x18002db6c  retn
```
