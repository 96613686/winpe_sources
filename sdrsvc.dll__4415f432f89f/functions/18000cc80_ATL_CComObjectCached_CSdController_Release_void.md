# ATL::CComObjectCached<CSdController>::Release(void)

- ea: `0x18000cc80`
- end: `0x18000cd71`
- name: `?Release@?$CComObjectCached@VCSdController@@@ATL@@UEAAKXZ`
- size: `241`
- prototype: `__int64 __fastcall(CSdController *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cd80`

## callees

- `0x180001554`
- `0x180009cd0`
- `0x18000cc80`
- `0x18000f158`
- `0x18000f85c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000ccfc`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000ccfc`
- `ntdll!RtlFreeHeap` at `0x18000ccf2`
- `ntdll!RtlFreeHeap` at `0x18000ccf2`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CSdController>::Release(CSdController *this)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  signed __int32 v4; // edx
  __int64 v5; // r8
  unsigned int v6; // esi
  PSLIST_ENTRY v7; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  v4 = *((_DWORD *)this + 6);
  v5 = 0x7FFFFFFF;
  while ( v4 != 0x7FFFFFFF && v4 != _InterlockedCompareExchange((volatile signed __int32 *)this + 6, v4 - 1, v4) )
    v4 = *((_DWORD *)this + 6);
  v6 = v4 - 1;
  if ( v2 )
  {
    CSxRefTraceList::CaptureStackTrace(v2, v6);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    {
      while ( 1 )
      {
        v7 = InterlockedPopEntrySList(v2 + 1);
        if ( !v7 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v7[-17]);
      }
      operator delete(v2);
    }
  }
  if ( v6 )
  {
    if ( v6 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
        ATL::_pAtlModule,
        *(_QWORD *)ATL::_pAtlModule,
        v5);
  }
  else if ( this )
  {
    *((_DWORD *)this + 6) = -1073741823;
    *(_QWORD *)this = &ATL::CComObjectCached<CSdController>::`vftable'{for `ISdScheduledBackup'};
    *((_QWORD *)this + 1) = &ATL::CComObjectCached<CSdController>::`vftable'{for `ISdCallback2'};
    CSdController::FinalRelease(this);
    CSdController::~CSdController(this);
    operator delete(this);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cc80  push    rbx
0x18000cc82  push    rbp
0x18000cc83  push    rsi
0x18000cc84  push    rdi
0x18000cc85  sub     rsp, 28h
0x18000cc89  mov     rax, [rcx+28h]
0x18000cc8d  xor     ebx, ebx
0x18000cc8f  mov     rdi, rcx
0x18000cc92  test    rax, rax
0x18000cc95  jz      short loc_18000CC9D
0x18000cc97  lock inc dword ptr [rax]
0x18000cc9a  mov     rbx, rax
0x18000cc9d  mov     edx, [rcx+18h]
0x18000cca0  mov     r8d, 7FFFFFFFh
0x18000cca6  jmp     short loc_18000CCB7
0x18000cca8  lea     ecx, [rdx-1]
0x18000ccab  mov     eax, edx
0x18000ccad  lock cmpxchg [rdi+18h], ecx
0x18000ccb2  jz      short loc_18000CCBC
0x18000ccb4  mov     edx, [rdi+18h]
0x18000ccb7  cmp     edx, r8d
0x18000ccba  jnz     short loc_18000CCA8
0x18000ccbc  lea     esi, [rdx-1]
0x18000ccbf  test    rbx, rbx
0x18000ccc2  jz      short loc_18000CD0F
0x18000ccc4  mov     edx, esi; unsigned int
0x18000ccc6  mov     rcx, rbx; this
0x18000ccc9  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000ccce  or      eax, 0FFFFFFFFh
0x18000ccd1  lock xadd [rbx], eax
0x18000ccd5  cmp     eax, 1
0x18000ccd8  jnz     short loc_18000CD0F
0x18000ccda  jmp     short loc_18000CCF8
0x18000ccdc  mov     rcx, gs:60h
0x18000cce5  lea     r8, [rax-110h]; P
0x18000ccec  xor     edx, edx; Flags
0x18000ccee  mov     rcx, [rcx+30h]; HeapHandle
0x18000ccf2  call    cs:__imp_RtlFreeHeap
0x18000ccf8  lea     rcx, [rbx+10h]; ListHead
0x18000ccfc  call    cs:__imp_InterlockedPopEntrySList
0x18000cd02  test    rax, rax
0x18000cd05  jnz     short loc_18000CCDC
0x18000cd07  mov     rcx, rbx; Block
0x18000cd0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd0f  test    esi, esi
0x18000cd11  jnz     short loc_18000CD4E
0x18000cd13  test    rdi, rdi
0x18000cd16  jz      short loc_18000CD66
0x18000cd18  lea     rax, ??_7?$CComObjectCached@VCSdController@@@ATL@@6BISdScheduledBackup@@@; const ATL::CComObjectCached<CSdController>::`vftable'{for `ISdScheduledBackup'}
0x18000cd1f  mov     dword ptr [rdi+18h], 0C0000001h
0x18000cd26  mov     [rdi], rax
0x18000cd29  mov     rcx, rdi; this
0x18000cd2c  lea     rax, ??_7?$CComObjectCached@VCSdController@@@ATL@@6BISdCallback2@@@; const ATL::CComObjectCached<CSdController>::`vftable'{for `ISdCallback2'}
0x18000cd33  mov     [rdi+8], rax
0x18000cd37  call    ?FinalRelease@CSdController@@AEAAXXZ; CSdController::FinalRelease(void)
0x18000cd3c  mov     rcx, rdi; this
0x18000cd3f  call    ??1CSdController@@AEAA@XZ; CSdController::~CSdController(void)
0x18000cd44  mov     rcx, rdi; Block
0x18000cd47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd4c  jmp     short loc_18000CD66
0x18000cd4e  cmp     esi, 1
0x18000cd51  jnz     short loc_18000CD66
0x18000cd53  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cd5a  mov     rdx, [rcx]
0x18000cd5d  mov     rax, [rdx+10h]
0x18000cd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd66  mov     eax, esi
0x18000cd68  add     rsp, 28h
0x18000cd6c  pop     rdi
0x18000cd6d  pop     rsi
0x18000cd6e  pop     rbp
0x18000cd6f  pop     rbx
0x18000cd70  retn
```
