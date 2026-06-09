# _WinStationBeepOpen

- ea: `0x18002a590`
- end: `0x18002a5d2`
- name: `_WinStationBeepOpen`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004558`
- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a5be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a5be`

## string_xrefs

- `0x18002a594`: `_WinStationBeepOpen`
- `0x18002a5a1`: `_WinStationBeepOpen failed: 0x%x in %s`

## pseudocode

```c
__int64 WinStationBeepOpen()
{
  DWORD v0; // eax

  _DbgPrintMessage(8, "_WinStationBeepOpen failed: 0x%x in %s", -2147467263, "_WinStationBeepOpen");
  v0 = ConvertHRESULT2WIN32(-2147467263);
  SetLastError(v0);
  return 0;
}

```

## disassembly

```asm
0x18002a590  sub     rsp, 28h
0x18002a594  lea     r9, aWinstationbeep_0; "_WinStationBeepOpen"
0x18002a59b  mov     r8d, 80004001h
0x18002a5a1  lea     rdx, aWinstationbeep_1; "_WinStationBeepOpen failed: 0x%x in %s"
0x18002a5a8  mov     ecx, 8; int
0x18002a5ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a5b2  mov     ecx, 80004001h; int
0x18002a5b7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002a5bc  mov     ecx, eax; dwErrCode
0x18002a5be  call    cs:__imp_SetLastError
0x18002a5c5  nop     dword ptr [rax+rax+00h]
0x18002a5ca  xor     eax, eax
0x18002a5cc  add     rsp, 28h
0x18002a5d0  retn
```
