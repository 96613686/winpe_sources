# UbpmpFindHost

- ea: `0x18001d230`
- end: `0x18001d618`
- name: `UbpmpFindHost`
- size: `1000`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid1, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001da20`

## callees

- `0x1800166b0`
- `0x18001cee4`
- `0x18001d1d8`
- `0x18001d230`
- `0x18002cae0`
- `0x1800351ec`
- `0x18003ec6c`
- `0x18003f36c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d352`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d352`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d3b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d54d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d3b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d54d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001d39a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001d39a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d292`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d292`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d450`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d29e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d29e`

## pseudocode

```c
__int64 __fastcall UbpmpFindHost(
        wchar_t *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        PSID pSid1,
        char *a6,
        _DWORD *a7)
{
  _QWORD *v7; // r15
  bool v8; // zf
  _DWORD *v9; // r12
  unsigned int IsCriticalAction; // ebp
  char *i; // rbx
  char v14; // cl
  char *v15; // rdi
  __int64 v16; // rcx
  void *v17; // rdx
  PSID v18; // rcx
  __int64 v19; // rdx
  PSID v20; // rcx
  char *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // ebx
  char *j; // rcx
  volatile signed __int64 *v26; // rdx
  char v27; // al
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rcx
  char v35; // al

  v7 = a6;
  v8 = *(_DWORD *)a2 == 2;
  v9 = a7;
  a6 = 0;
  *v7 = 0;
  IsCriticalAction = 0;
  *v9 = 0;
  if ( v8 )
    IsCriticalAction = UbpmpIsCriticalAction(*(UUID **)(a2 + 8));
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)&g_MachineState, 0, 0) )
  {
    for ( i = (char *)g_leTaskHostContextListHead; ; i = *(char **)i )
    {
      if ( i == (char *)&g_leTaskHostContextListHead )
      {
        for ( j = (char *)g_leTaskHostContextListHead; j != (char *)&g_leTaskHostContextListHead; j = *(char **)j )
        {
          v26 = (volatile signed __int64 *)(j - 8);
          v27 = j[96] & 0x30;
          a6 = j - 8;
          if ( v27 == 48 )
          {
            _InterlockedIncrement64(v26 + 12);
            *v7 = v26;
            v24 = 0;
            *v9 = 1;
            goto LABEL_33;
          }
        }
        v24 = UbpmpCreatePartiallyInitializedTaskHostContextBlock(IsCriticalAction, &a6);
        if ( v24 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v32 = 178;
            v33 = a3;
            goto LABEL_50;
          }
        }
        else
        {
          v29 = off_18004F130;
          if ( *off_18004F130 != (_UNKNOWN *)&g_leTaskHostContextListHead )
            __fastfail(3u);
          v24 = 1168;
          v30 = a6 + 8;
          *v7 = a6;
          *v30 = &g_leTaskHostContextListHead;
          v30[1] = v29;
          *v29 = v30;
          off_18004F130 = (_UNKNOWN **)v30;
        }
        goto LABEL_33;
      }
      v14 = i[96];
      v15 = i - 8;
      a6 = i - 8;
      if ( (v14 & 0x10) != 0
        && (unsigned __int8)v15[432] == IsCriticalAction
        && a3 == *((_DWORD *)v15 + 48)
        && (v14 & 0x64) == 0 )
      {
        v16 = *(_QWORD *)(a2 + 32);
        if ( v16 )
        {
          v17 = (void *)*((_QWORD *)v15 + 23);
          if ( !v17 || *((_DWORD *)v15 + 66) != *(_DWORD *)(v16 + 36) || *((_DWORD *)v15 + 67) != *(_DWORD *)(v16 + 32) )
            continue;
          v18 = pSid1 ? pSid1 : *(PSID *)(*(_QWORD *)(v16 + 8) + 8LL);
          if ( !EqualSid(v18, v17) )
            continue;
          v19 = *((_QWORD *)v15 + 48);
          if ( v19 )
          {
            if ( (v19 & *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL)) != *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL) )
              continue;
          }
          if ( pSid1 )
            v20 = pSid1;
          else
            v20 = *(PSID *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 8LL) + 8LL);
          if ( UbpmUtilsSidSupportsHardening(v20) )
          {
            v34 = *(_QWORD *)(a2 + 32);
            v35 = *(_BYTE *)(v34 + 49);
            if ( v35 )
            {
              if ( v35 != 1
                || !*((_DWORD *)v15 + 98)
                || !(unsigned __int8)UbpmpIsConsumerSidPresent(*(wchar_t **)(v34 + 64)) )
              {
                continue;
              }
            }
            else if ( *((_DWORD *)v15 + 98) )
            {
              continue;
            }
          }
        }
        else if ( *((_QWORD *)v15 + 23) )
        {
          continue;
        }
        RtlAcquireSRWLockShared(v15 + 64);
        v21 = v15 + 64;
        if ( v15[104] >= 0 )
        {
          RtlReleaseSRWLockShared(v21);
          _InterlockedIncrement64((volatile signed __int64 *)v15 + 12);
          *v7 = v15;
          v24 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, *((unsigned int *)v15 + 8), a3, v15);
          if ( *((_QWORD *)v15 + 48) && !*((_DWORD *)v15 + 98) )
            UbpmpUpdateHardeningListNoSidConsumer(a1);
          goto LABEL_33;
        }
        RtlReleaseSRWLockShared(v21);
      }
    }
  }
  v24 = 1115;
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v32 = 176;
    v33 = 1115;
LABEL_50:
    WPP_SF_d(v31[2], v32, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v33);
  }
LABEL_33:
  dword_180050018 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  return v24;
}

```

