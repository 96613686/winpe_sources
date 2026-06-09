# ATL::CComObject<CSdrRestoreService>::Release(void)

- ea: `0x18000cb90`
- end: `0x18000cc6b`
- name: `?Release@?$CComObject@VCSdrRestoreService@@@ATL@@UEAAKXZ`
- size: `219`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001554`
- `0x180009cd0`
- `0x18000cb90`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000cc0c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000cc0c`
- `ntdll!RtlFreeHeap` at `0x18000cc02`
- `ntdll!RtlFreeHeap` at `0x18000cc02`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSdrRestoreService>::Release(__int64 a1)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // esi
  PSLIST_ENTRY v7; // rax

  v1 = *(volatile signed __int32 **)(a1 + 32);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  v4 = *(unsigned int *)(a1 + 16);
  v5 = 0x7FFFFFFF;
  while ( (_DWORD)v4 != 0x7FFFFFFF
       && (_DWORD)v4 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v4 - 1, v4) )
    v4 = *(unsigned int *)(a1 + 16);
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
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cb90  push    rbx
0x18000cb92  push    rbp
0x18000cb93  push    rsi
0x18000cb94  push    rdi
0x18000cb95  sub     rsp, 28h
0x18000cb99  mov     rax, [rcx+20h]
0x18000cb9d  xor     ebx, ebx
0x18000cb9f  mov     rdi, rcx
0x18000cba2  test    rax, rax
0x18000cba5  jz      short loc_18000CBAD
0x18000cba7  lock inc dword ptr [rax]
0x18000cbaa  mov     rbx, rax
0x18000cbad  mov     edx, [rcx+10h]
0x18000cbb0  mov     r8d, 7FFFFFFFh
0x18000cbb6  jmp     short loc_18000CBC7
0x18000cbb8  lea     ecx, [rdx-1]
0x18000cbbb  mov     eax, edx
0x18000cbbd  lock cmpxchg [rdi+10h], ecx
0x18000cbc2  jz      short loc_18000CBCC
0x18000cbc4  mov     edx, [rdi+10h]
0x18000cbc7  cmp     edx, r8d
0x18000cbca  jnz     short loc_18000CBB8
0x18000cbcc  lea     esi, [rdx-1]
0x18000cbcf  test    rbx, rbx
0x18000cbd2  jz      short loc_18000CC1F
0x18000cbd4  mov     edx, esi; unsigned int
0x18000cbd6  mov     rcx, rbx; this
0x18000cbd9  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000cbde  or      eax, 0FFFFFFFFh
0x18000cbe1  lock xadd [rbx], eax
0x18000cbe5  cmp     eax, 1
0x18000cbe8  jnz     short loc_18000CC1F
0x18000cbea  jmp     short loc_18000CC08
0x18000cbec  mov     rcx, gs:60h
0x18000cbf5  lea     r8, [rax-110h]; P
0x18000cbfc  xor     edx, edx; Flags
0x18000cbfe  mov     rcx, [rcx+30h]; HeapHandle
0x18000cc02  call    cs:__imp_RtlFreeHeap
0x18000cc08  lea     rcx, [rbx+10h]; ListHead
0x18000cc0c  call    cs:__imp_InterlockedPopEntrySList
0x18000cc12  test    rax, rax
0x18000cc15  jnz     short loc_18000CBEC
0x18000cc17  mov     rcx, rbx; Block
0x18000cc1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc1f  test    esi, esi
0x18000cc21  jnz     short loc_18000CC60
0x18000cc23  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cc2a  mov     rax, [rcx]
0x18000cc2d  mov     rax, [rax+8]
0x18000cc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc36  test    rdi, rdi
0x18000cc39  jz      short loc_18000CC4D
0x18000cc3b  mov     rax, [rdi]
0x18000cc3e  lea     edx, [rsi+1]
0x18000cc41  mov     rcx, rdi
0x18000cc44  mov     rax, [rax+38h]
0x18000cc48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cc54  mov     rdx, [rcx]
0x18000cc57  mov     rax, [rdx+10h]
0x18000cc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc60  mov     eax, esi
0x18000cc62  add     rsp, 28h
0x18000cc66  pop     rdi
0x18000cc67  pop     rsi
0x18000cc68  pop     rbp
0x18000cc69  pop     rbx
0x18000cc6a  retn
```
