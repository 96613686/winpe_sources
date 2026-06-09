# CWcnThreadpoolSession::FinishDisconnectCbThunk(void *,void *,void *)

- ea: `0x1800567b0`
- end: `0x1800567db`
- name: `?FinishDisconnectCbThunk@CWcnThreadpoolSession@@CAXPEAX00@Z`
- size: `43`
- prototype: `void __fastcall(void *, PTP_WORK *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015db4`
- `0x1800567b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800567c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800567c6`

## pseudocode

```c
void __fastcall CWcnThreadpoolSession::FinishDisconnectCbThunk(void *a1, PTP_WORK *a2, void *a3)
{
  if ( a2 )
  {
    WaitForThreadpoolWorkCallbacks(a2[9], 1);
    CWcnSession::FinishDisconnect(a2[2]);
  }
}

```

## disassembly

```asm
0x1800567b0  test    rdx, rdx
0x1800567b3  jz      short locret_1800567DA
0x1800567b5  push    rbx
0x1800567b6  sub     rsp, 20h
0x1800567ba  mov     rbx, rdx
0x1800567bd  mov     edx, 1; fCancelPendingCallbacks
0x1800567c2  mov     rcx, [rbx+48h]; pwk
0x1800567c6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800567cc  mov     rcx, [rbx+10h]; this
0x1800567d0  call    ?FinishDisconnect@CWcnSession@@QEAAXXZ; CWcnSession::FinishDisconnect(void)
0x1800567d5  add     rsp, 20h
0x1800567d9  pop     rbx
0x1800567da  retn
```
