# GetNtsInfoIfReady(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,NtsKeTelemetryInfo &)

- ea: `0x180054058`
- end: `0x180054505`
- name: `?GetNtsInfoIfReady@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUNtsKeTelemetryInfo@@@Z`
- size: `1197`
- prototype: `__int64 __fastcall(_QWORD *, struct NtsKeTelemetryInfo *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054690`

## callees

- `0x180016454`
- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a320`
- `0x18003a6b8`
- `0x18003ad30`
- `0x18003d270`
- `0x18003d294`
- `0x18003dd2c`
- `0x18003f49d`
- `0x180041384`
- `0x1800425c8`
- `0x180045abc`
- `0x180048cac`
- `0x180051c48`
- `0x180052354`
- `0x180052428`
- `0x180052b4c`
- `0x180053158`
- `0x1800532a4`
- `0x180053484`
- `0x180053524`
- `0x180053710`
- `0x180054058`
- `0x18005450c`
- `0x180056264`
- `0x180056b14`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054255`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054265`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054255`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054265`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800543cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800543cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180054113`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180054132`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180054113`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180054132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005444d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005444d`

## string_xrefs

- `0x180054498`: `onecore\ds\security\services\w32time\nts\nts.cpp`
- `0x1800541b3`: `GetNtsInfoIfReady: server %s not found in infopairs, kicking off KE\n`
- `0x1800540f4`: `GetNtsInfoIfReady: Server %s has no keyExchangeCompleteEvent\n`
- `0x180054185`: `GetNtsInfoIfReady: We need to wait for server %s to finish a KE request.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetNtsInfoIfReady(_QWORD *a1, struct NtsKeTelemetryInfo *a2)
{
  struct NtsForNtpInfoInternal *v4; // rbx
  void *v5; // rdi
  unsigned int NtsInfoWhenSignaled; // ebx
  DWORD v7; // eax
  __int64 v8; // r8
  const char *v9; // r9
  _QWORD *v10; // rdx
  char *v11; // rbx
  __int64 v12; // rcx
  NtsKeyExchangeCallbackContext *v13; // rdx
  _QWORD *v14; // r15
  __int64 *v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // rsi
  char *v18; // rdi
  size_t v19; // rbx
  HANDLE EventW; // rax
  __int64 v21; // rcx
  char v22; // al
  __int64 v23; // rdx
  __int128 v24; // xmm0
  int v25; // edx
  char *v26; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  int v28; // eax
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h]
  __int64 Src; // [rsp+48h] [rbp-B8h] BYREF
  char v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+51h] [rbp-AFh]
  __int16 v36; // [rsp+55h] [rbp-ABh]
  char v37; // [rsp+57h] [rbp-A9h]
  _BYTE v38[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v39[128]; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+F8h] [rbp-8h]
  int v41; // [rsp+FCh] [rbp-4h]
  ULONGLONG v42; // [rsp+100h] [rbp+0h]
  ULONGLONG TickCount64; // [rsp+108h] [rbp+8h]
  __int64 v44; // [rsp+110h] [rbp+10h]
  char v45; // [rsp+118h] [rbp+18h]
  int v46; // [rsp+119h] [rbp+19h]
  __int16 v47; // [rsp+11Dh] [rbp+1Dh]
  char v48; // [rsp+11Fh] [rbp+1Fh]
  __int64 v49; // [rsp+120h] [rbp+20h]
  _QWORD v50[3]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v51[16]; // [rsp+140h] [rbp+40h] BYREF
  PVOID pv; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h] BYREF
  __int64 v54; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::critical_section::lock(&g_NtsState, &v30);
  std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
    &qword_1800A4928,
    &Src,
    a1);
  if ( Src != qword_1800A4928 )
  {
    v4 = (struct NtsForNtpInfoInternal *)(Src + 64);
    v5 = *(void **)(Src + 328);
    if ( !v5 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(L"GetNtsInfoIfReady: Server %s has no keyExchangeCompleteEvent\n");
      NtsInfoWhenSignaled = -2147024890;
      goto LABEL_36;
    }
    v7 = WaitForSingleObjectEx(*(HANDLE *)(Src + 328), 0, 0);
    if ( v7 != 258 )
    {
      if ( v7 || WaitForSingleObjectEx(v5, 0, 0) )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v8, v9);
      NtsInfoWhenSignaled = GetNtsInfoWhenSignaled(v4, a2);
      goto LABEL_36;
    }
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(L"GetNtsInfoIfReady: We need to wait for server %s to finish a KE request.\n", a1);
    }
    goto LABEL_38;
  }
  if ( (unsigned __int8)FileLogAllowEntry(200) )
  {
    if ( a1[3] <= 7u )
      v10 = a1;
    else
      v10 = (_QWORD *)*a1;
    FileLogAdd(L"GetNtsInfoIfReady: server %s not found in infopairs, kicking off KE\n", v10);
  }
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  std::wstring::wstring(v38);
  memset_0(v39, 0, sizeof(v39));
  v40 = 123;
  v41 = 0xFFFF;
  v42 = 0;
  TickCount64 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v50);
  std::set<std::array<unsigned char,32>>::set<std::array<unsigned char,32>>(v51);
  pv = 0;
  v53 = 0;
  v54 = 0;
  std::wstring::operator=(v38, a1);
  TickCount64 = GetTickCount64();
  v42 = GetTickCount64();
  v11 = (char *)operator new(0x50u);
  v31[0] = v11;
  memset_0(v11, 0, 0x50u);
  std::wstring::wstring(v11);
  v11[32] = 0;
  *(_OWORD *)(v11 + 33) = 0;
  *(_DWORD *)(v11 + 49) = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v11 + 7);
  Src = 0;
  v13 = (NtsKeyExchangeCallbackContext *)pv;
  pv = v11;
  if ( v13 )
    std::default_delete<NtsKeyExchangeCallbackContext>::operator()(v12, v13);
  std::unique_ptr<NtsKeyExchangeCallbackContext>::~unique_ptr<NtsKeyExchangeCallbackContext>(&Src);
  std::wstring::operator=(pv, a1);
  if ( qword_1800A4950 != qword_1800A4958 )
  {
    std::vector<unsigned short>::operator=((char *)pv + 56, &qword_1800A4950);
    goto LABEL_29;
  }
  Src = 0x3000100040002LL;
  v14 = pv;
  v15 = (__int64 *)*((_QWORD *)pv + 7);
  if ( (unsigned __int64)((__int64)(*((_QWORD *)pv + 9) - (_QWORD)v15) >> 1) >= 4 )
  {
    v16 = (__int64)(*((_QWORD *)pv + 8) - (_QWORD)v15) >> 1;
    if ( v16 < 4 )
    {
      v17 = 2 * v16;
      memmove_0(v15, &Src, 2 * v16);
      v18 = (char *)v14[8];
      v19 = 2 * (4 - v16);
      memmove_0(v18, (char *)&Src + v17, v19);
      v14[8] = &v18[v19];
      goto LABEL_29;
    }
  }
  else
  {
    std::vector<unsigned short>::_Clear_and_reserve_geometric((char *)pv + 56, 4);
    v15 = (__int64 *)v14[7];
  }
  *v15 = Src;
  v14[8] = v15 + 1;
