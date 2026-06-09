# ManifestProcessor::RetractProviderNode(AbstractDomElement &,StringSet const &)

- ea: `0x14000a6a0`
- end: `0x14000ade4`
- name: `?RetractProviderNode@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEBVStringSet@@@Z`
- size: `1860`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, struct AbstractDomElement *, const struct StringSet *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001bf0`
- `0x14001663c`

## callees

- `0x140003700`
- `0x140004d40`
- `0x140006a30`
- `0x140007d00`
- `0x140008020`
- `0x14000a6a0`
- `0x14000cc80`
- `0x140019a68`
- `0x14001b244`
- `0x14001d828`
- `0x14001e0c0`
- `0x140021b00`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`
- `0x14003181c`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000a8e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000a8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ManifestProcessor::RetractProviderNode(
        ManifestProcessor *this,
        struct AbstractDomElement *a2,
        const struct StringSet *a3)
{
  struct AbstractDomElement *v3; // rdi
  HKEY v4; // r13
  unsigned int v5; // edx
  __int64 v6; // r14
  const char *v7; // r8
  volatile signed __int32 **v8; // rbx
  volatile signed __int32 *v9; // rcx
  volatile signed __int32 *v10; // rcx
  LPCWCH *v11; // r14
  __int64 v12; // rax
  const char *v13; // r8
  __int64 v14; // r12
  unsigned int v15; // eax
  __int64 *CurrentReader; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdx
  int v20; // eax
  const WCHAR *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rdi
  struct StringSet *v26; // r12
  volatile signed __int32 **v27; // rbx
  ManifestProcessor *v28; // rcx
  __int64 v29; // rbx
  struct StringSet *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  char v34; // r8
  __int128 *p_Buf2; // rdx
  __int64 v36; // rcx
  wchar_t v37; // ax
  __int64 v38; // rax
  __int64 v39; // rcx
  volatile signed __int32 *v40; // rcx
  HKEY v41; // rcx
  volatile signed __int32 *v42; // rcx
  const char *v43; // r8
  const char *v44; // r8
  LPCWCH *v45; // [rsp+30h] [rbp-388h]
  struct StringSet *v46; // [rsp+38h] [rbp-380h] BYREF
  volatile signed __int32 *v47; // [rsp+40h] [rbp-378h] BYREF
  volatile signed __int32 *v48; // [rsp+48h] [rbp-370h] BYREF
  __int64 v49; // [rsp+50h] [rbp-368h] BYREF
  ManifestProcessor *v50; // [rsp+58h] [rbp-360h] BYREF
  __int64 v51; // [rsp+60h] [rbp-358h]
  struct StringSet *v52; // [rsp+68h] [rbp-350h]
  _QWORD v53[2]; // [rsp+70h] [rbp-348h] BYREF
  struct _GUID Buf1; // [rsp+80h] [rbp-338h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+90h] [rbp-328h] BYREF
  _BYTE v56[40]; // [rsp+B8h] [rbp-300h] BYREF
  _BYTE v57[40]; // [rsp+E0h] [rbp-2D8h] BYREF
  _BYTE v58[40]; // [rsp+108h] [rbp-2B0h] BYREF
  __int128 Buf2; // [rsp+130h] [rbp-288h] BYREF
  HKEY hKey[4]; // [rsp+140h] [rbp-278h] BYREF
  int v61; // [rsp+160h] [rbp-258h]
  int v62; // [rsp+164h] [rbp-254h]

  v46 = a3;
  v3 = a2;
  v4 = (HKEY)this;
  v50 = this;
  v53[0] = a2;
  v52 = a3;
  if ( *(_BYTE *)tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get() )
  {
    (*(void (__fastcall **)(struct AbstractDomElement *, volatile signed __int32 **, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
      v3,
      &v48,
      L"guid");
    if ( !v48 )
    {
      eventlog::ai::WarningMessage((eventlog::ai *)0x4F, v5);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v43, 1400);
      throw (EvtException *)pExceptionObject;
    }
    Buf2 = 0;
    v6 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 16LL))(v48);
    v47 = (volatile signed __int32 *)v6;
    if ( !tlx::string_to_guid<wchar_t const *>(&Buf2, &v47) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)v56, 0xDu, v7, 1407);
      throw (EvtException *)v56;
    }
    v8 = (volatile signed __int32 **)(*(__int64 (__fastcall **)(struct AbstractDomElement *, volatile signed __int32 **, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
                                       v3,
                                       &v47,
                                       L"name");
    v9 = v48;
    if ( v48 && _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 && v9 )
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    v48 = 0;
    v48 = *v8;
    *v8 = 0;
    v10 = v47;
    if ( v47 && _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 && v10 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v10)(v10, 1);
    if ( !v48 )
    {
      eventlog::ai::WarningMessage((eventlog::ai *)0x47, v6);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)v57, 0xDu, v44, 1414);
      throw (EvtException *)v57;
    }
    v11 = (LPCWCH *)(v4 + 12);
    v12 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 16LL))(v48);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v4 + 12,
                             v12) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)v58, 0xEu, v13, 1419);
      throw (EvtException *)v58;
    }
    v45 = (LPCWCH *)(v4 + 12);
    v14 = 0;
    v51 = 0;
    PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)hKey, *((void **)v4 + 1));
    v61 = v62;
    while ( 1 )
    {
      v15 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
      if ( v15 == 259 )
        break;
      try
      {
        CurrentReader = (__int64 *)PublisherConfigEnumerator::GetCurrentReader(hKey, &v47);
        v18 = *CurrentReader;
        *CurrentReader = 0;
        v19 = v14;
        v14 = v18;
        v51 = v18;
        if ( v19 )
          utl::default_delete<PublisherConfigReader>::operator()(v17, v19);
        if ( v47 )
          utl::default_delete<PublisherConfigReader>::operator()(v17, v47);
        Buf1 = *(struct _GUID *)(v18 + 16);
        v20 = memcmp_0(&Buf1, &Buf2, 0x10u);
      }
      catch ( EvtException )
      {
        v14 = v51;
        v4 = (HKEY)v50;
        v3 = (struct AbstractDomElement *)v53[0];
        v46 = v52;
        v11 = v45;
        continue;
      }
      if ( v20 )
      {
        v21 = *(const WCHAR **)(v18 + 72);
        v22 = (__int64)(*(_QWORD *)(v18 + 80) - (_QWORD)v21) >> 1;
        v23 = (__int64)(*((_QWORD *)v4 + 7) - (_QWORD)*v11) >> 1;
        if ( v22 != v23 || CompareStringOrdinal(v21, v22, *v11, v23, 1) != 2 )
          continue;
      }
      Buf1 = *(struct _GUID *)(v18 + 16);
      ManifestProcessor::RetractProvider((ManifestProcessor *)v4, &Buf1, v46);
    }
    (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *, const wchar_t *))(*(_QWORD *)v3 + 32LL))(
      v3,
      &v49,
      L"channels");
    v24 = v49;
    if ( v49 )
    {
      (*(void (__fastcall **)(__int64, volatile signed __int32 **))(*(_QWORD *)v49 + 24LL))(v49, &v47);
      v25 = 0;
      v52 = 0;
      v26 = v46;
      while ( 1 )
      {
        v27 = (volatile signed __int32 **)(*(__int64 (__fastcall **)(volatile signed __int32 *, ManifestProcessor **))(*(_QWORD *)v47 + 8LL))(
                                            v47,
                                            &v50);
        if ( v25 && _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        v25 = *v27;
        v52 = (struct StringSet *)*v27;
        *v27 = 0;
        v28 = v50;
        if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)v50 + 2, 0xFFFFFFFF) == 1 && v28 )
          (**(void (__fastcall ***)(ManifestProcessor *, __int64))v28)(v28, 1);
        v50 = 0;
        if ( !v25 )
          break;
        v29 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 16LL))(v25);
        (*(void (__fastcall **)(volatile signed __int32 *, struct StringSet **, const wchar_t *))(*(_QWORD *)v25 + 40LL))(
          v25,
          &v46,
          L"name");
        v30 = v46;
        if ( v46 )
        {
          v31 = 0;
          while ( String1[v31] == *(_WORD *)(v29 + 2 * v31) && String1[v31 + 1] == *(_WORD *)(v29 + 2 * v31 + 2) )
          {
            v31 += 2;
            if ( v31 == 14 )
            {
              v32 = (*(__int64 (__fastcall **)(struct StringSet *))(*(_QWORD *)v46 + 16LL))(v46);
              v33 = -1;
              do
                ++v33;
              while ( *(_WORD *)(v32 + 2 * v33) );
              *(_QWORD *)&Buf2 = v32;
              *((_QWORD *)&Buf2 + 1) = v33;
              v34 = 1;
              p_Buf2 = &Buf2;
LABEL_51:
              ManifestProcessor::RetractChannel(v4, p_Buf2, v34, (__int64)v26);
              v30 = v46;
              goto LABEL_52;
            }
          }
          v36 = 0;
          while ( 1 )
          {
            v37 = aChannel[v36++];
            if ( v37 != *(_WORD *)(v29 + 2 * v36 - 2) )
              break;
            if ( v36 == 8 )
            {
              v38 = (*(__int64 (__fastcall **)(struct StringSet *))(*(_QWORD *)v46 + 16LL))(v46);
              v39 = -1;
              do
                ++v39;
              while ( *(_WORD *)(v38 + 2 * v39) );
              v53[0] = v38;
              v53[1] = v39;
              v34 = 0;
              p_Buf2 = (__int128 *)v53;
              goto LABEL_51;
            }
          }
LABEL_52:
          if ( v30 && _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 2, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(struct StringSet *, __int64))v30)(v30, 1);
          v46 = 0;
        }
        else
        {
          v46 = 0;
        }
      }
      v40 = v47;
      v14 = v51;
      if ( v47 && _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 && v40 )
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v40)(v40, 1);
      v24 = v49;
    }
    if ( v24 && _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v24)(v24, 1);
    v49 = 0;
    v41 = hKey[0];
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( v14 )
      utl::default_delete<PublisherConfigReader>::operator()(v41, v14);
    v42 = v48;
    if ( v48 && _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 && v42 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v42)(v42, 1);
  }
}

