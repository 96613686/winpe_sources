# RtmAddRouteToDest

- ea: `0x18000b440`
- end: `0x18000c54e`
- name: `RtmAddRouteToDest`
- size: `4366`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_ROUTE_HANDLE RouteHandle, PRTM_NET_ADDRESS DestAddress, PRTM_ROUTE_INFO RouteInfo, ULONG TimeToLive, RTM_ROUTE_LIST_HANDLE RouteListHandle, RTM_NOTIFY_FLAGS NotifyType, RTM_NOTIFY_HANDLE NotifyHandle, PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002380`
- `0x180002560`
- `0x1800027d8`
- `0x180002bec`
- `0x180002cb0`
- `0x180009d14`
- `0x180009ef0`
- `0x18000a0b0`
- `0x18000a1bc`
- `0x18000a230`
- `0x18000a298`
- `0x18000b224`
- `0x18000b294`
- `0x18000b3bc`
- `0x18000b440`
- `0x18000dc60`
- `0x180014d2c`
- `0x180015178`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000b642`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000bf09`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b642`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000bf09`
- `ntdll!RtlReleaseResource` at `0x18000b630`
- `ntdll!RtlReleaseResource` at `0x18000b713`
- `ntdll!RtlReleaseResource` at `0x18000b775`
- `ntdll!RtlReleaseResource` at `0x18000bef4`
- `ntdll!RtlReleaseResource` at `0x18000bf5d`
- `ntdll!RtlReleaseResource` at `0x18000b630`
- `ntdll!RtlReleaseResource` at `0x18000b713`
- `ntdll!RtlReleaseResource` at `0x18000b775`
- `ntdll!RtlReleaseResource` at `0x18000bef4`
- `ntdll!RtlReleaseResource` at `0x18000bf5d`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c0a3`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c195`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c0a3`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c195`
- `ntdll!RtlAcquireResourceShared` at `0x18000b5ec`
- `ntdll!RtlAcquireResourceShared` at `0x18000bea2`
- `ntdll!RtlAcquireResourceShared` at `0x18000b5ec`
- `ntdll!RtlAcquireResourceShared` at `0x18000bea2`
- `KERNEL32!HeapAlloc` at `0x18000bf85`
- `KERNEL32!HeapAlloc` at `0x18000bf85`
- `KERNEL32!GetProcessHeap` at `0x18000bf76`
- `KERNEL32!GetProcessHeap` at `0x18000bfda`
- `KERNEL32!GetProcessHeap` at `0x18000c4f4`
- `KERNEL32!GetProcessHeap` at `0x18000bf76`
- `KERNEL32!GetProcessHeap` at `0x18000bfda`
- `KERNEL32!GetProcessHeap` at `0x18000c4f4`
- `KERNEL32!HeapFree` at `0x18000bfe8`
- `KERNEL32!HeapFree` at `0x18000c502`
- `KERNEL32!HeapFree` at `0x18000bfe8`
- `KERNEL32!HeapFree` at `0x18000c502`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000bfbb`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000bfbb`
- `KERNEL32!GetLastError` at `0x18000bfcb`
- `KERNEL32!GetLastError` at `0x18000bfcb`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000c4ea`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000c4ea`
- `WS2_32!__imp_htonl` at `0x18000c22c`
- `WS2_32!__imp_htonl` at `0x18000c326`
- `WS2_32!__imp_htonl` at `0x18000c22c`
- `WS2_32!__imp_htonl` at `0x18000c326`

## pseudocode

```c
DWORD __stdcall RtmAddRouteToDest(
        RTM_ENTITY_HANDLE RtmRegHandle,
        PRTM_ROUTE_HANDLE RouteHandle,
        PRTM_NET_ADDRESS DestAddress,
        PRTM_ROUTE_INFO RouteInfo,
        ULONG TimeToLive,
        RTM_ROUTE_LIST_HANDLE RouteListHandle,
        RTM_NOTIFY_FLAGS NotifyType,
        RTM_NOTIFY_HANDLE NotifyHandle,
        PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)
{
  unsigned __int64 v9; // r14
  PRTM_ROUTE_HANDLE v11; // r12
  unsigned __int64 v12; // rsi
  PRTM_ROUTE_INFO v13; // r13
  char *v14; // rcx
  DWORD result; // eax
  __int64 v16; // r15
  DWORD inserted; // ebx
  struct _RTL_RESOURCE *v18; // rsi
  int v19; // r13d
  PRTM_ROUTE_CHANGE_FLAGS v20; // rdi
  _QWORD *i; // rcx
  int v22; // r11d
  unsigned int v23; // r10d
  ULONG Preference; // eax
  ULONG Metric; // eax
  _QWORD *v26; // rdx
  LPVOID *v27; // rcx
  __int64 *j; // rcx
  unsigned int v29; // edx
  unsigned int v30; // edx
  __int64 **v31; // rdx
  int v32; // r9d
  int v33; // r13d
  unsigned int v34; // r8d
  unsigned int v35; // edx
  LPVOID *k; // rcx
  PRTM_ROUTE_INFO v37; // r12
  RTM_VIEW_SET BelongsToViews; // ebx
  unsigned int v39; // edi
  __int64 v40; // r8
  LPVOID *v41; // rcx
  _DWORD *v42; // rdx
  ULONG v43; // eax
  ULONG v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned int v47; // esi
  int v48; // ebx
  unsigned int v49; // edi
  unsigned int v50; // r13d
  __int64 v51; // rax
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int64 *v54; // rcx
  __int64 v55; // rdx
  _QWORD *v56; // rsi
  _QWORD *v57; // r12
  _QWORD *v58; // rax
  _QWORD *v59; // rdi
  __int64 v60; // rax
  unsigned int v61; // eax
  unsigned int v62; // eax
  __int64 v63; // rax
  int v64; // edx
  LPVOID *v65; // r8
  LPVOID *v66; // rax
  int v67; // eax
  unsigned int v68; // r13d
  unsigned int v69; // r9d
  unsigned int v70; // eax
  unsigned int v71; // edx
  int v72; // eax
  int v73; // ecx
  BOOL v74; // eax
  PRTM_ROUTE_CHANGE_FLAGS v75; // rax
  unsigned __int64 v76; // rcx
  void *v77; // rcx
  unsigned __int64 Neighbour; // rax
  unsigned int NumNextHops; // ebx
  unsigned int v80; // edx
  __int64 v81; // rsi
  unsigned int m; // edi
  void *v83; // rcx
  __int16 v84; // cx
  unsigned int n; // edx
  __int64 v86; // rcx
  HANDLE *v87; // rdi
  __int64 v88; // rdx
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // r13
  _QWORD *v92; // rax
  _QWORD *v93; // rcx
  _QWORD *v94; // rdx
  _QWORD *v95; // rdx
  HANDLE *v96; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v98; // rax
  void *v99; // rbx
  HANDLE v100; // rax
  __int64 v101; // r12
  __int128 *v102; // r9
  __int128 *v103; // r9
  __int64 v104; // rbx
  __int128 *v105; // r9
  __int128 *v106; // r9
  __int16 v107; // ax
  unsigned int v108; // esi
  u_long v109; // ecx
  __int128 *v110; // r9
  __int64 v111; // r13
  __int16 v112; // ax
  u_long v113; // ebx
  __int128 *v114; // r9
  __int128 *v115; // r9
  __int128 *v116; // r9
  HANDLE v117; // rax
  DWORD DueTime[2]; // [rsp+20h] [rbp-E0h]
  DWORD DueTimea[2]; // [rsp+20h] [rbp-E0h]
  DWORD Period[2]; // [rsp+28h] [rbp-D8h]
  DWORD Perioda[2]; // [rsp+28h] [rbp-D8h]
  __int64 Flags; // [rsp+30h] [rbp-D0h]
  __int64 v123; // [rsp+38h] [rbp-C8h]
  __int64 v124; // [rsp+40h] [rbp-C0h]
  __int64 v125; // [rsp+48h] [rbp-B8h]
  __int64 v126; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v127; // [rsp+50h] [rbp-B0h]
  char *Parameter; // [rsp+58h] [rbp-A8h]
  __int64 v129; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v130; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  DWORD pLength; // [rsp+78h] [rbp-88h] BYREF
  PRTM_ROUTE_HANDLE v133; // [rsp+80h] [rbp-80h]
  __int64 v134; // [rsp+88h] [rbp-78h]
  PRTM_ROUTE_INFO v135; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v136; // [rsp+98h] [rbp-68h]
  RTM_ENTITY_HANDLE v137; // [rsp+A0h] [rbp-60h]
  PRTM_ROUTE_CHANGE_FLAGS v138; // [rsp+A8h] [rbp-58h]
  struct in6_addr Addr; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v140[2]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG uliInst[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v142; // [rsp+F0h] [rbp-10h] BYREF
  int v143; // [rsp+100h] [rbp+0h] BYREF
  __int128 v144; // [rsp+104h] [rbp+4h]
  __int128 v145; // [rsp+114h] [rbp+14h]
  int v146; // [rsp+124h] [rbp+24h]
  CHAR S[80]; // [rsp+130h] [rbp+30h] BYREF
  int v148; // [rsp+180h] [rbp+80h] BYREF
  char v149[2044]; // [rsp+184h] [rbp+84h] BYREF

  v9 = 0;
  v133 = RouteHandle;
  v11 = RouteHandle;
  v137 = RtmRegHandle;
  v12 = (unsigned __int64)RtmRegHandle;
  v138 = ChangeFlags;
  *(_QWORD *)uliInst = 0;
  v129 = 0;
  pLength = 0;
  memset(v140, 0, sizeof(v140));
  v148 = 0;
  v13 = RouteInfo;
  v135 = RouteInfo;
  memset_0(v149, 0, sizeof(v149));
  v143 = 0;
  v146 = 0;
  v134 = v12 ^ 0x7754DF32;
  v144 = 0;
  v145 = 0;
  v142 = 0;
  if ( v12 == 0x7754DF32 || *(_DWORD *)((v12 ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v14 = *(char **)((v12 ^ 0x7754DF32) + 0x10);
  Parameter = v14;
  if ( (~*((_DWORD *)v14 + 10) & v13->BelongsToViews) != 0 )
    return 87;
  *(_QWORD *)Addr.u.Byte = 0;
  if ( RouteListHandle )
  {
    *(_QWORD *)Addr.u.Byte = (unsigned __int64)RouteListHandle ^ 0x7754DF32;
    if ( (unsigned __int64)RouteListHandle == 0x7754DF32 )
      return 6;
    v9 = 0;
  }
  GetInstance((LPSPropValue)*(unsigned __int16 *)(*((_QWORD *)v14 + 2) + 4LL), 0, (ULONG)uliInst);
  if ( result )
    return result;
  LODWORD(v126) = 0;
  v16 = 0;
  lpMem = 0;
  if ( !v11 || (v9 = (unsigned __int64)*v11) == 0 )
  {
    v130 = (LPVOID)v9;
    v18 = (struct _RTL_RESOURCE *)(Parameter + 608);
    RtlAcquireResourceShared((PRTL_RESOURCE)(Parameter + 608), 1u);
    inserted = SearchInTable(*((_QWORD *)Parameter + 89), DestAddress->NumBits, (int)DestAddress + 4, 0, (__int64)&v129);
    if ( inserted )
    {
      RtlReleaseResource(v18);
      v19 = 1;
      RtlAcquireResourceExclusive(v18, 1u);
      inserted = SearchInTable(
                   *((_QWORD *)Parameter + 89),
                   DestAddress->NumBits,
                   (int)DestAddress + 4,
                   (unsigned int)v140,
                   (__int64)&v129);
      if ( inserted )
      {
        inserted = CreateRoute(v134, v135, &v130);
        if ( inserted )
        {
          v9 = (unsigned __int64)v130;
          goto LABEL_35;
        }
        inserted = CreateDest(Parameter, DestAddress, &lpMem);
        if ( inserted )
        {
          v9 = (unsigned __int64)v130;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v130, 0xFFFFFFFF) == 1 )
            DestroyRoute((LPVOID)v9);
          v16 = (__int64)lpMem;
          goto LABEL_35;
        }
        v16 = (__int64)lpMem;
        inserted = InsertIntoTable(
                     *((_QWORD *)Parameter + 89),
                     DestAddress->NumBits,
                     (int)DestAddress + 4,
                     (unsigned int)v140,
                     (__int64)lpMem + 16);
        if ( inserted )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
            DestroyDest((LPVOID)v16);
          v9 = (unsigned __int64)v130;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v130, 0xFFFFFFFF) == 1 )
            DestroyRoute((LPVOID)v9);
          goto LABEL_35;
        }
        LODWORD(v126) = 1;
        *v138 = 2;
        ++*((_DWORD *)Parameter + 180);
        v9 = (unsigned __int64)v130;
        *((_QWORD *)v130 + 6) = v16 ^ 0x7754DF32;
LABEL_25:
        AcquireWriteLock(v16 + 32);
        if ( !v19 )
        {
          RtlReleaseResource(v18);
LABEL_36:
          v13 = v135;
          v11 = v133;
          v12 = (unsigned __int64)v137;
          goto LABEL_37;
        }
LABEL_35:
        RtlReleaseResource(v18);
        if ( inserted )
          return inserted;
        goto LABEL_36;
      }
    }
    else
    {
      v19 = 0;
    }
    v16 = v129 - 16;
    goto LABEL_25;
  }
  if ( *v138 )
    return 87;
  v9 ^= 0x7754DF32u;
  v130 = (LPVOID)v9;
  if ( !v9 )
    return 6;
  v16 = *(_QWORD *)(v9 + 48) ^ 0x7754DF32LL;
  AcquireWriteLock(v16 + 32);
  inserted = v12 != *(_QWORD *)(v9 + 56) ? 5 : 0;
  if ( *(_BYTE *)(v9 + 72) == 2 )
  {
    inserted = 6;
LABEL_15:
    ReleaseWriteLock(v16 + 32);
    return inserted;
  }
  if ( *(_QWORD *)(v9 + 56) != v12 )
    goto LABEL_15;
