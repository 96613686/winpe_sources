# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1800137b0`
- end: `0x1800137eb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800136f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800137d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800137d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137c4`

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
0x1800137b0  mov     [rsp+arg_0], rbx
0x1800137b5  push    rdi
0x1800137b6  sub     rsp, 20h
0x1800137ba  lea     rdi, [rcx+20h]
0x1800137be  mov     rbx, rcx
0x1800137c1  mov     rcx, rdi; lpCriticalSection
0x1800137c4  call    cs:__imp_EnterCriticalSection
0x1800137ca  lea     rcx, [rbx+8]; this
0x1800137ce  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800137d3  mov     rcx, rdi; lpCriticalSection
0x1800137d6  mov     ebx, eax
0x1800137d8  call    cs:__imp_LeaveCriticalSection
0x1800137de  mov     eax, ebx
0x1800137e0  mov     rbx, [rsp+28h+arg_0]
0x1800137e5  add     rsp, 20h
0x1800137e9  pop     rdi
0x1800137ea  retn
```
