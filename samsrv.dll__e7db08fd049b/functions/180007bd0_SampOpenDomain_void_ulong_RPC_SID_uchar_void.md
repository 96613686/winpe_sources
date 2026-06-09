# SampOpenDomain(void *,ulong,_RPC_SID *,uchar,void * *)

- ea: `0x180007bd0`
- end: `0x180008583`
- name: `?SampOpenDomain@@YAJPEAXKPEAU_RPC_SID@@EPEAPEAX@Z`
- size: `2483`
- prototype: `int(void *, unsigned int, struct _RPC_SID *, unsigned __int8, void **)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025dd0`
- `0x1800673d4`
- `0x18006efb4`
- `0x180093d5c`

## callees

- `0x1800022a0`
- `0x180006800`
- `0x180007bd0`
- `0x180008590`
- `0x1800096c0`
- `0x180011810`
- `0x180012a28`
- `0x180017a60`
- `0x18001cfa0`
- `0x180024dc0`
- `0x1800270b4`
- `0x180027e24`
- `0x180027ef8`
- `0x180037284`
- `0x1800372ac`
- `0x18008ecd0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x1800080ac`
- `ntdll!NtSetEvent` at `0x1800080ac`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007cd2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007cd2`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007cad`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007cad`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180007cc2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180007cc2`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000811b`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000811b`
- `ntdll!RtlLeaveCriticalSection` at `0x180007fde`
- `ntdll!RtlLeaveCriticalSection` at `0x180008180`
- `ntdll!RtlLeaveCriticalSection` at `0x180007fde`
- `ntdll!RtlLeaveCriticalSection` at `0x180008180`
- `ntdll!RtlEnterCriticalSection` at `0x180007d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180008148`
- `ntdll!RtlEnterCriticalSection` at `0x180007d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180008148`
- `ntdll!RtlValidSid` at `0x180007c02`
- `ntdll!RtlValidSid` at `0x180007c02`
- `ntdll!RtlEqualSid` at `0x1800080d8`
- `ntdll!RtlEqualSid` at `0x1800080d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d68`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007fc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d68`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007fc3`
- `RPCRT4!RpcRevertToSelf` at `0x18000812b`
- `RPCRT4!RpcRevertToSelf` at `0x18000812b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180008320`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180008320`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x1800083ff`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x1800083ff`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x180008550`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x180008550`

## pseudocode

```c
__int64 __fastcall SampOpenDomain(__int64 a1, DWORD a2, struct _RPC_SID *a3, char a4, void **a5)
{
  unsigned int v6; // r12d
  int v10; // edi
  unsigned int v11; // ebx
  int v12; // ebp
  PUNICODE_STRING v13; // r10
  unsigned __int8 v14; // dl
  __int64 v15; // rbx
  char v16; // bp
  PVOID v17; // rdi
  int v18; // edi
  DWORD TickCount; // ebx
  DWORD v20; // eax
  unsigned int v21; // ecx
  DWORD v22; // eax
  unsigned int v23; // eax
  PUNICODE_STRING v24; // rcx
  __int64 Context; // rax
  __int64 v26; // r9
  __int64 v27; // rbx
  char v28; // cl
  __int64 v29; // r8
  char *v30; // rdx
  __int64 v31; // rax
  unsigned int v32; // eax
  PUNICODE_STRING v33; // rcx
  bool v34; // bl
  signed int v35; // eax
  unsigned int v37; // eax
  int v38; // r14d
  bool v39; // zf
  char v40; // al
  __int64 v41; // rcx
  _QWORD *v42; // rax
  int v43; // r14d
  _DWORD v44[4]; // [rsp+50h] [rbp-38h] BYREF
  __int64 Buffer; // [rsp+90h] [rbp+8h] BYREF

  v6 = 0;
  v44[0] = 0;
  v10 = -1073741601;
  if ( RtlValidSid(a3) )
  {
    v11 = SampDefinedDomainsCount;
    v12 = -1073741601;
    if ( a4 )
      v11 = 2;
    while ( v11 )
    {
      if ( RtlEqualSid(a3, *((PSID *)SampDefinedDomains + 170 * --v11 + 1)) )
      {
        v6 = v11;
        v12 = 0;
        break;
      }
    }
  }
  else
  {
    v12 = -1073741811;
  }
  v13 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      137,
      &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
      (unsigned int)v12,
      v12);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12 < 0 )
  {
    v10 = v12;
  }
  else
  {
    if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      WPP_SF_d(v13[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
      v13 = WPP_GLOBAL_Control;
    }
    v14 = SampUseDsData;
    if ( !SampUseDsData || !*(_BYTE *)(a1 + 856) || v6 >= 2 )
    {
      v15 = *((_QWORD *)SampDefinedDomains + 170 * v6);
      if ( (*(_BYTE *)(v15 + 192) & 2) != 0 )
        v15 = a1;
      if ( v15 )
      {
        Buffer = v15;
        v16 = 0;
        RtlAcquireSRWLockShared(&SampClientContextLock);
        v17 = RtlLookupElementGenericTableAvl(&SampClientContextTableAVL, &Buffer);
        RtlReleaseSRWLockShared(&SampClientContextLock);
        v13 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 51, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v17 != 0);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v17 )
        {
          v18 = 0;
          if ( *(_DWORD *)(v15 + 24) != -294125688 )
            v18 = -1073741816;
        }
        else
        {
          v18 = -1073545211;
        }
        if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_Dd(v13[3].Buffer, 15, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, (unsigned int)v18, v18);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v18 < 0 )
        {
LABEL_32:
          v23 = SampLookupContextEx(a1, 0x20u, 0, 0, v44);
          v10 = v23;
          v24 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v23, v23);
            v24 = WPP_GLOBAL_Control;
          }
          if ( v10 >= 0 )
          {
            Context = SampCreateContextEx(
                        1,
                        (*(_BYTE *)(a1 + 20) & 0x20) != 0,
                        *(_BYTE *)(a1 + 28) & 1,
                        *(_BYTE *)(a1 + 20) >> 7,
                        0,
                        0,
                        0,
                        0,
                        v6);
            v27 = Context;
            if ( Context )
            {
              v28 = *(_BYTE *)(Context + 20);
              *(_DWORD *)(Context + 204) = *(_DWORD *)(a1 + 204);
              *(_BYTE *)(Context + 20) ^= (*(_BYTE *)(a1 + 20) ^ v28) & 0x40;
              if ( (*(_BYTE *)(a1 + 192) & 2) == 0 )
              {
                _InterlockedIncrement((volatile signed __int32 *)(a1 + 144));
                *(_QWORD *)(Context + 1440) = a1;
              }
              v29 = *(unsigned int *)(Context + 200);
              *(_BYTE *)(Context + 29) ^= (*(_BYTE *)(a1 + 29) ^ *(_BYTE *)(Context + 29)) & 0x20;
              v30 = (char *)SampDefinedDomains + 1360 * v29;
              v31 = *(_QWORD *)v30;
              if ( (*(_BYTE *)(*(_QWORD *)v30 + 192LL) & 2) != 0 )
              {
                *(_QWORD *)(v27 + 176) = *(_QWORD *)(v31 + 176);
                *(_DWORD *)(v27 + 192) = *(_DWORD *)(*(_QWORD *)v30 + 192LL);
              }
              else
              {
                *(_QWORD *)(v27 + 152) = *(_QWORD *)(v31 + 152);
                *(_OWORD *)(v27 + 160) = *(_OWORD *)(*(_QWORD *)v30 + 160LL);
                SampSetTransactionDomain((unsigned int)v29);
              }
              _InterlockedIncrement((volatile signed __int32 *)(v27 + 144));
              v32 = SampValidateObjectAccess2((struct _SAMP_OBJECT *)v27, a2, 0, v26, 0, 0);
              v10 = v32;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 18, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v32, v32);
              if ( v10 >= 0
                && *((_BYTE *)SampDefinedDomains + 1360 * *(unsigned int *)(v27 + 200) + 1336)
                && *(_DWORD *)(v27 + 204) < 3u )
              {
                v10 = -1073741637;
              }
              if ( v16 )
              {
                SampDeReferenceContext(v27, 0);
              }
              else if ( (*(_BYTE *)(v27 + 192) & 2) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v27 + 144));
                if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                  WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 33, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, 0, 0);
              }
              else
              {
                v37 = SampDeReferenceContext(v27, 0);
                if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                  WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 32, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v37, v37);
              }
              if ( v10 < 0 )
              {
                *(_BYTE *)(v27 + 20) |= 0x10u;
                v38 = 0;
                v39 = (*(_BYTE *)(v27 + 20) & 0x20) == 0;
                LODWORD(Buffer) = 0;
                if ( v39 )
                {
                  SampImpersonateClient(&Buffer);
                  v38 = Buffer;
                }
                NtCloseObjectAuditAlarm(&SampSamSubsystem, (PVOID)v27, *(_BYTE *)(v27 + 208));
                if ( v38 == 2 )
                {
                  RpcRevertToSelf();
                }
                else
                {
                  v43 = v38 - 1;
                  if ( v43 )
                  {
                    if ( v43 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
                      NtdsaExtUnImpersonateAnyClient();
                  }
                  else
                  {
                    SamIRevertNullSession();
                  }
                }
                *(_BYTE *)(v27 + 21) &= ~1u;
                v40 = *(_BYTE *)(v27 + 28);
                if ( ((v40 & 1) == 0 || (*(_BYTE *)(v27 + 192) & 2) == 0) && v40 >= 0 )
                {
                  RtlEnterCriticalSection(&SampContextListCritSect);
                  v41 = *(_QWORD *)v27;
                  if ( *(_QWORD *)v27 )
                  {
                    v42 = *(_QWORD **)(v27 + 8);
                    if ( v42 )
                    {
                      if ( *(_QWORD *)(v41 + 8) != v27 || *v42 != v27 )
                        __fastfail(3u);
                      *v42 = v41;
                      *(_QWORD *)(v41 + 8) = v42;
                    }
                  }
                  RtlLeaveCriticalSection(&SampContextListCritSect);
                }
                SampDeReferenceContext(v27, 0);
              }
              else
              {
                *(_BYTE *)(v27 + 856) = *(_BYTE *)(a1 + 856);
                *a5 = (void *)v27;
              }
            }
            else
            {
              v10 = -1073741670;
            }
            SampDeReferenceContext(a1, 0);
            v24 = WPP_GLOBAL_Control;
          }
          if ( v16 )
          {
            if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
              WPP_SF_d(v24[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
            if ( SampUseDsData && (unsigned int)SampExtIsWriteLockHeldByDs() )
            {
              SampSetTransactionWithinDomain(0);
              v13 = WPP_GLOBAL_Control;
              goto LABEL_66;
            }
            if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
            {
              v33 = WPP_GLOBAL_Control;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
                v33 = WPP_GLOBAL_Control;
              }
              SampTransactionWithinDomainGlobal = 0;
            }
            else
            {
              v33 = WPP_GLOBAL_Control;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
                v33 = WPP_GLOBAL_Control;
              }
              if ( (*(_BYTE *)(&v33[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v33[4].Length) >= 2u )
              {
                WPP_SF_(v33[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
                v33 = WPP_GLOBAL_Control;
              }
            }
            v34 = SampUseDsData && !SampDsStopped;
            if ( (*(_DWORD *)(&v33[4].MaximumLength + 1) & 0x20000) != 0 )
              WPP_SF_d(v33[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v34);
            if ( v34 )
              SampExtMaybeEndDsTransactionDs(3);
            v35 = GetTickCount() - SamLockCurrentHoldStartTime;
            if ( v35 > 0 && SamLockTotalAquisitions )
              SamCumulativeHoldTime += v35;
            RtlLeaveCriticalSection(&SampLock);
          }
          else
          {
            if ( (int)SampShouldCallNtdsaApiSet() >= 0 )
              NtdsaExtMaybeEndDsTransaction(3);
            if ( _InterlockedDecrement((volatile signed __int32 *)&SampActiveThreadCount) == 0x40000000 )
            {
              NtSetEvent(SampShutdownEventHandle, 0);
              v13 = WPP_GLOBAL_Control;
              goto LABEL_66;
            }
          }
          v13 = WPP_GLOBAL_Control;
          goto LABEL_66;
        }
        if ( (*(_BYTE *)(v15 + 192) & 2) != 0 && (*(_BYTE *)(v15 + 28) & 1) != 0 )
        {
          SampIncrementActiveThreads();
          goto LABEL_32;
        }
        v14 = SampUseDsData;
      }
      if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(v13[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v14);
        v14 = SampUseDsData;
      }
      if ( !v14 || !(unsigned int)SampExtIsWriteLockHeldByDs() )
      {
        TickCount = GetTickCount();
        _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
        RtlEnterCriticalSection(&SampLock);
        _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
        v20 = GetTickCount();
        v21 = SamLockTotalAquisitions + 1;
        SamLockCurrentHoldStartTime = v20;
        ++SamLockTotalAquisitions;
        v22 = v20 - TickCount;
        if ( v22 && v21 )
          SamCumulativeWaitTime += v22;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
        if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
          NtdsaExtSetGlobalTransactionType(0);
      }
      v16 = 1;
      goto LABEL_32;
    }
  }
LABEL_66:
  if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v13[3].Buffer, 11, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, (unsigned int)v10, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007bd0  mov     rax, rsp
0x180007bd3  mov     [rax+18h], rbx
0x180007bd7  mov     [rax+20h], rbp
0x180007bdb  push    rsi
0x180007bdc  push    rdi
0x180007bdd  push    r12
0x180007bdf  push    r13
0x180007be1  push    r14
0x180007be3  sub     rsp, 60h
0x180007be7  mov     rsi, rcx
0x180007bea  mov     [rax+10h], r15
0x180007bee  xor     r12d, r12d
0x180007bf1  mov     rcx, r8; Sid
0x180007bf4  mov     [rax-38h], r12d
0x180007bf8  movzx   r14d, r9b
0x180007bfc  mov     r15, r8
0x180007bff  mov     r13d, edx
0x180007c02  call    cs:__imp_RtlValidSid
0x180007c08  mov     edi, 0C00000DFh
0x180007c0d  test    al, al
0x180007c0f  jz      loc_1800081B3
0x180007c15  mov     ebx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x180007c1b  test    r14b, r14b
0x180007c1e  mov     eax, 2
0x180007c23  mov     ebp, edi
0x180007c25  cmovnz  ebx, eax
0x180007c28  test    ebx, ebx
0x180007c2a  jnz     loc_1800080BE
0x180007c30  mov     r10, cs:WPP_GLOBAL_Control
0x180007c37  mov     r15, [rsp+88h+arg_8]
0x180007c3f  test    dword ptr [r10+44h], 20000h
0x180007c47  jnz     loc_1800081E5
0x180007c4d  test    ebp, ebp
0x180007c4f  js      loc_18000855B
0x180007c55  test    dword ptr [r10+44h], 20000h
0x180007c5d  jnz     loc_18000820D
0x180007c63  movzx   edx, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180007c6a  test    dl, dl
0x180007c6c  jnz     loc_180008236
0x180007c72  mov     eax, r12d
0x180007c75  imul    rcx, rax, 550h
0x180007c7c  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180007c83  mov     rbx, [rcx+rax]
0x180007c87  test    byte ptr [rbx+0C0h], 2
0x180007c8e  cmovnz  rbx, rsi
0x180007c92  test    rbx, rbx
0x180007c95  jz      loc_180007D2F
0x180007c9b  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x180007ca2  mov     [rsp+88h+Buffer], rbx
0x180007caa  xor     bpl, bpl
0x180007cad  call    cs:__imp_RtlAcquireSRWLockShared
0x180007cb3  lea     rdx, [rsp+88h+Buffer]; Buffer
0x180007cbb  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x180007cc2  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180007cc8  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x180007ccf  mov     rdi, rax
0x180007cd2  call    cs:__imp_RtlReleaseSRWLockShared
0x180007cd8  mov     r10, cs:WPP_GLOBAL_Control
0x180007cdf  test    dword ptr [r10+44h], 20000h
0x180007ce7  jnz     loc_180008252
0x180007ced  test    rdi, rdi
0x180007cf0  jz      loc_18000827D
0x180007cf6  xor     edi, edi
0x180007cf8  cmp     dword ptr [rbx+18h], 0EE77FF88h
0x180007cff  jnz     loc_180008287
0x180007d05  test    dword ptr [r10+44h], 20000h
0x180007d0d  jnz     loc_1800081BD
0x180007d13  test    edi, edi
0x180007d15  js      loc_180007DAE
0x180007d1b  test    byte ptr [rbx+0C0h], 2
0x180007d22  jnz     loc_180008291
0x180007d28  movzx   edx, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180007d2f  test    dword ptr [r10+44h], 20000h
0x180007d37  jnz     loc_1800082A5
0x180007d3d  test    dl, dl
0x180007d3f  jnz     loc_1800082CA
0x180007d45  call    cs:__imp_GetTickCount
0x180007d4b  mov     ebx, eax
0x180007d4d  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180007d54  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180007d5b  call    cs:__imp_RtlEnterCriticalSection
0x180007d61  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180007d68  call    cs:__imp_GetTickCount
0x180007d6e  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x180007d74  inc     ecx
0x180007d76  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x180007d7c  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x180007d82  sub     eax, ebx
0x180007d84  jnz     loc_1800082DC
0x180007d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d91  test    dword ptr [rcx+44h], 20000h
0x180007d98  jnz     loc_1800082EF
0x180007d9e  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x180007da5  jnz     loc_180008311
0x180007dab  mov     bpl, 1
0x180007dae  lea     rax, [rsp+88h+var_38]
0x180007db3  xor     r9d, r9d
0x180007db6  xor     r8d, r8d
0x180007db9  mov     qword ptr [rsp+88h+var_68], rax
0x180007dbe  mov     edx, 20h ; ' '
0x180007dc3  mov     rcx, rsi
0x180007dc6  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x180007dcb  mov     edi, eax
0x180007dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd4  test    dword ptr [rcx+44h], 20000h
0x180007ddb  jnz     loc_18000832B
0x180007de1  test    edi, edi
0x180007de3  js      loc_180007F47
0x180007de9  movzx   edx, byte ptr [rsi+14h]
0x180007ded  mov     ecx, 1
0x180007df2  movzx   r8d, byte ptr [rsi+1Ch]
0x180007df7  movzx   r9d, dl
0x180007dfb  mov     [rsp+88h+var_48], r12d
0x180007e00  and     r8b, 1
0x180007e04  mov     [rsp+88h+var_50], 0
0x180007e09  shr     dl, 5
0x180007e0c  mov     [rsp+88h+var_58], 0
0x180007e11  and     dl, 1
0x180007e14  shr     r9b, 7
0x180007e18  mov     [rsp+88h+var_60], 0
0x180007e1d  mov     [rsp+88h+var_68], 0
0x180007e22  call    SampCreateContextEx
0x180007e27  mov     rbx, rax
0x180007e2a  test    rax, rax
0x180007e2d  jz      loc_18000841B
0x180007e33  mov     eax, [rsi+0CCh]
0x180007e39  movzx   ecx, byte ptr [rbx+14h]
0x180007e3d  mov     [rbx+0CCh], eax
0x180007e43  xor     cl, [rsi+14h]
0x180007e46  and     cl, 40h
0x180007e49  xor     [rbx+14h], cl
0x180007e4c  test    byte ptr [rsi+0C0h], 2
0x180007e53  jz      loc_180008195
0x180007e59  movzx   ecx, byte ptr [rbx+1Dh]
0x180007e5d  xor     cl, [rsi+1Dh]
0x180007e60  mov     r8d, [rbx+0C8h]
0x180007e67  and     cl, 20h
0x180007e6a  xor     [rbx+1Dh], cl
0x180007e6d  imul    rdx, r8, 550h
0x180007e74  add     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180007e7b  mov     rax, [rdx]
0x180007e7e  test    byte ptr [rax+0C0h], 2
0x180007e85  jz      loc_180008014
0x180007e8b  mov     rax, [rax+0B0h]
0x180007e92  mov     [rbx+0B0h], rax
0x180007e99  mov     rax, [rdx]
0x180007e9c  mov     ecx, [rax+0C0h]
0x180007ea2  mov     [rbx+0C0h], ecx
0x180007ea8  lock inc dword ptr [rbx+90h]
0x180007eaf  mov     [rsp+88h+var_60], 0; unsigned __int8
0x180007eb4  xor     r8d, r8d; void *
0x180007eb7  mov     edx, r13d; unsigned int
0x180007eba  mov     [rsp+88h+var_68], 0; unsigned __int8
0x180007ebf  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180007ec2  call    ?SampValidateObjectAccess2@@YAJPEAU_SAMP_OBJECT@@KPEAXEEE@Z; SampValidateObjectAccess2(_SAMP_OBJECT *,ulong,void *,uchar,uchar,uchar)
0x180007ec7  mov     edi, eax
0x180007ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ed0  test    dword ptr [rcx+44h], 20000h
0x180007ed7  jnz     loc_180008353
0x180007edd  test    edi, edi
0x180007edf  js      short loc_180007F03
0x180007ee1  mov     eax, [rbx+0C8h]
0x180007ee7  imul    rcx, rax, 550h
0x180007eee  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180007ef5  cmp     byte ptr [rcx+rax+538h], 0
0x180007efd  jnz     loc_180008374
0x180007f03  test    bpl, bpl
0x180007f06  jz      loc_180008040
0x180007f0c  xor     edx, edx
0x180007f0e  mov     rcx, rbx
0x180007f11  call    SampDeReferenceContext
0x180007f16  test    edi, edi
0x180007f18  js      loc_1800080F0
0x180007f1e  movzx   eax, byte ptr [rsi+358h]
0x180007f25  mov     [rbx+358h], al
0x180007f2b  mov     rax, [rsp+88h+arg_20]
0x180007f33  mov     [rax], rbx
0x180007f36  xor     edx, edx
0x180007f38  mov     rcx, rsi
0x180007f3b  call    SampDeReferenceContext
0x180007f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f47  test    bpl, bpl
0x180007f4a  jz      loc_18000807C
0x180007f50  test    dword ptr [rcx+44h], 20000h
0x180007f57  jnz     loc_180008425
0x180007f5d  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x180007f64  jnz     loc_180008447
0x180007f6a  mov     rax, gs:30h
0x180007f73  mov     rcx, [rax+48h]
0x180007f77  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rcx; _RTL_CRITICAL_SECTION SampLock ...
0x180007f7e  jnz     loc_18000848E
0x180007f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f8b  test    dword ptr [rcx+44h], 20000h
0x180007f92  jnz     loc_180008467
0x180007f98  mov     cs:?SampTransactionWithinDomainGlobal@@3EA, 0; uchar SampTransactionWithinDomainGlobal
0x180007f9f  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x180007fa6  jnz     loc_1800084F2
0x180007fac  xor     bl, bl
0x180007fae  test    dword ptr [rcx+44h], 20000h
0x180007fb5  jnz     loc_180008506
0x180007fbb  test    bl, bl
0x180007fbd  jnz     loc_180008524
0x180007fc3  call    cs:__imp_GetTickCount
0x180007fc9  sub     eax, cs:?SamLockCurrentHoldStartTime@@3KA; ulong SamLockCurrentHoldStartTime
0x180007fcf  test    eax, eax
0x180007fd1  jg      loc_180008533
0x180007fd7  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180007fde  call    cs:__imp_RtlLeaveCriticalSection
0x180007fe4  mov     r10, cs:WPP_GLOBAL_Control
0x180007feb  test    dword ptr [r10+44h], 20000h
0x180007ff3  jnz     loc_180008562
0x180007ff9  lea     r11, [rsp+88h+var_28]
0x180007ffe  mov     eax, edi
0x180008000  mov     rbx, [r11+40h]
0x180008004  mov     rbp, [r11+48h]
0x180008008  mov     rsp, r11
0x18000800b  pop     r14
0x18000800d  pop     r13
0x18000800f  pop     r12
0x180008011  pop     rdi
0x180008012  pop     rsi
0x180008013  retn
0x180008014  mov     rax, [rax+98h]
0x18000801b  mov     ecx, r8d
0x18000801e  mov     [rbx+98h], rax
0x180008025  mov     rax, [rdx]
0x180008028  movups  xmm0, xmmword ptr [rax+0A0h]
0x18000802f  movups  xmmword ptr [rbx+0A0h], xmm0
0x180008036  call    SampSetTransactionDomain
0x18000803b  jmp     loc_180007EA8
0x180008040  test    byte ptr [rbx+0C0h], 2
0x180008047  jnz     loc_180008388
0x18000804d  xor     edx, edx
0x18000804f  mov     rcx, rbx
0x180008052  call    SampDeReferenceContext
0x180008057  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805e  test    dword ptr [rcx+44h], 20000h
0x180008065  jz      loc_180007F16
0x18000806b  mov     edx, 20h ; ' '
0x180008070  mov     dword ptr [rsp+88h+var_68], eax
0x180008074  mov     r9d, eax
0x180008077  jmp     loc_1800083B3
0x18000807c  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x180008081  test    eax, eax
0x180008083  jns     loc_18000854B
0x180008089  mov     eax, 0FFFFFFFFh
0x18000808e  lock xadd cs:?SampActiveThreadCount@@3KA, eax; ulong SampActiveThreadCount
0x180008096  dec     eax
0x180008098  cmp     eax, 40000000h
0x18000809d  jnz     loc_180007FE4
0x1800080a3  mov     rcx, cs:?SampShutdownEventHandle@@3PEAXEA; EventHandle
0x1800080aa  xor     edx, edx; PreviousState
0x1800080ac  call    cs:__imp_NtSetEvent
0x1800080b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800080b9  jmp     loc_180007FEB
0x1800080be  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800080c5  dec     ebx
0x1800080c7  mov     eax, ebx
0x1800080c9  imul    rcx, rax, 550h
0x1800080d0  mov     rdx, [rcx+rdx+8]; Sid2
0x1800080d5  mov     rcx, r15; Sid1
0x1800080d8  call    cs:__imp_RtlEqualSid
0x1800080de  test    al, al
0x1800080e0  jz      loc_180007C28
0x1800080e6  mov     r12d, ebx
0x1800080e9  xor     ebp, ebp
0x1800080eb  jmp     loc_180007C30
0x1800080f0  or      byte ptr [rbx+14h], 10h
0x1800080f4  xor     r14d, r14d
0x1800080f7  test    byte ptr [rbx+14h], 20h
0x1800080fb  mov     dword ptr [rsp+88h+Buffer], r14d
0x180008103  jz      loc_1800083C8
0x180008109  movzx   r8d, byte ptr [rbx+0D0h]; GenerateOnClose
0x180008111  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x180008118  mov     rdx, rbx; HandleId
0x18000811b  call    cs:__imp_NtCloseObjectAuditAlarm
0x180008121  cmp     r14d, 2
0x180008125  jnz     loc_1800083E2
0x18000812b  call    cs:__imp_RpcRevertToSelf
0x180008131  and     byte ptr [rbx+15h], 0FEh
0x180008135  movzx   eax, byte ptr [rbx+1Ch]
0x180008139  test    al, 1
0x18000813b  jnz     short loc_1800081A8
0x18000813d  test    al, al
0x18000813f  js      short loc_180008186
0x180008141  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180008148  call    cs:__imp_RtlEnterCriticalSection
0x18000814e  mov     rcx, [rbx]
0x180008151  test    rcx, rcx
0x180008154  jz      short loc_180008179
0x180008156  mov     rax, [rbx+8]
0x18000815a  test    rax, rax
0x18000815d  jz      short loc_180008179
0x18000815f  cmp     [rcx+8], rbx
0x180008163  jnz     loc_180008414
0x180008169  cmp     [rax], rbx
0x18000816c  jnz     loc_180008414
0x180008172  mov     [rax], rcx
0x180008175  mov     [rcx+8], rax
0x180008179  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
  ... truncated ...
```
