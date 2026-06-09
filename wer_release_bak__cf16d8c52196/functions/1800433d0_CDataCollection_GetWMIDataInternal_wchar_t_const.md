# CDataCollection::GetWMIDataInternal(wchar_t const *)

- ea: `0x1800433d0`
- end: `0x180043cde`
- name: `?GetWMIDataInternal@CDataCollection@@AEAAJPEB_W@Z`
- size: `2318`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x18000bc10`
- `0x18000d75c`
- `0x18000dad0`
- `0x180013a20`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001fe24`
- `0x18002c220`
- `0x180030130`
- `0x1800433d0`
- `0x180043ce4`
- `0x180043d04`
- `0x180050db0`
- `0x180061e50`
- `0x18008b0ac`
- `0x18008b18c`
- `0x18008b1c0`
- `0x18008e1a4`
- `0x18008e1c8`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c66`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004346f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800437f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800438ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004346f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800437f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800438ff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180043757`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800439e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180043757`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800439e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043ae1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043ae1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18004369c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18004369c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004350d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004350d`

## pseudocode

```c
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
  int v15; // eax
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
  v15 = CReport::AddFile(*(CReport **)v3, 5, 65537, FileName, L"wql.txt", 0);
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
0x1800433d0  mov     [rsp-8+arg_10], rbx
0x1800433d5  push    rbp
0x1800433d6  push    rsi
0x1800433d7  push    rdi
0x1800433d8  push    r12
0x1800433da  push    r13
0x1800433dc  push    r14
0x1800433de  push    r15
0x1800433e0  lea     rbp, [rsp-220h]
0x1800433e8  sub     rsp, 320h
0x1800433ef  mov     rax, cs:__security_cookie
0x1800433f6  xor     rax, rsp
0x1800433f9  mov     [rbp+250h+var_40], rax
0x180043400  mov     rsi, rdx
0x180043403  mov     r12, rcx
0x180043406  mov     [rbp+250h+var_2C0], rcx
0x18004340a  xor     r13d, r13d
0x18004340d  mov     [rsp+350h+pProxy], r13
0x180043412  mov     [rsp+350h+var_2E0], r13
0x180043417  mov     [rbp+250h+var_2D0], r13d
0x18004341b  lea     rcx, [rbp+250h+var_2A8]; void *
0x18004341f  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180043424  nop
0x180043425  lea     rcx, [rbp+250h+var_2B0]; void *
0x180043429  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18004342e  nop
0x18004342f  lea     rcx, [rbp+250h+var_2B8]; void *
0x180043433  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180043438  nop
0x180043439  lea     rcx, [rbp+250h+var_2A0]; void *
0x18004343d  call    ??0?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180043442  nop
0x180043443  mov     ebx, r13d
0x180043446  mov     [rbp+250h+hFile], rbx
0x18004344a  mov     eax, 0FEFFh
0x18004344f  mov     [rsp+350h+Buffer], ax
0x180043454  mov     [rsp+350h+NumberOfBytesWritten], r13d
0x180043459  lea     rcx, [rbp+250h+lpBuffer]; void *
0x18004345d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180043462  nop
0x180043463  mov     [rbp+250h+FileName], r13w
0x180043468  xor     edx, edx; dwMilliseconds
0x18004346a  mov     rcx, [r12+10h]; hHandle
0x18004346f  call    cs:__imp_WaitForSingleObject
0x180043475  test    eax, eax
0x180043477  jnz     short loc_180043483
0x180043479  mov     edi, 801B8001h
0x18004347e  jmp     loc_180043AE8
0x180043483  test    rsi, rsi
0x180043486  jnz     short loc_1800434C2
0x180043488  lea     r14, WPP_GLOBAL_Control
0x18004348f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043496  cmp     rcx, r14
0x180043499  jz      short loc_1800434B8
0x18004349b  lea     r15d, [rsi+1]
0x18004349f  test    [rcx+1Ch], r15b
0x1800434a3  jz      short loc_1800434B8
0x1800434a5  lea     edx, [rsi+0Ah]
0x1800434a8  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800434af  mov     rcx, [rcx+10h]
0x1800434b3  call    WPP_SF_
0x1800434b8  mov     edi, 80070057h
0x1800434bd  jmp     loc_180043AE8
0x1800434c2  mov     [rbp+250h+var_270], r13
0x1800434c6  lea     rax, [rsp+350h+var_2E0]
0x1800434cb  mov     [rbp+250h+var_268], rax
0x1800434cf  mov     rcx, [rsp+350h+var_2E0]
0x1800434d4  mov     [rsp+350h+var_2E0], r13
0x1800434d9  test    rcx, rcx
0x1800434dc  jz      short loc_1800434EB
0x1800434de  mov     rax, [rcx]
0x1800434e1  mov     rax, [rax+10h]
0x1800434e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434ea  nop
0x1800434eb  lea     rax, [rbp+250h+var_270]
0x1800434ef  mov     [rsp+350h+ppv], rax; ppv
0x1800434f4  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x1800434fb  mov     r15d, 1
0x180043501  mov     r8d, r15d; dwClsContext
0x180043504  xor     edx, edx; pUnkOuter
0x180043506  lea     rcx, _GUID_4590f811_1d3a_11d0_891f_00aa004b2e24; rclsid
0x18004350d  call    cs:__imp_CoCreateInstance
0x180043513  mov     edi, eax
0x180043515  lea     rcx, [rbp+250h+var_270]
0x180043519  call    ??1?$out_ptr_t@V?$unique_ptr@UIFlightClientAPI@@Urelease_delete@tlx@@@utl@@PEAUIFlightClientAPI@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>::~out_ptr_t<utl::unique_ptr<IFlightClientAPI,tlx::release_delete>,IFlightClientAPI *,>(void)
0x18004351e  test    edi, edi
0x180043520  jns     short loc_18004355F
0x180043522  lea     r14, WPP_GLOBAL_Control
0x180043529  mov     rcx, cs:WPP_GLOBAL_Control
0x180043530  cmp     rcx, r14
0x180043533  jz      loc_180043ACE
0x180043539  test    [rcx+1Ch], r15b
0x18004353d  jz      loc_180043ACE
0x180043543  lea     edx, [r15+0Ah]
0x180043547  mov     r9d, edi
0x18004354a  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180043551  mov     rcx, [rcx+10h]
0x180043555  call    WPP_SF_d
0x18004355a  jmp     loc_180043ACE
0x18004355f  lea     rdx, aRootCimv2; "root\\cimv2"
0x180043566  lea     rcx, [rsp+350h+var_300]
0x18004356b  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_W@Z; tlx::make_bstr(wchar_t const *)
0x180043570  mov     rdx, rax
0x180043573  lea     rcx, [rbp+250h+var_2B8]
0x180043577  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x18004357c  lea     rcx, [rsp+350h+var_300]
0x180043581  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180043586  lea     rcx, [rbp+250h+var_2B8]
0x18004358a  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x18004358f  test    al, al
0x180043591  jz      loc_180043CB0
0x180043597  lea     rdx, aWql; "WQL"
0x18004359e  lea     rcx, [rsp+350h+var_300]
0x1800435a3  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_W@Z; tlx::make_bstr(wchar_t const *)
0x1800435a8  mov     rdx, rax
0x1800435ab  lea     rcx, [rbp+250h+var_2A8]
0x1800435af  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x1800435b4  lea     rcx, [rsp+350h+var_300]
0x1800435b9  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x1800435be  lea     rcx, [rbp+250h+var_2A8]
0x1800435c2  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x1800435c7  test    al, al
0x1800435c9  jz      loc_180043C7A
0x1800435cf  mov     rdi, [rsp+350h+var_2E0]
0x1800435d4  mov     rax, [rdi]
0x1800435d7  mov     r14, [rax+18h]
0x1800435db  mov     rcx, [rsp+350h+pProxy]
0x1800435e0  mov     [rsp+350h+pProxy], r13
0x1800435e5  test    rcx, rcx
0x1800435e8  jz      short loc_1800435F7
0x1800435ea  mov     rax, [rcx]
0x1800435ed  mov     rax, [rax+10h]
0x1800435f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435f6  nop
0x1800435f7  lea     rax, [rsp+350h+pProxy]
0x1800435fc  mov     [rsp+350h+var_310], rax
0x180043601  mov     qword ptr [rsp+350h+dwCapabilities], r13
0x180043606  mov     [rsp+350h+pAuthInfo], r13
0x18004360b  mov     [rsp+350h+dwImpLevel], r13d
0x180043610  mov     [rsp+350h+ppv], r13
0x180043615  xor     r9d, r9d
0x180043618  xor     r8d, r8d
0x18004361b  mov     rdx, [rbp+250h+var_2B8]
0x18004361f  mov     rcx, rdi
0x180043622  mov     rax, r14
0x180043625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004362a  mov     edi, eax
0x18004362c  mov     rcx, [rsp+350h+var_2E0]
0x180043631  mov     [rsp+350h+var_2E0], r13
0x180043636  test    rcx, rcx
0x180043639  jz      short loc_180043648
0x18004363b  mov     rdx, [rcx]
0x18004363e  mov     rax, [rdx+10h]
0x180043642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043647  nop
0x180043648  test    edi, edi
0x18004364a  jz      short loc_180043677
0x18004364c  lea     r14, WPP_GLOBAL_Control
0x180043653  mov     rcx, cs:WPP_GLOBAL_Control
0x18004365a  cmp     rcx, r14
0x18004365d  jz      loc_180043ACE
0x180043663  test    [rcx+1Ch], r15b
0x180043667  jz      loc_180043ACE
0x18004366d  mov     edx, 0Eh
0x180043672  jmp     loc_180043547
0x180043677  mov     [rsp+350h+dwCapabilities], r13d; dwCapabilities
0x18004367c  mov     [rsp+350h+pAuthInfo], r13; pAuthInfo
0x180043681  mov     [rsp+350h+dwImpLevel], 3; dwImpLevel
0x180043689  mov     dword ptr [rsp+350h+ppv], r13d; dwAuthnLevel
0x18004368e  xor     r9d, r9d; pServerPrincName
0x180043691  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180043694  mov     r8d, edx; dwAuthzSvc
0x180043697  mov     rcx, [rsp+350h+pProxy]; pProxy
0x18004369c  call    cs:__imp_CoSetProxyBlanket
0x1800436a2  mov     edi, eax
0x1800436a4  test    eax, eax
0x1800436a6  jns     short loc_1800436D6
0x1800436a8  lea     r14, WPP_GLOBAL_Control
0x1800436af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800436b6  cmp     rcx, r14
0x1800436b9  jz      loc_180043ACE
0x1800436bf  test    [rcx+1Ch], r15b
0x1800436c3  jz      loc_180043ACE
0x1800436c9  mov     edx, 0Fh
0x1800436ce  mov     r9d, eax
0x1800436d1  jmp     loc_18004354A
0x1800436d6  mov     [rsp+350h+dwCapabilities], r13d
0x1800436db  mov     dword ptr [rsp+350h+pAuthInfo], r15d
0x1800436e0  mov     qword ptr [rsp+350h+dwImpLevel], r13
0x1800436e5  lea     r9, [rbp+250h+FileName]
0x1800436e9  lea     r8, aWmiTxt; ".wmi.txt"
0x1800436f0  xor     edx, edx
0x1800436f2  lea     rcx, [rbp+250h+hFile]
0x1800436f6  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1800436fb  mov     edi, eax
0x1800436fd  test    eax, eax
0x1800436ff  jns     short loc_18004373B
0x180043701  lea     r14, WPP_GLOBAL_Control
0x180043708  mov     rcx, cs:WPP_GLOBAL_Control
0x18004370f  cmp     rcx, r14
0x180043712  jz      short loc_180043732
0x180043714  test    [rcx+1Ch], r15b
0x180043718  jz      short loc_180043732
0x18004371a  mov     edx, 10h
0x18004371f  mov     r9d, eax
0x180043722  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180043729  mov     rcx, [rcx+10h]
0x18004372d  call    WPP_SF_d
0x180043732  mov     rbx, [rbp+250h+hFile]
0x180043736  jmp     loc_180043ACE
0x18004373b  mov     [rsp+350h+ppv], r13; lpOverlapped
0x180043740  lea     r9, [rsp+350h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180043745  mov     r8d, 2; nNumberOfBytesToWrite
0x18004374b  lea     rdx, [rsp+350h+Buffer]; lpBuffer
0x180043750  mov     rbx, [rbp+250h+hFile]
0x180043754  mov     rcx, rbx; hFile
0x180043757  call    cs:__imp_WriteFile
0x18004375d  test    eax, eax
0x18004375f  jz      loc_180043C38
0x180043765  mov     [rbp+250h+var_2CC], r13d
0x180043769  cmp     [rsp+350h+NumberOfBytesWritten], 2
0x18004376e  jnz     loc_180043C38
0x180043774  lea     r14, WPP_GLOBAL_Control
0x18004377b  test    rsi, rsi
0x18004377e  jz      loc_180043B72
0x180043784  cmp     [rsi], r13w
0x180043788  jz      loc_180043B72
0x18004378e  mov     al, r13b
0x180043791  mov     cl, r13b
0x180043794  mov     r13, rsi
0x180043797  xor     edi, edi
0x180043799  test    al, al
0x18004379b  jz      short loc_1800437A5
0x18004379d  mov     al, dil
0x1800437a0  jmp     loc_1800438BC
0x1800437a5  cmp     [r13+0], di
0x1800437aa  jz      short loc_1800437E8
0x1800437ac  cmp     word ptr [r13+0], 22h ; '"'
0x1800437b2  jz      loc_1800438BC
0x1800437b8  cmp     word ptr [r13+0], 27h ; '''
0x1800437be  jz      loc_1800438B7
0x1800437c4  cmp     word ptr [r13+0], 3Bh ; ';'
0x1800437ca  jz      short loc_1800437E0
0x1800437cc  cmp     word ptr [r13+0], 5Ch ; '\'
0x1800437d2  jnz     loc_1800438BC
0x1800437d8  mov     al, r15b
0x1800437db  jmp     loc_1800438BC
0x1800437e0  test    cl, cl
0x1800437e2  jnz     loc_1800438BC
0x1800437e8  test    r13, r13
0x1800437eb  jz      loc_180043B6F
0x1800437f1  xor     edx, edx; dwMilliseconds
0x1800437f3  mov     rcx, [r12+10h]; hHandle
0x1800437f8  call    cs:__imp_WaitForSingleObject
0x1800437fe  test    eax, eax
0x180043800  jz      loc_180043C1B
0x180043806  mov     r8, r13
0x180043809  sub     r8, rsi
0x18004380c  sar     r8, 1
0x18004380f  mov     rdx, rsi
0x180043812  lea     rcx, [rbp+250h+var_278]
0x180043816  call    ?make_bstr@tlx@@YA?AV?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEB_WI@Z; tlx::make_bstr(wchar_t const *,uint)
0x18004381b  mov     rdx, rax
0x18004381e  lea     rcx, [rbp+250h+var_2B0]
0x180043822  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x180043827  lea     rcx, [rbp+250h+var_278]
0x18004382b  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180043830  lea     rcx, [rbp+250h+var_2B0]
0x180043834  call    ??B?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEBA_NXZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator bool(void)
0x180043839  test    al, al
0x18004383b  jz      loc_180043BDC
0x180043841  mov     [rsp+350h+var_300], rdi
0x180043846  mov     rcx, [rsp+350h+pProxy]
0x18004384b  mov     rax, [rcx]
0x18004384e  mov     [rsp+350h+var_300], rdi
0x180043853  lea     rdx, [rsp+350h+var_300]
0x180043858  mov     qword ptr [rsp+350h+dwImpLevel], rdx
0x18004385d  mov     [rsp+350h+ppv], rdi
0x180043862  mov     r9d, 30h ; '0'
0x180043868  mov     r8, [rbp+250h+var_2B0]
0x18004386c  mov     rdx, [rbp+250h+var_2A8]
0x180043870  mov     rax, [rax+0A0h]
0x180043877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004387c  test    eax, eax
0x18004387e  jns     short loc_1800438C5
0x180043880  mov     rcx, cs:WPP_GLOBAL_Control
0x180043887  cmp     rcx, r14
0x18004388a  jz      loc_180043A90
0x180043890  test    [rcx+1Ch], r15b
0x180043894  jz      loc_180043A90
0x18004389a  mov     edx, 13h
0x18004389f  mov     r9d, eax
0x1800438a2  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800438a9  mov     rcx, [rcx+10h]
0x1800438ad  call    WPP_SF_d
0x1800438b2  jmp     loc_180043A90
0x1800438b7  test    cl, cl
0x1800438b9  setz    cl
0x1800438bc  add     r13, 2
0x1800438c0  jmp     loc_180043799
  ... truncated ...
```
