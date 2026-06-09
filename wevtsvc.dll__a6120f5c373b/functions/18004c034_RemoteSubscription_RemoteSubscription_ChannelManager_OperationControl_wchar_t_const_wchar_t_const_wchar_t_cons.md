# RemoteSubscription::RemoteSubscription(ChannelManager &,OperationControl *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>> &)

- ea: `0x18004c034`
- end: `0x18004c9c5`
- name: `??0RemoteSubscription@@QEAA@AEAVChannelManager@@PEAVOperationControl@@PEB_W22KAEAV?$vector@UQueryChannelInfo@@V?$allocator@UQueryChannelInfo@@@utl@@@utl@@@Z`
- size: `2449`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config`

## callers

- `0x18004bb3c`

## callees

- `0x180003de0`
- `0x180004820`
- `0x180016250`
- `0x180017b60`
- `0x18002dcc0`
- `0x180034744`
- `0x1800348a4`
- `0x18003617c`
- `0x1800363fc`
- `0x180047c6c`
- `0x180047ee0`
- `0x180048340`
- `0x1800487f8`
- `0x180049664`
- `0x18004a3b0`
- `0x18004a488`
- `0x18004c034`
- `0x180054150`
- `0x1800620ac`
- `0x180064718`
- `0x18006bcb0`
- `0x18006cd10`
- `0x1800701d0`
- `0x180070268`
- `0x180070418`
- `0x180071ed0`
- `0x180073cb8`
- `0x1800742f8`
- `0x1800743ec`
- `0x18007f1ec`
- `0x180087d14`
- `0x18008c820`
- `0x18008cb3c`
- `0x180092008`
- `0x180092d78`
- `0x180092ee4`
- `0x18009aee0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18004c7ea`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18004c7ea`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18004c7ca`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18004c7ca`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18004c814`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18004c869`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18004c814`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18004c869`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c5d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c5d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c289`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c5f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c289`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c5f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall RemoteSubscription::RemoteSubscription(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const WCHAR *a5,
        wchar_t *a6,
        int a7,
        __int64 a8)
{
  __int64 v8; // r14
  MergedLogQueryResult *v9; // rdi
  __int64 v10; // r12
  __int64 v11; // r9
  RTL_SRWLOCK *v12; // rbx
  MergedLogQueryResult *v13; // rax
  MergedLogQueryResult *v14; // rax
  MergedLogQueryResult *v15; // rbx
  const char *v16; // r8
  __int64 v17; // rbx
  __m128i si128; // xmm6
  __int64 LogQueryResultForChannel; // rax
  __int64 i; // rsi
  __int64 v21; // rcx
  const WCHAR *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rax
  const char *v25; // r8
  char v26; // eax^2
  __int64 v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  MergedLogQueryResult *v30; // rcx
  int v31; // edi
  wchar_t *v32; // rsi
  MergedLogQueryResult *v33; // rcx
  char v34; // di
  const WCHAR *v35; // r9
  __int64 v36; // rcx
  const WCHAR *v37; // r8
  __int64 v38; // rax
  const WCHAR *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  const WCHAR *v43; // r8
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  struct _PERF_COUNTERSET_INSTANCE *v45; // rdx
  struct _PERF_COUNTERSET_INSTANCE *v46; // rdx
  ULONG v47; // eax
  ULONG v48; // eax
  void *v50; // rax
  __int128 v51; // kr30_16
  volatile signed __int32 *v52; // r10
  __int64 v53; // rsi
  __int64 v54; // rax
  int v55; // ebx
  const char *v56; // r8
  bool v57; // di
  __int64 v58; // r8
  __int64 v59; // rcx
  char v60; // [rsp+50h] [rbp-2E8h]
  int v61; // [rsp+54h] [rbp-2E4h] BYREF
  unsigned int v62; // [rsp+58h] [rbp-2E0h]
  int v63; // [rsp+60h] [rbp-2D8h]
  __int64 v64; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v65; // [rsp+70h] [rbp-2C8h]
  const WCHAR *v66; // [rsp+78h] [rbp-2C0h] BYREF
  wchar_t *v67; // [rsp+80h] [rbp-2B8h]
  __int64 v68; // [rsp+88h] [rbp-2B0h]
  __int128 v69; // [rsp+90h] [rbp-2A8h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-298h] BYREF
  wchar_t *v71; // [rsp+A8h] [rbp-290h]
  WCHAR *v72; // [rsp+B0h] [rbp-288h]
  const WCHAR *v73; // [rsp+B8h] [rbp-280h]
  __int64 v74; // [rsp+C0h] [rbp-278h]
  MergedLogQueryResult *v75; // [rsp+C8h] [rbp-270h]
  __int128 v76; // [rsp+D0h] [rbp-268h] BYREF
  __int64 v77; // [rsp+E0h] [rbp-258h]
  __int64 v78; // [rsp+E8h] [rbp-250h]
  void *v79; // [rsp+F0h] [rbp-248h]
  __int128 v80; // [rsp+100h] [rbp-238h] BYREF
  __int128 v81; // [rsp+110h] [rbp-228h] BYREF
  EvtException *v82; // [rsp+120h] [rbp-218h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+128h] [rbp-210h] BYREF
  _BYTE v84[40]; // [rsp+150h] [rbp-1E8h] BYREF
  _BYTE v85[40]; // [rsp+178h] [rbp-1C0h] BYREF
  _BYTE v86[192]; // [rsp+1A0h] [rbp-198h] BYREF
  PCWSTR Name[4]; // [rsp+260h] [rbp-D8h] BYREF
  const WCHAR *v88; // [rsp+280h] [rbp-B8h] BYREF
  __int64 v89; // [rsp+288h] [rbp-B0h]
  const WCHAR *Src; // [rsp+2A0h] [rbp-98h] BYREF
  __int64 v91; // [rsp+2A8h] [rbp-90h]
  __m128i v92; // [rsp+2C0h] [rbp-78h] BYREF
  __int128 v93; // [rsp+2D0h] [rbp-68h]
  _BYTE v94[6]; // [rsp+2EAh] [rbp-4Eh] BYREF

  v66 = (const WCHAR *)a4;
  v8 = a1;
  v78 = a4;
  v73 = a5;
  v71 = a6;
  v68 = a1;
  v74 = a4;
  v72 = (WCHAR *)a5;
  v67 = a6;
  v61 = a7;
  v63 = a7;
  v65 = a8;
  v62 = 0;
  *(_QWORD *)a1 = &wmi::RefBase::`vftable';
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &RemoteSubscription::`vftable'{for `wmi::RefBase'};
  *(_QWORD *)(a1 + 16) = &RemoteSubscription::`vftable'{for `FilterConsumerCallback'};
  *(_QWORD *)(a1 + 24) = a2;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = a3;
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 8));
  *(_QWORD *)(a1 + 48) = 0;
  RemoteSubscription::RpcStatusSubscription::RpcStatusSubscription(
    (RemoteSubscription::RpcStatusSubscription *)(a1 + 112),
    (enum _RPC_NOTIFICATIONS)a2);
  v9 = (MergedLogQueryResult *)(v8 + 240);
  *(_QWORD *)(v8 + 240) = v8 + 240;
  *(_QWORD *)(v8 + 248) = v8 + 240;
  *(_QWORD *)(v8 + 256) = v8 + 240;
  *(_QWORD *)(v8 + 264) = 0;
  *(_QWORD *)(v8 + 272) = 0;
  v10 = -1;
  *(_QWORD *)(v8 + 280) = -1;
  *(_QWORD *)(v8 + 288) = -1;
  *(_QWORD *)(v8 + 296) = -1;
  *(_QWORD *)(v8 + 304) = -1;
  *(_QWORD *)(v8 + 312) = -1;
  *(_QWORD *)(v8 + 320) = -1;
  *(_QWORD *)(v8 + 328) = 0;
  *(_QWORD *)(v8 + 336) = 0;
  *(_QWORD *)(v8 + 344) = 0;
  *(_DWORD *)(v8 + 352) = 0;
  *(_BYTE *)(v8 + 356) = 0;
  *(_DWORD *)(v8 + 392) = GetRpcClientPid();
  *(_DWORD *)(v8 + 396) = _InterlockedIncrement(&dword_180111674);
  *(_DWORD *)(v8 + 404) = a7;
  *(_DWORD *)(v8 + 408) = 0;
  *(_WORD *)(v8 + 412) = 0;
  *(_BYTE *)(v8 + 414) = 0;
  *(_QWORD *)(v8 + 56) = 0;
  *(_QWORD *)(v8 + 64) = 0;
  *(_QWORD *)(v8 + 72) = 0;
  *(_QWORD *)(v8 + 80) = 0;
  *(_QWORD *)(v8 + 88) = 0;
  *(_QWORD *)(v8 + 96) = 0;
  *(_QWORD *)(v8 + 104) = 0;
  v11 = *(unsigned int *)(v8 + 392);
  if ( (_DWORD)v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v11);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_939241f3766634594ecc55fb100debfa_Traceguids);
  }
  v12 = *(RTL_SRWLOCK **)(v8 + 40);
  AcquireSRWLockExclusive(v12 + 2);
  v12[4].Ptr = RemoteSubscription::CancelCallback;
  v12[5].Ptr = (PVOID)v8;
  ReleaseSRWLockExclusive(v12 + 2);
  v13 = (MergedLogQueryResult *)operator new(0x70u);
  v75 = v13;
  if ( v13 )
  {
    v14 = MergedLogQueryResult::MergedLogQueryResult(v13, *(struct OperationControl **)(v8 + 40), 0);
    v15 = v14;
    if ( v14 )
      _InterlockedIncrement((volatile signed __int32 *)v14 + 2);
  }
  else
  {
    v15 = 0;
  }
  wmi::AutoRef<PublisherMetadata>::Release(v8 + 272);
  *(_QWORD *)(v8 + 272) = v15;
  QueryXmlParser::QueryXmlParser((QueryXmlParser *)v86, v72, v8 + 240, v74);
  if ( !*(_QWORD *)(v8 + 264) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, 15001);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x3A99u, v16, 259);
    throw (EvtException *)pExceptionObject;
  }
  v17 = *(_QWORD *)(v8 + 256);
  v64 = v17;
  v75 = (MergedLogQueryResult *)(v8 + 240);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  while ( (MergedLogQueryResult *)v17 != v9 )
  {
    try
    {
      v77 = v17 + 56;
      *(_QWORD *)&v69 = *(_QWORD *)(v17 + 24);
      *((_QWORD *)&v69 + 1) = (__int64)(*(_QWORD *)(v17 + 32) - v69) >> 1;
      v92 = si128;
      *(_QWORD *)&v93 = -1;
      v80 = v69;
      LogQueryResultForChannel = ChannelManager::GetLogQueryResultForChannel(*(_QWORD *)(v8 + 24), Name, &v80);
      utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::operator=(
        &v92,
        LogQueryResultForChannel);
      utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::_Uninit(Name);
      v26 = BYTE2(v61);
    }
    catch ( EvtException *v82 )
    {
      if ( (v63 & 0x1000) == 0 )
        throw;
      v50 = operator new(0x50u);
      v79 = v50;
      v51 = v69;
      if ( v50 )
      {
        v81 = v69;
        v52 = (volatile signed __int32 *)EvtxFile::EvtxFile((__int64)v50, 0, 0, &v81, 0);
      }
      else
      {
        v52 = 0;
      }
      v66 = (const WCHAR *)v52;
      if ( v52 )
        _InterlockedIncrement(v52 + 2);
      v53 = v68;
      (*(void (__fastcall **)(volatile signed __int32 *, __int64 *, _QWORD, __int64, __int64))(*(_QWORD *)v52 + 8LL))(
        v52,
        &v70,
        *(_QWORD *)(v53 + 40),
        v77,
        v53 + 336);
      v61 = *((_DWORD *)v82 + 6);
      v76 = v51;
      v54 = MakeOrThrowOOM(Name);
      v55 = v62 | 1;
      v62 |= 1u;
      v57 = !(unsigned __int8)utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>>::emplace_back<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,unsigned long,0>(
                                v65,
                                v54,
                                &v61)
         || !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                                v53 + 280,
                                &v69);
      if ( (v55 & 1) != 0 )
      {
        v62 = v55 & 0xFFFFFFFE;
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Name);
      }
      if ( v57 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)v84, 0xEu, v56, 290);
        throw (EvtException *)v84;
      }
      MergedLogQueryResult::AddQueryResult(*(_QWORD *)(v53 + 272), &v70);
      v58 = v92.m128i_i64[1];
      v92.m128i_i64[1] = v92.m128i_i64[0];
      utl::_RangeDestroyApc<utl::allocator<wmi::AutoRef<LogQueryResult>>>(
        v59,
        v92.m128i_i64[1],
        (v58 - v92.m128i_i64[1]) >> 3);
      wmi::AutoRef<PublisherMetadata>::Release(&v70);
      wmi::AutoRef<PublisherMetadata>::Release(&v66);
      v10 = -1;
      v17 = v64;
      v9 = v75;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v66 = (const WCHAR *)v78;
      v8 = v68;
      v26 = BYTE2(v63);
      v61 = v63;
    }
    for ( i = v92.m128i_i64[0]; i != v92.m128i_i64[1]; i += 8 )
    {
      v21 = *(_QWORD *)i;
      v22 = *(const WCHAR **)(*(_QWORD *)i + 16LL);
      Src = v22;
      v91 = (__int64)(*(_QWORD *)(v21 + 24) - (_QWORD)v22) >> 1;
      v23 = v91;
      *(_BYTE *)(v21 + 70) = v26 & 1;
      LODWORD(v64) = 0;
      v88 = v22;
      v89 = v23;
      v24 = MakeOrThrowOOM(Name);
      if ( !(unsigned __int8)utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>>::emplace_back<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,long,0>(
                               v65,
                               v24,
                               &v64)
        || (v60 = 0,
            !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                                v8 + 280,
                                &Src)) )
      {
        v60 = 1;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Name);
      if ( v60 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)v85, 0xEu, v25, 307);
        throw (EvtException *)v85;
      }
      v62 &= ~2u;
      MergedLogQueryResult::AddQueryResult(*(_QWORD *)(v8 + 272), i);
      v26 = BYTE2(v61);
    }
    utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::_Uninit(&v92);
    LOBYTE(v27) = 1;
    v28 = utl::_TreeNodeHeader<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<unsigned long,QueryNode,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,QueryNode>>>>>::_Traverse(
            v17,
            v27);
    v17 = v28;
    v64 = v28;
  }
  v29 = *(_DWORD *)(v8 + 404) & 3;
  v30 = *(MergedLogQueryResult **)(v8 + 272);
  if ( v29 == 3 )
  {
    v31 = v61;
    v32 = v67;
    MergedLogQueryResult::Seek(v30, 0, v67, v61 & 0x10000 | 4);
    MergedLogQueryResult::NextRecord(*(MergedLogQueryResult **)(v8 + 272));
    if ( !MergedLogQueryResult::IsEof(*(MergedLogQueryResult **)(v8 + 272)) )
      *(_BYTE *)(v8 + 412) = 1;
  }
  else
  {
    if ( v29 == 2 )
    {
      MergedLogQueryResult::SeekToBof(v30);
      *(_BYTE *)(v8 + 412) = 1;
    }
    else
    {
      MergedLogQueryResult::SeekToEof(v30);
      *(_BYTE *)(v8 + 412) = 0;
    }
    v32 = v67;
    v31 = v61;
  }
  if ( MergedLogQueryResult::GetReadDirection(*(MergedLogQueryResult **)(v8 + 272)) )
    MergedLogQueryResult::SwitchReadDirection(v33);
  MergedLogQueryResult::GetBookmark(*(_QWORD *)(v8 + 272), v8 + 304, v8 + 400);
  v79 = (void *)(v8 + 48);
  AcquireSRWLockExclusive((PSRWLOCK)(v8 + 48));
  ChannelManager::RegisterSubscription(*(PSRWLOCK *)(v8 + 24));
  ReleaseSRWLockExclusive((PSRWLOCK)(v8 + 48));
  _InterlockedIncrement(&g_ActiveSubscriptionCount);
  v34 = (v31 & 0x10000000) != 0;
  v35 = v71;
  if ( !v32 )
    v35 = &pszFormat;
  v36 = -1;
  do
    ++v36;
  while ( v35[v36] );
  v37 = v73;
  if ( !v72 )
    v37 = &pszFormat;
  v38 = -1;
  do
    ++v38;
  while ( v37[v38] );
  v39 = v66;
  if ( !v74 )
    v39 = &pszFormat;
  do
    ++v10;
  while ( v39[v10] );
  Src = v35;
  v91 = v36;
  v88 = v37;
  v89 = v38;
  *(_QWORD *)&v76 = v39;
  *((_QWORD *)&v76 + 1) = v10;
  LogSubscriptionRpcTrackingEvent(
    *(_DWORD *)(v8 + 392),
    *(_DWORD *)(v8 + 396),
    (unsigned int)&v76,
    (unsigned int)&v88,
    (__int64)&Src,
    v34);
  try
  {
    std::_Integral_to_string<wchar_t,long>(&v88, *(unsigned int *)(v8 + 396));
    v40 = std::_UIntegral_to_buff<wchar_t,unsigned long>(v94, *(unsigned int *)(v8 + 392));
    std::wstring::wstring(&Src, v40, v94);
    v41 = std::wstring::_Append<wchar_t>(&Src);
    v92 = *(__m128i *)v41;
    v93 = *(_OWORD *)(v41 + 16);
    *(_WORD *)v41 = 0;
    *(_QWORD *)(v41 + 16) = 0;
    *(_QWORD *)(v41 + 24) = 7;
    std::wstring::wstring(Name, v42, &v92, &v88);
    std::wstring::~wstring(&v92);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(&v88);
    v43 = (const WCHAR *)Name;
    if ( Name[3] > (PCWSTR)7 )
      v43 = Name[0];
    Instance = PerfCreateInstance(
                 WevtEventLogCounterProvider,
                 &WevtEventLogSubscriptionsCounterSetGuid,
                 v43,
                 *(_DWORD *)(v8 + 396));
    v45 = *(struct _PERF_COUNTERSET_INSTANCE **)(v8 + 328);
    *(_QWORD *)(v8 + 328) = Instance;
    if ( v45 )
      PerfDeleteInstance(WevtEventLogCounterProvider, v45);
    v46 = *(struct _PERF_COUNTERSET_INSTANCE **)(v8 + 328);
    if ( v46 )
    {
      v47 = PerfSetCounterRefValue(WevtEventLogCounterProvider, v46, 8u, (PVOID)(v8 + 336));
      if ( v47
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v47);
      }
      v48 = PerfSetCounterRefValue(
              WevtEventLogCounterProvider,
              *(PPERF_COUNTERSET_INSTANCE *)(v8 + 328),
              7u,
              (PVOID)(v8 + 344));
      if ( v48
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v48);
      }
    }
    std::wstring::~wstring(Name);
  }
  catch ( std::exception )
  {
    v8 = v68;
  }
  QueryXmlParser::~QueryXmlParser((QueryXmlParser *)v86);
  return v8;
}

