# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180008d70`
- end: `0x180008dab`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008cbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d84`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  int v3; // edx
  unsigned int v4; // r8d

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3, v4);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008d70  mov     [rsp+arg_0], rbx
0x180008d75  push    rdi
0x180008d76  sub     rsp, 20h
0x180008d7a  lea     rdi, [rcx+20h]
0x180008d7e  mov     rbx, rcx
0x180008d81  mov     rcx, rdi; lpCriticalSection
0x180008d84  call    cs:__imp_EnterCriticalSection
0x180008d8a  lea     rcx, [rbx+8]; this
0x180008d8e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180008d93  mov     rcx, rdi; lpCriticalSection
0x180008d96  mov     ebx, eax
0x180008d98  call    cs:__imp_LeaveCriticalSection
0x180008d9e  mov     eax, ebx
0x180008da0  mov     rbx, [rsp+28h+arg_0]
0x180008da5  add     rsp, 20h
0x180008da9  pop     rdi
0x180008daa  retn
```
