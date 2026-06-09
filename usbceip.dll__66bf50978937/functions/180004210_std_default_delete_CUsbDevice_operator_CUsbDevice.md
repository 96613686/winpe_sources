# std::default_delete<CUsbDevice>::operator()(CUsbDevice *)

- ea: `0x180004210`
- end: `0x180004238`
- name: `??R?$default_delete@VCUsbDevice@@@std@@QEBAXPEAVCUsbDevice@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, CUsbDevice *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004108`
- `0x1800097ec`
- `0x1800099cc`

## callees

- `0x180002434`
- `0x1800041b4`
- `0x180004210`

## pseudocode

```c
void __fastcall std::default_delete<CUsbDevice>::operator()(__int64 a1, CUsbDevice *a2)
{
  if ( a2 )
  {
    CUsbDevice::~CUsbDevice(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180004210  test    rdx, rdx
0x180004213  jz      short locret_180004237
0x180004215  push    rbx
0x180004216  sub     rsp, 20h
0x18000421a  mov     rcx, rdx; this
0x18000421d  mov     rbx, rdx
0x180004220  call    ??1CUsbDevice@@QEAA@XZ; CUsbDevice::~CUsbDevice(void)
0x180004225  mov     edx, 68h ; 'h'
0x18000422a  mov     rcx, rbx; Block
0x18000422d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004232  add     rsp, 20h
0x180004236  pop     rbx
0x180004237  retn
```
