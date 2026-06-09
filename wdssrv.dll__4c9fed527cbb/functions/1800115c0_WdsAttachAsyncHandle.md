# WdsAttachAsyncHandle

- ea: `0x1800115c0`
- end: `0x1800115f2`
- name: `WdsAttachAsyncHandle`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013ee8`

## import_xrefs

- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800115d5`
- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800115d5`

## pseudocode

```c
__int64 __fastcall WdsAttachAsyncHandle(void *a1)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8

  v1 = CCompPort::Attach((CCompPort *)qword_180039238, a1, (struct ICpRecvRequest *)&qword_180039230);
  return ElValidateWin32_5(v1, v2, v3, 127);
}

```

## disassembly

```asm
0x1800115c0  sub     rsp, 28h
0x1800115c4  mov     rdx, rcx
0x1800115c7  lea     r8, qword_180039230
0x1800115ce  lea     rcx, qword_180039238
0x1800115d5  call    cs:__imp_?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z; CCompPort::Attach(void *,ICpRecvRequest *)
0x1800115dc  nop     dword ptr [rax+rax+00h]
0x1800115e1  mov     ecx, eax
0x1800115e3  mov     r9d, 7Fh
0x1800115e9  add     rsp, 28h
0x1800115ed  jmp     ElValidateWin32_5
```
