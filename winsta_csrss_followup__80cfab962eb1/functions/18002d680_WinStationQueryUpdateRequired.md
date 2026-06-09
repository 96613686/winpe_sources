# WinStationQueryUpdateRequired

- ea: `0x18002d680`
- end: `0x18002d6ae`
- name: `WinStationQueryUpdateRequired`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d69a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d69a`

## string_xrefs

- `0x18002d684`: `!!! WinStationQueryUpdateRequired deprecated`

## pseudocode

```c
char WinStationQueryUpdateRequired()
{
  _DbgPrintMessage(4, "!!! WinStationQueryUpdateRequired deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002d680  sub     rsp, 28h
0x18002d684  lea     rdx, aWinstationquer_14; "!!! WinStationQueryUpdateRequired depre"...
0x18002d68b  mov     ecx, 4; int
0x18002d690  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d695  mov     ecx, 1; dwErrCode
0x18002d69a  call    cs:__imp_SetLastError
0x18002d6a1  nop     dword ptr [rax+rax+00h]
0x18002d6a6  xor     al, al
0x18002d6a8  add     rsp, 28h
0x18002d6ac  retn
```
