# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003010`
- end: `0x18000304b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002f58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003024`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003038`

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
0x180003010  mov     [rsp+arg_0], rbx
0x180003015  push    rdi
0x180003016  sub     rsp, 20h
0x18000301a  lea     rdi, [rcx+20h]
0x18000301e  mov     rbx, rcx
0x180003021  mov     rcx, rdi; lpCriticalSection
0x180003024  call    cs:__imp_EnterCriticalSection
0x18000302a  lea     rcx, [rbx+8]; this
0x18000302e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003033  mov     rcx, rdi; lpCriticalSection
0x180003036  mov     ebx, eax
0x180003038  call    cs:__imp_LeaveCriticalSection
0x18000303e  mov     eax, ebx
0x180003040  mov     rbx, [rsp+28h+arg_0]
0x180003045  add     rsp, 20h
0x180003049  pop     rdi
0x18000304a  retn
```
