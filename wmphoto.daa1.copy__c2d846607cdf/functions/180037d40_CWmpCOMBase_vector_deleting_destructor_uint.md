# CWmpCOMBase::`vector deleting destructor'(uint)

- ea: `0x180037d40`
- end: `0x180037d6b`
- name: `??_ECWmpCOMBase@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(CWmpCOMBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180036264`
- `0x180037d40`

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
0x180037d40  push    rbx
0x180037d42  sub     rsp, 20h
0x180037d46  lea     rax, ??_7CWmpCOMBase@@6B@; const CWmpCOMBase::`vftable'
0x180037d4d  mov     rbx, rcx
0x180037d50  mov     [rcx], rax
0x180037d53  test    dl, 1
0x180037d56  jz      short loc_180037D62
0x180037d58  mov     edx, 10h; unsigned __int64
0x180037d5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037d62  mov     rax, rbx
0x180037d65  add     rsp, 20h
0x180037d69  pop     rbx
0x180037d6a  retn
```
