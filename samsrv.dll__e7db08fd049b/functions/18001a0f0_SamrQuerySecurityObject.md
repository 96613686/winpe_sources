# SamrQuerySecurityObject

- ea: `0x18001a0f0`
- end: `0x18001a8d9`
- name: `SamrQuerySecurityObject`
- size: `2025`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006da20`

## callees

- `0x1800022a0`
- `0x180008590`
- `0x1800096c0`
- `0x18000ae10`
- `0x180012a28`
- `0x180018620`
- `0x18001a0f0`
- `0x1800270b4`
- `0x180027e24`
- `0x180027ef8`
- `0x180037284`
- `0x1800372ac`
- `0x180037394`
- `0x18003c010`
- `0x18003c920`
- `0x180076ff0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlMakeSelfRelativeSD` at `0x18001a650`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001a687`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001a650`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001a687`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a80c`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a80c`
- `ntdll!RtlEnterCriticalSection` at `0x18001a21a`
- `ntdll!RtlEnterCriticalSection` at `0x18001a21a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001a564`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001a5f8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001a564`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001a5f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a667`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a667`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a57b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a82b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a57b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a82b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a839`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a204`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a227`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a7e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a204`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a227`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a7e6`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtConvertNt5SdToNt4Sd` at `0x18001a5e4`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtConvertNt5SdToNt4Sd` at `0x18001a5e4`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18001a290`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18001a290`

## pseudocode

```c
__int64 __fastcall SamrQuerySecurityObject(struct _SAMP_OBJECT *a1, char a2, _QWORD *a3)
{
  ACCESS_MASK v5; // r15d
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  NTSTATUS SelfRelativeSD; // ebx
  void *v9; // r13
  DWORD TickCount; // ebx
  DWORD v11; // eax
  unsigned int v12; // ecx
  DWORD v13; // eax
  unsigned int v14; // eax
  PUNICODE_STRING v15; // rcx
  bool v16; // zf
  unsigned int CachedObjectSDDs; // eax
  void *v18; // rcx
  __int64 v19; // rax
  NTSTATUS v20; // eax
  PUNICODE_STRING v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  int v24; // r13d
  int *v25; // r9
  int *v26; // r9
  unsigned int v27; // ebx
  const void *v28; // r13
  SIZE_T v29; // r15
  HLOCAL v30; // rax
  PUNICODE_STRING v31; // rcx
  int v32; // eax
  HLOCAL v33; // rax
  PUNICODE_STRING v34; // rcx
  bool v35; // di
  signed int v36; // eax
  _QWORD *v37; // rax
  PUNICODE_STRING v38; // rcx
  int v40; // [rsp+30h] [rbp-48h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-40h] BYREF
  void *v42; // [rsp+40h] [rbp-38h]
  ULONG BufferLength; // [rsp+98h] [rbp+20h] BYREF
  _QWORD *v44; // [rsp+A0h] [rbp+28h]
  unsigned int SecurityDescriptorLength; // [rsp+A8h] [rbp+30h] BYREF

  v44 = a3;
  v40 = 0;
  pSecurityDescriptor = 0;
  SecurityDescriptorLength = 0;
  BufferLength = 0;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control[3].Buffer, 83, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, a1, a2);
  SampTraceEvent(1);
  v5 = ((a2 & 8) != 0 ? 0x1000000 : 0) | 0x20000;
  if ( (a2 & 7) == 0 )
    v5 = (a2 & 8) != 0 ? 0x1000000 : 0;
  v6 = LocalAlloc(0x40u, 0x10u);
  v7 = v6;
  if ( !v6 )
  {
    SelfRelativeSD = -1073741670;
    goto LABEL_115;
  }
  v9 = 0;
  v42 = 0;
  *(_DWORD *)v6 = 0;
  v6[1] = 0;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
  if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
  {
    TickCount = GetTickCount();
    _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
    RtlEnterCriticalSection(&SampLock);
    _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
    v11 = GetTickCount();
    v12 = SamLockTotalAquisitions + 1;
    SamLockCurrentHoldStartTime = v11;
    ++SamLockTotalAquisitions;
    v13 = v11 - TickCount;
    if ( v13 && v12 )
      SamCumulativeWaitTime += v13;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
      NtdsaExtSetGlobalTransactionType(0);
  }
  v14 = SampLookupContextEx((__int64)a1, v5, 0, 5, &v40);
  SelfRelativeSD = v14;
  v15 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v14, v14);
    v15 = WPP_GLOBAL_Control;
  }
  if ( SelfRelativeSD >= 0 )
  {
    v16 = (*((_BYTE *)a1 + 192) & 2) == 0;
    SecurityDescriptorLength = 0;
    if ( v16 )
      goto LABEL_38;
    if ( *((_DWORD *)a1 + 4) <= 1u )
    {
      CachedObjectSDDs = SampExtGetCachedObjectSDDs(a1, &SecurityDescriptorLength, &pSecurityDescriptor);
      SelfRelativeSD = CachedObjectSDDs;
      if ( CachedObjectSDDs != -1073741823 )
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            36,
            WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
            CachedObjectSDDs,
            CachedObjectSDDs);
        goto LABEL_62;
      }
    }
    if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
    {
LABEL_38:
      v20 = SampValidateRegAttributes(a1, 1u);
    }
    else
    {
      if ( *((_QWORD *)a1 + 14) )
      {
        if ( _bittest64(*((const signed __int64 **)a1 + 8), 0) )
        {
          v18 = (void *)*((_QWORD *)a1 + 17);
          if ( v18 )
            LocalFree(v18);
          v19 = *((_QWORD *)a1 + 14);
          *((_BYTE *)a1 + 20) &= 0xF0u;
          *((_QWORD *)a1 + 17) = v19;
          *((_QWORD *)a1 + 14) = 0;
          *((_QWORD *)a1 + 15) = 0;
          *((_DWORD *)a1 + 32) = 0;
          SelfRelativeSD = SampValidateDsAttributes(a1, 0);
          if ( SelfRelativeSD >= 0 )
          {
            SelfRelativeSD = SampValidateDsAttributes(a1, 1u);
            if ( SelfRelativeSD >= 0 )
            {
              SampMarkPerAttributeInvalidFromWhichFields(a1, 0);
              *((_BYTE *)a1 + 29) &= ~1u;
            }
          }
LABEL_40:
          v21 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              110,
              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
              (unsigned int)SelfRelativeSD,
              SelfRelativeSD);
            v21 = WPP_GLOBAL_Control;
          }
          if ( SelfRelativeSD >= 0 )
          {
            v22 = *((_QWORD *)a1 + 14);
            v23 = 88LL * *((int *)a1 + 4);
            if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
            {
              v24 = *(_DWORD *)((char *)&SampObjectInformation + v23 + 72);
              v25 = dword_1800EEC4C;
            }
            else
            {
              v24 = *(_DWORD *)((char *)&SampObjectInformation + v23 + 56);
              v25 = dword_1800EEC34;
            }
            v26 = &v25[(unsigned __int64)v23 / 4];
            v27 = *(_DWORD *)((unsigned int)*v26 + v22 + 8);
            v28 = (const void *)(v22 + (unsigned int)(*(_DWORD *)((unsigned int)*v26 + v22) + v24));
            v29 = *(unsigned int *)((unsigned int)*v26 + v22 + 4);
            v30 = LocalAlloc(0x40u, v29);
            pSecurityDescriptor = v30;
            if ( !v30 )
            {
              v31 = WPP_GLOBAL_Control;
              SelfRelativeSD = -1073741801;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control[3].Buffer,
                  44,
                  WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                  3221225495LL,
                  -1073741801);
                v31 = WPP_GLOBAL_Control;
              }
              v9 = v42;
              goto LABEL_60;
            }
            memcpy_0(v30, v28, v29);
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 45, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
            if ( (v27 & 0xFFFF0000) > 0x10000 || v27 > 0x10009 )
            {
              SelfRelativeSD = -1073741736;
              LocalFree(pSecurityDescriptor);
              pSecurityDescriptor = 0;
            }
            else
            {
              SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
              SelfRelativeSD = 0;
            }
            v9 = v42;
          }
          else
          {
            if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) == 0 )
            {
LABEL_62:
              if ( SelfRelativeSD >= 0 )
              {
                if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
                  goto LABEL_69;
                v32 = SampShouldCallNtdsaApiSet();
                SelfRelativeSD = v32;
                if ( v32 == -1073741637 )
                {
                  SelfRelativeSD = 0;
                }
                else if ( v32 >= 0 )
                {
                  SelfRelativeSD = NtdsaExtConvertNt5SdToNt4Sd(a1, &pSecurityDescriptor);
                }
                if ( SelfRelativeSD >= 0 )
                {
LABEL_69:
                  SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
                  if ( (a2 & 8) == 0 )
                    *((_WORD *)pSecurityDescriptor + 1) &= ~0x10u;
                  if ( (a2 & 4) == 0 )
                    *((_WORD *)pSecurityDescriptor + 1) &= ~4u;
                  if ( (a2 & 1) == 0 )
                    *((_DWORD *)pSecurityDescriptor + 1) = 0;
                  if ( (a2 & 2) == 0 )
                    *((_DWORD *)pSecurityDescriptor + 2) = 0;
                  BufferLength = 0;
                  SelfRelativeSD = RtlMakeSelfRelativeSD(pSecurityDescriptor, 0, &BufferLength);
                  if ( SelfRelativeSD == -1073741789 )
                  {
                    v33 = LocalAlloc(0x40u, BufferLength);
                    v9 = v33;
                    if ( v33 )
                      SelfRelativeSD = RtlMakeSelfRelativeSD(pSecurityDescriptor, v33, &BufferLength);
                    else
                      SelfRelativeSD = -1073741670;
                  }
                }
                if ( pSecurityDescriptor )
                  LocalFree(pSecurityDescriptor);
              }
              SampDeReferenceContext(a1, 0);
              v15 = WPP_GLOBAL_Control;
              goto LABEL_84;
            }
            WPP_SF_Dd(
              v21[3].Buffer,
              42,
              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
              (unsigned int)SelfRelativeSD,
              SelfRelativeSD);
          }
          v31 = WPP_GLOBAL_Control;
