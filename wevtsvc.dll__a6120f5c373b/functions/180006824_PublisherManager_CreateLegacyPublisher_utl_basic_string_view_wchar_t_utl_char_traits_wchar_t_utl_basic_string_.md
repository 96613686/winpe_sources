# PublisherManager::CreateLegacyPublisher(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x180006824`
- end: `0x180006e4a`
- name: `?CreateLegacyPublisher@PublisherManager@@QEAA?AV?$AutoRef@VPublisher@@@wmi@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@00@Z`
- size: `1574`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180006fcc`
- `0x18003b87c`
- `0x18005e4e4`

## callees

- `0x180006824`
- `0x180014bd0`
- `0x180016250`
- `0x18001722c`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x18002afa8`
- `0x18002c6f4`
- `0x18002d6dc`
- `0x18003b0e8`
- `0x18003ce74`
- `0x18003d170`
- `0x180063d50`
- `0x18006de84`
- `0x18007aa1c`
- `0x180083f2c`
- `0x180090d74`
- `0x180092008`
- `0x18009aee0`
- `0x18009e770`
- `0x1800a016c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ce3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006989`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006b04`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006b04`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall PublisherManager::CreateLegacyPublisher(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  __int64 v6; // rcx
  unsigned int EventlogServiceRegPath; // eax
  unsigned int v8; // esi
  PVOID *v9; // rcx
  char v10; // r12
  int PublisherConfigReader; // eax
  unsigned int v12; // edx
  int v13; // r8d
  HKEY v14; // rsi
  __int64 v15; // r15
  __int64 v16; // rsi
  _WORD *v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  bool v26; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h]
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v31; // [rsp+70h] [rbp-90h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  int v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ch] [rbp-64h]
  _QWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v39[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v41; // [rsp+D0h] [rbp-30h] BYREF
  void *v42[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v43; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v44; // [rsp+110h] [rbp+10h] BYREF
  __int128 v45; // [rsp+120h] [rbp+20h] BYREF
  void *v46[2]; // [rsp+130h] [rbp+30h] BYREF
  char v47; // [rsp+140h] [rbp+40h] BYREF
  void *v48[2]; // [rsp+150h] [rbp+50h] BYREF
  char v49; // [rsp+160h] [rbp+60h] BYREF
  __int128 v50; // [rsp+170h] [rbp+70h] BYREF

  v38[0] = a4;
  v39[0] = a3;
  v31 = a1;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v6, &hKey, lpSubKey);
  v8 = EventlogServiceRegPath;
  if ( EventlogServiceRegPath )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_80;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_c10225a1bfc8322526427285fd9158a0_Traceguids,
        EventlogServiceRegPath);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_76:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(v9[2], 14, &WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids, v8);
