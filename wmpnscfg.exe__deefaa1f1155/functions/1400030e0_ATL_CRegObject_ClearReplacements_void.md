# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1400030e0`
- end: `0x14000311b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000302c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400030f4`
- `KERNEL32!EnterCriticalSection` at `0x1400030f4`
- `KERNEL32!LeaveCriticalSection` at `0x140003108`
- `KERNEL32!LeaveCriticalSection` at `0x140003108`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  unsigned int v3; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400030e0  mov     [rsp+arg_0], rbx
0x1400030e5  push    rdi
0x1400030e6  sub     rsp, 20h
0x1400030ea  lea     rdi, [rcx+20h]
0x1400030ee  mov     rbx, rcx
0x1400030f1  mov     rcx, rdi; lpCriticalSection
0x1400030f4  call    cs:__imp_EnterCriticalSection
0x1400030fa  lea     rcx, [rbx+8]; this
0x1400030fe  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140003103  mov     rcx, rdi; lpCriticalSection
0x140003106  mov     ebx, eax
0x140003108  call    cs:__imp_LeaveCriticalSection
0x14000310e  mov     eax, ebx
0x140003110  mov     rbx, [rsp+28h+arg_0]
0x140003115  add     rsp, 20h
0x140003119  pop     rdi
0x14000311a  retn
```
