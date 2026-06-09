# ATL::CRegObject::ClearReplacements(void)

- ea: `0x140003370`
- end: `0x1400033ab`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400032c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003398`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003384`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003384`

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
0x140003370  mov     [rsp+arg_0], rbx
0x140003375  push    rdi
0x140003376  sub     rsp, 20h
0x14000337a  lea     rdi, [rcx+20h]
0x14000337e  mov     rbx, rcx
0x140003381  mov     rcx, rdi; lpCriticalSection
0x140003384  call    cs:__imp_EnterCriticalSection
0x14000338a  lea     rcx, [rbx+8]; this
0x14000338e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140003393  mov     rcx, rdi; lpCriticalSection
0x140003396  mov     ebx, eax
0x140003398  call    cs:__imp_LeaveCriticalSection
0x14000339e  mov     eax, ebx
0x1400033a0  mov     rbx, [rsp+28h+arg_0]
0x1400033a5  add     rsp, 20h
0x1400033a9  pop     rdi
0x1400033aa  retn
```
