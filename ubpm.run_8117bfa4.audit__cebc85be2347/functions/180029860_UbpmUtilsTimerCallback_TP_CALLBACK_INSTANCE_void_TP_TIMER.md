# UbpmUtilsTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180029860`
- end: `0x1800298be`
- name: `?UbpmUtilsTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `94`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000fbf0`
- `0x180029860`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180029876`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180029876`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800298a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800298a6`

## pseudocode

```c
void __fastcall UbpmUtilsTimerCallback(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context, PTP_TIMER Timer)
{
  _BYTE *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9

  v4 = Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 1;
  (*((void (__fastcall **)(_QWORD, _BYTE *, _QWORD))v4 + 2))(*((_QWORD *)v4 + 1), Context, *((_QWORD *)v4 + 4));
  if ( (v4[24] & 2) == 0 )
  {
    UBPM_MIDL_user_free(v4, v5, v6, v7);
    CloseThreadpoolTimer(Timer);
  }
}

```

## disassembly

```asm
0x180029860  mov     [rsp+arg_0], rbx
0x180029865  push    rdi
0x180029866  sub     rsp, 20h
0x18002986a  test    byte ptr [rdx+18h], 1
0x18002986e  mov     rdi, r8
0x180029871  mov     rbx, rdx
0x180029874  jz      short loc_180029882
0x180029876  call    cs:__imp_CallbackMayRunLong
0x18002987d  nop     dword ptr [rax+rax+00h]
0x180029882  mov     r8, [rbx+20h]
0x180029886  mov     dl, 1
0x180029888  mov     rcx, [rbx+8]
0x18002988c  mov     rax, [rbx+10h]
0x180029890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029895  test    byte ptr [rbx+18h], 2
0x180029899  jnz     short loc_1800298B2
0x18002989b  mov     rcx, rbx
0x18002989e  call    UBPM_MIDL_user_free
0x1800298a3  mov     rcx, rdi; pti
0x1800298a6  call    cs:__imp_CloseThreadpoolTimer
0x1800298ad  nop     dword ptr [rax+rax+00h]
0x1800298b2  mov     rbx, [rsp+28h+arg_0]
0x1800298b7  add     rsp, 20h
0x1800298bb  pop     rdi
0x1800298bc  retn
```
