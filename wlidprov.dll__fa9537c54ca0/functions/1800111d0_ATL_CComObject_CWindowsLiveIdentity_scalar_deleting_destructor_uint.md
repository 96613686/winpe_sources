# ATL::CComObject<CWindowsLiveIdentity>::`scalar deleting destructor'(uint)

- ea: `0x1800111d0`
- end: `0x180011260`
- name: `??_G?$CComObject@VCWindowsLiveIdentity@@@ATL@@UEAAPEAXI@Z`
- size: `144`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800111d0`
- `0x18001a0f4`
- `0x18001a164`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001120b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011238`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001120b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011238`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ATL::CComObject<CWindowsLiveIdentity>::`scalar deleting destructor'(char *Block, char a2)
{
  *(_QWORD *)Block = &ATL::CComObject<CWindowsLiveIdentity>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 136));
  `eh vector destructor iterator'(
    Block + 64,
    8u,
    9u,
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>);
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800111d0  mov     [rsp+arg_0], rbx
0x1800111d5  push    rdi
0x1800111d6  sub     rsp, 20h
0x1800111da  mov     edi, edx
0x1800111dc  mov     rbx, rcx
0x1800111df  lea     rax, ??_7?$CComObject@VCWindowsLiveIdentity@@@ATL@@6B@; const ATL::CComObject<CWindowsLiveIdentity>::`vftable'
0x1800111e6  mov     [rcx], rax
0x1800111e9  mov     dword ptr [rcx+8], 0C0000001h
0x1800111f0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800111f7  mov     rax, [rcx]
0x1800111fa  mov     rax, [rax+10h]
0x1800111fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011203  nop
0x180011204  lea     rcx, [rbx+88h]; lpCriticalSection
0x18001120b  call    cs:__imp_DeleteCriticalSection
0x180011211  lea     rcx, [rbx+40h]; void *
0x180011215  lea     r9, ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; void (*)(void *)
0x18001121c  mov     edx, 8; unsigned __int64
0x180011221  lea     r8d, [rdx+1]; unsigned __int64
0x180011225  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001122a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001122e  cmp     byte ptr [rcx+28h], 0
0x180011232  jz      short loc_18001123F
0x180011234  mov     byte ptr [rcx+28h], 0
0x180011238  call    cs:__imp_DeleteCriticalSection
0x18001123e  nop
0x18001123f  test    dil, 1
0x180011243  jz      short loc_180011252
0x180011245  mov     edx, 0B0h
0x18001124a  mov     rcx, rbx; Block
0x18001124d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011252  mov     rax, rbx
0x180011255  mov     rbx, [rsp+28h+arg_0]
0x18001125a  add     rsp, 20h
0x18001125e  pop     rdi
0x18001125f  retn
```
