# UbpmUtilsWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180038140`
- end: `0x180038195`
- name: `?UbpmUtilsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `85`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000fbf0`
- `0x180038140`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180038156`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180038156`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180038189`

## pseudocode

```c
void __fastcall UbpmUtilsWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _BYTE *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  _BYTE *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9

  v5 = Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 8;
  (*((void (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))v5 + 2))(*((_QWORD *)v5 + 1), Context, 0, WaitResult);
  UBPM_MIDL_user_free(v5, v6, v7, v8);
  CloseThreadpoolWait(Wait);
}

```

## disassembly

```asm
0x180038140  mov     [rsp+arg_0], rbx
0x180038145  push    rdi
0x180038146  sub     rsp, 20h
0x18003814a  test    byte ptr [rdx+18h], 1
0x18003814e  mov     rdi, r8
0x180038151  mov     rbx, rdx
0x180038154  jz      short loc_180038162
0x180038156  call    cs:__imp_CallbackMayRunLong
0x18003815d  nop     dword ptr [rax+rax+00h]
0x180038162  mov     rcx, [rbx+8]
0x180038166  xor     r8d, r8d
0x180038169  mov     rax, [rbx+10h]
0x18003816d  mov     dl, 8
0x18003816f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038174  mov     rcx, rbx
0x180038177  call    UBPM_MIDL_user_free
0x18003817c  mov     rcx, rdi
0x18003817f  mov     rbx, [rsp+28h+arg_0]
0x180038184  add     rsp, 20h
0x180038188  pop     rdi
0x180038189  jmp     cs:__imp_CloseThreadpoolWait
```
