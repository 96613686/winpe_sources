# RtmDeleteRouteToDest

- ea: `0x18000c560`
- end: `0x18000cdb5`
- name: `RtmDeleteRouteToDest`
- size: `2133`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ROUTE_HANDLE RouteHandle, PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ebc`
- `0x18000d8c0`

## callees

- `0x180001de0`
- `0x1800027d8`
- `0x180002bec`
- `0x180002cb0`
- `0x180009d14`
- `0x18000a298`
- `0x18000b224`
- `0x18000b3bc`
- `0x18000c560`
- `0x18000dc60`
- `0x180014d2c`
- `0x180015178`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000c8dd`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c8dd`
- `ntdll!RtlReleaseResource` at `0x18000c8f6`
- `ntdll!RtlReleaseResource` at `0x18000c997`
- `ntdll!RtlReleaseResource` at `0x18000cc4b`
- `ntdll!RtlReleaseResource` at `0x18000cd78`
- `ntdll!RtlReleaseResource` at `0x18000c8f6`
- `ntdll!RtlReleaseResource` at `0x18000c997`
- `ntdll!RtlReleaseResource` at `0x18000cc4b`
- `ntdll!RtlReleaseResource` at `0x18000cd78`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c6ed`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000c6ed`
- `ntdll!RtlAcquireResourceShared` at `0x18000cc1f`
- `ntdll!RtlAcquireResourceShared` at `0x18000cc1f`
- `KERNEL32!HeapAlloc` at `0x18000cc75`
- `KERNEL32!HeapAlloc` at `0x18000cc75`
- `KERNEL32!GetProcessHeap` at `0x18000cc66`
- `KERNEL32!GetProcessHeap` at `0x18000ccca`
- `KERNEL32!GetProcessHeap` at `0x18000cd0b`
- `KERNEL32!GetProcessHeap` at `0x18000cc66`
- `KERNEL32!GetProcessHeap` at `0x18000ccca`
- `KERNEL32!GetProcessHeap` at `0x18000cd0b`
- `KERNEL32!HeapFree` at `0x18000ccd8`
- `KERNEL32!HeapFree` at `0x18000cd19`
- `KERNEL32!HeapFree` at `0x18000ccd8`
- `KERNEL32!HeapFree` at `0x18000cd19`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ccab`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ccab`
- `KERNEL32!GetLastError` at `0x18000ccbb`
- `KERNEL32!GetLastError` at `0x18000ccbb`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000cd01`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000cd01`
- `WS2_32!__imp_htonl` at `0x18000c76a`
- `WS2_32!__imp_htonl` at `0x18000c76a`

## pseudocode

```c
DWORD __stdcall RtmDeleteRouteToDest(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_ROUTE_HANDLE RouteHandle,
        PRTM_ROUTE_CHANGE_FLAGS ChangeFlags)
{
  PRTM_ROUTE_CHANGE_FLAGS v3; // r13
  unsigned __int64 v6; // rsi
  DWORD result; // eax
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 v10; // r14
  __int128 *v11; // r9
  __int64 v12; // r12
  __int128 *v13; // r9
  __int16 v14; // ax
  unsigned int v15; // r13d
  u_long v16; // ecx
  __int128 *v17; // r9
  __int128 *v18; // r9
  int v19; // ebx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  int v22; // edx
  unsigned int v23; // r8d
  DWORD v24; // r12d
  unsigned int i; // edx
  _QWORD *j; // rcx
  __int64 v27; // r13
  DWORD v28; // ebx
  DWORD v29; // edi
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned int v32; // eax
  __int64 *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rdx
  _QWORD *m; // rdi
  _DWORD *v37; // rdi
  __int64 v38; // rax
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // ecx
  DWORD v44; // ecx
  DWORD v45; // edi
  unsigned int k; // edx
  __int64 v47; // r8
  int v48; // ebx
  HANDLE *v49; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v51; // rax
  void *v52; // rdi
  HANDLE v53; // rax
  HANDLE v54; // rax
  DWORD DueTime[2]; // [rsp+20h] [rbp-E0h]
  DWORD Period[2]; // [rsp+28h] [rbp-D8h]
  DWORD pLength; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v58; // [rsp+58h] [rbp-A8h]
  PRTM_ROUTE_CHANGE_FLAGS v59; // [rsp+60h] [rbp-A0h]
  ULONG uliInst[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v61; // [rsp+80h] [rbp-80h] BYREF
  int v62; // [rsp+90h] [rbp-70h] BYREF
  __int128 v63; // [rsp+94h] [rbp-6Ch]
  __int128 v64; // [rsp+A4h] [rbp-5Ch]
  int v65; // [rsp+B4h] [rbp-4Ch]
  CHAR S[80]; // [rsp+C0h] [rbp-40h] BYREF
  int v67; // [rsp+110h] [rbp+10h] BYREF
  char v68[2044]; // [rsp+114h] [rbp+14h] BYREF

  v59 = ChangeFlags;
  v3 = ChangeFlags;
  *(_QWORD *)uliInst = 0;
  pLength = 0;
  v67 = 0;
  memset_0(v68, 0, sizeof(v68));
  v62 = 0;
  v65 = 0;
  v63 = 0;
  v64 = 0;
  v61 = 0;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v6 = (unsigned __int64)RouteHandle ^ 0x7754DF32;
  if ( !v6 || *(_BYTE *)(v6 + 72) == 2 )
    return 6;
  if ( *(RTM_ENTITY_HANDLE *)(v6 + 56) != RtmRegHandle )
    return 5;
  v8 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  v9 = *(_QWORD *)(v6 + 48);
  GetInstance((LPSPropValue)*(unsigned __int16 *)(*(_QWORD *)(v8 + 16) + 4LL), 0, (ULONG)uliInst);
  if ( !result )
  {
    v10 = v9 ^ 0x7754DF32;
    LOBYTE(v58) = byte_18002BD1A & 8;
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_31;
    v11 = &v61;
    v12 = *(_QWORD *)uliInst + 48LL;
    LOWORD(v62) = 0;
    if ( *(_QWORD *)uliInst != -48 )
      LODWORD(v11) = uliInst[0] + 48;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
      (unsigned int)L"Deleting Route with address: ",
      (_DWORD)v11,
      0,
      (__int64)&v62);
    if ( *(_WORD *)(v10 + 80) == 23 )
    {
      *(_OWORD *)uliInst = 0;
      memset_0(S, 0, 0x41u);
      RtmConvertNetAddressToIpv6AddressAndLength((PRTM_NET_ADDRESS)(v10 + 80), (PIN6_ADDR)uliInst, &pLength, 0x10u);
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_31;
      LOWORD(v67) = 0;
      LOWORD(v62) = 0;
      RtlIpv6AddressToStringA((const struct in6_addr *)uliInst, S);
      FormatRRASErrorString(&v67, L"address is %S  mask %d", S, pLength);
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_31;
      v13 = &v61;
      if ( v12 )
        LODWORD(v13) = v12;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)&v67,
        (_DWORD)v13,
        0,
        (__int64)&v62);
    }
    else
    {
      v14 = *(_WORD *)(v10 + 82);
      v15 = *(_DWORD *)(v10 + 84);
      if ( v14 )
        v16 = htonl(-1 << (32 - v14));
      else
        v16 = 0;
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v67) = 0;
        LOWORD(v62) = 0;
        Period[0] = HIBYTE(v15);
        DueTime[0] = BYTE2(v15);
        FormatRRASErrorString(
          &v67,
          L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
          (unsigned __int8)v15,
          BYTE1(v15),
          *(_QWORD *)DueTime,
          *(_QWORD *)Period,
          (unsigned __int8)v16,
          BYTE1(v16),
          BYTE2(v16),
          HIBYTE(v16));
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v17 = &v61;
          if ( v12 )
            LODWORD(v17) = v12;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v67,
            (_DWORD)v17,
            0,
            (__int64)&v62);
        }
      }
      v3 = v59;
    }
    if ( (byte_18002BD1A & 8) != 0 )
    {
      LOWORD(v67) = 0;
      LOWORD(v62) = 0;
      FormatRRASErrorString(&v67, L"Dest = %p and Route = %p\n", v10, v6);
      if ( (byte_18002BD1A & 8) != 0 )
      {
        v18 = &v61;
        if ( v12 )
          LODWORD(v18) = v12;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
          (unsigned int)&v67,
          (_DWORD)v18,
          0,
          (__int64)&v62);
      }
    }
