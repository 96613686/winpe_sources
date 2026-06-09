# ManifestProcessor::ValidatePublisherAndChannelOwner(_GUID const &,StringSet const &)

- ea: `0x14000adf0`
- end: `0x14000b461`
- name: `?ValidatePublisherAndChannelOwner@ManifestProcessor@@AEAAXAEBU_GUID@@AEBVStringSet@@@Z`
- size: `1649`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, const struct _GUID *, const struct StringSet *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001663c`

## callees

- `0x140003b50`
- `0x140004cb0`
- `0x140004d40`
- `0x140006a30`
- `0x140007d00`
- `0x140008020`
- `0x140008b20`
- `0x14000adf0`
- `0x14000cc80`
- `0x14001b244`
- `0x14001c3ec`
- `0x140021b00`
- `0x140022cec`
- `0x14002c900`
- `0x14002f69c`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b1c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b1e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b1c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b1e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b1bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b1d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b1bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b1d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000afe3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000b0bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000b130`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000afe3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000b0bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000b130`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b269`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ManifestProcessor::ValidatePublisherAndChannelOwner(
        ManifestProcessor *this,
        const struct _GUID *a2,
        const struct StringSet *a3)
{
  const struct StringSet *v3; // r14
  ManifestProcessor *v4; // rsi
  char *v5; // rdi
  unsigned __int16 *v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r8
  unsigned int v11; // eax
  __m128i si128; // xmm6
  __m128i **CurrentReader; // rax
  __m128i *v14; // rbx
  __m128i *v15; // rdx
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned __int64 v19; // r15
  _BYTE *v20; // rcx
  _BYTE *v21; // rdi
  char *v22; // rsi
  __int64 *v23; // rdi
  __int64 *v24; // rbx
  __int64 v25; // r10
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rbx
  char *v37; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v39; // rax
  __int64 v40; // rax
  __int64 StrId; // rax
  unsigned int v42; // eax
  const char *v43; // r8
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 Name; // rax
  unsigned int v49; // eax
  const char *v50; // r8
  __m128i *v51; // [rsp+30h] [rbp-358h] BYREF
  ManifestProcessor *v52; // [rsp+38h] [rbp-350h]
  char *v53; // [rsp+40h] [rbp-348h]
  LPVOID lpMem[2]; // [rsp+48h] [rbp-340h] BYREF
  __int64 v55; // [rsp+58h] [rbp-330h]
  ManifestProcessor *v56; // [rsp+60h] [rbp-328h]
  char *v57; // [rsp+68h] [rbp-320h] BYREF
  _QWORD v58[2]; // [rsp+78h] [rbp-310h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+88h] [rbp-300h] BYREF
  _BYTE v60[40]; // [rsp+B0h] [rbp-2D8h] BYREF
  _BYTE v61[40]; // [rsp+D8h] [rbp-2B0h] BYREF
  HKEY hKey[4]; // [rsp+100h] [rbp-288h] BYREF
  int v63; // [rsp+120h] [rbp-268h]
  int v64; // [rsp+124h] [rbp-264h]

  v3 = a3;
  v4 = this;
  v52 = this;
  v56 = this;
  if ( !*(_BYTE *)tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get() )
    return;
  v5 = (char *)v4 + 48;
  v53 = (char *)v4 + 48;
  v6 = (unsigned __int16 *)*((_QWORD *)v4 + 6);
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  if ( !v7 || (unsigned __int64)(v7 + 1) > 0x100 )
  {
LABEL_69:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 15004);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x3A9Cu);
    throw (EvtException *)pExceptionObject;
  }
  v8 = &v6[v7];
  v9 = 0xD40004C4FFFFFFFFuLL;
  while ( v6 != v8 )
  {
    v10 = *v6;
    if ( (unsigned int)v10 <= 0x3F && _bittest64((const __int64 *)&v9, v10) || (_DWORD)v10 == 124 || (_DWORD)v10 == 92 )
      goto LABEL_69;
    ++v6;
  }
  v57 = (char *)v4 + 48;
  v51 = 0;
  PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)hKey, *((void **)v4 + 1));
  v63 = v64;
  v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  while ( v11 != 259 )
  {
    try
    {
      CurrentReader = (__m128i **)PublisherConfigEnumerator::GetCurrentReader(hKey, v58);
      v14 = *CurrentReader;
      *CurrentReader = 0;
      v15 = v51;
      v51 = v14;
      if ( v15 )
        utl::default_delete<PublisherConfigReader>::operator()();
      if ( v58[0] )
        utl::default_delete<PublisherConfigReader>::operator()();
    }
    catch ( EvtException )
    {
      goto LABEL_63;
    }
    if ( v14[1].m128i_i64[0] == *(_QWORD *)&a2->Data1 && _mm_srli_si128(v14[1], 8).m128i_u64[0] == *(_QWORD *)a2->Data4 )
    {
      if ( *((_BYTE *)v4 + 1) )
        goto LABEL_62;
      eventlog::ai::WarningMessage((eventlog::ai *)0x46, v14[2].m128i_i64[1]);
      v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
    }
    else
    {
      v16 = (const WCHAR *)v14[4].m128i_i64[1];
      v17 = (v14[5].m128i_i64[0] - (__int64)v16) >> 1;
      v18 = (__int64)(*((_QWORD *)v5 + 1) - *(_QWORD *)v5) >> 1;
      if ( v17 == v18 && CompareStringOrdinal(v16, v17, *(LPCWCH *)v5, v18, 1) == 2 )
      {
        v40 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(&v51);
        StrId = PublisherConfigReader::GetStrId(v40, v58);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(StrId);
        v42 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(v5);
        eventlog::ai::WarningMessage((eventlog::ai *)0x4C, v42);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 15010);
        }
        EvtException::EvtException((EvtException *)v60, 0x3AA2u, v43, 776);
        throw (EvtException *)v60;
      }
      if ( *((_QWORD *)v3 + 3) )
      {
        try
        {
          *(__m128i *)lpMem = si128;
          v55 = -1;
          PublisherConfigReader::GetAndValidateManifestedChannelReferences(
            (__int64)v14,
            (const struct std::nothrow_t **)lpMem);
        }
        catch ( EvtException )
        {
          utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(lpMem);
LABEL_63:
          v3 = a3;
          si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          v4 = v56;
          v52 = v56;
          v5 = v57;
          v53 = v57;
          v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
          continue;
        }
        v19 = 0;
        v20 = lpMem[1];
        v21 = lpMem[0];
        if ( 0xAAAAAAAAAAAAAAABuLL * (((char *)lpMem[1] - (char *)lpMem[0]) >> 4) )
        {
          do
          {
            v22 = &v21[48 * v19];
            if ( (v22[40] & 1) == 0 && *((const struct StringSet **)v3 + 2) != v3 )
            {
              v23 = (__int64 *)v3;
              v24 = *(__int64 **)v3;
              do
              {
                v25 = v24[3];
                v26 = (v24[4] - v25) >> 1;
                v27 = (__int64)(*((_QWORD *)v22 + 1) - *(_QWORD *)v22) >> 1;
                if ( (v26 | (unsigned __int64)v27) > 0x7FFFFFFF )
                  __int2c();
                v28 = 2;
                if ( *(_QWORD *)v22 )
                  v28 = *(_QWORD *)v22;
                v29 = 2;
                if ( v25 )
                  v29 = v24[3];
                if ( CompareStringOrdinal((LPCWCH)v29, v26, (LPCWCH)v28, v27, 1) == 1 )
                {
                  v30 = 2;
                }
                else
                {
                  v23 = v24;
                  v30 = 1;
                }
                v24 = (__int64 *)v24[v30];
              }
              while ( v24 != (__int64 *)&utl::_TreeSentinel );
              if ( v3 != (const struct StringSet *)v23 )
              {
                v31 = (__int64)(*((_QWORD *)v22 + 1) - *(_QWORD *)v22) >> 1;
                v32 = v23[3];
                v33 = (v23[4] - v32) >> 1;
                if ( (v33 | (unsigned __int64)v31) > 0x7FFFFFFF )
                  __int2c();
                v34 = 2;
                if ( v32 )
                  v34 = v23[3];
                v35 = 2;
                if ( *(_QWORD *)v22 )
                  v35 = *(_QWORD *)v22;
                if ( CompareStringOrdinal((LPCWCH)v35, v31, (LPCWCH)v34, v33, 1) != 1
                  && v3 != (const struct StringSet *)v23 )
                {
                  v44 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(&v51);
                  v45 = PublisherConfigReader::GetStrId(v44, v58);
                  v46 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(v45);
                  Name = PublisherConfigReader::GetName(v47, &v57, v47, v46);
                  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(Name);
                  v49 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(v22);
                  eventlog::ai::WarningMessage((eventlog::ai *)0x4D, v49);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      47,
                      &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
                      15010);
                  }
                  EvtException::EvtException((EvtException *)v61, 0x3AA2u, v50, 810);
                  throw (EvtException *)v61;
                }
              }
              v20 = lpMem[1];
              v21 = lpMem[0];
            }
            ++v19;
          }
          while ( v19 < 0xAAAAAAAAAAAAAAABuLL * ((v20 - v21) >> 4) );
          v4 = v52;
        }
        if ( v21 != (_BYTE *)-1LL )
        {
          lpMem[1] = v21;
          v36 = (v20 - v21) / 48;
          if ( v36 )
          {
            do
            {
              --v36;
              v37 = *(char **)&v21[48 * v36];
              if ( v37 != &v21[48 * v36 + 16] )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v37);
              }
            }
            while ( v36 );
            v21 = lpMem[0];
          }
          v39 = GetProcessHeap();
          HeapFree(v39, 0, v21);
          v4 = v52;
        }
        v5 = v53;
      }
