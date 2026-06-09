# SamrCloseHandle

- ea: `0x18000a570`
- end: `0x18000ae02`
- name: `SamrCloseHandle`
- size: `2194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `36`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18005bc50`
- `0x1800662a4`
- `0x1800673d4`
- `0x180068dd0`
- `0x18006a730`
- `0x18006af68`
- `0x18006b0e0`
- `0x18006bee8`
- `0x18006c280`
- `0x18006c858`
- `0x18006dde0`
- `0x18006e5b0`
- `0x18006ea94`
- `0x18006efb4`
- `0x18006f42c`
- `0x180072b30`
- `0x180073370`
- `0x180073870`
- `0x180075fec`
- `0x1800884a4`
- `0x18008ff20`
- `0x180090030`
- `0x1800901a0`
- `0x18009109c`
- `0x1800930f8`
- `0x180093d5c`
- `0x1800975e0`
- `0x1800989d0`
- `0x18009b224`
- `0x18009bd34`
- `0x18009c588`
- `0x1800a15bc`
- `0x1800a3440`
- `0x1800a3d10`
- `0x1800a6e50`
- `0x1800acd48`

## callees

- `0x1800022a0`
- `0x180008590`
- `0x1800096c0`
- `0x18000a570`
- `0x18000ae10`
- `0x180012a28`
- `0x18001cfa0`
- `0x180024dc0`
- `0x1800270b4`
- `0x180027e24`
- `0x180027ef8`
- `0x180037284`
- `0x1800372ac`
- `0x1800372ec`
- `0x18004db98`
- `0x18008ecd0`
- `0x1800ab8c0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18000a84d`
- `ntdll!NtSetEvent` at `0x18000a84d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a60a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a60a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a5e5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a5e5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000a5fa`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000a5fa`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000a8a1`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000a8a1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a7ca`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a91a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a7ca`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a91a`
- `ntdll!RtlEnterCriticalSection` at `0x18000a68e`
- `ntdll!RtlEnterCriticalSection` at `0x18000a8e2`
- `ntdll!RtlEnterCriticalSection` at `0x18000a68e`
- `ntdll!RtlEnterCriticalSection` at `0x18000a8e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a678`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a69b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a7af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a678`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a69b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a7af`
- `RPCRT4!RpcRevertToSelf` at `0x18000a8b1`
- `RPCRT4!RpcRevertToSelf` at `0x18000a8b1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18000ab50`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18000ab50`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000abdd`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000abdd`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x18000ad4c`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x18000ad4c`

## pseudocode

