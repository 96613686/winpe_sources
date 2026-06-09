# CDataCollection::GetWMIDataInternal(wchar_t const *)

- ea: `0x180044a18`
- end: `0x18004535d`
- name: `?GetWMIDataInternal@CDataCollection@@AEAAJPEB_W@Z`
- size: `2373`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044080`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008298`
- `0x180008698`
- `0x18000cf50`
- `0x18000db80`
- `0x18000ed68`
- `0x1800172c0`
- `0x18001c368`
- `0x180020680`
- `0x18002dc4c`
- `0x180031870`
- `0x180044a18`
- `0x180045364`
- `0x180045388`
- `0x180053300`
- `0x180064778`
- `0x18008ef84`
- `0x18008f054`
- `0x18008f080`
- `0x1800921b8`
- `0x1800921e4`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044ab7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044e58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044f65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044ab7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044e58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044f65`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180044db1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045055`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180044db1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045055`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045153`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045153`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180044cf0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180044cf0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b5b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDataCollection::GetWMIDataInternal(CDataCollection *this, const wchar_t *a2)
{
  CDataCollection *v3; // r12
  HANDLE v4; // rbx
  HRESULT Instance; // edi
  wchar_t *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 bstr; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // r14
  IUnknown *v13; // rcx
  __int64 v14; // rcx
  HRESULT v15; // eax
  int TempFile; // eax
  bool v17; // al
  bool v18; // cl
  const wchar_t *i; // r13
  __int64 v20; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // edi
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64); // rdi
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rdi
  __int64 v30; // r12
  __int64 v31; // rsi
  DWORD v32; // edi
  int v34; // eax
  DWORD LastError; // eax
  int pAuthInfo; // [rsp+30h] [rbp-D0h]
  int dwCapabilities; // [rsp+38h] [rbp-C8h]
  __int64 *v38; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int16 Buffer; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *pProxy; // [rsp+78h] [rbp-88h] BYREF
  int v44; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+84h] [rbp-7Ch]
  HANDLE hFile; // [rsp+88h] [rbp-78h] BYREF
  CDataCollection *v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h] BYREF
  LPCVOID lpBuffer; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE *v53; // [rsp+C0h] [rbp-40h]
  _BYTE v54[8]; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID ppv[4]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR FileName[264]; // [rsp+100h] [rbp+0h] BYREF

  v3 = this;
  v47 = this;
  pProxy = 0;
  v42 = 0;
  v44 = 0;
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v50);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v49);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v48);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v51);
  v4 = 0;
  hFile = 0;
  Buffer = -257;
  NumberOfBytesWritten = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  FileName[0] = 0;
  if ( !WaitForSingleObject(*((HANDLE *)v3 + 2), 0) )
  {
    Instance = -2145681407;
    goto LABEL_90;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    Instance = -2147024809;
    goto LABEL_90;
  }
  ppv[0] = 0;
  ppv[1] = &v42;
  v42 = 0;
  Instance = CoCreateInstance(
               &GUID_4590f811_1d3a_11d0_891f_00aa004b2e24,
               0,
               1u,
               &GUID_dc12a687_737f_11cf_884d_00aa004b2e24,
               ppv);
  utl::out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>::~out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>(ppv);
  if ( Instance < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v7 = 11;
LABEL_12:
    v8 = (unsigned int)Instance;
    goto LABEL_13;
  }
  bstr = tlx::make_bstr(&v38, L"root\\cimv2");
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(&v48, bstr);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v38);
  if ( !(unsigned __int8)utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(&v48) )
  {
    Instance = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v7 = 12;
    goto LABEL_112;
  }
  v10 = tlx::make_bstr(&v38, L"WQL");
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(&v50, v10);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v38);
  if ( !(unsigned __int8)utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(&v50) )
  {
    Instance = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v7 = 13;
LABEL_112:
    v8 = 2147942414LL;
    goto LABEL_13;
  }
  v11 = v42;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v42 + 24LL);
  v13 = pProxy;
  pProxy = 0;
  if ( v13 )
    ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
  Instance = v12(v11, v48, 0, 0, 0, 0, 0, 0, &pProxy);
  v14 = v42;
  v42 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( Instance )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v7 = 14;
    goto LABEL_12;
  }
  v15 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
  Instance = v15;
  if ( v15 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 15;
      goto LABEL_28;
    }
    goto LABEL_87;
  }
  dwCapabilities = 0;
  pAuthInfo = 1;
  TempFile = UtilGetTempFile(&hFile, 0, L".wmi.txt", FileName);
  Instance = TempFile;
  if ( TempFile < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)TempFile);
    v4 = hFile;
    goto LABEL_87;
  }
  v4 = hFile;
  if ( !WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) || (v45 = 0, NumberOfBytesWritten != 2) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    LastError = GetLastError();
    Instance = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_87;
  }
  while ( 2 )
  {
    if ( !a2 || !*a2 )
      goto LABEL_92;
    v17 = 0;
    v18 = 0;
    for ( i = a2; ; ++i )
    {
      if ( v17 )
      {
        v17 = 0;
        continue;
      }
      if ( !*i )
        break;
      if ( *i != 34 )
      {
        if ( *i == 39 )
        {
          v18 = !v18;
          continue;
        }
        if ( *i != 59 )
        {
          v17 = *i == 92;
          continue;
        }
        if ( !v18 )
          break;
      }
    }
    if ( !i )
      goto LABEL_92;
    if ( !WaitForSingleObject(*((HANDLE *)v3 + 2), 0) )
    {
      Instance = -2145681407;
      goto LABEL_87;
    }
    v20 = tlx::make_bstr(v54, a2, i - a2);
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(&v49, v20);
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(v54);
    if ( !(unsigned __int8)utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(&v49) )
    {
      Instance = -2147024882;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147942414LL);
      goto LABEL_87;
    }
    v38 = 0;
    lpVtbl = pProxy->lpVtbl;
    v38 = 0;
    v22 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, __int64 **, int, int))lpVtbl[6].Release)(
            pProxy,
            v50,
            v49,
            48,
            0,
            &v38,
            pAuthInfo,
            dwCapabilities);
    if ( v22 >= 0 )
    {
      while ( 1 )
      {
        v40 = 0;
        v23 = *v38;
        v40 = 0;
        v24 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *, int *))(v23 + 32))(
                v38,
                500,
                1,
                &v40,
                &v44);
        if ( !WaitForSingleObject(*((HANDLE *)v3 + 2), 0) )
          break;
        if ( v24 != 262148 )
        {
          if ( v24 < 0 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
                (unsigned int)v24);
LABEL_82:
            utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v40);
            goto LABEL_83;
          }
          if ( v44 == 1 )
          {
            v25 = v40;
            v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v40 + 104LL);
            v27 = utl::replace<wchar_t [0],tlx::sysfreestring_delete>(&v51);
            v28 = v26(v25, 0, v27);
            v29 = 0;
            if ( v28 >= 0 )
            {
              v30 = v51;
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)(v51 + 2 * v31) );
              v53 = lpBuffer;
              *(_WORD *)lpBuffer = 0;
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(&lpBuffer);
              while ( v29 != v31 )
              {
                if ( *(_WORD *)(v30 + 2 * v29) == 10
                  && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                         &lpBuffer,
                                         13)
                  || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                         &lpBuffer,
                                         *(unsigned __int16 *)(v30 + 2 * v29)) )
                {
                  Instance = -2147024882;
                  goto LABEL_86;
                }
                ++v29;
              }
              v32 = 2 * ((v53 - (_BYTE *)lpBuffer) >> 1);
              if ( WriteFile(v4, lpBuffer, v32, &NumberOfBytesWritten, 0) && v32 == NumberOfBytesWritten )
              {
                v45 = 1;
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
                  v32,
                  NumberOfBytesWritten);
              }
              v3 = v47;
            }
          }
          else if ( !v44 )
          {
            goto LABEL_82;
          }
        }
        utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v40);
      }
      Instance = -2145681407;
LABEL_86:
      utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v40);
      utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v38);
      goto LABEL_87;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)v22);
LABEL_83:
    if ( *i )
    {
      a2 = i + 1;
      utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v38);
      continue;
    }
    break;
  }
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v38);
LABEL_92:
  v34 = 0;
  if ( !v45 )
    goto LABEL_103;
  v15 = CReport::AddFile(*(CReport **)v3, WerFileTypeOther, 0x10001u, FileName, L"wql.txt", 0);
  Instance = v15;
  if ( v15 >= 0 )
  {
    v34 = 1;
LABEL_103:
    Instance = 0;
    if ( !v34 )
      goto LABEL_87;
    goto LABEL_90;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v7 = 22;
LABEL_28:
    v8 = (unsigned int)v15;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v8);
  }
LABEL_87:
  if ( (unsigned __int64)v4 + 1 > 1 && FileName[0] )
    DeleteFileW(FileName);
LABEL_90:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpBuffer);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v51);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v48);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v49);
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v50);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v42);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&pProxy);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180044a18  mov     [rsp-8+arg_10], rbx
0x180044a1d  push    rbp
0x180044a1e  push    rsi
0x180044a1f  push    rdi
0x180044a20  push    r12
0x180044a22  push    r13
0x180044a24  push    r14
0x180044a26  push    r15
0x180044a28  lea     rbp, [rsp-220h]
0x180044a30  sub     rsp, 320h
0x180044a37  mov     rax, cs:__security_cookie
0x180044a3e  xor     rax, rsp
0x180044a41  mov     [rbp+250h+var_40], rax
0x180044a48  mov     rsi, rdx
0x180044a4b  mov     r12, rcx
0x180044a4e  mov     [rbp+250h+var_2C0], rcx
0x180044a52  xor     r13d, r13d
0x180044a55  mov     [rsp+350h+pProxy], r13
0x180044a5a  mov     [rsp+350h+var_2E0], r13
0x180044a5f  mov     [rbp+250h+var_2D0], r13d
0x180044a63  lea     rcx, [rbp+250h+var_2A8]; void *
0x180044a67  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044a6c  nop
0x180044a6d  lea     rcx, [rbp+250h+var_2B0]; void *
0x180044a71  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044a76  nop
0x180044a77  lea     rcx, [rbp+250h+var_2B8]; void *
0x180044a7b  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044a80  nop
0x180044a81  lea     rcx, [rbp+250h+var_2A0]; void *
0x180044a85  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044a8a  nop
0x180044a8b  mov     ebx, r13d
0x180044a8e  mov     [rbp+250h+hFile], rbx
0x180044a92  mov     eax, 0FEFFh
0x180044a97  mov     [rsp+350h+Buffer], ax
0x180044a9c  mov     [rsp+350h+NumberOfBytesWritten], r13d
0x180044aa1  lea     rcx, [rbp+250h+lpBuffer]; void *
0x180044aa5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180044aaa  nop
0x180044aab  mov     [rbp+250h+FileName], r13w
0x180044ab0  xor     edx, edx; dwMilliseconds
0x180044ab2  mov     rcx, [r12+10h]; hHandle
0x180044ab7  call    cs:__imp_WaitForSingleObject
0x180044abe  nop     dword ptr [rax+rax+00h]
0x180044ac3  test    eax, eax
0x180044ac5  jnz     short loc_180044AD1
0x180044ac7  mov     edi, 801B8001h
0x180044acc  jmp     loc_180045160
0x180044ad1  test    rsi, rsi
0x180044ad4  jnz     short loc_180044B10
0x180044ad6  lea     r14, WPP_GLOBAL_Control
0x180044add  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ae4  cmp     rcx, r14
0x180044ae7  jz      short loc_180044B06
0x180044ae9  lea     r15d, [rsi+1]
0x180044aed  test    [rcx+1Ch], r15b
0x180044af1  jz      short loc_180044B06
0x180044af3  lea     edx, [rsi+0Ah]
0x180044af6  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180044afd  mov     rcx, [rcx+10h]
0x180044b01  call    WPP_SF_
0x180044b06  mov     edi, 80070057h
0x180044b0b  jmp     loc_180045160
0x180044b10  mov     [rbp+250h+var_270], r13
0x180044b14  lea     rax, [rsp+350h+var_2E0]
0x180044b19  mov     [rbp+250h+var_268], rax
0x180044b1d  mov     rcx, [rsp+350h+var_2E0]
0x180044b22  mov     [rsp+350h+var_2E0], r13
0x180044b27  test    rcx, rcx
0x180044b2a  jz      short loc_180044B39
0x180044b2c  mov     rax, [rcx]
0x180044b2f  mov     rax, [rax+10h]
0x180044b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b38  nop
0x180044b39  lea     rax, [rbp+250h+var_270]
0x180044b3d  mov     [rsp+350h+ppv], rax; ppv
0x180044b42  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x180044b49  mov     r15d, 1
0x180044b4f  mov     r8d, r15d; dwClsContext
0x180044b52  xor     edx, edx; pUnkOuter
0x180044b54  lea     rcx, _GUID_4590f811_1d3a_11d0_891f_00aa004b2e24; rclsid
0x180044b5b  call    cs:__imp_CoCreateInstance
0x180044b62  nop     dword ptr [rax+rax+00h]
0x180044b67  mov     edi, eax
0x180044b69  lea     rcx, [rbp+250h+var_270]
0x180044b6d  call    ??1?$out_ptr_t@V?$unique_ptr@UIFlightClientAPI@@Urelease_delete@tlx@@@utl@@PEAUIFlightClientAPI@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>::~out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>(void)
0x180044b72  test    edi, edi
0x180044b74  jns     short loc_180044BB3
0x180044b76  lea     r14, WPP_GLOBAL_Control
0x180044b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b84  cmp     rcx, r14
0x180044b87  jz      loc_180045140
0x180044b8d  test    [rcx+1Ch], r15b
0x180044b91  jz      loc_180045140
0x180044b97  lea     edx, [r15+0Ah]
0x180044b9b  mov     r9d, edi
0x180044b9e  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180044ba5  mov     rcx, [rcx+10h]
0x180044ba9  call    WPP_SF_d
0x180044bae  jmp     loc_180045140
0x180044bb3  lea     rdx, aRootCimv2; "root\\cimv2"
0x180044bba  lea     rcx, [rsp+350h+var_300]
0x180044bbf  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_W@Z; tlx::make_bstr(wchar_t const *)
0x180044bc4  mov     rdx, rax
0x180044bc7  lea     rcx, [rbp+250h+var_2B8]
0x180044bcb  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x180044bd0  lea     rcx, [rsp+350h+var_300]
0x180044bd5  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044bda  lea     rcx, [rbp+250h+var_2B8]
0x180044bde  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x180044be3  test    al, al
0x180044be5  jz      loc_18004532F
0x180044beb  lea     rdx, aWql; "WQL"
0x180044bf2  lea     rcx, [rsp+350h+var_300]
0x180044bf7  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_W@Z; tlx::make_bstr(wchar_t const *)
0x180044bfc  mov     rdx, rax
0x180044bff  lea     rcx, [rbp+250h+var_2A8]
0x180044c03  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x180044c08  lea     rcx, [rsp+350h+var_300]
0x180044c0d  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044c12  lea     rcx, [rbp+250h+var_2A8]
0x180044c16  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x180044c1b  test    al, al
0x180044c1d  jz      loc_1800452F9
0x180044c23  mov     rdi, [rsp+350h+var_2E0]
0x180044c28  mov     rax, [rdi]
0x180044c2b  mov     r14, [rax+18h]
0x180044c2f  mov     rcx, [rsp+350h+pProxy]
0x180044c34  mov     [rsp+350h+pProxy], r13
0x180044c39  test    rcx, rcx
0x180044c3c  jz      short loc_180044C4B
0x180044c3e  mov     rax, [rcx]
0x180044c41  mov     rax, [rax+10h]
0x180044c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c4a  nop
0x180044c4b  lea     rax, [rsp+350h+pProxy]
0x180044c50  mov     [rsp+350h+var_310], rax
0x180044c55  mov     qword ptr [rsp+350h+dwCapabilities], r13
0x180044c5a  mov     [rsp+350h+pAuthInfo], r13
0x180044c5f  mov     [rsp+350h+dwImpLevel], r13d
0x180044c64  mov     [rsp+350h+ppv], r13
0x180044c69  xor     r9d, r9d
0x180044c6c  xor     r8d, r8d
0x180044c6f  mov     rdx, [rbp+250h+var_2B8]
0x180044c73  mov     rcx, rdi
0x180044c76  mov     rax, r14
0x180044c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c7e  mov     edi, eax
0x180044c80  mov     rcx, [rsp+350h+var_2E0]
0x180044c85  mov     [rsp+350h+var_2E0], r13
0x180044c8a  test    rcx, rcx
0x180044c8d  jz      short loc_180044C9C
0x180044c8f  mov     rdx, [rcx]
0x180044c92  mov     rax, [rdx+10h]
0x180044c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c9b  nop
0x180044c9c  test    edi, edi
0x180044c9e  jz      short loc_180044CCB
0x180044ca0  lea     r14, WPP_GLOBAL_Control
0x180044ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cae  cmp     rcx, r14
0x180044cb1  jz      loc_180045140
0x180044cb7  test    [rcx+1Ch], r15b
0x180044cbb  jz      loc_180045140
0x180044cc1  mov     edx, 0Eh
0x180044cc6  jmp     loc_180044B9B
0x180044ccb  mov     [rsp+350h+dwCapabilities], r13d; dwCapabilities
0x180044cd0  mov     [rsp+350h+pAuthInfo], r13; pAuthInfo
0x180044cd5  mov     [rsp+350h+dwImpLevel], 3; dwImpLevel
0x180044cdd  mov     dword ptr [rsp+350h+ppv], r13d; dwAuthnLevel
0x180044ce2  xor     r9d, r9d; pServerPrincName
0x180044ce5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180044ce8  mov     r8d, edx; dwAuthzSvc
0x180044ceb  mov     rcx, [rsp+350h+pProxy]; pProxy
0x180044cf0  call    cs:__imp_CoSetProxyBlanket
0x180044cf7  nop     dword ptr [rax+rax+00h]
0x180044cfc  mov     edi, eax
0x180044cfe  test    eax, eax
0x180044d00  jns     short loc_180044D30
0x180044d02  lea     r14, WPP_GLOBAL_Control
0x180044d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d10  cmp     rcx, r14
0x180044d13  jz      loc_180045140
0x180044d19  test    [rcx+1Ch], r15b
0x180044d1d  jz      loc_180045140
0x180044d23  mov     edx, 0Fh
0x180044d28  mov     r9d, eax
0x180044d2b  jmp     loc_180044B9E
0x180044d30  mov     [rsp+350h+dwCapabilities], r13d
0x180044d35  mov     dword ptr [rsp+350h+pAuthInfo], r15d
0x180044d3a  mov     qword ptr [rsp+350h+dwImpLevel], r13
0x180044d3f  lea     r9, [rbp+250h+FileName]
0x180044d43  lea     r8, aWmiTxt; ".wmi.txt"
0x180044d4a  xor     edx, edx
0x180044d4c  lea     rcx, [rbp+250h+hFile]
0x180044d50  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180044d55  mov     edi, eax
0x180044d57  test    eax, eax
0x180044d59  jns     short loc_180044D95
0x180044d5b  lea     r14, WPP_GLOBAL_Control
0x180044d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d69  cmp     rcx, r14
0x180044d6c  jz      short loc_180044D8C
0x180044d6e  test    [rcx+1Ch], r15b
0x180044d72  jz      short loc_180044D8C
0x180044d74  mov     edx, 10h
0x180044d79  mov     r9d, eax
0x180044d7c  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180044d83  mov     rcx, [rcx+10h]
0x180044d87  call    WPP_SF_d
0x180044d8c  mov     rbx, [rbp+250h+hFile]
0x180044d90  jmp     loc_180045140
0x180044d95  mov     [rsp+350h+ppv], r13; lpOverlapped
0x180044d9a  lea     r9, [rsp+350h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180044d9f  mov     r8d, 2; nNumberOfBytesToWrite
0x180044da5  lea     rdx, [rsp+350h+Buffer]; lpBuffer
0x180044daa  mov     rbx, [rbp+250h+hFile]
0x180044dae  mov     rcx, rbx; hFile
0x180044db1  call    cs:__imp_WriteFile
0x180044db8  nop     dword ptr [rax+rax+00h]
0x180044dbd  test    eax, eax
0x180044dbf  jz      loc_1800452B1
0x180044dc5  mov     [rbp+250h+var_2CC], r13d
0x180044dc9  cmp     [rsp+350h+NumberOfBytesWritten], 2
0x180044dce  jnz     loc_1800452B1
0x180044dd4  lea     r14, WPP_GLOBAL_Control
0x180044ddb  test    rsi, rsi
0x180044dde  jz      loc_1800451EB
0x180044de4  cmp     [rsi], r13w
0x180044de8  jz      loc_1800451EB
0x180044dee  mov     al, r13b
0x180044df1  mov     cl, r13b
0x180044df4  mov     r13, rsi
0x180044df7  xor     edi, edi
0x180044df9  test    al, al
0x180044dfb  jz      short loc_180044E05
0x180044dfd  mov     al, dil
0x180044e00  jmp     loc_180044F22
0x180044e05  cmp     [r13+0], di
0x180044e0a  jz      short loc_180044E48
0x180044e0c  cmp     word ptr [r13+0], 22h ; '"'
0x180044e12  jz      loc_180044F22
0x180044e18  cmp     word ptr [r13+0], 27h ; '''
0x180044e1e  jz      loc_180044F1D
0x180044e24  cmp     word ptr [r13+0], 3Bh ; ';'
0x180044e2a  jz      short loc_180044E40
0x180044e2c  cmp     word ptr [r13+0], 5Ch ; '\'
0x180044e32  jnz     loc_180044F22
0x180044e38  mov     al, r15b
0x180044e3b  jmp     loc_180044F22
0x180044e40  test    cl, cl
0x180044e42  jnz     loc_180044F22
0x180044e48  test    r13, r13
0x180044e4b  jz      loc_1800451E8
0x180044e51  xor     edx, edx; dwMilliseconds
0x180044e53  mov     rcx, [r12+10h]; hHandle
0x180044e58  call    cs:__imp_WaitForSingleObject
0x180044e5f  nop     dword ptr [rax+rax+00h]
0x180044e64  test    eax, eax
0x180044e66  jz      loc_180045294
0x180044e6c  mov     r8, r13
0x180044e6f  sub     r8, rsi
0x180044e72  sar     r8, 1
0x180044e75  mov     rdx, rsi
0x180044e78  lea     rcx, [rbp+250h+var_278]
0x180044e7c  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_WI@Z; tlx::make_bstr(wchar_t const *,uint)
0x180044e81  mov     rdx, rax
0x180044e84  lea     rcx, [rbp+250h+var_2B0]
0x180044e88  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x180044e8d  lea     rcx, [rbp+250h+var_278]
0x180044e91  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180044e96  lea     rcx, [rbp+250h+var_2B0]
0x180044e9a  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x180044e9f  test    al, al
0x180044ea1  jz      loc_180045255
0x180044ea7  mov     [rsp+350h+var_300], rdi
0x180044eac  mov     rcx, [rsp+350h+pProxy]
0x180044eb1  mov     rax, [rcx]
0x180044eb4  mov     [rsp+350h+var_300], rdi
0x180044eb9  lea     rdx, [rsp+350h+var_300]
0x180044ebe  mov     qword ptr [rsp+350h+dwImpLevel], rdx
0x180044ec3  mov     [rsp+350h+ppv], rdi
0x180044ec8  mov     r9d, 30h ; '0'
0x180044ece  mov     r8, [rbp+250h+var_2B0]
0x180044ed2  mov     rdx, [rbp+250h+var_2A8]
0x180044ed6  mov     rax, [rax+0A0h]
0x180044edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ee2  test    eax, eax
0x180044ee4  jns     short loc_180044F2B
0x180044ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180044eed  cmp     rcx, r14
0x180044ef0  jz      loc_180045102
0x180044ef6  test    [rcx+1Ch], r15b
0x180044efa  jz      loc_180045102
0x180044f00  mov     edx, 13h
0x180044f05  mov     r9d, eax
0x180044f08  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180044f0f  mov     rcx, [rcx+10h]
0x180044f13  call    WPP_SF_d
  ... truncated ...
```