```

## disassembly

```asm
0x14000a6a0  push    rbx
0x14000a6a2  push    rsi
0x14000a6a3  push    rdi
0x14000a6a4  push    r12
0x14000a6a6  push    r13
0x14000a6a8  push    r14
0x14000a6aa  push    r15
0x14000a6ac  sub     rsp, 380h
0x14000a6b3  mov     rax, cs:__security_cookie
0x14000a6ba  xor     rax, rsp
0x14000a6bd  mov     [rsp+3B8h+var_48], rax
0x14000a6c5  mov     rax, r8
0x14000a6c8  mov     [rsp+3B8h+var_380], rax
0x14000a6cd  mov     rdi, rdx
0x14000a6d0  mov     r13, rcx
0x14000a6d3  mov     [rsp+3B8h+var_360], rcx
0x14000a6d8  mov     [rsp+3B8h+var_348], rdx
0x14000a6dd  mov     [rsp+3B8h+var_350], rax
0x14000a6e2  call    ?get@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAAAEAVPublishersKeyExists@@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get(void)
0x14000a6e7  cmp     byte ptr [rax], 0
0x14000a6ea  jz      loc_14000AC0E
0x14000a6f0  mov     rax, [rdi]
0x14000a6f3  lea     r8, aGuid_0; "guid"
0x14000a6fa  lea     rdx, [rsp+3B8h+var_370]
0x14000a6ff  mov     rcx, rdi
0x14000a702  mov     rax, [rax+28h]
0x14000a706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a70b  nop
0x14000a70c  mov     rcx, [rsp+3B8h+var_370]
0x14000a711  test    rcx, rcx
0x14000a714  jz      loc_14000AC31
0x14000a71a  xorps   xmm0, xmm0
0x14000a71d  movups  [rsp+3B8h+Buf2], xmm0
0x14000a725  mov     rax, [rcx]
0x14000a728  mov     rax, [rax+10h]
0x14000a72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a731  mov     r14, rax
0x14000a734  mov     [rsp+3B8h+var_378], rax
0x14000a739  lea     rdx, [rsp+3B8h+var_378]
0x14000a73e  lea     rcx, [rsp+3B8h+Buf2]
0x14000a746  call    ??$string_to_guid@PEB_W@tlx@@YAPEB_WPEAU_GUID@@AEBQEB_W@Z; tlx::string_to_guid<wchar_t const *>(_GUID *,wchar_t const * const &)
0x14000a74b  test    rax, rax
0x14000a74e  jz      loc_14000ACA2
0x14000a754  mov     rax, [rdi]
0x14000a757  lea     r8, aName_0; "name"
0x14000a75e  lea     rdx, [rsp+3B8h+var_378]
0x14000a763  mov     rcx, rdi
0x14000a766  mov     rax, [rax+28h]
0x14000a76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a76f  mov     rbx, rax
0x14000a772  mov     rcx, [rsp+3B8h+var_370]
0x14000a777  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14000a77e  test    rcx, rcx
0x14000a781  jz      short loc_14000A7A0
0x14000a783  mov     edx, r15d
0x14000a786  lock xadd [rcx+8], edx
0x14000a78b  cmp     edx, 1
0x14000a78e  jnz     short loc_14000A7A0
0x14000a790  test    rcx, rcx
0x14000a793  jz      short loc_14000A7A0
0x14000a795  mov     rax, [rcx]
0x14000a798  mov     rax, [rax]
0x14000a79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7a0  xor     esi, esi
0x14000a7a2  mov     [rsp+3B8h+var_370], rsi
0x14000a7a7  mov     rax, [rbx]
0x14000a7aa  mov     [rsp+3B8h+var_370], rax
0x14000a7af  mov     [rbx], rsi
0x14000a7b2  mov     rcx, [rsp+3B8h+var_378]
0x14000a7b7  test    rcx, rcx
0x14000a7ba  jz      short loc_14000A7DE
0x14000a7bc  mov     eax, r15d
0x14000a7bf  lock xadd [rcx+8], eax
0x14000a7c4  cmp     eax, 1
0x14000a7c7  jnz     short loc_14000A7DE
0x14000a7c9  test    rcx, rcx
0x14000a7cc  jz      short loc_14000A7DE
0x14000a7ce  mov     rax, [rcx]
0x14000a7d1  mov     edx, 1
0x14000a7d6  mov     rax, [rax]
0x14000a7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7de  mov     rcx, [rsp+3B8h+var_370]
0x14000a7e3  test    rcx, rcx
0x14000a7e6  jz      loc_14000AD09
0x14000a7ec  lea     r14, [r13+30h]
0x14000a7f0  mov     rax, [rcx]
0x14000a7f3  mov     rax, [rax+10h]
0x14000a7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7fc  mov     rdx, rax
0x14000a7ff  mov     rcx, r14
0x14000a802  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x14000a807  test    al, al
0x14000a809  jz      loc_14000AD7D
0x14000a80f  mov     [rsp+3B8h+var_388], r14
0x14000a814  mov     r12, rsi
0x14000a817  mov     [rsp+3B8h+var_358], rsi
0x14000a81c  mov     rdx, [r13+8]; void *
0x14000a820  lea     rcx, [rsp+3B8h+hKey]; this
0x14000a828  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x14000a82d  nop
0x14000a82e  mov     eax, [rsp+3B8h+var_254]
0x14000a835  mov     [rsp+3B8h+var_258], eax
0x14000a83c  lea     rcx, [rsp+3B8h+hKey]; this
0x14000a844  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14000a849  cmp     eax, 103h
0x14000a84e  jz      loc_14000A949
0x14000a854  lea     rdx, [rsp+3B8h+var_378]
0x14000a859  lea     rcx, [rsp+3B8h+hKey]
0x14000a861  call    ?GetCurrentReader@PublisherConfigEnumerator@@QEAA?AV?$unique_ptr@VPublisherConfigReader@@U?$default_delete@VPublisherConfigReader@@@utl@@@utl@@XZ; PublisherConfigEnumerator::GetCurrentReader(void)
0x14000a866  mov     rbx, [rax]
0x14000a869  mov     [rax], rsi
0x14000a86c  mov     rdx, r12
0x14000a86f  mov     r12, rbx
0x14000a872  mov     [rsp+3B8h+var_358], rbx
0x14000a877  test    rdx, rdx
0x14000a87a  jz      short loc_14000A881
0x14000a87c  call    ??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z; utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)
0x14000a881  mov     rdx, [rsp+3B8h+var_378]
0x14000a886  test    rdx, rdx
0x14000a889  jz      short loc_14000A891
0x14000a88b  call    ??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z; utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)
0x14000a890  nop
0x14000a891  movups  xmm0, xmmword ptr [rbx+10h]
0x14000a895  movups  [rsp+3B8h+Buf1], xmm0
0x14000a89d  mov     r8d, 10h; Size
0x14000a8a3  lea     rdx, [rsp+3B8h+Buf2]; Buf2
0x14000a8ab  lea     rcx, [rsp+3B8h+Buf1]; Buf1
0x14000a8b3  call    memcmp_0
0x14000a8b8  test    eax, eax
0x14000a8ba  jz      short loc_14000A8F7
0x14000a8bc  mov     rcx, [rbx+48h]; lpString1
0x14000a8c0  mov     rdx, [rbx+50h]
0x14000a8c4  sub     rdx, rcx
0x14000a8c7  sar     rdx, 1; cchCount1
0x14000a8ca  mov     r8, [r14]; lpString2
0x14000a8cd  mov     r9, [r13+38h]
0x14000a8d1  sub     r9, r8
0x14000a8d4  sar     r9, 1; cchCount2
0x14000a8d7  cmp     rdx, r9
0x14000a8da  jnz     loc_14000A83C
0x14000a8e0  mov     [rsp+3B8h+bIgnoreCase], 1; bIgnoreCase
0x14000a8e8  call    cs:__imp_CompareStringOrdinal
0x14000a8ee  cmp     eax, 2
0x14000a8f1  jnz     loc_14000A83C
0x14000a8f7  movups  xmm0, xmmword ptr [rbx+10h]
0x14000a8fb  movaps  [rsp+3B8h+Buf1], xmm0
0x14000a903  mov     r8, [rsp+3B8h+var_380]; struct StringSet *
0x14000a908  lea     rdx, [rsp+3B8h+Buf1]; struct _GUID
0x14000a910  mov     rcx, r13; this
0x14000a913  call    ?RetractProvider@ManifestProcessor@@AEAAXU_GUID@@AEBVStringSet@@@Z; ManifestProcessor::RetractProvider(_GUID,StringSet const &)
0x14000a918  jmp     loc_14000A83C
0x14000a91d  xor     esi, esi
0x14000a91f  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14000a926  mov     r12, [rsp+3B8h+var_358]
0x14000a92b  mov     r13, [rsp+3B8h+var_360]
0x14000a930  mov     rdi, [rsp+3B8h+var_348]
0x14000a935  mov     rax, [rsp+3B8h+var_350]
0x14000a93a  mov     [rsp+3B8h+var_380], rax
0x14000a93f  mov     r14, [rsp+3B8h+var_388]
0x14000a944  jmp     loc_14000A83C
0x14000a949  mov     rax, [rdi]
0x14000a94c  lea     r8, aChannels_2; "channels"
0x14000a953  lea     rdx, [rsp+3B8h+var_368]
0x14000a958  mov     rcx, rdi
0x14000a95b  mov     rax, [rax+20h]
0x14000a95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a964  nop
0x14000a965  mov     rcx, [rsp+3B8h+var_368]
0x14000a96a  test    rcx, rcx
0x14000a96d  jz      loc_14000AB97
0x14000a973  mov     rax, [rcx]
0x14000a976  lea     rdx, [rsp+3B8h+var_378]
0x14000a97b  mov     rax, [rax+18h]
0x14000a97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a984  nop
0x14000a985  mov     rdi, rsi
0x14000a988  mov     [rsp+3B8h+var_350], rsi
0x14000a98d  lea     r14, aImportchannel; "importChannel"
0x14000a994  mov     r12, [rsp+3B8h+var_380]
0x14000a999  nop     dword ptr [rax+00000000h]
0x14000a9a0  mov     rcx, [rsp+3B8h+var_378]
0x14000a9a5  mov     rax, [rcx]
0x14000a9a8  lea     rdx, [rsp+3B8h+var_360]
0x14000a9ad  mov     rax, [rax+8]
0x14000a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9b6  mov     rbx, rax
0x14000a9b9  test    rdi, rdi
0x14000a9bc  jz      short loc_14000A9DE
0x14000a9be  mov     edx, r15d
0x14000a9c1  lock xadd [rdi+8], edx
0x14000a9c6  cmp     edx, 1
0x14000a9c9  jnz     short loc_14000A9DE
0x14000a9cb  test    rdi, rdi
0x14000a9ce  jz      short loc_14000A9DE
0x14000a9d0  mov     rax, [rdi]
0x14000a9d3  mov     rcx, rdi
0x14000a9d6  mov     rax, [rax]
0x14000a9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9de  mov     rdi, [rbx]
0x14000a9e1  mov     [rsp+3B8h+var_350], rdi
0x14000a9e6  mov     [rbx], rsi
0x14000a9e9  mov     rcx, [rsp+3B8h+var_360]
0x14000a9ee  test    rcx, rcx
0x14000a9f1  jz      short loc_14000AA15
0x14000a9f3  mov     eax, r15d
0x14000a9f6  lock xadd [rcx+8], eax
0x14000a9fb  cmp     eax, 1
0x14000a9fe  jnz     short loc_14000AA15
0x14000aa00  test    rcx, rcx
0x14000aa03  jz      short loc_14000AA15
0x14000aa05  mov     rax, [rcx]
0x14000aa08  mov     edx, 1
0x14000aa0d  mov     rax, [rax]
0x14000aa10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa15  mov     [rsp+3B8h+var_360], rsi
0x14000aa1a  test    rdi, rdi
0x14000aa1d  jz      loc_14000AB61
0x14000aa23  mov     rax, [rdi]
0x14000aa26  mov     rcx, rdi
0x14000aa29  mov     rax, [rax+10h]
0x14000aa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa32  mov     rbx, rax
0x14000aa35  mov     rcx, [rdi]
0x14000aa38  mov     rax, [rcx+28h]
0x14000aa3c  lea     r8, aName_0; "name"
0x14000aa43  lea     rdx, [rsp+3B8h+var_380]
0x14000aa48  mov     rcx, rdi
0x14000aa4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa50  nop
0x14000aa51  mov     r8, [rsp+3B8h+var_380]
0x14000aa56  test    r8, r8
0x14000aa59  jnz     short loc_14000AA65
0x14000aa5b  mov     [rsp+3B8h+var_380], rsi
0x14000aa60  jmp     loc_14000A9A0
0x14000aa65  mov     rcx, rsi
0x14000aa68  nop     dword ptr [rax+rax+00000000h]
0x14000aa70  movzx   eax, word ptr [r14+rcx*2]
0x14000aa75  cmp     ax, [rbx+rcx*2]
0x14000aa79  jnz     short loc_14000AACB
0x14000aa7b  movzx   eax, word ptr [r14+rcx*2+2]
0x14000aa81  cmp     ax, [rbx+rcx*2+2]
0x14000aa86  jnz     short loc_14000AACB
0x14000aa88  add     rcx, 2
0x14000aa8c  cmp     rcx, 0Eh
0x14000aa90  jnz     short loc_14000AA70
0x14000aa92  mov     rax, [r8]
0x14000aa95  mov     rcx, r8
0x14000aa98  mov     rax, [rax+10h]
0x14000aa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaa1  mov     rcx, r15
0x14000aaa4  inc     rcx
0x14000aaa7  cmp     word ptr [rax+rcx*2], 0
0x14000aaac  jnz     short loc_14000AAA4
0x14000aaae  mov     qword ptr [rsp+3B8h+Buf2], rax
0x14000aab6  mov     qword ptr [rsp+3B8h+Buf2+8], rcx
0x14000aabe  mov     r8b, 1
0x14000aac1  lea     rdx, [rsp+3B8h+Buf2]
0x14000aac9  jmp     short loc_14000AB1C
0x14000aacb  mov     rcx, rsi
0x14000aace  xchg    ax, ax
0x14000aad0  lea     rax, aChannel; "channel"
0x14000aad7  movzx   eax, word ptr [rax+rcx*2]
0x14000aadb  inc     rcx
0x14000aade  cmp     ax, [rbx+rcx*2-2]
0x14000aae3  jnz     short loc_14000AB2C
0x14000aae5  cmp     rcx, 8
0x14000aae9  jnz     short loc_14000AAD0
0x14000aaeb  mov     rax, [r8]
0x14000aaee  mov     rcx, r8
0x14000aaf1  mov     rax, [rax+10h]
0x14000aaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aafa  mov     rcx, r15
0x14000aafd  nop     dword ptr [rax]
0x14000ab00  inc     rcx
0x14000ab03  cmp     word ptr [rax+rcx*2], 0
0x14000ab08  jnz     short loc_14000AB00
0x14000ab0a  mov     [rsp+3B8h+var_348], rax
0x14000ab0f  mov     [rsp+3B8h+var_340], rcx
0x14000ab14  xor     r8d, r8d
0x14000ab17  lea     rdx, [rsp+3B8h+var_348]
0x14000ab1c  mov     r9, r12
0x14000ab1f  mov     rcx, r13
0x14000ab22  call    ?RetractChannel@ManifestProcessor@@AEAAXV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_NAEBVStringSet@@@Z; ManifestProcessor::RetractChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,StringSet const &)
0x14000ab27  mov     r8, [rsp+3B8h+var_380]
0x14000ab2c  test    r8, r8
0x14000ab2f  jz      short loc_14000AB57
0x14000ab31  mov     eax, r15d
0x14000ab34  lock xadd [r8+8], eax
0x14000ab3a  cmp     eax, 1
0x14000ab3d  jnz     short loc_14000AB57
0x14000ab3f  test    r8, r8
0x14000ab42  jz      short loc_14000AB57
0x14000ab44  mov     rax, [r8]
0x14000ab47  mov     edx, 1
0x14000ab4c  mov     rcx, r8
0x14000ab4f  mov     rax, [rax]
0x14000ab52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab57  mov     [rsp+3B8h+var_380], rsi
0x14000ab5c  jmp     loc_14000A9A0
0x14000ab61  mov     rcx, [rsp+3B8h+var_378]
  ... truncated ...
```
