# EventService::GetChannelConfig(wchar_t const *,ulong,tag_EvtRpcVariantList &)

- ea: `0x180017370`
- end: `0x180017b15`
- name: `?GetChannelConfig@EventService@@QEAAXPEB_WKAEAUtag_EvtRpcVariantList@@@Z`
- size: `1957`
- prototype: `void __fastcall(RTL_SRWLOCK *this, const wchar_t *, int, struct tag_EvtRpcVariantList *)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007c4c0`

## callees

- `0x180003e80`
- `0x180009200`
- `0x180016250`
- `0x180017128`
- `0x180017370`
- `0x180017b1c`
- `0x180017b60`
- `0x180017b98`
- `0x180017bb8`
- `0x180019d28`
- `0x18002b190`
- `0x18002cae4`
- `0x18003b3f8`
- `0x18003c0b4`
- `0x180043a88`
- `0x180043c94`
- `0x180057e30`
- `0x180058aec`
- `0x180058b2c`
- `0x180058b48`
- `0x18006bb18`
- `0x180084018`
- `0x1800840a0`
- `0x180084f08`
- `0x180088d04`
- `0x180090c60`
- `0x180092008`
- `0x18009bb88`
- `0x1800a98bc`
- `0x1800c09dc`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017690`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800174c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800174c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017656`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017656`
- `RPCRT4!RpcImpersonateClient` at `0x180017444`
- `RPCRT4!RpcImpersonateClient` at `0x180017444`
- `RPCRT4!RpcRevertToSelf` at `0x1800175fe`
- `RPCRT4!RpcRevertToSelf` at `0x1800175fe`

## pseudocode

```c
void __fastcall EventService::GetChannelConfig(
        RTL_SRWLOCK *this,
        const wchar_t *a2,
        int a3,
        struct tag_EvtRpcVariantList *a4)
{
  __int64 v7; // r14
  __int64 v8; // r8
  const wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  unsigned __int64 v11; // r8
  void *v12; // rax
  int v13; // edx
  void *v14; // r15
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rax
  wmi::RefBase *v18; // rsi
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  const struct ChannelConfigSnapshot *v20; // rdx
  __int64 v21; // rcx
  _BYTE *v22; // rbx
  const wchar_t *v23; // rbx
  __int64 v24; // rdi
  const wchar_t *v25; // rbx
  __int64 v26; // rdi
  wmi::RefBase *v27; // rcx
  __int64 ChannelConfig; // rax
  EventService *v29; // rax
  __int64 v30; // rcx
  EventService *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rbx
  const wchar_t *v34; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v35; // [rsp+28h] [rbp-D8h]
  wmi::RefBase *v36; // [rsp+30h] [rbp-D0h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h]
  int v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+54h] [rbp-ACh] BYREF
  char v41; // [rsp+5Ch] [rbp-A4h]
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  void *v43; // [rsp+90h] [rbp-70h]
  char v44[8]; // [rsp+A0h] [rbp-60h] BYREF
  char v45[8]; // [rsp+A8h] [rbp-58h] BYREF
  char v46[16]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v47[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v48[64]; // [rsp+E0h] [rbp-20h] BYREF
  char v49; // [rsp+120h] [rbp+20h]
  char v50; // [rsp+1A0h] [rbp+A0h]
  _BYTE v51[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v52; // [rsp+1F0h] [rbp+F0h]
  _BYTE v53[248]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int8 v54; // [rsp+2F8h] [rbp+1F8h]
  char v55; // [rsp+300h] [rbp+200h]
  _BYTE v56[256]; // [rsp+310h] [rbp+210h] BYREF
  char v57; // [rsp+410h] [rbp+310h]
  wmi::RefBase *v58; // [rsp+468h] [rbp+368h] BYREF
  int v59; // [rsp+470h] [rbp+370h]

  v59 = a3;
  EventService::WaitForInit(this);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8 || (unsigned __int64)(v8 + 1) > 0x100 )
  {
LABEL_90:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 15000);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v38 = 0;
    v39 = 15000;
    v40 = -1;
    v41 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v9 = a2;
  v10 = &a2[v8];
  while ( v9 != v10 )
  {
    if ( *v9 <= 0x3Fu )
    {
      v11 = 0xD40004C4FFFFFFFFuLL;
      if ( _bittest64((const __int64 *)&v11, *v9) )
        goto LABEL_90;
    }
    if ( *v9 == 92 || *v9 == 124 )
      goto LABEL_90;
    ++v9;
  }
  *(_OWORD *)a4 = 0;
  v12 = operator new(0x1F8u);
  v14 = v12;
  if ( v12 )
  {
    LOBYTE(v13) = 0;
    memset_0(v12, v13, 0x1F8u);
  }
  else
  {
    v14 = 0;
  }
  v43 = v14;
  do
    ++v7;
  while ( a2[v7] );
  v15 = RpcImpersonateClient(0);
  v16 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v15);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v38 = 0;
    v39 = v16;
    v40 = -1;
    v41 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  BYTE1(v59) = 1;
  memset_0(v53, 0, 0x108u);
  v53[0] = 0;
  v55 = 0;
  v17 = -1;
  do
    ++v17;
  while ( a2[v17] );
  v34 = a2;
  v35 = v17;
  ChannelManager::GetExistingChannel(&this[45], &v36, &v34);
  v18 = v36;
  if ( v36 )
  {
    v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v36 + 16);
    v58 = (wmi::RefBase *)((char *)v36 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v36 + 16));
    v20 = (wmi::RefBase *)((char *)v18 + 168);
    v18 = 0;
    v44[0] = 0;
    v50 = 0;
    if ( *((_BYTE *)v20 + 256) )
    {
      ChannelConfigSnapshot::ChannelConfigSnapshot((ChannelConfigSnapshot *)v44, v20);
      v50 = 1;
    }
    LeaveCriticalSection(v19);
    if ( v50 )
    {
      if ( v55 )
      {
        ChannelConfigSnapshot::operator=(v53, v44);
      }
      else
      {
        ChannelConfigSnapshot::ChannelConfigSnapshot(v53, v44);
        v55 = 1;
      }
    }
    else
    {
      if ( !v55 )
        goto LABEL_39;
      ChannelConfigSnapshot::`scalar deleting destructor'((ChannelConfigSnapshot *)v53, 0);
      v55 = 0;
    }
    if ( v50 )
      ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v44);
  }
  if ( v55 != (_BYTE)v18 )
    goto LABEL_28;
LABEL_39:
  v34 = a2;
  v35 = v7;
  ChannelConfigReader::ChannelConfigReader(v44, &v34, -1);
  v23 = (const wchar_t *)v47[0];
  v24 = (__int64)(v47[1] - v47[0]) >> 1;
  *(_QWORD *)&v42 = this + 12;
  AcquireSRWLockShared(this + 12);
  BYTE8(v42) = 1;
  v34 = v23;
  v35 = v24;
  if ( this[21].Ptr == &this[19]
    || (v29 = (EventService *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
                                &this[19],
                                &v34),
        v31 = v29,
        v29 == (EventService *)&this[19]) )
  {
    v18 = 0;
LABEL_41:
    memset_0(v51, 0, 0x48u);
    goto LABEL_42;
  }
  v18 = 0;
  if ( (unsigned __int8)tlx::istring_less_ordinal::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(
                          v30,
                          &v34,
                          (char *)v29 + 24) )
    goto LABEL_41;
  v32 = ChannelPolicy::Clone((char *)v31 + 56, &pExceptionObject);
  ChannelPolicy::ChannelPolicy(v51, v32);
  v52 = 1;
  Buffer::~Buffer((Buffer *)((char *)&v40 + 4));
  utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(&pExceptionObject);
LABEL_42:
  ReleaseSRWLockShared(this + 12);
  if ( v52 )
  {
    if ( v49 )
    {
      ChannelPolicy::operator=(v48, v51);
    }
    else
    {
      ChannelPolicy::ChannelPolicy(v48, v51);
      v49 = 1;
    }
LABEL_45:
    if ( v52 )
      ChannelPolicy::~ChannelPolicy((ChannelPolicy *)v51);
    goto LABEL_47;
  }
  if ( v49 )
  {
    ChannelPolicy::~ChannelPolicy((ChannelPolicy *)v48);
    v49 = 0;
    goto LABEL_45;
  }
LABEL_47:
  if ( v55 )
  {
    ChannelConfigSnapshot::`scalar deleting destructor'((ChannelConfigSnapshot *)v53, 0);
    v55 = 0;
  }
  v42 = 0;
  ChannelConfigSnapshot::ChannelConfigSnapshot(v53, v44, &v42);
  v55 = 1;
  utl::_OptionalData1<ChannelPolicy,0>::~_OptionalData1<ChannelPolicy,0>(v48);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v46);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v45);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v44);
