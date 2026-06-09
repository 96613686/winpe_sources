# _WinStationOpenSessionDirectory

- ea: `0x18002b960`
- end: `0x18002b987`
- name: `_WinStationOpenSessionDirectory`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b97a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b97a`

## string_xrefs

- `0x18002b964`: `!!! _WinStationOpenSessionDirectory deprecated`

## pseudocode

```c
char WinStationOpenSessionDirectory()
{
  _DbgPrintMessage(4, "!!! _WinStationOpenSessionDirectory deprecated");
  SetLastError(1u);
  return 0;
}

```

## disassembly

```asm
0x18002b960  sub     rsp, 28h
0x18002b964  lea     rdx, aWinstationopen_4; "!!! _WinStationOpenSessionDirectory dep"...
0x18002b96b  mov     ecx, 4; int
0x18002b970  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b975  mov     ecx, 1; dwErrCode
0x18002b97a  call    cs:__imp_SetLastError
0x18002b980  xor     al, al
0x18002b982  add     rsp, 28h
0x18002b986  retn
```