LABEL_29:
  EventW = CreateEventW(0, 1, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v53,
    EventW);
  if ( byte_1800A4948 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::array<unsigned char,20>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::array<unsigned char,20>>>,0>>::_Find_lower_bound<std::wstring>(
      &qword_1800A4938,
      v31,
      a1);
    v22 = std::_Tree<std::_Tmap_traits<std::wstring,std::array<unsigned char,20>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::array<unsigned char,20>>>,0>>::_Lower_bound_duplicate<std::wstring>(
            v21,
            v32,
            a1);
    v23 = qword_1800A4938;
    if ( v22 )
      v23 = v32;
    if ( v23 != qword_1800A4938 )
    {
      *((_BYTE *)pv + 32) = 1;
      v24 = *(_OWORD *)(v23 + 64);
      v25 = *(_DWORD *)(v23 + 80);
      v26 = (char *)pv;
      *(_OWORD *)((char *)pv + 33) = v24;
      *(_DWORD *)(v26 + 49) = v25;
    }
  }
  ThreadpoolTimer = CreateThreadpoolTimer(NtsKeyExchangeCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &v54,
    ThreadpoolTimer);
  std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::_Emplace<std::wstring &,NtsForNtpInfoInternal>(
    &qword_1800A4928,
    v31,
    v38,
    &v34);
  v28 = CommenceNtsKE(a1);
  NtsInfoWhenSignaled = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
      (const char *)(unsigned int)v28,
      0);
    NtsForNtpInfoInternal::~NtsForNtpInfoInternal((NtsForNtpInfoInternal *)&v34);
