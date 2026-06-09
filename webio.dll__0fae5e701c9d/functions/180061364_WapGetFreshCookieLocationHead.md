# WapGetFreshCookieLocationHead

- ea: `0x180061364`
- end: `0x180061493`
- name: `WapGetFreshCookieLocationHead`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180074064`

## callees

- `0x1800067d8`
- `0x180061364`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180061435`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006146e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180061435`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006146e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800613cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800613cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800613de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800613de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061426`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006145f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061426`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006145f`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800613aa`
- `ntdll!RtlCompareUnicodeStrings` at `0x180061409`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800613aa`
- `ntdll!RtlCompareUnicodeStrings` at `0x180061409`

## pseudocode

```c
__int64 __fastcall WapGetFreshCookieLocationHead(__int64 a1, RTL_SRWLOCK *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  RTL_SRWLOCK *i; // rbx
  RTL_SRWLOCK *v9; // rbx
  RTL_SRWLOCK *j; // rsi
  unsigned int v11; // edi
  int v13; // [rsp+20h] [rbp-48h]

  *a5 = 0;
  while ( 2 )
  {
    for ( i = (RTL_SRWLOCK *)a2->Ptr; ; i = (RTL_SRWLOCK *)i->Ptr )
    {
      if ( i == a2 )
        goto LABEL_7;
      LOBYTE(v13) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(i[2].Ptr, i[3].Ptr, a3, a4, v13) )
        break;
    }
    if ( i == (RTL_SRWLOCK *)8 )
    {
LABEL_7:
      v9 = a2 + 3;
      ReleaseSRWLockShared(a2 + 3);
      AcquireSRWLockExclusive(a2 + 3);
      for ( j = (RTL_SRWLOCK *)a2->Ptr; ; j = (RTL_SRWLOCK *)j->Ptr )
      {
        if ( j == a2 )
          goto LABEL_13;
        LOBYTE(v13) = 1;
        if ( !(unsigned int)RtlCompareUnicodeStrings(j[2].Ptr, j[3].Ptr, a3, a4, v13) )
          break;
      }
      if ( j != (RTL_SRWLOCK *)8 )
      {
LABEL_12:
        ReleaseSRWLockExclusive(a2 + 3);
        AcquireSRWLockShared(a2 + 3);
        continue;
      }
LABEL_13:
      if ( WapCreateCookieLocationHead(a2, a3, a4) )
        goto LABEL_12;
      v11 = 8;
      ReleaseSRWLockExclusive(v9);
      AcquireSRWLockShared(v9);
    }
    else
    {
      *a5 = i - 1;
      return 0;
    }
    return v11;
  }
}

```

## disassembly

```asm
0x180061364  push    rbx
0x180061366  push    rbp
0x180061367  push    rsi
0x180061368  push    rdi
0x180061369  push    r12
0x18006136b  push    r14
0x18006136d  push    r15
0x18006136f  sub     rsp, 30h
0x180061373  mov     r14, [rsp+68h+arg_20]
0x18006137b  mov     r15, r9
0x18006137e  mov     r12, r8
0x180061381  mov     rdi, rdx
0x180061384  mov     qword ptr [r14], 0
0x18006138b  mov     rbx, [rdi]
0x18006138e  cmp     rbx, rdi
0x180061391  jz      short loc_1800613C8
0x180061393  lea     rsi, [rbx-8]
0x180061397  mov     byte ptr [rsp+68h+var_48], 1
0x18006139c  mov     rdx, [rsi+20h]
0x1800613a0  mov     r9, r15
0x1800613a3  mov     rcx, [rsi+18h]
0x1800613a7  mov     r8, r12
0x1800613aa  call    cs:__imp_RtlCompareUnicodeStrings
0x1800613b1  nop     dword ptr [rax+rax+00h]
0x1800613b6  test    eax, eax
0x1800613b8  jz      short loc_1800613BF
0x1800613ba  mov     rbx, [rbx]
0x1800613bd  jmp     short loc_18006138E
0x1800613bf  test    rsi, rsi
0x1800613c2  jnz     loc_18006148C
0x1800613c8  lea     rbx, [rdi+18h]
0x1800613cc  mov     rcx, rbx; SRWLock
0x1800613cf  call    cs:__imp_ReleaseSRWLockShared
0x1800613d6  nop     dword ptr [rax+rax+00h]
0x1800613db  mov     rcx, rbx; SRWLock
0x1800613de  call    cs:__imp_AcquireSRWLockExclusive
0x1800613e5  nop     dword ptr [rax+rax+00h]
0x1800613ea  mov     rsi, [rdi]
0x1800613ed  cmp     rsi, rdi
0x1800613f0  jz      short loc_180061446
0x1800613f2  lea     rbp, [rsi-8]
0x1800613f6  mov     byte ptr [rsp+68h+var_48], 1
0x1800613fb  mov     rdx, [rbp+20h]
0x1800613ff  mov     r9, r15
0x180061402  mov     rcx, [rbp+18h]
0x180061406  mov     r8, r12
0x180061409  call    cs:__imp_RtlCompareUnicodeStrings
0x180061410  nop     dword ptr [rax+rax+00h]
0x180061415  test    eax, eax
0x180061417  jz      short loc_18006141E
0x180061419  mov     rsi, [rsi]
0x18006141c  jmp     short loc_1800613ED
0x18006141e  test    rbp, rbp
0x180061421  jz      short loc_180061446
0x180061423  mov     rcx, rbx; SRWLock
0x180061426  call    cs:__imp_ReleaseSRWLockExclusive
0x18006142d  nop     dword ptr [rax+rax+00h]
0x180061432  mov     rcx, rbx; SRWLock
0x180061435  call    cs:__imp_AcquireSRWLockShared
0x18006143c  nop     dword ptr [rax+rax+00h]
0x180061441  jmp     loc_18006138B
0x180061446  mov     r8, r15
0x180061449  mov     rdx, r12
0x18006144c  mov     rcx, rdi
0x18006144f  call    WapCreateCookieLocationHead
0x180061454  test    rax, rax
0x180061457  jnz     short loc_180061423
0x180061459  lea     edi, [rax+8]
0x18006145c  mov     rcx, rbx; SRWLock
0x18006145f  call    cs:__imp_ReleaseSRWLockExclusive
0x180061466  nop     dword ptr [rax+rax+00h]
0x18006146b  mov     rcx, rbx; SRWLock
0x18006146e  call    cs:__imp_AcquireSRWLockShared
0x180061475  nop     dword ptr [rax+rax+00h]
0x18006147a  mov     eax, edi
0x18006147c  add     rsp, 30h
0x180061480  pop     r15
0x180061482  pop     r14
0x180061484  pop     r12
0x180061486  pop     rdi
0x180061487  pop     rsi
0x180061488  pop     rbp
0x180061489  pop     rbx
0x18006148a  retn
0x18006148c  mov     [r14], rsi
0x18006148f  xor     edi, edi
0x180061491  jmp     short loc_18006147A
```
