# CSdController::InternalFinalConstructRelease(void)

- ea: `0x18000ae88`
- end: `0x18000af22`
- name: `?InternalFinalConstructRelease@CSdController@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(CSdController *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a308`
- `0x18000a7a8`

## callees

- `0x180001554`
- `0x180009cd0`
- `0x18000ae88`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000af04`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000af04`
- `ntdll!RtlFreeHeap` at `0x18000aefa`
- `ntdll!RtlFreeHeap` at `0x18000aefa`

## pseudocode

```c
void __fastcall CSdController::InternalFinalConstructRelease(CSdController *this)
{
  volatile signed __int32 *v1; // rax
  union _SLIST_HEADER *v2; // rbx
  signed __int32 i; // edx
  PSLIST_ENTRY v4; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  v2 = 0;
  if ( v1 )
  {
    _InterlockedIncrement(v1);
    v2 = (union _SLIST_HEADER *)v1;
  }
  for ( i = *((_DWORD *)this + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 6, i - 1, i);
        i = *((_DWORD *)this + 6) )
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
0x18000ae88  mov     [rsp+arg_8], rbx
0x18000ae8d  push    rdi
0x18000ae8e  sub     rsp, 20h
0x18000ae92  mov     rax, [rcx+28h]
0x18000ae96  xor     ebx, ebx
0x18000ae98  mov     r8, rcx
0x18000ae9b  test    rax, rax
0x18000ae9e  jz      short loc_18000AEA6
0x18000aea0  lock inc dword ptr [rax]
0x18000aea3  mov     rbx, rax
0x18000aea6  mov     edx, [rcx+18h]
0x18000aea9  mov     r9d, 7FFFFFFFh
0x18000aeaf  jmp     short loc_18000AEC2
0x18000aeb1  lea     ecx, [rdx-1]
0x18000aeb4  mov     eax, edx
0x18000aeb6  lock cmpxchg [r8+18h], ecx
0x18000aebc  jz      short loc_18000AEC7
0x18000aebe  mov     edx, [r8+18h]
0x18000aec2  cmp     edx, r9d
0x18000aec5  jnz     short loc_18000AEB1
0x18000aec7  test    rbx, rbx
0x18000aeca  jz      short loc_18000AF17
0x18000aecc  dec     edx; unsigned int
0x18000aece  mov     rcx, rbx; this
0x18000aed1  call    ?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z; CSxRefTraceList::CaptureStackTrace(ulong)
0x18000aed6  or      eax, 0FFFFFFFFh
0x18000aed9  lock xadd [rbx], eax
0x18000aedd  cmp     eax, 1
0x18000aee0  jnz     short loc_18000AF17
0x18000aee2  jmp     short loc_18000AF00
0x18000aee4  mov     rcx, gs:60h
0x18000aeed  lea     r8, [rax-110h]; P
0x18000aef4  xor     edx, edx; Flags
0x18000aef6  mov     rcx, [rcx+30h]; HeapHandle
0x18000aefa  call    cs:__imp_RtlFreeHeap
0x18000af00  lea     rcx, [rbx+10h]; ListHead
0x18000af04  call    cs:__imp_InterlockedPopEntrySList
0x18000af0a  test    rax, rax
0x18000af0d  jnz     short loc_18000AEE4
0x18000af0f  mov     rcx, rbx; Block
0x18000af12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000af17  mov     rbx, [rsp+28h+arg_8]
0x18000af1c  add     rsp, 20h
0x18000af20  pop     rdi
0x18000af21  retn
```
