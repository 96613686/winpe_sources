# ATL::CComObject<CSdController>::Release(void)

- ea: `0x18000ca90`
- end: `0x18000cb6b`
- name: `?Release@?$CComObject@VCSdController@@@ATL@@UEAAKXZ`
- size: `219`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000cb80`

## callees

- `0x180001554`
- `0x180009cd0`
- `0x18000ca90`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000cb0c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000cb0c`
- `ntdll!RtlFreeHeap` at `0x18000cb02`
- `ntdll!RtlFreeHeap` at `0x18000cb02`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSdController>::Release(__int64 a1)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // esi
  PSLIST_ENTRY v7; // rax

  v1 = *(volatile signed __int32 **)(a1 + 40);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  v4 = *(unsigned int *)(a1 + 24);
  v5 = 0x7FFFFFFF;
  while ( (_DWORD)v4 != 0x7FFFFFFF
       && (_DWORD)v4 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), v4 - 1, v4) )
    v4 = *(unsigned int *)(a1 + 24);
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
  if ( !v6 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, __int64, __int64))(*(_QWORD *)ATL::_pAtlModule + 8LL))(
      ATL::_pAtlModule,
      v4,
      v5);
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 120LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v6;
}

```

## disassembly

```asm
0x18000ca90  push    rbx
0x18000ca92  push    rbp
0x18000ca93  push    rsi
0x18000ca94  push    rdi
0x18000ca95  sub     rsp, 28h
0x18000ca99  mov     rax, [rcx+28h]
0x18000ca9d  xor     ebx, ebx
0x18000ca9f  mov     rdi, rcx
0x18000caa2  test    rax, rax
0x18000caa5  jz      short loc_18000CAAD
0x18000caa7  lock inc dword ptr [rax]
0x18000caaa  mov     rbx, rax
0x18000caad  mov     edx, [rcx+18h]
0x18000cab0  mov     r8d, 7FFFFFFFh
0x18000cab6  jmp     short loc_18000CAC7
0x18000cab8  lea     ecx, [rdx-1]
0x18000cabb  mov     eax, edx
0x18000cabd  lock cmpxchg [rdi+18h], ecx
0x18000cac2  jz      short loc_18000CACC
0x18000cac4  mov     edx, [rdi+18h]
0x18000cac7  cmp     edx, r8d
0x18000caca  jnz     short loc_18000CAB8
0x18000cacc  lea     esi, [rdx-1]
0x18000cacf  test    rbx, rbx
0x18000cad2  jz      short loc_18000CB1F
0x18000cad4  mov     edx, esi; unsigned int
0x18000cad6  mov     rcx, rbx; this
0x18000cad9  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000cade  or      eax, 0FFFFFFFFh
0x18000cae1  lock xadd [rbx], eax
0x18000cae5  cmp     eax, 1
0x18000cae8  jnz     short loc_18000CB1F
0x18000caea  jmp     short loc_18000CB08
0x18000caec  mov     rcx, gs:60h
0x18000caf5  lea     r8, [rax-110h]; P
0x18000cafc  xor     edx, edx; Flags
0x18000cafe  mov     rcx, [rcx+30h]; HeapHandle
0x18000cb02  call    cs:__imp_RtlFreeHeap
0x18000cb08  lea     rcx, [rbx+10h]; ListHead
0x18000cb0c  call    cs:__imp_InterlockedPopEntrySList
0x18000cb12  test    rax, rax
0x18000cb15  jnz     short loc_18000CAEC
0x18000cb17  mov     rcx, rbx; Block
0x18000cb1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb1f  test    esi, esi
0x18000cb21  jnz     short loc_18000CB60
0x18000cb23  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cb2a  mov     rax, [rcx]
0x18000cb2d  mov     rax, [rax+8]
0x18000cb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb36  test    rdi, rdi
0x18000cb39  jz      short loc_18000CB4D
0x18000cb3b  mov     rax, [rdi]
0x18000cb3e  lea     edx, [rsi+1]
0x18000cb41  mov     rcx, rdi
0x18000cb44  mov     rax, [rax+78h]
0x18000cb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cb54  mov     rdx, [rcx]
0x18000cb57  mov     rax, [rdx+10h]
0x18000cb5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb60  mov     eax, esi
0x18000cb62  add     rsp, 28h
0x18000cb66  pop     rdi
0x18000cb67  pop     rsi
0x18000cb68  pop     rbp
0x18000cb69  pop     rbx
0x18000cb6a  retn
```
