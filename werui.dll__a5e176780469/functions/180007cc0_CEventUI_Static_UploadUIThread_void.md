# CEventUI::Static_UploadUIThread(void *)

- ea: `0x180007cc0`
- end: `0x180007cd5`
- name: `?Static_UploadUIThread@CEventUI@@CAKPEAX@Z`
- size: `21`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007cc0`
- `0x180008cd0`

## pseudocode

```c
__int64 __fastcall CEventUI::Static_UploadUIThread(CEventUI *Parameter)
{
  if ( Parameter )
    CEventUI::UploadUIThread(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180007cc0  sub     rsp, 28h
0x180007cc4  test    rcx, rcx
0x180007cc7  jz      short loc_180007CCE
0x180007cc9  call    ?UploadUIThread@CEventUI@@AEAAXXZ; CEventUI::UploadUIThread(void)
0x180007cce  xor     eax, eax
0x180007cd0  add     rsp, 28h
0x180007cd4  retn
```
