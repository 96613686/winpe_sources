# QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),CAddRemoveSynchronizer *)

- ea: `0x180022e44`
- end: `0x180022e8e`
- name: `?QueueWorkItem@@YAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAVCAddRemoveSynchronizer@@@Z`
- size: `74`
- prototype: `void __fastcall(void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), struct CAddRemoveSynchronizer *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180022b78`
- `0x180022cc0`

## callees

- `0x180022e44`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022e7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022e7d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022e74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022e74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022e54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022e54`

## pseudocode

```c
void __fastcall QueueWorkItem(
        void (*a1)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *),
        struct CAddRemoveSynchronizer *a2)
{
  struct _TP_WORK *ThreadpoolWork; // rdi

  ThreadpoolWork = CreateThreadpoolWork(a1, a2, 0);
  if ( ThreadpoolWork )
  {
    (*(void (__fastcall **)(struct CAddRemoveSynchronizer *))(*(_QWORD *)a2 + 8LL))(a2);
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(ThreadpoolWork);
  }
}

```

## disassembly

```asm
0x180022e44  mov     [rsp+arg_0], rbx
0x180022e49  push    rdi
0x180022e4a  sub     rsp, 20h
0x180022e4e  xor     r8d, r8d; pcbe
0x180022e51  mov     rbx, rdx
0x180022e54  call    cs:__imp_CreateThreadpoolWork
0x180022e5a  mov     rdi, rax
0x180022e5d  test    rax, rax
0x180022e60  jz      short loc_180022E83
0x180022e62  mov     rcx, [rbx]
0x180022e65  mov     rax, [rcx+8]
0x180022e69  mov     rcx, rbx
0x180022e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e71  mov     rcx, rdi; pwk
0x180022e74  call    cs:__imp_SubmitThreadpoolWork
0x180022e7a  mov     rcx, rdi; pwk
0x180022e7d  call    cs:__imp_CloseThreadpoolWork
0x180022e83  mov     rbx, [rsp+28h+arg_0]
0x180022e88  add     rsp, 20h
0x180022e8c  pop     rdi
0x180022e8d  retn
```
