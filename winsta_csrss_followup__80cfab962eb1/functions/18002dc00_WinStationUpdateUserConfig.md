# _WinStationUpdateUserConfig

- ea: `0x18002dc00`
- end: `0x18002dc2e`
- name: `_WinStationUpdateUserConfig`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc1a`

## string_xrefs

- `0x18002dc04`: `!!! _WinStationUpdateUserConfig deprecated`

## pseudocode

```c
char WinStationUpdateUserConfig()
{
  _DbgPrintMessage(4, "!!! _WinStationUpdateUserConfig deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002dc00  sub     rsp, 28h
0x18002dc04  lea     rdx, aWinstationupda_3; "!!! _WinStationUpdateUserConfig depreca"...
0x18002dc0b  mov     ecx, 4; int
0x18002dc10  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dc15  mov     ecx, 1; dwErrCode
0x18002dc1a  call    cs:__imp_SetLastError
0x18002dc21  nop     dword ptr [rax+rax+00h]
0x18002dc26  xor     al, al
0x18002dc28  add     rsp, 28h
0x18002dc2c  retn
```
