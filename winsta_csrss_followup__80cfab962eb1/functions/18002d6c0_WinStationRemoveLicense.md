# WinStationRemoveLicense

- ea: `0x18002d6c0`
- end: `0x18002d6ee`
- name: `WinStationRemoveLicense`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6da`

## string_xrefs

- `0x18002d6c4`: `!!! WinStationRemoveLicense deprecated`

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
0x18002d6c0  sub     rsp, 28h
0x18002d6c4  lea     rdx, aWinstationremo_0; "!!! WinStationRemoveLicense deprecated"
0x18002d6cb  mov     ecx, 4; int
0x18002d6d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d6d5  mov     ecx, 1; dwErrCode
0x18002d6da  call    cs:__imp_SetLastError
0x18002d6e1  nop     dword ptr [rax+rax+00h]
0x18002d6e6  xor     al, al
0x18002d6e8  add     rsp, 28h
0x18002d6ec  retn
```