```c
__int64 __fastcall SamrCloseHandle(_QWORD *a1)
{
  _QWORD *v2; // rsi
  int v3; // r15d
  char v4; // bp
  PVOID v5; // rbx
  PUNICODE_STRING v6; // rcx
  int v7; // edi
  DWORD TickCount; // ebx
  DWORD v9; // eax
  unsigned int v10; // ecx
  DWORD v11; // eax
  unsigned int v12; // eax
  int v13; // edi
  PUNICODE_STRING v14; // rcx
  char v15; // r13
  union _LARGE_INTEGER v16; // rbx
  PUNICODE_STRING v17; // rcx
  bool v18; // si
  signed int v19; // eax
  int v20; // edx
  int v21; // r8d
  PUNICODE_STRING v22; // rcx
  DWORD LowPart; // r12d
  bool v25; // zf
  char v26; // cl
  __int64 v27; // rcx
  _QWORD *v28; // rax
  unsigned int v29; // eax
  PUNICODE_STRING v30; // rcx
  unsigned int v31; // eax
  DWORD v32; // r12d
  const wchar_t *v33; // r9
  unsigned int v34; // [rsp+70h] [rbp+8h] BYREF
  union _LARGE_INTEGER v35; // [rsp+78h] [rbp+10h] BYREF
  _QWORD *Buffer; // [rsp+80h] [rbp+18h] BYREF

  v34 = 5;
  v35.QuadPart = 0;
  SampTraceEvent(1);
  if ( !a1 || (v2 = (_QWORD *)*a1) == 0 )
  {
    v13 = -1073741816;
    SampTraceEvent(2);
    goto LABEL_44;
  }
  v3 = v2[24] & 2;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control[3].Buffer, 10, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, *a1);
  Buffer = v2;
  v4 = 0;
  RtlAcquireSRWLockShared(&SampClientContextLock);
  v5 = RtlLookupElementGenericTableAvl(&SampClientContextTableAVL, &Buffer);
  RtlReleaseSRWLockShared(&SampClientContextLock);
  v6 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 51, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v5 != 0);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    v7 = 0;
    if ( *((_DWORD *)v2 + 6) != -294125688 )
      v7 = -1073741816;
  }
  else
  {
    v7 = -1073545211;
  }
  if ( (*(_DWORD *)(&v6[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v6[3].Buffer, 15, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, (unsigned int)v7, v7);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v7 >= 0 )
  {
    if ( (v2[24] & 2) != 0 && (*((_BYTE *)v2 + 28) & 1) != 0 )
    {
      SampIncrementActiveThreads(v6);
    }
    else
    {
      if ( (*(_DWORD *)(&v6[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(v6[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
      if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
      {
        TickCount = GetTickCount();
        _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
        RtlEnterCriticalSection(&SampLock);
        _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
        v9 = GetTickCount();
        v10 = SamLockTotalAquisitions + 1;
        SamLockCurrentHoldStartTime = v9;
        ++SamLockTotalAquisitions;
        v11 = v9 - TickCount;
        if ( v11 && v10 )
          SamCumulativeWaitTime += v11;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
        if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
          NtdsaExtSetGlobalTransactionType(0);
      }
      v4 = 1;
    }
  }
  v12 = SampLookupContextEx((__int64)v2, 0xFFFFFFFF, 0, 5, &v34);
  v13 = v12;
  v14 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v12, v12);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v13 >= 0 )
  {
    v15 = *((_BYTE *)v2 + 1448);
    v16 = (union _LARGE_INTEGER)v2[182];
    if ( (*(_BYTE *)(&v14[4].MaximumLength + 1) & 8) != 0 && HIBYTE(v14[4].Length) >= 4u )
      WPP_SF_d(v14[3].Buffer, 11, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, v34);
    *((_BYTE *)v2 + 20) |= 0x10u;
    LowPart = 0;
    v25 = (*((_BYTE *)v2 + 20) & 0x20) == 0;
    v35.LowPart = 0;
    if ( v25 )
    {
      SampImpersonateClient((int *)&v35);
      LowPart = v35.LowPart;
    }
    NtCloseObjectAuditAlarm(&SampSamSubsystem, v2, *((_BYTE *)v2 + 208));
    if ( LowPart == 2 )
    {
      RpcRevertToSelf();
    }
    else
    {
      v32 = LowPart - 1;
      if ( v32 )
      {
        if ( v32 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
          NtdsaExtUnImpersonateAnyClient();
      }
      else
      {
        SamIRevertNullSession();
      }
    }
    *((_BYTE *)v2 + 21) &= ~1u;
    v26 = *((_BYTE *)v2 + 28);
    if ( ((unsigned __int8)v26 & ((v2[24] & 2) != 0)) == 0 && v26 >= 0 )
    {
      RtlEnterCriticalSection(&SampContextListCritSect);
      v27 = *v2;
      if ( *v2 )
      {
        v28 = (_QWORD *)v2[1];
        if ( v28 )
        {
          if ( *(_QWORD **)(v27 + 8) != v2 || (_QWORD *)*v28 != v2 )
            __fastfail(3u);
          *v28 = v27;
          *(_QWORD *)(v27 + 8) = v28;
        }
      }
      RtlLeaveCriticalSection(&SampContextListCritSect);
    }
    SampDeReferenceContext((__int64)v2, 0);
    SampDeReferenceContext((__int64)v2, 0);
    *a1 = 0;
    v14 = WPP_GLOBAL_Control;
  }
  else
  {
    v15 = 0;
    if ( (*(_BYTE *)(&v14[4].MaximumLength + 1) & 8) != 0 && HIBYTE(v14[4].Length) >= 2u )
    {
      WPP_SF_d(v14[3].Buffer, 12, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, (unsigned int)v13);
      v14 = WPP_GLOBAL_Control;
    }
    v16 = v35;
  }
  if ( v4 )
  {
    if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(v14[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( SampUseDsData && (unsigned int)SampExtIsWriteLockHeldByDs() )
    {
      SampSetTransactionWithinDomain(0);
    }
    else
    {
      if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
      {
        v17 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
          v17 = WPP_GLOBAL_Control;
        }
        SampTransactionWithinDomainGlobal = 0;
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
          v17 = WPP_GLOBAL_Control;
        }
        if ( (*(_BYTE *)(&v17[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v17[4].Length) >= 2u )
        {
          WPP_SF_(v17[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
          v17 = WPP_GLOBAL_Control;
        }
      }
      v18 = SampUseDsData && !SampDsStopped;
      if ( (*(_DWORD *)(&v17[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(v17[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v18);
      if ( v18 )
        SampExtMaybeEndDsTransactionDs(3);
      v19 = GetTickCount() - SamLockCurrentHoldStartTime;
      if ( v19 > 0 && SamLockTotalAquisitions )
        SamCumulativeHoldTime += v19;
      RtlLeaveCriticalSection(&SampLock);
    }
  }
  else
  {
    if ( (int)SampShouldCallNtdsaApiSet() >= 0 )
      NtdsaExtMaybeEndDsTransaction(3);
    if ( _InterlockedDecrement((volatile signed __int32 *)&SampActiveThreadCount) == 0x40000000 )
      NtSetEvent(SampShutdownEventHandle, 0);
  }
  if ( v13 >= 0 )
  {
    v29 = v34;
    if ( !v34 && !v3 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      {
LABEL_68:
        if ( !v29 && !v3 && v15 == 1 && v16.QuadPart >= LastFlushTimestamp.QuadPart )
        {
          if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v30[4].Length) >= 4u )
            WPP_SF_(v30[3].Buffer, 14, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids);
          v31 = SampFlushRegistryHive();
          v13 = v31;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 15, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, v31);
          }
        }
        goto LABEL_43;
      }
      v33 = L"TRUE";
      if ( !v15 )
        v33 = (const wchar_t *)L"FALSE";
      WPP_SF_Sii(WPP_GLOBAL_Control[3].Buffer, v20, v21, (_DWORD)v33, v16.QuadPart, LastFlushTimestamp.QuadPart);
      v29 = v34;
    }
    v30 = WPP_GLOBAL_Control;
    goto LABEL_68;
  }
LABEL_43:
  SampTraceEvent(2);
  if ( v13 < 0 )
  {
LABEL_44:
    v22 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 17, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, (unsigned int)v13);
      goto LABEL_122;
    }
    goto LABEL_45;
  }
  v22 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 16, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids);
LABEL_122:
    v22 = WPP_GLOBAL_Control;
  }
LABEL_45:
  if ( (*(_DWORD *)(&v22[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v22[3].Buffer, 18, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids, (unsigned int)v13, v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a570  push    rbx
0x18000a572  push    rbp
0x18000a573  push    rsi
0x18000a574  push    rdi
0x18000a575  push    r13
0x18000a577  push    r14
0x18000a579  push    r15
0x18000a57b  sub     rsp, 30h
0x18000a57f  mov     edx, 1
0x18000a584  mov     [rsp+68h+arg_0], 5
0x18000a58c  mov     r14, rcx
0x18000a58f  mov     [rsp+68h+arg_8], 0
0x18000a598  mov     ecx, edx
0x18000a59a  xor     r8d, r8d
0x18000a59d  call    SampTraceEvent
0x18000a5a2  test    r14, r14
0x18000a5a5  jz      loc_18000AA3F
0x18000a5ab  mov     rsi, [r14]
0x18000a5ae  test    rsi, rsi
0x18000a5b1  jz      loc_18000AA3F
0x18000a5b7  mov     r15d, [rsi+0C0h]
0x18000a5be  and     r15d, 2
0x18000a5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5c9  test    byte ptr [rcx+44h], 8
0x18000a5cd  jnz     loc_18000AA5E
0x18000a5d3  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x18000a5da  mov     [rsp+68h+Buffer], rsi
0x18000a5e2  xor     bpl, bpl
0x18000a5e5  call    cs:__imp_RtlAcquireSRWLockShared
0x18000a5eb  lea     rdx, [rsp+68h+Buffer]; Buffer
0x18000a5f3  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x18000a5fa  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000a600  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x18000a607  mov     rbx, rax
0x18000a60a  call    cs:__imp_RtlReleaseSRWLockShared
0x18000a610  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a617  test    dword ptr [rcx+44h], 20000h
0x18000a61e  jnz     loc_18000AA85
0x18000a624  test    rbx, rbx
0x18000a627  jz      loc_18000AAB0
0x18000a62d  xor     edi, edi
0x18000a62f  cmp     dword ptr [rsi+18h], 0EE77FF88h
0x18000a636  jnz     loc_18000AABA
0x18000a63c  test    dword ptr [rcx+44h], 20000h
0x18000a643  jnz     loc_18000AA17
0x18000a649  test    edi, edi
0x18000a64b  js      loc_18000A6E1
0x18000a651  test    byte ptr [rsi+0C0h], 2
0x18000a658  jnz     loc_18000AAC4
0x18000a65e  test    dword ptr [rcx+44h], 20000h
0x18000a665  jnz     loc_18000AAD8
0x18000a66b  cmp     cs:?SampUseDsData@@3EA, bpl; uchar SampUseDsData
0x18000a672  jnz     loc_18000AAFA
0x18000a678  call    cs:__imp_GetTickCount
0x18000a67e  mov     ebx, eax
0x18000a680  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18000a687  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000a68e  call    cs:__imp_RtlEnterCriticalSection
0x18000a694  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18000a69b  call    cs:__imp_GetTickCount
0x18000a6a1  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x18000a6a7  inc     ecx
0x18000a6a9  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x18000a6af  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x18000a6b5  sub     eax, ebx
0x18000a6b7  jnz     loc_18000AB0C
0x18000a6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6c4  test    dword ptr [rcx+44h], 20000h
0x18000a6cb  jnz     loc_18000AB1F
0x18000a6d1  cmp     cs:?SampUseDsData@@3EA, bpl; uchar SampUseDsData
0x18000a6d8  jnz     loc_18000AB41
0x18000a6de  mov     bpl, 1
0x18000a6e1  lea     rax, [rsp+68h+arg_0]
0x18000a6e6  mov     r9d, 5
0x18000a6ec  xor     r8d, r8d
0x18000a6ef  mov     [rsp+68h+var_48], rax
0x18000a6f4  mov     edx, 0FFFFFFFFh
0x18000a6f9  mov     rcx, rsi
0x18000a6fc  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x18000a701  mov     edi, eax
0x18000a703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a70a  test    dword ptr [rcx+44h], 20000h
0x18000a711  jnz     loc_18000AB5B
0x18000a717  test    edi, edi
0x18000a719  jns     loc_18000A858
0x18000a71f  xor     r13b, r13b
0x18000a722  test    byte ptr [rcx+44h], 8
0x18000a726  jnz     loc_18000ABF9
0x18000a72c  mov     rbx, [rsp+68h+arg_8]
0x18000a731  test    bpl, bpl
0x18000a734  jz      loc_18000A821
0x18000a73a  test    dword ptr [rcx+44h], 20000h
0x18000a741  jnz     loc_18000AC27
0x18000a747  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18000a74e  jnz     loc_18000AC49
0x18000a754  mov     rax, gs:30h
0x18000a75d  mov     rcx, [rax+48h]
0x18000a761  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rcx; _RTL_CRITICAL_SECTION SampLock ...
0x18000a768  jnz     loc_18000AC89
0x18000a76e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a775  test    dword ptr [rcx+44h], 20000h
0x18000a77c  jnz     loc_18000AC62
0x18000a782  mov     cs:?SampTransactionWithinDomainGlobal@@3EA, 0; uchar SampTransactionWithinDomainGlobal
0x18000a789  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18000a790  jnz     loc_18000ACED
0x18000a796  xor     sil, sil
0x18000a799  test    dword ptr [rcx+44h], 20000h
0x18000a7a0  jnz     loc_18000AD02
0x18000a7a6  test    sil, sil
0x18000a7a9  jnz     loc_18000AD20
0x18000a7af  call    cs:__imp_GetTickCount
0x18000a7b5  sub     eax, cs:?SamLockCurrentHoldStartTime@@3KA; ulong SamLockCurrentHoldStartTime
0x18000a7bb  test    eax, eax
0x18000a7bd  jg      loc_18000AD2F
0x18000a7c3  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000a7ca  call    cs:__imp_RtlLeaveCriticalSection
0x18000a7d0  test    edi, edi
0x18000a7d2  jns     loc_18000A947
0x18000a7d8  mov     r8d, edi
0x18000a7db  mov     edx, 1
0x18000a7e0  mov     ecx, 2
0x18000a7e5  call    SampTraceEvent
0x18000a7ea  test    edi, edi
0x18000a7ec  jns     loc_18000A9E2
0x18000a7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7f9  test    byte ptr [rcx+44h], 8
0x18000a7fd  jnz     loc_18000ADB3
0x18000a803  test    dword ptr [rcx+44h], 20000h
0x18000a80a  jnz     loc_18000ADE1
0x18000a810  mov     eax, edi
0x18000a812  add     rsp, 30h
0x18000a816  pop     r15
0x18000a818  pop     r14
0x18000a81a  pop     r13
0x18000a81c  pop     rdi
0x18000a81d  pop     rsi
0x18000a81e  pop     rbp
0x18000a81f  pop     rbx
0x18000a820  retn
0x18000a821  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18000a826  test    eax, eax
0x18000a828  jns     loc_18000AD47
0x18000a82e  mov     eax, 0FFFFFFFFh
0x18000a833  lock xadd cs:?SampActiveThreadCount@@3KA, eax; ulong SampActiveThreadCount
0x18000a83b  dec     eax
0x18000a83d  cmp     eax, 40000000h
0x18000a842  jnz     short loc_18000A7D0
0x18000a844  mov     rcx, cs:?SampShutdownEventHandle@@3PEAXEA; EventHandle
0x18000a84b  xor     edx, edx; PreviousState
0x18000a84d  call    cs:__imp_NtSetEvent
0x18000a853  jmp     loc_18000A7D0
0x18000a858  movzx   r13d, byte ptr [rsi+5A8h]
0x18000a860  mov     rbx, [rsi+5B0h]
0x18000a867  mov     [rsp+68h+arg_18], r12
0x18000a86f  test    byte ptr [rcx+44h], 8
0x18000a873  jnz     loc_18000AB83
0x18000a879  or      byte ptr [rsi+14h], 10h
0x18000a87d  xor     r12d, r12d
0x18000a880  test    byte ptr [rsi+14h], 20h
0x18000a884  mov     dword ptr [rsp+68h+arg_8], r12d
0x18000a889  jz      loc_18000ABAC
0x18000a88f  movzx   r8d, byte ptr [rsi+0D0h]; GenerateOnClose
0x18000a897  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x18000a89e  mov     rdx, rsi; HandleId
0x18000a8a1  call    cs:__imp_NtCloseObjectAuditAlarm
0x18000a8a7  cmp     r12d, 2
0x18000a8ab  jnz     loc_18000ABC0
0x18000a8b1  call    cs:__imp_RpcRevertToSelf
0x18000a8b7  and     byte ptr [rsi+15h], 0FEh
0x18000a8bb  test    byte ptr [rsi+0C0h], 2
0x18000a8c2  movzx   ecx, byte ptr [rsi+1Ch]
0x18000a8c6  mov     r12, [rsp+68h+arg_18]
0x18000a8ce  setnz   al
0x18000a8d1  and     al, cl
0x18000a8d3  test    al, 1
0x18000a8d5  jnz     short loc_18000A920
0x18000a8d7  test    cl, cl
0x18000a8d9  js      short loc_18000A920
0x18000a8db  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000a8e2  call    cs:__imp_RtlEnterCriticalSection
0x18000a8e8  mov     rcx, [rsi]
0x18000a8eb  test    rcx, rcx
0x18000a8ee  jz      short loc_18000A913
0x18000a8f0  mov     rax, [rsi+8]
0x18000a8f4  test    rax, rax
0x18000a8f7  jz      short loc_18000A913
0x18000a8f9  cmp     [rcx+8], rsi
0x18000a8fd  jnz     loc_18000ABF2
0x18000a903  cmp     [rax], rsi
0x18000a906  jnz     loc_18000ABF2
0x18000a90c  mov     [rax], rcx
0x18000a90f  mov     [rcx+8], rax
0x18000a913  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000a91a  call    cs:__imp_RtlLeaveCriticalSection
0x18000a920  xor     edx, edx
0x18000a922  mov     rcx, rsi
0x18000a925  call    SampDeReferenceContext
0x18000a92a  xor     edx, edx
0x18000a92c  mov     rcx, rsi
0x18000a92f  call    SampDeReferenceContext
0x18000a934  mov     qword ptr [r14], 0
0x18000a93b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a942  jmp     loc_18000A731
0x18000a947  mov     eax, [rsp+68h+arg_0]
0x18000a94b  test    eax, eax
0x18000a94d  jz      loc_18000AD57
0x18000a953  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a95a  test    eax, eax
0x18000a95c  jnz     loc_18000A7D8
0x18000a962  test    r15d, r15d
0x18000a965  jnz     loc_18000A7D8
0x18000a96b  cmp     r13b, 1
0x18000a96f  jnz     loc_18000A7D8
0x18000a975  cmp     rbx, qword ptr cs:?LastFlushTimestamp@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LastFlushTimestamp ...
0x18000a97c  jl      loc_18000A7D8
0x18000a982  test    byte ptr [rcx+44h], 4
0x18000a986  jz      short loc_18000A9A3
0x18000a988  cmp     byte ptr [rcx+41h], 4
0x18000a98c  jb      short loc_18000A9A3
0x18000a98e  mov     rcx, [rcx+38h]
0x18000a992  lea     r8, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids
0x18000a999  mov     edx, 0Eh
0x18000a99e  call    WPP_SF_
0x18000a9a3  call    ?SampFlushRegistryHive@@YAJXZ; SampFlushRegistryHive(void)
0x18000a9a8  mov     edi, eax
0x18000a9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9b1  test    byte ptr [rcx+44h], 4
0x18000a9b5  jz      loc_18000A7D8
0x18000a9bb  cmp     byte ptr [rcx+41h], 4
0x18000a9bf  jb      loc_18000A7D8
0x18000a9c5  mov     rcx, [rcx+38h]
0x18000a9c9  lea     r8, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids
0x18000a9d0  mov     edx, 0Fh
0x18000a9d5  mov     r9d, eax
0x18000a9d8  call    WPP_SF_d
0x18000a9dd  jmp     loc_18000A7D8
0x18000a9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9e9  test    byte ptr [rcx+44h], 8
0x18000a9ed  jz      loc_18000A803
0x18000a9f3  cmp     byte ptr [rcx+41h], 4
0x18000a9f7  jb      loc_18000A803
0x18000a9fd  mov     rcx, [rcx+38h]
0x18000aa01  lea     r8, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids
0x18000aa08  mov     edx, 10h
0x18000aa0d  call    WPP_SF_
0x18000aa12  jmp     loc_18000ADD5
0x18000aa17  mov     rcx, [rcx+38h]
0x18000aa1b  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18000aa22  mov     edx, 0Fh
0x18000aa27  mov     dword ptr [rsp+68h+var_48], edi
0x18000aa2b  mov     r9d, edi
0x18000aa2e  call    WPP_SF_Dd
0x18000aa33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa3a  jmp     loc_18000A649
0x18000aa3f  mov     edx, 1
0x18000aa44  mov     ecx, 2
0x18000aa49  mov     r8d, 0C0000008h
0x18000aa4f  mov     edi, 0C0000008h
0x18000aa54  call    SampTraceEvent
0x18000aa59  jmp     loc_18000A7F2
0x18000aa5e  cmp     byte ptr [rcx+41h], 4
0x18000aa62  jb      loc_18000A5D3
0x18000aa68  mov     rcx, [rcx+38h]
0x18000aa6c  lea     r8, WPP_81f5cf520d27374bdccd04ae61b7db31_Traceguids
0x18000aa73  mov     edx, 0Ah
0x18000aa78  mov     r9, rsi
0x18000aa7b  call    WPP_SF_q
0x18000aa80  jmp     loc_18000A5D3
0x18000aa85  mov     rcx, [rcx+38h]
0x18000aa89  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18000aa90  xor     r9d, r9d
0x18000aa93  mov     edx, 33h ; '3'
0x18000aa98  test    rbx, rbx
0x18000aa9b  setnz   r9b
0x18000aa9f  call    WPP_SF_d
0x18000aaa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaab  jmp     loc_18000A624
0x18000aab0  mov     edi, 0C0030005h
0x18000aab5  jmp     loc_18000A63C
0x18000aaba  mov     edi, 0C0000008h
0x18000aabf  jmp     loc_18000A63C
0x18000aac4  test    byte ptr [rsi+1Ch], 1
0x18000aac8  jz      loc_18000A65E
0x18000aace  call    SampIncrementActiveThreads
0x18000aad3  jmp     loc_18000A6E1
0x18000aad8  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18000aae0  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18000aae7  mov     rcx, [rcx+38h]
0x18000aaeb  mov     edx, 49h ; 'I'
0x18000aaf0  call    WPP_SF_d
0x18000aaf5  jmp     loc_18000A66B
0x18000aafa  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x18000aaff  test    eax, eax
0x18000ab01  jnz     loc_18000A6DE
0x18000ab07  jmp     loc_18000A678
0x18000ab0c  test    ecx, ecx
0x18000ab0e  jz      loc_18000A6BD
0x18000ab14  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x18000ab1a  jmp     loc_18000A6BD
0x18000ab1f  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
  ... truncated ...
```
