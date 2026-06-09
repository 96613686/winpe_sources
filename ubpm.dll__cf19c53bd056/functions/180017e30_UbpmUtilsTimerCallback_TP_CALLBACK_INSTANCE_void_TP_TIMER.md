# UbpmUtilsTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180017e30`
- end: `0x180017e81`
- name: `?UbpmUtilsTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `81`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180017e30`
- `0x180019d90`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180017e46`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180017e46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e70`

## pseudocode

```c
void __fastcall UbpmUtilsTimerCallback(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context, PTP_TIMER Timer)
{
  _BYTE *v4; // rbx

  v4 = Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 1;
  (*((void (__fastcall **)(_QWORD, _BYTE *, _QWORD))v4 + 2))(*((_QWORD *)v4 + 1), Context, *((_QWORD *)v4 + 4));
  if ( (v4[24] & 2) == 0 )
  {
    UBPM_MIDL_user_free(v4);
    CloseThreadpoolTimer(Timer);
  }
}

```

## disassembly

```asm
0x180017e30  mov     [rsp+arg_0], rbx
0x180017e35  push    rdi
0x180017e36  sub     rsp, 20h
0x180017e3a  test    byte ptr [rdx+18h], 1
0x180017e3e  mov     rdi, r8
0x180017e41  mov     rbx, rdx
0x180017e44  jz      short loc_180017E4C
0x180017e46  call    cs:__imp_CallbackMayRunLong
0x180017e4c  mov     r8, [rbx+20h]
0x180017e50  mov     dl, 1
0x180017e52  mov     rcx, [rbx+8]
0x180017e56  mov     rax, [rbx+10h]
0x180017e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e5f  test    byte ptr [rbx+18h], 2
0x180017e63  jnz     short loc_180017E76
0x180017e65  mov     rcx, rbx
0x180017e68  call    UBPM_MIDL_user_free
0x180017e6d  mov     rcx, rdi; pti
0x180017e70  call    cs:__imp_CloseThreadpoolTimer
0x180017e76  mov     rbx, [rsp+28h+arg_0]
0x180017e7b  add     rsp, 20h
0x180017e7f  pop     rdi
0x180017e80  retn
```
