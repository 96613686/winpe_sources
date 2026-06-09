# EventService::GetPublisherList(ulong &,wchar_t * * &)

- ea: `0x18007b190`
- end: `0x18007badd`
- name: `?GetPublisherList@EventService@@QEAAXAEAKAEAPEAPEA_W@Z`
- size: `2381`
- prototype: `void __fastcall(RTL_SRWLOCK *this, unsigned int *, wchar_t ***)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800a8e80`

## callees

- `0x180003de0`
- `0x1800064f0`
- `0x180006600`
- `0x180006770`
- `0x180006e60`
- `0x180006fb0`
- `0x180008870`
- `0x180008d30`
- `0x1800092c4`
- `0x180017128`
- `0x180017b60`
- `0x180017b98`
- `0x18002c6f4`
- `0x18002d934`
- `0x18002de9c`
- `0x18003be9c`
- `0x18003d1dc`
- `0x180054848`
- `0x18005667c`
- `0x18006fc64`
- `0x180074c48`
- `0x180075f00`
- `0x180077f8c`
- `0x18007b190`
- `0x180088e9c`
- `0x18008d8a8`
- `0x180090d74`
- `0x1800916a0`
- `0x180092008`
- `0x1800929b4`
- `0x180092c6c`
- `0x180092d78`
- `0x18009aee0`
- `0x18009bb88`
- `0x18009f870`
- `0x1800a19d8`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18007b1e2`
- `RPCRT4!RpcImpersonateClient` at `0x18007b1e2`
- `RPCRT4!RpcRevertToSelf` at `0x18007b861`
- `RPCRT4!RpcRevertToSelf` at `0x18007b861`

## string_xrefs

- `0x18007b220`: `SYSTEM\CurrentControlSet\Services\Eventlog`

## pseudocode

```c
void __fastcall EventService::GetPublisherList(RTL_SRWLOCK *this, unsigned int *a2, wchar_t ***a3)
{
  wchar_t ***v3; // r13
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  HKEY *v8; // rdi
  __m128i v9; // xmm6
  HKEY v10; // rbx
  HKEY *v11; // rax
  HKEY v12; // rbx
  int v13; // eax
  void *v14; // rbx
  __int64 v15; // r13
  __int64 v16; // rax
  const char *v17; // r8
  HKEY v18; // r15
  const char *v19; // r8
  __int64 v20; // r9
  void *v21; // r15
  __int64 v22; // rbx
  wchar_t ***v23; // rbx
  const char *v24; // r8
  HKEY v25; // r15
  const char *v26; // r8
  void *v27; // rcx
  const char *v28; // r8
  HKEY v29; // rbx
  const char *v30; // r8
  HKEY *v31; // r14
  __int64 v32; // rcx
  HKEY *v33; // rbx
  HKEY *i; // rsi
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rdi
  HKEY v37; // rdx
  unsigned __int64 j; // rcx
  HKEY v39; // rax
  HKEY v40; // [rsp+38h] [rbp-D0h] BYREF
  void *v41; // [rsp+40h] [rbp-C8h] BYREF
  char v42; // [rsp+48h] [rbp-C0h]
  char v43; // [rsp+49h] [rbp-BFh]
  __m128i si128; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A8h]
  wchar_t ***v46; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+70h] [rbp-98h] BYREF
  _WORD v48[12]; // [rsp+80h] [rbp-88h] BYREF
  void *v49; // [rsp+98h] [rbp-70h] BYREF
  char *v50; // [rsp+A0h] [rbp-68h]
  _WORD v51[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v52; // [rsp+B8h] [rbp-50h] BYREF
  void *v53; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-38h]
  __int128 v55; // [rsp+D8h] [rbp-30h] BYREF
  struct _GUID v56; // [rsp+E8h] [rbp-20h] BYREF
  HKEY hKey[2]; // [rsp+F8h] [rbp-10h] BYREF
  void *Src; // [rsp+108h] [rbp+0h]
  __int64 v59; // [rsp+110h] [rbp+8h]
  __int64 v60; // [rsp+118h] [rbp+10h]
  char v61[520]; // [rsp+120h] [rbp+18h] BYREF
  HKEY v62[2]; // [rsp+328h] [rbp+220h] BYREF
  __int128 v63; // [rsp+338h] [rbp+230h]
  int v64; // [rsp+348h] [rbp+240h]
  int v65; // [rsp+34Ch] [rbp+244h]
  _BYTE v66[16]; // [rsp+558h] [rbp+450h] BYREF
  void *v67; // [rsp+568h] [rbp+460h]
  __int64 v68; // [rsp+570h] [rbp+468h]
  int v69; // [rsp+578h] [rbp+470h]
  int v70; // [rsp+57Ch] [rbp+474h]

  v3 = a3;
  v46 = a3;
  EventService::WaitForInit(this);
  *a2 = 0;
  *v3 = 0;
  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v5);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v6);
    throw (EvtException *)pExceptionObject;
  }
  v43 = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v45 = -1;
  utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_SetCapacity(
    &si128,
    1400);
  RegistryKeyEnumerator::RegistryKeyEnumerator(
    (RegistryKeyEnumerator *)v62,
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Services\\Eventlog",
    (void *)0xFFFFFFFFFFFFFFFFLL);
  v64 = v65;
  v7 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v62);
  v8 = (HKEY *)si128.m128i_i64[1];
  if ( v7 != 259 )
  {
    v9 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
    do
    {
      v52 = v63;
      if ( !(unsigned __int8)ShouldSkipLegacyChannelKey(&v52) )
      {
        v40 = 0;
        v10 = v62[1];
        v11 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v40);
        OpenRegKey(v62[0], (const wchar_t *)v63, 0x20019u, v11, v10);
        v12 = v40;
        if ( v40 )
        {
          *(__m128i *)hKey = v9;
          Src = (void *)&pszFormat;
          v59 = 0;
          v60 = 0;
          memset_0(v61, 0, 0x200u);
          v13 = RegistryKeyEnumerator::Reset(
                  (RegistryKeyEnumerator *)hKey,
                  v12,
                  &pszFormat,
                  (void *)0xFFFFFFFFFFFFFFFFLL);
          if ( v13 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v55 = v63;
              WPP_SF__utlwsv_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                120,
                (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                (unsigned int)&v55,
                v13);
            }
          }
          else
          {
            LODWORD(v60) = HIDWORD(v60);
            while ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey) != 259 )
            {
              v14 = Src;
              v15 = v59;
              v56 = 0;
              if ( !GetRegCacheProviderGuidForName((const wchar_t *)Src, &v56) )
              {
                pExceptionObject[0] = v48;
                pExceptionObject[1] = v48;
                v48[0] = 0;
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                  pExceptionObject,
                  36);
                if ( (unsigned int)RegReadStringValueNoThrow(hKey[0])
                  || !tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                        &v56,
                        pExceptionObject) )
                {
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pExceptionObject);
                  utl::make_unique_for_overwrite<wchar_t [0],0>(&v41, v15 + 1);
                  v18 = (HKEY)v41;
                  if ( !v41 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        121,
                        &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                        14);
                    }
                    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v17, 2630);
                    throw (EvtException *)pExceptionObject;
                  }
                  memcpy_0(v41, v14, 2 * v15 + 2);
                  if ( v8 == (HKEY *)v45 )
                  {
                    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(
                                             &si128,
                                             &v41) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          122,
                          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                          14);
                      }
                      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v19, 2637);
                      throw (EvtException *)pExceptionObject;
                    }
                    v8 = (HKEY *)si128.m128i_i64[1];
                  }
                  else
                  {
                    v41 = 0;
                    *v8++ = v18;
                    si128.m128i_i64[1] = (__int64)v8;
                  }
                  utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v41);
                }
                else
                {
                  v16 = -1;
                  do
                    ++v16;
                  while ( *((_WORD *)v14 + v16) );
                  v53 = v14;
                  v54 = v16;
                  AddRegCacheProviderGuidForName(&v53, &v56);
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pExceptionObject);
                }
              }
            }
          }
          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
        }
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v40);
      }
    }
    while ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v62) != 259 );
    v3 = v46;
  }
  v49 = v51;
  v50 = (char *)v51;
  v51[0] = 0;
  PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)v66, (void *)0xFFFFFFFFFFFFFFFFLL);
  v69 = v70;
  if ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v66) != 259 )
  {
    while ( 1 )
    {
      v55 = 0;
      v21 = v67;
      v53 = v67;
      v22 = v68;
      v54 = v68;
      if ( !v68 || !tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(&v55, &v53) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          *(_QWORD *)&v52 = v21;
          *((_QWORD *)&v52 + 1) = v22;
          WPP_SF__utlwsv_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            123,
            &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
            &v52);
        }
        goto LABEL_54;
      }
      GetRegCacheProviderNodebyGuid(&v46, &v55);
      v23 = v46;
      if ( !v46 )
        break;
      if ( ((_BYTE)v46[24] & 4) != 0 )
      {
        utl::make_unique_for_overwrite<wchar_t [0],0>(&v40, (char *)v46[4] + 1);
        v25 = v40;
        if ( !v40 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v24, 2668);
          throw (EvtException *)pExceptionObject;
        }
        memcpy_0(v40, v23[3], 2LL * (_QWORD)v23[4]);
        *((_WORD *)v25 + (_QWORD)v23[4]) = 0;
        if ( v8 == (HKEY *)v45 )
        {
          if ( !(unsigned __int8)utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(
                                   &si128,
                                   &v40) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v26, 2676);
            throw (EvtException *)pExceptionObject;
          }
          v8 = (HKEY *)si128.m128i_i64[1];
        }
        else
        {
          v40 = 0;
          *v8++ = v25;
          si128.m128i_i64[1] = (__int64)v8;
        }
        v27 = &v40;
