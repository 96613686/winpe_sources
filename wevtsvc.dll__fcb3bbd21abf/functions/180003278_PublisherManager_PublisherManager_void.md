# PublisherManager::PublisherManager(void)

- ea: `0x180003278`
- end: `0x180003473`
- name: `??0PublisherManager@@QEAA@XZ`
- size: `507`
- prototype: `PublisherManager *__fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800978a0`

## callees

- `0x180003278`
- `0x18000347c`
- `0x180014bd0`
- `0x18002fa38`
- `0x18008d914`
- `0x180091c58`
- `0x180092008`
- `0x180092700`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800032e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800032e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PublisherManager *__fastcall PublisherManager::PublisherManager(_QWORD *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD LastError; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  DWORD v11; // [rsp+38h] [rbp-18h]
  int v12; // [rsp+3Ch] [rbp-14h]
  int v13; // [rsp+40h] [rbp-10h]

  *pv = 0;
  pv[1] = 0;
  pv[2] = 0;
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(pv + 3);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(pv + 7);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pv + 11);
  *((_WORD *)pv + 60) = 0;
  GetLocalComputerDnsName((LPWSTR *)pv + 11);
  ThreadpoolTimer = CreateThreadpoolTimer(PublisherManager::PublisherCacheTimerCallback, pv, 0);
  pv[2] = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = LastError;
    v12 = -1;
    v13 = 54;
    throw (EvtException *)&pExceptionObject;
  }
  TlgRegisterAggregateProviderEx();
  v4 = InitializeSystemTemplates();
  v5 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids, v4);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = v5;
    v12 = -1;
    v13 = 62;
    throw (EvtException *)&pExceptionObject;
  }
  v6 = InitializeEmptyUserTemplate();
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids, v6);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = v7;
    v12 = -1;
    v13 = 68;
    throw (EvtException *)&pExceptionObject;
  }
  return (PublisherManager *)pv;
}