LABEL_62:
      v11 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v51 )
    utl::default_delete<PublisherConfigReader>::operator()();
}

```

## disassembly

```asm
0x14000adf0  mov     [rsp+arg_10], r8
0x14000adf5  mov     [rsp+arg_8], rdx
0x14000adfa  push    rbx
0x14000adfb  push    rsi
0x14000adfc  push    rdi
0x14000adfd  push    r12
0x14000adff  push    r13
0x14000ae01  push    r14
0x14000ae03  push    r15
0x14000ae05  sub     rsp, 350h
0x14000ae0c  movaps  [rsp+388h+var_48], xmm6
0x14000ae14  mov     rax, cs:__security_cookie
0x14000ae1b  xor     rax, rsp
0x14000ae1e  mov     [rsp+388h+var_58], rax
0x14000ae26  mov     r14, r8
0x14000ae29  mov     rsi, rcx
0x14000ae2c  mov     [rsp+388h+var_350], rcx
0x14000ae31  mov     [rsp+388h+var_328], rcx
0x14000ae36  call    ?get@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAAAEAVPublishersKeyExists@@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get(void)
0x14000ae3b  cmp     byte ptr [rax], 0
0x14000ae3e  jz      loc_14000B27F
0x14000ae44  lea     rdi, [rsi+30h]
0x14000ae48  mov     [rsp+388h+var_348], rdi
0x14000ae4d  mov     rax, [rdi]
0x14000ae50  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000ae57  nop     word ptr [rax+rax+00000000h]
0x14000ae60  inc     rdx
0x14000ae63  cmp     word ptr [rax+rdx*2], 0
0x14000ae68  jnz     short loc_14000AE60
0x14000ae6a  test    rdx, rdx
0x14000ae6d  jz      loc_14000B2AA
0x14000ae73  lea     rcx, [rdx+1]
0x14000ae77  cmp     rcx, 100h
0x14000ae7e  ja      loc_14000B2AA
0x14000ae84  lea     rcx, [rax+rdx*2]
0x14000ae88  mov     r9, 0D40004C4FFFFFFFFh
0x14000ae92  cmp     rax, rcx
0x14000ae95  jz      short loc_14000AEC5
0x14000ae97  movzx   r8d, word ptr [rax]
0x14000ae9b  cmp     r8d, 3Fh ; '?'
0x14000ae9f  ja      short loc_14000AEAB
0x14000aea1  bt      r9, r8
0x14000aea5  jb      loc_14000B2AA
0x14000aeab  cmp     r8d, 7Ch ; '|'
0x14000aeaf  jz      loc_14000B2AA
0x14000aeb5  cmp     r8d, 5Ch ; '\'
0x14000aeb9  jz      loc_14000B2AA
0x14000aebf  add     rax, 2
0x14000aec3  jmp     short loc_14000AE92
0x14000aec5  mov     [rsp+388h+var_320], rdi
0x14000aeca  mov     [rsp+388h+var_358], 0
0x14000aed3  mov     rdx, [rsi+8]; void *
0x14000aed7  lea     rcx, [rsp+388h+hKey]; this
0x14000aedf  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x14000aee4  nop
0x14000aee5  mov     eax, [rsp+388h+var_264]
0x14000aeec  mov     [rsp+388h+var_268], eax
0x14000aef3  lea     rcx, [rsp+388h+hKey]; this
0x14000aefb  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14000af00  mov     r13, 0AAAAAAAAAAAAAAABh
0x14000af0a  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14000af11  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000af19  nop     dword ptr [rax+00000000h]
0x14000af20  cmp     eax, 103h
0x14000af25  jz      loc_14000B25C
0x14000af2b  lea     rdx, [rsp+388h+var_310]
0x14000af30  lea     rcx, [rsp+388h+hKey]
0x14000af38  call    ?GetCurrentReader@PublisherConfigEnumerator@@QEAA?AV?$unique_ptr@VPublisherConfigReader@@U?$default_delete@VPublisherConfigReader@@@utl@@@utl@@XZ; PublisherConfigEnumerator::GetCurrentReader(void)
0x14000af3d  mov     rbx, [rax]
0x14000af40  mov     qword ptr [rax], 0
0x14000af47  mov     rdx, [rsp+388h+var_358]
0x14000af4c  mov     [rsp+388h+var_358], rbx
0x14000af51  test    rdx, rdx
0x14000af54  jz      short loc_14000AF5B
0x14000af56  call    ??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z; utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)
0x14000af5b  mov     rdx, [rsp+388h+var_310]
0x14000af60  test    rdx, rdx
0x14000af63  jz      short loc_14000AF6B
0x14000af65  call    ??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z; utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)
0x14000af6a  nop
0x14000af6b  movups  xmm0, xmmword ptr [rbx+10h]
0x14000af6f  mov     rcx, [rsp+388h+arg_8]
0x14000af77  movq    rax, xmm0
0x14000af7c  cmp     rax, [rcx]
0x14000af7f  jnz     short loc_14000AFBB
0x14000af81  psrldq  xmm0, 8
0x14000af86  movq    rax, xmm0
0x14000af8b  cmp     rax, [rcx+8]
0x14000af8f  jnz     short loc_14000AFBB
0x14000af91  cmp     byte ptr [rsi+1], 0
0x14000af95  jnz     loc_14000B1F7
0x14000af9b  mov     rdx, [rbx+28h]; unsigned int
0x14000af9f  mov     ecx, 46h ; 'F'; this
0x14000afa4  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14000afa9  lea     rcx, [rsp+388h+hKey]; this
0x14000afb1  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14000afb6  jmp     loc_14000AF20
0x14000afbb  mov     rcx, [rbx+48h]; lpString1
0x14000afbf  mov     rdx, [rbx+50h]
0x14000afc3  sub     rdx, rcx
0x14000afc6  sar     rdx, 1; cchCount1
0x14000afc9  mov     r8, [rdi]; lpString2
0x14000afcc  mov     r9, [rdi+8]
0x14000afd0  sub     r9, r8
0x14000afd3  sar     r9, 1; cchCount2
0x14000afd6  cmp     rdx, r9
0x14000afd9  jnz     short loc_14000AFF2
0x14000afdb  mov     [rsp+388h+bIgnoreCase], 1; bIgnoreCase
0x14000afe3  call    cs:__imp_CompareStringOrdinal
0x14000afe9  cmp     eax, 2
0x14000afec  jz      loc_14000B30A
0x14000aff2  cmp     qword ptr [r14+18h], 0
0x14000aff7  jz      loc_14000B1F7
0x14000affd  movdqu  xmmword ptr [rsp+388h+lpMem], xmm6
0x14000b003  mov     [rsp+388h+var_330], 0FFFFFFFFFFFFFFFFh
0x14000b00c  lea     rdx, [rsp+388h+lpMem]
0x14000b011  mov     rcx, rbx
0x14000b014  call    ?GetAndValidateManifestedChannelReferences@PublisherConfigReader@@QEBA_NAEAV?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@@Z; PublisherConfigReader::GetAndValidateManifestedChannelReferences(utl::vector<ChannelReference,utl::allocator<ChannelReference>> &)
0x14000b019  nop
0x14000b01a  xor     r15d, r15d
0x14000b01d  mov     rcx, [rsp+388h+lpMem+8]
0x14000b022  mov     rax, rcx
0x14000b025  mov     rdi, [rsp+388h+lpMem]
0x14000b02a  sub     rax, rdi
0x14000b02d  sar     rax, 4
0x14000b031  imul    rax, r13
0x14000b035  test    rax, rax
0x14000b038  jz      loc_14000B16D
0x14000b03e  xchg    ax, ax
0x14000b040  lea     rsi, [r15+r15*2]
0x14000b044  shl     rsi, 4
0x14000b048  add     rsi, rdi
0x14000b04b  test    byte ptr [rsi+28h], 1
0x14000b04f  jnz     loc_14000B14E
0x14000b055  cmp     [r14+10h], r14
0x14000b059  jz      loc_14000B14E
0x14000b05f  mov     rdi, r14
0x14000b062  mov     rbx, [r14]
0x14000b065  nop     word ptr [rax+rax+00000000h]
0x14000b070  mov     r10, [rbx+18h]
0x14000b074  mov     rdx, [rbx+20h]
0x14000b078  sub     rdx, r10
0x14000b07b  sar     rdx, 1; cchCount1
0x14000b07e  mov     rcx, [rsi]
0x14000b081  mov     r9, [rsi+8]
0x14000b085  sub     r9, rcx
0x14000b088  sar     r9, 1; cchCount2
0x14000b08b  mov     rax, r9
0x14000b08e  or      rax, rdx
0x14000b091  cmp     rax, 7FFFFFFFh
0x14000b097  jbe     short loc_14000B09B
0x14000b099  int     2Ch; Windows NT - assertion failure
0x14000b09b  mov     r8d, 2
0x14000b0a1  test    rcx, rcx
0x14000b0a4  cmovnz  r8, rcx; lpString2
0x14000b0a8  mov     ecx, 2
0x14000b0ad  test    r10, r10
0x14000b0b0  cmovnz  rcx, r10; lpString1
0x14000b0b4  mov     [rsp+388h+bIgnoreCase], 1; bIgnoreCase
0x14000b0bc  call    cs:__imp_CompareStringOrdinal
0x14000b0c2  cmp     eax, 1
0x14000b0c5  jz      short loc_14000B0D1
0x14000b0c7  mov     rdi, rbx
0x14000b0ca  mov     eax, 8
0x14000b0cf  jmp     short loc_14000B0D6
0x14000b0d1  mov     eax, 10h
0x14000b0d6  mov     rbx, [rax+rbx]
0x14000b0da  cmp     rbx, r12
0x14000b0dd  jnz     short loc_14000B070
0x14000b0df  cmp     r14, rdi
0x14000b0e2  jz      short loc_14000B144
0x14000b0e4  mov     r10, [rsi]
0x14000b0e7  mov     rdx, [rsi+8]
0x14000b0eb  sub     rdx, r10
0x14000b0ee  sar     rdx, 1; cchCount1
0x14000b0f1  mov     rcx, [rdi+18h]
0x14000b0f5  mov     r9, [rdi+20h]
0x14000b0f9  sub     r9, rcx
0x14000b0fc  sar     r9, 1; cchCount2
0x14000b0ff  mov     rax, rdx
0x14000b102  or      rax, r9
0x14000b105  cmp     rax, 7FFFFFFFh
0x14000b10b  jbe     short loc_14000B10F
0x14000b10d  int     2Ch; Windows NT - assertion failure
0x14000b10f  mov     r8d, 2
0x14000b115  test    rcx, rcx
0x14000b118  cmovnz  r8, rcx; lpString2
0x14000b11c  mov     ecx, 2
0x14000b121  test    r10, r10
0x14000b124  cmovnz  rcx, r10; lpString1
0x14000b128  mov     [rsp+388h+bIgnoreCase], 1; bIgnoreCase
0x14000b130  call    cs:__imp_CompareStringOrdinal
0x14000b136  cmp     eax, 1
0x14000b139  jz      short loc_14000B144
0x14000b13b  cmp     r14, rdi
0x14000b13e  jnz     loc_14000B3A8
0x14000b144  mov     rcx, [rsp+388h+lpMem+8]
0x14000b149  mov     rdi, [rsp+388h+lpMem]
0x14000b14e  inc     r15
0x14000b151  mov     rax, rcx
0x14000b154  sub     rax, rdi
0x14000b157  sar     rax, 4
0x14000b15b  imul    rax, r13
0x14000b15f  cmp     r15, rax
0x14000b162  jb      loc_14000B040
0x14000b168  mov     rsi, [rsp+388h+var_350]
0x14000b16d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000b171  jz      short loc_14000B1F2
0x14000b173  mov     [rsp+388h+lpMem+8], rdi
0x14000b178  sub     rcx, rdi
0x14000b17b  mov     rax, 2AAAAAAAAAAAAAABh
0x14000b185  imul    rcx
0x14000b188  mov     rbx, rdx
0x14000b18b  sar     rbx, 3
0x14000b18f  mov     rax, rbx
0x14000b192  shr     rax, 3Fh
0x14000b196  add     rbx, rax
0x14000b199  jz      short loc_14000B1D9
0x14000b19b  nop     dword ptr [rax+rax+00h]
0x14000b1a0  dec     rbx
0x14000b1a3  lea     rax, [rbx+rbx*2]
0x14000b1a7  shl     rax, 4
0x14000b1ab  mov     rsi, [rax+rdi]
0x14000b1af  add     rax, 10h
0x14000b1b3  add     rax, rdi
0x14000b1b6  cmp     rsi, rax
0x14000b1b9  jz      short loc_14000B1CF
0x14000b1bb  call    cs:__imp_GetProcessHeap
0x14000b1c1  mov     rcx, rax; hHeap
0x14000b1c4  mov     r8, rsi; lpMem
0x14000b1c7  xor     edx, edx; dwFlags
0x14000b1c9  call    cs:__imp_HeapFree
0x14000b1cf  test    rbx, rbx
0x14000b1d2  jnz     short loc_14000B1A0
0x14000b1d4  mov     rdi, [rsp+388h+lpMem]
0x14000b1d9  call    cs:__imp_GetProcessHeap
0x14000b1df  mov     rcx, rax; hHeap
0x14000b1e2  mov     r8, rdi; lpMem
0x14000b1e5  xor     edx, edx; dwFlags
0x14000b1e7  call    cs:__imp_HeapFree
0x14000b1ed  mov     rsi, [rsp+388h+var_350]
0x14000b1f2  mov     rdi, [rsp+388h+var_348]
0x14000b1f7  lea     rcx, [rsp+388h+hKey]; this
0x14000b1ff  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14000b204  jmp     loc_14000AF20
0x14000b209  lea     rcx, [rsp+388h+lpMem]
0x14000b20e  call    ?_Uninit@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@AEAAXXZ; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(void)
0x14000b213  mov     r13, 0AAAAAAAAAAAAAAABh
0x14000b21d  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14000b224  mov     r14, [rsp+388h+arg_10]
0x14000b22c  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000b234  mov     rsi, [rsp+388h+var_328]
0x14000b239  mov     [rsp+388h+var_350], rsi
0x14000b23e  mov     rdi, [rsp+388h+var_320]
0x14000b243  mov     [rsp+388h+var_348], rdi
0x14000b248  lea     rcx, [rsp+388h+hKey]; this
0x14000b250  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14000b255  jmp     loc_14000AF20
0x14000b25a  jmp     short loc_14000B213
0x14000b25c  mov     rcx, [rsp+388h+hKey]; hKey
0x14000b264  test    rcx, rcx
0x14000b267  jz      short loc_14000B270
0x14000b269  call    cs:__imp_RegCloseKey
0x14000b26f  nop
0x14000b270  mov     rdx, [rsp+388h+var_358]
0x14000b275  test    rdx, rdx
0x14000b278  jz      short loc_14000B27F
0x14000b27a  call    ??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z; utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)
0x14000b27f  mov     rcx, [rsp+388h+var_58]
0x14000b287  xor     rcx, rsp; StackCookie
0x14000b28a  call    __security_check_cookie
0x14000b28f  movaps  xmm6, [rsp+388h+var_48]
0x14000b297  add     rsp, 350h
0x14000b29e  pop     r15
0x14000b2a0  pop     r14
0x14000b2a2  pop     r13
0x14000b2a4  pop     r12
0x14000b2a6  pop     rdi
0x14000b2a7  pop     rsi
0x14000b2a8  pop     rbx
0x14000b2a9  retn
0x14000b2aa  mov     ebx, 3A9Ch
0x14000b2af  lea     rax, WPP_GLOBAL_Control
0x14000b2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b2bd  cmp     rcx, rax
0x14000b2c0  jz      short loc_14000B2E6
0x14000b2c2  test    byte ptr [rcx+1Ch], 4
0x14000b2c6  jz      short loc_14000B2E6
0x14000b2c8  cmp     byte ptr [rcx+19h], 2
0x14000b2cc  jb      short loc_14000B2E6
0x14000b2ce  mov     edx, 2Dh ; '-'
0x14000b2d3  mov     r9d, ebx
0x14000b2d6  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14000b2dd  mov     rcx, [rcx+10h]
0x14000b2e1  call    WPP_SF_d
0x14000b2e6  mov     edx, ebx; unsigned int
0x14000b2e8  lea     rcx, [rsp+388h+pExceptionObject]; this
0x14000b2f0  call    ??0EvtException@@QEAA@K@Z; EvtException::EvtException(ulong)
0x14000b2f5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b2fc  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
  ... truncated ...
```
