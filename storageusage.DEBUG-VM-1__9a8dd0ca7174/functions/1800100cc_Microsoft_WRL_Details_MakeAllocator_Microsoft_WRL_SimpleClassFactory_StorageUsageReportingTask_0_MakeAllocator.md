# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(void)

- ea: `0x1800100cc`
- end: `0x1800100e2`
- name: `??1?$MakeAllocator@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000dd00`
- `0x18000dd98`
- `0x18000decc`
- `0x18002b244`

## callees

- `0x1800055f8`
- `0x1800100cc`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(
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
0x1800100cc  sub     rsp, 28h
0x1800100d0  mov     rcx, [rcx]; Block
0x1800100d3  test    rcx, rcx
0x1800100d6  jz      short loc_1800100DD
0x1800100d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800100dd  add     rsp, 28h
0x1800100e1  retn
```
