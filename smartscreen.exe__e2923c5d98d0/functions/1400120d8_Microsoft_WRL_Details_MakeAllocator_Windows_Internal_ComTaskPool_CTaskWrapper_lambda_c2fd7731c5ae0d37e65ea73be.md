# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)

- ea: `0x1400120d8`
- end: `0x1400120ee`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14002fb9c`
- `0x14002fc28`
- `0x14002fcf0`
- `0x14002fdb0`
- `0x140036928`
- `0x140038ed4`
- `0x140063a80`
- `0x140063b31`
- `0x140064307`
- `0x14006436a`
- `0x14006508c`
- `0x14006547c`

## callees

- `0x1400120d8`
- `0x140025fb4`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1400120d8  sub     rsp, 28h
0x1400120dc  mov     rcx, [rcx]; Block
0x1400120df  test    rcx, rcx
0x1400120e2  jz      short loc_1400120E9
0x1400120e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400120e9  add     rsp, 28h
0x1400120ed  retn
```
