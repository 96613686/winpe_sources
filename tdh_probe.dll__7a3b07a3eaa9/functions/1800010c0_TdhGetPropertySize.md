# TdhGetPropertySize

- ea: `0x1800010c0`
- end: `0x180001727`
- name: `TdhGetPropertySize`
- size: `1639`
- prototype: `TDHSTATUS __stdcall(PEVENT_RECORD pEvent, ULONG TdhContextCount, PTDH_CONTEXT pTdhContext, ULONG PropertyDataCount, PPROPERTY_DATA_DESCRIPTOR pPropertyData, ULONG *pPropertySize)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800010c0`
- `0x180001f40`
- `0x180003940`
- `0x180004fb0`
- `0x1800059e8`
- `0x1800064d0`
- `0x180006660`
- `0x180007720`
- `0x180012470`
- `0x180016df4`
- `0x1800207c0`
- `0x180024318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000137d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000137d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000151e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000170d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000151e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000170d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000134b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000136c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800016fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000134b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000136c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800016fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800012ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001433`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800012ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001433`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800014a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800014f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001556`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000164e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800014a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800014f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001556`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000164e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000155f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001678`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000155f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001678`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000159e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800016d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000159e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800016d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
TDHSTATUS __stdcall TdhGetPropertySize(
        PEVENT_RECORD pEvent,
        ULONG TdhContextCount,
        PTDH_CONTEXT pTdhContext,
        ULONG PropertyDataCount,
        PPROPERTY_DATA_DESCRIPTOR pPropertyData,
        ULONG *pPropertySize)
{
  USHORT Flags; // dx
  TDHSTATUS WPPCache; // edi
  struct _TRACE_EVENT_INFO *v13; // r13
  __int64 v14; // rbx
  ULONG v15; // ecx
  ULONG i; // ecx
  unsigned int j; // edx
  unsigned __int8 v18; // dl
  unsigned int k; // r8d
  __int64 v20; // rax
  char v21; // dl
  RTL_SRWLOCK *v22; // rdi
  RTL_SRWLOCK *v23; // r8
  unsigned int m; // edi
  RTL_SRWLOCK *v25; // rdx
  RTL_SRWLOCK *Ptr; // rcx
  HANDLE v27; // rax
  unsigned int v28; // edi
  HANDLE v29; // rax
  RTL_SRWLOCK *v30; // rax
  struct TDH_MOF_INFO *v31; // r14
  RTL_SRWLOCK *v32; // rax
  RTL_SRWLOCK *v33; // r13
  int v34; // edi
  _WORD *TraceEventInfoFromMofInfo; // rax
  unsigned __int8 v36; // dl
  __int64 v37; // rax
  char v38; // dl
  void *v39; // rbx
  HANDLE v40; // rax
  __int64 ParameterType; // r8
  RTL_SRWLOCK *v42; // r9
  char v43; // al
  unsigned __int8 v44; // al
  HANDLE ProcessHeap; // rax
  unsigned __int16 v46[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct _STRUCTUREDMESSAGE *ParameterValue; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h]
  LPVOID v49; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  PSRWLOCK v51; // [rsp+68h] [rbp-98h]
  struct _TRACE_EVENT_INFO Mem[14]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int dwBytes; // [rsp+860h] [rbp+760h] BYREF
  char dwBytes_4; // [rsp+864h] [rbp+764h]

  if ( !pEvent || !pPropertyData || !pPropertySize || PropertyDataCount - 1 > 0x7E )
    return 87;
  if ( !TdhContextCount )
  {
    if ( !pTdhContext )
      goto LABEL_7;
    return 87;
  }
  if ( !pTdhContext )
    return 87;
LABEL_7:
  if ( TdhContextCount >= 5 )
    return 87;
  Flags = pEvent->EventHeader.Flags;
  if ( (Flags & 0x108) != 0 && PropertyDataCount != 1 )
    return 87;
  if ( pTdhContext )
  {
    v14 = 0;
    dwBytes = 0;
    LODWORD(ParameterValue) = 0;
    v15 = 0;
    dwBytes_4 = 0;
    while ( v15 < TdhContextCount )
    {
      ParameterType = pTdhContext[v15].ParameterType;
      if ( (unsigned int)ParameterType > 4 )
        return 87;
      if ( *((_BYTE *)&dwBytes + ParameterType) )
        return 87;
      *((_BYTE *)&dwBytes + ParameterType) = 1;
      if ( (_DWORD)ParameterType == 3 )
      {
        ParameterValue = (struct _STRUCTUREDMESSAGE *)pTdhContext[v15].ParameterValue;
        if ( (((unsigned __int64)ParameterValue - 4) & 0xFFFFFFFFFFFFFFFBuLL) != 0 )
          return 87;
      }
      ++v15;
    }
  }
  else
  {
    v14 = 0;
    LODWORD(ParameterValue) = 0;
  }
  for ( i = 0; i < PropertyDataCount; ++i )
  {
    if ( !pPropertyData[i].PropertyName )
      return 87;
  }
  if ( (Flags & 8) != 0 )
  {
    ParameterValue = 0;
    dwBytes = 0;
    v30 = (RTL_SRWLOCK *)TdhpCacheLockEntry(0, &pEvent->EventHeader.ProviderId);
    v31 = (struct TDH_MOF_INFO *)v30;
    if ( !v30 )
      return 8;
    AcquireSRWLockExclusive(v30);
    WPPCache = TdhpGetWPPCache(v31, pEvent, TdhContextCount, pTdhContext, &ParameterValue, &dwBytes);
    if ( !WPPCache )
      WPPCache = TdhpGetPropertyorSizeFromStructMessage(pPropertyData, ParameterValue, dwBytes, 0, 0, pPropertySize);
    ReleaseSRWLockExclusive((PSRWLOCK)v31);
    v44 = 0;
    do
    {
      v43 = *((_BYTE *)v31 + v14++ + 8) ^ v44;
      v44 = __ROL1__(v43, 3);
    }
    while ( v14 != 16 );
    ReleaseSRWLockShared((PSRWLOCK)g_TdhCache + 8 * (unsigned __int64)v44);
    return WPPCache;
  }
  if ( pEvent->EventHeader.EventDescriptor.Channel != 11 )
  {
    for ( j = 0; j < pEvent->ExtendedDataCount; ++j )
    {
      if ( pEvent->ExtendedData[j].ExtType == 11 )
        goto LABEL_14;
    }
    *(_DWORD *)v46 = 0;
    v18 = 0;
    dwBytes = 0;
    for ( k = 0; k < 0x10; k += 4 )
    {
      v20 = k + 3;
      v21 = __ROL1__(
              *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + k + 2)
            ^ __ROL1__(
                *((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + k + 1)
              ^ __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + k) ^ v18, 3),
                3),
              3);
      v18 = __ROL1__(*((_BYTE *)&pEvent->EventHeader.ProviderId.Data1 + v20) ^ v21, 3);
    }
    v22 = (RTL_SRWLOCK *)((char *)g_TdhCache + 64 * (unsigned __int64)v18);
    v51 = v22;
LABEL_32:
    AcquireSRWLockShared(v22);
    v23 = 0;
    SRWLock = 0;
    v49 = 0;
    for ( m = 0; m < 7; ++m )
    {
      v25 = &v51[m + 1];
      Ptr = (RTL_SRWLOCK *)v25->Ptr;
      lpMem = v25;
      if ( Ptr )
      {
        if ( LODWORD(Ptr[1].Ptr) == pEvent->EventHeader.ProviderId.Data1
          && HIDWORD(Ptr[1].Ptr) == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data2
          && LODWORD(Ptr[2].Ptr) == *(_DWORD *)pEvent->EventHeader.ProviderId.Data4
          && HIDWORD(Ptr[2].Ptr) == *(_DWORD *)&pEvent->EventHeader.ProviderId.Data4[4] )
        {
          v32 = Ptr;
          SRWLock = Ptr;
          goto LABEL_52;
        }
      }
      else
      {
        if ( !v23 )
        {
          v49 = TdhpCacheEntryAllocate(&pEvent->EventHeader.ProviderId);
          v23 = (RTL_SRWLOCK *)v49;
          if ( !v49 )
          {
LABEL_65:
            v22 = v51;
            ReleaseSRWLockShared(v51);
            AcquireSRWLockExclusive(v51);
            v49 = TdhpFindOrAddEntry((struct TDH_CACHE_BUCKET *)v51, &pEvent->EventHeader.ProviderId, &dwBytes);
            if ( !v49 && !dwBytes )
              v49 = TdhpCacheEvictAndAddEntry((struct TDH_CACHE_BUCKET *)v51, &pEvent->EventHeader.ProviderId);
            ReleaseSRWLockExclusive(v51);
            if ( !v49 )
              return 8;
            goto LABEL_32;
          }
          v25 = (RTL_SRWLOCK *)lpMem;
        }
        if ( !_InterlockedCompareExchange64((volatile signed __int64 *)v25, (signed __int64)v23, 0) )
        {
          v32 = v23;
          SRWLock = v23;
          goto LABEL_55;
        }
        if ( (unsigned int)InlineIsEqualGUID(
                             (const struct _GUID *)((char *)v25->Ptr + 8),
                             &pEvent->EventHeader.ProviderId) )
        {
          v32 = v42;
          SRWLock = v42;
          goto LABEL_52;
        }
      }
    }
    v32 = 0;
LABEL_52:
    if ( v32 != v23 && v23 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v49);
      v32 = SRWLock;
    }
LABEL_55:
    if ( !v32 )
      goto LABEL_65;
    AcquireSRWLockShared(v32);
    v33 = SRWLock;
    v34 = (int)ParameterValue;
    TraceEventInfoFromMofInfo = TdhpGetTraceEventInfoFromMofInfo(
                                  (unsigned int)ParameterValue,
                                  pEvent->EventHeader.Flags,
                                  (__int64)SRWLock,
                                  &pEvent->EventHeader.ProviderId,
                                  (__int64)&pEvent->EventHeader.EventDescriptor,
                                  0,
                                  0,
                                  v46);
    lpMem = TraceEventInfoFromMofInfo;
    if ( TraceEventInfoFromMofInfo )
      WPPCache = GetPropertySizeOrDataFromTei(
                   (__int64)pEvent,
                   (__int64)TraceEventInfoFromMofInfo,
                   (__int64)pPropertyData,
                   PropertyDataCount,
                   v34,
                   0,
                   0,
                   pPropertySize);
    else
      WPPCache = 1168;
    ReleaseSRWLockShared(v33);
    v36 = 0;
    do
    {
      v37 = (unsigned int)(v14 + 3);
      v38 = __ROL1__(
              *((_BYTE *)&v33[1].Ptr + (unsigned int)(v14 + 2))
            ^ __ROL1__(
                *((_BYTE *)&v33[1].Ptr + (unsigned int)(v14 + 1))
              ^ __ROL1__(*((_BYTE *)&v33[1].Ptr + (unsigned int)v14) ^ v36, 3),
                3),
              3);
      LODWORD(v14) = v14 + 4;
      v36 = __ROL1__(*((_BYTE *)&v33[1].Ptr + v37) ^ v38, 3);
    }
    while ( (unsigned int)v14 < 0x10 );
    ReleaseSRWLockShared((PSRWLOCK)g_TdhCache + 8 * (unsigned __int64)v36);
    if ( *(_DWORD *)v46 )
    {
      v39 = lpMem;
      if ( lpMem )
      {
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v39);
        return WPPCache;
      }
    }
    return WPPCache;
  }
LABEL_14:
  dwBytes = 2032;
  v46[0] = 0;
  WPPCache = TraceLogging::MetadataReader::TeiFromPayload(Mem, 0x7F0u, &dwBytes, pEvent, v46);
  if ( WPPCache == 122 )
  {
    v28 = dwBytes;
    v29 = GetProcessHeap();
    v13 = (struct _TRACE_EVENT_INFO *)HeapAlloc(v29, 8u, v28);
    if ( !v13 )
      return 14;
    WPPCache = TraceLogging::MetadataReader::TeiFromPayload(v13, dwBytes, &dwBytes, pEvent, v46);
    if ( WPPCache == 122 )
    {
      WPPCache = 1392;
      goto LABEL_18;
    }
  }
  else
  {
    v13 = Mem;
  }
  if ( !WPPCache )
    WPPCache = GetPropertySizeOrDataFromTei(
                 (__int64)pEvent,
                 (__int64)v13,
                 (__int64)pPropertyData,
                 PropertyDataCount,
                 (int)ParameterValue,
                 0,
                 0,
                 pPropertySize);
LABEL_18:
  if ( v13 == Mem || !v13 )
    return WPPCache;
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v13);
  return WPPCache;
}

```

