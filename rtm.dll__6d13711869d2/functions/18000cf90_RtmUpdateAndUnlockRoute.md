# RtmUpdateAndUnlockRoute

- ea: `0x18000cf90`
- end: `0x18000d8b4`
- name: `RtmUpdateAndUnlockRoute`
- size: `2340`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ROUTE_HANDLE RouteHandle, ULONG TimeToLive, RTM_ROUTE_LIST_HANDLE RouteListHandle, RTM_NOTIFY_FLAGS NotifyType, RTM_NOTIFY_HANDLE NotifyHandle, PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800027d8`
- `0x180002bec`
- `0x180002cb0`
- `0x180009d14`
- `0x18000a298`
- `0x18000b224`
- `0x18000b294`
- `0x18000b3bc`
- `0x18000cf90`
- `0x18000dc60`
- `0x180015178`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000d74e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000d74e`
- `ntdll!RtlReleaseResource` at `0x18000d72b`
- `ntdll!RtlReleaseResource` at `0x18000d7a1`
- `ntdll!RtlReleaseResource` at `0x18000d72b`
- `ntdll!RtlReleaseResource` at `0x18000d7a1`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000d1a8`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000d1a8`
- `ntdll!RtlAcquireResourceShared` at `0x18000d6fd`
- `ntdll!RtlAcquireResourceShared` at `0x18000d6fd`
- `KERNEL32!HeapAlloc` at `0x18000d7c5`
- `KERNEL32!HeapAlloc` at `0x18000d7c5`
- `KERNEL32!GetProcessHeap` at `0x18000d7b6`
- `KERNEL32!GetProcessHeap` at `0x18000d81a`
- `KERNEL32!GetProcessHeap` at `0x18000d860`
- `KERNEL32!GetProcessHeap` at `0x18000d7b6`
- `KERNEL32!GetProcessHeap` at `0x18000d81a`
- `KERNEL32!GetProcessHeap` at `0x18000d860`
- `KERNEL32!HeapFree` at `0x18000d828`
- `KERNEL32!HeapFree` at `0x18000d86e`
- `KERNEL32!HeapFree` at `0x18000d828`
- `KERNEL32!HeapFree` at `0x18000d86e`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000d7fc`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000d7fc`
- `KERNEL32!GetLastError` at `0x18000d80b`
- `KERNEL32!GetLastError` at `0x18000d80b`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d856`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d856`
- `WS2_32!__imp_htonl` at `0x18000d225`
- `WS2_32!__imp_htonl` at `0x18000d225`

## pseudocode

