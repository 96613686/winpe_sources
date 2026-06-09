# EventService::EventService(bool,bool)

- ea: `0x1800978a0`
- end: `0x180097ed1`
- name: `??0EventService@@QEAA@_N0@Z`
- size: `1585`
- prototype: `EventService *__fastcall(EventService *this, char, char)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a4d68`

## callees

- `0x180003278`
- `0x18000347c`
- `0x180006770`
- `0x180017b98`
- `0x18002de70`
- `0x18005ff90`
- `0x1800641b8`
- `0x1800641d0`
- `0x18006c144`
- `0x180070418`
- `0x1800787c0`
- `0x18008aa0c`
- `0x18008d244`
- `0x18008d308`
- `0x18009177c`
- `0x180092008`
- `0x180092ee4`
- `0x180096164`
- `0x1800978a0`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800a1dbc`
- `0x1800a1dd8`
- `0x1800a1fcc`
- `0x1800a1ffc`
- `0x1800ae05c`
- `0x1800c5f74`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097ad5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097ad5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097a8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e41`

## string_xrefs

- `0x180097ae6`: `CompatFlags`

## pseudocode

```c
EventService *__fastcall EventService::EventService(EventService *this, char a2, char a3)
{
  EventService *v5; // r12
  _QWORD *v6; // r13
  __int64 v7; // r8
  HANDLE EventW; // rax
  HKEY *phkResult; // rax
  _QWORD *v10; // rax
  struct minrpc::IRpcSocketHandler *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  ContainerManager *v14; // rax
  ContainerManager *v15; // rax
  __int64 v16; // rdx
  DWORD LastError; // edi
  HKEY v19; // [rsp+30h] [rbp-128h] BYREF
  EventService *v20; // [rsp+38h] [rbp-120h]
  ContainerManager *v21; // [rsp+40h] [rbp-118h]
  __int128 pExceptionObject; // [rsp+48h] [rbp-110h] BYREF
  __int64 v23; // [rsp+58h] [rbp-100h]
  int v24; // [rsp+60h] [rbp-F8h]
  int v25; // [rsp+64h] [rbp-F4h]
  int v26; // [rsp+68h] [rbp-F0h]
  __int128 v27; // [rsp+70h] [rbp-E8h] BYREF
  __int64 v28; // [rsp+80h] [rbp-D8h]
  int v29; // [rsp+88h] [rbp-D0h]
  int v30; // [rsp+8Ch] [rbp-CCh]
  int v31; // [rsp+90h] [rbp-C8h]
  __int128 v32; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-B0h]
  int v34; // [rsp+B0h] [rbp-A8h]
  int v35; // [rsp+B4h] [rbp-A4h]
  int v36; // [rsp+B8h] [rbp-A0h]
  __int128 v37; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-88h]
  DWORD v39; // [rsp+D8h] [rbp-80h]
  int v40; // [rsp+DCh] [rbp-7Ch]
  int v41; // [rsp+E0h] [rbp-78h]
  __int128 v42; // [rsp+E8h] [rbp-70h]
  __int128 v43; // [rsp+F8h] [rbp-60h]
  __int128 v44; // [rsp+108h] [rbp-50h] BYREF
  __int128 v45; // [rsp+118h] [rbp-40h]

  v5 = this;
  v20 = this;
  *(_QWORD *)this = 0;
  v6 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = CreateTraceDecodingHandle();
  FileManager::FileManager((char *)v5 + 24);
  *((_QWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 13) = 0;
  *((_DWORD *)v5 + 28) = 0;
  *((_QWORD *)v5 + 15) = 0;
  *((_QWORD *)v5 + 16) = 0;
  *((_QWORD *)v5 + 17) = 0;
  *((_QWORD *)v5 + 18) = 0;
  memset_0((char *)v5 + 152, 0, 0x48u);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>((char *)v5 + 152);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>((char *)v5 + 184);
  *((_QWORD *)v5 + 27) = 0;
  *((_DWORD *)v5 + 56) = 0x1000000;
  *((_BYTE *)v5 + 228) = 0;
  PublisherManager::PublisherManager((char *)v5 + 232);
  ChannelManager::ChannelManager(
    (EventService *)((char *)v5 + 360),
    (EventService *)((char *)v5 + 24),
    (EventService *)((char *)v5 + 96),
    *((void **)v5 + 2));
  *((_QWORD *)v5 + 57) = 0;
  *((_QWORD *)v5 + 58) = 0;
  *((_QWORD *)v5 + 59) = 0;
  *((_DWORD *)v5 + 120) = 0;
  *((_BYTE *)v5 + 484) = a3;
  *((_BYTE *)v5 + 485) = a2;
  v7 = *((_QWORD *)v5 + 2);
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 6);
    }
    pExceptionObject = 0;
    v23 = 0;
    v24 = 6;
    v25 = -1;
    v26 = 302;
    throw (EvtException *)&pExceptionObject;
  }
  SetTraceFormatParameterW(7, (_WORD *)1, v7);
  SetTraceFormatParameterW(3, L"winevt\\TraceFormat", *((_QWORD *)v5 + 2));
  SetTraceFormatParameterW(12, (_WORD *)8, *((_QWORD *)v5 + 2));
  EventW = CreateEventW(0, 1, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(v6, EventW);
  if ( (unsigned __int64)(*v6 + 1LL) <= 1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, LastError);
    }
    v37 = 0;
    v38 = 0;
    v39 = LastError;
    v40 = -1;
    v41 = 312;
    throw (EvtException *)&v37;
  }
  v19 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v19);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT", 0, 1u, phkResult)
    && !(unsigned int)RegReadDWORDValueNoThrow(v19, &pszFormat, L"CompatFlags", &g_compatFlags)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, g_compatFlags);
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v19);
  if ( !*((_BYTE *)v5 + 484) )
  {
    try
    {
      if ( (unsigned int)ContainerCommon::GetContainerOperationMode() == 2 )
      {
        v44 = 0;
        *(_QWORD *)&v45 = 0;
        *((_QWORD *)&v45 + 1) = 7;
        LOWORD(v44) = 0;
        v10 = (_QWORD *)tlx::_LazyImpl<ContainerCommon::LazyMachineId,tlx::lazy_construct<ContainerCommon::LazyMachineId>,tlx::static_lazy<ContainerCommon::LazyMachineId,0,tlx::lazy_construct<ContainerCommon::LazyMachineId>>>::get();
        std::wstring::_Assign<wchar_t>(&v44, *v10);
        ContainerCommon::GetContainerCommunicationProtocol();
        v11 = (struct minrpc::IRpcSocketHandler *)MIDL_user_allocate(0x148u);
        v19 = (HKEY)v11;
        if ( v11 )
        {
          v42 = v44;
          v43 = v45;
          *(_QWORD *)&v45 = 0;
          *((_QWORD *)&v45 + 1) = 7;
          LOWORD(v44) = 0;
          v12 = ContainerForwarder::ContainerForwarder(v11);
        }
        else
        {
          v12 = 0;
        }
        v19 = 0;
        v13 = *((_QWORD *)v5 + 58);
        *((_QWORD *)v5 + 58) = v12;
        if ( v13 )
          utl::default_delete<ContainerForwarder>::operator()();
        utl::unique_ptr<ContainerForwarder,utl::default_delete<ContainerForwarder>>::~unique_ptr<ContainerForwarder,utl::default_delete<ContainerForwarder>>(&v19);
        if ( !*((_QWORD *)v5 + 58) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
          }
          v27 = 0;
          v28 = 0;
          v29 = 14;
          v30 = -1;
          v31 = 353;
          throw (EvtException *)&v27;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
        }
        std::wstring::~wstring(&v44);
      }
      else
      {
        v14 = (ContainerManager *)MIDL_user_allocate(0x1E0u);
        v21 = v14;
        if ( v14 )
          v15 = ContainerManager::ContainerManager(
                  v14,
                  (EventService *)((char *)v5 + 360),
                  (EventService *)((char *)v5 + 232));
        else
          v15 = 0;
        v19 = 0;
        v16 = *((_QWORD *)v5 + 57);
        *((_QWORD *)v5 + 57) = v15;
        if ( v16 )
          utl::default_delete<ContainerManager>::operator()();
        utl::unique_ptr<ContainerManager,utl::default_delete<ContainerManager>>::~unique_ptr<ContainerManager,utl::default_delete<ContainerManager>>(&v19);
        if ( !*((_QWORD *)v5 + 57) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
          }
          v32 = 0;
          v33 = 0;
          v34 = 14;
          v35 = -1;
          v36 = 363;
          throw (EvtException *)&v32;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
        }
      }
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids);
      }
      return v20;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800978a0  mov     [rsp+arg_8], rbx
0x1800978a5  mov     [rsp+arg_10], rsi
0x1800978aa  push    rdi
0x1800978ab  push    r12
0x1800978ad  push    r13
0x1800978af  push    r14
0x1800978b1  push    r15
0x1800978b3  sub     rsp, 130h
0x1800978ba  mov     rax, cs:__security_cookie
0x1800978c1  xor     rax, rsp
0x1800978c4  mov     [rsp+158h+var_30], rax
0x1800978cc  mov     r14b, r8b
0x1800978cf  mov     r15b, dl
0x1800978d2  mov     r12, rcx
0x1800978d5  mov     [rsp+158h+var_120], rcx
0x1800978da  xor     ebx, ebx
0x1800978dc  mov     [rcx], rbx
0x1800978df  lea     r13, [rcx+8]
0x1800978e3  mov     [r13+0], rbx
0x1800978e7  call    CreateTraceDecodingHandle
0x1800978ec  mov     [r12+10h], rax
0x1800978f1  lea     rcx, [r12+18h]; pv
0x1800978f6  call    ??0FileManager@@QEAA@XZ; FileManager::FileManager(void)
0x1800978fb  nop
0x1800978fc  mov     [r12+60h], rbx
0x180097901  mov     [r12+68h], rbx
0x180097906  mov     [r12+70h], ebx
0x18009790b  mov     [r12+78h], rbx
0x180097910  mov     [r12+80h], rbx
0x180097918  mov     [r12+88h], rbx
0x180097920  mov     [r12+90h], rbx
0x180097928  xor     edx, edx; Val
0x18009792a  lea     r8d, [rbx+48h]; Size
0x18009792e  lea     rcx, [r12+98h]; void *
0x180097936  call    memset_0
0x18009793b  lea     rcx, [r12+98h]
0x180097943  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x180097948  lea     rcx, [r12+0B8h]
0x180097950  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x180097955  xor     ecx, ecx
0x180097957  mov     [r12+0D8h], rcx
0x18009795f  mov     dword ptr [r12+0E0h], 1000000h
0x18009796b  lea     ebx, [rcx+1]
0x18009796e  mov     [r12+0E4h], cl
0x180097976  lea     rcx, [r12+0E8h]; pv
0x18009797e  call    ??0PublisherManager@@QEAA@XZ; PublisherManager::PublisherManager(void)
0x180097983  nop
0x180097984  lea     rcx, [r12+168h]; this
0x18009798c  mov     r9, [r12+10h]; void *
0x180097991  lea     r8, [r12+60h]; struct PolicyManager *
0x180097996  lea     rdx, [r12+18h]; struct FileManager *
0x18009799b  call    ??0ChannelManager@@QEAA@AEAVFileManager@@AEAVPolicyManager@@PEAX@Z; ChannelManager::ChannelManager(FileManager &,PolicyManager &,void *)
0x1800979a0  nop
0x1800979a1  xor     esi, esi
0x1800979a3  mov     [r12+1C8h], rsi
0x1800979ab  mov     [r12+1D0h], rsi
0x1800979b3  mov     [r12+1D8h], rsi
0x1800979bb  mov     [r12+1E0h], esi
0x1800979c3  mov     [r12+1E4h], r14b
0x1800979cb  mov     [r12+1E5h], r15b
0x1800979d3  mov     r8, [r12+10h]
0x1800979d8  test    r8, r8
0x1800979db  jnz     short loc_180097A4B
0x1800979dd  lea     rbx, WPP_GLOBAL_Control
0x1800979e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800979eb  cmp     rcx, rbx
0x1800979ee  jz      short loc_180097A13
0x1800979f0  test    byte ptr [rcx+1Ch], 8
0x1800979f4  jz      short loc_180097A13
0x1800979f6  cmp     byte ptr [rcx+19h], 2
0x1800979fa  jb      short loc_180097A13
0x1800979fc  lea     edx, [rsi+1Bh]
0x1800979ff  lea     r9d, [rsi+6]
0x180097a03  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097a0a  mov     rcx, [rcx+10h]
0x180097a0e  call    WPP_SF_d
0x180097a13  xorps   xmm0, xmm0
0x180097a16  movdqu  [rsp+158h+pExceptionObject], xmm0
0x180097a1c  mov     [rsp+158h+var_100], rsi
0x180097a21  mov     [rsp+158h+var_F8], 6
0x180097a29  mov     [rsp+158h+var_F4], 0FFFFFFFFh
0x180097a31  mov     [rsp+158h+var_F0], 12Eh
0x180097a39  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180097a40  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180097a45  call    _CxxThrowException_0
0x180097a4b  mov     rdx, rbx
0x180097a4e  mov     r14d, 7
0x180097a54  mov     ecx, r14d
0x180097a57  call    SetTraceFormatParameterW
0x180097a5c  mov     r8, [r12+10h]
0x180097a61  lea     rdx, aWinevtTracefor; "winevt\\TraceFormat"
0x180097a68  lea     ecx, [r14-4]
0x180097a6c  call    SetTraceFormatParameterW
0x180097a71  mov     r8, [r12+10h]
0x180097a76  lea     edx, [r14+1]
0x180097a7a  lea     ecx, [rdx+4]
0x180097a7d  call    SetTraceFormatParameterW
0x180097a82  xor     r9d, r9d; lpName
0x180097a85  xor     r8d, r8d; bInitialState
0x180097a88  mov     edx, ebx; bManualReset
0x180097a8a  xor     ecx, ecx; lpEventAttributes
0x180097a8c  call    cs:__imp_CreateEventW
0x180097a92  mov     rdx, rax
0x180097a95  mov     rcx, r13
0x180097a98  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180097a9d  mov     rax, [r13+0]
0x180097aa1  add     rax, rbx
0x180097aa4  cmp     rax, rbx
0x180097aa7  jbe     loc_180097E41
0x180097aad  mov     [rsp+158h+var_128], rsi
0x180097ab2  lea     rcx, [rsp+158h+var_128]
0x180097ab7  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180097abc  mov     [rsp+158h+phkResult], rax; phkResult
0x180097ac1  mov     r9d, ebx; samDesired
0x180097ac4  xor     r8d, r8d; ulOptions
0x180097ac7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180097ace  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097ad5  call    cs:__imp_RegOpenKeyExW
0x180097adb  test    eax, eax
0x180097add  jnz     short loc_180097B3D
0x180097adf  lea     r9, ?g_compatFlags@@3KA; unsigned int *
0x180097ae6  lea     r8, aCompatflags; "CompatFlags"
0x180097aed  lea     rdx, pszFormat; wchar_t *
0x180097af4  mov     rcx, [rsp+158h+var_128]; HKEY
0x180097af9  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x180097afe  test    eax, eax
0x180097b00  jnz     short loc_180097B3D
0x180097b02  lea     rbx, WPP_GLOBAL_Control
0x180097b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180097b10  cmp     rcx, rbx
0x180097b13  jz      short loc_180097B44
0x180097b15  test    byte ptr [rcx+1Ch], 8
0x180097b19  jz      short loc_180097B44
0x180097b1b  cmp     byte ptr [rcx+19h], 4
0x180097b1f  jb      short loc_180097B44
0x180097b21  lea     edx, [rax+1Dh]
0x180097b24  mov     r9d, cs:?g_compatFlags@@3KA; ulong g_compatFlags
0x180097b2b  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097b32  mov     rcx, [rcx+10h]
0x180097b36  call    WPP_SF_d
0x180097b3b  jmp     short loc_180097B44
0x180097b3d  lea     rbx, WPP_GLOBAL_Control
0x180097b44  lea     rcx, [rsp+158h+var_128]
0x180097b49  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180097b4e  cmp     [r12+1E4h], sil
0x180097b56  jnz     loc_180097E11
0x180097b5c  call    ?GetContainerOperationMode@ContainerCommon@@YA?AW4ContainerOperatingMode@1@XZ; ContainerCommon::GetContainerOperationMode(void)
0x180097b61  cmp     eax, 2
0x180097b64  jnz     loc_180097CFE
0x180097b6a  xorps   xmm0, xmm0
0x180097b6d  movups  [rsp+158h+var_50], xmm0
0x180097b75  mov     qword ptr [rsp+158h+var_40], rsi
0x180097b7d  mov     qword ptr [rsp+158h+var_40+8], r14
0x180097b85  mov     word ptr [rsp+158h+var_50], si
0x180097b8d  call    ?get@?$_LazyImpl@VLazyMachineId@ContainerCommon@@V?$lazy_construct@VLazyMachineId@ContainerCommon@@@tlx@@V?$static_lazy@VLazyMachineId@ContainerCommon@@$0A@V?$lazy_construct@VLazyMachineId@ContainerCommon@@@tlx@@@4@@tlx@@QEAAAEAVLazyMachineId@ContainerCommon@@XZ; tlx::_LazyImpl<ContainerCommon::LazyMachineId,tlx::lazy_construct<ContainerCommon::LazyMachineId>,tlx::static_lazy<ContainerCommon::LazyMachineId,0,tlx::lazy_construct<ContainerCommon::LazyMachineId>>>::get(void)
0x180097b92  mov     r8, [rax+8]
0x180097b96  sub     r8, [rax]
0x180097b99  sar     r8, 1
0x180097b9c  mov     rdx, [rax]
0x180097b9f  lea     rcx, [rsp+158h+var_50]
0x180097ba7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180097bac  call    ?GetContainerCommunicationProtocol@ContainerCommon@@YA?AW4ContainerCommunicationProtocol@1@XZ; ContainerCommon::GetContainerCommunicationProtocol(void)
0x180097bb1  mov     edi, eax
0x180097bb3  mov     ecx, 148h; size
0x180097bb8  call    MIDL_user_allocate
0x180097bbd  mov     rcx, rax; struct minrpc::IRpcSocketHandler *
0x180097bc0  mov     [rsp+158h+var_128], rax
0x180097bc5  test    rax, rax
0x180097bc8  jz      short loc_180097C14
0x180097bca  movups  xmm0, [rsp+158h+var_50]
0x180097bd2  movups  [rsp+158h+var_70], xmm0
0x180097bda  movups  xmm1, [rsp+158h+var_40]
0x180097be2  movups  [rsp+158h+var_60], xmm1
0x180097bea  mov     qword ptr [rsp+158h+var_40], rsi
0x180097bf2  mov     qword ptr [rsp+158h+var_40+8], r14
0x180097bfa  mov     word ptr [rsp+158h+var_50], si
0x180097c02  mov     r8d, edi
0x180097c05  lea     rdx, [rsp+158h+var_70]
0x180097c0d  call    ??0ContainerForwarder@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ContainerCommunicationProtocol@ContainerCommon@@@Z; ContainerForwarder::ContainerForwarder(std::wstring,ContainerCommon::ContainerCommunicationProtocol)
0x180097c12  jmp     short loc_180097C17
0x180097c14  mov     rax, rsi
0x180097c17  mov     [rsp+158h+var_128], rsi
0x180097c1c  mov     rdx, [r12+1D0h]
0x180097c24  mov     [r12+1D0h], rax
0x180097c2c  test    rdx, rdx
0x180097c2f  jz      short loc_180097C36
0x180097c31  call    ??R?$default_delete@VContainerForwarder@@@utl@@QEBAXPEAVContainerForwarder@@@Z; utl::default_delete<ContainerForwarder>::operator()(ContainerForwarder *)
0x180097c36  lea     rcx, [rsp+158h+var_128]
0x180097c3b  call    ??1?$unique_ptr@VContainerForwarder@@U?$default_delete@VContainerForwarder@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ContainerForwarder,utl::default_delete<ContainerForwarder>>::~unique_ptr<ContainerForwarder,utl::default_delete<ContainerForwarder>>(void)
0x180097c40  cmp     [r12+1D0h], rsi
0x180097c48  jnz     short loc_180097CBE
0x180097c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c51  cmp     rcx, rbx
0x180097c54  jz      short loc_180097C7B
0x180097c56  test    byte ptr [rcx+1Ch], 8
0x180097c5a  jz      short loc_180097C7B
0x180097c5c  cmp     byte ptr [rcx+19h], 2
0x180097c60  jb      short loc_180097C7B
0x180097c62  mov     edx, 1Eh
0x180097c67  lea     r9d, [rdx-10h]
0x180097c6b  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097c72  mov     rcx, [rcx+10h]
0x180097c76  call    WPP_SF_d
0x180097c7b  xorps   xmm0, xmm0
0x180097c7e  movdqu  [rsp+158h+var_E8], xmm0
0x180097c84  mov     [rsp+158h+var_D8], rsi
0x180097c8c  mov     [rsp+158h+var_D0], 0Eh
0x180097c97  mov     [rsp+158h+var_CC], 0FFFFFFFFh
0x180097ca2  mov     [rsp+158h+var_C8], 161h
0x180097cad  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180097cb4  lea     rcx, [rsp+158h+var_E8]; pExceptionObject
0x180097cb9  call    _CxxThrowException_0
0x180097cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180097cc5  cmp     rcx, rbx
0x180097cc8  jz      short loc_180097CEC
0x180097cca  test    byte ptr [rcx+1Ch], 8
0x180097cce  jz      short loc_180097CEC
0x180097cd0  cmp     byte ptr [rcx+19h], 4
0x180097cd4  jb      short loc_180097CEC
0x180097cd6  mov     edx, 1Fh
0x180097cdb  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097ce2  mov     rcx, [rcx+10h]
0x180097ce6  call    WPP_SF_
0x180097ceb  nop
0x180097cec  lea     rcx, [rsp+158h+var_50]
0x180097cf4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180097cf9  jmp     loc_180097E0A
0x180097cfe  mov     ecx, 1E0h; size
0x180097d03  call    MIDL_user_allocate
0x180097d08  mov     [rsp+158h+var_118], rax
0x180097d0d  test    rax, rax
0x180097d10  jz      short loc_180097D2C
0x180097d12  lea     r8, [r12+0E8h]; struct PublisherManager *
0x180097d1a  lea     rdx, [r12+168h]; struct ChannelManager *
0x180097d22  mov     rcx, rax; this
0x180097d25  call    ??0ContainerManager@@QEAA@AEAVChannelManager@@AEAVPublisherManager@@@Z; ContainerManager::ContainerManager(ChannelManager &,PublisherManager &)
0x180097d2a  jmp     short loc_180097D2F
0x180097d2c  mov     rax, rsi
0x180097d2f  mov     [rsp+158h+var_128], rsi
0x180097d34  mov     rdx, [r12+1C8h]
0x180097d3c  mov     [r12+1C8h], rax
0x180097d44  test    rdx, rdx
0x180097d47  jz      short loc_180097D4E
0x180097d49  call    ??R?$default_delete@VContainerManager@@@utl@@QEBAXPEAVContainerManager@@@Z; utl::default_delete<ContainerManager>::operator()(ContainerManager *)
0x180097d4e  lea     rcx, [rsp+158h+var_128]
0x180097d53  call    ??1?$unique_ptr@VContainerManager@@U?$default_delete@VContainerManager@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ContainerManager,utl::default_delete<ContainerManager>>::~unique_ptr<ContainerManager,utl::default_delete<ContainerManager>>(void)
0x180097d58  cmp     [r12+1C8h], rsi
0x180097d60  jnz     short loc_180097DDC
0x180097d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d69  cmp     rcx, rbx
0x180097d6c  jz      short loc_180097D93
0x180097d6e  test    byte ptr [rcx+1Ch], 8
0x180097d72  jz      short loc_180097D93
0x180097d74  cmp     byte ptr [rcx+19h], 2
0x180097d78  jb      short loc_180097D93
0x180097d7a  mov     edx, 20h ; ' '
0x180097d7f  lea     r9d, [rdx-12h]
0x180097d83  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097d8a  mov     rcx, [rcx+10h]
0x180097d8e  call    WPP_SF_d
0x180097d93  xorps   xmm0, xmm0
0x180097d96  movdqu  [rsp+158h+var_C0], xmm0
0x180097d9f  mov     [rsp+158h+var_B0], rsi
0x180097da7  mov     [rsp+158h+var_A8], 0Eh
0x180097db2  mov     [rsp+158h+var_A4], 0FFFFFFFFh
0x180097dbd  mov     [rsp+158h+var_A0], 16Bh
0x180097dc8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180097dcf  lea     rcx, [rsp+158h+var_C0]; pExceptionObject
0x180097dd7  call    _CxxThrowException_0
0x180097ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180097de3  cmp     rcx, rbx
0x180097de6  jz      short loc_180097E0A
0x180097de8  test    byte ptr [rcx+1Ch], 8
0x180097dec  jz      short loc_180097E0A
0x180097dee  cmp     byte ptr [rcx+19h], 4
0x180097df2  jb      short loc_180097E0A
0x180097df4  mov     edx, 21h ; '!'
0x180097df9  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180097e00  mov     rcx, [rcx+10h]
0x180097e04  call    WPP_SF_
0x180097e09  nop
0x180097e0a  jmp     short loc_180097E11
0x180097e0c  mov     r12, [rsp+158h+var_120]
0x180097e11  mov     rax, r12
0x180097e14  mov     rcx, [rsp+158h+var_30]
0x180097e1c  xor     rcx, rsp; StackCookie
0x180097e1f  call    __security_check_cookie
0x180097e24  lea     r11, [rsp+158h+var_28]
0x180097e2c  mov     rbx, [r11+38h]
0x180097e30  mov     rsi, [r11+40h]
0x180097e34  mov     rsp, r11
0x180097e37  pop     r15
0x180097e39  pop     r14
0x180097e3b  pop     r13
0x180097e3d  pop     r12
0x180097e3f  pop     rdi
0x180097e40  retn
0x180097e41  call    cs:__imp_GetLastError
0x180097e47  nop
0x180097e48  mov     edi, eax
  ... truncated ...
```
