# ATL::CComObjectCached<CSdrRestoreService>::Release(void)

- ea: `0x18000cd90`
- end: `0x18000ce6e`
- name: `?Release@?$CComObjectCached@VCSdrRestoreService@@@ATL@@UEAAKXZ`
- size: `222`
- prototype: `__int64 __fastcall(CSdrRestoreService *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001554`
- `0x180008b74`
- `0x180009cd0`
- `0x18000cd90`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000ce0c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000ce0c`
- `ntdll!RtlFreeHeap` at `0x18000ce02`
- `ntdll!RtlFreeHeap` at `0x18000ce02`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CSdrRestoreService>::Release(CSdrRestoreService *this)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  signed __int32 v4; // edx
  __int64 v5; // r8
  unsigned int v6; // esi
  PSLIST_ENTRY v7; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  v4 = *((_DWORD *)this + 4);
  v5 = 0x7FFFFFFF;
  while ( v4 != 0x7FFFFFFF && v4 != _InterlockedCompareExchange((volatile signed __int32 *)this + 4, v4 - 1, v4) )
    v4 = *((_DWORD *)this + 4);
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
    *((_DWORD *)this + 4) = -1073741823;
    *(_QWORD *)this = &ATL::CComObjectCached<CSdrRestoreService>::`vftable';
    CSdrRestoreService::~CSdrRestoreService(this);
    operator delete(this);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cd90  push    rbx
0x18000cd92  push    rbp
0x18000cd93  push    rsi
0x18000cd94  push    rdi
0x18000cd95  sub     rsp, 28h
0x18000cd99  mov     rax, [rcx+20h]
0x18000cd9d  xor     ebx, ebx
0x18000cd9f  mov     rdi, rcx
0x18000cda2  test    rax, rax
0x18000cda5  jz      short loc_18000CDAD
0x18000cda7  lock inc dword ptr [rax]
0x18000cdaa  mov     rbx, rax
0x18000cdad  mov     edx, [rcx+10h]
0x18000cdb0  mov     r8d, 7FFFFFFFh
0x18000cdb6  jmp     short loc_18000CDC7
0x18000cdb8  lea     ecx, [rdx-1]
0x18000cdbb  mov     eax, edx
0x18000cdbd  lock cmpxchg [rdi+10h], ecx
0x18000cdc2  jz      short loc_18000CDCC
0x18000cdc4  mov     edx, [rdi+10h]
0x18000cdc7  cmp     edx, r8d
0x18000cdca  jnz     short loc_18000CDB8
0x18000cdcc  lea     esi, [rdx-1]
0x18000cdcf  test    rbx, rbx
0x18000cdd2  jz      short loc_18000CE1F
0x18000cdd4  mov     edx, esi; unsigned int
0x18000cdd6  mov     rcx, rbx; this
0x18000cdd9  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000cdde  or      eax, 0FFFFFFFFh
0x18000cde1  lock xadd [rbx], eax
0x18000cde5  cmp     eax, 1
0x18000cde8  jnz     short loc_18000CE1F
0x18000cdea  jmp     short loc_18000CE08
0x18000cdec  mov     rcx, gs:60h
0x18000cdf5  lea     r8, [rax-110h]; P
0x18000cdfc  xor     edx, edx; Flags
0x18000cdfe  mov     rcx, [rcx+30h]; HeapHandle
0x18000ce02  call    cs:__imp_RtlFreeHeap
0x18000ce08  lea     rcx, [rbx+10h]; ListHead
0x18000ce0c  call    cs:__imp_InterlockedPopEntrySList
0x18000ce12  test    rax, rax
0x18000ce15  jnz     short loc_18000CDEC
0x18000ce17  mov     rcx, rbx; Block
0x18000ce1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ce1f  test    esi, esi
0x18000ce21  jnz     short loc_18000CE4B
0x18000ce23  test    rdi, rdi
0x18000ce26  jz      short loc_18000CE63
0x18000ce28  lea     rax, ??_7?$CComObjectCached@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComObjectCached<CSdrRestoreService>::`vftable'
0x18000ce2f  mov     dword ptr [rdi+10h], 0C0000001h
0x18000ce36  mov     rcx, rdi; this
0x18000ce39  mov     [rdi], rax
0x18000ce3c  call    ??1CSdrRestoreService@@QEAA@XZ; CSdrRestoreService::~CSdrRestoreService(void)
0x18000ce41  mov     rcx, rdi; Block
0x18000ce44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ce49  jmp     short loc_18000CE63
0x18000ce4b  cmp     esi, 1
0x18000ce4e  jnz     short loc_18000CE63
0x18000ce50  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ce57  mov     rdx, [rcx]
0x18000ce5a  mov     rax, [rdx+10h]
0x18000ce5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce63  mov     eax, esi
0x18000ce65  add     rsp, 28h
0x18000ce69  pop     rdi
0x18000ce6a  pop     rsi
0x18000ce6b  pop     rbp
0x18000ce6c  pop     rbx
0x18000ce6d  retn
```
