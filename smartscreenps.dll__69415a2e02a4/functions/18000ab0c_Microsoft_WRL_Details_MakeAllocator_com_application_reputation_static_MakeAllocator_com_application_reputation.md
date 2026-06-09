# Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(void)

- ea: `0x18000ab0c`
- end: `0x18000ab28`
- name: `??1?$MakeAllocator@Vapplication_reputation_static@com@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a100`
- `0x18000d1a0`

## callees

- `0x180001960`
- `0x18000ab0c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(
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
0x18000ab0c  sub     rsp, 28h
0x18000ab10  mov     rcx, [rcx]; void *
0x18000ab13  test    rcx, rcx
0x18000ab16  jz      short loc_18000AB22
0x18000ab18  mov     edx, 1; unsigned __int64
0x18000ab1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab22  add     rsp, 28h
0x18000ab26  retn
```