LABEL_37:
  v20 = v138;
  if ( !v9 )
  {
    if ( (*(_BYTE *)v138 & 2) != 0 )
    {
      i = (_QWORD *)(v16 + 56);
    }
    else
    {
      for ( i = *(_QWORD **)(v16 + 56); i != (_QWORD *)(v16 + 56); i = (_QWORD *)*i )
      {
        v9 = (unsigned __int64)(i - 1);
        v130 = i - 1;
        if ( i[6] == v12 && ((*(_BYTE *)v138 & 1) != 0 || *(RTM_NEXTHOP_HANDLE *)(v9 + 64) == v13->Neighbour) )
          break;
      }
    }
    if ( i == (_QWORD *)(v16 + 56) )
    {
      inserted = CreateRoute(v134, v13, &v130);
      if ( inserted )
        goto LABEL_15;
      *v20 = 2;
      _InterlockedIncrement((volatile signed __int32 *)v16);
      v9 = (unsigned __int64)v130;
      *((_QWORD *)v130 + 6) = v16 ^ 0x7754DF32;
    }
  }
  if ( *v20 != 2 )
  {
    Preference = v13->PrefInfo.Preference;
    v23 = *(_DWORD *)(v9 + 84);
    LODWORD(v129) = v23;
    if ( Preference < *(_DWORD *)(v9 + 80) )
    {
LABEL_53:
      v22 = 1;
      goto LABEL_58;
    }
    if ( Preference <= *(_DWORD *)(v9 + 80) )
    {
      Metric = v13->PrefInfo.Metric;
      if ( Metric < *(_DWORD *)(v9 + 76) )
        goto LABEL_53;
      if ( Metric <= *(_DWORD *)(v9 + 76) )
      {
        v22 = 0;
        HIDWORD(v126) = 0;
        goto LABEL_62;
      }
    }
    v22 = -1;
LABEL_58:
    --*(_DWORD *)(v16 + 52);
    v26 = *(_QWORD **)(v9 + 8);
    HIDWORD(v126) = v22;
    if ( v26[1] != v9 + 8 )
      goto LABEL_192;
    v27 = *(LPVOID **)(v9 + 16);
    if ( *v27 != (LPVOID)(v9 + 8) )
      goto LABEL_192;
    *v27 = v26;
    v26[1] = v27;
LABEL_62:
    *(RTM_PREF_INFO *)(v9 + 76) = v13->PrefInfo;
    *(_DWORD *)(v9 + 84) = v13->BelongsToViews;
    if ( !v22 )
      goto LABEL_72;
    goto LABEL_63;
  }
  v22 = 1;
  HIDWORD(v126) = 1;
  v23 = 0;
  LODWORD(v129) = 0;
  _InterlockedIncrement((volatile signed __int32 *)Parameter + 181);
