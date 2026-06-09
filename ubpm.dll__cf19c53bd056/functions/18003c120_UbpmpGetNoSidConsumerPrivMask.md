# UbpmpGetNoSidConsumerPrivMask

- ea: `0x18003c120`
- end: `0x18003c1da`
- name: `UbpmpGetNoSidConsumerPrivMask`
- size: `186`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019480`

## callees

- `0x18000a6e0`
- `0x18003c120`
- `0x18003c650`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003c15a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003c15a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003c1d3`

## pseudocode

```c
__int64 __fastcall UbpmpGetNoSidConsumerPrivMask(PSID pSid1, _QWORD *a2)
{
  struct _LIST_ENTRY *i; // rbx
  int v5; // r8d

  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_TaskHostContextListLock);
  for ( i = g_leTaskHostHardeningListHead.Flink; i != &g_leTaskHostHardeningListHead; i = i->Flink )
  {
    if ( !i[3].Flink )
    {
      if ( EqualSid(pSid1, i[1].Blink) )
      {
        if ( ((LODWORD(i[3].Blink) + 1) & 0xFFFFFFFE) == 0 )
        {
          *a2 |= (unsigned __int64)i[2].Flink;
          LODWORD(i[3].Blink) = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Si(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, v5, i[1].Flink, *a2);
        }
      }
    }
  }
  dword_18004CF18 = 0;
  return RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
}

```

## disassembly

```asm
0x18003c120  push    rbx
0x18003c122  push    rsi
0x18003c123  push    rdi
0x18003c124  push    r14
0x18003c126  sub     rsp, 38h
0x18003c12a  mov     rsi, rcx
0x18003c12d  mov     rdi, rdx
0x18003c130  lea     rcx, g_TaskHostContextListLock; struct _UBPM_SRWLOCK *
0x18003c137  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003c13c  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18003c143  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18003c14a  jmp     short loc_18003C1B4
0x18003c14c  cmp     qword ptr [rbx+30h], 0
0x18003c151  jnz     short loc_18003C1B1
0x18003c153  mov     rdx, [rbx+18h]; pSid2
0x18003c157  mov     rcx, rsi; pSid1
0x18003c15a  call    cs:__imp_EqualSid
0x18003c160  test    eax, eax
0x18003c162  jz      short loc_18003C1B1
0x18003c164  mov     eax, [rbx+38h]
0x18003c167  inc     eax
0x18003c169  test    eax, 0FFFFFFFEh
0x18003c16e  jnz     short loc_18003C1B1
0x18003c170  mov     rax, [rbx+20h]
0x18003c174  or      [rdi], rax
0x18003c177  mov     dword ptr [rbx+38h], 0
0x18003c17e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c185  lea     rax, WPP_GLOBAL_Control
0x18003c18c  cmp     rcx, rax
0x18003c18f  jz      short loc_18003C1B1
0x18003c191  test    byte ptr [rcx+1Ch], 80h
0x18003c195  jz      short loc_18003C1B1
0x18003c197  mov     rax, [rdi]
0x18003c19a  mov     edx, 0E2h
0x18003c19f  mov     r9, [rbx+10h]
0x18003c1a3  mov     rcx, [rcx+10h]
0x18003c1a7  mov     [rsp+58h+var_38], rax
0x18003c1ac  call    WPP_SF_Si
0x18003c1b1  mov     rbx, [rbx]
0x18003c1b4  cmp     rbx, r14
0x18003c1b7  jnz     short loc_18003C14C
0x18003c1b9  lea     rcx, g_TaskHostContextListLock
0x18003c1c0  mov     cs:dword_18004CF18, 0
0x18003c1ca  add     rsp, 38h
0x18003c1ce  pop     r14
0x18003c1d0  pop     rdi
0x18003c1d1  pop     rsi
0x18003c1d2  pop     rbx
0x18003c1d3  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
