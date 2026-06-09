# UbpmUtilsWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180035bc0`
- end: `0x180035c0a`
- name: `?UbpmUtilsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `74`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019d90`
- `0x180035bc0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180035bd6`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180035bd6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180035c03`

## pseudocode

```c
void __fastcall UbpmUtilsWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _BYTE *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  _BYTE *v5; // rbx

  v5 = Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 8;
  (*((void (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))v5 + 2))(*((_QWORD *)v5 + 1), Context, 0, WaitResult);
  UBPM_MIDL_user_free(v5);
  CloseThreadpoolWait(Wait);
}

```

## disassembly

```asm
0x180035bc0  mov     [rsp+arg_0], rbx
0x180035bc5  push    rdi
0x180035bc6  sub     rsp, 20h
0x180035bca  test    byte ptr [rdx+18h], 1
0x180035bce  mov     rdi, r8
0x180035bd1  mov     rbx, rdx
0x180035bd4  jz      short loc_180035BDC
0x180035bd6  call    cs:__imp_CallbackMayRunLong
0x180035bdc  mov     rcx, [rbx+8]
0x180035be0  xor     r8d, r8d
0x180035be3  mov     rax, [rbx+10h]
0x180035be7  mov     dl, 8
0x180035be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bee  mov     rcx, rbx
0x180035bf1  call    UBPM_MIDL_user_free
0x180035bf6  mov     rcx, rdi
0x180035bf9  mov     rbx, [rsp+28h+arg_0]
0x180035bfe  add     rsp, 20h
0x180035c02  pop     rdi
0x180035c03  jmp     cs:__imp_CloseThreadpoolWait
```