LABEL_63:
  for ( j = *(__int64 **)(v16 + 56); j != (__int64 *)(v16 + 56); j = (__int64 *)*j )
  {
    v29 = *((_DWORD *)j + 18);
    if ( v29 >= *(_DWORD *)(v9 + 80) )
    {
      if ( v29 > *(_DWORD *)(v9 + 80) )
        break;
      v30 = *((_DWORD *)j + 17);
      if ( v30 >= *(_DWORD *)(v9 + 76) && v30 > *(_DWORD *)(v9 + 76) )
        break;
    }
  }
  v31 = (__int64 **)j[1];
  if ( *v31 != j )
    goto LABEL_192;
  *(_QWORD *)(v9 + 8) = j;
  *(_QWORD *)(v9 + 16) = v31;
  *v31 = (__int64 *)(v9 + 8);
  j[1] = v9 + 8;
  ++*(_DWORD *)(v16 + 52);
LABEL_72:
  if ( v11 && !*v11 )
  {
    *v11 = (HANDLE)(v9 ^ 0x7754DF32);
    _InterlockedIncrement((volatile signed __int32 *)v9);
  }
  LODWORD(lpMem) = 0;
  v32 = 0;
  LODWORD(v130) = 0;
  v33 = 0;
  v34 = v23;
  v35 = 0;
  if ( v23 )
  {
    do
    {
      if ( v35 >= 0x20 )
        break;
      if ( (v34 & 1) != 0 )
      {
        for ( k = *(LPVOID **)(v16 + 24LL * *(int *)&Parameter[4 * v35 + 176] + 128); k; k = (LPVOID *)k[1] )
        {
          if ( *k == (LPVOID)v9 )
          {
            v32 |= 1 << v35;
            break;
          }
        }
      }
      ++v35;
      v34 >>= 1;
    }
    while ( v34 );
    LODWORD(lpMem) = v32;
  }
  v37 = v135;
  BelongsToViews = v135->BelongsToViews;
  if ( v22 <= 0 )
    BelongsToViews &= ~v23;
  *(_DWORD *)(v16 + 112) |= BelongsToViews;
  v39 = 0;
  if ( BelongsToViews )
  {
    while ( 1 )
    {
      if ( v39 >= 0x20 )
      {
LABEL_105:
        v32 = (int)lpMem;
        v22 = HIDWORD(v126);
        break;
      }
      if ( (BelongsToViews & 1) != 0 )
      {
        v40 = v16 + 24LL * *(int *)&Parameter[4 * v39 + 176];
        v41 = *(LPVOID **)(v40 + 128);
        if ( !v41 || (v42 = *v41) == 0 || (v43 = v37->PrefInfo.Preference, v43 < v42[20]) )
        {
LABEL_103:
          DestroyRouteList(v41);
          *(_QWORD *)(v16 + 24LL * *(int *)&Parameter[4 * v39 + 176] + 128) = 0;
          v46 = *(int *)&Parameter[4 * v39 + 176];
          v45 = v16 + 8 * (v46 + 2 * (v46 + 8));
LABEL_101:
          result = InsertInRouteList(v45, v9);
          if ( result )
            return result;
          v33 |= 1 << v39;
          LODWORD(v130) = v33;
          goto LABEL_104;
        }
        if ( v43 <= v42[20] )
        {
          if ( v37->PrefInfo.Metric < v42[19] )
            goto LABEL_103;
          v44 = v37->PrefInfo.Metric;
          if ( v44 >= v42[19] && v44 <= v42[19] )
          {
            do
            {
              if ( *v41 == (LPVOID)v9 )
                goto LABEL_104;
              v41 = (LPVOID *)v41[1];
            }
            while ( v41 );
            v45 = v40 + 128;
            goto LABEL_101;
          }
        }
      }
LABEL_104:
      ++v39;
      BelongsToViews >>= 1;
      if ( !BelongsToViews )
        goto LABEL_105;
    }
  }
  LODWORD(v133) = 0;
  v47 = 0;
  if ( v22 >= 0 )
    v48 = v32 & ~v37->BelongsToViews;
  else
    v48 = v32;
  LODWORD(v137) = v48;
  v49 = v48;
  v50 = 0;
  if ( v48 )
  {
    do
    {
      if ( v50 >= 0x20 )
        break;
      if ( (v49 & 1) != 0 )
      {
        v51 = *(int *)&Parameter[4 * v50 + 176];
        v52 = v51 + 2 * (v51 + 8);
        v53 = 0;
        v54 = (__int64 *)(v16 + 8 * v52);
        v55 = *v54;
        if ( *v54 )
        {
          do
          {
            v55 = *(_QWORD *)(v55 + 8);
            ++v53;
          }
          while ( v55 );
          if ( v53 <= 1 )
          {
            if ( v53 == 1 )
            {
              v56 = 0;
              DeleteRouteFromRouteList(v54, v9);
              v57 = *(_QWORD **)(v16 + 56);
              if ( v57 != (_QWORD *)(v16 + 56) )
              {
                v58 = (_QWORD *)(v16 + 56);
                do
                {
                  v59 = v57 - 1;
                  if ( (v48 & *((_DWORD *)v57 + 19)) != 0 )
                  {
                    if ( v56 )
                    {
                      v61 = *((_DWORD *)v56 + 20);
                      if ( v61 >= *((_DWORD *)v59 + 20) && v61 <= *((_DWORD *)v59 + 20) )
                      {
                        v62 = *((_DWORD *)v56 + 19);
                        if ( v62 >= *((_DWORD *)v59 + 19) && v62 <= *((_DWORD *)v59 + 19) )
                        {
                          v63 = *(int *)&Parameter[4 * v50 + 176];
                          result = InsertInRouteList(v16 + 8 * (v63 + 2 * (v63 + 8)), v57 - 1);
                          if ( result )
                            return result;
                        }
                      }
                    }
                    else
                    {
                      v60 = *(int *)&Parameter[4 * v50 + 176];
                      result = InsertInRouteList(v16 + 8 * (v60 + 2 * (v60 + 8)), v57 - 1);
                      if ( result )
                        return result;
                      v56 = v57 - 1;
                    }
                    v58 = (_QWORD *)(v16 + 56);
                  }
                  v57 = (_QWORD *)*v57;
                }
                while ( v57 != v58 );
              }
              v64 = 0;
              v65 = *(LPVOID **)(v16 + 24LL * *(int *)&Parameter[4 * v50 + 176] + 128);
              v66 = v65;
              if ( !v65 )
                goto LABEL_149;
              do
              {
                v66 = (LPVOID *)v66[1];
                ++v64;
              }
              while ( v66 );
              if ( (!v64 || (v48 &= ~(1 << v50), v64 != 1) || *v65 == (LPVOID)v9) && v64 == 1 )
              {
                v47 = (unsigned int)v133;
              }
              else
              {
LABEL_149:
                v47 = (1 << v50) | (unsigned int)v133;
                LODWORD(v133) = v47;
              }
              v49 = (unsigned int)v137;
            }
          }
          else
          {
            DeleteRouteFromRouteList(v54, v9);
            v47 |= 1 << v50;
            v48 &= ~(1 << v50);
            LODWORD(v133) = v47;
          }
        }
      }
      v49 >>= 1;
      ++v50;
      LODWORD(v137) = v49;
    }
    while ( v49 );
    v22 = HIDWORD(v126);
    v37 = v135;
  }
  v67 = v129;
  *(_DWORD *)(v16 + 112) &= ~v48;
  v68 = v47 | (unsigned int)v130;
  LODWORD(v135) = v37->BelongsToViews | v67;
  HIDWORD(v135) = v47 | (unsigned int)v130;
  v136 = v47 | (unsigned int)v130;
  v69 = (unsigned int)lpMem & ~v47;
  if ( v69 )
  {
    if ( !v22 )
    {
      v70 = *(unsigned __int16 *)(v9 + 96);
      if ( (_WORD)v70 == v37->NextHopsList.NumNextHops )
      {
        v71 = 0;
        if ( *(_WORD *)(v9 + 96) )
        {
          while ( *(RTM_NEXTHOP_HANDLE *)(v9 + 8LL * v71 + 104) == v37->NextHopsList.NextHops[v71] )
          {
            if ( ++v71 >= v70 )
              goto LABEL_146;
          }
        }
        else
        {
LABEL_146:
          if ( v71 == v70 )
          {
            v72 = v37->Flags;
            if ( (((unsigned __int8)v72 ^ (unsigned __int8)*(_WORD *)(v9 + 74)) & 0xF) == 0 )
            {
              v73 = 0;
              v74 = v72 != *(unsigned __int16 *)(v9 + 74);
LABEL_151:
              v68 |= v69 & v74;
              HIDWORD(v135) = v68;
              v136 = v69 & v73 | v47 | (unsigned int)v130;
              goto LABEL_152;
            }
          }
        }
      }
    }
    v74 = 1;
    v73 = 1;
    goto LABEL_151;
  }