LABEL_80:
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v33 = 0;
    v34 = v8;
    v35 = -1;
    v36 = -1;
    v37 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           lpSubKey,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c10225a1bfc8322526427285fd9158a0_Traceguids, 14);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 14;
    goto LABEL_76;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           lpSubKey,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids, 14);
    }
    pExceptionObject = 0;
    v33 = 0;
    v34 = 14;
    v35 = -1;
    v36 = 166;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v48);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
  phkResult = 0;
  RegOpenKeyExW(hKey, lpSubKey[0], 0, 1u, &phkResult);
  v10 = 0;
  if ( phkResult && !(unsigned int)RegReadStringValueNoThrow(phkResult) )
  {
    v50 = 0;
    if ( tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(&v50, v42) )
    {
      hKey = 0;
      PublisherConfigReader = PublisherConfigReader::TryGetPublisherConfigReader(&hKey, &v50);
      v14 = hKey;
      if ( !PublisherConfigReader )
      {
        v26 = 0;
        if ( !PublisherConfigReader::GetEnabled((PublisherConfigReader *)hKey, &v26) || v26 )
        {
          hKey = (HKEY)*((_QWORD *)v14 + 9);
          v28 = (__int64)(*((_QWORD *)v14 + 10) - (_QWORD)hKey) >> 1;
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v48) )
          {
            if ( (unsigned __int8)PublisherConfigReader::GetResourceFilePathUnexpanded(v14, v46) )
            {
              v10 = 1;
LABEL_26:
              if ( v14 )
                PublisherConfigReader::`scalar deleting destructor'((PublisherConfigReader *)v14, v12);
              goto LABEL_32;
            }
            LOBYTE(PublisherConfigReader) = -102;
          }
          else
          {
            LOBYTE(PublisherConfigReader) = 14;
          }
        }
        else
        {
          LOBYTE(PublisherConfigReader) = -67;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, lpSubKey[0], (__int64)v42[0], PublisherConfigReader);
      }
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids,
        lpSubKey[0],
        (__int64)v42[0]);
    }
  }
LABEL_32:
  v15 = *a5;
  v16 = a5[1];
  ClientLocalFlag = 0;
  if ( !I_RpcBindingIsClientLocal(0, &ClientLocalFlag) && ClientLocalFlag && (g_compatFlags & 2) == 0 )
  {
    v15 = v31[11];
    v16 = (v31[12] - v15) >> 1;
  }
  if ( v10 )
  {
    v17 = v42[0];
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v42[0] + v19) );
    if ( v19 == 38 )
    {
      *((_WORD *)v42[0] + 37) = 0;
      ++v17;
    }
    v20 = operator new(0xA8u);
    v31 = v20;
    if ( v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v17[v21] );
      do
        ++v18;
      while ( *((_WORD *)v48[0] + v18) );
      v44 = *(_OWORD *)v38[0];
      v45 = *(_OWORD *)v39[0];
      *(_QWORD *)&v50 = v15;
      *((_QWORD *)&v50 + 1) = v16;
      v39[0] = v17;
      v39[1] = v21;
      v38[0] = v48[0];
      v38[1] = v18;
      hKey = (HKEY)v46[0];
      v28 = ((char *)v46[1] - (char *)v46[0]) >> 1;
      v22 = Publisher::Publisher(
              (_DWORD)v20,
              (unsigned int)&hKey,
              (unsigned int)v38,
              (unsigned int)v39,
              (__int64)&v50,
              (__int64)&v45,
              (__int64)&v44);
    }
    else
    {
      v22 = 0;
    }
    *a2 = v22;
    if ( v22 )
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&phkResult);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v48);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  }
  else
  {
    v24 = operator new(0xA8u);
    v31 = v24;
    if ( v24 )
    {
      *(_QWORD *)&v50 = v15;
      *((_QWORD *)&v50 + 1) = v16;
      v45 = *(_OWORD *)v38[0];
      v44 = *(_OWORD *)v39[0];
      v25 = Publisher::Publisher(v24, &v44, &v45, &v50);
    }
    else
    {
      v25 = 0;
    }
    *a2 = v25;
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v46[0] != &v47 )
      operator delete(v46[0]);
    if ( v42[0] != &v43 )
      operator delete(v42[0]);
    if ( v48[0] != &v49 )
      operator delete(v48[0]);
    if ( (char *)lpSubKey[0] != &v41 )
      operator delete((void *)lpSubKey[0]);
  }
  return a2;
}

```

## disassembly

```asm
0x180006824  mov     [rsp-8+arg_0], rbx
0x180006829  push    rbp
0x18000682a  push    rsi
0x18000682b  push    rdi
0x18000682c  push    r12
0x18000682e  push    r13
0x180006830  push    r14
0x180006832  push    r15
0x180006834  lea     rbp, [rsp-90h]
0x18000683c  sub     rsp, 190h
0x180006843  mov     rax, cs:__security_cookie
0x18000684a  xor     rax, rsp
0x18000684d  mov     [rbp+0C0h+var_40], rax
0x180006854  mov     r15, r9
0x180006857  mov     [rbp+0C0h+var_120], r9
0x18000685b  mov     rbx, r8
0x18000685e  mov     [rbp+0C0h+var_110], rbx
0x180006862  mov     r14, rdx
0x180006865  mov     [rsp+1C0h+var_150], rcx
0x18000686a  mov     [rsp+1C0h+hKey], rdx
0x18000686f  mov     r13, [rbp+0C0h+arg_20]
0x180006876  xor     r12d, r12d
0x180006879  mov     [rsp+1C0h+hKey], r12
0x18000687e  lea     rcx, [rbp+0C0h+lpSubKey]; void *
0x180006882  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180006887  nop
0x180006888  lea     r8, [rbp+0C0h+lpSubKey]
0x18000688c  lea     rdx, [rsp+1C0h+hKey]
0x180006891  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180006896  mov     esi, eax
0x180006898  lea     edi, [r12+0Eh]
0x18000689d  test    eax, eax
0x18000689f  jz      short loc_1800068EE
0x1800068a1  lea     rbx, WPP_GLOBAL_Control
0x1800068a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068af  cmp     rcx, rbx
0x1800068b2  jz      loc_180006E0B
0x1800068b8  test    byte ptr [rcx+1Ch], 4
0x1800068bc  jz      loc_180006DE5
0x1800068c2  cmp     byte ptr [rcx+19h], 2
0x1800068c6  jb      loc_180006DE5
0x1800068cc  lea     edx, [rdi-1]
0x1800068cf  mov     r9d, eax
0x1800068d2  lea     r8, WPP_c10225a1bfc8322526427285fd9158a0_Traceguids
0x1800068d9  mov     rcx, [rcx+10h]
0x1800068dd  call    WPP_SF_d
0x1800068e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068e9  jmp     loc_180006DE5
0x1800068ee  mov     esi, 5Ch ; '\'
0x1800068f3  mov     edx, esi
0x1800068f5  lea     rcx, [rbp+0C0h+lpSubKey]
0x1800068f9  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800068fe  test    al, al
0x180006900  jz      loc_180006DA8
0x180006906  mov     r8, [r15+8]
0x18000690a  mov     rdx, [r15]
0x18000690d  lea     rcx, [rbp+0C0h+lpSubKey]
0x180006911  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180006916  xor     r15d, r15d
0x180006919  test    al, al
0x18000691b  jz      loc_180006DA5
0x180006921  mov     edx, esi
0x180006923  lea     rcx, [rbp+0C0h+lpSubKey]
0x180006927  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000692c  test    al, al
0x18000692e  jz      loc_180006D3E
0x180006934  mov     r8, [rbx+8]
0x180006938  mov     rdx, [rbx]
0x18000693b  lea     rcx, [rbp+0C0h+lpSubKey]
0x18000693f  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180006944  test    al, al
0x180006946  jz      loc_180006D3E
0x18000694c  lea     rcx, [rbp+0C0h+var_70]; void *
0x180006950  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180006955  nop
0x180006956  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18000695a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000695f  nop
0x180006960  lea     rcx, [rbp+0C0h+var_90]; void *
0x180006964  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180006969  nop
0x18000696a  mov     [rsp+1C0h+var_158], r15
0x18000696f  lea     rax, [rsp+1C0h+var_158]
0x180006974  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180006979  lea     r9d, [rsi-5Bh]; samDesired
0x18000697d  xor     r8d, r8d; ulOptions
0x180006980  mov     rdx, [rbp+0C0h+lpSubKey]; lpSubKey
0x180006984  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180006989  call    cs:__imp_RegOpenKeyExW
0x18000698f  mov     r12b, r15b
0x180006992  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180006997  test    rcx, rcx
0x18000699a  jz      loc_180006AED
0x1800069a0  lea     r9, [rbp+0C0h+var_E0]
0x1800069a4  lea     r8, aProviderguid; "ProviderGuid"
0x1800069ab  lea     rdx, pszFormat
0x1800069b2  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800069b7  test    eax, eax
0x1800069b9  jnz     loc_180006AED
0x1800069bf  xorps   xmm0, xmm0
0x1800069c2  movups  [rbp+0C0h+var_50], xmm0
0x1800069c6  lea     rdx, [rbp+0C0h+var_E0]
0x1800069ca  lea     rcx, [rbp+0C0h+var_50]
0x1800069ce  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800069d3  test    rax, rax
0x1800069d6  jz      loc_180006AAC
0x1800069dc  mov     [rsp+1C0h+hKey], r15
0x1800069e1  lea     rdx, [rbp+0C0h+var_50]
0x1800069e5  lea     rcx, [rsp+1C0h+hKey]
0x1800069ea  call    ?TryGetPublisherConfigReader@PublisherConfigReader@@SAKAEAV?$unique_ptr@VPublisherConfigReader@@U?$default_delete@VPublisherConfigReader@@@utl@@@utl@@AEBU_GUID@@PEAX@Z; PublisherConfigReader::TryGetPublisherConfigReader(utl::unique_ptr<PublisherConfigReader,utl::default_delete<PublisherConfigReader>> &,_GUID const &,void *)
0x1800069ef  mov     rsi, [rsp+1C0h+hKey]
0x1800069f4  test    eax, eax
0x1800069f6  jnz     short loc_180006A64
0x1800069f8  mov     [rsp+1C0h+var_180], r15b
0x1800069fd  lea     rdx, [rsp+1C0h+var_180]; bool *
0x180006a02  mov     rcx, rsi; this
0x180006a05  call    ?GetEnabled@PublisherConfigReader@@QEBA_NAEA_N@Z; PublisherConfigReader::GetEnabled(bool &)
0x180006a0a  test    al, al
0x180006a0c  jz      short loc_180006A1C
0x180006a0e  cmp     [rsp+1C0h+var_180], r15b
0x180006a13  jnz     short loc_180006A1C
0x180006a15  mov     eax, 3ABDh
0x180006a1a  jmp     short loc_180006A64
0x180006a1c  mov     rax, [rsi+48h]
0x180006a20  mov     [rsp+1C0h+hKey], rax
0x180006a25  mov     rcx, [rsi+50h]
0x180006a29  sub     rcx, rax
0x180006a2c  sar     rcx, 1
0x180006a2f  mov     [rsp+1C0h+var_168], rcx
0x180006a34  lea     rdx, [rsp+1C0h+hKey]
0x180006a39  lea     rcx, [rbp+0C0h+var_70]
0x180006a3d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180006a42  test    al, al
0x180006a44  jnz     short loc_180006A4A
0x180006a46  mov     eax, edi
0x180006a48  jmp     short loc_180006A64
0x180006a4a  lea     rdx, [rbp+0C0h+var_90]
0x180006a4e  mov     rcx, rsi
0x180006a51  call    ?GetResourceFilePathUnexpanded@PublisherConfigReader@@QEBA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherConfigReader::GetResourceFilePathUnexpanded(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180006a56  test    al, al
0x180006a58  jz      short loc_180006A5F
0x180006a5a  mov     r12b, 1
0x180006a5d  jmp     short loc_180006A9D
0x180006a5f  mov     eax, 3A9Ah
0x180006a64  lea     rbx, WPP_GLOBAL_Control
0x180006a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a72  cmp     rcx, rbx
0x180006a75  jz      short loc_180006A9D
0x180006a77  test    byte ptr [rcx+1Ch], 10h
0x180006a7b  jz      short loc_180006A9D
0x180006a7d  cmp     byte ptr [rcx+19h], 3
0x180006a81  jb      short loc_180006A9D
0x180006a83  mov     dword ptr [rsp+1C0h+var_198], eax
0x180006a87  mov     rax, [rbp+0C0h+var_E0]
0x180006a8b  mov     [rsp+1C0h+phkResult], rax
0x180006a90  mov     r9, [rbp+0C0h+lpSubKey]
0x180006a94  mov     rcx, [rcx+10h]
0x180006a98  call    WPP_SF_SSD
0x180006a9d  test    rsi, rsi
0x180006aa0  jz      short loc_180006AED
0x180006aa2  mov     rcx, rsi; this
0x180006aa5  call    ??_GPublisherConfigReader@@QEAAPEAXI@Z; PublisherConfigReader::`scalar deleting destructor'(uint)
0x180006aaa  jmp     short loc_180006AED
0x180006aac  lea     rbx, WPP_GLOBAL_Control
0x180006ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aba  cmp     rcx, rbx
0x180006abd  jz      short loc_180006AED
0x180006abf  test    byte ptr [rcx+1Ch], 10h
0x180006ac3  jz      short loc_180006AED
0x180006ac5  cmp     byte ptr [rcx+19h], 3
0x180006ac9  jb      short loc_180006AED
0x180006acb  mov     edx, 11h
0x180006ad0  mov     rax, [rbp+0C0h+var_E0]
0x180006ad4  mov     [rsp+1C0h+phkResult], rax
0x180006ad9  mov     r9, [rbp+0C0h+lpSubKey]
0x180006add  lea     r8, WPP_bddca2f51854389758d0cdf6a87913a3_Traceguids
0x180006ae4  mov     rcx, [rcx+10h]
0x180006ae8  call    WPP_SF_SS
0x180006aed  mov     r15, [r13+0]
0x180006af1  mov     rsi, [r13+8]
0x180006af5  xor     r13d, r13d
0x180006af8  mov     [rsp+1C0h+ClientLocalFlag], r13d
0x180006afd  lea     rdx, [rsp+1C0h+ClientLocalFlag]; ClientLocalFlag
0x180006b02  xor     ecx, ecx; BindingHandle
0x180006b04  call    cs:__imp_I_RpcBindingIsClientLocal
0x180006b0a  test    eax, eax
0x180006b0c  jnz     short loc_180006B31
0x180006b0e  cmp     [rsp+1C0h+ClientLocalFlag], r13d
0x180006b13  jz      short loc_180006B31
0x180006b15  test    byte ptr cs:?g_compatFlags@@3KA, 2; ulong g_compatFlags
0x180006b1c  jnz     short loc_180006B31
0x180006b1e  mov     rax, [rsp+1C0h+var_150]
0x180006b23  mov     r15, [rax+58h]
0x180006b27  mov     rsi, [rax+60h]
0x180006b2b  sub     rsi, r15
0x180006b2e  sar     rsi, 1
0x180006b31  test    r12b, r12b
0x180006b34  jz      loc_180006C7E
0x180006b3a  mov     rdi, [rbp+0C0h+var_E0]
0x180006b3e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006b42  mov     rax, rbx
0x180006b45  inc     rax
0x180006b48  cmp     [rdi+rax*2], r13w
0x180006b4d  jnz     short loc_180006B45
0x180006b4f  cmp     rax, 26h ; '&'
0x180006b53  jnz     short loc_180006B5E
0x180006b55  mov     [rdi+4Ah], r13w
0x180006b5a  add     rdi, 2
0x180006b5e  mov     ecx, 0A8h; dwBytes
0x180006b63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b68  mov     r10, rax
0x180006b6b  mov     [rsp+1C0h+var_150], rax
0x180006b70  test    rax, rax
0x180006b73  jz      loc_180006C10
0x180006b79  mov     rdx, rbx
0x180006b7c  inc     rdx
0x180006b7f  cmp     [rdi+rdx*2], r13w
0x180006b84  jnz     short loc_180006B7C
0x180006b86  mov     rax, [rbp+0C0h+var_70]
0x180006b8a  inc     rbx
0x180006b8d  cmp     [rax+rbx*2], r13w
0x180006b92  jnz     short loc_180006B8A
0x180006b94  mov     rcx, [rbp+0C0h+var_90]
0x180006b98  mov     r8, [rbp+0C0h+var_120]
0x180006b9c  movups  xmm0, xmmword ptr [r8]
0x180006ba0  movdqu  [rbp+0C0h+var_B0], xmm0
0x180006ba5  mov     r8, [rbp+0C0h+var_110]
0x180006ba9  movups  xmm1, xmmword ptr [r8]
0x180006bad  movdqu  [rbp+0C0h+var_A0], xmm1
0x180006bb2  mov     qword ptr [rbp+0C0h+var_50], r15
0x180006bb6  mov     qword ptr [rbp+0C0h+var_50+8], rsi
0x180006bba  mov     [rbp+0C0h+var_110], rdi
0x180006bbe  mov     [rbp+0C0h+var_108], rdx
0x180006bc2  mov     [rbp+0C0h+var_120], rax
0x180006bc6  mov     [rbp+0C0h+var_118], rbx
0x180006bca  mov     [rsp+1C0h+hKey], rcx
0x180006bcf  mov     rax, [rbp+0C0h+var_88]
0x180006bd3  sub     rax, rcx
0x180006bd6  sar     rax, 1
0x180006bd9  mov     [rsp+1C0h+var_168], rax
0x180006bde  lea     rax, [rbp+0C0h+var_B0]
0x180006be2  mov     [rsp+1C0h+var_190], rax
0x180006be7  lea     rax, [rbp+0C0h+var_A0]
0x180006beb  mov     [rsp+1C0h+var_198], rax
0x180006bf0  lea     rax, [rbp+0C0h+var_50]
0x180006bf4  mov     [rsp+1C0h+phkResult], rax
0x180006bf9  lea     r9, [rbp+0C0h+var_110]
0x180006bfd  lea     r8, [rbp+0C0h+var_120]
0x180006c01  lea     rdx, [rsp+1C0h+hKey]
0x180006c06  mov     rcx, r10
0x180006c09  call    ??0Publisher@@AEAA@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@1111@Z; Publisher::Publisher(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180006c0e  jmp     short loc_180006C13
0x180006c10  mov     rax, r13
0x180006c13  mov     [r14], rax
0x180006c16  test    rax, rax
0x180006c19  jz      short loc_180006C1F
0x180006c1b  lock inc dword ptr [rax+8]
0x180006c1f  lea     rcx, [rsp+1C0h+var_158]
0x180006c24  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180006c29  nop
0x180006c2a  lea     rcx, [rbp+0C0h+var_90]; void *
0x180006c2e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180006c33  nop
0x180006c34  lea     rcx, [rbp+0C0h+var_E0]; void *
0x180006c38  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180006c3d  nop
0x180006c3e  lea     rcx, [rbp+0C0h+var_70]; void *
0x180006c42  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180006c47  nop
0x180006c48  lea     rcx, [rbp+0C0h+lpSubKey]; void *
0x180006c4c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180006c51  mov     rax, r14
0x180006c54  mov     rcx, [rbp+0C0h+var_40]
0x180006c5b  xor     rcx, rsp; StackCookie
0x180006c5e  call    __security_check_cookie
0x180006c63  mov     rbx, [rsp+1C0h+arg_0]
0x180006c6b  add     rsp, 190h
0x180006c72  pop     r15
0x180006c74  pop     r14
0x180006c76  pop     r13
0x180006c78  pop     r12
0x180006c7a  pop     rdi
0x180006c7b  pop     rsi
0x180006c7c  pop     rbp
0x180006c7d  retn
0x180006c7e  mov     ecx, 0A8h; dwBytes
0x180006c83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c88  mov     [rsp+1C0h+var_150], rax
0x180006c8d  test    rax, rax
0x180006c90  jz      short loc_180006CCA
0x180006c92  mov     qword ptr [rbp+0C0h+var_50], r15
0x180006c96  mov     qword ptr [rbp+0C0h+var_50+8], rsi
0x180006c9a  mov     r8, [rbp+0C0h+var_120]
0x180006c9e  movups  xmm0, xmmword ptr [r8]
0x180006ca2  movdqu  [rbp+0C0h+var_A0], xmm0
0x180006ca7  mov     r8, [rbp+0C0h+var_110]
0x180006cab  movups  xmm1, xmmword ptr [r8]
0x180006caf  movdqu  [rbp+0C0h+var_B0], xmm1
0x180006cb4  lea     r9, [rbp+0C0h+var_50]
0x180006cb8  lea     r8, [rbp+0C0h+var_A0]
  ... truncated ...
```
