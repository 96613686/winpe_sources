# EventService::AssertConfig(wchar_t const *,ulong)

- ea: `0x18005afd8`
- end: `0x18005b5eb`
- name: `?AssertConfig@EventService@@QEAAXPEB_WK@Z`
- size: `1555`
- prototype: `void __fastcall(EventService *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007bd60`
- `0x1800a9420`

## callees

- `0x180006064`
- `0x180006770`
- `0x180014bd0`
- `0x180017128`
- `0x180017b60`
- `0x180017b98`
- `0x180019d28`
- `0x18002d6dc`
- `0x18002f1b0`
- `0x18005572c`
- `0x180055b58`
- `0x18005af7c`
- `0x18005afd8`
- `0x18005b6a0`
- `0x18005c040`
- `0x18005c418`
- `0x18005c6fc`
- `0x180083b84`
- `0x180084c24`
- `0x1800885cc`
- `0x180092008`
- `0x18009aee0`
- `0x1800a1a10`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b4af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b4af`
- `RPCRT4!RpcImpersonateClient` at `0x18005b136`
- `RPCRT4!RpcImpersonateClient` at `0x18005b406`
- `RPCRT4!RpcImpersonateClient` at `0x18005b136`
- `RPCRT4!RpcImpersonateClient` at `0x18005b406`
- `RPCRT4!RpcRevertToSelf` at `0x18005b1ed`
- `RPCRT4!RpcRevertToSelf` at `0x18005b575`
- `RPCRT4!RpcRevertToSelf` at `0x18005b1ed`
- `RPCRT4!RpcRevertToSelf` at `0x18005b575`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall EventService::AssertConfig(RTL_SRWLOCK *this, const wchar_t *a2, int a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // esi
  unsigned int v9; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int WinevtRegPath; // ebx
  unsigned int v13; // ebx
  HKEY *phkResult; // rax
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  struct _SECURITY_ATTRIBUTES *v17; // r9
  void *v18; // [rsp+28h] [rbp-D8h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  int v23; // [rsp+50h] [rbp-B0h]
  char v24; // [rsp+54h] [rbp-ACh]
  char v25; // [rsp+59h] [rbp-A7h]
  HKEY hKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  unsigned int v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+8Ch] [rbp-74h]
  int v32; // [rsp+90h] [rbp-70h]
  char v33; // [rsp+94h] [rbp-6Ch]
  HKEY v34; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v36; // [rsp+C0h] [rbp-40h] BYREF
  int v37[4]; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v38; // [rsp+E0h] [rbp-20h] BYREF
  char v39; // [rsp+218h] [rbp+118h]
  char v40; // [rsp+21Fh] [rbp+11Fh]

  hKey[0] = (HKEY)a2;
  EventService::WaitForInit(this);
  if ( BYTE4(this[60].Ptr) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 50);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 50;
    v22 = -1;
    v23 = 1903;
    throw (EvtException *)&pExceptionObject;
  }
  if ( a3 )
  {
    v36 = 0;
    v34 = 0;
    if ( !tlx::string_to_guid<wchar_t const *>(&v36, hKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 13);
      }
      pExceptionObject = 0;
      v20 = 0;
      v21 = 13;
      v22 = -1;
      v23 = 1946;
      throw (EvtException *)&pExceptionObject;
    }
    hKey[0] = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v27);
    WinevtRegPath = RegistryPaths::GetWinevtRegPath(v11, hKey, lpSubKey, &v27);
    if ( WinevtRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
          WinevtRegPath);
      }
      *(_QWORD *)&pExceptionObject = &word_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v20 = 0;
      v21 = WinevtRegPath;
      v22 = -1;
      v23 = -1;
      v24 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
      }
      pExceptionObject = 0;
      v20 = 0;
      v21 = 14;
      v22 = -1;
      v23 = 1955;
      throw (EvtException *)&pExceptionObject;
    }
    v13 = RpcImpersonateClient(0);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v13);
      }
      *(_QWORD *)&pExceptionObject = &word_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v20 = 0;
      v21 = v13;
      v22 = -1;
      v23 = -1;
      v24 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    v25 = 1;
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v34);
    v15 = RegOpenKeyExW(hKey[0], lpSubKey[0], 0, 0x20006u, phkResult);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v15);
      }
      *(_QWORD *)&pExceptionObject = &word_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v20 = 0;
      v21 = v15;
      v22 = -1;
      v23 = -1;
      v24 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    PublisherConfigWriter::PublisherConfigWriter((PublisherConfigWriter *)v37, &v36, v16, v17, v34, v18);
    v39 = 1;
    v40 = 1;
    PublisherConfigWriter::Save((PublisherConfigWriter *)v37);
    RemoveRegCacheProviderNode(&v38);
    PublisherConfigWriter::~PublisherConfigWriter((PublisherConfigWriter *)v37);
    RpcRevertToSelf();
    PublisherManager::ReleasePublisher((PublisherManager *)&this[29], &v36);
    *(struct _GUID *)hKey = v36;
    ChannelManager::AssertPublisherToChannels(this + 45, (struct _GUID *)hKey);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v27);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v34);
  }
  else
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    *(_QWORD *)&v36.Data1 = a2;
    *(_QWORD *)v36.Data4 = v7;
    v8 = ScanForInvalidChars(&v36, 15000);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v8);
      }
      v27 = &word_1800EC961;
      v28 = 0;
      v29 = 0;
      v30 = v8;
      v31 = -1;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&v27;
    }
    v9 = RpcImpersonateClient(0);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v9);
      }
      v27 = &word_1800EC961;
      v28 = 0;
      v29 = 0;
      v30 = v9;
      v31 = -1;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&v27;
    }
    v25 = 1;
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    *(_QWORD *)&v36.Data1 = a2;
    *(_QWORD *)v36.Data4 = v10;
    ChannelConfigWriter::ChannelConfigWriter((int)v37, (int)&v36, 0, 0, HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
    ChannelConfigWriter::~ChannelConfigWriter((ChannelConfigWriter *)v37);
    RpcRevertToSelf();
    do
      ++v6;
    while ( a2[v6] );
    *(_QWORD *)&v36.Data1 = a2;
    *(_QWORD *)v36.Data4 = v6;
    ChannelManager::GetChannel(this + 45, 0x10u);
    if ( hKey[0] )
      wmi::RefBase::Release((wmi::RefBase *)hKey[0]);
    PublisherManager::ReleasePublishersWithNullChannelReference((PublisherManager *)&this[29]);
  }
}

```

