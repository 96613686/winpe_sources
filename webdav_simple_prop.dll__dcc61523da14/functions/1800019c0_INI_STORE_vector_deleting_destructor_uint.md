# INI_STORE::`vector deleting destructor'(uint)

- ea: `0x1800019c0`
- end: `0x1800019e6`
- name: `??_EINI_STORE@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(INI_STORE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800019c0`

## pseudocode

```c
INI_STORE *__fastcall INI_STORE::`vector deleting destructor'(INI_STORE *this, char a2)
{
  *(_QWORD *)this = &IPubPropertyStore::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800019c0  push    rbx
0x1800019c2  sub     rsp, 20h
0x1800019c6  lea     rax, ??_7IPubPropertyStore@@6B@; const IPubPropertyStore::`vftable'
0x1800019cd  mov     rbx, rcx
0x1800019d0  mov     [rcx], rax
0x1800019d3  test    dl, 1
0x1800019d6  jz      short loc_1800019DD
0x1800019d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800019dd  mov     rax, rbx
0x1800019e0  add     rsp, 20h
0x1800019e4  pop     rbx
0x1800019e5  retn
```
