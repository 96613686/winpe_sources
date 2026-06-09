# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)

- ea: `0x140012794`
- end: `0x1400127b0`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140030e80`
- `0x140030f0c`
- `0x140030fd8`
- `0x14003109c`
- `0x140037e64`
- `0x14003a4c0`
- `0x140065740`
- `0x1400657f2`
- `0x140066043`
- `0x1400660a8`
- `0x140066df0`
- `0x14006726d`

## callees

- `0x140012794`
- `0x140027084`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)1);
}

```

## disassembly

```asm
0x140012794  sub     rsp, 28h
0x140012798  mov     rcx, [rcx]; void *
0x14001279b  test    rcx, rcx
0x14001279e  jz      short loc_1400127AA
0x1400127a0  mov     edx, 1; struct std::nothrow_t *
0x1400127a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400127aa  add     rsp, 28h
0x1400127ae  retn
```