## disassembly

```asm
0x18005afd8  mov     [rsp-8+arg_18], rbx
0x18005afdd  push    rbp
0x18005afde  push    rsi
0x18005afdf  push    rdi
0x18005afe0  push    r14
0x18005afe2  push    r15
0x18005afe4  lea     rbp, [rsp-150h]
0x18005afec  sub     rsp, 250h
0x18005aff3  mov     rax, cs:__security_cookie
0x18005affa  xor     rax, rsp
0x18005affd  mov     [rbp+170h+var_30], rax
0x18005b004  mov     ebx, r8d
0x18005b007  mov     rdi, rdx
0x18005b00a  mov     r14, rcx
0x18005b00d  mov     [rsp+270h+hKey], rdx
0x18005b012  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x18005b017  xor     r15d, r15d
0x18005b01a  cmp     [r14+1E4h], r15b
0x18005b021  jz      short loc_18005B090
0x18005b023  lea     rax, WPP_GLOBAL_Control
0x18005b02a  lea     ebx, [r15+32h]
0x18005b02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b035  cmp     rcx, rax
0x18005b038  jz      short loc_18005B05C
0x18005b03a  test    byte ptr [rcx+1Ch], 8
0x18005b03e  jz      short loc_18005B05C
0x18005b040  cmp     byte ptr [rcx+19h], 2
0x18005b044  jb      short loc_18005B05C
0x18005b046  lea     edx, [rbx+22h]
0x18005b049  mov     r9d, ebx
0x18005b04c  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b053  mov     rcx, [rcx+10h]
0x18005b057  call    WPP_SF_d
0x18005b05c  xorps   xmm0, xmm0
0x18005b05f  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18005b065  mov     [rsp+270h+var_230], r15
0x18005b06a  mov     [rsp+270h+var_228], ebx
0x18005b06e  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18005b076  mov     [rsp+270h+var_220], 76Fh
0x18005b07e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b085  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18005b08a  call    _CxxThrowException_0
0x18005b090  test    ebx, ebx
0x18005b092  jnz     loc_18005B245
0x18005b098  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b09c  mov     rax, rbx
0x18005b09f  inc     rax
0x18005b0a2  cmp     [rdi+rax*2], r15w
0x18005b0a7  jnz     short loc_18005B09F
0x18005b0a9  mov     qword ptr [rbp+170h+var_1B0.Data1], rdi
0x18005b0ad  mov     qword ptr [rbp+170h+var_1B0.Data4], rax
0x18005b0b1  mov     edx, 3A98h
0x18005b0b6  lea     rcx, [rbp+170h+var_1B0]
0x18005b0ba  call    ScanForInvalidChars
0x18005b0bf  mov     esi, eax
0x18005b0c1  test    eax, eax
0x18005b0c3  jz      short loc_18005B134
0x18005b0c5  lea     rax, WPP_GLOBAL_Control
0x18005b0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b0d3  cmp     rcx, rax
0x18005b0d6  jz      short loc_18005B0FC
0x18005b0d8  test    byte ptr [rcx+1Ch], 8
0x18005b0dc  jz      short loc_18005B0FC
0x18005b0de  cmp     byte ptr [rcx+19h], 2
0x18005b0e2  jb      short loc_18005B0FC
0x18005b0e4  mov     edx, 55h ; 'U'
0x18005b0e9  mov     r9d, esi
0x18005b0ec  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b0f3  mov     rcx, [rcx+10h]
0x18005b0f7  call    WPP_SF_d
0x18005b0fc  lea     rax, word_1800EC961
0x18005b103  mov     [rsp+270h+var_200], rax
0x18005b108  mov     [rsp+270h+var_1F8], r15
0x18005b10d  mov     [rbp+170h+var_1F0], r15
0x18005b111  mov     [rbp+170h+var_1E8], esi
0x18005b114  mov     [rbp+170h+var_1E4], 0FFFFFFFFh
0x18005b11b  mov     [rbp+170h+var_1E0], ebx
0x18005b11e  mov     [rbp+170h+var_1DC], r15b
0x18005b122  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b129  lea     rcx, [rsp+270h+var_200]; pExceptionObject
0x18005b12e  call    _CxxThrowException_0
0x18005b134  xor     ecx, ecx; BindingHandle
0x18005b136  call    cs:__imp_RpcImpersonateClient
0x18005b13c  mov     esi, eax
0x18005b13e  test    eax, eax
0x18005b140  jz      short loc_18005B1B1
0x18005b142  lea     rax, WPP_GLOBAL_Control
0x18005b149  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b150  cmp     rcx, rax
0x18005b153  jz      short loc_18005B179
0x18005b155  test    byte ptr [rcx+1Ch], 8
0x18005b159  jz      short loc_18005B179
0x18005b15b  cmp     byte ptr [rcx+19h], 2
0x18005b15f  jb      short loc_18005B179
0x18005b161  mov     edx, 56h ; 'V'
0x18005b166  mov     r9d, esi
0x18005b169  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b170  mov     rcx, [rcx+10h]
0x18005b174  call    WPP_SF_d
0x18005b179  lea     rax, word_1800EC961
0x18005b180  mov     [rsp+270h+var_200], rax
0x18005b185  mov     [rsp+270h+var_1F8], r15
0x18005b18a  mov     [rbp+170h+var_1F0], r15
0x18005b18e  mov     [rbp+170h+var_1E8], esi
0x18005b191  mov     [rbp+170h+var_1E4], 0FFFFFFFFh
0x18005b198  mov     [rbp+170h+var_1E0], ebx
0x18005b19b  mov     [rbp+170h+var_1DC], r15b
0x18005b19f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b1a6  lea     rcx, [rsp+270h+var_200]; pExceptionObject
0x18005b1ab  call    _CxxThrowException_0
0x18005b1b1  mov     [rsp+270h+var_217], 1
0x18005b1b6  mov     rax, rbx
0x18005b1b9  inc     rax
0x18005b1bc  cmp     [rdi+rax*2], r15w
0x18005b1c1  jnz     short loc_18005B1B9
0x18005b1c3  mov     qword ptr [rbp+170h+var_1B0.Data1], rdi
0x18005b1c7  mov     qword ptr [rbp+170h+var_1B0.Data4], rax
0x18005b1cb  mov     [rsp+270h+phkResult], rbx; hKey
0x18005b1d0  xor     r9d, r9d; int
0x18005b1d3  xor     r8d, r8d; int
0x18005b1d6  lea     rdx, [rbp+170h+var_1B0]; int
0x18005b1da  lea     rcx, [rbp+170h+var_1A0]; int
0x18005b1de  call    ??0ChannelConfigWriter@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_NPEAX@Z; ChannelConfigWriter::ChannelConfigWriter(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,ulong,bool,void *)
0x18005b1e3  lea     rcx, [rbp+170h+var_1A0]; this
0x18005b1e7  call    ??1ChannelConfigWriter@@QEAA@XZ; ChannelConfigWriter::~ChannelConfigWriter(void)
0x18005b1ec  nop
0x18005b1ed  call    cs:__imp_RpcRevertToSelf
0x18005b1f3  inc     rbx
0x18005b1f6  cmp     [rdi+rbx*2], r15w
0x18005b1fb  jnz     short loc_18005B1F3
0x18005b1fd  mov     qword ptr [rbp+170h+var_1B0.Data1], rdi
0x18005b201  mov     qword ptr [rbp+170h+var_1B0.Data4], rbx
0x18005b205  lea     rcx, [r14+168h]; SRWLock
0x18005b20c  mov     dword ptr [rsp+270h+phkResult], 10h; unsigned int
0x18005b214  mov     r9b, 1
0x18005b217  lea     r8, [rbp+170h+var_1B0]
0x18005b21b  lea     rdx, [rsp+270h+hKey]
0x18005b220  call    ?GetChannel@ChannelManager@@AEAA?AV?$AutoRef@VChannel@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_NK@Z; ChannelManager::GetChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,ulong)
0x18005b225  mov     rcx, [rsp+270h+hKey]; this
0x18005b22a  test    rcx, rcx
0x18005b22d  jz      short loc_18005B234
0x18005b22f  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18005b234  lea     rcx, [r14+0E8h]; this
0x18005b23b  call    ?ReleasePublishersWithNullChannelReference@PublisherManager@@QEAAXXZ; PublisherManager::ReleasePublishersWithNullChannelReference(void)
0x18005b240  jmp     loc_18005B5C5
0x18005b245  xorps   xmm0, xmm0
0x18005b248  movups  xmmword ptr [rbp+170h+var_1B0.Data1], xmm0
0x18005b24c  mov     [rbp+170h+var_1D8], r15
0x18005b250  lea     rdx, [rsp+270h+hKey]
0x18005b255  lea     rcx, [rbp+170h+var_1B0]
0x18005b259  call    ??$string_to_guid@PEB_W@tlx@@YAPEB_WPEAU_GUID@@AEBQEB_W@Z; tlx::string_to_guid<wchar_t const *>(_GUID *,wchar_t const * const &)
0x18005b25e  test    rax, rax
0x18005b261  jnz     short loc_18005B2D1
0x18005b263  lea     rax, WPP_GLOBAL_Control
0x18005b26a  mov     ebx, 0Dh
0x18005b26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b276  cmp     rcx, rax
0x18005b279  jz      short loc_18005B29D
0x18005b27b  test    byte ptr [rcx+1Ch], 8
0x18005b27f  jz      short loc_18005B29D
0x18005b281  cmp     byte ptr [rcx+19h], 2
0x18005b285  jb      short loc_18005B29D
0x18005b287  lea     edx, [rbx+4Ah]
0x18005b28a  mov     r9d, ebx
0x18005b28d  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b294  mov     rcx, [rcx+10h]
0x18005b298  call    WPP_SF_d
0x18005b29d  xorps   xmm0, xmm0
0x18005b2a0  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18005b2a6  mov     [rsp+270h+var_230], r15
0x18005b2ab  mov     [rsp+270h+var_228], ebx
0x18005b2af  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18005b2b7  mov     [rsp+270h+var_220], 79Ah
0x18005b2bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b2c6  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18005b2cb  call    _CxxThrowException_0
0x18005b2d1  mov     [rsp+270h+hKey], r15
0x18005b2d6  lea     rcx, [rbp+170h+lpSubKey]; void *
0x18005b2da  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b2df  nop
0x18005b2e0  lea     rcx, [rsp+270h+var_200]; void *
0x18005b2e5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b2ea  nop
0x18005b2eb  lea     r9, [rsp+270h+var_200]
0x18005b2f0  lea     r8, [rbp+170h+lpSubKey]
0x18005b2f4  lea     rdx, [rsp+270h+hKey]
0x18005b2f9  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005b2fe  mov     ebx, eax
0x18005b300  test    eax, eax
0x18005b302  jz      short loc_18005B37C
0x18005b304  lea     rax, WPP_GLOBAL_Control
0x18005b30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b312  cmp     rcx, rax
0x18005b315  jz      short loc_18005B33B
0x18005b317  test    byte ptr [rcx+1Ch], 8
0x18005b31b  jz      short loc_18005B33B
0x18005b31d  cmp     byte ptr [rcx+19h], 2
0x18005b321  jb      short loc_18005B33B
0x18005b323  mov     edx, 58h ; 'X'
0x18005b328  mov     r9d, ebx
0x18005b32b  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b332  mov     rcx, [rcx+10h]
0x18005b336  call    WPP_SF_d
0x18005b33b  lea     rax, word_1800EC961
0x18005b342  mov     qword ptr [rsp+270h+pExceptionObject], rax
0x18005b347  mov     qword ptr [rsp+270h+pExceptionObject+8], r15
0x18005b34c  mov     [rsp+270h+var_230], r15
0x18005b351  mov     [rsp+270h+var_228], ebx
0x18005b355  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18005b35d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b361  mov     [rsp+270h+var_220], ebx
0x18005b365  mov     [rsp+270h+var_21C], r15b
0x18005b36a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b371  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18005b376  call    _CxxThrowException_0
0x18005b37c  mov     r8d, 0Bh
0x18005b382  lea     rdx, aPublishers; "\\Publishers"
0x18005b389  lea     rcx, [rbp+170h+lpSubKey]
0x18005b38d  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18005b392  test    al, al
0x18005b394  jnz     short loc_18005B404
0x18005b396  lea     rax, WPP_GLOBAL_Control
0x18005b39d  mov     ebx, 0Eh
0x18005b3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b3a9  cmp     rcx, rax
0x18005b3ac  jz      short loc_18005B3D0
0x18005b3ae  test    byte ptr [rcx+1Ch], 8
0x18005b3b2  jz      short loc_18005B3D0
0x18005b3b4  cmp     byte ptr [rcx+19h], 2
0x18005b3b8  jb      short loc_18005B3D0
0x18005b3ba  lea     edx, [rbx+4Bh]
0x18005b3bd  mov     r9d, ebx
0x18005b3c0  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b3c7  mov     rcx, [rcx+10h]
0x18005b3cb  call    WPP_SF_d
0x18005b3d0  xorps   xmm0, xmm0
0x18005b3d3  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18005b3d9  mov     [rsp+270h+var_230], r15
0x18005b3de  mov     [rsp+270h+var_228], ebx
0x18005b3e2  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18005b3ea  mov     [rsp+270h+var_220], 7A3h
0x18005b3f2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b3f9  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18005b3fe  call    _CxxThrowException_0
0x18005b404  xor     ecx, ecx; BindingHandle
0x18005b406  call    cs:__imp_RpcImpersonateClient
0x18005b40c  mov     ebx, eax
0x18005b40e  test    eax, eax
0x18005b410  jz      short loc_18005B48A
0x18005b412  lea     rax, WPP_GLOBAL_Control
0x18005b419  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b420  cmp     rcx, rax
0x18005b423  jz      short loc_18005B449
0x18005b425  test    byte ptr [rcx+1Ch], 8
0x18005b429  jz      short loc_18005B449
0x18005b42b  cmp     byte ptr [rcx+19h], 2
0x18005b42f  jb      short loc_18005B449
0x18005b431  mov     edx, 5Ah ; 'Z'
0x18005b436  mov     r9d, ebx
0x18005b439  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b440  mov     rcx, [rcx+10h]
0x18005b444  call    WPP_SF_d
0x18005b449  lea     rax, word_1800EC961
0x18005b450  mov     qword ptr [rsp+270h+pExceptionObject], rax
0x18005b455  mov     qword ptr [rsp+270h+pExceptionObject+8], r15
0x18005b45a  mov     [rsp+270h+var_230], r15
0x18005b45f  mov     [rsp+270h+var_228], ebx
0x18005b463  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18005b46b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b46f  mov     [rsp+270h+var_220], ebx
0x18005b473  mov     [rsp+270h+var_21C], r15b
0x18005b478  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b47f  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18005b484  call    _CxxThrowException_0
0x18005b48a  mov     [rsp+270h+var_217], 1
0x18005b48f  lea     rcx, [rbp+170h+var_1D8]
0x18005b493  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005b498  mov     [rsp+270h+phkResult], rax; phkResult
0x18005b49d  mov     r9d, 20006h; samDesired
0x18005b4a3  xor     r8d, r8d; ulOptions
0x18005b4a6  mov     rdx, [rbp+170h+lpSubKey]; lpSubKey
0x18005b4aa  mov     rcx, [rsp+270h+hKey]; hKey
0x18005b4af  call    cs:__imp_RegOpenKeyExW
0x18005b4b5  mov     ebx, eax
0x18005b4b7  test    eax, eax
0x18005b4b9  jz      short loc_18005B533
0x18005b4bb  lea     rax, WPP_GLOBAL_Control
0x18005b4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4c9  cmp     rcx, rax
0x18005b4cc  jz      short loc_18005B4F2
0x18005b4ce  test    byte ptr [rcx+1Ch], 8
0x18005b4d2  jz      short loc_18005B4F2
0x18005b4d4  cmp     byte ptr [rcx+19h], 2
0x18005b4d8  jb      short loc_18005B4F2
0x18005b4da  mov     edx, 5Bh ; '['
0x18005b4df  mov     r9d, ebx
0x18005b4e2  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18005b4e9  mov     rcx, [rcx+10h]
0x18005b4ed  call    WPP_SF_d
0x18005b4f2  lea     rax, word_1800EC961
  ... truncated ...
```
