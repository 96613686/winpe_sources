# UbpmpCloseTriggerConsumer

- ea: `0x18000aba0`
- end: `0x18000ad34`
- name: `UbpmpCloseTriggerConsumer`
- size: `404`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a8b0`
- `0x18000aac0`
- `0x18000e090`
- `0x18002dcc0`
- `0x180035df0`
- `0x18003625c`

## callees

- `0x18000aba0`
- `0x18000ad3c`
- `0x18000ada4`
- `0x18000ae00`
- `0x18001e9f4`
- `0x1800354e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ac90`
- `ntdll!RtlFreeHeap` at `0x18000acae`
- `ntdll!RtlFreeHeap` at `0x18000ac90`
- `ntdll!RtlFreeHeap` at `0x18000acae`
- `ntdll!RtlFreeHeap` at `0x18000acce`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000abb0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000abb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ac22`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ac02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ac22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abb6`

## pseudocode

```c
BOOLEAN __fastcall UbpmpCloseTriggerConsumer(__int64 a1)
{
  signed __int64 v2; // rdi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  void *v7; // r8
  void *v8; // r8

  RtlAcquireSRWLockExclusive(a1 + 48);
  *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
  v2 = _InterlockedDecrement64((volatile signed __int64 *)(a1 + 64));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Siq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      v2,
      a1);
  if ( v2 || !(unsigned __int8)UbpmConsumerIsUnregistered(a1) )
  {
    *(_DWORD *)(a1 + 56) = 0;
    return RtlReleaseSRWLockExclusive(a1 + 48);
  }
  else
  {
    *(_BYTE *)(a1 + 104) = 1;
    *(_DWORD *)(a1 + 56) = 0;
    RtlReleaseSRWLockExclusive(a1 + 48);
    UbpmpAcquireListLockExclusive();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        g_cTotalConsumers);
    v4 = *(_QWORD *)(a1 + 8);
    v5 = (_QWORD *)(a1 + 8);
    if ( v4 != a1 + 8 )
    {
      if ( *(_QWORD **)(v4 + 8) != v5 || (v6 = *(_QWORD **)(a1 + 16), (_QWORD *)*v6 != v5) )
        __fastfail(3u);
      --g_cTotalConsumers;
      *v6 = v4;
      *(_QWORD *)(v4 + 8) = v6;
      *(_QWORD *)(a1 + 16) = a1 + 8;
      *v5 = v5;
    }
    UbpmpReleaseListLockExclusive();
    v7 = *(void **)(a1 + 32);
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v8 = *(void **)(a1 + 24);
    if ( v8 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
  }
}

