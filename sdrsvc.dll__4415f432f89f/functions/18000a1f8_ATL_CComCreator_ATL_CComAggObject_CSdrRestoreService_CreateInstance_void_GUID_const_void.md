# ATL::CComCreator<ATL::CComAggObject<CSdrRestoreService>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a1f8`
- end: `0x18000a300`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCSdrRestoreService@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0a0`

## callees

- `0x180001578`
- `0x18000a1f8`
- `0x18000df34`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a27b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a27b`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CSdrRestoreService>>::CreateInstance(
        void *a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *v9; // rbx
  struct ATL::CAtlModule *v10; // rcx
  int v11; // eax
  int v12; // ecx
  int v13; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (RTL_SRWLOCK *)operator new(0x58u);
  v9 = v8;
  if ( v8 )
  {
    LODWORD(v8[1].Ptr) = 0;
    LODWORD(v8[4].Ptr) = 1668698962;
    v8->Ptr = &ATL::CComAggObject<CSdrRestoreService>::`vftable';
    v8[8].Ptr = qword_180028260;
    LODWORD(v8[5].Ptr) = 0;
    v8[7].Ptr = 0;
    v8[9].Ptr = 0;
    InitializeSRWLock(v8 + 10);
    v10 = ATL::_pAtlModule;
    v9[3].Ptr = &ATL::CComContainedObject<CSdrRestoreService>::`vftable';
    v9[5].Ptr = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct((__int64)&v9[5]);
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD *))v9->Ptr)(v9, a2, a3)) != 0 )
      (*((void (__fastcall **)(RTL_SRWLOCK *, __int64))v9->Ptr + 3))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000a1f8  push    rbx
0x18000a1fa  push    rbp
0x18000a1fb  push    rsi
0x18000a1fc  push    rdi
0x18000a1fd  push    r14
0x18000a1ff  sub     rsp, 20h
0x18000a203  mov     rsi, r8
0x18000a206  mov     rbp, rdx
0x18000a209  mov     r14, rcx
0x18000a20c  test    r8, r8
0x18000a20f  jnz     short loc_18000A21B
0x18000a211  mov     eax, 80004003h
0x18000a216  jmp     loc_18000A2F5
0x18000a21b  mov     ecx, 58h ; 'X'; Size
0x18000a220  mov     qword ptr [r8], 0
0x18000a227  mov     edi, 8007000Eh
0x18000a22c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a231  mov     rbx, rax
0x18000a234  test    rax, rax
0x18000a237  jz      loc_18000A2F3
0x18000a23d  mov     dword ptr [rax+8], 0
0x18000a244  lea     rcx, [rbx+50h]; SRWLock
0x18000a248  lea     rax, ??_7?$CComAggObject@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComAggObject<CSdrRestoreService>::`vftable'
0x18000a24f  mov     dword ptr [rbx+20h], 63765352h
0x18000a256  mov     [rbx], rax
0x18000a259  lea     rax, qword_180028260
0x18000a260  mov     [rbx+40h], rax
0x18000a264  mov     dword ptr [rbx+28h], 0
0x18000a26b  mov     qword ptr [rbx+38h], 0
0x18000a273  mov     qword ptr [rbx+48h], 0
0x18000a27b  call    cs:__imp_InitializeSRWLock
0x18000a281  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a288  lea     rax, ??_7?$CComContainedObject@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComContainedObject<CSdrRestoreService>::`vftable'
0x18000a28f  mov     [rbx+18h], rax
0x18000a293  mov     [rbx+28h], r14
0x18000a297  mov     rax, [rcx]
0x18000a29a  mov     rax, [rax+8]
0x18000a29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a3  lea     rcx, [rbx+28h]
0x18000a2a7  call    ?_AtlInitialConstruct@?$CSxComObjectRootEx@VCSdrRestoreService@@VCComMultiThreadModelNoCS@ATL@@@@IEAAJXZ; CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(void)
0x18000a2ac  xor     ecx, ecx
0x18000a2ae  test    eax, eax
0x18000a2b0  cmovs   ecx, eax
0x18000a2b3  xor     eax, eax
0x18000a2b5  test    ecx, ecx
0x18000a2b7  cmovs   eax, ecx
0x18000a2ba  xor     edi, edi
0x18000a2bc  test    eax, eax
0x18000a2be  cmovs   edi, eax
0x18000a2c1  test    edi, edi
0x18000a2c3  jnz     short loc_18000A2DF
0x18000a2c5  mov     rax, [rbx]
0x18000a2c8  mov     r8, rsi
0x18000a2cb  mov     rdx, rbp
0x18000a2ce  mov     rcx, rbx
0x18000a2d1  mov     rax, [rax]
0x18000a2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d9  mov     edi, eax
0x18000a2db  test    eax, eax
0x18000a2dd  jz      short loc_18000A2F3
0x18000a2df  mov     rcx, [rbx]
0x18000a2e2  mov     edx, 1
0x18000a2e7  mov     rax, [rcx+18h]
0x18000a2eb  mov     rcx, rbx
0x18000a2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f3  mov     eax, edi
0x18000a2f5  add     rsp, 20h
0x18000a2f9  pop     r14
0x18000a2fb  pop     rdi
0x18000a2fc  pop     rsi
0x18000a2fd  pop     rbp
0x18000a2fe  pop     rbx
0x18000a2ff  retn
```
