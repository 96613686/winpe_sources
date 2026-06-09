# ATL::CComObjectCached<CSdrRestoreService>::CreateInstance(ATL::CComObjectCached<CSdrRestoreService> * *)

- ea: `0x18000a8fc`
- end: `0x18000aa01`
- name: `?CreateInstance@?$CComObjectCached@VCSdrRestoreService@@@ATL@@SAJPEAPEAV12@@Z`
- size: `261`
- prototype: `__int64 __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009f80`

## callees

- `0x180001554`
- `0x180001578`
- `0x180008b74`
- `0x180009cd0`
- `0x18000a8fc`
- `0x18000af28`
- `0x18000df34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a964`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a964`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CSdrRestoreService>::CreateInstance(volatile signed __int32 **a1)
{
  RTL_SRWLOCK *v3; // rax
  volatile signed __int32 *v4; // rbx
  int v5; // r8d
  volatile signed __int32 *v6; // r14
  signed __int32 v7; // edx
  union _SLIST_HEADER *v8; // rcx
  int v9; // eax
  int v10; // edx
  unsigned int v11; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (RTL_SRWLOCK *)operator new(0x40u);
  v4 = (volatile signed __int32 *)v3;
  if ( v3 )
  {
    LODWORD(v3[1].Ptr) = 1668698962;
    LODWORD(v3[2].Ptr) = 0;
    v3[4].Ptr = 0;
    v3[5].Ptr = qword_180028260;
    v3[6].Ptr = 0;
    InitializeSRWLock(v3 + 7);
    v5 = 0x7FFFFFFF;
    *(_QWORD *)v4 = &ATL::CComObjectCached<CSdrRestoreService>::`vftable';
    v6 = v4 + 4;
    while ( 1 )
    {
      v7 = *v6;
      if ( *v6 == 0x7FFFFFFF )
        break;
      if ( v7 == _InterlockedCompareExchange(v6, v7 + 1, v7) )
      {
        v5 = v7 + 1;
        break;
      }
    }
    v8 = (union _SLIST_HEADER *)*((_QWORD *)v4 + 4);
    if ( v8 )
      CSxRefTraceList::CaptureStackTrace(v8, v5);
    v9 = CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct((__int64)(v4 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    CSdrRestoreService::InternalFinalConstructRelease((CSdrRestoreService *)v4);
    if ( !v11 )
      goto LABEL_19;
    *(_QWORD *)v4 = &ATL::CComObjectCached<CSdrRestoreService>::`vftable';
    *v6 = -1073741823;
    CSdrRestoreService::~CSdrRestoreService((CSdrRestoreService *)v4);
    operator delete((void *)v4);
  }
  else
  {
    v11 = -2147024882;
  }
  v4 = 0;
LABEL_19:
  *a1 = v4;
  return v11;
}

```

## disassembly

```asm
0x18000a8fc  push    rbx
0x18000a8fe  push    rsi
0x18000a8ff  push    rdi
0x18000a900  push    r14
0x18000a902  push    r15
0x18000a904  sub     rsp, 20h
0x18000a908  mov     rsi, rcx
0x18000a90b  test    rcx, rcx
0x18000a90e  jnz     short loc_18000A91A
0x18000a910  mov     eax, 80004003h
0x18000a915  jmp     loc_18000A9F5
0x18000a91a  mov     qword ptr [rcx], 0
0x18000a921  mov     ecx, 40h ; '@'; Size
0x18000a926  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a92b  mov     rbx, rax
0x18000a92e  test    rax, rax
0x18000a931  jz      loc_18000A9E9
0x18000a937  mov     dword ptr [rax+8], 63765352h
0x18000a93e  lea     rcx, [rbx+38h]; SRWLock
0x18000a942  mov     dword ptr [rax+10h], 0
0x18000a949  mov     qword ptr [rax+20h], 0
0x18000a951  lea     rax, qword_180028260
0x18000a958  mov     [rbx+28h], rax
0x18000a95c  mov     qword ptr [rbx+30h], 0
0x18000a964  call    cs:__imp_InitializeSRWLock
0x18000a96a  lea     r15, ??_7?$CComObjectCached@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComObjectCached<CSdrRestoreService>::`vftable'
0x18000a971  mov     r8d, 7FFFFFFFh
0x18000a977  mov     [rbx], r15
0x18000a97a  lea     r14, [rbx+10h]
0x18000a97e  jmp     short loc_18000A98C
0x18000a980  lea     ecx, [rdx+1]
0x18000a983  mov     eax, edx
0x18000a985  lock cmpxchg [r14], ecx
0x18000a98a  jz      short loc_18000A996
0x18000a98c  mov     edx, [r14]
0x18000a98f  cmp     edx, r8d
0x18000a992  jnz     short loc_18000A980
0x18000a994  jmp     short loc_18000A99A
0x18000a996  lea     r8d, [rdx+1]
0x18000a99a  mov     rcx, [r14+10h]; this
0x18000a99e  test    rcx, rcx
0x18000a9a1  jz      short loc_18000A9AB
0x18000a9a3  mov     edx, r8d; unsigned int
0x18000a9a6  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000a9ab  mov     rcx, r14
0x18000a9ae  call    ?_AtlInitialConstruct@?$CSxComObjectRootEx@VCSdrRestoreService@@VCComMultiThreadModelNoCS@ATL@@@@IEAAJXZ; CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(void)
0x18000a9b3  xor     edx, edx
0x18000a9b5  mov     rcx, rbx; this
0x18000a9b8  test    eax, eax
0x18000a9ba  cmovs   edx, eax
0x18000a9bd  xor     edi, edi
0x18000a9bf  test    edx, edx
0x18000a9c1  cmovs   edi, edx
0x18000a9c4  call    ?InternalFinalConstructRelease@CSdrRestoreService@@QEAAXXZ; CSdrRestoreService::InternalFinalConstructRelease(void)
0x18000a9c9  test    edi, edi
0x18000a9cb  jz      short loc_18000A9F0
0x18000a9cd  mov     rcx, rbx; this
0x18000a9d0  mov     [rbx], r15
0x18000a9d3  mov     dword ptr [r14], 0C0000001h
0x18000a9da  call    ??1CSdrRestoreService@@QEAA@XZ; CSdrRestoreService::~CSdrRestoreService(void)
0x18000a9df  mov     rcx, rbx; Block
0x18000a9e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9e7  jmp     short loc_18000A9EE
0x18000a9e9  mov     edi, 8007000Eh
0x18000a9ee  xor     ebx, ebx
0x18000a9f0  mov     [rsi], rbx
0x18000a9f3  mov     eax, edi
0x18000a9f5  add     rsp, 20h
0x18000a9f9  pop     r15
0x18000a9fb  pop     r14
0x18000a9fd  pop     rdi
0x18000a9fe  pop     rsi
0x18000a9ff  pop     rbx
0x18000aa00  retn
```
