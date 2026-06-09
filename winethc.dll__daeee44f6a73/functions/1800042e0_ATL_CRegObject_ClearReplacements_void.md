# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1800042e0`
- end: `0x180004328`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004220`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000430e`
- `KERNEL32!LeaveCriticalSection` at `0x18000430e`
- `KERNEL32!EnterCriticalSection` at `0x1800042f4`
- `KERNEL32!EnterCriticalSection` at `0x1800042f4`

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
0x1800042e0  mov     [rsp+arg_0], rbx
0x1800042e5  push    rdi
0x1800042e6  sub     rsp, 20h
0x1800042ea  lea     rdi, [rcx+20h]
0x1800042ee  mov     rbx, rcx
0x1800042f1  mov     rcx, rdi; lpCriticalSection
0x1800042f4  call    cs:__imp_EnterCriticalSection
0x1800042fb  nop     dword ptr [rax+rax+00h]
0x180004300  lea     rcx, [rbx+8]; this
0x180004304  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004309  mov     rcx, rdi; lpCriticalSection
0x18000430c  mov     ebx, eax
0x18000430e  call    cs:__imp_LeaveCriticalSection
0x180004315  nop     dword ptr [rax+rax+00h]
0x18000431a  mov     eax, ebx
0x18000431c  mov     rbx, [rsp+28h+arg_0]
0x180004321  add     rsp, 20h
0x180004325  pop     rdi
0x180004326  retn
```