LABEL_48:
        utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(v27);
      }
LABEL_49:
      wmi::AutoRef<PublisherMetadata>::Release(&v46);
LABEL_54:
      if ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v66) == 259 )
        goto LABEL_55;
    }
    if ( !(unsigned __int8)PublisherConfigEnumerator::GetCurrentPublisherName(v66, &v49) || v49 == v50 )
      goto LABEL_49;
    utl::make_unique_for_overwrite<wchar_t [0],0>(&v41, ((v50 - (_BYTE *)v49) >> 1) + 1);
    v29 = (HKEY)v41;
    if ( !v41 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v28, 2685);
      throw (EvtException *)pExceptionObject;
    }
    memcpy_0(v41, v49, 2 * ((v50 - (_BYTE *)v49) >> 1) + 2);
    if ( v8 == (HKEY *)v45 )
    {
      if ( !(unsigned __int8)utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(
                               &si128,
                               &v41) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v30, 2692);
        throw (EvtException *)pExceptionObject;
      }
      v8 = (HKEY *)si128.m128i_i64[1];
    }
    else
    {
      v41 = 0;
      *v8++ = v29;
      si128.m128i_i64[1] = (__int64)v8;
    }
    v27 = &v41;
    goto LABEL_48;
  }
LABEL_55:
  v31 = (HKEY *)si128.m128i_i64[0];
  LOBYTE(v20) = v42;
  utl::_SortImp_utl::_ArrayIt_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0_________int64__EventService::GetPublisherList_::_2_::_lambda_2___(
    si128.m128i_i64[0],
    v8,
    ((__int64)v8 - si128.m128i_i64[0]) >> 3,
    v20);
  v33 = v31;
  if ( v31 != v8 )
  {
    for ( i = v31; ; v33 = i )
    {
      if ( ++i == v8 )
      {
        v33 = v8;
        goto LABEL_65;
      }
      if ( (unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_3_::operator()(v32, v33, i) )
        break;
    }
    while ( ++i != v8 )
    {
      if ( !(unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_3_::operator()(v32, v33, i) )
        utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(++v33, i);
    }
    ++v33;
  }
LABEL_65:
  v35 = v33 - v31;
  v36 = 0xFFFFFFFFLL;
  if ( v35 <= 0xFFFFFFFF )
  {
    if ( !v35 )
      goto LABEL_73;
    v36 = v35;
  }
  utl::make_unique_for_overwrite<wchar_t * [0],0>(&v40, v36);
  v37 = v40;
  if ( v40 )
  {
    for ( j = 0; j < v36; ++j )
    {
      v39 = v31[j];
      v31[j] = 0;
      *((_QWORD *)v37 + j) = v39;
    }
    v40 = 0;
    *v3 = (wchar_t **)v37;
    *a2 = v36;
  }
  utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v40);
LABEL_73:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v66);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v49);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v62);
  utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_Uninit(&si128);
  RpcRevertToSelf();
}