```

## disassembly

```asm
0x18000aba0  push    rbx
0x18000aba2  push    rbp
0x18000aba3  push    rsi
0x18000aba4  push    rdi
0x18000aba5  sub     rsp, 38h
0x18000aba9  mov     rsi, rcx
0x18000abac  add     rcx, 30h ; '0'
0x18000abb0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000abb6  call    cs:__imp_GetCurrentThreadId
0x18000abbc  mov     [rsi+38h], eax
0x18000abbf  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000abc6  lock xadd [rsi+40h], rdi
0x18000abcc  dec     rdi
0x18000abcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd6  lea     rbp, WPP_GLOBAL_Control
0x18000abdd  cmp     rcx, rbp
0x18000abe0  jz      short loc_18000ABEC
0x18000abe2  test    byte ptr [rcx+1Ch], 8
0x18000abe6  jnz     loc_18000ACDC
0x18000abec  test    rdi, rdi
0x18000abef  jz      short loc_18000AC09
0x18000abf1  xor     eax, eax
0x18000abf3  lea     rcx, [rsi+30h]
0x18000abf7  mov     [rsi+38h], eax
0x18000abfa  add     rsp, 38h
0x18000abfe  pop     rdi
0x18000abff  pop     rsi
0x18000ac00  pop     rbp
0x18000ac01  pop     rbx
0x18000ac02  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x18000ac09  mov     rcx, rsi
0x18000ac0c  call    UbpmConsumerIsUnregistered
0x18000ac11  test    al, al
0x18000ac13  jz      short loc_18000ABF1
0x18000ac15  xor     eax, eax
0x18000ac17  mov     byte ptr [rsi+68h], 1
0x18000ac1b  lea     rcx, [rsi+30h]
0x18000ac1f  mov     [rsi+38h], eax
0x18000ac22  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ac28  call    UbpmpAcquireListLockExclusive
0x18000ac2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac34  cmp     rcx, rbp
0x18000ac37  jz      short loc_18000AC43
0x18000ac39  test    byte ptr [rcx+1Ch], 4
0x18000ac3d  jnz     loc_18000AD08
0x18000ac43  mov     rcx, [rsi+8]
0x18000ac47  lea     rax, [rsi+8]
0x18000ac4b  cmp     rcx, rax
0x18000ac4e  jz      short loc_18000AC73
0x18000ac50  cmp     [rcx+8], rax
0x18000ac54  jnz     short loc_18000ACD5
0x18000ac56  mov     rdx, [rax+8]
0x18000ac5a  cmp     [rdx], rax
0x18000ac5d  jnz     short loc_18000ACD5
0x18000ac5f  dec     cs:g_cTotalConsumers
0x18000ac65  mov     [rdx], rcx
0x18000ac68  mov     [rcx+8], rdx
0x18000ac6c  mov     [rax+8], rax
0x18000ac70  mov     [rax], rax
0x18000ac73  call    UbpmpReleaseListLockExclusive
0x18000ac78  mov     r8, [rsi+20h]; P
0x18000ac7c  test    r8, r8
0x18000ac7f  jz      short loc_18000AC96
0x18000ac81  mov     rcx, gs:60h
0x18000ac8a  xor     edx, edx; Flags
0x18000ac8c  mov     rcx, [rcx+30h]; HeapHandle
0x18000ac90  call    cs:__imp_RtlFreeHeap
0x18000ac96  mov     r8, [rsi+18h]; P
0x18000ac9a  test    r8, r8
0x18000ac9d  jz      short loc_18000ACB4
0x18000ac9f  mov     rcx, gs:60h
0x18000aca8  xor     edx, edx; Flags
0x18000acaa  mov     rcx, [rcx+30h]; HeapHandle
0x18000acae  call    cs:__imp_RtlFreeHeap
0x18000acb4  mov     rcx, gs:60h
0x18000acbd  mov     r8, rsi
0x18000acc0  xor     edx, edx
0x18000acc2  mov     rcx, [rcx+30h]
0x18000acc6  add     rsp, 38h
0x18000acca  pop     rdi
0x18000accb  pop     rsi
0x18000accc  pop     rbp
0x18000accd  pop     rbx
0x18000acce  jmp     cs:__imp_RtlFreeHeap
0x18000acd5  mov     ecx, 3
0x18000acda  int     29h; Win8: RtlFailFast(ecx)
0x18000acdc  mov     r9, [rsi+18h]
0x18000ace0  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000ace7  mov     rcx, [rcx+10h]
0x18000aceb  mov     edx, 7Ah ; 'z'
0x18000acf0  mov     [rsp+58h+var_30], rsi
0x18000acf5  mov     [rsp+58h+var_38], rdi
0x18000acfa  mov     r9, [r9+8]
0x18000acfe  call    WPP_SF_Siq
0x18000ad03  jmp     loc_18000ABEC
0x18000ad08  mov     r9, [rsi+18h]
0x18000ad0c  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000ad13  mov     eax, cs:g_cTotalConsumers
0x18000ad19  mov     edx, 7Bh ; '{'
0x18000ad1e  mov     rcx, [rcx+10h]
0x18000ad22  mov     dword ptr [rsp+58h+var_38], eax
0x18000ad26  mov     r9, [r9+8]
0x18000ad2a  call    WPP_SF_Sd
0x18000ad2f  jmp     loc_18000AC43
```
