# URL_AUTHZ_META_STORED_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x1800026c0`
- end: `0x18000272d`
- name: `??_GURL_AUTHZ_META_STORED_CONTEXT@@EEAAPEAXI@Z`
- size: `109`
- prototype: `void *__fastcall(URL_AUTHZ_META_STORED_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001048`
- `0x180002588`
- `0x1800026c0`

## pseudocode

```c
URL_AUTHZ_META_STORED_CONTEXT *__fastcall URL_AUTHZ_META_STORED_CONTEXT::`scalar deleting destructor'(
        URL_AUTHZ_META_STORED_CONTEXT *this,
        char a2)
{
  URL_AUTHZ_RULE_ENTRY **v3; // rdi
  URL_AUTHZ_RULE_ENTRY *v5; // rbx
  URL_AUTHZ_RULE_ENTRY *v6; // rax

  *(_QWORD *)this = &URL_AUTHZ_META_STORED_CONTEXT::`vftable';
  v3 = (URL_AUTHZ_RULE_ENTRY **)((char *)this + 8);
  while ( 1 )
  {
    v5 = *v3;
    if ( *v3 == (URL_AUTHZ_RULE_ENTRY *)v3 )
      break;
    if ( *((URL_AUTHZ_RULE_ENTRY ***)v5 + 1) != v3
      || (v6 = *(URL_AUTHZ_RULE_ENTRY **)v5, *(URL_AUTHZ_RULE_ENTRY **)(*(_QWORD *)v5 + 8LL) != v5) )
    {
      __fastfail(3u);
    }
    *v3 = v6;
    *((_QWORD *)v6 + 1) = v3;
    URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(v5);
    operator delete(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800026c0  push    rbx
0x1800026c2  push    rbp
0x1800026c3  push    rsi
0x1800026c4  push    rdi
0x1800026c5  sub     rsp, 28h
0x1800026c9  lea     rax, ??_7URL_AUTHZ_META_STORED_CONTEXT@@6B@; const URL_AUTHZ_META_STORED_CONTEXT::`vftable'
0x1800026d0  mov     ebp, edx
0x1800026d2  mov     [rcx], rax
0x1800026d5  lea     rdi, [rcx+8]
0x1800026d9  mov     rsi, rcx
0x1800026dc  mov     rbx, [rdi]
0x1800026df  cmp     rbx, rdi
0x1800026e2  jz      short loc_180002713
0x1800026e4  cmp     [rbx+8], rdi
0x1800026e8  jnz     short loc_18000270C
0x1800026ea  mov     rax, [rbx]
0x1800026ed  cmp     [rax+8], rbx
0x1800026f1  jnz     short loc_18000270C
0x1800026f3  mov     [rdi], rax
0x1800026f6  mov     rcx, rbx; this
0x1800026f9  mov     [rax+8], rdi
0x1800026fd  call    ??1URL_AUTHZ_RULE_ENTRY@@QEAA@XZ; URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(void)
0x180002702  mov     rcx, rbx; Block
0x180002705  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000270a  jmp     short loc_1800026DC
0x18000270c  mov     ecx, 3
0x180002711  int     29h; Win8: RtlFailFast(ecx)
0x180002713  test    bpl, 1
0x180002717  jz      short loc_180002721
0x180002719  mov     rcx, rsi; Block
0x18000271c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002721  mov     rax, rsi
0x180002724  add     rsp, 28h
0x180002728  pop     rdi
0x180002729  pop     rsi
0x18000272a  pop     rbp
0x18000272b  pop     rbx
0x18000272c  retn
```
