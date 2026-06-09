# CNetworkAddresses::_PopulateDeviceAddresses(void)

- ea: `0x1800e7ef8`
- end: `0x1800e83d1`
- name: `?_PopulateDeviceAddresses@CNetworkAddresses@@CAJXZ`
- size: `1241`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e7b54`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x1800161e0`
- `0x1800171f0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180037e48`
- `0x180039b00`
- `0x180048a6c`
- `0x1800814f8`
- `0x1800a3b60`
- `0x1800e6958`
- `0x1800e7c54`
- `0x1800e7ef8`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e809d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e809d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e800b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e80b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e818a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e800b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e80b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e818a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800e803a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800e803a`

## string_xrefs

- `0x1800e7fa0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`
- `0x1800e7fd6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`
- `0x1800e8331`: `hr = SafeCopyMemory(pCur, dwSize - (pCur - Buffer), pCurAddress->Address.lpSockaddr, pCurAddress->Address.iSockaddrLength)`
- `0x1800e81c7`: `hr = SafeCopyMemory(Buffer, dwSize, &dwCount, sizeof(dwCount))`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 CNetworkAddresses::_PopulateDeviceAddresses(void)
{
  int v0; // edi
  _QWORD *v1; // r15
  unsigned int i; // esi
  int v3; // r12d
  signed int v4; // ebx
  void *v5; // rcx
  HLOCAL v6; // rax
  unsigned int v7; // r14d
  __int64 j; // r8
  __int64 k; // rdx
  __int64 v10; // rcx
  unsigned int v11; // r12d
  __int64 m; // r8
  __int64 n; // rdx
  __int64 ii; // rcx
  unsigned __int8 *v15; // rdi
  int v16; // eax
  const char *v17; // rcx
  unsigned int v18; // r8d
  unsigned __int8 *v19; // r10
  __int64 v20; // rsi
  __int64 jj; // rbx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  unsigned __int8 *v24; // rdx
  unsigned __int8 *v25; // r10
  unsigned int v26; // ebx
  char *v28; // [rsp+20h] [rbp-A9h]
  int LastKnownGood; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int8 *v30; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-89h]
  DWORD nSize; // [rsp+44h] [rbp-85h] BYREF
  __int64 v33; // [rsp+48h] [rbp-81h] BYREF
  __int64 v34; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v35; // [rsp+58h] [rbp-71h] BYREF
  int v36; // [rsp+60h] [rbp-69h]
  __int64 v37; // [rsp+68h] [rbp-61h]
  __int64 v38; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v39[3]; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v40[4]; // [rsp+90h] [rbp-39h] BYREF
  WCHAR Buffer[8]; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-9h]
  __int16 v43; // [rsp+D0h] [rbp+7h]

  v35 = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  LastKnownGood = 0;
  v0 = 0;
  LODWORD(v30) = 0;
  memset(v39, 0, sizeof(v39));
  *(_OWORD *)Buffer = 0;
  v42 = 0;
  v43 = 0;
  nSize = 16;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  v40[0] = "CNetworkAddresses::_PopulateDeviceAddresses";
  v40[1] = &LastKnownGood;
  v40[2] = 0;
  v40[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
    "CNetworkAddresses::_PopulateDeviceAddresses",
    (const char *)0x32E,
    0,
    (const unsigned __int16 *)v28);
  if ( !CNetworkAddresses::m_pGetAdaptersAddresses )
  {
    LastKnownGood = -2147467263;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
      "CNetworkAddresses::_PopulateDeviceAddresses",
      0x330u,
      -2147467263,
      "m_pGetAdaptersAddresses != nullptr");
    goto LABEL_69;
  }
  ATL::CSimpleStringT<char,0>::Truncate(&CNetworkAddresses::m_pszAddresses, 0);
  ATL::CSimpleStringT<char,0>::Truncate(&CNetworkAddresses::m_pszFriendlyName, 0);
  v1 = LocalAlloc(0x40u, 0x10u);
  AutoArray<_IP_ADAPTER_ADDRESSES_LH * *,LocalAllocArrayFunctor<_IP_ADAPTER_ADDRESSES_LH *>,DummyContext>::Clear(&v35);
  v35 = v1;
  v36 = 2;
  if ( !v1 )
    goto LABEL_68;
  if ( GetComputerNameW(Buffer, &nSize) )
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(
      &CNetworkAddresses::m_pszFriendlyName,
      Buffer);
  for ( i = 0; i < 2; ++i )
  {
    v3 = 0;
    while ( 1 )
    {
      v4 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, char *))CNetworkAddresses::m_pGetAdaptersAddresses)(
             *((unsigned int *)&CNetworkAddresses::m_aProtocols + i),
             46,
             0,
             v1[i],
             (char *)&v39[-1] + 4 * i);
      if ( v4 != 111 )
        break;
      v5 = (void *)v1[i];
      if ( v5 )
      {
        LocalFree(v5);
        v1[i] = 0;
      }
      v6 = LocalAlloc(0x40u, *((unsigned int *)&v39[-1] + i));
      v1[i] = v6;
      if ( !v6 )
        goto LABEL_68;
      if ( (unsigned int)++v3 >= 5 )
        goto LABEL_66;
    }
    v7 = 0;
    if ( v4 )
    {
      if ( v4 > 0 )
LABEL_66:
        v4 = (unsigned __int16)v4 | 0x80070000;
      LastKnownGood = v4;
      goto LABEL_69;
    }
  }
  for ( j = 0; j != 2; ++j )
  {
    for ( k = v1[j]; k; k = *(_QWORD *)(k + 8) )
    {
      v10 = *(_QWORD *)(k + 24);
      if ( v10 )
      {
        do
        {
          if ( (*(_DWORD *)(v10 + 4) & 3) == 1 )
            ++v0;
          v10 = *(_QWORD *)(v10 + 8);
        }
        while ( v10 );
        LODWORD(v30) = v0;
      }
    }
  }
  if ( !v0 )
    goto LABEL_54;
  v11 = 12 * v0 + 8;
  for ( m = 0; m != 2; ++m )
  {
    for ( n = v1[m]; n; n = *(_QWORD *)(n + 8) )
    {
      for ( ii = *(_QWORD *)(n + 24); ii; ii = *(_QWORD *)(ii + 8) )
      {
        if ( (*(_DWORD *)(ii + 4) & 3) == 1 )
          v11 += *(_DWORD *)(ii + 24);
      }
    }
  }
  v15 = (unsigned __int8 *)LocalAlloc(0x40u, v11);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v39);
  v39[0] = v15;
  if ( !v15 )
  {
LABEL_68:
    LastKnownGood = -2147024882;
    goto LABEL_69;
  }
  v16 = SafeCopyMemory(v15, v11, &v30, 4);
  LastKnownGood = v16;
  if ( v16 < 0 )
  {
    v17 = "hr = SafeCopyMemory(Buffer, dwSize, &dwCount, sizeof(dwCount))";
    v18 = 979;
    goto LABEL_41;
  }
  v31 = 0;
  v19 = &v15[8 * (unsigned int)v30 + 8 + 4 * (unsigned int)v30];
  v30 = v19;
  while ( 1 )
  {
    v20 = v1[v7];
LABEL_51:
    if ( v20 )
      break;
    if ( ++v7 >= 2 )
    {
      LastKnownGood = PassportEncode::Base64Encode(v15, v11);
LABEL_54:
      if ( LastKnownGood >= 0 )
      {
        if ( CNetworkAddresses::m_fLKGIsValid )
        {
          LastKnownGood = CNetworkAddresses::_GetLastKnownGood(&v33, &v34);
          if ( LastKnownGood < 0 )
          {
            CNetworkAddresses::m_fOutOfSync = 3;
          }
          else
          {
            CNetworkAddresses::m_fOutOfSync = 0;
            if ( (unsigned int)ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Compare(
                                 &v33,
                                 CNetworkAddresses::m_pszAddresses) )
              CNetworkAddresses::m_fOutOfSync |= 1u;
            if ( (unsigned int)ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Compare(
                                 &v34,
                                 CNetworkAddresses::m_pszFriendlyName) )
              CNetworkAddresses::m_fOutOfSync |= 2u;
          }
          LastKnownGood = 0;
        }
        else
        {
          CNetworkAddresses::m_fOutOfSync = 3;
        }
      }
      goto LABEL_69;
    }
  }
  for ( jj = *(_QWORD *)(v20 + 24); ; jj = *(_QWORD *)(jj + 8) )
  {
    if ( !jj )
    {
      v20 = *(_QWORD *)(v20 + 8);
      goto LABEL_51;
    }
    if ( (*(_DWORD *)(jj + 4) & 3) == 1 )
      break;
LABEL_48:
    ;
  }
  v16 = SafeCopyMemory(v19, &v15[v11 - (_QWORD)v19], *(_QWORD *)(jj + 16), *(int *)(jj + 24));
  LastKnownGood = v16;
  if ( v16 >= 0 )
  {
    v22 = v31;
    v23 = 3LL * v31;
    v24 = v15 + 8;
    *(_DWORD *)&v24[4 * v23] = *(_DWORD *)(jj + 24);
    v25 = v30;
    *(_DWORD *)&v24[4 * v23 + 8] = (_DWORD)v30 - ((_DWORD)v15 + 8);
    *(_DWORD *)&v24[4 * v23 + 4] = *((_DWORD *)&CNetworkAddresses::m_aProtocols + v7);
    v31 = v22 + 1;
    v19 = &v25[*(int *)(jj + 24)];
    v30 = v19;
    goto LABEL_48;
  }
  v17 = "hr = SafeCopyMemory(pCur, dwSize - (pCur - Buffer), pCurAddress->Address.lpSockaddr, pCurAddress->Address.iSockaddrLength)";
  v18 = 1004;
LABEL_41:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
    "CNetworkAddresses::_PopulateDeviceAddresses",
    v18,
    v16,
    v17);
LABEL_69:
  v26 = LastKnownGood;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v39);
  AutoArray<_IP_ADAPTER_ADDRESSES_LH * *,LocalAllocArrayFunctor<_IP_ADAPTER_ADDRESSES_LH *>,DummyContext>::Clear(&v35);
  return v26;
}

```