```

## disassembly

```asm
0x18004c034  mov     rax, rsp
0x18004c037  mov     [rax+10h], rbx
0x18004c03b  mov     [rax+18h], rsi
0x18004c03f  push    rdi
0x18004c040  push    r12
0x18004c042  push    r13
0x18004c044  push    r14
0x18004c046  push    r15
0x18004c048  sub     rsp, 310h
0x18004c04f  movaps  xmmword ptr [rax-38h], xmm6
0x18004c053  mov     rax, cs:__security_cookie
0x18004c05a  xor     rax, rsp
0x18004c05d  mov     [rsp+338h+var_48], rax
0x18004c065  mov     rax, r9
0x18004c068  mov     [rsp+338h+var_2C0], rax
0x18004c06d  mov     r14, rcx
0x18004c070  mov     [rsp+338h+var_250], rax
0x18004c078  mov     rcx, [rsp+338h+arg_20]
0x18004c080  mov     [rsp+338h+var_280], rcx
0x18004c088  mov     r9, [rsp+338h+arg_28]
0x18004c090  mov     [rsp+338h+var_290], r9
0x18004c098  mov     [rsp+338h+var_2B0], r14
0x18004c0a0  mov     [rsp+338h+var_278], rax
0x18004c0a8  mov     [rsp+338h+var_288], rcx
0x18004c0b0  mov     [rsp+338h+var_2B8], r9
0x18004c0b8  mov     ebx, [rsp+338h+arg_30]
0x18004c0bf  mov     [rsp+338h+var_2E4], ebx
0x18004c0c3  mov     [rsp+338h+var_2D8], ebx
0x18004c0c7  mov     rax, [rsp+338h+arg_38]
0x18004c0cf  mov     [rsp+338h+var_2C8], rax
0x18004c0d4  xor     r15d, r15d
0x18004c0d7  mov     [rsp+338h+var_2E0], r15d
0x18004c0dc  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18004c0e3  mov     [r14], rax
0x18004c0e6  mov     [r14+8], r15d
0x18004c0ea  lea     rax, ??_7RemoteSubscription@@6BRefBase@wmi@@@; const RemoteSubscription::`vftable'{for `wmi::RefBase'}
0x18004c0f1  mov     [r14], rax
0x18004c0f4  lea     rax, ??_7RemoteSubscription@@6BFilterConsumerCallback@@@; const RemoteSubscription::`vftable'{for `FilterConsumerCallback'}
0x18004c0fb  mov     [r14+10h], rax
0x18004c0ff  mov     [r14+18h], rdx
0x18004c103  mov     [r14+20h], r15
0x18004c107  mov     [r14+28h], r8
0x18004c10b  test    r8, r8
0x18004c10e  jz      short loc_18004C115
0x18004c110  lock inc dword ptr [r8+8]
0x18004c115  mov     [r14+30h], r15
0x18004c119  lea     rcx, [r14+70h]; this
0x18004c11d  call    ??0RpcStatusSubscription@RemoteSubscription@@QEAA@W4_RPC_NOTIFICATIONS@@@Z; RemoteSubscription::RpcStatusSubscription::RpcStatusSubscription(_RPC_NOTIFICATIONS)
0x18004c122  nop
0x18004c123  lea     rdi, [r14+0F0h]
0x18004c12a  mov     [rdi], rdi
0x18004c12d  mov     [rdi+8], rdi
0x18004c131  mov     [rdi+10h], rdi
0x18004c135  mov     [rdi+18h], r15
0x18004c139  mov     [r14+110h], r15
0x18004c140  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004c144  mov     [r14+118h], r12
0x18004c14b  mov     [r14+120h], r12
0x18004c152  mov     [r14+128h], r12
0x18004c159  mov     [r14+130h], r12
0x18004c160  mov     [r14+138h], r12
0x18004c167  mov     [r14+140h], r12
0x18004c16e  mov     [r14+148h], r15
0x18004c175  mov     [r14+150h], r15
0x18004c17c  mov     [r14+158h], r15
0x18004c183  mov     [r14+160h], r15d
0x18004c18a  mov     [r14+164h], r15b
0x18004c191  call    ?GetRpcClientPid@@YAKXZ; GetRpcClientPid(void)
0x18004c196  mov     [r14+188h], eax
0x18004c19d  lea     eax, [r12+2]
0x18004c1a2  lock xadd cs:dword_180111674, eax
0x18004c1aa  inc     eax
0x18004c1ac  mov     [r14+18Ch], eax
0x18004c1b3  mov     [r14+194h], ebx
0x18004c1ba  mov     [r14+198h], r15d
0x18004c1c1  mov     [r14+19Ch], r15w
0x18004c1c9  mov     [r14+19Eh], r15b
0x18004c1d0  mov     [r14+38h], r15
0x18004c1d4  mov     [r14+40h], r15
0x18004c1d8  mov     [r14+48h], r15
0x18004c1dc  mov     [r14+50h], r15
0x18004c1e0  mov     [r14+58h], r15
0x18004c1e4  mov     [r14+60h], r15
0x18004c1e8  mov     [r14+68h], r15
0x18004c1ec  mov     r9d, [r14+188h]
0x18004c1f3  test    r9d, r9d
0x18004c1f6  jz      short loc_18004C231
0x18004c1f8  lea     r13, WPP_GLOBAL_Control
0x18004c1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c206  cmp     rcx, r13
0x18004c209  jz      short loc_18004C268
0x18004c20b  test    dword ptr [rcx+1Ch], 100h
0x18004c212  jz      short loc_18004C268
0x18004c214  cmp     byte ptr [rcx+19h], 4
0x18004c218  jb      short loc_18004C268
0x18004c21a  lea     edx, [r12+10h]
0x18004c21f  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x18004c226  mov     rcx, [rcx+10h]
0x18004c22a  call    WPP_SF_d
0x18004c22f  jmp     short loc_18004C268
0x18004c231  lea     r13, WPP_GLOBAL_Control
0x18004c238  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c23f  cmp     rcx, r13
0x18004c242  jz      short loc_18004C268
0x18004c244  test    dword ptr [rcx+1Ch], 100h
0x18004c24b  jz      short loc_18004C268
0x18004c24d  cmp     byte ptr [rcx+19h], 4
0x18004c251  jb      short loc_18004C268
0x18004c253  mov     edx, 10h
0x18004c258  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x18004c25f  mov     rcx, [rcx+10h]
0x18004c263  call    WPP_SF_
0x18004c268  mov     rbx, [r14+28h]
0x18004c26c  lea     rcx, [rbx+10h]; SRWLock
0x18004c270  call    cs:__imp_AcquireSRWLockExclusive
0x18004c276  lea     rax, ?CancelCallback@RemoteSubscription@@CAXPEAX@Z; RemoteSubscription::CancelCallback(void *)
0x18004c27d  mov     [rbx+20h], rax
0x18004c281  mov     [rbx+28h], r14
0x18004c285  lea     rcx, [rbx+10h]; SRWLock
0x18004c289  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c28f  mov     ecx, 70h ; 'p'; dwBytes
0x18004c294  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c299  mov     [rsp+338h+var_270], rax
0x18004c2a1  test    rax, rax
0x18004c2a4  jz      short loc_18004C2C3
0x18004c2a6  xor     r8d, r8d; unsigned int
0x18004c2a9  mov     rdx, [r14+28h]; struct OperationControl *
0x18004c2ad  mov     rcx, rax; this
0x18004c2b0  call    ??0MergedLogQueryResult@@QEAA@PEAVOperationControl@@K@Z; MergedLogQueryResult::MergedLogQueryResult(OperationControl *,ulong)
0x18004c2b5  mov     rbx, rax
0x18004c2b8  test    rax, rax
0x18004c2bb  jz      short loc_18004C2C6
0x18004c2bd  lock inc dword ptr [rax+8]
0x18004c2c1  jmp     short loc_18004C2C6
0x18004c2c3  mov     rbx, r15
0x18004c2c6  lea     rsi, [r14+110h]
0x18004c2cd  mov     rcx, rsi
0x18004c2d0  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18004c2d5  mov     [rsi], rbx
0x18004c2d8  mov     r9, [rsp+338h+var_278]
0x18004c2e0  mov     r8, rdi
0x18004c2e3  mov     rdx, [rsp+338h+var_288]
0x18004c2eb  lea     rcx, [rsp+338h+var_198]; this
0x18004c2f3  call    ??0QueryXmlParser@@QEAA@PEB_WAEAV?$map@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@2@@utl@@@2@@utl@@0@Z; QueryXmlParser::QueryXmlParser(wchar_t const *,utl::map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>>>>> &,wchar_t const *)
0x18004c2f8  nop
0x18004c2f9  cmp     [r14+108h], r15
0x18004c300  jz      loc_18004C901
0x18004c306  mov     rbx, [rdi+10h]
0x18004c30a  mov     [rsp+338h+var_2D0], rbx
0x18004c30f  mov     [rsp+338h+var_270], rdi
0x18004c317  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004c31f  cmp     rbx, rdi
0x18004c322  jz      loc_18004C508
0x18004c328  lea     rdx, [rbx+38h]
0x18004c32c  mov     [rsp+338h+var_258], rdx
0x18004c334  mov     rcx, [rbx+18h]
0x18004c338  mov     [rsp+338h+var_2A8], rcx
0x18004c340  mov     rax, [rbx+20h]
0x18004c344  sub     rax, rcx
0x18004c347  sar     rax, 1
0x18004c34a  mov     [rsp+338h+var_2A0], rax
0x18004c352  movdqu  [rsp+338h+var_78], xmm6
0x18004c35b  mov     qword ptr [rsp+338h+var_68], r12
0x18004c363  mov     [rsp+338h+var_238], rcx
0x18004c36b  mov     [rsp+338h+var_230], rax
0x18004c373  lea     rax, [r14+150h]
0x18004c37a  mov     [rsp+338h+var_2F8], rax
0x18004c37f  mov     [rsp+338h+var_308], rdx
0x18004c384  mov     rax, [r14+28h]
0x18004c388  mov     [rsp+338h+var_310], rax
0x18004c38d  lea     r8, [rsp+338h+var_238]
0x18004c395  lea     rdx, [rsp+338h+Name]
0x18004c39d  mov     rcx, [r14+18h]
0x18004c3a1  call    ?GetLogQueryResultForChannel@ChannelManager@@QEAA?AV?$vector@V?$AutoRef@VLogQueryResult@@@wmi@@V?$allocator@V?$AutoRef@VLogQueryResult@@@wmi@@@utl@@@utl@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_N1PEAVOperationControl@@AEBV?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@3@KAEA_J@Z; ChannelManager::GetLogQueryResultForChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,bool,OperationControl *,utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>> const &,ulong,__int64 &)
0x18004c3a6  mov     rdx, rax
0x18004c3a9  lea     rcx, [rsp+338h+var_78]
0x18004c3b1  call    ??4?$vector@V?$AutoRef@VLogQueryResult@@@wmi@@V?$allocator@V?$AutoRef@VLogQueryResult@@@wmi@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::operator=(utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>> &&)
0x18004c3b6  lea     rcx, [rsp+338h+Name]
0x18004c3be  call    ?_Uninit@?$vector@V?$AutoRef@VLogQueryResult@@@wmi@@V?$allocator@V?$AutoRef@VLogQueryResult@@@wmi@@@utl@@@utl@@AEAAXXZ; utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::_Uninit(void)
0x18004c3c3  nop
0x18004c3c4  mov     eax, [rsp+338h+var_2E4]
0x18004c3c8  jmp     short loc_18004C40A
0x18004c3ca  xor     r15d, r15d
0x18004c3cd  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004c3d1  lea     r13, WPP_GLOBAL_Control
0x18004c3d8  mov     rbx, [rsp+338h+var_2D0]
0x18004c3dd  mov     rdi, [rsp+338h+var_270]
0x18004c3e5  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004c3ed  mov     rax, [rsp+338h+var_250]
0x18004c3f5  mov     [rsp+338h+var_2C0], rax
0x18004c3fa  mov     r14, [rsp+338h+var_2B0]
0x18004c402  mov     eax, [rsp+338h+var_2D8]
0x18004c406  mov     [rsp+338h+var_2E4], eax
0x18004c40a  mov     rsi, qword ptr [rsp+338h+var_78]
0x18004c412  cmp     rsi, qword ptr [rsp+338h+var_78+8]
0x18004c41a  jz      loc_18004C4E4
0x18004c420  mov     rcx, [rsi]
0x18004c423  mov     r8, [rcx+10h]
0x18004c427  mov     [rsp+338h+Src], r8
0x18004c42f  mov     rdx, [rcx+18h]
0x18004c433  sub     rdx, r8
0x18004c436  sar     rdx, 1
0x18004c439  mov     [rsp+338h+var_90], rdx
0x18004c441  shr     eax, 10h
0x18004c444  and     al, 1
0x18004c446  mov     [rcx+46h], al
0x18004c449  mov     dword ptr [rsp+338h+var_2D0], r15d
0x18004c44e  mov     [rsp+338h+var_B8], r8
0x18004c456  mov     [rsp+338h+var_B0], rdx
0x18004c45e  lea     rdx, [rsp+338h+var_B8]
0x18004c466  lea     rcx, [rsp+338h+Name]
0x18004c46e  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18004c473  lea     r8, [rsp+338h+var_2D0]
0x18004c478  mov     rdx, rax
0x18004c47b  mov     rcx, [rsp+338h+var_2C8]
0x18004c480  call    ??$emplace_back@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@J$0A@@?$vector@UQueryChannelInfo@@V?$allocator@UQueryChannelInfo@@@utl@@@utl@@QEAA_N$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAJ@Z; utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>>::emplace_back<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,long,0>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,long &&)
0x18004c485  test    al, al
0x18004c487  jz      short loc_18004C4A6
0x18004c489  lea     rcx, [r14+118h]
0x18004c490  lea     rdx, [rsp+338h+Src]
0x18004c498  call    ??$emplace_back@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@$0A@@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18004c49d  test    al, al
0x18004c49f  mov     [rsp+338h+var_2E8], r15b
0x18004c4a4  jnz     short loc_18004C4AB
0x18004c4a6  mov     [rsp+338h+var_2E8], 1
0x18004c4ab  lea     rcx, [rsp+338h+Name]; void *
0x18004c4b3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18004c4b8  cmp     [rsp+338h+var_2E8], r15b
0x18004c4bd  jnz     loc_18004C964
0x18004c4c3  and     [rsp+338h+var_2E0], 0FFFFFFFDh
0x18004c4c8  mov     rdx, rsi
0x18004c4cb  mov     rcx, [r14+110h]
0x18004c4d2  call    ?AddQueryResult@MergedLogQueryResult@@QEAAX$$QEAV?$AutoRef@VLogQueryResult@@@wmi@@@Z; MergedLogQueryResult::AddQueryResult(wmi::AutoRef<LogQueryResult> &&)
0x18004c4d7  add     rsi, 8
0x18004c4db  mov     eax, [rsp+338h+var_2E4]
0x18004c4df  jmp     loc_18004C412
0x18004c4e4  lea     rcx, [rsp+338h+var_78]
0x18004c4ec  call    ?_Uninit@?$vector@V?$AutoRef@VLogQueryResult@@@wmi@@V?$allocator@V?$AutoRef@VLogQueryResult@@@wmi@@@utl@@@utl@@AEAAXXZ; utl::vector<wmi::AutoRef<LogQueryResult>,utl::allocator<wmi::AutoRef<LogQueryResult>>>::_Uninit(void)
0x18004c4f1  mov     dl, 1
0x18004c4f3  mov     rcx, rbx
0x18004c4f6  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@2@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@2@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>>>>::_Traverse(bool)
0x18004c4fb  mov     rbx, rax
0x18004c4fe  mov     [rsp+338h+var_2D0], rax
0x18004c503  jmp     loc_18004C31F
0x18004c508  mov     eax, [r14+194h]
0x18004c50f  and     eax, 3
0x18004c512  mov     rcx, [r14+110h]; this
0x18004c519  cmp     eax, 3
0x18004c51c  jnz     short loc_18004C568
0x18004c51e  mov     edi, [rsp+338h+var_2E4]
0x18004c522  mov     r9d, edi
0x18004c525  and     r9d, 10000h
0x18004c52c  or      r9d, 4; unsigned int
0x18004c530  mov     rsi, [rsp+338h+var_2B8]
0x18004c538  mov     r8, rsi; wchar_t *
0x18004c53b  xor     edx, edx; __int64
0x18004c53d  call    ?Seek@MergedLogQueryResult@@QEAAX_JPEB_WK@Z; MergedLogQueryResult::Seek(__int64,wchar_t const *,ulong)
0x18004c542  mov     rcx, [r14+110h]; this
0x18004c549  call    ?NextRecord@MergedLogQueryResult@@UEAA_NXZ; MergedLogQueryResult::NextRecord(void)
0x18004c54e  mov     rcx, [r14+110h]; this
0x18004c555  call    ?IsEof@MergedLogQueryResult@@QEAA_NXZ; MergedLogQueryResult::IsEof(void)
0x18004c55a  test    al, al
0x18004c55c  jnz     short loc_18004C594
0x18004c55e  mov     byte ptr [r14+19Ch], 1
0x18004c566  jmp     short loc_18004C594
0x18004c568  cmp     eax, 2
0x18004c56b  jnz     short loc_18004C57C
0x18004c56d  call    ?SeekToBof@MergedLogQueryResult@@UEAAXXZ; MergedLogQueryResult::SeekToBof(void)
0x18004c572  mov     byte ptr [r14+19Ch], 1
0x18004c57a  jmp     short loc_18004C588
0x18004c57c  call    ?SeekToEof@MergedLogQueryResult@@UEAAXXZ; MergedLogQueryResult::SeekToEof(void)
0x18004c581  mov     [r14+19Ch], r15b
0x18004c588  mov     rsi, [rsp+338h+var_2B8]
0x18004c590  mov     edi, [rsp+338h+var_2E4]
0x18004c594  mov     rcx, [r14+110h]; this
0x18004c59b  call    ?GetReadDirection@MergedLogQueryResult@@QEAAKXZ; MergedLogQueryResult::GetReadDirection(void)
0x18004c5a0  test    eax, eax
0x18004c5a2  jz      short loc_18004C5A9
0x18004c5a4  call    ?SwitchReadDirection@MergedLogQueryResult@@QEAAXXZ; MergedLogQueryResult::SwitchReadDirection(void)
0x18004c5a9  lea     r8, [r14+190h]
0x18004c5b0  lea     rdx, [r14+130h]
0x18004c5b7  mov     rcx, [r14+110h]
0x18004c5be  call    ?GetBookmark@MergedLogQueryResult@@QEAAXAEAV?$vector@_JV?$allocator@_J@utl@@@utl@@AEAK@Z; MergedLogQueryResult::GetBookmark(utl::vector<__int64,utl::allocator<__int64>> &,ulong &)
0x18004c5c3  lea     rbx, [r14+30h]
0x18004c5c7  mov     [rsp+338h+var_248], rbx
0x18004c5cf  mov     rcx, rbx; SRWLock
0x18004c5d2  call    cs:__imp_AcquireSRWLockExclusive
0x18004c5d8  nop
0x18004c5d9  mov     r8d, edi
0x18004c5dc  shr     r8d, 0Ch
0x18004c5e0  and     r8b, 1
0x18004c5e4  mov     r9, [rsp+338h+var_2C8]
0x18004c5e9  mov     rdx, r14
0x18004c5ec  mov     rcx, [r14+18h]; SRWLock
0x18004c5f0  call    ?RegisterSubscription@ChannelManager@@QEAAXPEAVRemoteSubscription@@_NAEAV?$vector@UQueryChannelInfo@@V?$allocator@UQueryChannelInfo@@@utl@@@utl@@@Z; ChannelManager::RegisterSubscription(RemoteSubscription *,bool,utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>> &)
0x18004c5f5  nop
0x18004c5f6  mov     rcx, rbx; SRWLock
0x18004c5f9  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c5ff  lock inc cs:?g_ActiveSubscriptionCount@@3JA; long g_ActiveSubscriptionCount
0x18004c606  shr     edi, 1Ch
  ... truncated ...
```