```

## disassembly

```asm
0x180003278  mov     [rsp-8+arg_8], rbx
0x18000327d  mov     [rsp-8+arg_10], rdi
0x180003282  mov     [rsp-8+arg_0], rcx
0x180003287  push    rbp
0x180003288  mov     rbp, rsp
0x18000328b  sub     rsp, 50h
0x18000328f  mov     rdi, rcx
0x180003292  mov     qword ptr [rcx], 0
0x180003299  mov     qword ptr [rcx+8], 0
0x1800032a1  mov     qword ptr [rcx+10h], 0
0x1800032a9  add     rcx, 18h
0x1800032ad  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x1800032b2  nop
0x1800032b3  lea     rcx, [rdi+38h]
0x1800032b7  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x1800032bc  nop
0x1800032bd  lea     rcx, [rdi+58h]; void *
0x1800032c1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800032c6  nop
0x1800032c7  mov     word ptr [rdi+78h], 0
0x1800032cd  lea     rcx, [rdi+58h]
0x1800032d1  call    ?GetLocalComputerDnsName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; GetLocalComputerDnsName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800032d6  xor     r8d, r8d; pcbe
0x1800032d9  mov     rdx, rdi; pv
0x1800032dc  lea     rcx, ?PublisherCacheTimerCallback@PublisherManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800032e3  call    cs:__imp_CreateThreadpoolTimer
0x1800032e9  mov     [rdi+10h], rax
0x1800032ed  test    rax, rax
0x1800032f0  jnz     short loc_18000336F
0x1800032f2  call    cs:__imp_GetLastError
0x1800032f8  mov     ebx, eax
0x1800032fa  mov     eax, 507h
0x1800032ff  test    ebx, ebx
0x180003301  cmovz   ebx, eax
0x180003304  lea     rcx, WPP_GLOBAL_Control
0x18000330b  mov     r10, cs:WPP_GLOBAL_Control
0x180003312  cmp     r10, rcx
0x180003315  jz      short loc_18000333D
0x180003317  test    byte ptr [r10+1Ch], 10h
0x18000331c  jz      short loc_18000333D
0x18000331e  cmp     byte ptr [r10+19h], 2
0x180003323  jb      short loc_18000333D
0x180003325  mov     edx, 0Ah
0x18000332a  mov     r9d, ebx
0x18000332d  lea     r8, WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids
0x180003334  mov     rcx, [r10+10h]
0x180003338  call    WPP_SF_d
0x18000333d  xorps   xmm0, xmm0
0x180003340  movdqu  [rbp+pExceptionObject], xmm0
0x180003345  mov     [rbp+var_20], 0
0x18000334d  mov     [rbp+var_18], ebx
0x180003350  mov     [rbp+var_14], 0FFFFFFFFh
0x180003357  mov     [rbp+var_10], 36h ; '6'
0x18000335e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003365  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003369  call    _CxxThrowException_0
0x18000336f  call    TlgRegisterAggregateProviderEx
0x180003374  call    ?InitializeSystemTemplates@@YAKXZ; InitializeSystemTemplates(void)
0x180003379  mov     ebx, eax
0x18000337b  test    eax, eax
0x18000337d  jz      short loc_1800033EA
0x18000337f  lea     rcx, WPP_GLOBAL_Control
0x180003386  mov     r10, cs:WPP_GLOBAL_Control
0x18000338d  cmp     r10, rcx
0x180003390  jz      short loc_1800033B8
0x180003392  test    byte ptr [r10+1Ch], 10h
0x180003397  jz      short loc_1800033B8
0x180003399  cmp     byte ptr [r10+19h], 2
0x18000339e  jb      short loc_1800033B8
0x1800033a0  mov     edx, 0Bh
0x1800033a5  mov     r9d, eax
0x1800033a8  lea     r8, WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids
0x1800033af  mov     rcx, [r10+10h]
0x1800033b3  call    WPP_SF_d
0x1800033b8  xorps   xmm0, xmm0
0x1800033bb  movdqu  [rbp+pExceptionObject], xmm0
0x1800033c0  mov     [rbp+var_20], 0
0x1800033c8  mov     [rbp+var_18], ebx
0x1800033cb  mov     [rbp+var_14], 0FFFFFFFFh
0x1800033d2  mov     [rbp+var_10], 3Eh ; '>'
0x1800033d9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800033e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800033e4  call    _CxxThrowException_0
0x1800033ea  call    ?InitializeEmptyUserTemplate@@YAKXZ; InitializeEmptyUserTemplate(void)
0x1800033ef  mov     ebx, eax
0x1800033f1  test    eax, eax
0x1800033f3  jz      short loc_180003460
0x1800033f5  lea     rcx, WPP_GLOBAL_Control
0x1800033fc  mov     r10, cs:WPP_GLOBAL_Control
0x180003403  cmp     r10, rcx
0x180003406  jz      short loc_18000342E
0x180003408  test    byte ptr [r10+1Ch], 10h
0x18000340d  jz      short loc_18000342E
0x18000340f  cmp     byte ptr [r10+19h], 2
0x180003414  jb      short loc_18000342E
0x180003416  mov     edx, 0Ch
0x18000341b  mov     r9d, eax
0x18000341e  lea     r8, WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids
0x180003425  mov     rcx, [r10+10h]
0x180003429  call    WPP_SF_d
0x18000342e  xorps   xmm0, xmm0
0x180003431  movdqu  [rbp+pExceptionObject], xmm0
0x180003436  mov     [rbp+var_20], 0
0x18000343e  mov     [rbp+var_18], ebx
0x180003441  mov     [rbp+var_14], 0FFFFFFFFh
0x180003448  mov     [rbp+var_10], 44h ; 'D'
0x18000344f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003456  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000345a  call    _CxxThrowException_0
0x180003460  mov     rax, rdi
0x180003463  mov     rbx, [rsp+50h+arg_8]
0x180003468  mov     rdi, [rsp+50h+arg_10]
0x18000346d  add     rsp, 50h
0x180003471  pop     rbp
0x180003472  retn
```
