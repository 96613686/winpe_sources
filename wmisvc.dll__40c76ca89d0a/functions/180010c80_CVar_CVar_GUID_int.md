# CVar::CVar(_GUID *,int)

- ea: `0x180010c80`
- end: `0x180010cc0`
- name: `??0CVar@@QEAA@PEAU_GUID@@H@Z`
- size: `64`
- prototype: `CVar *__fastcall(CVar *__hidden this, struct _GUID *, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!?SetClsId@CVar@@QEAAXPEAU_GUID@@H@Z` at `0x180010ca7`
- `wbemcomn!?SetClsId@CVar@@QEAAXPEAU_GUID@@H@Z` at `0x180010ca7`
- `wbemcomn!?Init@CVar@@AEAAXXZ` at `0x180010c98`
- `wbemcomn!?Init@CVar@@AEAAXXZ` at `0x180010c98`

## pseudocode

```c
CVar *__fastcall CVar::CVar(CVar *this, struct _GUID *a2, int a3)
{
  CVar::Init(this);
  CVar::SetClsId(this, a2, a3);
  return this;
}

```

## disassembly

```asm
0x180010c80  mov     [rsp+arg_0], rbx
0x180010c85  mov     [rsp+arg_8], rsi
0x180010c8a  push    rdi
0x180010c8b  sub     rsp, 20h
0x180010c8f  mov     ebx, r8d
0x180010c92  mov     rdi, rdx
0x180010c95  mov     rsi, rcx
0x180010c98  call    cs:__imp_?Init@CVar@@AEAAXXZ; CVar::Init(void)
0x180010c9e  mov     r8d, ebx
0x180010ca1  mov     rdx, rdi
0x180010ca4  mov     rcx, rsi
0x180010ca7  call    cs:__imp_?SetClsId@CVar@@QEAAXPEAU_GUID@@H@Z; CVar::SetClsId(_GUID *,int)
0x180010cad  mov     rbx, [rsp+28h+arg_0]
0x180010cb2  mov     rax, rsi
0x180010cb5  mov     rsi, [rsp+28h+arg_8]
0x180010cba  add     rsp, 20h
0x180010cbe  pop     rdi
0x180010cbf  retn
```
