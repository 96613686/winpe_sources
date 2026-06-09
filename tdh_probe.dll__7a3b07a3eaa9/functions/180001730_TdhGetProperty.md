# TdhGetProperty

- ea: `0x180001730`
- end: `0x180001f2e`
- name: `TdhGetProperty`
- size: `2046`
- prototype: `TDHSTATUS __stdcall(PEVENT_RECORD pEvent, ULONG TdhContextCount, PTDH_CONTEXT pTdhContext, ULONG PropertyDataCount, PPROPERTY_DATA_DESCRIPTOR pPropertyData, ULONG BufferSize, PBYTE pBuffer)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001730`
- `0x180001f40`
- `0x180003940`
- `0x180004fb0`
- `0x1800059e8`
- `0x180006660`
- `0x180007720`
- `0x180012470`
- `0x180016df4`
- `0x1800207c0`
- `0x180024318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000181b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800019c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001abb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000181b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800019c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001abb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000189b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800018e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001c6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001d72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000189b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800018e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001c6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001d72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001e7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001bdc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001d7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001e88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001bdc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001d7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001e88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001ec3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001ec3`

## pseudocode

```c
TDHSTATUS __stdcall TdhGetProperty(
        PEVENT_RECORD pEvent,
        ULONG TdhContextCount,
        PTDH_CONTEXT pTdhContext,
        ULONG PropertyDataCount,
        PPROPERTY_DATA_DESCRIPTOR pPropertyData,
        ULONG BufferSize,
        PBYTE pBuffer)
{
  USHORT Flags; // dx
  __int64 v12; // r13
  int v13; // esi
  _WORD *TraceEventInfoFromMofInfo; // rax
  void *v15; // r14
  TDHSTATUS WPPCache; // esi
  unsigned __int8 v17; // dl
  __int64 v18; // rax
  char v19; // dl
  __int64 v20; // rbx
  struct _STRUCTUREDMESSAGE *ParameterValue; // r14
  ULONG i; // ecx
  ULONG j; // ecx
  unsigned __int8 v24; // al
  unsigned int v25; // r8d
  __int64 v26; // rcx
  char v27; // al
  RTL_SRWLOCK *v28; // rsi
  RTL_SRWLOCK *v29; // r12
  struct TDH_MOF_INFO *v30; // r13
  unsigned int k; // r14d
  __int64 v32; // rdx
  RTL_SRWLOCK *Ptr; // rcx
  volatile signed __int64 *v34; // rdx
  unsigned int m; // edx
  unsigned __int8 v36; // dl
  unsigned int n; // r8d
  __int64 v38; // rax
  char v39; // dl
  RTL_SRWLOCK *v40; // r12
  LPVOID v41; // r8
  unsigned int ii; // esi
  _DWORD *v43; // rcx
  RTL_SRWLOCK *v44; // r13
  TDHSTATUS PropertySizeOrDataFromTei; // ebx
  struct _TRACE_EVENT_INFO *v46; // rsi
  unsigned __int8 v47; // al
  char v48; // al
  RTL_SRWLOCK *v49; // r8
  HANDLE v50; // rax
  unsigned int v51; // ebx
  HANDLE v52; // rax
  struct TDH_MOF_INFO *v53; // rsi
  __int64 ParameterType; // r10
  HANDLE ProcessHeap; // rax
  struct TDH_MOF_INFO *v56; // r14
  HANDLE v57; // rax
  HANDLE v58; // rax
  unsigned int v59; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  struct _STRUCTUREDMESSAGE *v61; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v62; // [rsp+58h] [rbp-A8h]
  volatile signed __int64 *v63; // [rsp+60h] [rbp-A0h]
  struct _TDH_CONTEXT *v64; // [rsp+68h] [rbp-98h]
  struct _PROPERTY_DATA_DESCRIPTOR *v65; // [rsp+70h] [rbp-90h]
  struct _TRACE_EVENT_INFO Mem[14]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int dwBytes; // [rsp+870h] [rbp+770h] BYREF
  char dwBytes_4; // [rsp+874h] [rbp+774h]

  v65 = pPropertyData;
  v62 = pBuffer;
  v64 = pTdhContext;
  LODWORD(lpMem) = TdhContextCount;
  if ( !pEvent || !pPropertyData || !pBuffer || !BufferSize || PropertyDataCount - 1 > 0x7E )
    return 87;
  if ( !TdhContextCount )
  {
    if ( !pTdhContext )
      goto LABEL_8;
    return 87;
  }
  if ( !pTdhContext )
    return 87;
LABEL_8:
  if ( TdhContextCount >= 5 )
    return 87;
  Flags = pEvent->EventHeader.Flags;
  if ( (Flags & 0x108) != 0 && PropertyDataCount != 1 )
    return 87;
  if ( pTdhContext )
  {
    v20 = 0;
    dwBytes = 0;
    LODWORD(ParameterValue) = 0;
    dwBytes_4 = 0;
    v61 = 0;
    for ( i = 0; i < TdhContextCount; ++i )
    {
      ParameterType = pTdhContext[i].ParameterType;
      if ( (unsigned int)ParameterType > 4 )
        return 87;
      if ( *((_BYTE *)&dwBytes + ParameterType) )
        return 87;
      *((_BYTE *)&dwBytes + ParameterType) = 1;
      if ( (_DWORD)ParameterType == 3 )
      {
        ParameterValue = (struct _STRUCTUREDMESSAGE *)pTdhContext[i].ParameterValue;
        v61 = ParameterValue;
        if ( (((unsigned __int64)ParameterValue - 4) & 0xFFFFFFFFFFFFFFFBuLL) != 0 )
          return 87;
      }
    }
  }
  else
  {
    v20 = 0;
    LODWORD(ParameterValue) = 0;
    v61 = 0;
  }
  for ( j = 0; j < PropertyDataCount; ++j )
  {
    if ( !pPropertyData[j].PropertyName )
      return 87;
  }
  if ( (Flags & 8) != 0 )
  {
    v61 = 0;
    v24 = 0;
    v59 = 0;
    v25 = 0;
    dwBytes = 0;
    do
    {
      v26 = v25 + 3;
      v27 = __ROL1__(
              *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v25 + 2)
            ^ __ROL1__(
                *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v25 + 1)
              ^ __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v25) ^ v24, 3),
                3),
              3);
      v25 += 4;
      v24 = __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v26) ^ v27, 3);
    }
    while ( v25 < 0x10 );
    v28 = (RTL_SRWLOCK *)((char *)g_TdhCache + 64 * (unsigned __int64)v24);
    while ( 1 )
    {
      AcquireSRWLockShared(v28);
      v29 = 0;
      v30 = 0;
      for ( k = 0; k < 7; ++k )
      {
        v32 = k + 1LL;
        Ptr = (RTL_SRWLOCK *)v28[v32].Ptr;
        v34 = (volatile signed __int64 *)&v28[v32];
        v63 = v34;
        if ( Ptr )
        {
          if ( LODWORD(Ptr[1].Ptr) == pEvent->EventHeader.ProviderId.Data1
            && HIDWORD(Ptr[1].Ptr) == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data2
            && LODWORD(Ptr[2].Ptr) == *(_DWORD *)pEvent->EventHeader.ProviderId.Data4
            && HIDWORD(Ptr[2].Ptr) == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data4[4] )
          {
            v29 = Ptr;
            break;
          }
        }
        else
        {
          if ( !v30 )
          {
            v30 = TdhpCacheEntryAllocate(&pEvent->EventHeader.ProviderId);
            if ( !v30 )
              goto LABEL_70;
            v34 = v63;
          }
          if ( !_InterlockedCompareExchange64(v34, (signed __int64)v30, 0) )
          {
            v29 = (RTL_SRWLOCK *)v30;
            goto LABEL_70;
          }
          if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)(*v34 + 8), &pEvent->EventHeader.ProviderId) )
          {
            v29 = v49;
            break;
          }
        }
      }
      if ( v29 != (RTL_SRWLOCK *)v30 && v30 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v30);
      }
LABEL_70:
      if ( v29 )
        break;
      ReleaseSRWLockShared(v28);
      AcquireSRWLockExclusive(v28);
      v56 = TdhpFindOrAddEntry((struct TDH_CACHE_BUCKET *)v28, &pEvent->EventHeader.ProviderId, &dwBytes);
      if ( !v56 && !dwBytes )
        v56 = TdhpCacheEvictAndAddEntry((struct TDH_CACHE_BUCKET *)v28, &pEvent->EventHeader.ProviderId);
      ReleaseSRWLockExclusive(v28);
      if ( !v56 )
        return 8;
    }
    AcquireSRWLockExclusive(v29);
    WPPCache = TdhpGetWPPCache((struct TDH_MOF_INFO *)v29, pEvent, (unsigned int)lpMem, v64, &v61, &v59);
    if ( !WPPCache )
      WPPCache = TdhpGetPropertyorSizeFromStructMessage(v65, v61, v59, BufferSize, v62, (unsigned int *)&lpMem);
    ReleaseSRWLockExclusive(v29);
    v47 = 0;
    do
    {
      v48 = *((_BYTE *)&v29[1].Ptr + v20++) ^ v47;
      v47 = __ROL1__(v48, 3);
    }
    while ( v20 != 16 );
    ReleaseSRWLockShared((PSRWLOCK)g_TdhCache + 8 * (unsigned __int64)v47);
    return WPPCache;
  }
  if ( pEvent->EventHeader.EventDescriptor.Channel != 11 )
  {
    for ( m = 0; m < pEvent->ExtendedDataCount; ++m )
    {
      if ( pEvent->ExtendedData[m].ExtType == 11 )
        goto LABEL_58;
    }
    v59 = 0;
    v36 = 0;
    dwBytes = 0;
    for ( n = 0; n < 0x10; n += 4 )
    {
      v38 = n + 3;
      v39 = __ROL1__(
              *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + n + 2)
            ^ __ROL1__(
                *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + n + 1)
              ^ __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + n) ^ v36, 3),
                3),
              3);
      v36 = __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v38) ^ v39, 3);
    }
    v40 = (RTL_SRWLOCK *)((char *)g_TdhCache + 64 * (unsigned __int64)v36);
LABEL_51:
    AcquireSRWLockShared(v40);
    v41 = 0;
    lpMem = 0;
    for ( ii = 0; ii < 7; ++ii )
    {
      v43 = v40[ii + 1].Ptr;
      v44 = &v40[ii];
      if ( v43 )
      {
        if ( v43[2] == pEvent->EventHeader.ProviderId.Data1
          && v43[3] == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data2
          && v43[4] == *(_DWORD *)pEvent->EventHeader.ProviderId.Data4
          && v43[5] == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data4[4] )
        {
          v12 = (__int64)v40[ii + 1].Ptr;
          goto LABEL_17;
        }
      }
      else
      {
        if ( !v41 )
        {
          lpMem = TdhpCacheEntryAllocate(&pEvent->EventHeader.ProviderId);
          v41 = lpMem;
          if ( !lpMem )
          {
LABEL_90:
            ReleaseSRWLockShared(v40);
            AcquireSRWLockExclusive(v40);
            v53 = TdhpFindOrAddEntry((struct TDH_CACHE_BUCKET *)v40, &pEvent->EventHeader.ProviderId, &dwBytes);
            if ( !v53 && !dwBytes )
              v53 = TdhpCacheEvictAndAddEntry((struct TDH_CACHE_BUCKET *)v40, &pEvent->EventHeader.ProviderId);
            ReleaseSRWLockExclusive(v40);
            if ( !v53 )
              return 8;
            goto LABEL_51;
          }
        }
        if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&v44[1], (signed __int64)v41, 0) )
        {
          v12 = (__int64)v41;
          goto LABEL_20;
        }
        v12 = (__int64)v44[1].Ptr;
        if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)(v12 + 8), &pEvent->EventHeader.ProviderId) )
          goto LABEL_17;
      }
    }
    v12 = 0;
LABEL_17:
    if ( (LPVOID)v12 != v41 && v41 )
    {
      v57 = GetProcessHeap();
      HeapFree(v57, 0, lpMem);
    }
LABEL_20:
    if ( !v12 )
      goto LABEL_90;
    AcquireSRWLockShared((PSRWLOCK)v12);
    v13 = (int)v61;
    TraceEventInfoFromMofInfo = TdhpGetTraceEventInfoFromMofInfo(
                                  (unsigned int)v61,
                                  pEvent->EventHeader.Flags,
                                  v12,
                                  &pEvent->EventHeader.ProviderId,
                                  (__int64)&pEvent->EventHeader.EventDescriptor,
                                  0,
                                  0,
                                  &v59);
    v15 = TraceEventInfoFromMofInfo;
    if ( TraceEventInfoFromMofInfo )
      WPPCache = GetPropertySizeOrDataFromTei(
                   (__int64)pEvent,
                   (__int64)TraceEventInfoFromMofInfo,
                   (__int64)v65,
                   PropertyDataCount,
                   v13,
                   (char *)v62,
                   BufferSize,
                   &lpMem);
    else
      WPPCache = 1168;
    ReleaseSRWLockShared((PSRWLOCK)v12);
    v17 = 0;
    do
    {
      v18 = (unsigned int)(v20 + 3);
      v19 = __ROL1__(
              *(_BYTE *)((unsigned int)(v20 + 2) + v12 + 8)
            ^ __ROL1__(
                *(_BYTE *)((unsigned int)(v20 + 1) + v12 + 8)
              ^ __ROL1__(*(_BYTE *)((unsigned int)v20 + v12 + 8) ^ v17, 3),
                3),
              3);
      LODWORD(v20) = v20 + 4;
      v17 = __ROL1__(*(_BYTE *)(v18 + v12 + 8) ^ v19, 3);
    }
    while ( (unsigned int)v20 < 0x10 );
    ReleaseSRWLockShared((PSRWLOCK)g_TdhCache + 8 * (unsigned __int64)v17);
    if ( v59 && v15 )
    {
      v58 = GetProcessHeap();
      HeapFree(v58, 0, v15);
    }
    return WPPCache;
  }
LABEL_58:
  dwBytes = 2032;
  LOWORD(v59) = 0;
  PropertySizeOrDataFromTei = TraceLogging::MetadataReader::TeiFromPayload(
                                Mem,
                                0x7F0u,
                                &dwBytes,
                                pEvent,
                                (unsigned __int16 *)&v59);
  if ( PropertySizeOrDataFromTei != 122 )
  {
    v46 = Mem;
LABEL_60:
    if ( !PropertySizeOrDataFromTei )
      PropertySizeOrDataFromTei = GetPropertySizeOrDataFromTei(
                                    (__int64)pEvent,
                                    (__int64)v46,
                                    (__int64)pPropertyData,
                                    PropertyDataCount,
                                    (int)ParameterValue,
                                    (char *)v62,
                                    BufferSize,
                                    &lpMem);
    goto LABEL_62;
  }
  v51 = dwBytes;
  v52 = GetProcessHeap();
  v46 = (struct _TRACE_EVENT_INFO *)HeapAlloc(v52, 8u, v51);
  if ( !v46 )
    return 14;
  PropertySizeOrDataFromTei = TraceLogging::MetadataReader::TeiFromPayload(
                                v46,
                                dwBytes,
                                &dwBytes,
                                pEvent,
                                (unsigned __int16 *)&v59);
  if ( PropertySizeOrDataFromTei != 122 )
    goto LABEL_60;
  PropertySizeOrDataFromTei = 1392;
LABEL_62:
  if ( v46 != Mem && v46 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v46);
  }
  return PropertySizeOrDataFromTei;
}

```

