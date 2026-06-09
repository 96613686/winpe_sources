# WdsQueueWorkItem

- ea: `0x180011a90`
- end: `0x180011ac6`
- name: `WdsQueueWorkItem`
- size: `54`
- prototype: `__int64 __fastcall(struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800049b4`

## callees

- `0x180013ee8`

## import_xrefs

- `WdsServerCommonLib!?Post@CCompPort@@QEAAKPEAVICpRecvRequest@@KPEAU_OVERLAPPED@@@Z` at `0x180011aa9`
- `WdsServerCommonLib!?Post@CCompPort@@QEAAKPEAVICpRecvRequest@@KPEAU_OVERLAPPED@@@Z` at `0x180011aa9`

## pseudocode

```c
__int64 __fastcall WdsQueueWorkItem(struct _OVERLAPPED *a1)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8

  v1 = CCompPort::Post((CCompPort *)qword_180039238, (struct ICpRecvRequest *)&qword_180039230, a1[1].Offset, a1);
  return ElValidateWin32_5(v1, v2, v3, 153);
}

```

## disassembly

```asm
0x180011a90  sub     rsp, 28h
0x180011a94  mov     r8d, [rcx+30h]
0x180011a98  lea     rdx, qword_180039230
0x180011a9f  mov     r9, rcx
0x180011aa2  lea     rcx, qword_180039238
0x180011aa9  call    cs:__imp_?Post@CCompPort@@QEAAKPEAVICpRecvRequest@@KPEAU_OVERLAPPED@@@Z; CCompPort::Post(ICpRecvRequest *,ulong,_OVERLAPPED *)
0x180011ab0  nop     dword ptr [rax+rax+00h]
0x180011ab5  mov     ecx, eax
0x180011ab7  mov     r9d, 99h
0x180011abd  add     rsp, 28h
0x180011ac1  jmp     ElValidateWin32_5
```
