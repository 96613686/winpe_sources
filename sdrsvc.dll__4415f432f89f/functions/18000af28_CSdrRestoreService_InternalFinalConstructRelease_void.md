# CSdrRestoreService::InternalFinalConstructRelease(void)

- ea: `0x18000af28`
- end: `0x18000afc2`
- name: `?InternalFinalConstructRelease@CSdrRestoreService@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(CSdrRestoreService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a460`
- `0x18000a8fc`

## callees

- `0x180001554`
- `0x180009cd0`
- `0x18000af28`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000afa4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000afa4`
- `ntdll!RtlFreeHeap` at `0x18000af9a`
- `ntdll!RtlFreeHeap` at `0x18000af9a`

## pseudocode

```c
void __fastcall CSdrRestoreService::InternalFinalConstructRelease(CSdrRestoreService *this)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  signed __int32 i; // edx
  PSLIST_ENTRY v4; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  for ( i = *((_DWORD *)this + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 4, i - 1, i);
        i = *((_DWORD *)this + 4) )
  {
    ;
  }
  if ( v2 )
  {
    CSxRefTraceList::CaptureStackTrace(v2, i - 1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    {
      while ( 1 )
      {
        v4 = InterlockedPopEntrySList(v2 + 1);
        if ( !v4 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v4[-17]);
      }
      operator delete(v2);
    }
  }
}

```

## disassembly

```asm
0x18000af28  mov     [rsp+arg_8], rbx
0x18000af2d  push    rdi
0x18000af2e  sub     rsp, 20h
0x18000af32  mov     rax, [rcx+20h]
0x18000af36  xor     ebx, ebx
0x18000af38  mov     r8, rcx
0x18000af3b  test    rax, rax
0x18000af3e  jz      short loc_18000AF46
0x18000af40  lock inc dword ptr [rax]
0x18000af43  mov     rbx, rax
0x18000af46  mov     edx, [rcx+10h]
0x18000af49  mov     r9d, 7FFFFFFFh
0x18000af4f  jmp     short loc_18000AF62
0x18000af51  lea     ecx, [rdx-1]
0x18000af54  mov     eax, edx
0x18000af56  lock cmpxchg [r8+10h], ecx
0x18000af5c  jz      short loc_18000AF67
0x18000af5e  mov     edx, [r8+10h]
0x18000af62  cmp     edx, r9d
0x18000af65  jnz     short loc_18000AF51
0x18000af67  test    rbx, rbx
0x18000af6a  jz      short loc_18000AFB7
0x18000af6c  dec     edx; unsigned int
0x18000af6e  mov     rcx, rbx; this
0x18000af71  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000af76  or      eax, 0FFFFFFFFh
0x18000af79  lock xadd [rbx], eax
0x18000af7d  cmp     eax, 1
0x18000af80  jnz     short loc_18000AFB7
0x18000af82  jmp     short loc_18000AFA0
0x18000af84  mov     rcx, gs:60h
0x18000af8d  lea     r8, [rax-110h]; P
0x18000af94  xor     edx, edx; Flags
0x18000af96  mov     rcx, [rcx+30h]; HeapHandle
0x18000af9a  call    cs:__imp_RtlFreeHeap
0x18000afa0  lea     rcx, [rbx+10h]; ListHead
0x18000afa4  call    cs:__imp_InterlockedPopEntrySList
0x18000afaa  test    rax, rax
0x18000afad  jnz     short loc_18000AF84
0x18000afaf  mov     rcx, rbx; Block
0x18000afb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000afb7  mov     rbx, [rsp+28h+arg_8]
0x18000afbc  add     rsp, 20h
0x18000afc0  pop     rdi
0x18000afc1  retn
```