LABEL_36:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
    return NtsInfoWhenSignaled;
  }
  NtsForNtpInfoInternal::~NtsForNtpInfoInternal((NtsForNtpInfoInternal *)&v34);
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
  return 2147483658LL;
}

```

## disassembly

```asm
0x180054058  mov     [rsp-8+arg_10], rbx
0x18005405d  push    rbp
0x18005405e  push    rsi
0x18005405f  push    rdi
0x180054060  push    r12
0x180054062  push    r13
0x180054064  push    r14
0x180054066  push    r15
0x180054068  lea     rbp, [rsp-80h]
0x18005406d  sub     rsp, 180h
0x180054074  mov     rax, cs:__security_cookie
0x18005407b  xor     rax, rsp
0x18005407e  mov     [rbp+0B0h+var_40], rax
0x180054082  mov     rsi, rdx
0x180054085  mov     r14, rcx
0x180054088  xor     r13d, r13d
0x18005408b  mov     [rsp+1B0h+var_190], r13d
0x180054090  lea     rdx, [rsp+1B0h+var_188]
0x180054095  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x18005409c  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x1800540a1  nop
0x1800540a2  mov     r8, r14
0x1800540a5  lea     rdx, [rsp+1B0h+Src]
0x1800540aa  lea     rcx, qword_1800A4928
0x1800540b1  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x1800540b6  mov     rax, [rsp+1B0h+Src]
0x1800540bb  cmp     rax, cs:qword_1800A4928
0x1800540c2  jz      loc_180054196
0x1800540c8  lea     rbx, [rax+40h]
0x1800540cc  mov     rdi, [rbx+108h]
0x1800540d3  test    rdi, rdi
0x1800540d6  jnz     short loc_18005410B
0x1800540d8  mov     ecx, 0C8h
0x1800540dd  call    FileLogAllowEntry
0x1800540e2  test    al, al
0x1800540e4  jz      short loc_180054101
0x1800540e6  lea     rdx, [rbx+8]
0x1800540ea  cmp     qword ptr [rdx+18h], 7
0x1800540ef  jbe     short loc_1800540F4
0x1800540f1  mov     rdx, [rdx]
0x1800540f4  lea     rcx, aGetntsinfoifre_1; "GetNtsInfoIfReady: Server %s has no key"...
0x1800540fb  call    FileLogAdd
0x180054100  nop
0x180054101  mov     ebx, 80070006h
0x180054106  jmp     loc_1800544B5
0x18005410b  xor     r8d, r8d; bAlertable
0x18005410e  xor     edx, edx; dwMilliseconds
0x180054110  mov     rcx, rdi; hHandle
0x180054113  call    cs:__imp_WaitForSingleObjectEx
0x18005411a  nop     dword ptr [rax+rax+00h]
0x18005411f  cmp     eax, 102h
0x180054124  jz      short loc_180054166
0x180054126  test    eax, eax
0x180054128  jnz     short loc_180054154
0x18005412a  xor     r8d, r8d; bAlertable
0x18005412d  xor     edx, edx; dwMilliseconds
0x18005412f  mov     rcx, rdi; hHandle
0x180054132  call    cs:__imp_WaitForSingleObjectEx
0x180054139  nop     dword ptr [rax+rax+00h]
0x18005413e  test    eax, eax
0x180054140  jnz     short loc_180054154
0x180054142  mov     rdx, rsi; struct NtsKeTelemetryInfo *
0x180054145  mov     rcx, rbx; struct NtsForNtpInfoInternal *
0x180054148  call    ?GetNtsInfoWhenSignaled@@YAJAEAUNtsForNtpInfoInternal@@AEAUNtsKeTelemetryInfo@@@Z; GetNtsInfoWhenSignaled(NtsForNtpInfoInternal &,NtsKeTelemetryInfo &)
0x18005414d  mov     ebx, eax
0x18005414f  jmp     loc_1800544B5
0x180054154  mov     rcx, [rbp+0B8h]; this
0x18005415b  mov     edx, 0B07h; void *
0x180054160  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180054166  mov     ecx, 0C8h
0x18005416b  call    FileLogAllowEntry
0x180054170  test    al, al
0x180054172  jz      loc_1800544CE
0x180054178  cmp     qword ptr [r14+18h], 7
0x18005417d  jbe     short loc_180054182
0x18005417f  mov     r14, [r14]
0x180054182  mov     rdx, r14
0x180054185  lea     rcx, aGetntsinfoifre_0; "GetNtsInfoIfReady: We need to wait for "...
0x18005418c  call    FileLogAdd
0x180054191  jmp     loc_1800544CE
0x180054196  mov     ecx, 0C8h
0x18005419b  call    FileLogAllowEntry
0x1800541a0  test    al, al
0x1800541a2  jz      short loc_1800541BF
0x1800541a4  cmp     qword ptr [r14+18h], 7
0x1800541a9  jbe     short loc_1800541B0
0x1800541ab  mov     rdx, [r14]
0x1800541ae  jmp     short loc_1800541B3
0x1800541b0  mov     rdx, r14
0x1800541b3  lea     rcx, aGetntsinfoifre; "GetNtsInfoIfReady: server %s not found "...
0x1800541ba  call    FileLogAdd
0x1800541bf  mov     [rsp+1B0h+var_160], r13b
0x1800541c4  xor     eax, eax
0x1800541c6  mov     [rsp+1B0h+var_15F], eax
0x1800541ca  mov     [rsp+1B0h+var_15B], ax
0x1800541cf  mov     [rsp+1B0h+var_159], al
0x1800541d3  lea     rcx, [rsp+1B0h+var_158]
0x1800541d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800541dd  nop
0x1800541de  xor     edx, edx; Val
0x1800541e0  mov     r8d, 80h; Size
0x1800541e6  lea     rcx, [rsp+1B0h+var_138]; void *
0x1800541eb  call    memset_0
0x1800541f0  mov     [rbp+0B0h+var_B8], 7Bh ; '{'
0x1800541f7  mov     [rbp+0B0h+var_B4], 0FFFFh
0x1800541fe  mov     [rbp+0B0h+var_B0], r13
0x180054202  mov     [rbp+0B0h+var_A8], r13
0x180054206  mov     [rbp+0B0h+var_A0], r13
0x18005420a  mov     [rbp+0B0h+var_98], r13b
0x18005420e  xor     eax, eax
0x180054210  mov     [rbp+0B0h+var_97], eax
0x180054213  mov     [rbp+0B0h+var_93], ax
0x180054217  mov     [rbp+0B0h+var_91], al
0x18005421a  mov     [rbp+0B0h+var_90], r13
0x18005421e  lea     rcx, [rbp+0B0h+var_88]
0x180054222  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180054227  nop
0x180054228  lea     rcx, [rbp+0B0h+var_70]
0x18005422c  call    ??0?$set@V?$array@E$0CA@@std@@U?$less@V?$array@E$0CA@@std@@@2@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@QEAA@XZ; std::set<std::array<uchar,32>>::set<std::array<uchar,32>>(void)
0x180054231  nop
0x180054232  mov     [rbp+0B0h+pv], r13
0x180054236  xor     eax, eax
0x180054238  mov     [rbp+0B0h+var_58], rax
0x18005423c  mov     [rbp+0B0h+var_58], r13
0x180054240  mov     [rbp+0B0h+var_50], rax
0x180054244  mov     [rbp+0B0h+var_50], r13
0x180054248  mov     rdx, r14
0x18005424b  lea     rcx, [rsp+1B0h+var_158]
0x180054250  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180054255  call    cs:__imp_GetTickCount64
0x18005425c  nop     dword ptr [rax+rax+00h]
0x180054261  mov     [rbp+0B0h+var_A8], rax
0x180054265  call    cs:__imp_GetTickCount64
0x18005426c  nop     dword ptr [rax+rax+00h]
0x180054271  mov     [rbp+0B0h+var_B0], rax
0x180054275  mov     edi, 50h ; 'P'
0x18005427a  mov     ecx, edi; Size
0x18005427c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054281  mov     rbx, rax
0x180054284  mov     [rsp+1B0h+var_180], rax
0x180054289  mov     r8d, edi; Size
0x18005428c  xor     edx, edx; Val
0x18005428e  mov     rcx, rax; void *
0x180054291  call    memset_0
0x180054296  mov     rcx, rbx
0x180054299  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005429e  nop
0x18005429f  mov     [rbx+20h], r13b
0x1800542a3  xorps   xmm0, xmm0
0x1800542a6  xor     eax, eax
0x1800542a8  movups  xmmword ptr [rbx+21h], xmm0
0x1800542ac  mov     [rbx+31h], eax
0x1800542af  lea     rcx, [rbx+38h]
0x1800542b3  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800542b8  nop
0x1800542b9  mov     [rsp+1B0h+Src], rbx
0x1800542be  mov     edi, 1
0x1800542c3  mov     [rsp+1B0h+var_190], edi
0x1800542c7  mov     [rsp+1B0h+Src], r13
0x1800542cc  mov     rdx, [rbp+0B0h+pv]
0x1800542d0  mov     [rbp+0B0h+pv], rbx
0x1800542d4  test    rdx, rdx
0x1800542d7  jz      short loc_1800542DE
0x1800542d9  call    ??R?$default_delete@UNtsKeyExchangeCallbackContext@@@std@@QEBAXPEAUNtsKeyExchangeCallbackContext@@@Z; std::default_delete<NtsKeyExchangeCallbackContext>::operator()(NtsKeyExchangeCallbackContext *)
0x1800542de  mov     eax, edi
0x1800542e0  and     eax, 0FFFFFFFEh
0x1800542e3  mov     [rsp+1B0h+var_190], eax; int
0x1800542e7  lea     rcx, [rsp+1B0h+Src]
0x1800542ec  call    ??1?$unique_ptr@UNtsKeyExchangeCallbackContext@@U?$default_delete@UNtsKeyExchangeCallbackContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<NtsKeyExchangeCallbackContext>::~unique_ptr<NtsKeyExchangeCallbackContext>(void)
0x1800542f1  mov     rdx, r14
0x1800542f4  mov     rcx, [rbp+0B0h+pv]
0x1800542f8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800542fd  mov     rax, cs:qword_1800A4958
0x180054304  cmp     cs:qword_1800A4950, rax
0x18005430b  jnz     loc_1800543AD
0x180054311  mov     dword ptr [rsp+1B0h+Src], 40002h
0x180054319  mov     r12d, 4
0x18005431f  mov     dword ptr [rsp+1B0h+Src+4], 30001h
0x180054327  mov     r15, [rbp+0B0h+pv]
0x18005432b  mov     rcx, [r15+38h]; void *
0x18005432f  mov     rax, [r15+48h]
0x180054333  sub     rax, rcx
0x180054336  sar     rax, 1
0x180054339  cmp     rax, r12
0x18005433c  jnb     short loc_180054360
0x18005433e  mov     edx, r12d
0x180054341  lea     rcx, [r15+38h]
0x180054345  call    ?_Clear_and_reserve_geometric@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Clear_and_reserve_geometric(unsigned __int64)
0x18005434a  mov     rcx, [r15+38h]
0x18005434e  mov     rax, [rsp+1B0h+Src]
0x180054353  mov     [rcx], rax
0x180054356  lea     rax, [rcx+8]
0x18005435a  mov     [r15+40h], rax
0x18005435e  jmp     short loc_1800543C1
0x180054360  mov     rbx, [r15+40h]
0x180054364  sub     rbx, rcx
0x180054367  sar     rbx, 1
0x18005436a  cmp     rbx, r12
0x18005436d  jnb     short loc_18005434E
0x18005436f  lea     rsi, [rbx+rbx]
0x180054373  mov     r8, rsi; Size
0x180054376  lea     rdx, [rsp+1B0h+Src]; Src
0x18005437b  call    memmove_0
0x180054380  mov     rdi, [r15+40h]
0x180054384  sub     r12, rbx
0x180054387  lea     rbx, [r12+r12]
0x18005438b  lea     rdx, [rsp+1B0h+Src]
0x180054390  add     rdx, rsi; Src
0x180054393  mov     r8, rbx; Size
0x180054396  mov     rcx, rdi; void *
0x180054399  call    memmove_0
0x18005439e  lea     rax, [rbx+rdi]
0x1800543a2  mov     [r15+40h], rax
0x1800543a6  mov     edi, 1
0x1800543ab  jmp     short loc_1800543C1
0x1800543ad  mov     rcx, [rbp+0B0h+pv]
0x1800543b1  add     rcx, 38h ; '8'
0x1800543b5  lea     rdx, qword_1800A4950
0x1800543bc  call    ??4?$vector@GV?$allocator@G@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<ushort>::operator=(std::vector<ushort> const &)
0x1800543c1  xor     r9d, r9d; lpName
0x1800543c4  xor     r8d, r8d; bInitialState
0x1800543c7  mov     edx, edi; bManualReset
0x1800543c9  xor     ecx, ecx; lpEventAttributes
0x1800543cb  call    cs:__imp_CreateEventW
0x1800543d2  nop     dword ptr [rax+rax+00h]
0x1800543d7  mov     rdx, rax
0x1800543da  lea     rcx, [rbp+0B0h+var_58]
0x1800543de  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800543e3  cmp     cs:byte_1800A4948, r13b
0x1800543ea  jz      short loc_18005443F
0x1800543ec  mov     r8, r14
0x1800543ef  lea     rdx, [rsp+1B0h+var_180]
0x1800543f4  lea     rcx, qword_1800A4938
0x1800543fb  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::array<uchar,20>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::array<uchar,20>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180054400  mov     r8, r14
0x180054403  mov     rdx, [rsp+1B0h+var_170]
0x180054408  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$array@E$0BE@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::array<uchar,20>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::array<uchar,20>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::array<uchar,20>>,void *> * const,std::wstring const &)
0x18005440d  mov     rdx, cs:qword_1800A4938
0x180054414  test    al, al
0x180054416  cmovnz  rdx, [rsp+1B0h+var_170]
0x18005441c  cmp     rdx, cs:qword_1800A4938
0x180054423  jz      short loc_18005443F
0x180054425  mov     rax, [rbp+0B0h+pv]
0x180054429  mov     [rax+20h], dil
0x18005442d  movups  xmm0, xmmword ptr [rdx+40h]
0x180054431  mov     edx, [rdx+50h]
0x180054434  mov     rax, [rbp+0B0h+pv]
0x180054438  movups  xmmword ptr [rax+21h], xmm0
0x18005443c  mov     [rax+31h], edx
0x18005443f  xor     r8d, r8d; pcbe
0x180054442  mov     rdx, [rbp+0B0h+pv]; pv
0x180054446  lea     rcx, ?NtsKeyExchangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005444d  call    cs:__imp_CreateThreadpoolTimer
0x180054454  nop     dword ptr [rax+rax+00h]
0x180054459  mov     rdx, rax
0x18005445c  lea     rcx, [rbp+0B0h+var_50]
0x180054460  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180054465  lea     r9, [rsp+1B0h+var_160]
0x18005446a  lea     r8, [rsp+1B0h+var_158]
0x18005446f  lea     rdx, [rsp+1B0h+var_180]
0x180054474  lea     rcx, qword_1800A4928
0x18005447b  call    ??$_Emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@PEAX@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAUNtsForNtpInfoInternal@@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::_Emplace<std::wstring &,NtsForNtpInfoInternal>(std::wstring &,NtsForNtpInfoInternal &&)
0x180054480  mov     rcx, r14
0x180054483  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x180054488  mov     ebx, eax
0x18005448a  test    eax, eax
0x18005448c  jns     short loc_1800544C3
0x18005448e  mov     rcx, [rbp+0B8h]; this
0x180054495  mov     r9d, eax; char *
0x180054498  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\w32tim"...
0x18005449f  mov     edx, 26Bh; void *
0x1800544a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800544a9  nop
0x1800544aa  lea     rcx, [rsp+1B0h+var_160]; this
0x1800544af  call    ??1NtsForNtpInfoInternal@@QEAA@XZ; NtsForNtpInfoInternal::~NtsForNtpInfoInternal(void)
0x1800544b4  nop
0x1800544b5  lea     rcx, [rsp+1B0h+var_188]
0x1800544ba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800544bf  mov     eax, ebx
0x1800544c1  jmp     short loc_1800544DD
0x1800544c3  lea     rcx, [rsp+1B0h+var_160]; this
0x1800544c8  call    ??1NtsForNtpInfoInternal@@QEAA@XZ; NtsForNtpInfoInternal::~NtsForNtpInfoInternal(void)
0x1800544cd  nop
0x1800544ce  lea     rcx, [rsp+1B0h+var_188]
0x1800544d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800544d8  mov     eax, 8000000Ah
0x1800544dd  mov     rcx, [rbp+0B0h+var_40]
0x1800544e1  xor     rcx, rsp; StackCookie
0x1800544e4  call    __security_check_cookie
0x1800544e9  mov     rbx, [rsp+1B0h+arg_10]
0x1800544f1  add     rsp, 180h
0x1800544f8  pop     r15
0x1800544fa  pop     r14
0x1800544fc  pop     r13
0x1800544fe  pop     r12
0x180054500  pop     rdi
0x180054501  pop     rsi
0x180054502  pop     rbp
0x180054503  retn
```