LABEL_152:
  v75 = v138;
  if ( *v138 == 2 )
  {
    v81 = v134;
LABEL_176:
    if ( v68 )
      *v75 |= 0x10000u;
    v87 = (HANDLE *)Parameter;
    RtlAcquireResourceShared((PRTL_RESOURCE)(Parameter + 744), 1u);
    if ( (_DWORD)v126 )
    {
      v88 = 0;
      v89 = **(_QWORD **)(v16 + 16);
      if ( v89 )
      {
        v90 = *(_QWORD *)(v89 + 24);
        if ( v90 )
          v88 = *(unsigned int *)(v90 + 24);
      }
    }
    else
    {
      v88 = *(unsigned int *)(v16 + 40);
    }
    if ( (unsigned int)ComputeCNsToBeNotified(Parameter, v88, &v135) )
      AddToChangedDestLists(Parameter);
    RtlReleaseResource((PRTL_RESOURCE)(Parameter + 744));
    v91 = *(_QWORD *)Addr.u.Byte;
    if ( !*(_QWORD *)Addr.u.Byte )
      goto LABEL_194;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v81 + 56), 1u);
    v92 = (_QWORD *)(v9 + 24);
    v93 = *(_QWORD **)(v9 + 24);
    if ( v93 == (_QWORD *)(v9 + 24) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v9);
      goto LABEL_191;
    }
    if ( (_QWORD *)v93[1] == v92 )
    {
      v94 = *(_QWORD **)(v9 + 32);
      if ( (_QWORD *)*v94 == v92 )
      {
        *v94 = v93;
        v93[1] = v94;
LABEL_191:
        v95 = *(_QWORD **)(v91 + 16);
        if ( *v95 != v91 + 8 )
          goto LABEL_192;
        *v92 = v91 + 8;
        *(_QWORD *)(v9 + 32) = v95;
        *v95 = v92;
        *(_QWORD *)(v91 + 16) = v92;
        RtlReleaseResource((PRTL_RESOURCE)(v81 + 56));
LABEL_194:
        v96 = *(HANDLE **)(v9 + 40);
        v134 = (__int64)v96;
        if ( TimeToLive != -1 )
        {
          ProcessHeap = GetProcessHeap();
          v98 = HeapAlloc(ProcessHeap, 0, 0x10u);
          *(_QWORD *)(v9 + 40) = v98;
          if ( !v98 )
          {
LABEL_201:
            LOBYTE(v126) = byte_18002BD1A & 8;
            if ( (byte_18002BD1A & 8) != 0 )
            {
              v101 = *(_QWORD *)uliInst + 48LL;
              LOWORD(v143) = 0;
              v102 = &v142;
              if ( *(_QWORD *)uliInst != -48 )
                LODWORD(v102) = uliInst[0] + 48;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                (unsigned int)L"Adding Route with address: ",
                (_DWORD)v102,
                0,
                (__int64)&v143);
              if ( *(_WORD *)(v16 + 80) == 23 )
              {
                *(_OWORD *)uliInst = 0;
                memset_0(S, 0, 0x41u);
                RtmConvertNetAddressToIpv6AddressAndLength(
                  (PRTM_NET_ADDRESS)(v16 + 80),
                  (PIN6_ADDR)uliInst,
                  &pLength,
                  0x10u);
                if ( (byte_18002BD1A & 8) != 0 )
                {
                  Addr = *(struct in6_addr *)uliInst;
                  LOWORD(v148) = 0;
                  LOWORD(v143) = 0;
                  RtlIpv6AddressToStringA(&Addr, S);
                  FormatRRASErrorString(&v148, L"address is %S  mask %d", S);
                  if ( (byte_18002BD1A & 8) != 0 )
                  {
                    v103 = &v142;
                    if ( v101 )
                      LODWORD(v103) = v101;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                      (unsigned int)&v148,
                      (_DWORD)v103,
                      0,
                      (__int64)&v143);
                  }
                }
                v104 = *(_QWORD *)(v9 + 104) ^ 0x7754DF32LL;
                if ( v104 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)v104);
                  RtmConvertNetAddressToIpv6AddressAndLength(
                    (PRTM_NET_ADDRESS)(v104 + 24),
                    (PIN6_ADDR)uliInst,
                    &pLength,
                    0x10u);
                  if ( (byte_18002BD1A & 8) != 0 )
                  {
                    LOWORD(v143) = 0;
                    v105 = &v142;
                    if ( v101 )
                      LODWORD(v105) = v101;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                      (unsigned int)L"Nexthop address: ",
                      (_DWORD)v105,
                      0,
                      (__int64)&v143);
                    if ( (byte_18002BD1A & 8) != 0 )
                    {
                      LOWORD(v148) = 0;
                      LOWORD(v143) = 0;
                      RtlIpv6AddressToStringA((const struct in6_addr *)uliInst, S);
                      FormatRRASErrorString(&v148, L"address is %S  mask %d", S, pLength);
                      if ( (byte_18002BD1A & 8) != 0 )
                      {
                        v106 = &v142;
                        if ( v101 )
                          LODWORD(v106) = v101;
                        McTemplateU0zjzz_EventWriteTransfer(
                          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                          (unsigned int)&v148,
                          (_DWORD)v106,
                          0,
                          (__int64)&v143);
                      }
                    }
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v104, 0xFFFFFFFF) == 1 )
                    DestroyNextHop((LPVOID)v104);
                }
              }
              else
              {
                v107 = *(_WORD *)(v16 + 82);
                v108 = *(_DWORD *)(v16 + 84);
                if ( v107 )
                  v109 = htonl(-1 << (32 - v107));
                else
                  v109 = 0;
                if ( (byte_18002BD1A & 8) != 0 )
                {
                  LOWORD(v148) = 0;
                  LOWORD(v143) = 0;
                  LODWORD(Flags) = (unsigned __int8)v109;
                  Period[0] = HIBYTE(v108);
                  DueTime[0] = BYTE2(v108);
                  FormatRRASErrorString(
                    &v148,
                    L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
                    (unsigned __int8)v108,
                    BYTE1(v108),
                    *(_QWORD *)DueTime,
                    *(_QWORD *)Period,
                    Flags,
                    BYTE1(v109),
                    BYTE2(v109),
                    HIBYTE(v109),
                    v126);
                  if ( (byte_18002BD1A & 8) != 0 )
                  {
                    v110 = &v142;
                    if ( v101 )
                      LODWORD(v110) = v101;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                      (unsigned int)&v148,
                      (_DWORD)v110,
                      0,
                      (__int64)&v143);
                  }
                }
                v111 = *(_QWORD *)(v9 + 104) ^ 0x7754DF32LL;
                if ( v111 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)v111);
                  LODWORD(v129) = *(_DWORD *)(v111 + 28);
                  v112 = *(_WORD *)(v111 + 26);
                  if ( v112 )
                  {
                    v113 = htonl(-1 << (32 - v112));
                    v127 = v113;
                  }
                  else
                  {
                    v113 = 0;
                    v127 = 0;
                  }
                  if ( (byte_18002BD1A & 8) != 0 )
                  {
                    LOWORD(v143) = 0;
                    v114 = &v142;
                    if ( v101 )
                      LODWORD(v114) = v101;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                      (unsigned int)L"Nexthop address: ",
                      (_DWORD)v114,
                      0,
                      (__int64)&v143);
                    if ( (byte_18002BD1A & 8) != 0 )
                    {
                      LOWORD(v148) = 0;
                      LOWORD(v143) = 0;
                      LODWORD(v125) = HIBYTE(v113);
                      LODWORD(v124) = BYTE2(v113);
                      LODWORD(v123) = BYTE1(v113);
                      LODWORD(Flags) = v127;
                      Perioda[0] = BYTE3(v129);
                      DueTimea[0] = BYTE2(v129);
                      FormatRRASErrorString(
                        &v148,
                        L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
                        (unsigned __int8)v129,
                        BYTE1(v129),
                        *(_QWORD *)DueTimea,
                        *(_QWORD *)Perioda,
                        Flags,
                        v123,
                        v124,
                        v125);
                      if ( (byte_18002BD1A & 8) != 0 )
                      {
                        v115 = &v142;
                        if ( v101 )
                          LODWORD(v115) = v101;
                        McTemplateU0zjzz_EventWriteTransfer(
                          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                          (unsigned int)&v148,
                          (_DWORD)v115,
                          0,
                          (__int64)&v143);
                      }
                    }
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v111, 0xFFFFFFFF) == 1 )
                    DestroyNextHop((LPVOID)v111);
                }
                v96 = (HANDLE *)v134;
              }
              if ( (byte_18002BD1A & 8) != 0 )
              {
                LOWORD(v148) = 0;
                LOWORD(v143) = 0;
                FormatRRASErrorString(&v148, L"Dest = %p and Route = %p\n", v16, v9);
                if ( (byte_18002BD1A & 8) != 0 )
                {
                  v116 = &v142;
                  if ( v101 )
                    LODWORD(v116) = v101;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                    (unsigned int)&v148,
                    (_DWORD)v116,
                    0,
                    (__int64)&v143);
                }
              }
              v87 = (HANDLE *)Parameter;
            }
            ReleaseWriteLock(v16 + 32);
            if ( v96 && DeleteTimerQueueTimer(v87[91], *v96, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
            {
              v117 = GetProcessHeap();
              HeapFree(v117, 0, v96);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
                DestroyRoute((LPVOID)v9);
            }
            return 0;
          }
          v98[1] = v9;
          if ( CreateTimerQueueTimer(
                 *(PHANDLE *)(v9 + 40),
                 *((HANDLE *)Parameter + 91),
                 RouteExpiryTimeoutCallback,
                 *(PVOID *)(v9 + 40),
                 TimeToLive,
                 0,
                 0) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v9);
            goto LABEL_201;
          }
          GetLastError();
          v99 = *(void **)(v9 + 40);
          if ( v99 )
          {
            v100 = GetProcessHeap();
            HeapFree(v100, 0, v99);
          }
        }
        *(_QWORD *)(v9 + 40) = 0;
        goto LABEL_201;
      }
    }