```c
DWORD __stdcall RtmUpdateAndUnlockRoute(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_ROUTE_HANDLE RouteHandle,
        ULONG TimeToLive,
        RTM_ROUTE_LIST_HANDLE RouteListHandle,
        RTM_NOTIFY_FLAGS NotifyType,
        RTM_NOTIFY_HANDLE NotifyHandle,
        PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)
{
  unsigned int v7; // r12d
  unsigned __int64 v10; // rsi
  DWORD result; // eax
  int *v12; // r13
  __int64 v13; // r14
  __int64 v14; // r14
  __int128 *v15; // r9
  __int64 v16; // r15
  char v17; // bl
  __int128 *v18; // r9
  bool v19; // zf
  __int128 *v20; // r9
  __int16 v21; // ax
  unsigned int v22; // r12d
  u_long v23; // eax
  u_long v24; // ecx
  _QWORD **v25; // r15
  __int64 v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // r8
  _QWORD *j; // rax
  __int64 v31; // rdx
  int v32; // r9d
  _QWORD *v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  _QWORD *i; // rcx
  _QWORD *v37; // rax
  ULONG v38; // r10d
  unsigned int v39; // r8d
  unsigned int v40; // edx
  _QWORD *k; // rcx
  DWORD v42; // ebx
  DWORD m; // edi
  __int64 v44; // rax
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 *v47; // rcx
  __int64 v48; // rdx
  _QWORD *v49; // r13
  _QWORD *v50; // r15
  _QWORD *v51; // rdi
  __int64 v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  int v57; // ecx
  int v58; // edi
  unsigned int v59; // ebx
  unsigned int v60; // r13d
  unsigned int n; // r15d
  __int64 v62; // r8
  __int64 *v63; // rcx
  __int64 v64; // rdx
  unsigned int v65; // eax
  unsigned int v66; // eax
  __int64 v67; // rcx
  int *v68; // rdx
  __int64 v69; // rax
  HANDLE *v70; // rdi
  struct _RTL_RESOURCE *v71; // rbx
  __int64 v72; // r15
  unsigned __int64 v73; // rbx
  _QWORD *v74; // rax
  __int64 v75; // rcx
  _QWORD *v76; // rdx
  _QWORD *v77; // rdx
  DWORD v78; // r15d
  HANDLE *v79; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v81; // rax
  void *v82; // rdi
  HANDLE v83; // rax
  HANDLE v84; // rax
  DWORD DueTime[2]; // [rsp+20h] [rbp-E0h]
  DWORD Period[2]; // [rsp+28h] [rbp-D8h]
  DWORD pLength; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Parameter; // [rsp+58h] [rbp-A8h]
  ULONG uliInst[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v90; // [rsp+68h] [rbp-98h]
  DWORD v91; // [rsp+6Ch] [rbp-94h]
  PRTM_ROUTE_CHANGE_FLAGS v92; // [rsp+70h] [rbp-90h]
  unsigned __int64 v93; // [rsp+78h] [rbp-88h]
  unsigned __int64 v94; // [rsp+80h] [rbp-80h]
  struct in6_addr pAddress; // [rsp+90h] [rbp-70h] BYREF
  __int128 v96; // [rsp+A0h] [rbp-60h] BYREF
  int v97; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v98; // [rsp+B4h] [rbp-4Ch]
  __int128 v99; // [rsp+C4h] [rbp-3Ch]
  int v100; // [rsp+D4h] [rbp-2Ch]
  CHAR S[80]; // [rsp+E0h] [rbp-20h] BYREF
  int v102; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v103[2044]; // [rsp+134h] [rbp+34h] BYREF

  v7 = 0;
  v91 = TimeToLive;
  v92 = ChangeFlags;
  *(_QWORD *)uliInst = 0;
  pLength = 0;
  v102 = 0;
  v93 = (unsigned __int64)RouteListHandle;
  memset_0(v103, 0, sizeof(v103));
  v97 = 0;
  v100 = 0;
  v94 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  v98 = 0;
  v99 = 0;
  v96 = 0;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v10 = (unsigned __int64)RouteHandle ^ 0x7754DF32;
  if ( !v10 || *(_BYTE *)(v10 + 72) == 2 )
    return 6;
  if ( *(RTM_ENTITY_HANDLE *)(v10 + 56) != RtmRegHandle )
    return 5;
  v12 = *(int **)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  v13 = *(_QWORD *)(v10 + 48);
  Parameter = v12;
  *(_DWORD *)(v10 + 84) &= v12[10];
  GetInstance((LPSPropValue)*(unsigned __int16 *)(*((_QWORD *)v12 + 2) + 4LL), 0, (ULONG)uliInst);
  if ( !result )
  {
    v14 = v13 ^ 0x7754DF32;
    LOBYTE(v90) = byte_18002BD1A & 8;
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v15 = &v96;
      v16 = *(_QWORD *)uliInst + 48LL;
      LOWORD(v97) = 0;
      if ( *(_QWORD *)uliInst != -48 )
        LODWORD(v15) = uliInst[0] + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)L"Updating Route with address: ",
        (_DWORD)v15,
        0,
        (__int64)&v97);
      v17 = byte_18002BD1A;
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v102) = 0;
        LOWORD(v97) = 0;
        FormatRRASErrorString(&v102, L"Dest = %p and Route = %p\n", v14, v10);
        v17 = byte_18002BD1A;
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v18 = &v96;
          if ( v16 )
            LODWORD(v18) = v16;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v102,
            (_DWORD)v18,
            0,
            (__int64)&v97);
          v17 = byte_18002BD1A;
        }
      }
      if ( *(_WORD *)(v14 + 80) == 23 )
      {
        pAddress = 0;
        memset_0(S, 0, 0x41u);
        RtmConvertNetAddressToIpv6AddressAndLength((PRTM_NET_ADDRESS)(v14 + 80), &pAddress, &pLength, 0x10u);
        if ( (v17 & 8) == 0 )
          goto LABEL_29;
        LOWORD(v102) = 0;
        LOWORD(v97) = 0;
        RtlIpv6AddressToStringA(&pAddress, S);
        FormatRRASErrorString(&v102, L"address is %S  mask %d", S, pLength);
        v19 = (byte_18002BD1A & 8) == 0;
      }
      else
      {
        v21 = *(_WORD *)(v14 + 82);
        v22 = *(_DWORD *)(v14 + 84);
        if ( v21 )
        {
          v23 = htonl(-1 << (32 - v21));
          v17 = byte_18002BD1A;
          v24 = v23;
        }
        else
        {
          v24 = 0;
        }
        if ( (v17 & 8) == 0 )
        {
          v7 = 0;
          goto LABEL_29;
        }
        LOWORD(v102) = 0;
        LOWORD(v97) = 0;
        Period[0] = HIBYTE(v22);
        DueTime[0] = BYTE2(v22);
        FormatRRASErrorString(
          &v102,
          L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
          (unsigned __int8)v22,
          BYTE1(v22),
          *(_QWORD *)DueTime,
          *(_QWORD *)Period,
          (unsigned __int8)v24,
          BYTE1(v24),
          BYTE2(v24),
          HIBYTE(v24));
        v7 = 0;
        v19 = (byte_18002BD1A & 8) == 0;
      }
      if ( !v19 )
      {
        v20 = &v96;
        if ( v16 )
          LODWORD(v20) = v16;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
          (unsigned int)&v102,
          (_DWORD)v20,
          0,
          (__int64)&v97);
      }
    }
LABEL_29:
    v25 = (_QWORD **)(v14 + 56);
    *v92 = 0;
    v26 = *(_QWORD *)(v10 + 16);
    if ( v26 == v14 + 56 || *(_QWORD *)(v26 + 68) <= *(_QWORD *)(v10 + 76) )
    {
      v33 = (_QWORD *)(v10 + 8);
      v32 = 0;
      v34 = *(_QWORD *)(v10 + 8);
      if ( (_QWORD **)v34 != v25 && *(_QWORD *)(v34 + 68) < *(_QWORD *)(v10 + 76) )
      {
        if ( *(_QWORD **)(v34 + 8) != v33 )
          goto LABEL_115;
        v35 = *(_QWORD **)(v10 + 16);
        if ( (_QWORD *)*v35 != v33 )
          goto LABEL_115;
        *v35 = v34;
        *(_QWORD *)(v34 + 8) = v35;
        for ( i = *(_QWORD **)v34; i != v25; i = (_QWORD *)*i )
        {
          if ( *(_QWORD *)((char *)i + 68) >= *(_QWORD *)(v10 + 76) )
            break;
        }
        v37 = (_QWORD *)i[1];
        if ( (_QWORD *)*v37 != i )
          goto LABEL_115;
        *v33 = i;
        v32 = -1;
        *(_QWORD *)(v10 + 16) = v37;
        *v37 = v33;
        i[1] = v33;
      }
    }
    else
    {
      v27 = (_QWORD *)(v10 + 8);
      v28 = *(_QWORD *)(v10 + 8);
      if ( *(_QWORD *)(v28 + 8) != v10 + 8 )
        goto LABEL_115;
      v29 = *(_QWORD **)(v10 + 16);
      if ( (_QWORD *)*v29 != v27 )
        goto LABEL_115;
      *v29 = v28;
      *(_QWORD *)(v28 + 8) = v29;
      for ( j = *(_QWORD **)(v26 + 8); j != v25; j = (_QWORD *)j[1] )
      {
        if ( *(_QWORD *)((char *)j + 68) <= *(_QWORD *)(v10 + 76) )
          break;
      }
      v31 = *j;
      if ( *(_QWORD **)(*j + 8LL) != j )
        goto LABEL_115;
      *v27 = v31;
      v32 = 1;
      *(_QWORD *)(v10 + 16) = j;
      *(_QWORD *)(v31 + 8) = v27;
      *j = v27;
    }
    v38 = 0;
    v90 = *(_DWORD *)(v14 + 112);
    v39 = v90;
    uliInst[0] = 0;
    v40 = 0;
    if ( v90 )
    {
      do
      {
        if ( v40 >= 0x20 )
          break;
        if ( (v39 & 1) != 0 )
        {
          for ( k = *(_QWORD **)(v14 + 24LL * v12[v40 + 44] + 128); k; k = (_QWORD *)k[1] )
          {
            if ( *k == v10 )
            {
              v38 |= 1 << v40;
              break;
            }
          }
        }
        ++v40;
        v39 >>= 1;
      }
      while ( v39 );
      uliInst[0] = v38;
    }
    v42 = v38;
    if ( v32 >= 0 )
      v42 = v38 & ~*(_DWORD *)(v10 + 84);
    pLength = v42;
    for ( m = v42; m; pLength = m )
    {
      if ( v7 >= 0x20 )
        break;
      if ( (m & 1) != 0 )
      {
        v44 = v12[v7 + 44];
        v45 = v44 + 2 * (v44 + 8);
        v46 = 0;
        v47 = (__int64 *)(v14 + 8 * v45);
        v48 = *v47;
        if ( *v47 )
        {
          do
          {
            v48 = *(_QWORD *)(v48 + 8);
            ++v46;
          }
          while ( v48 );
          if ( v46 <= 1 )
          {
            if ( v46 == 1 )
            {
              v49 = 0;
              DeleteRouteFromRouteList(v47, v10);
              v50 = *v25;
              if ( v50 != (_QWORD *)(v14 + 56) )
              {
                do
                {
                  v51 = v50 - 1;
                  if ( (v42 & *((_DWORD *)v50 + 19)) != 0 )
                  {
                    if ( v49 )
                    {
                      v53 = *((_DWORD *)v49 + 20);
                      if ( v53 >= *((_DWORD *)v51 + 20) && v53 <= *((_DWORD *)v51 + 20) )
                      {
                        v54 = *((_DWORD *)v49 + 19);
                        if ( v54 >= *((_DWORD *)v51 + 19) && v54 <= *((_DWORD *)v51 + 19) )
                        {
                          v55 = *((int *)Parameter + v7 + 44);
                          result = InsertInRouteList(v14 + 8 * (v55 + 2 * (v55 + 8)), v50 - 1);
                          if ( result )
                            return result;
                        }
                      }
                    }
                    else
                    {
                      v52 = *((int *)Parameter + v7 + 44);
                      result = InsertInRouteList(v14 + 8 * (v52 + 2 * (v52 + 8)), v50 - 1);
                      if ( result )
                        return result;
                      v49 = v50 - 1;
                    }
                  }
                  v50 = (_QWORD *)*v50;
                }
                while ( v50 != (_QWORD *)(v14 + 56) );
                m = pLength;
              }
              v12 = (int *)Parameter;
              v56 = *(_QWORD *)(v14 + 24LL * *((int *)Parameter + v7 + 44) + 128);
              v57 = 0;
              if ( v56 )
              {
                do
                {
                  v56 = *(_QWORD *)(v56 + 8);
                  ++v57;
                }
                while ( v56 );
                v25 = (_QWORD **)(v14 + 56);
                if ( v57 )
                  v42 &= ~(1 << v7);
              }
              else
              {
                v25 = (_QWORD **)(v14 + 56);
              }
            }
          }
          else
          {
            DeleteRouteFromRouteList(v47, v10);
            v42 &= ~(1 << v7);
          }
        }
      }
      m >>= 1;
      ++v7;
    }
    v58 = 0;
    *(_DWORD *)(v14 + 112) &= ~v42;
    v59 = 0;
    v60 = *(_DWORD *)(v10 + 84);
    for ( n = v60; n; n >>= 1 )
    {
      if ( v59 >= 0x20 )
        break;
      if ( (n & 1) != 0 )
      {
        v62 = v14 + 24LL * *((int *)Parameter + v59 + 44);
        v63 = *(__int64 **)(v62 + 128);
        if ( !v63 || (v64 = *v63) == 0 || (v65 = *(_DWORD *)(v10 + 80), v65 < *(_DWORD *)(v64 + 80)) )
        {
LABEL_99:
          DestroyRouteList(v63);
          v68 = (int *)Parameter;
          *(_QWORD *)(v14 + 24LL * *((int *)Parameter + v59 + 44) + 128) = 0;
          v69 = v68[v59 + 44];
          v67 = v14 + 8 * (v69 + 2 * (v69 + 8));
LABEL_100:
          result = InsertInRouteList(v67, v10);
          if ( result )
            return result;
          v58 |= 1 << v59;
          goto LABEL_102;
        }
        if ( v65 <= *(_DWORD *)(v64 + 80) )
        {
          if ( *(_DWORD *)(v10 + 76) < *(_DWORD *)(v64 + 76) )
            goto LABEL_99;
          v66 = *(_DWORD *)(v10 + 76);
          if ( v66 >= *(_DWORD *)(v64 + 76) && v66 <= *(_DWORD *)(v64 + 76) )
          {
            do
            {
              if ( *v63 == v10 )
                goto LABEL_102;
              v63 = (__int64 *)v63[1];
            }
            while ( v63 );
            v67 = v62 + 128;
            goto LABEL_100;
          }
        }
      }
LABEL_102:
      ++v59;
    }
    *(_DWORD *)(v14 + 112) |= v60;
    *(_DWORD *)pAddress.u.Byte = *(_DWORD *)(v10 + 84) | v90;
    *(_DWORD *)&pAddress.u.Word[2] = v58 | uliInst[0];
    *(_DWORD *)&pAddress.u.Word[4] = v58 | uliInst[0];
    if ( v58 | uliInst[0] )
      *v92 |= 0x10000u;
    v70 = (HANDLE *)Parameter;
    v71 = (struct _RTL_RESOURCE *)((char *)Parameter + 744);
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)Parameter + 744), 1u);
    if ( (unsigned int)ComputeCNsToBeNotified(v70, *(unsigned int *)(v14 + 40), &pAddress) )
      AddToChangedDestLists(v70);
    RtlReleaseResource(v71);
    if ( !v93 )
      goto LABEL_117;
    v72 = v93 ^ 0x7754DF32;
    if ( v93 == 0x7754DF32 )
      goto LABEL_117;
    v73 = v94;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v94 + 56), 1u);
    v74 = (_QWORD *)(v10 + 24);
    v75 = *(_QWORD *)(v10 + 24);
    if ( v75 == v10 + 24 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v10);
      goto LABEL_114;
    }
    if ( *(_QWORD **)(v75 + 8) == v74 )
    {
      v76 = *(_QWORD **)(v10 + 32);
      if ( (_QWORD *)*v76 == v74 )
      {
        *v76 = v75;
        *(_QWORD *)(v75 + 8) = v76;
LABEL_114:
        v77 = *(_QWORD **)(v72 + 16);
        if ( *v77 != v72 + 8 )
          goto LABEL_115;
        *v74 = v72 + 8;
        *(_QWORD *)(v10 + 32) = v77;
        *v77 = v74;
        *(_QWORD *)(v72 + 16) = v74;
        RtlReleaseResource((PRTL_RESOURCE)(v73 + 56));
LABEL_117:
        v78 = v91;
        v79 = *(HANDLE **)(v10 + 40);
        if ( v91 != -1 )
        {
          ProcessHeap = GetProcessHeap();
          v81 = HeapAlloc(ProcessHeap, 0, 0x10u);
          *(_QWORD *)(v10 + 40) = v81;
          if ( !v81 )
            goto LABEL_125;
          v81[1] = v10;
          if ( CreateTimerQueueTimer(
                 *(PHANDLE *)(v10 + 40),
                 v70[91],
                 RouteExpiryTimeoutCallback,
                 *(PVOID *)(v10 + 40),
                 v78,
                 0,
                 0) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v10);
            goto LABEL_125;
          }
          GetLastError();
          v82 = *(void **)(v10 + 40);
          if ( v82 )
          {
            v83 = GetProcessHeap();
            HeapFree(v83, 0, v82);
          }
          v70 = (HANDLE *)Parameter;
        }
        *(_QWORD *)(v10 + 40) = 0;
LABEL_125:
        ReleaseWriteLock(v14 + 32);
        if ( v79 && DeleteTimerQueueTimer(v70[91], *v79, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        {
          v84 = GetProcessHeap();
          HeapFree(v84, 0, v79);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
            DestroyRoute((LPVOID)v10);
        }
        return 0;
      }
    }
LABEL_115:
    __fastfail(3u);
  }
  return result;
}

```

