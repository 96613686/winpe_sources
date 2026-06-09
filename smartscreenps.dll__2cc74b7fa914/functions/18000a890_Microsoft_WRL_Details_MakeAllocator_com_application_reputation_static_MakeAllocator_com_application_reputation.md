# Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(void)

- ea: `0x18000a890`
- end: `0x18000a8a6`
- name: `??1?$MakeAllocator@Vapplication_reputation_static@com@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009ec0`
- `0x18000cebf`

## callees

- `0x1800019d0`
- `0x18000a890`

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
0x18000a890  sub     rsp, 28h
0x18000a894  mov     rcx, [rcx]; Block
0x18000a897  test    rcx, rcx
0x18000a89a  jz      short loc_18000A8A1
0x18000a89c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a8a1  add     rsp, 28h
0x18000a8a5  retn
```
