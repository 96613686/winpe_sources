# WinStationInstallLicense

- ea: `0x18002b4b0`
- end: `0x18002b4d7`
- name: `WinStationInstallLicense`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b4ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b4ca`

## string_xrefs

- `0x18002b4b4`: `!!! WinStationInstallLicense deprecated`

## pseudocode

```c
char WinStationInstallLicense()
{
  _DbgPrintMessage(4, "!!! WinStationInstallLicense deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b4b0  sub     rsp, 28h
0x18002b4b4  lea     rdx, aWinstationinst_0; "!!! WinStationInstallLicense deprecated"
0x18002b4bb  mov     ecx, 4; int
0x18002b4c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b4c5  mov     ecx, 1; dwErrCode
0x18002b4ca  call    cs:__imp_SetLastError
0x18002b4d0  xor     al, al
0x18002b4d2  add     rsp, 28h
0x18002b4d6  retn
```
