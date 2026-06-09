# CSettingsManager::DownloadSettingsStrings(ushort const *,ushort const *)

- ea: `0x1801bb5b8`
- end: `0x1801bb8e9`
- name: `?DownloadSettingsStrings@CSettingsManager@@QEAAJPEBG0@Z`
- size: `817`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18019f2a8`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x180027cc8`
- `0x180027ee4`
- `0x1801b0b8c`
- `0x1801bb5b8`
- `0x1801bbf40`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb772`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb7ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb7ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb845`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb772`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb7ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb7ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bb845`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb87f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb892`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb8aa`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb87f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb892`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801bb8aa`
- `XmlLite!CreateXmlReader` at `0x1801bb66b`
- `XmlLite!CreateXmlReader` at `0x1801bb66b`

## pseudocode

```c
__int64 __fastcall CSettingsManager::DownloadSettingsStrings(
        CSettingsManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // ebx
  __int64 v5; // rbx
  char v6; // si
  char v7; // di
  int v8; // eax
  CSettingsManager *v9; // rcx
  CSettingsManager *v10; // rcx
  CSettingsManager *v11; // rcx
  int v13; // [rsp+40h] [rbp-40h] BYREF
  int v14; // [rsp+44h] [rbp-3Ch] BYREF
  void *ppvObject; // [rsp+48h] [rbp-38h] BYREF
  LPCWCH lpString1; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-20h] BYREF
  int v19; // [rsp+C8h] [rbp+48h] BYREF

  v17 = 0;
  memset(v18, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v18,
         L"?setlang=%s&cc=%s",
         a2,
         a3);
  if ( v4 < 0 )
    goto LABEL_31;
  v5 = *((_QWORD *)this + 2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  v4 = CConnectedSearchTransport::_HttpRequest(v5, 7, L"GET", v18[0], 0, 0, 0, &v17);
  if ( v4 < 0 )
    goto LABEL_31;
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v4 < 0 )
    goto LABEL_30;
  v4 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v17);
  if ( v4 < 0 )
    goto LABEL_30;
  v6 = 0;
  v7 = 0;
  while ( v4 >= 0 && !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
  {
    v19 = 0;
    lpString1 = 0;
    v14 = 0;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v19);
    v4 = v8;
    if ( v8 == 1 )
    {
      v4 = 0;
      break;
    }
    if ( v8 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &lpString1,
             &v14);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &v13);
        if ( v4 >= 0 )
        {
          if ( v19 == 1 )
          {
            if ( v13 )
            {
              if ( v13 == 1 )
              {
                if ( CompareStringOrdinal(lpString1, -1, L"termsOfUse", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v9,
                         (struct IXmlReader *)ppvObject,
                         0,
                         L"ConnectedSearchTOUUrl");
                }
                else if ( CompareStringOrdinal(lpString1, -1, L"impressum", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v10,
                         (struct IXmlReader *)ppvObject,
                         L"ConnectedSearchImpressumTitle",
                         L"ConnectedSearchImpressumUrl");
                  v6 = 1;
                }
                else if ( CompareStringOrdinal(lpString1, -1, L"icp", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v11,
                         (struct IXmlReader *)ppvObject,
                         L"ConnectedSearchICPTitle",
                         0);
                  v7 = 1;
                }
              }
            }
            else
            {
LABEL_23:
              if ( CompareStringOrdinal(lpString1, -1, L"settings", -1, 0) != 2 )
                v4 = -2147467259;
            }
          }
          else if ( v19 == 15 && v13 == 1 )
          {
            goto LABEL_23;
          }
        }
      }
    }
  }
  if ( !v6 )
  {
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchImpressumTitle");
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchImpressumUrl");
  }
  if ( !v7 )
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchICPTitle");
LABEL_30:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
LABEL_31:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801bb5b8  mov     [rsp-28h+arg_0], rbx
0x1801bb5bd  mov     [rsp-28h+arg_8], rsi
0x1801bb5c2  push    rbp
0x1801bb5c3  push    rdi
0x1801bb5c4  push    r12
0x1801bb5c6  push    r14
0x1801bb5c8  push    r15
0x1801bb5ca  mov     rbp, rsp
0x1801bb5cd  sub     rsp, 80h
0x1801bb5d4  xor     r14d, r14d
0x1801bb5d7  mov     r9, r8
0x1801bb5da  mov     r8, rdx
0x1801bb5dd  mov     [rbp+var_28], r14
0x1801bb5e1  mov     rdi, rcx
0x1801bb5e4  mov     [rbp+var_20], r14
0x1801bb5e8  lea     rdx, aSetlangSCcS; "?setlang=%s&cc=%s"
0x1801bb5ef  mov     [rbp+var_18], r14
0x1801bb5f3  lea     rcx, [rbp+var_20]
0x1801bb5f7  mov     [rbp+var_10], r14
0x1801bb5fb  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801bb600  mov     ebx, eax
0x1801bb602  test    eax, eax
0x1801bb604  js      loc_1801BB8B9
0x1801bb60a  mov     rbx, [rdi+10h]
0x1801bb60e  lea     rcx, [rbp+var_28]
0x1801bb612  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bb617  mov     r9, [rbp+var_20]
0x1801bb61b  lea     rax, [rbp+var_28]
0x1801bb61f  mov     [rsp+80h+var_48], rax
0x1801bb624  lea     r8, aGet; "GET"
0x1801bb62b  mov     [rsp+80h+var_50], r14
0x1801bb630  lea     edx, [r14+7]
0x1801bb634  mov     [rsp+80h+var_58], r14d
0x1801bb639  mov     rcx, rbx
0x1801bb63c  mov     qword ptr [rsp+80h+bIgnoreCase], r14
0x1801bb641  call    ?_HttpRequest@CConnectedSearchTransport@@AEAAJW4HttpEndpoint@1@PEBG11W4HttpRequestFlags@@1PEAPEAUIStream@@@Z; CConnectedSearchTransport::_HttpRequest(CConnectedSearchTransport::HttpEndpoint,ushort const *,ushort const *,ushort const *,HttpRequestFlags,ushort const *,IStream * *)
0x1801bb646  mov     ebx, eax
0x1801bb648  test    eax, eax
0x1801bb64a  js      loc_1801BB8B9
0x1801bb650  lea     rcx, [rbp+ppvObject]
0x1801bb654  mov     [rbp+ppvObject], r14
0x1801bb658  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801bb65d  xor     r8d, r8d; pMalloc
0x1801bb660  lea     rdx, [rbp+ppvObject]; ppvObject
0x1801bb664  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1801bb66b  call    cs:__imp_CreateXmlReader
0x1801bb671  mov     ebx, eax
0x1801bb673  test    eax, eax
0x1801bb675  js      loc_1801BB8B0
0x1801bb67b  mov     rcx, [rbp+ppvObject]
0x1801bb67f  mov     rdx, [rbp+var_28]
0x1801bb683  mov     rax, [rcx]
0x1801bb686  mov     rax, [rax+18h]
0x1801bb68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb68f  mov     ebx, eax
0x1801bb691  test    eax, eax
0x1801bb693  js      loc_1801BB8B0
0x1801bb699  mov     sil, r14b
0x1801bb69c  mov     dil, r14b
0x1801bb69f  or      r15d, 0FFFFFFFFh
0x1801bb6a3  mov     r12d, 80004005h
0x1801bb6a9  test    ebx, ebx
0x1801bb6ab  js      loc_1801BB85F
0x1801bb6b1  mov     rcx, [rbp+ppvObject]
0x1801bb6b5  mov     rax, [rcx]
0x1801bb6b8  mov     rax, [rax+0C8h]
0x1801bb6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb6c4  test    eax, eax
0x1801bb6c6  jnz     loc_1801BB85F
0x1801bb6cc  mov     rcx, [rbp+ppvObject]
0x1801bb6d0  lea     rdx, [rbp+arg_18]
0x1801bb6d4  mov     [rbp+arg_18], r14d
0x1801bb6d8  mov     [rbp+lpString1], r14
0x1801bb6dc  mov     [rbp+var_3C], r14d
0x1801bb6e0  mov     [rbp+var_40], r14d
0x1801bb6e4  mov     rax, [rcx]
0x1801bb6e7  mov     rax, [rax+30h]
0x1801bb6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb6f0  mov     ebx, eax
0x1801bb6f2  cmp     eax, 1
0x1801bb6f5  jz      loc_1801BB85C
0x1801bb6fb  test    eax, eax
0x1801bb6fd  js      short loc_1801BB6A9
0x1801bb6ff  mov     rcx, [rbp+ppvObject]
0x1801bb703  lea     r8, [rbp+var_3C]
0x1801bb707  lea     rdx, [rbp+lpString1]
0x1801bb70b  mov     rax, [rcx]
0x1801bb70e  mov     rax, [rax+70h]
0x1801bb712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb717  mov     ebx, eax
0x1801bb719  test    eax, eax
0x1801bb71b  js      short loc_1801BB6A9
0x1801bb71d  mov     rcx, [rbp+ppvObject]
0x1801bb721  lea     rdx, [rbp+var_40]
0x1801bb725  mov     rax, [rcx]
0x1801bb728  mov     rax, [rax+0C0h]
0x1801bb72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb734  mov     ebx, eax
0x1801bb736  test    eax, eax
0x1801bb738  js      loc_1801BB6A9
0x1801bb73e  cmp     [rbp+arg_18], 1
0x1801bb742  jnz     loc_1801BB81B
0x1801bb748  mov     eax, [rbp+var_40]
0x1801bb74b  test    eax, eax
0x1801bb74d  jz      loc_1801BB82F
0x1801bb753  cmp     eax, 1
0x1801bb756  jnz     loc_1801BB6A9
0x1801bb75c  mov     rcx, [rbp+lpString1]; lpString1
0x1801bb760  lea     r8, aTermsofuse; "termsOfUse"
0x1801bb767  mov     r9d, r15d; cchCount2
0x1801bb76a  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801bb76f  mov     edx, r15d; cchCount1
0x1801bb772  call    cs:__imp_CompareStringOrdinal
0x1801bb778  cmp     eax, 2
0x1801bb77b  jnz     short loc_1801BB797
0x1801bb77d  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801bb781  lea     r9, aConnectedsearc_11; "ConnectedSearchTOUUrl"
0x1801bb788  xor     r8d, r8d; unsigned __int16 *
0x1801bb78b  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801bb790  mov     ebx, eax
0x1801bb792  jmp     loc_1801BB6A9
0x1801bb797  mov     rcx, [rbp+lpString1]; lpString1
0x1801bb79b  lea     r8, aImpressum; "impressum"
0x1801bb7a2  mov     r9d, r15d; cchCount2
0x1801bb7a5  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801bb7aa  mov     edx, r15d; cchCount1
0x1801bb7ad  call    cs:__imp_CompareStringOrdinal
0x1801bb7b3  cmp     eax, 2
0x1801bb7b6  jnz     short loc_1801BB7D9
0x1801bb7b8  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801bb7bc  lea     r9, aConnectedsearc_9; "ConnectedSearchImpressumUrl"
0x1801bb7c3  lea     r8, aConnectedsearc_7; "ConnectedSearchImpressumTitle"
0x1801bb7ca  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801bb7cf  mov     ebx, eax
0x1801bb7d1  mov     sil, 1
0x1801bb7d4  jmp     loc_1801BB6A9
0x1801bb7d9  mov     rcx, [rbp+lpString1]; lpString1
0x1801bb7dd  lea     r8, aIcp; "icp"
0x1801bb7e4  mov     r9d, r15d; cchCount2
0x1801bb7e7  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801bb7ec  mov     edx, r15d; cchCount1
0x1801bb7ef  call    cs:__imp_CompareStringOrdinal
0x1801bb7f5  cmp     eax, 2
0x1801bb7f8  jnz     loc_1801BB6A9
0x1801bb7fe  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801bb802  lea     r8, aConnectedsearc_10; "ConnectedSearchICPTitle"
0x1801bb809  xor     r9d, r9d; unsigned __int16 *
0x1801bb80c  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801bb811  mov     ebx, eax
0x1801bb813  mov     dil, 1
0x1801bb816  jmp     loc_1801BB6A9
0x1801bb81b  cmp     [rbp+arg_18], 0Fh
0x1801bb81f  jnz     loc_1801BB6A9
0x1801bb825  cmp     [rbp+var_40], 1
0x1801bb829  jnz     loc_1801BB6A9
0x1801bb82f  mov     rcx, [rbp+lpString1]; lpString1
0x1801bb833  lea     r8, aSettings; "settings"
0x1801bb83a  mov     r9d, r15d; cchCount2
0x1801bb83d  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801bb842  mov     edx, r15d; cchCount1
0x1801bb845  call    cs:__imp_CompareStringOrdinal
0x1801bb84b  cmp     eax, 2
0x1801bb84e  jz      loc_1801BB6A9
0x1801bb854  mov     ebx, r12d
0x1801bb857  jmp     loc_1801BB6A9
0x1801bb85c  mov     ebx, r14d
0x1801bb85f  lea     r15, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801bb866  mov     r12, 0FFFFFFFF80000001h
0x1801bb86d  test    sil, sil
0x1801bb870  jnz     short loc_1801BB898
0x1801bb872  lea     r8, aConnectedsearc_7; "ConnectedSearchImpressumTitle"
0x1801bb879  mov     rdx, r15; lpSubKey
0x1801bb87c  mov     rcx, r12; hKey
0x1801bb87f  call    cs:__imp_RegDeleteKeyValueW
0x1801bb885  lea     r8, aConnectedsearc_9; "ConnectedSearchImpressumUrl"
0x1801bb88c  mov     rdx, r15; lpSubKey
0x1801bb88f  mov     rcx, r12; hKey
0x1801bb892  call    cs:__imp_RegDeleteKeyValueW
0x1801bb898  test    dil, dil
0x1801bb89b  jnz     short loc_1801BB8B0
0x1801bb89d  lea     r8, aConnectedsearc_10; "ConnectedSearchICPTitle"
0x1801bb8a4  mov     rdx, r15; lpSubKey
0x1801bb8a7  mov     rcx, r12; hKey
0x1801bb8aa  call    cs:__imp_RegDeleteKeyValueW
0x1801bb8b0  lea     rcx, [rbp+ppvObject]
0x1801bb8b4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801bb8b9  lea     rcx, [rbp+var_20]
0x1801bb8bd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801bb8c2  lea     rcx, [rbp+var_28]
0x1801bb8c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bb8cb  lea     r11, [rsp+80h+var_s0]
0x1801bb8d3  mov     eax, ebx
0x1801bb8d5  mov     rbx, [r11+30h]
0x1801bb8d9  mov     rsi, [r11+38h]
0x1801bb8dd  mov     rsp, r11
0x1801bb8e0  pop     r15
0x1801bb8e2  pop     r14
0x1801bb8e4  pop     r12
0x1801bb8e6  pop     rdi
0x1801bb8e7  pop     rbp
0x1801bb8e8  retn
```
