# CThirdPartyManager::~CThirdPartyManager(void)

- ea: `0x18003677c`
- end: `0x180036804`
- name: `??1CThirdPartyManager@@UEAA@XZ`
- size: `136`
- prototype: `void __fastcall(CThirdPartyManager *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180036420`
- `0x180036840`
- `0x1800397a8`
- `0x180039b40`

## callees

- `0x180009f40`
- `0x180018b20`
- `0x18003677c`
- `0x18003680c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036799`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036799`

## pseudocode

```c
void __fastcall CThirdPartyManager::~CThirdPartyManager(CThirdPartyManager *this)
{
  bool v1; // zf
  __int64 v3; // rcx
  void (__fastcall ***Next)(_QWORD, __int64); // rax
  void *v5; // rcx
  __int64 HeadPosition; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 2) == 0;
  *(_QWORD *)this = &CThirdPartyManager::`vftable';
  if ( !v1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(v3);
    while ( HeadPosition )
    {
      Next = (void (__fastcall ***)(_QWORD, __int64))CList<CExternalBase *,CExternalBase *>::GetNext(
                                                       *((_QWORD *)this + 7),
                                                       &HeadPosition);
      if ( Next )
        (**Next)(Next, 1);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
      CList<CExternalBase *,CExternalBase *>::`scalar deleting destructor'(v5);
  }
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x18003677c  push    rbx
0x18003677e  sub     rsp, 20h
0x180036782  cmp     dword ptr [rcx+8], 0
0x180036786  lea     rax, ??_7CThirdPartyManager@@6B@; const CThirdPartyManager::`vftable'
0x18003678d  mov     [rcx], rax
0x180036790  mov     rbx, rcx
0x180036793  jz      short loc_18003679F
0x180036795  add     rcx, 10h; lpCriticalSection
0x180036799  call    cs:__imp_DeleteCriticalSection
0x18003679f  mov     rcx, [rbx+38h]
0x1800367a3  test    rcx, rcx
0x1800367a6  jz      short loc_1800367F6
0x1800367a8  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x1800367ad  mov     [rsp+28h+arg_0], rax
0x1800367b2  test    rax, rax
0x1800367b5  jz      short loc_1800367E8
0x1800367b7  mov     rcx, [rbx+38h]
0x1800367bb  lea     rdx, [rsp+28h+arg_0]
0x1800367c0  call    ?GetNext@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAPEAVCExternalBase@@AEAPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::GetNext(_CListElement * &)
0x1800367c5  mov     r9, rax
0x1800367c8  test    rax, rax
0x1800367cb  jz      short loc_1800367E0
0x1800367cd  mov     rcx, [rax]
0x1800367d0  mov     edx, 1
0x1800367d5  mov     rax, [rcx]
0x1800367d8  mov     rcx, r9
0x1800367db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367e0  cmp     [rsp+28h+arg_0], 0
0x1800367e6  jnz     short loc_1800367B7
0x1800367e8  mov     rcx, [rbx+38h]; Block
0x1800367ec  test    rcx, rcx
0x1800367ef  jz      short loc_1800367F6
0x1800367f1  call    ??_G?$CList@PEAVCExternalBase@@PEAV1@@@QEAAPEAXI@Z; CList<CExternalBase *,CExternalBase *>::`scalar deleting destructor'(uint)
0x1800367f6  mov     qword ptr [rbx+38h], 0
0x1800367fe  add     rsp, 20h
0x180036802  pop     rbx
0x180036803  retn
```
