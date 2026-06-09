# _WinStationBeepOpen

- ea: `0x1800289c0`
- end: `0x1800289fb`
- name: `_WinStationBeepOpen`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005fcc`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800289ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800289ee`

## string_xrefs

- `0x1800289c4`: `_WinStationBeepOpen`
- `0x1800289d1`: `_WinStationBeepOpen failed: 0x%x in %s`

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
0x1800289c0  sub     rsp, 28h
0x1800289c4  lea     r9, aWinstationbeep_0; "_WinStationBeepOpen"
0x1800289cb  mov     r8d, 80004001h
0x1800289d1  lea     rdx, aWinstationbeep_1; "_WinStationBeepOpen failed: 0x%x in %s"
0x1800289d8  mov     ecx, 8; int
0x1800289dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800289e2  mov     ecx, 80004001h; int
0x1800289e7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800289ec  mov     ecx, eax; dwErrCode
0x1800289ee  call    cs:__imp_SetLastError
0x1800289f4  xor     eax, eax
0x1800289f6  add     rsp, 28h
0x1800289fa  retn
```