LABEL_28:
  memset_0(v56, 0, 0x108u);
  v56[0] = (_BYTE)v18;
  v57 = (char)v18;
  if ( ChannelConfigSnapshot::IsOwnerOfEtwSession((ChannelConfigSnapshot *)v53) )
  {
    v22 = v53;
  }
  else
  {
    if ( v54 )
    {
      if ( v54 != 1 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(v21, v54, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 15007);
        }
        pExceptionObject = 0;
        v38 = 0;
        v39 = 15007;
        v40 = 0x910FFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
      v25 = L"System";
      v26 = 6;
    }
    else
    {
      v25 = L"Application";
      v26 = 11;
    }
    v34 = v25;
    v35 = v26;
    ChannelManager::GetExistingChannel(&this[45], &v58, &v34);
    v27 = v58;
    if ( v58 )
    {
      ChannelConfig = Channel::GetChannelConfig(v58, v44);
      if ( *(_BYTE *)(ChannelConfig + 256) == (_BYTE)v18 )
      {
        if ( v57 != (_BYTE)v18 )
        {
          ChannelConfigSnapshot::`scalar deleting destructor'((ChannelConfigSnapshot *)v56, 0);
          v57 = (char)v18;
        }
      }
      else if ( v57 == (_BYTE)v18 )
      {
        ChannelConfigSnapshot::ChannelConfigSnapshot(v56, ChannelConfig);
        v57 = 1;
      }
      else
      {
        ChannelConfigSnapshot::operator=(v56, ChannelConfig);
      }
      if ( v50 != (_BYTE)v18 )
        ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v44);
      v27 = v58;
    }
    if ( v57 == (_BYTE)v18 )
    {
      v34 = v25;
      v35 = v26;
      v33 = ChannelConfigReader::ChannelConfigReader(v44, &v34, -1);
      if ( v57 != (_BYTE)v18 )
      {
        ChannelConfigSnapshot::`scalar deleting destructor'((ChannelConfigSnapshot *)v56, 0);
        v57 = (char)v18;
      }
      v42 = 0;
      ChannelConfigSnapshot::ChannelConfigSnapshot(v56, v33, &v42);
      v57 = 1;
      ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v44);
      v27 = v58;
    }
    v22 = v56;
    if ( v27 )
      wmi::RefBase::Release(v27);
  }
  *((_QWORD *)a4 + 1) = v14;
  *(_DWORD *)a4 = 21;
  if ( v55 == (_BYTE)v18 )
    __int2c();
  ReadChannelMetaProps(v53, v22, a4);
  if ( v57 != (_BYTE)v18 )
    ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v56);
  if ( v36 )
    wmi::RefBase::Release(v36);
  v36 = v18;
  if ( v55 != (_BYTE)v18 )
    ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v53);
  RpcRevertToSelf();
}

