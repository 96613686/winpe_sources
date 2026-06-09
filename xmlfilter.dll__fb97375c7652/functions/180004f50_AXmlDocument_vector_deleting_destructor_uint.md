# AXmlDocument::`vector deleting destructor'(uint)

- ea: `0x180004f50`
- end: `0x180004f9d`
- name: `??_EAXmlDocument@@UEAAPEAXI@Z`
- size: `77`
- prototype: `AXmlDocument *__fastcall(AXmlDocument *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18000213c`
- `0x180004f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f76`

## pseudocode

```c
AXmlDocument *__fastcall AXmlDocument::`vector deleting destructor'(AXmlDocument *this, char a2)
{
  char *v4; // rcx

  *(_QWORD *)this = &AXmlDocument::`vftable';
  v4 = (char *)*((_QWORD *)this + 8);
  if ( v4 != (char *)this + 24 )
    free(v4);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004f50  mov     [rsp+arg_0], rbx
0x180004f55  push    rdi
0x180004f56  sub     rsp, 20h
0x180004f5a  mov     rbx, rcx
0x180004f5d  lea     rax, ??_7AXmlDocument@@6B@; const AXmlDocument::`vftable'
0x180004f64  mov     [rcx], rax
0x180004f67  mov     edi, edx
0x180004f69  mov     rcx, [rcx+40h]; Block
0x180004f6d  lea     rax, [rbx+18h]
0x180004f71  cmp     rcx, rax
0x180004f74  jz      short loc_180004F7C
0x180004f76  call    cs:__imp_free
0x180004f7c  test    dil, 1
0x180004f80  jz      short loc_180004F8F
0x180004f82  mov     edx, 48h ; 'H'
0x180004f87  mov     rcx, rbx; Block
0x180004f8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004f8f  mov     rax, rbx
0x180004f92  mov     rbx, [rsp+28h+arg_0]
0x180004f97  add     rsp, 20h
0x180004f9b  pop     rdi
0x180004f9c  retn
```