## disassembly

```asm
0x1800010c0  mov     [rsp-8+arg_18], rbx
0x1800010c5  push    rbp
0x1800010c6  push    rsi
0x1800010c7  push    rdi
0x1800010c8  push    r12
0x1800010ca  push    r13
0x1800010cc  push    r14
0x1800010ce  push    r15
0x1800010d0  lea     rbp, [rsp-770h]
0x1800010d8  sub     rsp, 870h
0x1800010df  mov     rax, cs:__security_cookie
0x1800010e6  xor     rax, rsp
0x1800010e9  mov     [rbp+7A0h+var_38], rax
0x1800010f0  mov     r15, [rbp+7A0h+pPropertyData]
0x1800010f7  mov     r14d, r9d
0x1800010fa  mov     r12, [rbp+7A0h+pPropertySize]
0x180001101  mov     r13, r8
0x180001104  mov     edi, edx
0x180001106  mov     rsi, rcx
0x180001109  test    rcx, rcx
0x18000110c  jz      short loc_18000114B
0x18000110e  test    r15, r15
0x180001111  jz      short loc_18000114B
0x180001113  test    r12, r12
0x180001116  jz      short loc_18000114B
0x180001118  lea     eax, [r9-1]
0x18000111c  cmp     eax, 7Eh ; '~'
0x18000111f  ja      short loc_18000114B
0x180001121  test    edx, edx
0x180001123  jz      short loc_180001155
0x180001125  test    r8, r8
0x180001128  jz      short loc_18000114B
0x18000112a  cmp     edi, 5
0x18000112d  jnb     short loc_18000114B
0x18000112f  movzx   edx, word ptr [rcx+4]
0x180001133  mov     eax, 108h
0x180001138  test    ax, dx
0x18000113b  jz      loc_18000121B
0x180001141  cmp     r14d, 1
0x180001145  jz      loc_18000121B
0x18000114b  mov     eax, 57h ; 'W'
0x180001150  jmp     loc_1800011F1
0x180001155  test    r13, r13
0x180001158  jz      short loc_18000112A
0x18000115a  jmp     short loc_18000114B
0x18000115c  mov     rax, [rsi+58h]
0x180001160  mov     ecx, edx
0x180001162  add     rcx, rcx
0x180001165  cmp     word ptr [rax+rcx*8+2], 0Bh
0x18000116b  jnz     loc_1800013C6
0x180001171  lea     rax, [rsp+8A0h+var_860]
0x180001176  mov     dword ptr [rbp+7A0h+dwBytes], 7F0h
0x180001180  mov     r9, rsi; struct _EVENT_RECORD *
0x180001183  mov     [rsp+8A0h+var_880], rax; unsigned __int16 *
0x180001188  lea     r8, [rbp+7A0h+dwBytes]; unsigned int *
0x18000118f  mov     [rsp+8A0h+var_860], bx
0x180001194  mov     edx, 7F0h; unsigned int
0x180001199  lea     rcx, [rsp+8A0h+Mem]; struct _TRACE_EVENT_INFO *
0x18000119e  call    ?TeiFromPayload@MetadataReader@TraceLogging@@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z; TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)
0x1800011a3  mov     edi, eax
0x1800011a5  cmp     eax, 7Ah ; 'z'
0x1800011a8  jz      loc_180001366
0x1800011ae  lea     r13, [rsp+8A0h+Mem]
0x1800011b3  test    edi, edi
0x1800011b5  jnz     short loc_1800011E1
0x1800011b7  mov     rax, [rsp+8A0h+var_858]
0x1800011bc  mov     r9d, r14d; int
0x1800011bf  mov     [rsp+8A0h+var_868], r12; __int64
0x1800011c4  mov     r8, r15; int
0x1800011c7  mov     [rsp+8A0h+var_870], ebx; int
0x1800011cb  mov     rdx, r13; int
0x1800011ce  mov     [rsp+8A0h+var_878], rbx; void *
0x1800011d3  mov     rcx, rsi; int
0x1800011d6  mov     dword ptr [rsp+8A0h+var_880], eax; int
0x1800011da  call    GetPropertySizeOrDataFromTei
0x1800011df  mov     edi, eax
0x1800011e1  lea     rax, [rsp+8A0h+Mem]
0x1800011e6  cmp     r13, rax
0x1800011e9  jnz     loc_180001342
0x1800011ef  mov     eax, edi
0x1800011f1  mov     rcx, [rbp+7A0h+var_38]
0x1800011f8  xor     rcx, rsp; StackCookie
0x1800011fb  call    __security_check_cookie
0x180001200  mov     rbx, [rsp+8A0h+arg_18]
0x180001208  add     rsp, 870h
0x18000120f  pop     r15
0x180001211  pop     r14
0x180001213  pop     r13
0x180001215  pop     r12
0x180001217  pop     rdi
0x180001218  pop     rsi
0x180001219  pop     rbp
0x18000121a  retn
0x18000121b  test    r13, r13
0x18000121e  jz      loc_180001337
0x180001224  xor     eax, eax
0x180001226  xor     ebx, ebx
0x180001228  mov     dword ptr [rbp+7A0h+dwBytes], eax
0x18000122e  mov     dword ptr [rsp+8A0h+var_858], ebx
0x180001232  mov     ecx, ebx
0x180001234  mov     byte ptr [rbp+7A0h+dwBytes+4], al
0x18000123a  cmp     ecx, edi
0x18000123c  jb      loc_1800015C4
0x180001242  mov     ecx, ebx
0x180001244  cmp     ecx, r14d
0x180001247  jb      loc_180001320
0x18000124d  test    dl, 8
0x180001250  jnz     loc_1800013CD
0x180001256  cmp     byte ptr [rsi+2Bh], 0Bh
0x18000125a  jz      loc_180001171
0x180001260  movzx   r8d, word ptr [rsi+54h]
0x180001265  mov     edx, ebx
0x180001267  cmp     edx, r8d
0x18000126a  jb      loc_18000115C
0x180001270  mov     dword ptr [rsp+8A0h+var_860], ebx
0x180001274  xor     dl, dl
0x180001276  mov     dword ptr [rbp+7A0h+dwBytes], ebx
0x18000127c  mov     r8d, ebx
0x18000127f  mov     eax, r8d
0x180001282  xor     dl, [rax+rsi+18h]
0x180001286  lea     eax, [r8+1]
0x18000128a  rol     dl, 3
0x18000128d  xor     dl, [rax+rsi+18h]
0x180001291  lea     eax, [r8+2]
0x180001295  rol     dl, 3
0x180001298  xor     dl, [rax+rsi+18h]
0x18000129c  lea     eax, [r8+3]
0x1800012a0  rol     dl, 3
0x1800012a3  add     r8d, 4
0x1800012a7  xor     dl, [rax+rsi+18h]
0x1800012ab  rol     dl, 3
0x1800012ae  cmp     r8d, 10h
0x1800012b2  jb      short loc_18000127F
0x1800012b4  movzx   edi, dl
0x1800012b7  shl     rdi, 6
0x1800012bb  add     rdi, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800012c2  mov     [rsp+8A0h+var_838], rdi
0x1800012c7  mov     rcx, rdi; SRWLock
0x1800012ca  call    cs:__imp_AcquireSRWLockShared
0x1800012d0  mov     r8, rbx
0x1800012d3  mov     [rsp+8A0h+SRWLock], rbx
0x1800012d8  mov     [rsp+8A0h+var_848], rbx
0x1800012dd  mov     edi, ebx
0x1800012df  cmp     edi, 7
0x1800012e2  jnb     loc_1800016F5
0x1800012e8  mov     rcx, [rsp+8A0h+var_838]
0x1800012ed  add     rcx, 8
0x1800012f1  mov     edx, edi
0x1800012f3  lea     rdx, [rcx+rdx*8]
0x1800012f7  mov     rcx, [rdx]
0x1800012fa  mov     [rsp+8A0h+lpMem], rdx
0x1800012ff  test    rcx, rcx
0x180001302  jz      loc_18000152B
0x180001308  mov     eax, [rsi+18h]
0x18000130b  cmp     [rcx+8], eax
0x18000130e  jnz     short loc_18000131C
0x180001310  mov     eax, [rsi+1Ch]
0x180001313  cmp     [rcx+0Ch], eax
0x180001316  jz      loc_1800013F9
0x18000131c  inc     edi
0x18000131e  jmp     short loc_1800012DF
0x180001320  mov     eax, ecx
0x180001322  add     rax, rax
0x180001325  cmp     qword ptr [r15+rax*8], 0
0x18000132a  jz      loc_18000114B
0x180001330  inc     ecx
0x180001332  jmp     loc_180001244
0x180001337  xor     ebx, ebx
0x180001339  mov     dword ptr [rsp+8A0h+var_858], ebx
0x18000133d  jmp     loc_180001242
0x180001342  test    r13, r13
0x180001345  jz      loc_1800011EF
0x18000134b  call    cs:__imp_GetProcessHeap
0x180001351  mov     r8, r13; lpMem
0x180001354  xor     edx, edx; dwFlags
0x180001356  mov     rcx, rax; hHeap
0x180001359  call    cs:__imp_HeapFree
0x18000135f  mov     eax, edi
0x180001361  jmp     loc_1800011F1
0x180001366  mov     edi, dword ptr [rbp+7A0h+dwBytes]
0x18000136c  call    cs:__imp_GetProcessHeap
0x180001372  mov     r8d, edi; dwBytes
0x180001375  mov     edx, 8; dwFlags
0x18000137a  mov     rcx, rax; hHeap
0x18000137d  call    cs:__imp_HeapAlloc
0x180001383  mov     r13, rax
0x180001386  test    rax, rax
0x180001389  jz      loc_1800015BA
0x18000138f  mov     edx, dword ptr [rbp+7A0h+dwBytes]; unsigned int
0x180001395  lea     rax, [rsp+8A0h+var_860]
0x18000139a  mov     r9, rsi; struct _EVENT_RECORD *
0x18000139d  mov     [rsp+8A0h+var_880], rax; unsigned __int16 *
0x1800013a2  lea     r8, [rbp+7A0h+dwBytes]; unsigned int *
0x1800013a9  mov     rcx, r13; struct _TRACE_EVENT_INFO *
0x1800013ac  call    ?TeiFromPayload@MetadataReader@TraceLogging@@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z; TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)
0x1800013b1  mov     edi, eax
0x1800013b3  cmp     eax, 7Ah ; 'z'
0x1800013b6  jnz     loc_1800011B3
0x1800013bc  mov     edi, 570h
0x1800013c1  jmp     loc_1800011E1
0x1800013c6  inc     edx
0x1800013c8  jmp     loc_180001267
0x1800013cd  lea     rdx, [rsi+18h]
0x1800013d1  mov     [rsp+8A0h+var_858], rbx
0x1800013d6  xor     ecx, ecx
0x1800013d8  mov     dword ptr [rbp+7A0h+dwBytes], ebx
0x1800013de  call    TdhpCacheLockEntry
0x1800013e3  mov     r14, rax
0x1800013e6  test    rax, rax
0x1800013e9  jnz     loc_180001675
0x1800013ef  mov     edi, 8
0x1800013f4  jmp     loc_1800011EF
0x1800013f9  mov     eax, [rsi+20h]
0x1800013fc  cmp     [rcx+10h], eax
0x1800013ff  jnz     loc_18000131C
0x180001405  mov     eax, [rsi+24h]
0x180001408  cmp     [rcx+14h], eax
0x18000140b  jnz     loc_18000131C
0x180001411  mov     rax, rcx
0x180001414  mov     [rsp+8A0h+SRWLock], rcx
0x180001419  cmp     rax, r8
0x18000141c  jz      short loc_180001427
0x18000141e  test    r8, r8
0x180001421  jnz     loc_1800016FD
0x180001427  test    rax, rax
0x18000142a  jz      loc_18000154E
0x180001430  mov     rcx, rax; SRWLock
0x180001433  call    cs:__imp_AcquireSRWLockShared
0x180001439  mov     r13, [rsp+8A0h+SRWLock]
0x18000143e  lea     rax, [rsp+8A0h+var_860]
0x180001443  mov     rdi, [rsp+8A0h+var_858]
0x180001448  lea     r9, [rsi+18h]
0x18000144c  movzx   edx, word ptr [rsi+4]
0x180001450  mov     r8, r13
0x180001453  mov     [rsp+8A0h+var_868], rax; __int64
0x180001458  mov     ecx, edi; unsigned int
0x18000145a  mov     [rsp+8A0h+var_870], ebx; int
0x18000145e  lea     rax, [rsi+28h]
0x180001462  mov     [rsp+8A0h+var_878], rbx; __int64
0x180001467  mov     [rsp+8A0h+var_880], rax; __int64
0x18000146c  call    TdhpGetTraceEventInfoFromMofInfo
0x180001471  mov     [rsp+8A0h+lpMem], rax
0x180001476  test    rax, rax
0x180001479  jz      loc_18000171D
0x18000147f  mov     [rsp+8A0h+var_868], r12; __int64
0x180001484  mov     r9d, r14d; int
0x180001487  mov     [rsp+8A0h+var_870], ebx; int
0x18000148b  mov     r8, r15; int
0x18000148e  mov     [rsp+8A0h+var_878], rbx; void *
0x180001493  mov     rdx, rax; int
0x180001496  mov     rcx, rsi; int
0x180001499  mov     dword ptr [rsp+8A0h+var_880], edi; int
0x18000149d  call    GetPropertySizeOrDataFromTei
0x1800014a2  mov     edi, eax
0x1800014a4  mov     rcx, r13; SRWLock
0x1800014a7  call    cs:__imp_ReleaseSRWLockShared
0x1800014ad  xor     dl, dl
0x1800014af  nop
0x1800014b0  mov     eax, ebx
0x1800014b2  xor     dl, [rax+r13+8]
0x1800014b7  lea     eax, [rbx+1]
0x1800014ba  rol     dl, 3
0x1800014bd  xor     dl, [rax+r13+8]
0x1800014c2  lea     eax, [rbx+2]
0x1800014c5  rol     dl, 3
0x1800014c8  xor     dl, [rax+r13+8]
0x1800014cd  lea     eax, [rbx+3]
0x1800014d0  rol     dl, 3
0x1800014d3  add     ebx, 4
0x1800014d6  xor     dl, [rax+r13+8]
0x1800014db  rol     dl, 3
0x1800014de  cmp     ebx, 10h
0x1800014e1  jb      short loc_1800014B0
0x1800014e3  movzx   ecx, dl
0x1800014e6  shl     rcx, 6
0x1800014ea  add     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; SRWLock
0x1800014f1  call    cs:__imp_ReleaseSRWLockShared
0x1800014f7  cmp     dword ptr [rsp+8A0h+var_860], 0
0x1800014fc  jz      loc_1800011EF
0x180001502  mov     rbx, [rsp+8A0h+lpMem]
0x180001507  test    rbx, rbx
0x18000150a  jz      loc_1800011EF
0x180001510  call    cs:__imp_GetProcessHeap
0x180001516  mov     r8, rbx; lpMem
0x180001519  xor     edx, edx; dwFlags
0x18000151b  mov     rcx, rax; hHeap
0x18000151e  call    cs:__imp_HeapFree
0x180001524  mov     eax, edi
0x180001526  jmp     loc_1800011F1
0x18000152b  test    r8, r8
0x18000152e  jnz     loc_1800015FD
0x180001534  lea     rcx, [rsi+18h]; struct _GUID *
0x180001538  call    ?TdhpCacheEntryAllocate@@YAPEAUTDH_MOF_INFO@@PEBU_GUID@@@Z; TdhpCacheEntryAllocate(_GUID const *)
0x18000153d  mov     [rsp+8A0h+var_848], rax
0x180001542  mov     r8, rax
0x180001545  test    rax, rax
0x180001548  jnz     loc_1800016DE
0x18000154e  mov     rdi, [rsp+8A0h+var_838]
0x180001553  mov     rcx, rdi; SRWLock
0x180001556  call    cs:__imp_ReleaseSRWLockShared
  ... truncated ...
```
