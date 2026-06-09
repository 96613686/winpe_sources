# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180008080`
- end: `0x1800080bb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007fd0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800080a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800080a8`
- `KERNEL32!EnterCriticalSection` at `0x180008094`
- `KERNEL32!EnterCriticalSection` at `0x180008094`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8));
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008080  mov     [rsp+arg_0], rbx
0x180008085  push    rdi
0x180008086  sub     rsp, 20h
0x18000808a  lea     rdi, [rcx+20h]
0x18000808e  mov     rbx, rcx
0x180008091  mov     rcx, rdi; lpCriticalSection
0x180008094  call    cs:__imp_EnterCriticalSection
0x18000809a  lea     rcx, [rbx+8]; this
0x18000809e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800080a3  mov     rcx, rdi; lpCriticalSection
0x1800080a6  mov     ebx, eax
0x1800080a8  call    cs:__imp_LeaveCriticalSection
0x1800080ae  mov     eax, ebx
0x1800080b0  mov     rbx, [rsp+28h+arg_0]
0x1800080b5  add     rsp, 20h
0x1800080b9  pop     rdi
0x1800080ba  retn
```