LABEL_31:
    v19 = 0;
    AcquireWriteLock(v10 + 32);
    if ( *(_DWORD *)(v10 + 52) == 1 && !*(_WORD *)(v10 + 110) && (*(_DWORD *)(v10 + 116) & *(_DWORD *)(v6 + 84)) == 0 )
    {
      if ( *(_BYTE *)(v6 + 72) == 2 )
      {
LABEL_114:
        if ( v19 )
          RtlReleaseResource((PRTL_RESOURCE)(v8 + 608));
        ReleaseWriteLock(v10 + 32);
        return 6;
      }
      *(_BYTE *)(v6 + 72) = 1;
      ReleaseWriteLock(v10 + 32);
      v19 = 1;
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v8 + 608), 1u);
      AcquireWriteLock(v10 + 32);
      if ( *(_BYTE *)(v6 + 72) != 1 )
      {
        RtlReleaseResource((PRTL_RESOURCE)(v8 + 608));
        ReleaseWriteLock(v10 + 32);
        return 0;
      }
    }
    if ( *(_BYTE *)(v6 + 72) != 2 )
    {
      *(_BYTE *)(v6 + 72) = 2;
      v20 = *(_QWORD *)(v6 + 8);
      if ( *(_QWORD *)(v20 + 8) != v6 + 8 || (v21 = *(_QWORD **)(v6 + 16), *v21 != v6 + 8) )
        __fastfail(3u);
      *v21 = v20;
      *(_QWORD *)(v20 + 8) = v21;
      --*(_DWORD *)(v10 + 52);
      *v3 = 0;
      if ( v19 )
      {
        if ( !*(_DWORD *)(v10 + 52) && !*(_WORD *)(v10 + 110) && (*(_DWORD *)(v10 + 116) & *(_DWORD *)(v6 + 84)) == 0 )
        {
          v22 = *(unsigned __int16 *)(v10 + 82);
          *(_WORD *)(v10 + 108) = 1;
          DeleteFromTable(*(_QWORD *)(v8 + 712), v22, v10 + 84, 0, (__int64)uliInst);
          --*(_DWORD *)(v8 + 720);
        }
        RtlReleaseResource((PRTL_RESOURCE)(v8 + 608));
      }
      v23 = *(_DWORD *)(v6 + 84);
      v24 = 0;
      for ( i = 0; v23; v23 >>= 1 )
      {
        if ( i >= 0x20 )
          break;
        if ( (v23 & 1) != 0 )
        {
          for ( j = *(_QWORD **)(v10 + 24LL * *(int *)(v8 + 4LL * i + 176) + 128); j; j = (_QWORD *)j[1] )
          {
            if ( *j == v6 )
            {
              v24 |= 1 << i;
              break;
            }
          }
        }
        ++i;
      }
      v27 = 0;
      pLength = v24;
      v28 = v24;
      v29 = v24;
      if ( !v24 )
      {
LABEL_85:
        v44 = v28;
        v45 = 0;
        for ( k = 0; v44; v44 >>= 1 )
        {
          if ( k >= 0x20 )
            break;
          if ( (v44 & 1) != 0 )
          {
            v47 = *(unsigned int *)(v8 + 4LL * k + 176);
            if ( *(_DWORD *)(v10 + 24 * v47 + 144) )
            {
              if ( !*(_QWORD *)(v10 + 24 * v47 + 136) )
              {
                *(_QWORD *)(v10 + 24 * v47 + 136) = v6;
                _InterlockedAdd((volatile signed __int32 *)v6, 1u);
                if ( v45 < *(_DWORD *)(v10 + 24 * v47 + 144) )
                  v45 = *(_DWORD *)(v10 + 24 * v47 + 144);
              }
              *(_DWORD *)(v10 + 24 * v47 + 144) = 0;
            }
          }
          ++k;
        }
        v48 = ~v28;
        uliInst[2] = v24;
        *(_DWORD *)(v10 + 112) &= v48;
        *(_DWORD *)(v10 + 116) &= v48;
        uliInst[0] = *(_DWORD *)(v6 + 84);
        uliInst[1] = v24;
        if ( v24 )
          *v59 |= 0x10000u;
        RtlAcquireResourceShared((PRTL_RESOURCE)(v8 + 744), 1u);
        if ( (unsigned int)ComputeCNsToBeNotified(v8, *(unsigned int *)(v10 + 40), uliInst) )
          AddToChangedDestLists((PVOID)v8);
        RtlReleaseResource((PRTL_RESOURCE)(v8 + 744));
        v49 = *(HANDLE **)(v6 + 40);
        *(_QWORD *)(v6 + 40) = 0;
        if ( v45 )
        {
          ++*(_WORD *)(v10 + 110);
          ProcessHeap = GetProcessHeap();
          v51 = HeapAlloc(ProcessHeap, 0, 0x10u);
          *(_QWORD *)(v6 + 40) = v51;
          if ( v51 )
          {
            v51[1] = v6;
            if ( CreateTimerQueueTimer(
                   *(PHANDLE *)(v6 + 40),
                   *(HANDLE *)(v8 + 728),
                   RouteHolddownTimeoutCallback,
                   *(PVOID *)(v6 + 40),
                   v45,
                   0,
                   0) )
            {
              _InterlockedAdd((volatile signed __int32 *)v6, 1u);
            }
            else
            {
              GetLastError();
              v52 = *(void **)(v6 + 40);
              if ( v52 )
              {
                v53 = GetProcessHeap();
                HeapFree(v53, 0, v52);
              }
              *(_QWORD *)(v6 + 40) = 0;
            }
          }
        }
        ReleaseWriteLock(v10 + 32);
        if ( v49 )
        {
          if ( DeleteTimerQueueTimer(*(HANDLE *)(v8 + 728), *v49, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
          {
            v54 = GetProcessHeap();
            HeapFree(v54, 0, v49);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
              DestroyRoute((LPVOID)v6);
          }
        }
        _InterlockedAdd((volatile signed __int32 *)(v8 + 724), 0xFFFFFFFF);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
          DestroyRoute((LPVOID)v6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
          DestroyRoute((LPVOID)v6);
        return 0;
      }
      while ( 1 )
      {
        if ( (unsigned int)v27 >= 0x20 )
          goto LABEL_85;
        if ( (v29 & 1) != 0 )
        {
          v30 = *(int *)(v8 + 4 * v27 + 176);
          v31 = v30 + 2 * (v30 + 8);
          v32 = 0;
          v33 = (__int64 *)(v10 + 8 * v31);
          v34 = *v33;
          if ( *v33 )
          {
            do
            {
              v34 = *(_QWORD *)(v34 + 8);
              ++v32;
            }
            while ( v34 );
            if ( v32 > 1 )
            {
              DeleteRouteFromRouteList(v33, v6);
              goto LABEL_64;
            }
            if ( v32 == 1 )
              break;
          }
        }
LABEL_84:
        v29 >>= 1;
        v27 = (unsigned int)(v27 + 1);
        pLength = v29;
        if ( !v29 )
          goto LABEL_85;
      }
      *(_QWORD *)uliInst = 0;
      DeleteRouteFromRouteList(v33, v6);
      v35 = v10 + 56;
      for ( m = *(_QWORD **)(v10 + 56); ; m = (_QWORD *)*v58 )
      {
        v58 = m;
        if ( m == (_QWORD *)v35 )
        {
          v42 = *(_QWORD *)(v10 + 24LL * *(int *)(v8 + 4 * v27 + 176) + 128);
          v43 = 0;
          if ( v42 )
          {
            do
            {
              v42 = *(_QWORD *)(v42 + 8);
              ++v43;
            }
            while ( v42 );
            v29 = pLength;
            if ( v43 )
LABEL_64:
              v28 &= ~(1 << v27);
          }
          else
          {
            v29 = pLength;
          }
          goto LABEL_84;
        }
        v37 = m - 1;
        if ( (v28 & v37[21]) != 0 )
        {
          if ( !*(_QWORD *)uliInst )
          {
            v38 = *(int *)(v8 + 4 * v27 + 176);
            result = InsertInRouteList(v10 + 8 * (v38 + 2 * (v38 + 8)), v37);
            if ( result )
              return result;
            *(_QWORD *)uliInst = v37;
LABEL_76:
            v35 = v10 + 56;
            continue;
          }
          v39 = *(_DWORD *)(*(_QWORD *)uliInst + 80LL);
          if ( v39 >= v37[20] && v39 <= v37[20] )
          {
            v40 = *(_DWORD *)(*(_QWORD *)uliInst + 76LL);
            if ( v40 >= v37[19] && v40 <= v37[19] )
            {
              v41 = *(int *)(v8 + 4 * v27 + 176);
              result = InsertInRouteList(v10 + 8 * (v41 + 2 * (v41 + 8)), v37);
              if ( result )
                return result;
              goto LABEL_76;
            }
          }
        }
      }
    }
    goto LABEL_114;
  }
  return result;
}

```

## disassembly

```asm
0x18000c560  mov     [rsp-8+arg_18], rbx
0x18000c565  push    rbp
0x18000c566  push    rsi
0x18000c567  push    rdi
0x18000c568  push    r12
0x18000c56a  push    r13
0x18000c56c  push    r14
0x18000c56e  push    r15
0x18000c570  lea     rbp, [rsp-820h]
0x18000c578  sub     rsp, 920h
0x18000c57f  mov     rax, cs:__security_cookie
0x18000c586  xor     rax, rsp
0x18000c589  mov     [rbp+850h+var_40], rax
0x18000c590  xor     edi, edi
0x18000c592  mov     [rsp+950h+var_8F0], r8
0x18000c597  mov     r13, r8
0x18000c59a  mov     qword ptr [rsp+950h+uliInst], rdi
0x18000c59f  mov     rsi, rdx
0x18000c5a2  mov     [rsp+950h+pLength], edi
0x18000c5a6  mov     rbx, rcx
0x18000c5a9  mov     [rbp+850h+var_840], edi
0x18000c5ac  xor     edx, edx; Val
0x18000c5ae  lea     rcx, [rbp+850h+var_83C]; void *
0x18000c5b2  mov     r8d, 7FCh; Size
0x18000c5b8  call    memset_0
0x18000c5bd  xorps   xmm0, xmm0
0x18000c5c0  mov     [rbp+850h+var_8C0], edi
0x18000c5c3  xor     eax, eax
0x18000c5c5  mov     r15, rbx
0x18000c5c8  mov     r12d, 7754DF32h
0x18000c5ce  mov     [rbp+850h+var_89C], eax
0x18000c5d1  xor     r15, r12
0x18000c5d4  movups  [rbp+850h+var_8BC], xmm0
0x18000c5d8  movups  [rbp+850h+var_8AC], xmm0
0x18000c5dc  movups  [rbp+850h+var_8D0], xmm0
0x18000c5e0  jz      loc_18000CD86
0x18000c5e6  cmp     dword ptr [r15+30h], 1
0x18000c5eb  jz      loc_18000CD86
0x18000c5f1  xor     rsi, r12
0x18000c5f4  jz      loc_18000CD86
0x18000c5fa  cmp     byte ptr [rsi+48h], 2
0x18000c5fe  jz      loc_18000CD86
0x18000c604  cmp     [rsi+38h], rbx
0x18000c608  jz      short loc_18000C612
0x18000c60a  lea     eax, [rdi+5]
0x18000c60d  jmp     loc_18000CD8B
0x18000c612  mov     r15, [r15+10h]
0x18000c616  lea     r8, [rsp+950h+uliInst]; uliInst
0x18000c61b  mov     r14, [rsi+30h]
0x18000c61f  xor     edx, edx; lpPropSv
0x18000c621  mov     rcx, [r15+10h]
0x18000c625  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000c629  call    GetInstance
0x18000c62e  test    eax, eax
0x18000c630  jnz     loc_18000CD8B
0x18000c636  mov     al, cs:byte_18002BD1A
0x18000c63c  xor     r14, r12
0x18000c63f  and     al, 8
0x18000c641  mov     byte ptr [rsp+950h+var_8F8], al
0x18000c645  jz      loc_18000C88C
0x18000c64b  mov     r12, qword ptr [rsp+950h+uliInst]
0x18000c650  lea     rax, [rbp+850h+var_8C0]
0x18000c654  mov     qword ptr [rsp+950h+Period], rax
0x18000c659  lea     r9, [rbp+850h+var_8D0]
0x18000c65d  add     r12, 30h ; '0'
0x18000c661  mov     word ptr [rbp+850h+var_8C0], di
0x18000c665  lea     r8, aDeletingRouteW; "Deleting Route with address: "
0x18000c66c  mov     qword ptr [rsp+950h+DueTime], rdi
0x18000c671  cmovnz  r9, r12
0x18000c675  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000c67c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c683  call    McTemplateU0zjzz_EventWriteTransfer
0x18000c688  cmp     word ptr [r14+50h], 17h
0x18000c68e  jnz     loc_18000C74E
0x18000c694  xor     edx, edx; Val
0x18000c696  lea     rcx, [rbp+850h+S]; void *
0x18000c69a  xorps   xmm0, xmm0
0x18000c69d  movups  xmmword ptr [rsp+950h+uliInst], xmm0
0x18000c6a2  lea     r8d, [rdx+41h]; Size
0x18000c6a6  call    memset_0
0x18000c6ab  mov     r9d, 10h; dwAddressSize
0x18000c6b1  lea     r8, [rsp+950h+pLength]; pLength
0x18000c6b6  lea     rdx, [rsp+950h+uliInst]; pAddress
0x18000c6bb  lea     rcx, [r14+50h]; pNetAddress
0x18000c6bf  call    RtmConvertNetAddressToIpv6AddressAndLength
0x18000c6c4  test    cs:byte_18002BD1A, 8
0x18000c6cb  jz      loc_18000C88C
0x18000c6d1  movaps  xmm0, xmmword ptr [rsp+950h+uliInst]
0x18000c6d6  lea     rdx, [rbp+850h+S]; S
0x18000c6da  lea     rcx, [rsp+950h+uliInst]; Addr
0x18000c6df  movdqa  xmmword ptr [rsp+950h+uliInst], xmm0
0x18000c6e5  mov     word ptr [rbp+850h+var_840], di
0x18000c6e9  mov     word ptr [rbp+850h+var_8C0], di
0x18000c6ed  call    cs:__imp_RtlIpv6AddressToStringA
0x18000c6f3  mov     r9d, [rsp+950h+pLength]
0x18000c6f8  lea     r8, [rbp+850h+S]
0x18000c6fc  lea     rdx, aAddressIsSMask; "address is %S  mask %d"
0x18000c703  lea     rcx, [rbp+850h+var_840]
0x18000c707  call    FormatRRASErrorString
0x18000c70c  test    cs:byte_18002BD1A, 8
0x18000c713  jz      loc_18000C88C
0x18000c719  test    r12, r12
0x18000c71c  lea     rax, [rbp+850h+var_8C0]
0x18000c720  mov     qword ptr [rsp+950h+Period], rax
0x18000c725  lea     r9, [rbp+850h+var_8D0]
0x18000c729  cmovnz  r9, r12
0x18000c72d  mov     qword ptr [rsp+950h+DueTime], rdi
0x18000c732  lea     r8, [rbp+850h+var_840]
0x18000c736  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000c73d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c744  call    McTemplateU0zjzz_EventWriteTransfer
0x18000c749  jmp     loc_18000C82C
0x18000c74e  movzx   eax, word ptr [r14+52h]
0x18000c753  mov     r13d, [r14+54h]
0x18000c757  test    ax, ax
0x18000c75a  jz      short loc_18000C774
0x18000c75c  mov     ecx, 20h ; ' '
0x18000c761  sub     ecx, eax
0x18000c763  or      eax, 0FFFFFFFFh
0x18000c766  shl     eax, cl
0x18000c768  mov     ecx, eax; hostlong
0x18000c76a  call    cs:__imp_htonl
0x18000c770  mov     ecx, eax
0x18000c772  jmp     short loc_18000C776
0x18000c774  mov     ecx, edi
0x18000c776  test    cs:byte_18002BD1A, 8
0x18000c77d  jz      loc_18000C827
0x18000c783  movzx   edx, cl
0x18000c786  mov     eax, ecx
0x18000c788  shr     eax, 10h
0x18000c78b  mov     r10d, r13d
0x18000c78e  movzx   ebx, al
0x18000c791  mov     eax, ecx
0x18000c793  shr     eax, 8
0x18000c796  movzx   r11d, al
0x18000c79a  mov     eax, r13d
0x18000c79d  shr     eax, 10h
0x18000c7a0  mov     word ptr [rbp+850h+var_840], di
0x18000c7a4  mov     word ptr [rbp+850h+var_8C0], di
0x18000c7a8  mov     edi, ecx
0x18000c7aa  movzx   ecx, al
0x18000c7ad  mov     eax, r13d
0x18000c7b0  shr     r10d, 18h
0x18000c7b4  shr     eax, 8
0x18000c7b7  shr     edi, 18h
0x18000c7ba  mov     [rsp+950h+var_908], edi
0x18000c7be  mov     [rsp+950h+var_910], ebx
0x18000c7c2  mov     [rsp+950h+var_918], r11d
0x18000c7c7  mov     [rsp+950h+Flags], edx
0x18000c7cb  lea     rdx, aDestDDDDMaskDD; "Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d"
0x18000c7d2  mov     [rsp+950h+Period], r10d
0x18000c7d7  mov     [rsp+950h+DueTime], ecx
0x18000c7db  lea     rcx, [rbp+850h+var_840]
0x18000c7df  movzx   r9d, al
0x18000c7e3  movzx   r8d, r13b
0x18000c7e7  call    FormatRRASErrorString
0x18000c7ec  xor     edi, edi
0x18000c7ee  test    cs:byte_18002BD1A, 8
0x18000c7f5  jz      short loc_18000C827
0x18000c7f7  test    r12, r12
0x18000c7fa  lea     rax, [rbp+850h+var_8C0]
0x18000c7fe  mov     qword ptr [rsp+950h+Period], rax
0x18000c803  lea     r9, [rbp+850h+var_8D0]
0x18000c807  cmovnz  r9, r12
0x18000c80b  mov     qword ptr [rsp+950h+DueTime], rdi
0x18000c810  lea     r8, [rbp+850h+var_840]
0x18000c814  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000c81b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c822  call    McTemplateU0zjzz_EventWriteTransfer
0x18000c827  mov     r13, [rsp+950h+var_8F0]
0x18000c82c  test    cs:byte_18002BD1A, 8
0x18000c833  jz      short loc_18000C88C
0x18000c835  mov     r9, rsi
0x18000c838  mov     word ptr [rbp+850h+var_840], di
0x18000c83c  mov     r8, r14
0x18000c83f  mov     word ptr [rbp+850h+var_8C0], di
0x18000c843  lea     rdx, aDestPAndRouteP; "Dest = %p and Route = %p\n"
0x18000c84a  lea     rcx, [rbp+850h+var_840]
0x18000c84e  call    FormatRRASErrorString
0x18000c853  test    cs:byte_18002BD1A, 8
0x18000c85a  jz      short loc_18000C88C
0x18000c85c  test    r12, r12
0x18000c85f  lea     rax, [rbp+850h+var_8C0]
0x18000c863  mov     qword ptr [rsp+950h+Period], rax
0x18000c868  lea     r9, [rbp+850h+var_8D0]
0x18000c86c  cmovnz  r9, r12
0x18000c870  mov     qword ptr [rsp+950h+DueTime], rdi
0x18000c875  lea     r8, [rbp+850h+var_840]
0x18000c879  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000c880  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c887  call    McTemplateU0zjzz_EventWriteTransfer
0x18000c88c  lea     r12, [r14+20h]
0x18000c890  mov     ebx, edi
0x18000c892  mov     rcx, r12
0x18000c895  call    AcquireWriteLock
0x18000c89a  mov     r8d, 1
0x18000c8a0  cmp     [r14+34h], r8d
0x18000c8a4  jnz     short loc_18000C90D
0x18000c8a6  cmp     [r14+6Eh], di
0x18000c8ab  jnz     short loc_18000C90D
0x18000c8ad  mov     eax, [r14+74h]
0x18000c8b1  test    [rsi+54h], eax
0x18000c8b4  jnz     short loc_18000C90D
0x18000c8b6  cmp     byte ptr [rsi+48h], 2
0x18000c8ba  jz      loc_18000CD6D
0x18000c8c0  mov     rcx, r12
0x18000c8c3  mov     [rsi+48h], r8b
0x18000c8c7  call    ReleaseWriteLock
0x18000c8cc  mov     ebx, 1
0x18000c8d1  lea     rdi, [r15+260h]
0x18000c8d8  mov     dl, bl; Wait
0x18000c8da  mov     rcx, rdi; Resource
0x18000c8dd  call    cs:__imp_RtlAcquireResourceExclusive
0x18000c8e3  mov     rcx, r12
0x18000c8e6  call    AcquireWriteLock
0x18000c8eb  mov     r8d, ebx
0x18000c8ee  cmp     [rsi+48h], bl
0x18000c8f1  jz      short loc_18000C90B
0x18000c8f3  mov     rcx, rdi; Resource
0x18000c8f6  call    cs:__imp_RtlReleaseResource
0x18000c8fc  mov     rcx, r12
0x18000c8ff  call    ReleaseWriteLock
0x18000c904  xor     eax, eax
0x18000c906  jmp     loc_18000CD8B
0x18000c90b  xor     edi, edi
0x18000c90d  cmp     byte ptr [rsi+48h], 2
0x18000c911  jz      loc_18000CD6D
0x18000c917  lea     rax, [rsi+8]
0x18000c91b  mov     byte ptr [rsi+48h], 2
0x18000c91f  mov     rdx, [rax]
0x18000c922  cmp     [rdx+8], rax
0x18000c926  jnz     loc_18000CD66
0x18000c92c  mov     rcx, [rax+8]
0x18000c930  cmp     [rcx], rax
0x18000c933  jnz     loc_18000CD66
0x18000c939  mov     [rcx], rdx
0x18000c93c  mov     [rdx+8], rcx
0x18000c940  dec     dword ptr [r14+34h]
0x18000c944  mov     [r13+0], edi
0x18000c948  test    ebx, ebx
0x18000c94a  jz      short loc_18000C99D
0x18000c94c  cmp     [r14+34h], edi
0x18000c950  jnz     short loc_18000C990
0x18000c952  cmp     [r14+6Eh], di
0x18000c957  jnz     short loc_18000C990
0x18000c959  mov     eax, [r14+74h]
0x18000c95d  test    [rsi+54h], eax
0x18000c960  jnz     short loc_18000C990
0x18000c962  movzx   edx, word ptr [r14+52h]
0x18000c967  lea     rax, [rsp+950h+uliInst]
0x18000c96c  mov     [r14+6Ch], r8w
0x18000c971  xor     r9d, r9d
0x18000c974  mov     rcx, [r15+2C8h]
0x18000c97b  lea     r8, [r14+54h]
0x18000c97f  mov     qword ptr [rsp+950h+DueTime], rax
0x18000c984  call    DeleteFromTable
0x18000c989  dec     dword ptr [r15+2D0h]
0x18000c990  lea     rcx, [r15+260h]; Resource
0x18000c997  call    cs:__imp_RtlReleaseResource
0x18000c99d  mov     r8d, [rsi+54h]
0x18000c9a1  mov     r12d, edi
0x18000c9a4  mov     edx, edi
0x18000c9a6  test    r8d, r8d
0x18000c9a9  jz      short loc_18000C9F5
0x18000c9ab  mov     r9d, 1
0x18000c9b1  cmp     edx, 20h ; ' '
0x18000c9b4  jnb     short loc_18000C9F5
0x18000c9b6  test    r9b, r8b
0x18000c9b9  jz      short loc_18000C9ED
0x18000c9bb  mov     eax, edx
0x18000c9bd  movsxd  rcx, dword ptr [r15+rax*4+0B0h]
0x18000c9c5  lea     rax, [rcx+rcx*2]
0x18000c9c9  mov     rcx, [r14+rax*8+80h]
0x18000c9d1  jmp     short loc_18000C9DC
0x18000c9d3  cmp     [rcx], rsi
0x18000c9d6  jz      short loc_18000C9E3
0x18000c9d8  mov     rcx, [rcx+8]
0x18000c9dc  test    rcx, rcx
0x18000c9df  jnz     short loc_18000C9D3
0x18000c9e1  jmp     short loc_18000C9ED
0x18000c9e3  mov     ecx, edx
0x18000c9e5  mov     eax, r9d
0x18000c9e8  shl     eax, cl
0x18000c9ea  or      r12d, eax
0x18000c9ed  add     edx, r9d
0x18000c9f0  shr     r8d, 1
0x18000c9f3  jnz     short loc_18000C9B1
0x18000c9f5  xor     r13d, r13d
0x18000c9f8  mov     [rsp+950h+pLength], r12d
0x18000c9fd  mov     ebx, r12d
0x18000ca00  mov     edi, r12d
0x18000ca03  test    r12d, r12d
0x18000ca06  jz      loc_18000CB74
0x18000ca0c  lea     r8d, [r13+1]
0x18000ca10  cmp     r13d, 20h ; ' '
0x18000ca14  jnb     loc_18000CB74
0x18000ca1a  test    r8b, dil
0x18000ca1d  jz      loc_18000CB63
0x18000ca23  movsxd  rax, dword ptr [r15+r13*4+0B0h]
0x18000ca2b  lea     rcx, [rax+8]
  ... truncated ...
```
