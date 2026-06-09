# UbpmpFindHost

- ea: `0x180020900`
- end: `0x180020cba`
- name: `UbpmpFindHost`
- size: `954`
- prototype: `__int64 __fastcall(wchar_t *, __int64, unsigned int, __int64, PSID pSid1, char *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021060`

## callees

- `0x1800143b0`
- `0x180020604`
- `0x1800208bc`
- `0x180020900`
- `0x18002ae3c`
- `0x180032e38`
- `0x18003c300`
- `0x18003c99c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180020a16`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180020a16`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020a6c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020bf5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020a6c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020bf5`
- `ntdll!RtlAcquireSRWLockShared` at `0x180020a58`
- `ntdll!RtlAcquireSRWLockShared` at `0x180020a58`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020962`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020962`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020b02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020b02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020968`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020968`

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
  dword_18004CF18 = GetCurrentThreadId();
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
          v29 = off_18004C130;
          if ( *off_18004C130 != (_UNKNOWN *)&g_leTaskHostContextListHead )
            __fastfail(3u);
          v24 = 1168;
          v30 = a6 + 8;
          *v7 = a6;
          *v30 = &g_leTaskHostContextListHead;
          v30[1] = v29;
          *v29 = v30;
          off_18004C130 = (_UNKNOWN **)v30;
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
  dword_18004CF18 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  return v24;
}