```

## disassembly

```asm
0x180017370  mov     [rsp-8+arg_0], rbx
0x180017375  mov     [rsp-8+arg_10], r8d
0x18001737a  push    rbp
0x18001737b  push    rsi
0x18001737c  push    rdi
0x18001737d  push    r12
0x18001737f  push    r13
0x180017381  push    r14
0x180017383  push    r15
0x180017385  lea     rbp, [rsp-320h]
0x18001738d  sub     rsp, 420h
0x180017394  mov     r12, r9
0x180017397  mov     rbx, rdx
0x18001739a  mov     r13, rcx
0x18001739d  xor     esi, esi
0x18001739f  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x1800173a4  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800173a8  mov     r8, r14
0x1800173ab  inc     r8
0x1800173ae  cmp     [rbx+r8*2], si
0x1800173b3  jnz     short loc_1800173AB
0x1800173b5  test    r8, r8
0x1800173b8  jz      loc_180017A9B
0x1800173be  lea     rax, [r8+1]
0x1800173c2  cmp     rax, 100h
0x1800173c8  ja      loc_180017A9B
0x1800173ce  mov     rax, rbx
0x1800173d1  lea     rcx, [rbx+r8*2]
0x1800173d5  cmp     rax, rcx
0x1800173d8  jz      short loc_180017411
0x1800173da  cmp     word ptr [rax], 3Fh ; '?'
0x1800173de  ja      short loc_1800173F7
0x1800173e0  movzx   edx, word ptr [rax]
0x1800173e3  mov     r8, 0D40004C4FFFFFFFFh
0x1800173ed  bt      r8, rdx
0x1800173f1  jb      loc_180017A9B
0x1800173f7  cmp     word ptr [rax], 5Ch ; '\'
0x1800173fb  jz      loc_180017A9B
0x180017401  cmp     word ptr [rax], 7Ch ; '|'
0x180017405  jz      loc_180017A9B
0x18001740b  add     rax, 2
0x18001740f  jmp     short loc_1800173D5
0x180017411  xorps   xmm0, xmm0
0x180017414  movups  xmmword ptr [r12], xmm0
0x180017419  mov     edi, 1F8h
0x18001741e  mov     ecx, edi; dwBytes
0x180017420  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017425  mov     r15, rax
0x180017428  test    rax, rax
0x18001742b  jnz     loc_18001772D
0x180017431  mov     r15, rsi
0x180017434  mov     [rbp+350h+var_3C0], r15
0x180017438  inc     r14
0x18001743b  cmp     [rbx+r14*2], si
0x180017440  jnz     short loc_180017438
0x180017442  xor     ecx, ecx; BindingHandle
0x180017444  call    cs:__imp_RpcImpersonateClient
0x18001744a  mov     edi, eax
0x18001744c  test    eax, eax
0x18001744e  jnz     loc_180017847
0x180017454  mov     byte ptr [rbp+350h+arg_10+1], 1
0x18001745b  xor     edx, edx; Val
0x18001745d  mov     r8d, 108h; Size
0x180017463  lea     rcx, [rbp+350h+var_250]; void *
0x18001746a  call    memset_0
0x18001746f  mov     [rbp+350h+var_250], sil
0x180017476  mov     [rbp+350h+var_150], sil
0x18001747d  lea     rcx, [r13+168h]
0x180017484  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017488  inc     rax
0x18001748b  cmp     [rbx+rax*2], si
0x18001748f  jnz     short loc_180017488
0x180017491  mov     [rsp+450h+var_430], rbx
0x180017496  mov     [rsp+450h+var_428], rax
0x18001749b  lea     r8, [rsp+450h+var_430]
0x1800174a0  lea     rdx, [rsp+450h+var_420]
0x1800174a5  call    ?GetExistingChannel@ChannelManager@@QEAA?AV?$AutoRef@VChannel@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; ChannelManager::GetExistingChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800174aa  nop
0x1800174ab  mov     rsi, [rsp+450h+var_420]
0x1800174b0  test    rsi, rsi
0x1800174b3  jz      loc_180017547
0x1800174b9  lea     rdi, [rsi+10h]
0x1800174bd  mov     [rbp+350h+arg_8], rdi
0x1800174c4  mov     rcx, rdi; lpCriticalSection
0x1800174c7  call    cs:__imp_EnterCriticalSection
0x1800174cd  nop
0x1800174ce  lea     rdx, [rsi+0A8h]; struct ChannelConfigSnapshot *
0x1800174d5  xor     esi, esi
0x1800174d7  mov     [rbp+350h+var_3B0], sil
0x1800174db  mov     [rbp+350h+var_2B0], sil
0x1800174e2  cmp     [rdx+100h], sil
0x1800174e9  jz      short loc_1800174FB
0x1800174eb  lea     rcx, [rbp+350h+var_3B0]; this
0x1800174ef  call    ??0ChannelConfigSnapshot@@QEAA@AEBV0@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigSnapshot const &)
0x1800174f4  mov     [rbp+350h+var_2B0], 1
0x1800174fb  mov     rcx, rdi; lpCriticalSection
0x1800174fe  call    cs:__imp_LeaveCriticalSection
0x180017504  cmp     [rbp+350h+var_2B0], sil
0x18001750b  jz      loc_1800178C4
0x180017511  lea     rdx, [rbp+350h+var_3B0]
0x180017515  lea     rcx, [rbp+350h+var_250]
0x18001751c  cmp     [rbp+350h+var_150], sil
0x180017523  jnz     loc_1800178BA
0x180017529  call    ??0ChannelConfigSnapshot@@QEAA@$$QEAV0@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigSnapshot &&)
0x18001752e  mov     [rbp+350h+var_150], 1
0x180017535  cmp     [rbp+350h+var_2B0], sil
0x18001753c  jz      short loc_180017547
0x18001753e  lea     rcx, [rbp+350h+var_3B0]; this
0x180017542  call    ??1ChannelConfigSnapshot@@QEAA@XZ; ChannelConfigSnapshot::~ChannelConfigSnapshot(void)
0x180017547  cmp     [rbp+350h+var_150], sil
0x18001754e  jz      loc_180017620
0x180017554  xor     edx, edx; Val
0x180017556  mov     r8d, 108h; Size
0x18001755c  lea     rcx, [rbp+350h+var_140]; void *
0x180017563  call    memset_0
0x180017568  mov     [rbp+350h+var_140], sil
0x18001756f  mov     [rbp+350h+var_40], sil
0x180017576  lea     rcx, [rbp+350h+var_250]; this
0x18001757d  call    ?IsOwnerOfEtwSession@ChannelConfigSnapshot@@QEBA_NXZ; ChannelConfigSnapshot::IsOwnerOfEtwSession(void)
0x180017582  test    al, al
0x180017584  jz      loc_18001775E
0x18001758a  lea     rbx, [rbp+350h+var_250]
0x180017591  mov     [r12+8], r15
0x180017596  mov     dword ptr [r12], 15h
0x18001759e  cmp     [rbp+350h+var_150], sil
0x1800175a5  jz      loc_180017A18
0x1800175ab  mov     r8, r12
0x1800175ae  mov     rdx, rbx
0x1800175b1  lea     rcx, [rbp+350h+var_250]
0x1800175b8  call    ReadChannelMetaProps
0x1800175bd  nop
0x1800175be  cmp     [rbp+350h+var_40], sil
0x1800175c5  jz      short loc_1800175D4
0x1800175c7  lea     rcx, [rbp+350h+var_140]; this
0x1800175ce  call    ??1ChannelConfigSnapshot@@QEAA@XZ; ChannelConfigSnapshot::~ChannelConfigSnapshot(void)
0x1800175d3  nop
0x1800175d4  mov     rcx, [rsp+450h+var_420]; this
0x1800175d9  test    rcx, rcx
0x1800175dc  jz      short loc_1800175E3
0x1800175de  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800175e3  mov     [rsp+450h+var_420], rsi
0x1800175e8  cmp     [rbp+350h+var_150], sil
0x1800175ef  jz      short loc_1800175FE
0x1800175f1  lea     rcx, [rbp+350h+var_250]; this
0x1800175f8  call    ??1ChannelConfigSnapshot@@QEAA@XZ; ChannelConfigSnapshot::~ChannelConfigSnapshot(void)
0x1800175fd  nop
0x1800175fe  call    cs:__imp_RpcRevertToSelf
0x180017604  nop
0x180017605  mov     rbx, [rsp+450h+arg_0]
0x18001760d  add     rsp, 420h
0x180017614  pop     r15
0x180017616  pop     r14
0x180017618  pop     r13
0x18001761a  pop     r12
0x18001761c  pop     rdi
0x18001761d  pop     rsi
0x18001761e  pop     rbp
0x18001761f  retn
0x180017620  mov     [rsp+450h+var_430], rbx
0x180017625  mov     [rsp+450h+var_428], r14
0x18001762a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001762e  lea     rdx, [rsp+450h+var_430]
0x180017633  lea     rcx, [rbp+350h+var_3B0]
0x180017637  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x18001763c  nop
0x18001763d  lea     r14, [r13+60h]
0x180017641  mov     rbx, [rbp+350h+var_390]
0x180017645  mov     rdi, [rbp+350h+var_388]
0x180017649  sub     rdi, rbx
0x18001764c  sar     rdi, 1
0x18001764f  mov     qword ptr [rbp+350h+var_3D0], r14
0x180017653  mov     rcx, r14; SRWLock
0x180017656  call    cs:__imp_AcquireSRWLockShared
0x18001765c  mov     byte ptr [rbp+350h+var_3D0+8], 1
0x180017660  lea     rsi, [r14+38h]
0x180017664  mov     [rsp+450h+var_430], rbx
0x180017669  mov     [rsp+450h+var_428], rdi
0x18001766e  cmp     [rsi+10h], rsi
0x180017672  jnz     loc_1800178EB
0x180017678  xor     esi, esi
0x18001767a  xor     edx, edx; Val
0x18001767c  lea     r8d, [rdx+48h]; Size
0x180017680  lea     rcx, [rbp+350h+var_2A0]; void *
0x180017687  call    memset_0
0x18001768c  nop
0x18001768d  mov     rcx, r14; SRWLock
0x180017690  call    cs:__imp_ReleaseSRWLockShared
0x180017696  cmp     [rbp+350h+var_260], sil
0x18001769d  jnz     loc_18001773F
0x1800176a3  cmp     [rbp+350h+var_330], sil
0x1800176a7  jz      short loc_1800176CB
0x1800176a9  lea     rcx, [rbp+350h+var_370]; this
0x1800176ad  call    ??1ChannelPolicy@@QEAA@XZ; ChannelPolicy::~ChannelPolicy(void)
0x1800176b2  mov     [rbp+350h+var_330], sil
0x1800176b6  cmp     [rbp+350h+var_260], sil
0x1800176bd  jz      short loc_1800176CB
0x1800176bf  lea     rcx, [rbp+350h+var_2A0]; this
0x1800176c6  call    ??1ChannelPolicy@@QEAA@XZ; ChannelPolicy::~ChannelPolicy(void)
0x1800176cb  cmp     [rbp+350h+var_150], sil
0x1800176d2  jnz     loc_180017959
0x1800176d8  xorps   xmm0, xmm0
0x1800176db  movdqa  [rbp+350h+var_3D0], xmm0
0x1800176e0  lea     r8, [rbp+350h+var_3D0]
0x1800176e4  lea     rdx, [rbp+350h+var_3B0]
0x1800176e8  lea     rcx, [rbp+350h+var_250]
0x1800176ef  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800176f4  mov     [rbp+350h+var_150], 1
0x1800176fb  lea     rcx, [rbp+350h+var_370]
0x1800176ff  call    ??1?$_OptionalData1@VChannelPolicy@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<ChannelPolicy,0>::~_OptionalData1<ChannelPolicy,0>(void)
0x180017704  lea     rcx, [rbp+350h+var_390]; void *
0x180017708  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001770d  lea     rcx, [rbp+350h+var_3A0]
0x180017711  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180017716  lea     rcx, [rbp+350h+var_3A8]
0x18001771a  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18001771f  lea     rcx, [rbp+350h+var_3B0]
0x180017723  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180017728  jmp     loc_180017554
0x18001772d  mov     r8, rdi; Size
0x180017730  xor     dl, dl; Val
0x180017732  mov     rcx, rax; void *
0x180017735  call    memset_0
0x18001773a  jmp     loc_180017434
0x18001773f  lea     rdx, [rbp+350h+var_2A0]
0x180017746  lea     rcx, [rbp+350h+var_370]
0x18001774a  cmp     [rbp+350h+var_330], sil
0x18001774e  jz      loc_180017828
0x180017754  call    ??4ChannelPolicy@@QEAAAEAV0@$$QEAV0@@Z; ChannelPolicy::operator=(ChannelPolicy &&)
0x180017759  jmp     loc_1800176B6
0x18001775e  movzx   edx, [rbp+350h+var_158]
0x180017765  test    edx, edx
0x180017767  jz      loc_180017836
0x18001776d  cmp     edx, 1
0x180017770  jnz     loc_180017A1F
0x180017776  lea     rbx, aSystem; "System"
0x18001777d  lea     edi, [rdx+5]
0x180017780  mov     [rsp+450h+var_430], rbx
0x180017785  mov     [rsp+450h+var_428], rdi
0x18001778a  lea     r8, [rsp+450h+var_430]
0x18001778f  lea     rdx, [rbp+350h+arg_8]
0x180017796  lea     rcx, [r13+168h]
0x18001779d  call    ?GetExistingChannel@ChannelManager@@QEAA?AV?$AutoRef@VChannel@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; ChannelManager::GetExistingChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800177a2  nop
0x1800177a3  mov     rcx, [rbp+350h+arg_8]
0x1800177aa  test    rcx, rcx
0x1800177ad  jz      short loc_180017801
0x1800177af  lea     rdx, [rbp+350h+var_3B0]
0x1800177b3  call    ?GetChannelConfig@Channel@@QEBA?AV?$optional@VChannelConfigSnapshot@@@utl@@XZ; Channel::GetChannelConfig(void)
0x1800177b8  cmp     [rax+100h], sil
0x1800177bf  jz      loc_18001797D
0x1800177c5  mov     rdx, rax
0x1800177c8  lea     rcx, [rbp+350h+var_140]
0x1800177cf  cmp     [rbp+350h+var_40], sil
0x1800177d6  jnz     loc_180017973
0x1800177dc  call    ??0ChannelConfigSnapshot@@QEAA@$$QEAV0@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigSnapshot &&)
0x1800177e1  mov     [rbp+350h+var_40], 1
0x1800177e8  cmp     [rbp+350h+var_2B0], sil
0x1800177ef  jz      short loc_1800177FA
0x1800177f1  lea     rcx, [rbp+350h+var_3B0]; this
0x1800177f5  call    ??1ChannelConfigSnapshot@@QEAA@XZ; ChannelConfigSnapshot::~ChannelConfigSnapshot(void)
0x1800177fa  mov     rcx, [rbp+350h+arg_8]; this
0x180017801  cmp     [rbp+350h+var_40], sil
0x180017808  jz      loc_1800179A4
0x18001780e  lea     rbx, [rbp+350h+var_140]
0x180017815  test    rcx, rcx
0x180017818  jz      loc_180017591
0x18001781e  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180017823  jmp     loc_180017591
0x180017828  call    ??0ChannelPolicy@@QEAA@$$QEAV0@@Z; ChannelPolicy::ChannelPolicy(ChannelPolicy &&)
0x18001782d  mov     [rbp+350h+var_330], 1
0x180017831  jmp     loc_1800176B6
0x180017836  lea     rbx, aApplication; "Application"
0x18001783d  mov     edi, 0Bh
0x180017842  jmp     loc_180017780
0x180017847  lea     rcx, WPP_GLOBAL_Control
0x18001784e  mov     r10, cs:WPP_GLOBAL_Control
0x180017855  cmp     r10, rcx
0x180017858  jz      short loc_180017880
0x18001785a  test    byte ptr [r10+1Ch], 8
0x18001785f  jz      short loc_180017880
0x180017861  cmp     byte ptr [r10+19h], 2
0x180017866  jb      short loc_180017880
0x180017868  mov     edx, 6Bh ; 'k'
0x18001786d  mov     r9d, edi
0x180017870  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180017877  mov     rcx, [r10+10h]
0x18001787b  call    WPP_SF_d
0x180017880  lea     rax, byte_1800EC961
0x180017887  mov     qword ptr [rsp+450h+pExceptionObject], rax
0x18001788c  mov     qword ptr [rsp+450h+pExceptionObject+8], rsi
0x180017891  mov     [rsp+450h+var_408], rsi
0x180017896  mov     [rsp+450h+var_400], edi
0x18001789a  mov     [rsp+450h+var_3FC], 0FFFFFFFFFFFFFFFFh
0x1800178a3  mov     [rsp+450h+var_3F4], sil
0x1800178a8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800178af  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800178b4  call    _CxxThrowException_0
0x1800178ba  call    ??4ChannelConfigSnapshot@@QEAAAEAV0@$$QEAV0@@Z; ChannelConfigSnapshot::operator=(ChannelConfigSnapshot &&)
0x1800178bf  jmp     loc_180017535
0x1800178c4  cmp     [rbp+350h+var_150], sil
  ... truncated ...
```