LABEL_60:
          if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              v31[3].Buffer,
              37,
              WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
              (unsigned int)SelfRelativeSD,
              SelfRelativeSD);
          goto LABEL_62;
        }
      }
      else
      {
        SelfRelativeSD = SampValidateDsAttributes(a1, 0);
        if ( SelfRelativeSD < 0 )
          goto LABEL_40;
      }
      v20 = SampValidateDsAttributes(a1, 1u);
    }
    SelfRelativeSD = v20;
    goto LABEL_40;
  }
LABEL_84:
  if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(v15[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
  if ( SampUseDsData && (unsigned int)SampExtIsWriteLockHeldByDs() )
  {
    SampSetTransactionWithinDomain(0);
  }
  else
  {
    if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
    {
      v34 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
        v34 = WPP_GLOBAL_Control;
      }
      SampTransactionWithinDomainGlobal = 0;
    }
    else
    {
      v34 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
        v34 = WPP_GLOBAL_Control;
      }
      if ( (*(_BYTE *)(&v34[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v34[4].Length) >= 2u )
      {
        WPP_SF_(v34[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
        v34 = WPP_GLOBAL_Control;
      }
    }
    v35 = SampUseDsData && !SampDsStopped;
    if ( (*(_DWORD *)(&v34[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(v34[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v35);
    if ( v35 )
      SampExtMaybeEndDsTransactionDs(3);
    v36 = GetTickCount() - SamLockCurrentHoldStartTime;
    if ( v36 > 0 && SamLockTotalAquisitions )
      SamCumulativeHoldTime += v36;
    RtlLeaveCriticalSection(&SampLock);
  }
  if ( SelfRelativeSD < 0 )
  {
    LocalFree(v7);
    if ( v9 )
      LocalFree(v9);
    *v44 = 0;
  }
  else
  {
    *(_DWORD *)v7 = BufferLength;
    v37 = v44;
    v7[1] = v9;
    *v37 = v7;
  }
LABEL_115:
  SampTraceEvent(2);
  v38 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[3].Buffer,
      84,
      WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
      (unsigned int)SelfRelativeSD);
    v38 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      v38[3].Buffer,
      85,
      WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
      (unsigned int)SelfRelativeSD,
      SelfRelativeSD);
  return (unsigned int)SelfRelativeSD;
}

```

## disassembly

```asm
0x18001a0f0  mov     rax, rsp
0x18001a0f3  mov     [rax+18h], r8
0x18001a0f7  push    rbp
0x18001a0f8  push    rbx
0x18001a0f9  mov     rbp, rsp
0x18001a0fc  sub     rsp, 78h
0x18001a100  mov     [rax+8], rsi
0x18001a104  xor     ebx, ebx
0x18001a106  mov     [rax-18h], rdi
0x18001a10a  mov     rdi, rcx
0x18001a10d  mov     [rax-20h], r12
0x18001a111  mov     [rax-30h], r14
0x18001a115  mov     r14d, edx
0x18001a118  mov     [rax-38h], r15
0x18001a11c  mov     [rbp+var_48], ebx
0x18001a11f  mov     [rbp+pSecurityDescriptor], rbx
0x18001a123  mov     [rbp+arg_18], ebx
0x18001a126  mov     [rbp+BufferLength], ebx
0x18001a129  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a130  test    byte ptr [rcx+44h], 8
0x18001a134  jz      short loc_18001A158
0x18001a136  cmp     byte ptr [rcx+41h], 4
0x18001a13a  jb      short loc_18001A158
0x18001a13c  mov     rcx, [rcx+38h]
0x18001a140  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18001a147  mov     edx, 53h ; 'S'
0x18001a14c  mov     [rax-68h], r14d
0x18001a150  mov     r9, rdi
0x18001a153  call    WPP_SF_qD
0x18001a158  xor     r8d, r8d
0x18001a15b  mov     edx, 3
0x18001a160  mov     ecx, 1
0x18001a165  call    SampTraceEvent
0x18001a16a  mov     r12d, r14d
0x18001a16d  mov     edx, 10h; uBytes
0x18001a172  and     r12d, 8
0x18001a176  mov     eax, r12d
0x18001a179  neg     eax
0x18001a17b  sbb     ecx, ecx
0x18001a17d  and     ecx, 1000000h
0x18001a183  mov     r15d, ecx
0x18001a186  bts     r15d, 11h
0x18001a18b  test    r14b, 7
0x18001a18f  cmovz   r15d, ecx
0x18001a193  mov     ecx, 40h ; '@'; uFlags
0x18001a198  call    cs:__imp_LocalAlloc
0x18001a19e  mov     rsi, rax
0x18001a1a1  test    rax, rax
0x18001a1a4  jnz     short loc_18001A1B0
0x18001a1a6  mov     ebx, 0C000009Ah
0x18001a1ab  jmp     loc_18001A84B
0x18001a1b0  mov     [rsp+78h+var_18], r13
0x18001a1b5  mov     r13, rbx
0x18001a1b8  mov     [rbp+var_38], rbx
0x18001a1bc  mov     [rax], ebx
0x18001a1be  mov     [rax+8], rbx
0x18001a1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1c9  test    dword ptr [rcx+44h], 20000h
0x18001a1d0  jz      short loc_18001A1EF
0x18001a1d2  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18001a1da  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001a1e1  mov     rcx, [rcx+38h]
0x18001a1e5  mov     edx, 49h ; 'I'
0x18001a1ea  call    WPP_SF_d
0x18001a1ef  cmp     cs:?SampUseDsData@@3EA, bl; uchar SampUseDsData
0x18001a1f5  jz      short loc_18001A204
0x18001a1f7  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x18001a1fc  test    eax, eax
0x18001a1fe  jnz     loc_18001A296
0x18001a204  call    cs:__imp_GetTickCount
0x18001a20a  mov     ebx, eax
0x18001a20c  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18001a213  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001a21a  call    cs:__imp_RtlEnterCriticalSection
0x18001a220  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18001a227  call    cs:__imp_GetTickCount
0x18001a22d  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x18001a233  inc     ecx
0x18001a235  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x18001a23b  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x18001a241  sub     eax, ebx
0x18001a243  jz      short loc_18001A24F
0x18001a245  test    ecx, ecx
0x18001a247  jz      short loc_18001A24F
0x18001a249  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x18001a24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a256  test    dword ptr [rcx+44h], 20000h
0x18001a25d  jz      short loc_18001A27C
0x18001a25f  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18001a267  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001a26e  mov     rcx, [rcx+38h]
0x18001a272  mov     edx, 49h ; 'I'
0x18001a277  call    WPP_SF_d
0x18001a27c  cmp     cs:?SampUseDsData@@3EA, r13b; uchar SampUseDsData
0x18001a283  jz      short loc_18001A296
0x18001a285  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001a28a  test    eax, eax
0x18001a28c  js      short loc_18001A296
0x18001a28e  xor     ecx, ecx
0x18001a290  call    cs:__imp_NtdsaExtSetGlobalTransactionType
0x18001a296  lea     rax, [rbp+var_48]
0x18001a29a  mov     r9d, 5
0x18001a2a0  xor     r8d, r8d
0x18001a2a3  mov     [rsp+78h+var_58], rax
0x18001a2a8  mov     edx, r15d
0x18001a2ab  mov     rcx, rdi
0x18001a2ae  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x18001a2b3  mov     ebx, eax
0x18001a2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2bc  test    dword ptr [rcx+44h], 20000h
0x18001a2c3  jz      short loc_18001A2E8
0x18001a2c5  mov     rcx, [rcx+38h]
0x18001a2c9  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001a2d0  mov     edx, 10h
0x18001a2d5  mov     dword ptr [rsp+78h+var_58], eax
0x18001a2d9  mov     r9d, eax
0x18001a2dc  call    WPP_SF_Dd
0x18001a2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2e8  xor     r15d, r15d
0x18001a2eb  test    ebx, ebx
0x18001a2ed  js      loc_18001A6AF
0x18001a2f3  test    byte ptr [rdi+0C0h], 2
0x18001a2fa  mov     [rbp+arg_18], r15d
0x18001a2fe  jz      loc_18001A3ED
0x18001a304  cmp     dword ptr [rdi+10h], 1
0x18001a308  ja      short loc_18001A348
0x18001a30a  lea     r8, [rbp+pSecurityDescriptor]; void **
0x18001a30e  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a311  lea     rdx, [rbp+arg_18]; unsigned int *
0x18001a315  call    ?SampExtGetCachedObjectSDDs@@YAJPEAU_SAMP_OBJECT@@PEAKPEAPEAX@Z; SampExtGetCachedObjectSDDs(_SAMP_OBJECT *,ulong *,void * *)
0x18001a31a  mov     ebx, eax
0x18001a31c  cmp     eax, 0C0000001h
0x18001a321  jz      short loc_18001A348
0x18001a323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a32a  test    dword ptr [rcx+44h], 20000h
0x18001a331  jz      loc_18001A5B5
0x18001a337  mov     edx, 24h ; '$'
0x18001a33c  mov     dword ptr [rsp+78h+var_58], eax
0x18001a340  mov     r9d, eax
0x18001a343  jmp     loc_18001A5A5
0x18001a348  test    byte ptr [rdi+0C0h], 2
0x18001a34f  jz      loc_18001A3ED
0x18001a355  cmp     [rdi+70h], r13
0x18001a359  jz      short loc_18001A3CE
0x18001a35b  mov     rax, [rdi+40h]
0x18001a35f  bt      qword ptr [rax], 0
0x18001a364  setb    al
0x18001a367  test    al, al
0x18001a369  jz      short loc_18001A3DE
0x18001a36b  mov     rcx, [rdi+88h]; hMem
0x18001a372  test    rcx, rcx
0x18001a375  jz      short loc_18001A37D
0x18001a377  call    cs:__imp_LocalFree
0x18001a37d  mov     rax, [rdi+70h]
0x18001a381  xor     edx, edx; unsigned int
0x18001a383  and     byte ptr [rdi+14h], 0F0h
0x18001a387  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a38a  mov     [rdi+88h], rax
0x18001a391  mov     [rdi+70h], r13
0x18001a395  mov     [rdi+78h], r13
0x18001a399  mov     [rdi+80h], r13d
0x18001a3a0  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x18001a3a5  mov     ebx, eax
0x18001a3a7  test    eax, eax
0x18001a3a9  js      short loc_18001A3FC
0x18001a3ab  mov     edx, 1; unsigned int
0x18001a3b0  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a3b3  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x18001a3b8  mov     ebx, eax
0x18001a3ba  test    eax, eax
0x18001a3bc  js      short loc_18001A3FC
0x18001a3be  xor     edx, edx
0x18001a3c0  mov     rcx, rdi
0x18001a3c3  call    SampMarkPerAttributeInvalidFromWhichFields
0x18001a3c8  and     byte ptr [rdi+1Dh], 0FEh
0x18001a3cc  jmp     short loc_18001A3FC
0x18001a3ce  xor     edx, edx; unsigned int
0x18001a3d0  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a3d3  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x18001a3d8  mov     ebx, eax
0x18001a3da  test    eax, eax
0x18001a3dc  js      short loc_18001A3FC
0x18001a3de  mov     edx, 1; unsigned int
0x18001a3e3  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a3e6  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x18001a3eb  jmp     short loc_18001A3FA
0x18001a3ed  mov     edx, 1; unsigned int
0x18001a3f2  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18001a3f5  call    SampValidateRegAttributes
0x18001a3fa  mov     ebx, eax
0x18001a3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a403  test    dword ptr [rcx+44h], 20000h
0x18001a40a  jz      short loc_18001A42F
0x18001a40c  mov     rcx, [rcx+38h]
0x18001a410  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x18001a417  mov     edx, 6Eh ; 'n'
0x18001a41c  mov     dword ptr [rsp+78h+var_58], ebx
0x18001a420  mov     r9d, ebx
0x18001a423  call    WPP_SF_Dd
0x18001a428  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a42f  test    ebx, ebx
0x18001a431  jns     short loc_18001A461
0x18001a433  test    dword ptr [rcx+44h], 20000h
0x18001a43a  jz      loc_18001A5B5
0x18001a440  mov     rcx, [rcx+38h]
0x18001a444  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x18001a44b  mov     edx, 2Ah ; '*'
0x18001a450  mov     dword ptr [rsp+78h+var_58], ebx
0x18001a454  mov     r9d, ebx
0x18001a457  call    WPP_SF_Dd
0x18001a45c  jmp     loc_18001A589
0x18001a461  movsxd  rax, dword ptr [rdi+10h]
0x18001a465  lea     r10, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x18001a46c  mov     r8, [rdi+70h]
0x18001a470  imul    rdx, rax, 58h ; 'X'
0x18001a474  test    byte ptr [rdi+0C0h], 2
0x18001a47b  jz      short loc_18001A488
0x18001a47d  mov     r13d, [rdx+r10+48h]
0x18001a482  lea     r9, [r10+4Ch]
0x18001a486  jmp     short loc_18001A491
0x18001a488  mov     r13d, [rdx+r10+38h]
0x18001a48d  lea     r9, [r10+34h]
0x18001a491  add     r9, rdx
0x18001a494  mov     eax, [r9]
0x18001a497  mov     ecx, [r9]
0x18001a49a  mov     ebx, [rax+r8+8]
0x18001a49f  add     r13d, [rcx+r8]
0x18001a4a3  mov     ecx, 40h ; '@'; uFlags
0x18001a4a8  mov     eax, [r9]
0x18001a4ab  add     r13, r8
0x18001a4ae  mov     r15d, [rax+r8+4]
0x18001a4b3  mov     edx, r15d; uBytes
0x18001a4b6  call    cs:__imp_LocalAlloc
0x18001a4bc  mov     [rbp+pSecurityDescriptor], rax
0x18001a4c0  test    rax, rax
0x18001a4c3  jnz     short loc_18001A50C
0x18001a4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4cc  mov     ebx, 0C0000017h
0x18001a4d1  test    dword ptr [rcx+44h], 20000h
0x18001a4d8  jz      short loc_18001A500
0x18001a4da  mov     rcx, [rcx+38h]
0x18001a4de  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x18001a4e5  mov     edx, 2Ch ; ','
0x18001a4ea  mov     dword ptr [rsp+78h+var_58], ebx
0x18001a4ee  mov     r9d, 0C0000017h
0x18001a4f4  call    WPP_SF_Dd
0x18001a4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a500  mov     r13, [rbp+var_38]
0x18001a504  xor     r15d, r15d
0x18001a507  jmp     loc_18001A590
0x18001a50c  mov     r8, r15; Size
0x18001a50f  mov     rdx, r13; Src
0x18001a512  mov     rcx, rax; void *
0x18001a515  call    memcpy_0
0x18001a51a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a521  xor     r15d, r15d
0x18001a524  test    dword ptr [rcx+44h], 20000h
0x18001a52b  jz      short loc_18001A54A
0x18001a52d  mov     rcx, [rcx+38h]
0x18001a531  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x18001a538  mov     edx, 2Dh ; '-'
0x18001a53d  mov     dword ptr [rsp+78h+var_58], r15d
0x18001a542  xor     r9d, r9d
0x18001a545  call    WPP_SF_Dd
0x18001a54a  mov     eax, ebx
0x18001a54c  and     eax, 0FFFF0000h
0x18001a551  cmp     eax, 10000h
0x18001a556  ja      short loc_18001A572
0x18001a558  cmp     ebx, 10009h
0x18001a55e  ja      short loc_18001A572
0x18001a560  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001a564  call    cs:__imp_GetSecurityDescriptorLength
0x18001a56a  mov     [rbp+arg_18], eax
0x18001a56d  mov     ebx, r15d
0x18001a570  jmp     short loc_18001A585
0x18001a572  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x18001a576  mov     ebx, 0C0000058h
0x18001a57b  call    cs:__imp_LocalFree
0x18001a581  mov     [rbp+pSecurityDescriptor], r15
0x18001a585  mov     r13, [rbp+var_38]
0x18001a589  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a590  test    dword ptr [rcx+44h], 20000h
0x18001a597  jz      short loc_18001A5B5
0x18001a599  mov     edx, 25h ; '%'
0x18001a59e  mov     dword ptr [rsp+78h+var_58], ebx
0x18001a5a2  mov     r9d, ebx
0x18001a5a5  mov     rcx, [rcx+38h]
0x18001a5a9  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18001a5b0  call    WPP_SF_Dd
0x18001a5b5  test    ebx, ebx
0x18001a5b7  js      loc_18001A69E
0x18001a5bd  test    byte ptr [rdi+0C0h], 2
0x18001a5c4  jz      short loc_18001A5F4
0x18001a5c6  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001a5cb  mov     ebx, eax
0x18001a5cd  cmp     eax, 0C00000BBh
0x18001a5d2  jnz     short loc_18001A5D9
0x18001a5d4  mov     ebx, r15d
0x18001a5d7  jmp     short loc_18001A5EC
0x18001a5d9  test    eax, eax
  ... truncated ...
```