```

## disassembly

```asm
0x180020900  mov     [rsp+arg_18], r9b
0x180020905  mov     [rsp+String1], rcx
0x18002090a  push    rbx
0x18002090b  push    rbp
0x18002090c  push    rsi
0x18002090d  push    r12
0x18002090f  push    r13
0x180020911  push    r14
0x180020913  push    r15
0x180020915  sub     rsp, 30h
0x180020919  mov     r15, [rsp+68h+arg_28]
0x180020921  xor     ebx, ebx
0x180020923  cmp     dword ptr [rdx], 2
0x180020926  movzx   esi, r9b
0x18002092a  mov     r12, [rsp+68h+arg_30]
0x180020932  mov     r13d, r8d
0x180020935  mov     r14, rdx
0x180020938  mov     [rsp+68h+arg_28], rbx
0x180020940  mov     [r15], rbx
0x180020943  mov     ebp, ebx
0x180020945  mov     [r12], ebx
0x180020949  jnz     short loc_180020956
0x18002094b  mov     rcx, [rdx+8]; Uuid2
0x18002094f  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x180020954  mov     ebp, eax
0x180020956  lea     rcx, g_TaskHostContextListLock
0x18002095d  mov     [rsp+68h+arg_8], rdi
0x180020962  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180020968  call    cs:__imp_GetCurrentThreadId
0x18002096e  mov     cs:dword_18004CF18, eax
0x180020974  mov     ecx, ebx
0x180020976  xor     eax, eax
0x180020978  lock cmpxchg cs:?g_MachineState@@3U_UBPM_MACHINE_STATE@@A, ecx; _UBPM_MACHINE_STATE g_MachineState
0x180020980  jnz     loc_180020B71
0x180020986  mov     rbx, cs:g_leTaskHostContextListHead
0x18002098d  lea     rdi, g_leTaskHostContextListHead
0x180020994  cmp     rbx, rdi
0x180020997  jz      loc_180020ABB
0x18002099d  movzx   ecx, byte ptr [rbx+60h]
0x1800209a1  lea     rdi, [rbx-8]
0x1800209a5  mov     [rsp+68h+arg_28], rdi
0x1800209ad  test    cl, 10h
0x1800209b0  jnz     short loc_1800209B7
0x1800209b2  mov     rbx, [rbx]
0x1800209b5  jmp     short loc_18002098D
0x1800209b7  movzx   eax, byte ptr [rdi+1B0h]
0x1800209be  cmp     eax, ebp
0x1800209c0  jnz     short loc_1800209B2
0x1800209c2  cmp     r13d, [rdi+0C0h]
0x1800209c9  jnz     short loc_1800209B2
0x1800209cb  test    cl, 64h
0x1800209ce  jnz     short loc_1800209B2
0x1800209d0  mov     rcx, [r14+20h]
0x1800209d4  test    rcx, rcx
0x1800209d7  jz      loc_180020B99
0x1800209dd  mov     rdx, [rdi+0B8h]; pSid2
0x1800209e4  test    rdx, rdx
0x1800209e7  jz      short loc_1800209B2
0x1800209e9  mov     eax, [rcx+24h]
0x1800209ec  cmp     [rdi+108h], eax
0x1800209f2  jnz     short loc_1800209B2
0x1800209f4  mov     eax, [rcx+20h]
0x1800209f7  cmp     [rdi+10Ch], eax
0x1800209fd  jnz     short loc_1800209B2
0x1800209ff  cmp     [rsp+68h+pSid1], 0
0x180020a08  jz      loc_180020BE8
0x180020a0e  mov     rcx, [rsp+68h+pSid1]; pSid1
0x180020a16  call    cs:__imp_EqualSid
0x180020a1c  test    eax, eax
0x180020a1e  jz      short loc_1800209B2
0x180020a20  mov     rdx, [rdi+180h]
0x180020a27  test    rdx, rdx
0x180020a2a  jnz     loc_180020BB4
0x180020a30  cmp     [rsp+68h+pSid1], 0
0x180020a39  jz      loc_180020BD7
0x180020a3f  mov     rcx, [rsp+68h+pSid1]; pSid1
0x180020a47  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x180020a4c  test    al, al
0x180020a4e  jnz     loc_180020C25
0x180020a54  lea     rcx, [rdi+40h]
0x180020a58  call    cs:__imp_RtlAcquireSRWLockShared
0x180020a5e  cmp     byte ptr [rdi+68h], 0
0x180020a62  lea     rcx, [rdi+40h]
0x180020a66  jl      loc_180020BF5
0x180020a6c  call    cs:__imp_RtlReleaseSRWLockShared
0x180020a72  lock inc qword ptr [rdi+60h]
0x180020a77  xor     esi, esi
0x180020a79  mov     [r15], rdi
0x180020a7c  mov     ebx, esi
0x180020a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a85  lea     rax, WPP_GLOBAL_Control
0x180020a8c  cmp     rcx, rax
0x180020a8f  jz      short loc_180020A9B
0x180020a91  test    byte ptr [rcx+1Ch], 80h
0x180020a95  jnz     loc_180020C78
0x180020a9b  cmp     [rdi+180h], rbx
0x180020aa2  jz      short loc_180020AF5
0x180020aa4  cmp     [rdi+188h], ebx
0x180020aaa  jnz     short loc_180020AF5
0x180020aac  mov     edx, [rdi+20h]
0x180020aaf  mov     rcx, [rsp+68h+String1]; String1
0x180020ab4  call    UbpmpUpdateHardeningListNoSidConsumer
0x180020ab9  jmp     short loc_180020AF5
0x180020abb  mov     rcx, cs:g_leTaskHostContextListHead
0x180020ac2  cmp     rcx, rdi
0x180020ac5  jz      short loc_180020B1F
0x180020ac7  movzx   eax, byte ptr [rcx+60h]
0x180020acb  lea     rdx, [rcx-8]
0x180020acf  and     al, 30h
0x180020ad1  mov     [rsp+68h+arg_28], rdx
0x180020ad9  cmp     al, 30h ; '0'
0x180020adb  jnz     loc_180020BAC
0x180020ae1  lock inc qword ptr [rdx+60h]
0x180020ae6  xor     esi, esi
0x180020ae8  mov     [r15], rdx
0x180020aeb  mov     ebx, esi
0x180020aed  mov     dword ptr [r12], 1
0x180020af5  lea     rcx, g_TaskHostContextListLock
0x180020afc  mov     cs:dword_18004CF18, esi
0x180020b02  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180020b08  mov     rdi, [rsp+68h+arg_8]
0x180020b0d  mov     eax, ebx
0x180020b0f  add     rsp, 30h
0x180020b13  pop     r15
0x180020b15  pop     r14
0x180020b17  pop     r13
0x180020b19  pop     r12
0x180020b1b  pop     rsi
0x180020b1c  pop     rbp
0x180020b1d  pop     rbx
0x180020b1e  retn
0x180020b1f  lea     rdx, [rsp+68h+arg_28]
0x180020b27  mov     ecx, ebp
0x180020b29  call    UbpmpCreatePartiallyInitializedTaskHostContextBlock
0x180020b2e  mov     ebx, eax
0x180020b30  test    eax, eax
0x180020b32  jnz     loc_180020C94
0x180020b38  mov     rcx, cs:off_18004C130
0x180020b3f  cmp     [rcx], rdi
0x180020b42  jnz     loc_180020BD0
0x180020b48  mov     rdx, [rsp+68h+arg_28]
0x180020b50  mov     ebx, 490h
0x180020b55  lea     rax, [rdx+8]
0x180020b59  mov     [r15], rdx
0x180020b5c  mov     [rax], rdi
0x180020b5f  mov     [rax+8], rcx
0x180020b63  mov     [rcx], rax
0x180020b66  mov     cs:off_18004C130, rax
0x180020b6d  xor     esi, esi
0x180020b6f  jmp     short loc_180020AF5
0x180020b71  mov     ebx, 45Bh
0x180020b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b7d  lea     rax, WPP_GLOBAL_Control
0x180020b84  cmp     rcx, rax
0x180020b87  jz      short loc_180020B6D
0x180020b89  test    byte ptr [rcx+1Ch], 80h
0x180020b8d  jz      short loc_180020B6D
0x180020b8f  mov     edx, 0B0h
0x180020b94  mov     r9d, ebx
0x180020b97  jmp     short loc_180020C10
0x180020b99  cmp     qword ptr [rdi+0B8h], 0
0x180020ba1  jnz     loc_1800209B2
0x180020ba7  jmp     loc_180020A54
0x180020bac  mov     rcx, [rcx]
0x180020baf  jmp     loc_180020AC2
0x180020bb4  mov     rax, [r14+20h]
0x180020bb8  mov     rcx, [rax+28h]
0x180020bbc  mov     rax, rcx
0x180020bbf  and     rax, rdx
0x180020bc2  cmp     rax, rcx
0x180020bc5  jnz     loc_1800209B2
0x180020bcb  jmp     loc_180020A30
0x180020bd0  mov     ecx, 3
0x180020bd5  int     29h; Win8: RtlFailFast(ecx)
0x180020bd7  mov     rax, [r14+20h]
0x180020bdb  mov     rcx, [rax+8]
0x180020bdf  mov     rcx, [rcx+8]
0x180020be3  jmp     loc_180020A47
0x180020be8  mov     rax, [rcx+8]
0x180020bec  mov     rcx, [rax+8]
0x180020bf0  jmp     loc_180020A16
0x180020bf5  call    cs:__imp_RtlReleaseSRWLockShared
0x180020bfb  movzx   esi, [rsp+68h+arg_18]
0x180020c03  jmp     loc_1800209B2
0x180020c08  mov     edx, 0B2h
0x180020c0d  mov     r9d, r13d
0x180020c10  mov     rcx, [rcx+10h]
0x180020c14  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180020c1b  call    WPP_SF_d
0x180020c20  jmp     loc_180020B6D
0x180020c25  mov     rcx, [r14+20h]
0x180020c29  movzx   eax, byte ptr [rcx+31h]
0x180020c2d  test    al, al
0x180020c2f  jnz     short loc_180020C43
0x180020c31  cmp     dword ptr [rdi+188h], 0
0x180020c38  jz      loc_180020A54
0x180020c3e  jmp     loc_1800209B2
0x180020c43  cmp     al, 1
0x180020c45  jnz     loc_1800209B2
0x180020c4b  cmp     dword ptr [rdi+188h], 0
0x180020c52  jbe     loc_1800209B2
0x180020c58  mov     edx, [rcx+48h]
0x180020c5b  movzx   r9d, sil
0x180020c5f  mov     rcx, [rcx+40h]; String2
0x180020c63  mov     r8, rdi
0x180020c66  call    UbpmpIsConsumerSidPresent
0x180020c6b  test    al, al
0x180020c6d  jz      loc_1800209B2
0x180020c73  jmp     loc_180020A54
0x180020c78  mov     r9d, [rdi+20h]
0x180020c7c  mov     rcx, [rcx+10h]
0x180020c80  mov     [rsp+68h+var_40], rdi
0x180020c85  mov     [rsp+68h+var_48], r13d
0x180020c8a  call    WPP_SF_ddq
0x180020c8f  jmp     loc_180020A9B
0x180020c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c9b  lea     rax, WPP_GLOBAL_Control
0x180020ca2  cmp     rcx, rax
0x180020ca5  jz      loc_180020B6D
0x180020cab  test    byte ptr [rcx+1Ch], 1
0x180020caf  jz      loc_180020B6D
0x180020cb5  jmp     loc_180020C08
```