## disassembly

```asm
0x1800e7ef8  push    rbp
0x1800e7efa  push    rbx
0x1800e7efb  push    rsi
0x1800e7efc  push    rdi
0x1800e7efd  push    r12
0x1800e7eff  push    r13
0x1800e7f01  push    r14
0x1800e7f03  push    r15
0x1800e7f05  lea     rbp, [rsp-1Fh]
0x1800e7f0a  sub     rsp, 0E8h
0x1800e7f11  mov     rax, cs:__security_cookie
0x1800e7f18  xor     rax, rsp
0x1800e7f1b  mov     [rbp+57h+var_48], rax
0x1800e7f1f  xor     r14d, r14d
0x1800e7f22  mov     [rbp+57h+var_C8], r14
0x1800e7f26  mov     [rbp+57h+var_B8], r14
0x1800e7f2a  mov     [rbp+57h+var_C0], r14d
0x1800e7f2e  mov     [rbp+57h+var_B0], r14
0x1800e7f32  mov     [rsp+120h+var_F0], r14d
0x1800e7f37  mov     edi, r14d
0x1800e7f3a  mov     dword ptr [rsp+120h+var_E8], r14d
0x1800e7f3f  mov     [rbp+57h+var_A8], r14
0x1800e7f43  mov     [rbp+57h+var_98], r14
0x1800e7f47  mov     [rbp+57h+var_A0], r14
0x1800e7f4b  xorps   xmm0, xmm0
0x1800e7f4e  xor     eax, eax
0x1800e7f50  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800e7f54  movups  [rbp+57h+var_60], xmm0
0x1800e7f58  mov     [rbp+57h+var_50], ax
0x1800e7f5c  lea     ebx, [rax+10h]
0x1800e7f5f  mov     [rsp+120h+nSize], ebx
0x1800e7f63  lea     rcx, [rbp+57h+var_D0]
0x1800e7f67  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e7f6c  nop
0x1800e7f6d  lea     rcx, [rsp+120h+var_D8]
0x1800e7f72  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e7f77  nop
0x1800e7f78  lea     rsi, aCnetworkaddres_5; "CNetworkAddresses::_PopulateDeviceAddre"...
0x1800e7f7f  mov     [rbp+57h+var_90], rsi
0x1800e7f83  lea     rax, [rsp+120h+var_F0]
0x1800e7f88  mov     [rbp+57h+var_88], rax
0x1800e7f8c  mov     [rbp+57h+var_80], r14
0x1800e7f90  mov     [rbp+57h+var_78], r14
0x1800e7f94  xor     r9d, r9d; unsigned int
0x1800e7f97  mov     r8d, 32Eh; char *
0x1800e7f9d  mov     rdx, rsi; char *
0x1800e7fa0  lea     rcx, aOnecoreuapDsEx_88; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e7fa7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800e7fac  nop
0x1800e7fad  cmp     cs:?m_pGetAdaptersAddresses@CNetworkAddresses@@0P6AKKKPEAXPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAK@ZEA, r14; ulong (*CNetworkAddresses::m_pGetAdaptersAddresses)(ulong,ulong,void *,_IP_ADAPTER_ADDRESSES_LH *,ulong *)
0x1800e7fb4  jnz     short loc_1800E7FE7
0x1800e7fb6  mov     r9d, 80004001h; int
0x1800e7fbc  mov     [rsp+120h+var_F0], r9d
0x1800e7fc1  lea     rax, aMPgetadaptersa; "m_pGetAdaptersAddresses != nullptr"
0x1800e7fc8  mov     [rsp+120h+var_100], rax; char *
0x1800e7fcd  mov     r8d, 330h; unsigned int
0x1800e7fd3  mov     rdx, rsi; char *
0x1800e7fd6  lea     rcx, aOnecoreuapDsEx_88; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e7fdd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e7fe2  jmp     loc_1800E8379
0x1800e7fe7  xor     edx, edx
0x1800e7fe9  lea     rcx, ?m_pszAddresses@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszAddresses
0x1800e7ff0  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800e7ff5  xor     edx, edx
0x1800e7ff7  lea     rcx, ?m_pszFriendlyName@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszFriendlyName
0x1800e7ffe  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800e8003  mov     rdx, rbx; uBytes
0x1800e8006  mov     ecx, 40h ; '@'; uFlags
0x1800e800b  call    cs:__imp_LocalAlloc
0x1800e8011  mov     r15, rax
0x1800e8014  lea     rcx, [rbp+57h+var_C8]
0x1800e8018  call    ?Clear@?$AutoArray@PEAPEAU_IP_ADAPTER_ADDRESSES_LH@@V?$LocalAllocArrayFunctor@PEAU_IP_ADAPTER_ADDRESSES_LH@@@@VDummyContext@@@@QEAAXXZ; AutoArray<_IP_ADAPTER_ADDRESSES_LH * *,LocalAllocArrayFunctor<_IP_ADAPTER_ADDRESSES_LH *>,DummyContext>::Clear(void)
0x1800e801d  mov     [rbp+57h+var_C8], r15
0x1800e8021  mov     [rbp+57h+var_C0], 2
0x1800e8028  test    r15, r15
0x1800e802b  jz      loc_1800E8371
0x1800e8031  lea     rdx, [rsp+120h+nSize]; nSize
0x1800e8036  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800e803a  call    cs:__imp_GetComputerNameW
0x1800e8040  test    eax, eax
0x1800e8042  jz      short loc_1800E8054
0x1800e8044  lea     rdx, [rbp+57h+Buffer]
0x1800e8048  lea     rcx, ?m_pszFriendlyName@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszFriendlyName
0x1800e804f  call    ??4?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(ushort const *)
0x1800e8054  mov     esi, r14d
0x1800e8057  lea     rax, ?m_aProtocols@CNetworkAddresses@@0QBKB; ulong const near * const CNetworkAddresses::m_aProtocols
0x1800e805e  mov     r12d, r14d
0x1800e8061  mov     r14d, esi
0x1800e8064  lea     r13, [rbp+57h+var_B0]
0x1800e8068  lea     r13, [r13+r14*4+0]
0x1800e806d  mov     [rsp+120h+var_100], r13
0x1800e8072  mov     r9, [r15+r14*8]
0x1800e8076  xor     r8d, r8d
0x1800e8079  lea     edx, [r8+2Eh]
0x1800e807d  mov     ecx, [rax+r14*4]
0x1800e8081  mov     rax, cs:?m_pGetAdaptersAddresses@CNetworkAddresses@@0P6AKKKPEAXPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAK@ZEA; ulong (*CNetworkAddresses::m_pGetAdaptersAddresses)(ulong,ulong,void *,_IP_ADAPTER_ADDRESSES_LH *,ulong *)
0x1800e8088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e808d  mov     ebx, eax
0x1800e808f  cmp     eax, 6Fh ; 'o'
0x1800e8092  jnz     short loc_1800E80DD
0x1800e8094  mov     rcx, [r15+r14*8]; hMem
0x1800e8098  test    rcx, rcx
0x1800e809b  jz      short loc_1800E80AB
0x1800e809d  call    cs:__imp_LocalFree
0x1800e80a3  mov     qword ptr [r15+r14*8], 0
0x1800e80ab  mov     edx, [r13+0]; uBytes
0x1800e80af  mov     ecx, 40h ; '@'; uFlags
0x1800e80b4  call    cs:__imp_LocalAlloc
0x1800e80ba  mov     [r15+r14*8], rax
0x1800e80be  test    rax, rax
0x1800e80c1  jz      loc_1800E8371
0x1800e80c7  inc     r12d
0x1800e80ca  cmp     r12d, 5
0x1800e80ce  jnb     loc_1800E8362
0x1800e80d4  lea     rax, ?m_aProtocols@CNetworkAddresses@@0QBKB; ulong const near * const CNetworkAddresses::m_aProtocols
0x1800e80db  jmp     short loc_1800E806D
0x1800e80dd  xor     r14d, r14d
0x1800e80e0  test    ebx, ebx
0x1800e80e2  jnz     loc_1800E8360
0x1800e80e8  inc     esi
0x1800e80ea  cmp     esi, 2
0x1800e80ed  lea     rax, ?m_aProtocols@CNetworkAddresses@@0QBKB; ulong const near * const CNetworkAddresses::m_aProtocols
0x1800e80f4  jb      loc_1800E805E
0x1800e80fa  mov     r8d, r14d
0x1800e80fd  mov     rdx, [r15+r8*8]
0x1800e8101  jmp     short loc_1800E8128
0x1800e8103  mov     rcx, [rdx+18h]
0x1800e8107  test    rcx, rcx
0x1800e810a  jz      short loc_1800E8124
0x1800e810c  mov     eax, [rcx+4]
0x1800e810f  and     al, 3
0x1800e8111  cmp     al, 1
0x1800e8113  jnz     short loc_1800E8117
0x1800e8115  inc     edi
0x1800e8117  mov     rcx, [rcx+8]
0x1800e811b  test    rcx, rcx
0x1800e811e  jnz     short loc_1800E810C
0x1800e8120  mov     dword ptr [rsp+120h+var_E8], edi
0x1800e8124  mov     rdx, [rdx+8]
0x1800e8128  test    rdx, rdx
0x1800e812b  jnz     short loc_1800E8103
0x1800e812d  inc     r8
0x1800e8130  cmp     r8, 2
0x1800e8134  jnz     short loc_1800E80FD
0x1800e8136  test    edi, edi
0x1800e8138  jz      loc_1800E82C5
0x1800e813e  lea     eax, [rdi+rdi*2]
0x1800e8141  lea     r12d, ds:8[rax*4]
0x1800e8149  mov     r8, r14
0x1800e814c  mov     rdx, [r15+r8*8]
0x1800e8150  jmp     short loc_1800E8172
0x1800e8152  mov     rcx, [rdx+18h]
0x1800e8156  jmp     short loc_1800E8169
0x1800e8158  mov     eax, [rcx+4]
0x1800e815b  and     al, 3
0x1800e815d  cmp     al, 1
0x1800e815f  jnz     short loc_1800E8165
0x1800e8161  add     r12d, [rcx+18h]
0x1800e8165  mov     rcx, [rcx+8]
0x1800e8169  test    rcx, rcx
0x1800e816c  jnz     short loc_1800E8158
0x1800e816e  mov     rdx, [rdx+8]
0x1800e8172  test    rdx, rdx
0x1800e8175  jnz     short loc_1800E8152
0x1800e8177  inc     r8
0x1800e817a  cmp     r8, 2
0x1800e817e  jnz     short loc_1800E814C
0x1800e8180  mov     r13d, r12d
0x1800e8183  mov     edx, r12d; uBytes
0x1800e8186  lea     ecx, [r8+3Eh]; uFlags
0x1800e818a  call    cs:__imp_LocalAlloc
0x1800e8190  mov     rdi, rax
0x1800e8193  lea     rcx, [rbp+57h+var_A8]
0x1800e8197  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x1800e819c  mov     [rbp+57h+var_A8], rdi
0x1800e81a0  test    rdi, rdi
0x1800e81a3  jz      loc_1800E8371
0x1800e81a9  mov     r9d, 4
0x1800e81af  lea     r8, [rsp+120h+var_E8]
0x1800e81b4  mov     edx, r13d
0x1800e81b7  mov     rcx, rdi
0x1800e81ba  call    SafeCopyMemory
0x1800e81bf  mov     [rsp+120h+var_F0], eax
0x1800e81c3  test    eax, eax
0x1800e81c5  jns     short loc_1800E81E8
0x1800e81c7  lea     rcx, aHrSafecopymemo_21; "hr = SafeCopyMemory(Buffer, dwSize, &dw"...
0x1800e81ce  mov     r8d, 3D3h
0x1800e81d4  mov     r9d, eax
0x1800e81d7  mov     [rsp+120h+var_100], rcx
0x1800e81dc  lea     rdx, aCnetworkaddres_5; "CNetworkAddresses::_PopulateDeviceAddre"...
0x1800e81e3  jmp     loc_1800E7FD6
0x1800e81e8  mov     [rsp+120h+var_E0], r14d
0x1800e81ed  mov     eax, dword ptr [rsp+120h+var_E8]
0x1800e81f1  lea     r10, [rax+1]
0x1800e81f5  lea     r10, [rax+r10*2]
0x1800e81f9  lea     r10, [rdi+r10*4]
0x1800e81fd  mov     [rsp+120h+var_E8], r10
0x1800e8202  mov     eax, r14d
0x1800e8205  mov     rsi, [r15+rax*8]
0x1800e8209  jmp     loc_1800E8296
0x1800e820e  mov     rbx, [rsi+18h]
0x1800e8212  jmp     short loc_1800E828D
0x1800e8214  mov     eax, [rbx+4]
0x1800e8217  and     al, 3
0x1800e8219  cmp     al, 1
0x1800e821b  jnz     short loc_1800E8289
0x1800e821d  movsxd  r9, dword ptr [rbx+18h]
0x1800e8221  mov     rdx, r13
0x1800e8224  sub     rdx, r10
0x1800e8227  add     rdx, rdi
0x1800e822a  mov     r8, [rbx+10h]
0x1800e822e  mov     rcx, r10
0x1800e8231  call    SafeCopyMemory
0x1800e8236  mov     [rsp+120h+var_F0], eax
0x1800e823a  test    eax, eax
0x1800e823c  js      loc_1800E8331
0x1800e8242  mov     r8d, [rsp+120h+var_E0]
0x1800e8247  lea     rcx, [r8+r8*2]
0x1800e824b  mov     eax, [rbx+18h]
0x1800e824e  lea     rdx, [rdi+8]
0x1800e8252  mov     [rdx+rcx*4], eax
0x1800e8255  mov     r10, [rsp+120h+var_E8]
0x1800e825a  mov     eax, r10d
0x1800e825d  sub     eax, edx
0x1800e825f  mov     [rdx+rcx*4+8], eax
0x1800e8263  mov     eax, r14d
0x1800e8266  lea     r9, ?m_aProtocols@CNetworkAddresses@@0QBKB; ulong const near * const CNetworkAddresses::m_aProtocols
0x1800e826d  mov     eax, [r9+rax*4]
0x1800e8271  mov     [rdx+rcx*4+4], eax
0x1800e8275  inc     r8d
0x1800e8278  mov     [rsp+120h+var_E0], r8d
0x1800e827d  movsxd  rax, dword ptr [rbx+18h]
0x1800e8281  add     r10, rax
0x1800e8284  mov     [rsp+120h+var_E8], r10
0x1800e8289  mov     rbx, [rbx+8]
0x1800e828d  test    rbx, rbx
0x1800e8290  jnz     short loc_1800E8214
0x1800e8292  mov     rsi, [rsi+8]
0x1800e8296  test    rsi, rsi
0x1800e8299  jnz     loc_1800E820E
0x1800e829f  inc     r14d
0x1800e82a2  cmp     r14d, 2
0x1800e82a6  jb      loc_1800E8202
0x1800e82ac  lea     r8, ?m_pszAddresses@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszAddresses
0x1800e82b3  mov     edx, r12d; int
0x1800e82b6  mov     rcx, rdi; unsigned __int8 *
0x1800e82b9  call    ?Base64Encode@PassportEncode@@YAJPEBXKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Encode(void const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800e82be  mov     [rsp+120h+var_F0], eax
0x1800e82c2  xor     r14d, r14d
0x1800e82c5  cmp     [rsp+120h+var_F0], r14d
0x1800e82ca  jl      loc_1800E8379
0x1800e82d0  cmp     cs:?m_fLKGIsValid@CNetworkAddresses@@0EA, r14b; uchar CNetworkAddresses::m_fLKGIsValid
0x1800e82d7  jz      short loc_1800E8354
0x1800e82d9  lea     rdx, [rbp+57h+var_D0]
0x1800e82dd  lea     rcx, [rsp+120h+var_D8]
0x1800e82e2  call    ?_GetLastKnownGood@CNetworkAddresses@@CAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@0@Z; CNetworkAddresses::_GetLastKnownGood(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800e82e7  mov     [rsp+120h+var_F0], eax
0x1800e82eb  test    eax, eax
0x1800e82ed  js      short loc_1800E8343
0x1800e82ef  mov     cs:?m_fOutOfSync@CNetworkAddresses@@0KA, r14d; ulong CNetworkAddresses::m_fOutOfSync
0x1800e82f6  mov     rdx, cs:?m_pszAddresses@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszAddresses
0x1800e82fd  lea     rcx, [rsp+120h+var_D8]
0x1800e8302  call    ?Compare@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEBAHPEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Compare(char const *)
0x1800e8307  nop
0x1800e8308  test    eax, eax
0x1800e830a  jz      short loc_1800E8313
0x1800e830c  or      cs:?m_fOutOfSync@CNetworkAddresses@@0KA, 1; ulong CNetworkAddresses::m_fOutOfSync
0x1800e8313  mov     rdx, cs:?m_pszFriendlyName@CNetworkAddresses@@0V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@A; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> CNetworkAddresses::m_pszFriendlyName
0x1800e831a  lea     rcx, [rbp+57h+var_D0]
0x1800e831e  call    ?Compare@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEBAHPEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Compare(char const *)
0x1800e8323  nop
0x1800e8324  test    eax, eax
0x1800e8326  jz      short loc_1800E834D
0x1800e8328  or      cs:?m_fOutOfSync@CNetworkAddresses@@0KA, 2; ulong CNetworkAddresses::m_fOutOfSync
0x1800e832f  jmp     short loc_1800E834D
0x1800e8331  lea     rcx, aHrSafecopymemo_33; "hr = SafeCopyMemory(pCur, dwSize - (pCu"...
0x1800e8338  mov     r8d, 3ECh
0x1800e833e  jmp     loc_1800E81D4
0x1800e8343  mov     cs:?m_fOutOfSync@CNetworkAddresses@@0KA, 3; ulong CNetworkAddresses::m_fOutOfSync
0x1800e834d  mov     [rsp+120h+var_F0], r14d
0x1800e8352  jmp     short loc_1800E8379
0x1800e8354  mov     cs:?m_fOutOfSync@CNetworkAddresses@@0KA, 3; ulong CNetworkAddresses::m_fOutOfSync
0x1800e835e  jmp     short loc_1800E8379
0x1800e8360  jle     short loc_1800E836B
0x1800e8362  movzx   ebx, bx
0x1800e8365  or      ebx, 80070000h
0x1800e836b  mov     [rsp+120h+var_F0], ebx
0x1800e836f  jmp     short loc_1800E8379
0x1800e8371  mov     [rsp+120h+var_F0], 8007000Eh
0x1800e8379  mov     ebx, [rsp+120h+var_F0]
0x1800e837d  lea     rcx, [rbp+57h+var_90]
0x1800e8381  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800e8386  nop
0x1800e8387  lea     rcx, [rsp+120h+var_D8]
0x1800e838c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e8391  nop
0x1800e8392  lea     rcx, [rbp+57h+var_D0]
0x1800e8396  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e839b  nop
0x1800e839c  lea     rcx, [rbp+57h+var_A8]
  ... truncated ...
```