## disassembly

```asm
0x18000cf90  push    rbp
0x18000cf92  push    rbx
0x18000cf93  push    rsi
0x18000cf94  push    rdi
0x18000cf95  push    r12
0x18000cf97  push    r13
0x18000cf99  push    r14
0x18000cf9b  push    r15
0x18000cf9d  lea     rbp, [rsp-848h]
0x18000cfa5  sub     rsp, 948h
0x18000cfac  mov     rax, cs:__security_cookie
0x18000cfb3  xor     rax, rsp
0x18000cfb6  mov     [rbp+880h+var_50], rax
0x18000cfbd  mov     rax, [rbp+880h+ChangeFlags]
0x18000cfc4  xor     r12d, r12d
0x18000cfc7  mov     [rsp+980h+var_914], r8d
0x18000cfcc  mov     rsi, rdx
0x18000cfcf  mov     rbx, rcx
0x18000cfd2  mov     [rsp+980h+var_910], rax
0x18000cfd7  xor     edx, edx; Val
0x18000cfd9  mov     qword ptr [rsp+980h+uliInst], r12
0x18000cfde  mov     r8d, 7FCh; Size
0x18000cfe4  mov     [rsp+980h+pLength], r12d
0x18000cfe9  lea     rcx, [rbp+880h+var_84C]; void *
0x18000cfed  mov     [rbp+880h+var_850], r12d
0x18000cff1  mov     [rsp+980h+var_908], r9
0x18000cff6  call    memset_0
0x18000cffb  xor     eax, eax
0x18000cffd  mov     [rbp+880h+var_8D0], r12d
0x18000d001  xorps   xmm0, xmm0
0x18000d004  mov     [rbp+880h+var_8AC], eax
0x18000d007  mov     rax, rbx
0x18000d00a  mov     edi, 7754DF32h
0x18000d00f  xor     rax, rdi
0x18000d012  mov     [rbp+880h+var_900], rax
0x18000d016  movups  [rbp+880h+var_8CC], xmm0
0x18000d01a  movups  [rbp+880h+var_8BC], xmm0
0x18000d01e  movups  [rbp+880h+var_8E0], xmm0
0x18000d022  jz      loc_18000D88C
0x18000d028  cmp     dword ptr [rax+30h], 1
0x18000d02c  jz      loc_18000D88C
0x18000d032  xor     rsi, rdi
0x18000d035  jz      loc_18000D88C
0x18000d03b  cmp     byte ptr [rsi+48h], 2
0x18000d03f  jz      loc_18000D88C
0x18000d045  cmp     [rsi+38h], rbx
0x18000d049  jz      short loc_18000D055
0x18000d04b  lea     eax, [r12+5]
0x18000d050  jmp     loc_18000D891
0x18000d055  mov     r13, [rax+10h]
0x18000d059  lea     r8, [rsp+980h+uliInst]; uliInst
0x18000d05e  mov     r14, [rsi+30h]
0x18000d062  xor     edx, edx; lpPropSv
0x18000d064  mov     [rsp+980h+Parameter], r13
0x18000d069  mov     eax, [r13+28h]
0x18000d06d  and     [rsi+54h], eax
0x18000d070  mov     rcx, [r13+10h]
0x18000d074  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000d078  call    GetInstance
0x18000d07d  test    eax, eax
0x18000d07f  jnz     loc_18000D891
0x18000d085  mov     al, cs:byte_18002BD1A
0x18000d08b  xor     r14, rdi
0x18000d08e  mov     dil, 8
0x18000d091  and     al, dil
0x18000d094  mov     byte ptr [rsp+980h+var_918], al
0x18000d098  jz      loc_18000D2B9
0x18000d09e  mov     r15, qword ptr [rsp+980h+uliInst]
0x18000d0a3  lea     rax, [rbp+880h+var_8D0]
0x18000d0a7  mov     qword ptr [rsp+980h+Period], rax
0x18000d0ac  lea     r9, [rbp+880h+var_8E0]
0x18000d0b0  add     r15, 30h ; '0'
0x18000d0b4  mov     word ptr [rbp+880h+var_8D0], r12w
0x18000d0b9  lea     r8, aUpdatingRouteW; "Updating Route with address: "
0x18000d0c0  mov     qword ptr [rsp+980h+DueTime], r12
0x18000d0c5  cmovnz  r9, r15
0x18000d0c9  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000d0d0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d0d7  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d0dc  mov     bl, cs:byte_18002BD1A
0x18000d0e2  test    dil, bl
0x18000d0e5  jz      short loc_18000D14A
0x18000d0e7  mov     eax, r12d
0x18000d0ea  mov     word ptr [rbp+880h+var_850], r12w
0x18000d0ef  mov     r9, rsi
0x18000d0f2  mov     word ptr [rbp+880h+var_8D0], ax
0x18000d0f6  mov     r8, r14
0x18000d0f9  lea     rdx, aDestPAndRouteP; "Dest = %p and Route = %p\n"
0x18000d100  lea     rcx, [rbp+880h+var_850]
0x18000d104  call    FormatRRASErrorString
0x18000d109  mov     bl, cs:byte_18002BD1A
0x18000d10f  test    dil, bl
0x18000d112  jz      short loc_18000D14A
0x18000d114  test    r15, r15
0x18000d117  lea     rax, [rbp+880h+var_8D0]
0x18000d11b  mov     qword ptr [rsp+980h+Period], rax
0x18000d120  lea     r9, [rbp+880h+var_8E0]
0x18000d124  cmovnz  r9, r15
0x18000d128  mov     qword ptr [rsp+980h+DueTime], r12
0x18000d12d  lea     r8, [rbp+880h+var_850]
0x18000d131  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000d138  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d13f  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d144  mov     bl, cs:byte_18002BD1A
0x18000d14a  cmp     word ptr [r14+50h], 17h
0x18000d150  jnz     loc_18000D209
0x18000d156  xor     edx, edx; Val
0x18000d158  lea     rcx, [rbp+880h+S]; void *
0x18000d15c  xorps   xmm0, xmm0
0x18000d15f  movups  xmmword ptr [rbp+880h+pAddress.u], xmm0
0x18000d163  lea     r8d, [rdx+41h]; Size
0x18000d167  call    memset_0
0x18000d16c  mov     r9d, 10h; dwAddressSize
0x18000d172  lea     r8, [rsp+980h+pLength]; pLength
0x18000d177  lea     rdx, [rbp+880h+pAddress]; pAddress
0x18000d17b  lea     rcx, [r14+50h]; pNetAddress
0x18000d17f  call    RtmConvertNetAddressToIpv6AddressAndLength
0x18000d184  test    dil, bl
0x18000d187  jz      loc_18000D2B9
0x18000d18d  movaps  xmm0, xmmword ptr [rbp+880h+pAddress.u]
0x18000d191  lea     rdx, [rbp+880h+S]; S
0x18000d195  lea     rcx, [rbp+880h+pAddress]; Addr
0x18000d199  movdqa  xmmword ptr [rbp+880h+pAddress.u], xmm0
0x18000d19e  mov     word ptr [rbp+880h+var_850], r12w
0x18000d1a3  mov     word ptr [rbp+880h+var_8D0], r12w
0x18000d1a8  call    cs:__imp_RtlIpv6AddressToStringA
0x18000d1ae  mov     r9d, [rsp+980h+pLength]
0x18000d1b3  lea     r8, [rbp+880h+S]
0x18000d1b7  lea     rdx, aAddressIsSMask; "address is %S  mask %d"
0x18000d1be  lea     rcx, [rbp+880h+var_850]
0x18000d1c2  call    FormatRRASErrorString
0x18000d1c7  test    cs:byte_18002BD1A, dil
0x18000d1ce  jz      loc_18000D2B9
0x18000d1d4  test    r15, r15
0x18000d1d7  lea     rax, [rbp+880h+var_8D0]
0x18000d1db  mov     qword ptr [rsp+980h+Period], rax
0x18000d1e0  lea     r9, [rbp+880h+var_8E0]
0x18000d1e4  cmovnz  r9, r15
0x18000d1e8  mov     qword ptr [rsp+980h+DueTime], r12
0x18000d1ed  lea     r8, [rbp+880h+var_850]
0x18000d1f1  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000d1f8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d1ff  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d204  jmp     loc_18000D2B9
0x18000d209  movzx   eax, word ptr [r14+52h]
0x18000d20e  xor     edx, edx
0x18000d210  mov     r12d, [r14+54h]
0x18000d214  test    ax, ax
0x18000d217  jz      short loc_18000D237
0x18000d219  lea     ecx, [rdx+20h]
0x18000d21c  sub     ecx, eax
0x18000d21e  or      eax, 0FFFFFFFFh
0x18000d221  shl     eax, cl
0x18000d223  mov     ecx, eax; hostlong
0x18000d225  call    cs:__imp_htonl
0x18000d22b  mov     bl, cs:byte_18002BD1A
0x18000d231  xor     edx, edx
0x18000d233  mov     ecx, eax
0x18000d235  jmp     short loc_18000D239
0x18000d237  mov     ecx, edx
0x18000d239  test    dil, bl
0x18000d23c  jz      short loc_18000D2B6
0x18000d23e  mov     eax, ecx
0x18000d240  mov     word ptr [rbp+880h+var_850], dx
0x18000d244  shr     eax, 10h
0x18000d247  mov     edi, ecx
0x18000d249  movzx   ebx, al
0x18000d24c  mov     r10d, r12d
0x18000d24f  mov     eax, ecx
0x18000d251  mov     word ptr [rbp+880h+var_8D0], dx
0x18000d255  shr     eax, 8
0x18000d258  movzx   r11d, al
0x18000d25c  mov     eax, r12d
0x18000d25f  movzx   edx, cl
0x18000d262  shr     eax, 10h
0x18000d265  movzx   ecx, al
0x18000d268  mov     eax, r12d
0x18000d26b  shr     r10d, 18h
0x18000d26f  shr     eax, 8
0x18000d272  shr     edi, 18h
0x18000d275  mov     [rsp+980h+var_938], edi
0x18000d279  mov     [rsp+980h+var_940], ebx
0x18000d27d  mov     [rsp+980h+var_948], r11d
0x18000d282  mov     [rsp+980h+Flags], edx
0x18000d286  lea     rdx, aDestDDDDMaskDD; "Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d"
0x18000d28d  mov     [rsp+980h+Period], r10d
0x18000d292  mov     [rsp+980h+DueTime], ecx
0x18000d296  lea     rcx, [rbp+880h+var_850]
0x18000d29a  movzx   r9d, al
0x18000d29e  movzx   r8d, r12b
0x18000d2a2  call    FormatRRASErrorString
0x18000d2a7  xor     r12d, r12d
0x18000d2aa  test    cs:byte_18002BD1A, 8
0x18000d2b1  jmp     loc_18000D1CE
0x18000d2b6  xor     r12d, r12d
0x18000d2b9  mov     rax, [rsp+980h+var_910]
0x18000d2be  lea     r15, [r14+38h]
0x18000d2c2  mov     [rax], r12d
0x18000d2c5  mov     rax, [rsi+10h]
0x18000d2c9  cmp     rax, r15
0x18000d2cc  jz      loc_18000D355
0x18000d2d2  mov     ecx, [rax+48h]
0x18000d2d5  cmp     ecx, [rsi+50h]
0x18000d2d8  jb      short loc_18000D355
0x18000d2da  ja      short loc_18000D2E4
0x18000d2dc  mov     ecx, [rax+44h]
0x18000d2df  cmp     ecx, [rsi+4Ch]
0x18000d2e2  jbe     short loc_18000D355
0x18000d2e4  lea     rcx, [rsi+8]
0x18000d2e8  mov     rdx, [rcx]
0x18000d2eb  cmp     [rdx+8], rcx
0x18000d2ef  jnz     loc_18000D788
0x18000d2f5  mov     r8, [rcx+8]
0x18000d2f9  cmp     [r8], rcx
0x18000d2fc  jnz     loc_18000D788
0x18000d302  mov     [r8], rdx
0x18000d305  mov     [rdx+8], r8
0x18000d309  mov     rax, [rax+8]
0x18000d30d  cmp     rax, r15
0x18000d310  jz      short loc_18000D32F
0x18000d312  mov     r8d, [rsi+50h]
0x18000d316  cmp     [rax+48h], r8d
0x18000d31a  jb      short loc_18000D32F
0x18000d31c  ja      short loc_18000D326
0x18000d31e  mov     edx, [rax+44h]
0x18000d321  cmp     edx, [rsi+4Ch]
0x18000d324  jbe     short loc_18000D32F
0x18000d326  mov     rax, [rax+8]
0x18000d32a  cmp     rax, r15
0x18000d32d  jnz     short loc_18000D316
0x18000d32f  mov     rdx, [rax]
0x18000d332  cmp     [rdx+8], rax
0x18000d336  jnz     loc_18000D788
0x18000d33c  mov     [rcx], rdx
0x18000d33f  mov     r9d, 1
0x18000d345  mov     [rcx+8], rax
0x18000d349  mov     [rdx+8], rcx
0x18000d34d  mov     [rax], rcx
0x18000d350  jmp     loc_18000D3D7
0x18000d355  lea     rdx, [rsi+8]
0x18000d359  mov     r9d, r12d
0x18000d35c  mov     rcx, [rdx]
0x18000d35f  cmp     rcx, r15
0x18000d362  jz      short loc_18000D3D7
0x18000d364  mov     eax, [rcx+48h]
0x18000d367  cmp     eax, [rsi+50h]
0x18000d36a  jb      short loc_18000D376
0x18000d36c  ja      short loc_18000D3D7
0x18000d36e  mov     eax, [rsi+4Ch]
0x18000d371  cmp     [rcx+44h], eax
0x18000d374  jnb     short loc_18000D3D7
0x18000d376  cmp     [rcx+8], rdx
0x18000d37a  jnz     loc_18000D788
0x18000d380  mov     rax, [rdx+8]
0x18000d384  cmp     [rax], rdx
0x18000d387  jnz     loc_18000D788
0x18000d38d  mov     [rax], rcx
0x18000d390  mov     [rcx+8], rax
0x18000d394  mov     rcx, [rcx]
0x18000d397  cmp     rcx, r15
0x18000d39a  jz      short loc_18000D3B8
0x18000d39c  mov     r8d, [rsi+50h]
0x18000d3a0  cmp     [rcx+48h], r8d
0x18000d3a4  jb      short loc_18000D3B0
0x18000d3a6  ja      short loc_18000D3B8
0x18000d3a8  mov     eax, [rsi+4Ch]
0x18000d3ab  cmp     [rcx+44h], eax
0x18000d3ae  jnb     short loc_18000D3B8
0x18000d3b0  mov     rcx, [rcx]
0x18000d3b3  cmp     rcx, r15
0x18000d3b6  jnz     short loc_18000D3A0
0x18000d3b8  mov     rax, [rcx+8]
0x18000d3bc  cmp     [rax], rcx
0x18000d3bf  jnz     loc_18000D788
0x18000d3c5  mov     [rdx], rcx
0x18000d3c8  or      r9d, 0FFFFFFFFh
0x18000d3cc  mov     [rdx+8], rax
0x18000d3d0  mov     [rax], rdx
0x18000d3d3  mov     [rcx+8], rdx
0x18000d3d7  mov     eax, [r14+70h]
0x18000d3db  mov     r10d, r12d
0x18000d3de  mov     [rsp+980h+var_918], eax
0x18000d3e2  mov     r8d, eax
0x18000d3e5  mov     [rsp+980h+uliInst], r12d
0x18000d3ea  mov     edx, r12d
0x18000d3ed  test    eax, eax
0x18000d3ef  jz      short loc_18000D43C
0x18000d3f1  cmp     edx, 20h ; ' '
0x18000d3f4  jnb     short loc_18000D437
0x18000d3f6  test    r8b, 1
0x18000d3fa  jz      short loc_18000D430
0x18000d3fc  mov     eax, edx
0x18000d3fe  movsxd  rcx, dword ptr [r13+rax*4+0B0h]
0x18000d406  lea     rax, [rcx+rcx*2]
0x18000d40a  mov     rcx, [r14+rax*8+80h]
0x18000d412  jmp     short loc_18000D41D
0x18000d414  cmp     [rcx], rsi
0x18000d417  jz      short loc_18000D424
0x18000d419  mov     rcx, [rcx+8]
0x18000d41d  test    rcx, rcx
  ... truncated ...
```