LABEL_192:
    __fastfail(3u);
  }
  v76 = *(_QWORD *)(v9 + 64);
  *(_BYTE *)(v9 + 72) = 0;
  *(_BYTE *)(v9 + 73) = v37->Flags1;
  *(_WORD *)(v9 + 74) = v37->Flags;
  *(RTM_PREF_INFO *)(v9 + 76) = v37->PrefInfo;
  *(_DWORD *)(v9 + 84) = v37->BelongsToViews;
  *(_QWORD *)(v9 + 88) = v37->EntitySpecificInfo;
  if ( (RTM_NEXTHOP_HANDLE)v76 != v37->Neighbour )
  {
    if ( v76 )
    {
      v77 = (void *)(v76 ^ 0x7754DF32);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v77, 0xFFFFFFFF) == 1 )
        DestroyNextHop(v77);
    }
    Neighbour = (unsigned __int64)v37->Neighbour;
    if ( Neighbour )
      _InterlockedIncrement((volatile signed __int32 *)(Neighbour ^ 0x7754DF32));
    *(_QWORD *)(v9 + 64) = v37->Neighbour;
  }
  NumNextHops = v37->NextHopsList.NumNextHops;
  v80 = 0;
  v81 = v134;
  if ( *(_DWORD *)(*(_QWORD *)(v134 + 16) + 308LL) <= NumNextHops )
    NumNextHops = *(_DWORD *)(*(_QWORD *)(v134 + 16) + 308LL);
  if ( NumNextHops )
  {
    do
      _InterlockedIncrement((volatile signed __int32 *)((__int64)v37->NextHopsList.NextHops[v80++] ^ 0x7754DF32));
    while ( v80 < NumNextHops );
  }
  for ( m = 0; m < *(unsigned __int16 *)(v9 + 96); ++m )
  {
    v83 = (void *)(*(_QWORD *)(v9 + 8LL * m + 104) ^ 0x7754DF32LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83, 0xFFFFFFFF) == 1 )
      DestroyNextHop(v83);
  }
  if ( NumNextHops > 0xFFFF )
    v84 = -1;
  else
    v84 = NumNextHops;
  result = NumNextHops > 0xFFFF ? 0x216 : 0;
  if ( NumNextHops <= 0xFFFF )
  {
    *(_WORD *)(v9 + 96) = v84;
    for ( n = 0; n < NumNextHops; *(_QWORD *)(v9 + 8 * v86 + 104) = v37->NextHopsList.NextHops[v86] )
      v86 = n++;
    v75 = v138;
    goto LABEL_176;
  }
  return result;
}