```

## disassembly

```asm
0x18007b190  mov     rax, rsp
0x18007b193  mov     [rax+20h], rbx
0x18007b197  push    rbp
0x18007b198  push    rsi
0x18007b199  push    rdi
0x18007b19a  push    r12
0x18007b19c  push    r13
0x18007b19e  push    r14
0x18007b1a0  push    r15
0x18007b1a2  lea     rbp, [rax-6D8h]
0x18007b1a9  sub     rsp, 7A0h
0x18007b1b0  movaps  xmmword ptr [rax-48h], xmm6
0x18007b1b4  mov     rax, cs:__security_cookie
0x18007b1bb  xor     rax, rsp
0x18007b1be  mov     [rbp+6D0h+var_50], rax
0x18007b1c5  mov     r13, r8
0x18007b1c8  mov     [rsp+7D0h+var_770], r8
0x18007b1cd  mov     r12, rdx
0x18007b1d0  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x18007b1d5  xor     r15d, r15d
0x18007b1d8  mov     [r12], r15d
0x18007b1dc  mov     [r13+0], r15
0x18007b1e0  xor     ecx, ecx; BindingHandle
0x18007b1e2  call    cs:__imp_RpcImpersonateClient
0x18007b1e8  mov     ebx, eax
0x18007b1ea  test    eax, eax
0x18007b1ec  jnz     loc_18007B8E9
0x18007b1f2  mov     byte ptr [rsp+7D0h+var_790+1], 1
0x18007b1f7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18007b1ff  movdqu  [rsp+7D0h+var_790+8], xmm0
0x18007b205  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007b209  mov     [rsp+7D0h+var_778], rbx
0x18007b20e  mov     edx, 578h
0x18007b213  lea     rcx, [rsp+7D0h+var_790+8]
0x18007b218  call    ?_SetCapacity@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_SetCapacity(unsigned __int64)
0x18007b21d  mov     r9, rbx; void *
0x18007b220  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18007b227  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18007b22e  lea     rcx, [rbp+6D0h+var_4B0]; this
0x18007b235  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEB_WPEAX@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,wchar_t const *,void *)
0x18007b23a  nop
0x18007b23b  mov     eax, [rbp+6D0h+var_48C]
0x18007b241  mov     [rbp+6D0h+var_490], eax
0x18007b247  lea     rcx, [rbp+6D0h+var_4B0]; this
0x18007b24e  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18007b253  lea     rsi, WPP_GLOBAL_Control
0x18007b25a  lea     r14, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18007b261  mov     rdi, [rsp+7D0h+var_780]
0x18007b266  cmp     eax, 103h
0x18007b26b  jz      loc_18007B522
0x18007b271  lea     r13, pszFormat
0x18007b278  movdqa  xmm6, cs:__xmm@ffffffffffffffff0000000000000000
0x18007b280  mov     rax, qword ptr [rbp+6D0h+var_4A0]
0x18007b287  mov     rcx, qword ptr [rbp+6D0h+var_4A0+8]
0x18007b28e  mov     qword ptr [rbp+6D0h+var_720], rax
0x18007b292  mov     qword ptr [rbp+6D0h+var_720+8], rcx
0x18007b296  lea     rcx, [rbp+6D0h+var_720]
0x18007b29a  call    ?ShouldSkipLegacyChannelKey@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ShouldSkipLegacyChannelKey(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18007b29f  test    al, al
0x18007b2a1  jnz     loc_18007B502
0x18007b2a7  mov     [rsp+7D0h+var_7A0], r15
0x18007b2ac  mov     rbx, [rbp+6D0h+var_4A8]
0x18007b2b3  lea     rcx, [rsp+7D0h+var_7A0]
0x18007b2b8  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18007b2bd  mov     [rsp+7D0h+var_7B0], rbx; void *
0x18007b2c2  mov     r9, rax; HKEY *
0x18007b2c5  mov     r8d, 20019h; unsigned int
0x18007b2cb  mov     rdx, qword ptr [rbp+6D0h+var_4A0]; wchar_t *
0x18007b2d2  mov     rcx, [rbp+6D0h+var_4B0]; HKEY
0x18007b2d9  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18007b2de  nop
0x18007b2df  mov     rbx, [rsp+7D0h+var_7A0]
0x18007b2e4  test    rbx, rbx
0x18007b2e7  jz      loc_18007B4F8
0x18007b2ed  movdqa  xmmword ptr [rbp+6D0h+hKey], xmm6
0x18007b2f2  mov     [rbp+6D0h+Src], r13
0x18007b2f6  mov     [rbp+6D0h+var_6C8], r15
0x18007b2fa  mov     [rbp+6D0h+var_6C0], 0
0x18007b302  xor     edx, edx; Val
0x18007b304  mov     r8d, 200h; Size
0x18007b30a  lea     rcx, [rbp+6D0h+var_6B8]; void *
0x18007b30e  call    memset_0
0x18007b313  nop
0x18007b314  or      r9, 0FFFFFFFFFFFFFFFFh; void *
0x18007b318  mov     r8, r13; wchar_t *
0x18007b31b  mov     rdx, rbx; HKEY
0x18007b31e  lea     rcx, [rbp+6D0h+hKey]; this
0x18007b322  call    ?Reset@RegistryKeyEnumerator@@QEAAJPEAUHKEY__@@PEB_WPEAX@Z; RegistryKeyEnumerator::Reset(HKEY__ *,wchar_t const *,void *)
0x18007b327  mov     r8d, eax
0x18007b32a  test    eax, eax
0x18007b32c  jz      short loc_18007B387
0x18007b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b335  cmp     rcx, rsi
0x18007b338  jz      loc_18007B4EE
0x18007b33e  test    byte ptr [rcx+1Ch], 8
0x18007b342  jz      loc_18007B4EE
0x18007b348  cmp     byte ptr [rcx+19h], 3
0x18007b34c  jb      loc_18007B4EE
0x18007b352  mov     rax, qword ptr [rbp+6D0h+var_4A0]
0x18007b359  mov     rdx, qword ptr [rbp+6D0h+var_4A0+8]
0x18007b360  mov     qword ptr [rbp+6D0h+var_700], rax
0x18007b364  mov     qword ptr [rbp+6D0h+var_700+8], rdx
0x18007b368  mov     edx, 78h ; 'x'
0x18007b36d  mov     dword ptr [rsp+7D0h+var_7B0], r8d
0x18007b372  lea     r9, [rbp+6D0h+var_700]
0x18007b376  mov     r8, r14
0x18007b379  mov     rcx, [rcx+10h]
0x18007b37d  call    WPP_SF__utlwsv_D
0x18007b382  jmp     loc_18007B4EE
0x18007b387  mov     eax, dword ptr [rbp+6D0h+var_6C0+4]
0x18007b38a  mov     dword ptr [rbp+6D0h+var_6C0], eax
0x18007b38d  lea     rcx, [rbp+6D0h+hKey]; this
0x18007b391  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18007b396  cmp     eax, 103h
0x18007b39b  jz      loc_18007B4EE
0x18007b3a1  mov     rbx, [rbp+6D0h+Src]
0x18007b3a5  mov     r13, [rbp+6D0h+var_6C8]
0x18007b3a9  xorps   xmm0, xmm0
0x18007b3ac  movups  xmmword ptr [rbp+6D0h+var_6F0.Data1], xmm0
0x18007b3b0  lea     rdx, [rbp+6D0h+var_6F0]; struct _GUID *
0x18007b3b4  mov     rcx, rbx; wchar_t *
0x18007b3b7  call    ?GetRegCacheProviderGuidForName@@YA_NPEB_WPEAU_GUID@@@Z; GetRegCacheProviderGuidForName(wchar_t const *,_GUID *)
0x18007b3bc  test    al, al
0x18007b3be  jnz     loc_18007B4D3
0x18007b3c4  lea     rax, [rsp+7D0h+var_758]
0x18007b3c9  mov     [rsp+7D0h+pExceptionObject], rax
0x18007b3ce  lea     rax, [rsp+7D0h+var_758]
0x18007b3d3  mov     qword ptr [rsp+7D0h+var_760], rax
0x18007b3d8  mov     [rsp+7D0h+var_758], r15w
0x18007b3de  mov     edx, 24h ; '$'
0x18007b3e3  lea     rcx, [rsp+7D0h+pExceptionObject]
0x18007b3e8  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007b3ed  lea     r9, [rsp+7D0h+pExceptionObject]
0x18007b3f2  lea     r8, aProviderguid; "ProviderGuid"
0x18007b3f9  mov     rdx, rbx
0x18007b3fc  mov     rcx, [rbp+6D0h+hKey]; hKey
0x18007b400  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007b405  test    eax, eax
0x18007b407  jnz     short loc_18007B44F
0x18007b409  lea     rdx, [rsp+7D0h+pExceptionObject]
0x18007b40e  lea     rcx, [rbp+6D0h+var_6F0]
0x18007b412  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x18007b417  test    rax, rax
0x18007b41a  jz      short loc_18007B44F
0x18007b41c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007b420  inc     rax
0x18007b423  cmp     [rbx+rax*2], r15w
0x18007b428  jnz     short loc_18007B420
0x18007b42a  mov     [rbp+6D0h+var_710], rbx
0x18007b42e  mov     [rbp+6D0h+var_708], rax
0x18007b432  lea     rdx, [rbp+6D0h+var_6F0]
0x18007b436  lea     rcx, [rbp+6D0h+var_710]
0x18007b43a  call    ?AddRegCacheProviderGuidForName@@YAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBU_GUID@@@Z; AddRegCacheProviderGuidForName(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_GUID const &)
0x18007b43f  nop
0x18007b440  lea     rcx, [rsp+7D0h+pExceptionObject]; void *
0x18007b445  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007b44a  jmp     loc_18007B4D3
0x18007b44f  lea     rcx, [rsp+7D0h+pExceptionObject]; void *
0x18007b454  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007b459  lea     rdx, [r13+1]
0x18007b45d  lea     rcx, [rsp+7D0h+var_798]
0x18007b462  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18007b467  nop
0x18007b468  mov     r15, [rsp+7D0h+var_798]
0x18007b46d  test    r15, r15
0x18007b470  jz      loc_18007B991
0x18007b476  lea     r8, ds:2[r13*2]; Size
0x18007b47e  mov     rdx, rbx; Src
0x18007b481  mov     rcx, r15; void *
0x18007b484  call    memcpy_0
0x18007b489  cmp     rdi, [rsp+7D0h+var_778]
0x18007b48e  jz      short loc_18007B4AA
0x18007b490  mov     [rsp+7D0h+var_798], 0
0x18007b499  mov     [rdi], r15
0x18007b49c  add     rdi, 8
0x18007b4a0  mov     [rsp+7D0h+var_780], rdi
0x18007b4a5  xor     r15d, r15d
0x18007b4a8  jmp     short loc_18007B4C9
0x18007b4aa  lea     rdx, [rsp+7D0h+var_798]
0x18007b4af  lea     rcx, [rsp+7D0h+var_790+8]
0x18007b4b4  call    ??$_PushBackOne2@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@AEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@@Z; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18007b4b9  xor     r15d, r15d
0x18007b4bc  test    al, al
0x18007b4be  jz      loc_18007B93E
0x18007b4c4  mov     rdi, [rsp+7D0h+var_780]
0x18007b4c9  lea     rcx, [rsp+7D0h+var_798]
0x18007b4ce  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18007b4d3  lea     rcx, [rbp+6D0h+hKey]; this
0x18007b4d7  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18007b4dc  cmp     eax, 103h
0x18007b4e1  jnz     loc_18007B3A1
0x18007b4e7  lea     r13, pszFormat
0x18007b4ee  lea     rcx, [rbp+6D0h+hKey]
0x18007b4f2  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007b4f7  nop
0x18007b4f8  lea     rcx, [rsp+7D0h+var_7A0]
0x18007b4fd  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007b502  lea     rcx, [rbp+6D0h+var_4B0]; this
0x18007b509  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18007b50e  cmp     eax, 103h
0x18007b513  jnz     loc_18007B280
0x18007b519  mov     r13, [rsp+7D0h+var_770]
0x18007b51e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007b522  lea     rax, [rbp+6D0h+var_730]
0x18007b526  mov     [rbp+6D0h+var_740], rax
0x18007b52a  lea     rax, [rbp+6D0h+var_730]
0x18007b52e  mov     [rbp+6D0h+var_738], rax
0x18007b532  mov     [rbp+6D0h+var_730], r15w
0x18007b537  mov     rdx, rbx; void *
0x18007b53a  lea     rcx, [rbp+6D0h+var_280]; this
0x18007b541  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x18007b546  nop
0x18007b547  mov     eax, [rbp+6D0h+var_25C]
0x18007b54d  mov     [rbp+6D0h+var_260], eax
0x18007b553  lea     rcx, [rbp+6D0h+var_280]; this
0x18007b55a  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18007b55f  cmp     eax, 103h
0x18007b564  jz      loc_18007B755
0x18007b56a  xorps   xmm0, xmm0
0x18007b56d  movups  [rbp+6D0h+var_700], xmm0
0x18007b571  mov     r15, [rbp+6D0h+var_270]
0x18007b578  mov     [rbp+6D0h+var_710], r15
0x18007b57c  mov     rbx, [rbp+6D0h+var_268]
0x18007b583  mov     [rbp+6D0h+var_708], rbx
0x18007b587  test    rbx, rbx
0x18007b58a  jz      loc_18007B706
0x18007b590  lea     rdx, [rbp+6D0h+var_710]
0x18007b594  lea     rcx, [rbp+6D0h+var_700]
0x18007b598  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007b59d  test    rax, rax
0x18007b5a0  jz      loc_18007B706
0x18007b5a6  lea     rdx, [rbp+6D0h+var_700]
0x18007b5aa  lea     rcx, [rsp+7D0h+var_770]
0x18007b5af  call    ?GetRegCacheProviderNodebyGuid@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@@Z; GetRegCacheProviderNodebyGuid(_GUID const *)
0x18007b5b4  nop
0x18007b5b5  mov     rbx, [rsp+7D0h+var_770]
0x18007b5ba  test    rbx, rbx
0x18007b5bd  jz      loc_18007B64E
0x18007b5c3  test    byte ptr [rbx+0C0h], 4
0x18007b5ca  jz      loc_18007B6FA
0x18007b5d0  mov     rdx, [rbx+20h]
0x18007b5d4  inc     rdx
0x18007b5d7  lea     rcx, [rsp+7D0h+var_7A0]
0x18007b5dc  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18007b5e1  nop
0x18007b5e2  mov     r15, [rsp+7D0h+var_7A0]
0x18007b5e7  test    r15, r15
0x18007b5ea  jz      loc_18007BA37
0x18007b5f0  mov     r8, [rbx+20h]
0x18007b5f4  add     r8, r8; Size
0x18007b5f7  mov     rdx, [rbx+18h]; Src
0x18007b5fb  mov     rcx, r15; void *
0x18007b5fe  call    memcpy_0
0x18007b603  mov     rcx, [rbx+20h]
0x18007b607  xor     eax, eax
0x18007b609  mov     [r15+rcx*2], ax
0x18007b60e  cmp     rdi, [rsp+7D0h+var_778]
0x18007b613  jz      short loc_18007B628
0x18007b615  mov     [rsp+7D0h+var_7A0], rax
0x18007b61a  mov     [rdi], r15
0x18007b61d  add     rdi, 8
0x18007b621  mov     [rsp+7D0h+var_780], rdi
0x18007b626  jmp     short loc_18007B644
0x18007b628  lea     rdx, [rsp+7D0h+var_7A0]
0x18007b62d  lea     rcx, [rsp+7D0h+var_790+8]
0x18007b632  call    ??$_PushBackOne2@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@AEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@@Z; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18007b637  test    al, al
0x18007b639  jz      loc_18007B9E4
0x18007b63f  mov     rdi, [rsp+7D0h+var_780]
0x18007b644  lea     rcx, [rsp+7D0h+var_7A0]
0x18007b649  jmp     loc_18007B6F4
0x18007b64e  lea     rdx, [rbp+6D0h+var_740]
0x18007b652  lea     rcx, [rbp+6D0h+var_280]
0x18007b659  call    ?GetCurrentPublisherName@PublisherConfigEnumerator@@QEAA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherConfigEnumerator::GetCurrentPublisherName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007b65e  test    al, al
0x18007b660  jz      loc_18007B6FA
0x18007b666  mov     rdx, [rbp+6D0h+var_738]
0x18007b66a  cmp     [rbp+6D0h+var_740], rdx
0x18007b66e  jz      loc_18007B6FA
0x18007b674  sub     rdx, [rbp+6D0h+var_740]
0x18007b678  sar     rdx, 1
0x18007b67b  inc     rdx
0x18007b67e  lea     rcx, [rsp+7D0h+var_798]
0x18007b683  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18007b688  nop
0x18007b689  mov     rbx, [rsp+7D0h+var_798]
0x18007b68e  test    rbx, rbx
0x18007b691  jz      loc_18007B896
0x18007b697  mov     r8, [rbp+6D0h+var_738]
0x18007b69b  mov     rdx, [rbp+6D0h+var_740]; Src
0x18007b69f  sub     r8, rdx
0x18007b6a2  sar     r8, 1
0x18007b6a5  lea     r8, ds:2[r8*2]; Size
0x18007b6ad  mov     rcx, rbx; void *
0x18007b6b0  call    memcpy_0
0x18007b6b5  cmp     rdi, [rsp+7D0h+var_778]
0x18007b6ba  jz      short loc_18007B6D3
0x18007b6bc  mov     [rsp+7D0h+var_798], 0
0x18007b6c5  mov     [rdi], rbx
0x18007b6c8  add     rdi, 8
  ... truncated ...
```
