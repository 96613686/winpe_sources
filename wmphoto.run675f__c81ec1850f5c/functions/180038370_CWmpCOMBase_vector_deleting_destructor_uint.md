# CWmpCOMBase::`vector deleting destructor'(uint)

- ea: `0x180038370`
- end: `0x18003839c`
- name: `??_ECWmpCOMBase@@UEAAPEAXI@Z`
- size: `44`
- prototype: `void *__fastcall(CWmpCOMBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180036834`
- `0x180038370`

## pseudocode

```c
CWmpCOMBase *__fastcall CWmpCOMBase::`vector deleting destructor'(CWmpCOMBase *this, char a2)
{
  *(_QWORD *)this = &CWmpCOMBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180038370  push    rbx
0x180038372  sub     rsp, 20h
0x180038376  lea     rax, ??_7CWmpCOMBase@@6B@; const CWmpCOMBase::`vftable'
0x18003837d  mov     rbx, rcx
0x180038380  mov     [rcx], rax
0x180038383  test    dl, 1
0x180038386  jz      short loc_180038392
0x180038388  mov     edx, 10h; unsigned __int64
0x18003838d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038392  mov     rax, rbx
0x180038395  add     rsp, 20h
0x180038399  pop     rbx
0x18003839a  retn
```