## disassembly

```asm
0x180001730  push    rbp
0x180001732  push    rbx
0x180001733  push    rdi
0x180001734  push    r12
0x180001736  push    r13
0x180001738  push    r14
0x18000173a  push    r15
0x18000173c  lea     rbp, [rsp-780h]
0x180001744  sub     rsp, 880h
0x18000174b  mov     rax, cs:__security_cookie
0x180001752  xor     rax, rsp
0x180001755  mov     [rbp+7B0h+var_38], rax
0x18000175c  mov     r12, [rbp+7B0h+pPropertyData]
0x180001763  mov     edi, r9d
0x180001766  mov     rax, [rbp+7B0h+pBuffer]
0x18000176d  mov     r9d, edx
0x180001770  mov     [rsp+8B0h+var_840], r12
0x180001775  mov     r15, rcx
0x180001778  mov     [rsp+8B0h+var_858], rax
0x18000177d  mov     [rsp+8B0h+var_848], r8
0x180001782  mov     dword ptr [rsp+8B0h+lpMem], edx
0x180001786  test    rcx, rcx
0x180001789  jz      short loc_1800017D3
0x18000178b  test    r12, r12
0x18000178e  jz      short loc_1800017D3
0x180001790  test    rax, rax
0x180001793  jz      short loc_1800017D3
0x180001795  mov     r13d, [rbp+7B0h+BufferSize]
0x18000179c  test    r13d, r13d
0x18000179f  jz      short loc_1800017D3
0x1800017a1  lea     eax, [rdi-1]
0x1800017a4  cmp     eax, 7Eh ; '~'
0x1800017a7  ja      short loc_1800017D3
0x1800017a9  test    edx, edx
0x1800017ab  jz      short loc_1800017DD
0x1800017ad  test    r8, r8
0x1800017b0  jz      short loc_1800017D3
0x1800017b2  cmp     r9d, 5
0x1800017b6  jnb     short loc_1800017D3
0x1800017b8  movzx   edx, word ptr [rcx+4]
0x1800017bc  mov     eax, 108h
0x1800017c1  test    ax, dx
0x1800017c4  jz      loc_180001921
0x1800017ca  cmp     edi, 1
0x1800017cd  jz      loc_180001921
0x1800017d3  mov     eax, 57h ; 'W'
0x1800017d8  jmp     loc_1800018FF
0x1800017dd  test    r8, r8
0x1800017e0  jz      short loc_1800017B2
0x1800017e2  jmp     short loc_1800017D3
0x1800017e4  mov     eax, [r15+20h]
0x1800017e8  cmp     [rcx+10h], eax
0x1800017eb  jnz     loc_180001B03
0x1800017f1  mov     eax, [r15+24h]
0x1800017f5  cmp     [rcx+14h], eax
0x1800017f8  jnz     loc_180001B03
0x1800017fe  mov     r13, rcx
0x180001801  cmp     r13, r8
0x180001804  jz      short loc_18000180F
0x180001806  test    r8, r8
0x180001809  jnz     loc_180001EE7
0x18000180f  test    r13, r13
0x180001812  jz      loc_180001D6F
0x180001818  mov     rcx, r13; SRWLock
0x18000181b  call    cs:__imp_AcquireSRWLockShared
0x180001821  mov     rsi, [rsp+8B0h+var_860]
0x180001826  lea     rax, [rsp+8B0h+var_870]
0x18000182b  movzx   edx, word ptr [r15+4]
0x180001830  lea     r9, [r15+18h]
0x180001834  mov     [rsp+8B0h+var_878], rax; __int64
0x180001839  mov     r8, r13
0x18000183c  mov     [rsp+8B0h+var_880], ebx; int
0x180001840  lea     rax, [r15+28h]
0x180001844  mov     [rsp+8B0h+var_888], rbx; __int64
0x180001849  mov     ecx, esi; unsigned int
0x18000184b  mov     [rsp+8B0h+var_890], rax; __int64
0x180001850  call    TdhpGetTraceEventInfoFromMofInfo
0x180001855  mov     r14, rax
0x180001858  test    rax, rax
0x18000185b  jz      loc_180001F02
0x180001861  mov     r8, [rsp+8B0h+var_840]; int
0x180001866  lea     rax, [rsp+8B0h+lpMem]
0x18000186b  mov     [rsp+8B0h+var_878], rax; __int64
0x180001870  mov     r9d, edi; int
0x180001873  mov     eax, [rbp+7B0h+BufferSize]
0x180001879  mov     rdx, r14; int
0x18000187c  mov     [rsp+8B0h+var_880], eax; int
0x180001880  mov     rcx, r15; int
0x180001883  mov     rax, [rsp+8B0h+var_858]
0x180001888  mov     [rsp+8B0h+var_888], rax; void *
0x18000188d  mov     dword ptr [rsp+8B0h+var_890], esi; int
0x180001891  call    GetPropertySizeOrDataFromTei
0x180001896  mov     esi, eax
0x180001898  mov     rcx, r13; SRWLock
0x18000189b  call    cs:__imp_ReleaseSRWLockShared
0x1800018a1  xor     dl, dl
0x1800018a3  mov     eax, ebx
0x1800018a5  xor     dl, [rax+r13+8]
0x1800018aa  lea     eax, [rbx+1]
0x1800018ad  rol     dl, 3
0x1800018b0  xor     dl, [rax+r13+8]
0x1800018b5  lea     eax, [rbx+2]
0x1800018b8  rol     dl, 3
0x1800018bb  xor     dl, [rax+r13+8]
0x1800018c0  lea     eax, [rbx+3]
0x1800018c3  rol     dl, 3
0x1800018c6  add     ebx, 4
0x1800018c9  xor     dl, [rax+r13+8]
0x1800018ce  rol     dl, 3
0x1800018d1  cmp     ebx, 10h
0x1800018d4  jb      short loc_1800018A3
0x1800018d6  movzx   ecx, dl
0x1800018d9  shl     rcx, 6
0x1800018dd  add     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; SRWLock
0x1800018e4  call    cs:__imp_ReleaseSRWLockShared
0x1800018ea  cmp     [rsp+8B0h+var_870], 0
0x1800018ef  jnz     loc_180001F0C
0x1800018f5  mov     eax, esi
0x1800018f7  mov     rsi, [rsp+8B0h+arg_18]
0x1800018ff  mov     rcx, [rbp+7B0h+var_38]
0x180001906  xor     rcx, rsp; StackCookie
0x180001909  call    __security_check_cookie
0x18000190e  add     rsp, 880h
0x180001915  pop     r15
0x180001917  pop     r14
0x180001919  pop     r13
0x18000191b  pop     r12
0x18000191d  pop     rdi
0x18000191e  pop     rbx
0x18000191f  pop     rbp
0x180001920  retn
0x180001921  test    r8, r8
0x180001924  jz      loc_180001A2D
0x18000192a  xor     eax, eax
0x18000192c  xor     ebx, ebx
0x18000192e  mov     dword ptr [rbp+7B0h+dwBytes], eax
0x180001934  mov     r14d, ebx
0x180001937  mov     byte ptr [rbp+7B0h+dwBytes+4], al
0x18000193d  mov     [rsp+8B0h+var_860], r14
0x180001942  mov     ecx, ebx
0x180001944  cmp     ecx, r9d
0x180001947  jb      loc_180001DDB
0x18000194d  mov     ecx, ebx
0x18000194f  cmp     ecx, edi
0x180001951  jb      loc_180001A16
0x180001957  mov     [rsp+8B0h+arg_18], rsi
0x18000195f  test    dl, 8
0x180001962  jz      loc_180001A3C
0x180001968  mov     [rsp+8B0h+var_860], rbx
0x18000196d  xor     al, al
0x18000196f  mov     [rsp+8B0h+var_870], ebx
0x180001973  mov     r8d, ebx
0x180001976  mov     dword ptr [rbp+7B0h+dwBytes], ebx
0x18000197c  mov     ecx, r8d
0x18000197f  xor     al, [rcx+r15+18h]
0x180001984  lea     ecx, [r8+1]
0x180001988  rol     al, 3
0x18000198b  xor     al, [rcx+r15+18h]
0x180001990  lea     ecx, [r8+2]
0x180001994  rol     al, 3
0x180001997  xor     al, [rcx+r15+18h]
0x18000199c  lea     ecx, [r8+3]
0x1800019a0  rol     al, 3
0x1800019a3  add     r8d, 4
0x1800019a7  xor     al, [rcx+r15+18h]
0x1800019ac  rol     al, 3
0x1800019af  cmp     r8d, 10h
0x1800019b3  jb      short loc_18000197C
0x1800019b5  movzx   esi, al
0x1800019b8  shl     rsi, 6
0x1800019bc  add     rsi, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800019c3  mov     rcx, rsi; SRWLock
0x1800019c6  call    cs:__imp_AcquireSRWLockShared
0x1800019cc  mov     r12, rbx
0x1800019cf  mov     r13, rbx
0x1800019d2  mov     r14d, ebx
0x1800019d5  cmp     r14d, 7
0x1800019d9  jnb     loc_180001BC2
0x1800019df  mov     edx, r14d
0x1800019e2  inc     rdx
0x1800019e5  mov     rcx, [rsi+rdx*8]
0x1800019e9  lea     rdx, [rsi+rdx*8]
0x1800019ed  mov     [rsp+8B0h+var_850], rdx
0x1800019f2  test    rcx, rcx
0x1800019f5  jz      loc_180001C7E
0x1800019fb  mov     eax, [r15+18h]
0x1800019ff  cmp     [rcx+8], eax
0x180001a02  jnz     short loc_180001A11
0x180001a04  mov     eax, [r15+1Ch]
0x180001a08  cmp     [rcx+0Ch], eax
0x180001a0b  jz      loc_180001BA5
0x180001a11  inc     r14d
0x180001a14  jmp     short loc_1800019D5
0x180001a16  mov     eax, ecx
0x180001a18  add     rax, rax
0x180001a1b  cmp     qword ptr [r12+rax*8], 0
0x180001a20  jz      loc_1800017D3
0x180001a26  inc     ecx
0x180001a28  jmp     loc_18000194F
0x180001a2d  xor     ebx, ebx
0x180001a2f  mov     r14d, ebx
0x180001a32  mov     [rsp+8B0h+var_860], r14
0x180001a37  jmp     loc_18000194D
0x180001a3c  cmp     byte ptr [r15+2Bh], 0Bh
0x180001a41  jz      loc_180001B1C
0x180001a47  movzx   r8d, word ptr [r15+54h]
0x180001a4c  mov     edx, ebx
0x180001a4e  cmp     edx, r8d
0x180001a51  jb      loc_180001B07
0x180001a57  mov     [rsp+8B0h+var_870], ebx
0x180001a5b  xor     dl, dl
0x180001a5d  mov     dword ptr [rbp+7B0h+dwBytes], ebx
0x180001a63  mov     r8d, ebx
0x180001a66  nop     word ptr [rax+rax+00000000h]
0x180001a70  mov     eax, r8d
0x180001a73  xor     dl, [rax+r15+18h]
0x180001a78  lea     eax, [r8+1]
0x180001a7c  rol     dl, 3
0x180001a7f  xor     dl, [rax+r15+18h]
0x180001a84  lea     eax, [r8+2]
0x180001a88  rol     dl, 3
0x180001a8b  xor     dl, [rax+r15+18h]
0x180001a90  lea     eax, [r8+3]
0x180001a94  rol     dl, 3
0x180001a97  add     r8d, 4
0x180001a9b  xor     dl, [rax+r15+18h]
0x180001aa0  rol     dl, 3
0x180001aa3  cmp     r8d, 10h
0x180001aa7  jb      short loc_180001A70
0x180001aa9  movzx   r12d, dl
0x180001aad  shl     r12, 6
0x180001ab1  add     r12, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180001ab8  mov     rcx, r12; SRWLock
0x180001abb  call    cs:__imp_AcquireSRWLockShared
0x180001ac1  mov     r8, rbx
0x180001ac4  mov     [rsp+8B0h+lpMem], rbx
0x180001ac9  mov     esi, ebx
0x180001acb  nop     dword ptr [rax+rax+00h]
0x180001ad0  cmp     esi, 7
0x180001ad3  jnb     loc_180001EDF
0x180001ad9  mov     eax, esi
0x180001adb  mov     rcx, [r12+rax*8+8]
0x180001ae0  lea     r13, [r12+rax*8]
0x180001ae4  test    rcx, rcx
0x180001ae7  jz      loc_180001D4C
0x180001aed  mov     eax, [r15+18h]
0x180001af1  cmp     [rcx+8], eax
0x180001af4  jnz     short loc_180001B03
0x180001af6  mov     eax, [r15+1Ch]
0x180001afa  cmp     [rcx+0Ch], eax
0x180001afd  jz      loc_1800017E4
0x180001b03  inc     esi
0x180001b05  jmp     short loc_180001AD0
0x180001b07  mov     rax, [r15+58h]
0x180001b0b  mov     ecx, edx
0x180001b0d  add     rcx, rcx
0x180001b10  cmp     word ptr [rax+rcx*8+2], 0Bh
0x180001b16  jnz     loc_180001C77
0x180001b1c  lea     rax, [rsp+8B0h+var_870]
0x180001b21  mov     dword ptr [rbp+7B0h+dwBytes], 7F0h
0x180001b2b  mov     r9, r15; struct _EVENT_RECORD *
0x180001b2e  mov     [rsp+8B0h+var_890], rax; unsigned __int16 *
0x180001b33  lea     r8, [rbp+7B0h+dwBytes]; unsigned int *
0x180001b3a  mov     word ptr [rsp+8B0h+var_870], bx
0x180001b3f  mov     edx, 7F0h; unsigned int
0x180001b44  lea     rcx, [rbp+7B0h+Mem]; struct _TRACE_EVENT_INFO *
0x180001b48  call    ?TeiFromPayload@MetadataReader@TraceLogging@@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z; TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)
0x180001b4d  mov     ebx, eax
0x180001b4f  cmp     eax, 7Ah ; 'z'
0x180001b52  jz      loc_180001CEC
0x180001b58  lea     rsi, [rbp+7B0h+Mem]
0x180001b5c  test    ebx, ebx
0x180001b5e  jnz     short loc_180001B91
0x180001b60  lea     rax, [rsp+8B0h+lpMem]
0x180001b65  mov     r9d, edi; int
0x180001b68  mov     [rsp+8B0h+var_878], rax; __int64
0x180001b6d  mov     r8, r12; int
0x180001b70  mov     rax, [rsp+8B0h+var_858]
0x180001b75  mov     rdx, rsi; int
0x180001b78  mov     [rsp+8B0h+var_880], r13d; int
0x180001b7d  mov     rcx, r15; int
0x180001b80  mov     [rsp+8B0h+var_888], rax; void *
0x180001b85  mov     dword ptr [rsp+8B0h+var_890], r14d; int
0x180001b8a  call    GetPropertySizeOrDataFromTei
0x180001b8f  mov     ebx, eax
0x180001b91  lea     rax, [rbp+7B0h+Mem]
0x180001b95  cmp     rsi, rax
0x180001b98  jnz     loc_180001CCA
0x180001b9e  mov     eax, ebx
0x180001ba0  jmp     loc_1800018F7
0x180001ba5  mov     eax, [r15+20h]
0x180001ba9  cmp     [rcx+10h], eax
0x180001bac  jnz     loc_180001A11
0x180001bb2  mov     eax, [r15+24h]
0x180001bb6  cmp     [rcx+14h], eax
0x180001bb9  jnz     loc_180001A11
0x180001bbf  mov     r12, rcx
0x180001bc2  cmp     r12, r13
0x180001bc5  jz      short loc_180001BD0
0x180001bc7  test    r13, r13
  ... truncated ...
```
