# _WinStationUpdateSettings

- ea: `0x18002dbc0`
- end: `0x18002dbee`
- name: `_WinStationUpdateSettings`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbda`

## string_xrefs

- `0x18002dbc4`: `!!! _WinStationUpdateSettings deprecated`

## pseudocode

```c
char WinStationUpdateSettings()
{
  _DbgPrintMessage(4, "!!! _WinStationUpdateSettings deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002dbc0  sub     rsp, 28h
0x18002dbc4  lea     rdx, aWinstationupda_4; "!!! _WinStationUpdateSettings deprecate"...
0x18002dbcb  mov     ecx, 4; int
0x18002dbd0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dbd5  mov     ecx, 1; dwErrCode
0x18002dbda  call    cs:__imp_SetLastError
0x18002dbe1  nop     dword ptr [rax+rax+00h]
0x18002dbe6  xor     al, al
0x18002dbe8  add     rsp, 28h
0x18002dbec  retn
```
