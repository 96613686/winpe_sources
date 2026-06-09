# ATL::CComCreator<ATL::CComObject<CSdrRestoreService>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a460`
- end: `0x18000a580`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCSdrRestoreService@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0a0`

## callees

- `0x180001578`
- `0x180009cd0`
- `0x18000a460`
- `0x18000af28`
- `0x18000df34`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a4cd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a4cd`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CSdrRestoreService>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  RTL_SRWLOCK *v7; // rax
  volatile signed __int32 *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // r8d
  volatile signed __int32 *v11; // rdi
  signed __int32 v12; // edx
  union _SLIST_HEADER *v13; // rcx
  int v14; // eax
  int v15; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (RTL_SRWLOCK *)operator new(0x40u);
  v8 = (volatile signed __int32 *)v7;
  if ( v7 )
  {
    LODWORD(v7[1].Ptr) = 1668698962;
    LODWORD(v7[2].Ptr) = 0;
    v7[4].Ptr = 0;
    v7[5].Ptr = qword_180028260;
    v7[6].Ptr = 0;
    InitializeSRWLock(v7 + 7);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CSdrRestoreService>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = 0x7FFFFFFF;
    v11 = v8 + 4;
    while ( 1 )
    {
      v12 = *v11;
      if ( *v11 == 0x7FFFFFFF )
        break;
      if ( v12 == _InterlockedCompareExchange(v11, v12 + 1, v12) )
      {
        v10 = v12 + 1;
        break;
      }
    }
    v13 = (union _SLIST_HEADER *)*((_QWORD *)v8 + 4);
    if ( v13 )
      CSxRefTraceList::CaptureStackTrace(v13, v10);
    v14 = CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct((__int64)(v8 + 4));
    v15 = 0;
    if ( v14 < 0 )
      v15 = v14;
    v6 = 0;
    if ( v15 < 0 )
      v6 = v15;
    CSdrRestoreService::InternalFinalConstructRelease((CSdrRestoreService *)v8);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile signed __int32 *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a460  push    rbx
0x18000a462  push    rbp
0x18000a463  push    rsi
0x18000a464  push    rdi
0x18000a465  sub     rsp, 28h
0x18000a469  mov     rsi, r8
0x18000a46c  mov     rbp, rdx
0x18000a46f  test    r8, r8
0x18000a472  jnz     short loc_18000A47E
0x18000a474  mov     eax, 80004003h
0x18000a479  jmp     loc_18000A577
0x18000a47e  mov     ecx, 40h ; '@'; Size
0x18000a483  mov     qword ptr [r8], 0
0x18000a48a  mov     edi, 8007000Eh
0x18000a48f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a494  mov     rbx, rax
0x18000a497  test    rax, rax
0x18000a49a  jz      loc_18000A575
0x18000a4a0  mov     dword ptr [rax+8], 63765352h
0x18000a4a7  lea     rcx, [rbx+38h]; SRWLock
0x18000a4ab  mov     dword ptr [rax+10h], 0
0x18000a4b2  mov     qword ptr [rax+20h], 0
0x18000a4ba  lea     rax, qword_180028260
0x18000a4c1  mov     [rbx+28h], rax
0x18000a4c5  mov     qword ptr [rbx+30h], 0
0x18000a4cd  call    cs:__imp_InitializeSRWLock
0x18000a4d3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a4da  lea     rax, ??_7?$CComObject@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComObject<CSdrRestoreService>::`vftable'
0x18000a4e1  mov     [rbx], rax
0x18000a4e4  mov     rax, [rcx]
0x18000a4e7  mov     rax, [rax+8]
0x18000a4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f0  mov     r8d, 7FFFFFFFh
0x18000a4f6  lea     rdi, [rbx+10h]
0x18000a4fa  jmp     short loc_18000A507
0x18000a4fc  lea     ecx, [rdx+1]
0x18000a4ff  mov     eax, edx
0x18000a501  lock cmpxchg [rdi], ecx
0x18000a505  jz      short loc_18000A510
0x18000a507  mov     edx, [rdi]
0x18000a509  cmp     edx, r8d
0x18000a50c  jnz     short loc_18000A4FC
0x18000a50e  jmp     short loc_18000A514
0x18000a510  lea     r8d, [rdx+1]
0x18000a514  mov     rcx, [rdi+10h]; this
0x18000a518  test    rcx, rcx
0x18000a51b  jz      short loc_18000A525
0x18000a51d  mov     edx, r8d; unsigned int
0x18000a520  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000a525  mov     rcx, rdi
0x18000a528  call    ?_AtlInitialConstruct@?$CSxComObjectRootEx@VCSdrRestoreService@@VCComMultiThreadModelNoCS@ATL@@@@IEAAJXZ; CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(void)
0x18000a52d  xor     ecx, ecx
0x18000a52f  test    eax, eax
0x18000a531  cmovs   ecx, eax
0x18000a534  xor     edi, edi
0x18000a536  test    ecx, ecx
0x18000a538  cmovs   edi, ecx
0x18000a53b  mov     rcx, rbx; this
0x18000a53e  call    ?InternalFinalConstructRelease@CSdrRestoreService@@QEAAXXZ; CSdrRestoreService::InternalFinalConstructRelease(void)
0x18000a543  test    edi, edi
0x18000a545  jnz     short loc_18000A561
0x18000a547  mov     rax, [rbx]
0x18000a54a  mov     r8, rsi
0x18000a54d  mov     rdx, rbp
0x18000a550  mov     rcx, rbx
0x18000a553  mov     rax, [rax]
0x18000a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a55b  mov     edi, eax
0x18000a55d  test    eax, eax
0x18000a55f  jz      short loc_18000A575
0x18000a561  mov     rdx, [rbx]
0x18000a564  mov     rcx, rbx
0x18000a567  mov     rax, [rdx+38h]
0x18000a56b  mov     edx, 1
0x18000a570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a575  mov     eax, edi
0x18000a577  add     rsp, 28h
0x18000a57b  pop     rdi
0x18000a57c  pop     rsi
0x18000a57d  pop     rbp
0x18000a57e  pop     rbx
0x18000a57f  retn
```
