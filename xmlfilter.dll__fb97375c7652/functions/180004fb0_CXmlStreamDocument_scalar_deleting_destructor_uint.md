# CXmlStreamDocument::`scalar deleting destructor'(uint)

- ea: `0x180004fb0`
- end: `0x180005013`
- name: `??_GCXmlStreamDocument@@UEAAPEAXI@Z`
- size: `99`
- prototype: `CXmlStreamDocument *__fastcall(CXmlStreamDocument *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x18000213c`
- `0x180004fb0`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004fec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004fec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CXmlStreamDocument *__fastcall CXmlStreamDocument::`scalar deleting destructor'(CXmlStreamDocument *this, char a2)
{
  __int64 v4; // rcx
  char *v5; // rcx

  v4 = *((_QWORD *)this + 9);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *(_QWORD *)this = &AXmlDocument::`vftable';
  v5 = (char *)*((_QWORD *)this + 8);
  if ( v5 != (char *)this + 24 )
    free(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  push    rdi
0x180004fb6  sub     rsp, 20h
0x180004fba  mov     edi, edx
0x180004fbc  mov     rbx, rcx
0x180004fbf  mov     rcx, [rcx+48h]
0x180004fc3  test    rcx, rcx
0x180004fc6  jz      short loc_180004FD5
0x180004fc8  mov     rax, [rcx]
0x180004fcb  mov     rax, [rax+10h]
0x180004fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd4  nop
0x180004fd5  lea     rax, ??_7AXmlDocument@@6B@; const AXmlDocument::`vftable'
0x180004fdc  mov     [rbx], rax
0x180004fdf  mov     rcx, [rbx+40h]; Block
0x180004fe3  lea     rax, [rbx+18h]
0x180004fe7  cmp     rcx, rax
0x180004fea  jz      short loc_180004FF2
0x180004fec  call    cs:__imp_free
0x180004ff2  test    dil, 1
0x180004ff6  jz      short loc_180005005
0x180004ff8  mov     edx, 50h ; 'P'
0x180004ffd  mov     rcx, rbx; Block
0x180005000  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005005  mov     rax, rbx
0x180005008  mov     rbx, [rsp+28h+arg_0]
0x18000500d  add     rsp, 20h
0x180005011  pop     rdi
0x180005012  retn
```
