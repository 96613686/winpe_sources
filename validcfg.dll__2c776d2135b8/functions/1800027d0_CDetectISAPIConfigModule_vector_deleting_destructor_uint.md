# CDetectISAPIConfigModule::`vector deleting destructor'(uint)

- ea: `0x1800027d0`
- end: `0x1800027f6`
- name: `??_ECDetectISAPIConfigModule@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(CDetectISAPIConfigModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001820`
- `0x1800027d0`

## pseudocode

```c
CDetectISAPIConfigModule *__fastcall CDetectISAPIConfigModule::`vector deleting destructor'(
        CDetectISAPIConfigModule *this,
        char a2)
{
  *(_QWORD *)this = &CHttpModule::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800027d0  push    rbx
0x1800027d2  sub     rsp, 20h
0x1800027d6  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x1800027dd  mov     rbx, rcx
0x1800027e0  mov     [rcx], rax
0x1800027e3  test    dl, 1
0x1800027e6  jz      short loc_1800027ED
0x1800027e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800027ed  mov     rax, rbx
0x1800027f0  add     rsp, 20h
0x1800027f4  pop     rbx
0x1800027f5  retn
```
