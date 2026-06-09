# ATL::CAutoVectorPtr<ushort>::~CAutoVectorPtr<ushort>(void)

- ea: `0x180002204`
- end: `0x180002222`
- name: `??1?$CAutoVectorPtr@G@ATL@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004fc6`
- `0x180004fd8`

## callees

- `0x180001534`

## pseudocode

```c
void __fastcall ATL::CAutoVectorPtr<unsigned short>::~CAutoVectorPtr<unsigned short>(void **a1)
{
  operator delete(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180002204  push    rbx
0x180002206  sub     rsp, 20h
0x18000220a  mov     rbx, rcx
0x18000220d  mov     rcx, [rcx]; Block
0x180002210  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002215  mov     qword ptr [rbx], 0
0x18000221c  add     rsp, 20h
0x180002220  pop     rbx
0x180002221  retn
```
