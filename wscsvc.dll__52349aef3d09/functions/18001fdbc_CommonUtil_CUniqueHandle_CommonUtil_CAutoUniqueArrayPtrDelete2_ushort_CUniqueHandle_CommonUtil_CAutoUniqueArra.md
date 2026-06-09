# CommonUtil::CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>::~CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>(void)

- ea: `0x18001fdbc`
- end: `0x18001fdd2`
- name: `??1?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEAG@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fd70`
- `0x18003fd90`
- `0x18003fe30`
- `0x18003ffc0`
- `0x180040040`
- `0x180040060`
- `0x1800401c2`

## callees

- `0x18001fdbc`
- `0x180029e74`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<unsigned short *>>::~CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<unsigned short *>>(
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
0x18001fdbc  sub     rsp, 28h
0x18001fdc0  mov     rcx, [rcx]; Block
0x18001fdc3  test    rcx, rcx
0x18001fdc6  jz      short loc_18001FDCD
0x18001fdc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fdcd  add     rsp, 28h
0x18001fdd1  retn
```
