# std::unique_ptr<CUsbDevice,std::default_delete<CUsbDevice>>::~unique_ptr<CUsbDevice,std::default_delete<CUsbDevice>>(void)

- ea: `0x180004108`
- end: `0x18000411e`
- name: `??1?$unique_ptr@VCUsbDevice@@U?$default_delete@VCUsbDevice@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041b4`
- `0x1800105d4`

## callees

- `0x180004108`
- `0x180004210`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CUsbDevice>::~unique_ptr<CUsbDevice>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CUsbDevice>::operator()();
  return result;
}

```

## disassembly

```asm
0x180004108  sub     rsp, 28h
0x18000410c  mov     rdx, [rcx]
0x18000410f  test    rdx, rdx
0x180004112  jz      short loc_180004119
0x180004114  call    ??R?$default_delete@VCUsbDevice@@@std@@QEBAXPEAVCUsbDevice@@@Z; std::default_delete<CUsbDevice>::operator()(CUsbDevice *)
0x180004119  add     rsp, 28h
0x18000411d  retn
```
