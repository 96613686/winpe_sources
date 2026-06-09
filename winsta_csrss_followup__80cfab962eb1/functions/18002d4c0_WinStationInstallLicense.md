# WinStationInstallLicense

- ea: `0x18002d4c0`
- end: `0x18002d4ee`
- name: `WinStationInstallLicense`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d4da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d4da`

## string_xrefs

- `0x18002d4c4`: `!!! WinStationInstallLicense deprecated`

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
0x18002d4c0  sub     rsp, 28h
0x18002d4c4  lea     rdx, aWinstationinst_0; "!!! WinStationInstallLicense deprecated"
0x18002d4cb  mov     ecx, 4; int
0x18002d4d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d4d5  mov     ecx, 1; dwErrCode
0x18002d4da  call    cs:__imp_SetLastError
0x18002d4e1  nop     dword ptr [rax+rax+00h]
0x18002d4e6  xor     al, al
0x18002d4e8  add     rsp, 28h
0x18002d4ec  retn
```
