# RegisterUsertokenForNoWinlogon

- ea: `0x180004b60`
- end: `0x180004b76`
- name: `RegisterUsertokenForNoWinlogon`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b69`

## pseudocode

```c
__int64 RegisterUsertokenForNoWinlogon()
{
  SetLastError(0x32u);
  return 0;
}

```

## disassembly

```asm
0x180004b60  sub     rsp, 28h; QueryActiveSession
0x180004b64  mov     ecx, 32h ; '2'; dwErrCode
0x180004b69  call    cs:__imp_SetLastError
0x180004b6f  xor     eax, eax
0x180004b71  add     rsp, 28h
0x180004b75  retn
```