```

## disassembly

```asm
0x18000b440  push    rbp
0x18000b442  push    rbx
0x18000b443  push    rsi
0x18000b444  push    rdi
0x18000b445  push    r12
0x18000b447  push    r13
0x18000b449  push    r14
0x18000b44b  push    r15
0x18000b44d  lea     rbp, [rsp-898h]
0x18000b455  sub     rsp, 998h
0x18000b45c  mov     rax, cs:__security_cookie
0x18000b463  xor     rax, rsp
0x18000b466  mov     [rbp+8D0h+var_50], rax
0x18000b46d  mov     rax, [rbp+8D0h+ChangeFlags]
0x18000b474  xor     r14d, r14d
0x18000b477  mov     rbx, [rbp+8D0h+RouteListHandle]
0x18000b47e  xorps   xmm0, xmm0
0x18000b481  mov     rdi, r8
0x18000b484  mov     [rbp+8D0h+var_950], rdx
0x18000b488  mov     r12, rdx
0x18000b48b  mov     [rbp+8D0h+var_930], rcx
0x18000b48f  mov     rsi, rcx
0x18000b492  mov     [rbp+8D0h+var_928], rax
0x18000b496  xor     edx, edx; Val
0x18000b498  mov     qword ptr [rbp+8D0h+uliInst], r14
0x18000b49c  mov     r8d, 7FCh; Size
0x18000b4a2  mov     [rsp+9D0h+var_970], r14
0x18000b4a7  lea     rcx, [rbp+8D0h+var_84C]; void *
0x18000b4ae  mov     [rsp+9D0h+pLength], r14d
0x18000b4b3  movups  [rbp+8D0h+var_910], xmm0
0x18000b4b7  mov     [rbp+8D0h+var_850], r14d
0x18000b4be  mov     r13, r9
0x18000b4c1  movups  [rbp+8D0h+var_900], xmm0
0x18000b4c5  mov     [rbp+8D0h+var_940], r9
0x18000b4c9  call    memset_0
0x18000b4ce  xor     eax, eax
0x18000b4d0  mov     [rbp+8D0h+var_8D0], r14d
0x18000b4d4  xorps   xmm0, xmm0
0x18000b4d7  mov     [rbp+8D0h+var_8AC], eax
0x18000b4da  mov     rax, rsi
0x18000b4dd  mov     edx, 7754DF32h
0x18000b4e2  xor     rax, rdx
0x18000b4e5  mov     [rbp+8D0h+var_948], rax
0x18000b4e9  movups  [rbp+8D0h+var_8CC], xmm0
0x18000b4ed  movups  [rbp+8D0h+var_8BC], xmm0
0x18000b4f1  movups  [rbp+8D0h+var_8E0], xmm0
0x18000b4f5  jz      loc_18000C526
0x18000b4fb  cmp     dword ptr [rax+30h], 1
0x18000b4ff  jz      loc_18000C526
0x18000b505  mov     rcx, [rax+10h]
0x18000b509  mov     [rsp+9D0h+Parameter], rcx
0x18000b50e  mov     eax, [rcx+28h]
0x18000b511  not     eax
0x18000b513  test    [r13+24h], eax
0x18000b517  jnz     loc_18000C51F
0x18000b51d  mov     qword ptr [rbp+8D0h+Addr.u], r14
0x18000b521  test    rbx, rbx
0x18000b524  jz      short loc_18000B539
0x18000b526  mov     r14, rbx
0x18000b529  xor     r14, rdx
0x18000b52c  mov     qword ptr [rbp+8D0h+Addr.u], r14
0x18000b530  jz      loc_18000C526
0x18000b536  xor     r14d, r14d
0x18000b539  mov     rcx, [rcx+10h]
0x18000b53d  lea     r8, [rbp+8D0h+uliInst]; uliInst
0x18000b541  xor     edx, edx; lpPropSv
0x18000b543  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000b547  call    GetInstance
0x18000b54c  test    eax, eax
0x18000b54e  jnz     loc_18000C52B
0x18000b554  mov     [rsp+9D0h+var_980], r14d
0x18000b559  mov     r15, r14
0x18000b55c  mov     [rsp+9D0h+lpMem], r14
0x18000b561  test    r12, r12
0x18000b564  jz      short loc_18000B5D6
0x18000b566  mov     r14, [r12]
0x18000b56a  test    r14, r14
0x18000b56d  jz      short loc_18000B5D6
0x18000b56f  mov     rax, [rbp+8D0h+var_928]
0x18000b573  cmp     dword ptr [rax], 0
0x18000b576  jnz     loc_18000C51F
0x18000b57c  mov     eax, 7754DF32h
0x18000b581  xor     r14, rax
0x18000b584  mov     [rsp+9D0h+var_968], r14
0x18000b589  jz      loc_18000C526
0x18000b58f  mov     r15, [r14+30h]
0x18000b593  xor     r15, rax
0x18000b596  lea     rcx, [r15+20h]
0x18000b59a  call    AcquireWriteLock
0x18000b59f  mov     rax, [r14+38h]
0x18000b5a3  sub     rax, rsi
0x18000b5a6  neg     rax
0x18000b5a9  sbb     ebx, ebx
0x18000b5ab  and     ebx, 5
0x18000b5ae  cmp     byte ptr [r14+48h], 2
0x18000b5b3  jnz     short loc_18000B5BC
0x18000b5b5  mov     ebx, 6
0x18000b5ba  jmp     short loc_18000B5C6
0x18000b5bc  cmp     [r14+38h], rsi
0x18000b5c0  jz      loc_18000B78F
0x18000b5c6  lea     rcx, [r15+20h]
0x18000b5ca  call    ReleaseWriteLock
0x18000b5cf  mov     eax, ebx
0x18000b5d1  jmp     loc_18000C52B
0x18000b5d6  mov     rbx, [rsp+9D0h+Parameter]
0x18000b5db  mov     dl, 1; Wait
0x18000b5dd  mov     [rsp+9D0h+var_968], r14
0x18000b5e2  lea     rsi, [rbx+260h]
0x18000b5e9  mov     rcx, rsi; Resource
0x18000b5ec  call    cs:__imp_RtlAcquireResourceShared
0x18000b5f2  movzx   edx, word ptr [rdi+2]
0x18000b5f6  lea     rax, [rsp+9D0h+var_970]
0x18000b5fb  mov     rcx, [rbx+2C8h]
0x18000b602  lea     r12, [rdi+4]
0x18000b606  mov     r8, r12
0x18000b609  mov     qword ptr [rsp+9D0h+DueTime], rax
0x18000b60e  xor     r9d, r9d
0x18000b611  call    SearchInTable
0x18000b616  mov     ebx, eax
0x18000b618  test    eax, eax
0x18000b61a  jnz     short loc_18000B62D
0x18000b61c  xor     r13d, r13d
0x18000b61f  mov     r15, [rsp+9D0h+var_970]
0x18000b624  add     r15, 0FFFFFFFFFFFFFFF0h
0x18000b628  jmp     loc_18000B702
0x18000b62d  mov     rcx, rsi; Resource
0x18000b630  call    cs:__imp_RtlReleaseResource
0x18000b636  mov     r13d, 1
0x18000b63c  mov     rcx, rsi; Resource
0x18000b63f  mov     dl, r13b; Wait
0x18000b642  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b648  movzx   edx, word ptr [rdi+2]
0x18000b64c  lea     rax, [rsp+9D0h+var_970]
0x18000b651  mov     qword ptr [rsp+9D0h+DueTime], rax
0x18000b656  lea     r9, [rbp+8D0h+var_910]
0x18000b65a  mov     rax, [rsp+9D0h+Parameter]
0x18000b65f  mov     r8, r12
0x18000b662  mov     rcx, [rax+2C8h]
0x18000b669  call    SearchInTable
0x18000b66e  mov     ebx, eax
0x18000b670  test    eax, eax
0x18000b672  jz      short loc_18000B61F
0x18000b674  mov     rdx, [rbp+8D0h+var_940]
0x18000b678  lea     r8, [rsp+9D0h+var_968]
0x18000b67d  mov     rcx, [rbp+8D0h+var_948]
0x18000b681  call    CreateRoute
0x18000b686  mov     ebx, eax
0x18000b688  test    eax, eax
0x18000b68a  jnz     loc_18000B76D
0x18000b690  mov     r14, [rsp+9D0h+Parameter]
0x18000b695  lea     r8, [rsp+9D0h+lpMem]
0x18000b69a  mov     rcx, r14
0x18000b69d  mov     rdx, rdi
0x18000b6a0  call    CreateDest
0x18000b6a5  mov     ebx, eax
0x18000b6a7  test    eax, eax
0x18000b6a9  jnz     loc_18000B74C
0x18000b6af  mov     r15, [rsp+9D0h+lpMem]
0x18000b6b4  lea     r9, [rbp+8D0h+var_910]
0x18000b6b8  movzx   edx, word ptr [rdi+2]
0x18000b6bc  mov     r8, r12
0x18000b6bf  mov     rcx, [r14+2C8h]
0x18000b6c6  lea     rax, [r15+10h]
0x18000b6ca  mov     qword ptr [rsp+9D0h+DueTime], rax
0x18000b6cf  call    InsertIntoTable
0x18000b6d4  mov     ebx, eax
0x18000b6d6  test    eax, eax
0x18000b6d8  jnz     short loc_18000B71B
0x18000b6da  mov     rax, [rbp+8D0h+var_928]
0x18000b6de  mov     [rsp+9D0h+var_980], r13d
0x18000b6e3  mov     dword ptr [rax], 2
0x18000b6e9  mov     rax, r15
0x18000b6ec  inc     dword ptr [r14+2D0h]
0x18000b6f3  mov     r14, [rsp+9D0h+var_968]
0x18000b6f8  xor     rax, 7754DF32h
0x18000b6fe  mov     [r14+30h], rax
0x18000b702  lea     rcx, [r15+20h]
0x18000b706  call    AcquireWriteLock
0x18000b70b  test    r13d, r13d
0x18000b70e  jnz     short loc_18000B772
0x18000b710  mov     rcx, rsi; Resource
0x18000b713  call    cs:__imp_RtlReleaseResource
0x18000b719  jmp     short loc_18000B783
0x18000b71b  or      eax, 0FFFFFFFFh
0x18000b71e  lock xadd [r15], eax
0x18000b723  cmp     eax, r13d
0x18000b726  jnz     short loc_18000B730
0x18000b728  mov     rcx, r15; lpMem
0x18000b72b  call    DestroyDest
0x18000b730  mov     r14, [rsp+9D0h+var_968]
0x18000b735  or      eax, 0FFFFFFFFh
0x18000b738  lock xadd [r14], eax
0x18000b73d  cmp     eax, r13d
0x18000b740  jnz     short loc_18000B772
0x18000b742  mov     rcx, r14; lpMem
0x18000b745  call    DestroyRoute
0x18000b74a  jmp     short loc_18000B772
0x18000b74c  mov     r14, [rsp+9D0h+var_968]
0x18000b751  or      eax, 0FFFFFFFFh
0x18000b754  lock xadd [r14], eax
0x18000b759  cmp     eax, r13d
0x18000b75c  jnz     short loc_18000B766
0x18000b75e  mov     rcx, r14; lpMem
0x18000b761  call    DestroyRoute
0x18000b766  mov     r15, [rsp+9D0h+lpMem]
0x18000b76b  jmp     short loc_18000B772
0x18000b76d  mov     r14, [rsp+9D0h+var_968]
0x18000b772  mov     rcx, rsi; Resource
0x18000b775  call    cs:__imp_RtlReleaseResource
0x18000b77b  test    ebx, ebx
0x18000b77d  jnz     loc_18000B5CF
0x18000b783  mov     r13, [rbp+8D0h+var_940]
0x18000b787  mov     r12, [rbp+8D0h+var_950]
0x18000b78b  mov     rsi, [rbp+8D0h+var_930]
0x18000b78f  mov     rdi, [rbp+8D0h+var_928]
0x18000b793  test    r14, r14
0x18000b796  jnz     short loc_18000B816
0x18000b798  test    byte ptr [rdi], 2
0x18000b79b  jnz     short loc_18000B7CE
0x18000b79d  lea     rdx, [r15+38h]
0x18000b7a1  mov     rcx, [rdx]
0x18000b7a4  jmp     short loc_18000B7C7
0x18000b7a6  lea     r14, [rcx-8]
0x18000b7aa  mov     [rsp+9D0h+var_968], r14
0x18000b7af  cmp     [r14+38h], rsi
0x18000b7b3  jnz     short loc_18000B7C4
0x18000b7b5  test    byte ptr [rdi], 1
0x18000b7b8  jnz     short loc_18000B7D2
0x18000b7ba  mov     rax, [r13+10h]
0x18000b7be  cmp     [r14+40h], rax
0x18000b7c2  jz      short loc_18000B7D2
0x18000b7c4  mov     rcx, [rcx]
0x18000b7c7  cmp     rcx, rdx
0x18000b7ca  jnz     short loc_18000B7A6
0x18000b7cc  jmp     short loc_18000B7D2
0x18000b7ce  lea     rcx, [r15+38h]
0x18000b7d2  lea     rax, [r15+38h]
0x18000b7d6  cmp     rcx, rax
0x18000b7d9  jnz     short loc_18000B816
0x18000b7db  mov     rcx, [rbp+8D0h+var_948]
0x18000b7df  lea     r8, [rsp+9D0h+var_968]
0x18000b7e4  mov     rdx, r13
0x18000b7e7  call    CreateRoute
0x18000b7ec  xor     esi, esi
0x18000b7ee  mov     ebx, eax
0x18000b7f0  test    eax, eax
0x18000b7f2  jnz     loc_18000B5C6
0x18000b7f8  mov     dword ptr [rdi], 2
0x18000b7fe  lock inc dword ptr [r15]
0x18000b802  mov     r14, [rsp+9D0h+var_968]
0x18000b807  mov     rax, r15
0x18000b80a  xor     rax, 7754DF32h
0x18000b810  mov     [r14+30h], rax
0x18000b814  jmp     short loc_18000B818
0x18000b816  xor     esi, esi
0x18000b818  cmp     dword ptr [rdi], 2
0x18000b81b  jnz     short loc_18000B83D
0x18000b81d  mov     rax, [rsp+9D0h+Parameter]
0x18000b822  mov     r11d, 1
0x18000b828  mov     [rsp+9D0h+var_97C], r11d
0x18000b82d  mov     r10d, esi
0x18000b830  mov     dword ptr [rsp+9D0h+var_970], esi
0x18000b834  lock inc dword ptr [rax+2D4h]
0x18000b83b  jmp     short loc_18000B8B6
0x18000b83d  mov     eax, [r13+20h]
0x18000b841  mov     r10d, [r14+54h]
0x18000b845  mov     dword ptr [rsp+9D0h+var_970], r10d
0x18000b84a  cmp     eax, [r14+50h]
0x18000b84e  jnb     short loc_18000B858
0x18000b850  mov     r11d, 1
0x18000b856  jmp     short loc_18000B86A
0x18000b858  ja      short loc_18000B866
0x18000b85a  mov     eax, [r13+1Ch]
0x18000b85e  cmp     eax, [r14+4Ch]
0x18000b862  jb      short loc_18000B850
0x18000b864  jbe     short loc_18000B89A
0x18000b866  or      r11d, 0FFFFFFFFh
0x18000b86a  dec     dword ptr [r15+34h]
0x18000b86e  lea     rax, [r14+8]
0x18000b872  mov     rdx, [rax]
0x18000b875  mov     [rsp+9D0h+var_97C], r11d
0x18000b87a  cmp     [rdx+8], rax
0x18000b87e  jnz     loc_18000BF44
0x18000b884  mov     rcx, [rax+8]
0x18000b888  cmp     [rcx], rax
0x18000b88b  jnz     loc_18000BF44
0x18000b891  mov     [rcx], rdx
0x18000b894  mov     [rdx+8], rcx
0x18000b898  jmp     short loc_18000B8A1
0x18000b89a  mov     r11d, esi
0x18000b89d  mov     [rsp+9D0h+var_97C], esi
0x18000b8a1  mov     rax, [r13+1Ch]
0x18000b8a5  mov     [r14+4Ch], rax
0x18000b8a9  mov     eax, [r13+24h]
0x18000b8ad  mov     [r14+54h], eax
0x18000b8b1  test    r11d, r11d
0x18000b8b4  jz      short loc_18000B900
0x18000b8b6  lea     rax, [r15+38h]
0x18000b8ba  mov     rcx, [rax]
0x18000b8bd  jmp     short loc_18000B8D8
  ... truncated ...
```
