# CSBESec::~CSBESec(void)

- ea: `0x180053088`
- end: `0x1800530dd`
- name: `??1CSBESec@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CSBESec *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009830`
- `0x18000a90c`
- `0x18000aadc`
- `0x18000eb30`
- `0x180014f20`
- `0x180053520`

## callees

- `0x180053088`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800530c2`
- `KERNEL32!LocalFree` at `0x1800530d1`
- `KERNEL32!LocalFree` at `0x1800530c2`
- `KERNEL32!LocalFree` at `0x1800530d1`
- `ADVAPI32!FreeSid` at `0x1800530a4`
- `ADVAPI32!FreeSid` at `0x1800530b3`
- `ADVAPI32!FreeSid` at `0x1800530a4`
- `ADVAPI32!FreeSid` at `0x1800530b3`

## pseudocode

```c
void __fastcall CSBESec::~CSBESec(CSBESec *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CSBESec::`vftable';
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
    FreeSid(v2);
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
    FreeSid(v3);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    LocalFree(v4);
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    LocalFree(v5);
}

```

## disassembly

```asm
0x180053088  push    rbx
0x18005308a  sub     rsp, 20h
0x18005308e  lea     rax, ??_7CSBESec@@6B@; const CSBESec::`vftable'
0x180053095  mov     rbx, rcx
0x180053098  mov     [rcx], rax
0x18005309b  mov     rcx, [rcx+30h]; pSid
0x18005309f  test    rcx, rcx
0x1800530a2  jz      short loc_1800530AA
0x1800530a4  call    cs:__imp_FreeSid
0x1800530aa  mov     rcx, [rbx+40h]; pSid
0x1800530ae  test    rcx, rcx
0x1800530b1  jz      short loc_1800530B9
0x1800530b3  call    cs:__imp_FreeSid
0x1800530b9  mov     rcx, [rbx+8]; hMem
0x1800530bd  test    rcx, rcx
0x1800530c0  jz      short loc_1800530C8
0x1800530c2  call    cs:__imp_LocalFree
0x1800530c8  mov     rcx, [rbx+48h]; hMem
0x1800530cc  test    rcx, rcx
0x1800530cf  jz      short loc_1800530D7
0x1800530d1  call    cs:__imp_LocalFree
0x1800530d7  add     rsp, 20h
0x1800530db  pop     rbx
0x1800530dc  retn
```