## disassembly

```asm
0x18001d230  mov     [rsp+arg_18], r9b
0x18001d235  mov     [rsp+String1], rcx
0x18001d23a  push    rbx
0x18001d23b  push    rbp
0x18001d23c  push    rsi
0x18001d23d  push    r12
0x18001d23f  push    r13
0x18001d241  push    r14
0x18001d243  push    r15
0x18001d245  sub     rsp, 30h
0x18001d249  mov     r15, [rsp+68h+arg_28]
0x18001d251  xor     ebx, ebx
0x18001d253  cmp     dword ptr [rdx], 2
0x18001d256  movzx   esi, r9b
0x18001d25a  mov     r12, [rsp+68h+arg_30]
0x18001d262  mov     r13d, r8d
0x18001d265  mov     r14, rdx
0x18001d268  mov     [rsp+68h+arg_28], rbx
0x18001d270  mov     [r15], rbx
0x18001d273  mov     ebp, ebx
0x18001d275  mov     [r12], ebx
0x18001d279  jnz     short loc_18001D286
0x18001d27b  mov     rcx, [rdx+8]; Uuid2
0x18001d27f  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x18001d284  mov     ebp, eax
0x18001d286  lea     rcx, g_TaskHostContextListLock
0x18001d28d  mov     [rsp+68h+arg_8], rdi
0x18001d292  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001d299  nop     dword ptr [rax+rax+00h]
0x18001d29e  call    cs:__imp_GetCurrentThreadId
0x18001d2a5  nop     dword ptr [rax+rax+00h]
0x18001d2aa  mov     cs:dword_180050018, eax
0x18001d2b0  mov     ecx, ebx
0x18001d2b2  xor     eax, eax
0x18001d2b4  lock cmpxchg cs:?g_MachineState@@3U_UBPM_MACHINE_STATE@@A, ecx; _UBPM_MACHINE_STATE g_MachineState
0x18001d2bc  jnz     loc_18001D4C9
0x18001d2c2  mov     rbx, cs:g_leTaskHostContextListHead
0x18001d2c9  lea     rdi, g_leTaskHostContextListHead
0x18001d2d0  cmp     rbx, rdi
0x18001d2d3  jz      loc_18001D409
0x18001d2d9  movzx   ecx, byte ptr [rbx+60h]
0x18001d2dd  lea     rdi, [rbx-8]
0x18001d2e1  mov     [rsp+68h+arg_28], rdi
0x18001d2e9  test    cl, 10h
0x18001d2ec  jnz     short loc_18001D2F3
0x18001d2ee  mov     rbx, [rbx]
0x18001d2f1  jmp     short loc_18001D2C9
0x18001d2f3  movzx   eax, byte ptr [rdi+1B0h]
0x18001d2fa  cmp     eax, ebp
0x18001d2fc  jnz     short loc_18001D2EE
0x18001d2fe  cmp     r13d, [rdi+0C0h]
0x18001d305  jnz     short loc_18001D2EE
0x18001d307  test    cl, 64h
0x18001d30a  jnz     short loc_18001D2EE
0x18001d30c  mov     rcx, [r14+20h]
0x18001d310  test    rcx, rcx
0x18001d313  jz      loc_18001D4F1
0x18001d319  mov     rdx, [rdi+0B8h]; pSid2
0x18001d320  test    rdx, rdx
0x18001d323  jz      short loc_18001D2EE
0x18001d325  mov     eax, [rcx+24h]
0x18001d328  cmp     [rdi+108h], eax
0x18001d32e  jnz     short loc_18001D2EE
0x18001d330  mov     eax, [rcx+20h]
0x18001d333  cmp     [rdi+10Ch], eax
0x18001d339  jnz     short loc_18001D2EE
0x18001d33b  cmp     [rsp+68h+pSid1], 0
0x18001d344  jz      loc_18001D540
0x18001d34a  mov     rcx, [rsp+68h+pSid1]; pSid1
0x18001d352  call    cs:__imp_EqualSid
0x18001d359  nop     dword ptr [rax+rax+00h]
0x18001d35e  test    eax, eax
0x18001d360  jz      short loc_18001D2EE
0x18001d362  mov     rdx, [rdi+180h]
0x18001d369  test    rdx, rdx
0x18001d36c  jnz     loc_18001D50C
0x18001d372  cmp     [rsp+68h+pSid1], 0
0x18001d37b  jz      loc_18001D52F
0x18001d381  mov     rcx, [rsp+68h+pSid1]; pSid1
0x18001d389  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x18001d38e  test    al, al
0x18001d390  jnz     loc_18001D583
0x18001d396  lea     rcx, [rdi+40h]
0x18001d39a  call    cs:__imp_RtlAcquireSRWLockShared
0x18001d3a1  nop     dword ptr [rax+rax+00h]
0x18001d3a6  cmp     byte ptr [rdi+68h], 0
0x18001d3aa  lea     rcx, [rdi+40h]
0x18001d3ae  jl      loc_18001D54D
0x18001d3b4  call    cs:__imp_RtlReleaseSRWLockShared
0x18001d3bb  nop     dword ptr [rax+rax+00h]
0x18001d3c0  lock inc qword ptr [rdi+60h]
0x18001d3c5  xor     esi, esi
0x18001d3c7  mov     [r15], rdi
0x18001d3ca  mov     ebx, esi
0x18001d3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d3  lea     rax, WPP_GLOBAL_Control
0x18001d3da  cmp     rcx, rax
0x18001d3dd  jz      short loc_18001D3E9
0x18001d3df  test    byte ptr [rcx+1Ch], 80h
0x18001d3e3  jnz     loc_18001D5D6
0x18001d3e9  cmp     [rdi+180h], rbx
0x18001d3f0  jz      short loc_18001D443
0x18001d3f2  cmp     [rdi+188h], ebx
0x18001d3f8  jnz     short loc_18001D443
0x18001d3fa  mov     edx, [rdi+20h]
0x18001d3fd  mov     rcx, [rsp+68h+String1]; String1
0x18001d402  call    UbpmpUpdateHardeningListNoSidConsumer
0x18001d407  jmp     short loc_18001D443
0x18001d409  mov     rcx, cs:g_leTaskHostContextListHead
0x18001d410  cmp     rcx, rdi
0x18001d413  jz      short loc_18001D474
0x18001d415  movzx   eax, byte ptr [rcx+60h]
0x18001d419  lea     rdx, [rcx-8]
0x18001d41d  and     al, 30h
0x18001d41f  mov     [rsp+68h+arg_28], rdx
0x18001d427  cmp     al, 30h ; '0'
0x18001d429  jnz     loc_18001D504
0x18001d42f  lock inc qword ptr [rdx+60h]
0x18001d434  xor     esi, esi
0x18001d436  mov     [r15], rdx
0x18001d439  mov     ebx, esi
0x18001d43b  mov     dword ptr [r12], 1
0x18001d443  lea     rcx, g_TaskHostContextListLock
0x18001d44a  mov     cs:dword_180050018, esi
0x18001d450  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d457  nop     dword ptr [rax+rax+00h]
0x18001d45c  mov     rdi, [rsp+68h+arg_8]
0x18001d461  mov     eax, ebx
0x18001d463  add     rsp, 30h
0x18001d467  pop     r15
0x18001d469  pop     r14
0x18001d46b  pop     r13
0x18001d46d  pop     r12
0x18001d46f  pop     rsi
0x18001d470  pop     rbp
0x18001d471  pop     rbx
0x18001d472  retn
0x18001d474  lea     rdx, [rsp+68h+arg_28]
0x18001d47c  mov     ecx, ebp
0x18001d47e  call    UbpmpCreatePartiallyInitializedTaskHostContextBlock
0x18001d483  mov     ebx, eax
0x18001d485  test    eax, eax
0x18001d487  jnz     loc_18001D5F2
0x18001d48d  mov     rcx, cs:off_18004F130
0x18001d494  cmp     [rcx], rdi
0x18001d497  jnz     loc_18001D528
0x18001d49d  mov     rdx, [rsp+68h+arg_28]
0x18001d4a5  mov     ebx, 490h
0x18001d4aa  lea     rax, [rdx+8]
0x18001d4ae  mov     [r15], rdx
0x18001d4b1  mov     [rax], rdi
0x18001d4b4  mov     [rax+8], rcx
0x18001d4b8  mov     [rcx], rax
0x18001d4bb  mov     cs:off_18004F130, rax
0x18001d4c2  xor     esi, esi
0x18001d4c4  jmp     loc_18001D443
0x18001d4c9  mov     ebx, 45Bh
0x18001d4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4d5  lea     rax, WPP_GLOBAL_Control
0x18001d4dc  cmp     rcx, rax
0x18001d4df  jz      short loc_18001D4C2
0x18001d4e1  test    byte ptr [rcx+1Ch], 80h
0x18001d4e5  jz      short loc_18001D4C2
0x18001d4e7  mov     edx, 0B0h
0x18001d4ec  mov     r9d, ebx
0x18001d4ef  jmp     short loc_18001D56E
0x18001d4f1  cmp     qword ptr [rdi+0B8h], 0
0x18001d4f9  jnz     loc_18001D2EE
0x18001d4ff  jmp     loc_18001D396
0x18001d504  mov     rcx, [rcx]
0x18001d507  jmp     loc_18001D410
0x18001d50c  mov     rax, [r14+20h]
0x18001d510  mov     rcx, [rax+28h]
0x18001d514  mov     rax, rcx
0x18001d517  and     rax, rdx
0x18001d51a  cmp     rax, rcx
0x18001d51d  jnz     loc_18001D2EE
0x18001d523  jmp     loc_18001D372
0x18001d528  mov     ecx, 3
0x18001d52d  int     29h; Win8: RtlFailFast(ecx)
0x18001d52f  mov     rax, [r14+20h]
0x18001d533  mov     rcx, [rax+8]
0x18001d537  mov     rcx, [rcx+8]
0x18001d53b  jmp     loc_18001D389
0x18001d540  mov     rax, [rcx+8]
0x18001d544  mov     rcx, [rax+8]
0x18001d548  jmp     loc_18001D352
0x18001d54d  call    cs:__imp_RtlReleaseSRWLockShared
0x18001d554  nop     dword ptr [rax+rax+00h]
0x18001d559  movzx   esi, [rsp+68h+arg_18]
0x18001d561  jmp     loc_18001D2EE
0x18001d566  mov     edx, 0B2h
0x18001d56b  mov     r9d, r13d
0x18001d56e  mov     rcx, [rcx+10h]
0x18001d572  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001d579  call    WPP_SF_d
0x18001d57e  jmp     loc_18001D4C2
0x18001d583  mov     rcx, [r14+20h]
0x18001d587  movzx   eax, byte ptr [rcx+31h]
0x18001d58b  test    al, al
0x18001d58d  jnz     short loc_18001D5A1
0x18001d58f  cmp     dword ptr [rdi+188h], 0
0x18001d596  jz      loc_18001D396
0x18001d59c  jmp     loc_18001D2EE
0x18001d5a1  cmp     al, 1
0x18001d5a3  jnz     loc_18001D2EE
0x18001d5a9  cmp     dword ptr [rdi+188h], 0
0x18001d5b0  jbe     loc_18001D2EE
0x18001d5b6  mov     edx, [rcx+48h]
0x18001d5b9  movzx   r9d, sil
0x18001d5bd  mov     rcx, [rcx+40h]; String2
0x18001d5c1  mov     r8, rdi
0x18001d5c4  call    UbpmpIsConsumerSidPresent
0x18001d5c9  test    al, al
0x18001d5cb  jz      loc_18001D2EE
0x18001d5d1  jmp     loc_18001D396
0x18001d5d6  mov     r9d, [rdi+20h]
0x18001d5da  mov     rcx, [rcx+10h]
0x18001d5de  mov     [rsp+68h+var_40], rdi
0x18001d5e3  mov     [rsp+68h+var_48], r13d
0x18001d5e8  call    WPP_SF_ddq
0x18001d5ed  jmp     loc_18001D3E9
0x18001d5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5f9  lea     rax, WPP_GLOBAL_Control
0x18001d600  cmp     rcx, rax
0x18001d603  jz      loc_18001D4C2
0x18001d609  test    byte ptr [rcx+1Ch], 1
0x18001d60d  jz      loc_18001D4C2
0x18001d613  jmp     loc_18001D566
```
