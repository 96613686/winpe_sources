# ApplySettings::ProcessRADIUSServerGroup(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x180045bd4`
- end: `0x1800463dc`
- name: `?ProcessRADIUSServerGroup@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `2056`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x18002cd74`
- `0x1800388a0`
- `0x180038ad0`
- `0x180042a80`
- `0x180043d8c`
- `0x180045bd4`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x18004608c`
- `msvcrt!wcstol` at `0x18004608c`
- `KERNEL32!GetLastError` at `0x180045c4b`
- `KERNEL32!GetLastError` at `0x180045cfc`
- `KERNEL32!GetLastError` at `0x180045d8f`
- `KERNEL32!GetLastError` at `0x180045e1f`
- `KERNEL32!GetLastError` at `0x1800460c1`
- `KERNEL32!GetLastError` at `0x18004618a`
- `KERNEL32!GetLastError` at `0x1800461f6`
- `KERNEL32!GetLastError` at `0x180046262`
- `KERNEL32!GetLastError` at `0x1800462cb`
- `KERNEL32!GetLastError` at `0x180045c4b`
- `KERNEL32!GetLastError` at `0x180045cfc`
- `KERNEL32!GetLastError` at `0x180045d8f`
- `KERNEL32!GetLastError` at `0x180045e1f`
- `KERNEL32!GetLastError` at `0x1800460c1`
- `KERNEL32!GetLastError` at `0x18004618a`
- `KERNEL32!GetLastError` at `0x1800461f6`
- `KERNEL32!GetLastError` at `0x180046262`
- `KERNEL32!GetLastError` at `0x1800462cb`
- `OLEAUT32!__imp_SysAllocString` at `0x180045ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x180045f58`
- `OLEAUT32!__imp_SysAllocString` at `0x180045ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x180045f58`
- `OLEAUT32!__imp_SysFreeString` at `0x180045cf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180045f7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180045cf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180045f7d`
- `OLEAUT32!__imp_VariantInit` at `0x18004604b`
- `OLEAUT32!__imp_VariantInit` at `0x18004604b`
- `OLEAUT32!__imp_VariantClear` at `0x1800460b3`
- `OLEAUT32!__imp_VariantClear` at `0x1800460b3`

## string_xrefs

- `0x180045ca8`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045d59`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045dec`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045e7c`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180046174`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800461e0`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004624c`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800462b8`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180046315`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045c94`: `g_pService->get_RemoteServers`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessRADIUSServerGroup(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r12
  const OLECHAR *v3; // r15
  __int64 v5; // rcx
  unsigned int v6; // edi
  signed int LastError; // eax
  char v8; // bl
  const char *v9; // rsi
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  const OLECHAR *v13; // rcx
  OLECHAR *v14; // rbx
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  __int64 v18; // rax
  const OLECHAR *v19; // rcx
  OLECHAR *v20; // rbx
  __int64 *v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int128 v25; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 (__fastcall *v27)(__int64, _QWORD, __int128 *); // rbx
  const wchar_t *v28; // rcx
  unsigned int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  __int64 v36; // [rsp+38h] [rbp-49h] BYREF
  __int64 v37; // [rsp+40h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-39h] BYREF
  __int128 v39; // [rsp+68h] [rbp-19h] BYREF
  IRecordInfo *v40; // [rsp+78h] [rbp-9h]
  __int64 v41; // [rsp+E8h] [rbp+67h] BYREF
  __int64 v42; // [rsp+F0h] [rbp+6Fh]
  __int64 v43; // [rsp+F8h] [rbp+77h] BYREF
  __int64 v44; // [rsp+100h] [rbp+7Fh] BYREF

  v42 = a2;
  v2 = a2;
  v3 = (const OLECHAR *)(a1 + 2);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 2);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v2, v3);
  v5 = a1[1];
  v37 = 0;
  v41 = 0;
  v43 = 0;
  v36 = 0;
  v44 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 216LL))(v5, &v37);
  if ( v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = LastError;
    }
    else
    {
      v8 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = "g_pService->get_RemoteServers";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v12 = 52;
LABEL_112:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v10, v11, (__int64)v9, v8);
    }
  }
  else
  {
    if ( *((_QWORD *)v3 + 3) < 8u )
      v13 = v3;
    else
      v13 = *(const OLECHAR **)v3;
    v14 = SysAllocString(v13);
    v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v37 + 96LL))(v37, v14, &v41);
    SysFreeString(v14);
    if ( v6 )
    {
      v15 = GetLastError();
      v8 = v15;
      if ( v15 )
      {
        if ( v15 > 0 )
          v8 = v15;
      }
      else
      {
        v8 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v9 = "pRemoteServerGroupsColl->Add";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v12 = 53;
        goto LABEL_112;
      }
    }
    else
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(v41, &IID_IIASServerGroup, &v43);
      if ( v6 )
      {
        v16 = GetLastError();
        v8 = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            v8 = v16;
        }
        else
        {
          v8 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v9 = "pItem->QueryInterface(IIASServerGroup)";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v12 = 54;
          goto LABEL_112;
        }
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 128LL))(v43, &v36);
        if ( v6 )
        {
          v17 = GetLastError();
          v8 = v17;
          if ( v17 )
          {
            if ( v17 > 0 )
              v8 = v17;
          }
          else
          {
            v8 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v9 = "pRemoteServerGroup->get_ServerCollection";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v12 = 55;
            goto LABEL_112;
          }
        }
        else
        {
          if ( v41 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            v41 = 0;
          }
          std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v2, v3);
          while ( 2 )
          {
            std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v2, v3);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WppDbgPrint("got: %ws");
              if ( a1[5] < 8u )
                v18 = (__int64)v3;
              else
                v18 = *(_QWORD *)v3;
              WPP_SF_sS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                56,
                (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
                (unsigned int)"NPSDS",
                v18);
            }
            if ( !(unsigned __int8)std::operator==<unsigned short>(
                                     v3,
                                     L"=================================================") )
            {
              if ( a1[5] < 8u )
                v19 = v3;
              else
                v19 = *(const OLECHAR **)v3;
              v20 = SysAllocString(v19);
              v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v36 + 96LL))(v36, v20, &v41);
              SysFreeString(v20);
              if ( v6 )
              {
                v34 = GetLastError();
                v8 = v34;
                if ( v34 )
                {
                  if ( v34 > 0 )
                    v8 = v34;
                }
                else
                {
                  v8 = 5;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v9 = "pRemoteServers->Add";
                  WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s retur"
                              "ned hr = %!HRESULT!");
                  v12 = 57;
                  goto LABEL_112;
                }
              }
              else
              {
                v21 = a1 + 6;
                while ( 1 )
                {
                  v22 = v42;
                  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
                    v42,
                    a1 + 6);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    WppDbgPrint("got: %ws");
                    if ( a1[9] < 8u )
                      v23 = (__int64)(a1 + 6);
                    else
                      v23 = *v21;
                    WPP_SF_sS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      58,
                      (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
                      (unsigned int)"NPSDS",
                      v23);
                  }
                  if ( (unsigned __int8)std::operator==<unsigned short>(
                                          a1 + 6,
                                          L"----------------------------------------") )
                    break;
                  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
                    v22,
                    a1 + 10);
                  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
                    v42,
                    a1 + 14);
                  memset(&pvarg, 0, sizeof(pvarg));
                  VariantInit(&pvarg);
                  ApplySettings::GetVariant(v24, a1 + 10, a1 + 14, &pvarg);
                  v25 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v41 + 64LL);
                  if ( a1[9] < 8u )
                    v28 = (const wchar_t *)(a1 + 6);
                  else
                    v28 = (const wchar_t *)*v21;
                  v29 = wcstol(v28, 0, 10);
                  v39 = v25;
                  v40 = pRecInfo;
                  v6 = v27(v41, v29, &v39);
                  VariantClear(&pvarg);
                  if ( v6 )
                  {
                    v30 = GetLastError();
                    v8 = v30;
                    if ( v30 )
                    {
                      if ( v30 > 0 )
                        v8 = v30;
                    }
                    else
                    {
                      v8 = 5;
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v9 = "pItem->PutProperty";
                      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s r"
                                  "eturned hr = %!HRESULT!");
                      v12 = 59;
                      goto LABEL_112;
                    }
                    goto LABEL_113;
                  }
                }
                v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 72LL))(v43);
                if ( v6 )
                {
                  v33 = GetLastError();
                  v8 = v33;
                  if ( v33 )
                  {
                    if ( v33 > 0 )
                      v8 = v33;
                  }
                  else
                  {
                    v8 = 5;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v9 = "pRemoteServerGroup->Apply";
                    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s ret"
                                "urned hr = %!HRESULT!");
                    v12 = 60;
                    goto LABEL_112;
                  }
                }
                else
                {
                  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(v41, &IID_IIASRemoteServer, &v44);
                  if ( v6 )
                  {
                    v32 = GetLastError();
                    v8 = v32;
                    if ( v32 )
                    {
                      if ( v32 > 0 )
                        v8 = v32;
                    }
                    else
                    {
                      v8 = 5;
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v9 = "pItem->QueryInterface(IIASRemoteServer)";
                      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s r"
                                  "eturned hr = %!HRESULT!");
                      v12 = 61;
                      goto LABEL_112;
                    }
                  }
                  else
                  {
                    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 72LL))(v44);
                    if ( !v6 )
                    {
                      v2 = v42;
                      continue;
                    }
                    v31 = GetLastError();
                    v8 = v31;
                    if ( v31 )
                    {
                      if ( v31 > 0 )
                        v8 = v31;
                    }
                    else
                    {
                      v8 = 5;
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v9 = "pRemoteServer->Apply";
                      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s r"
                                  "eturned hr = %!HRESULT!");
                      v12 = 62;
                      goto LABEL_112;
                    }
                  }
                }
              }
            }
            break;
          }
        }
      }
    }
  }
LABEL_113:
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return v6;
}

```

## disassembly

```asm
0x180045bd4  mov     rax, rsp
0x180045bd7  mov     [rax+10h], rdx
0x180045bdb  push    rbp
0x180045bdc  push    rbx
0x180045bdd  push    rsi
0x180045bde  push    rdi
0x180045bdf  push    r12
0x180045be1  push    r13
0x180045be3  push    r15
0x180045be5  lea     rbp, [rax-5Fh]
0x180045be9  sub     rsp, 0A0h
0x180045bf0  mov     r12, rdx
0x180045bf3  movaps  xmmword ptr [rax-48h], xmm6
0x180045bf7  lea     r15, [rcx+10h]
0x180045bfb  movaps  xmmword ptr [rax-58h], xmm7
0x180045bff  mov     r13, rcx
0x180045c02  mov     rdx, r15
0x180045c05  mov     rcx, r12
0x180045c08  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045c0d  mov     rdx, r15
0x180045c10  mov     rcx, r12
0x180045c13  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045c18  mov     rcx, [r13+8]
0x180045c1c  lea     rdx, [rbp+57h+var_98]
0x180045c20  xor     esi, esi
0x180045c22  mov     [rbp+57h+var_98], rsi
0x180045c26  mov     [rbp+57h+arg_0], rsi
0x180045c2a  mov     [rbp+57h+arg_10], rsi
0x180045c2e  mov     [rbp+57h+var_A0], rsi
0x180045c32  mov     [rbp+57h+arg_18], rsi
0x180045c36  mov     rax, [rcx]
0x180045c39  mov     rax, [rax+0D8h]
0x180045c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c45  mov     edi, eax
0x180045c47  test    eax, eax
0x180045c49  jz      short loc_180045CBE
0x180045c4b  call    cs:__imp_GetLastError
0x180045c51  mov     ebx, eax
0x180045c53  test    eax, eax
0x180045c55  jz      short loc_180045C64
0x180045c57  jle     short loc_180045C69
0x180045c59  movzx   ebx, ax
0x180045c5c  or      ebx, 80070000h
0x180045c62  jmp     short loc_180045C69
0x180045c64  mov     ebx, 80004005h
0x180045c69  mov     rax, cs:WPP_GLOBAL_Control
0x180045c70  lea     rsi, WPP_GLOBAL_Control
0x180045c77  cmp     rax, rsi
0x180045c7a  jz      loc_18004633F
0x180045c80  cmp     byte ptr [rax+19h], 2
0x180045c84  jb      loc_18004633F
0x180045c8a  test    byte ptr [rax+1Ch], 10h
0x180045c8e  jz      loc_18004633F
0x180045c94  lea     rsi, aGPserviceGetRe; "g_pService->get_RemoteServers"
0x180045c9b  mov     r9d, ebx
0x180045c9e  mov     r8, rsi
0x180045ca1  lea     rdx, aNpsds; "NPSDS"
0x180045ca8  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180045caf  call    WppDbgPrint
0x180045cb4  mov     edx, 34h ; '4'
0x180045cb9  jmp     loc_180046326
0x180045cbe  cmp     qword ptr [r15+18h], 8
0x180045cc3  jb      short loc_180045CCA
0x180045cc5  mov     rcx, [r15]
0x180045cc8  jmp     short loc_180045CCD
0x180045cca  mov     rcx, r15; psz
0x180045ccd  call    cs:__imp_SysAllocString
0x180045cd3  mov     rcx, [rbp+57h+var_98]
0x180045cd7  lea     r8, [rbp+57h+arg_0]
0x180045cdb  mov     rbx, rax
0x180045cde  mov     rdx, [rcx]
0x180045ce1  mov     rax, [rdx+60h]
0x180045ce5  mov     rdx, rbx
0x180045ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ced  mov     rcx, rbx; bstrString
0x180045cf0  mov     edi, eax
0x180045cf2  call    cs:__imp_SysFreeString
0x180045cf8  test    edi, edi
0x180045cfa  jz      short loc_180045D6F
0x180045cfc  call    cs:__imp_GetLastError
0x180045d02  mov     ebx, eax
0x180045d04  test    eax, eax
0x180045d06  jz      short loc_180045D15
0x180045d08  jle     short loc_180045D1A
0x180045d0a  movzx   ebx, ax
0x180045d0d  or      ebx, 80070000h
0x180045d13  jmp     short loc_180045D1A
0x180045d15  mov     ebx, 80004005h
0x180045d1a  mov     rax, cs:WPP_GLOBAL_Control
0x180045d21  lea     rsi, WPP_GLOBAL_Control
0x180045d28  cmp     rax, rsi
0x180045d2b  jz      loc_18004633F
0x180045d31  cmp     byte ptr [rax+19h], 2
0x180045d35  jb      loc_18004633F
0x180045d3b  test    byte ptr [rax+1Ch], 10h
0x180045d3f  jz      loc_18004633F
0x180045d45  lea     rsi, aPremoteserverg_0; "pRemoteServerGroupsColl->Add"
0x180045d4c  mov     r9d, ebx
0x180045d4f  mov     r8, rsi
0x180045d52  lea     rdx, aNpsds; "NPSDS"
0x180045d59  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180045d60  call    WppDbgPrint
0x180045d65  mov     edx, 35h ; '5'
0x180045d6a  jmp     loc_180046326
0x180045d6f  mov     rcx, [rbp+57h+arg_0]
0x180045d73  lea     r8, [rbp+57h+arg_10]
0x180045d77  lea     rdx, IID_IIASServerGroup
0x180045d7e  mov     rax, [rcx]
0x180045d81  mov     rax, [rax]
0x180045d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d89  mov     edi, eax
0x180045d8b  test    eax, eax
0x180045d8d  jz      short loc_180045E02
0x180045d8f  call    cs:__imp_GetLastError
0x180045d95  mov     ebx, eax
0x180045d97  test    eax, eax
0x180045d99  jz      short loc_180045DA8
0x180045d9b  jle     short loc_180045DAD
0x180045d9d  movzx   ebx, ax
0x180045da0  or      ebx, 80070000h
0x180045da6  jmp     short loc_180045DAD
0x180045da8  mov     ebx, 80004005h
0x180045dad  mov     rax, cs:WPP_GLOBAL_Control
0x180045db4  lea     rsi, WPP_GLOBAL_Control
0x180045dbb  cmp     rax, rsi
0x180045dbe  jz      loc_18004633F
0x180045dc4  cmp     byte ptr [rax+19h], 2
0x180045dc8  jb      loc_18004633F
0x180045dce  test    byte ptr [rax+1Ch], 10h
0x180045dd2  jz      loc_18004633F
0x180045dd8  lea     rsi, aPitemQueryinte; "pItem->QueryInterface(IIASServerGroup)"
0x180045ddf  mov     r9d, ebx
0x180045de2  mov     r8, rsi
0x180045de5  lea     rdx, aNpsds; "NPSDS"
0x180045dec  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180045df3  call    WppDbgPrint
0x180045df8  mov     edx, 36h ; '6'
0x180045dfd  jmp     loc_180046326
0x180045e02  mov     rcx, [rbp+57h+arg_10]
0x180045e06  lea     rdx, [rbp+57h+var_A0]
0x180045e0a  mov     rax, [rcx]
0x180045e0d  mov     rax, [rax+80h]
0x180045e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e19  mov     edi, eax
0x180045e1b  test    eax, eax
0x180045e1d  jz      short loc_180045E92
0x180045e1f  call    cs:__imp_GetLastError
0x180045e25  mov     ebx, eax
0x180045e27  test    eax, eax
0x180045e29  jz      short loc_180045E38
0x180045e2b  jle     short loc_180045E3D
0x180045e2d  movzx   ebx, ax
0x180045e30  or      ebx, 80070000h
0x180045e36  jmp     short loc_180045E3D
0x180045e38  mov     ebx, 80004005h
0x180045e3d  mov     rax, cs:WPP_GLOBAL_Control
0x180045e44  lea     rsi, WPP_GLOBAL_Control
0x180045e4b  cmp     rax, rsi
0x180045e4e  jz      loc_18004633F
0x180045e54  cmp     byte ptr [rax+19h], 2
0x180045e58  jb      loc_18004633F
0x180045e5e  test    byte ptr [rax+1Ch], 10h
0x180045e62  jz      loc_18004633F
0x180045e68  lea     rsi, aPremoteserverg_1; "pRemoteServerGroup->get_ServerCollectio"...
0x180045e6f  mov     r9d, ebx
0x180045e72  mov     r8, rsi
0x180045e75  lea     rdx, aNpsds; "NPSDS"
0x180045e7c  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180045e83  call    WppDbgPrint
0x180045e88  mov     edx, 37h ; '7'
0x180045e8d  jmp     loc_180046326
0x180045e92  mov     rcx, [rbp+57h+arg_0]
0x180045e96  test    rcx, rcx
0x180045e99  jz      short loc_180045EAB
0x180045e9b  mov     rax, [rcx]
0x180045e9e  mov     rax, [rax+10h]
0x180045ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ea7  mov     [rbp+57h+arg_0], rsi
0x180045eab  mov     rdx, r15
0x180045eae  mov     rcx, r12
0x180045eb1  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045eb6  lea     rsi, WPP_GLOBAL_Control
0x180045ebd  mov     rdx, r15
0x180045ec0  mov     rcx, r12
0x180045ec3  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045ec8  mov     rax, cs:WPP_GLOBAL_Control
0x180045ecf  cmp     rax, rsi
0x180045ed2  jz      short loc_180045F32
0x180045ed4  cmp     byte ptr [rax+19h], 4
0x180045ed8  jb      short loc_180045F32
0x180045eda  test    byte ptr [rax+1Ch], 10h
0x180045ede  jz      short loc_180045F32
0x180045ee0  cmp     qword ptr [r13+28h], 8
0x180045ee5  jb      short loc_180045EEC
0x180045ee7  mov     rdx, [r15]
0x180045eea  jmp     short loc_180045EEF
0x180045eec  mov     rdx, r15
0x180045eef  lea     rcx, aGotWs; "got: %ws"
0x180045ef6  call    WppDbgPrint
0x180045efb  cmp     qword ptr [r13+28h], 8
0x180045f00  jb      short loc_180045F07
0x180045f02  mov     rax, [r15]
0x180045f05  jmp     short loc_180045F0A
0x180045f07  mov     rax, r15
0x180045f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f11  lea     r9, aNpsds; "NPSDS"
0x180045f18  mov     edx, 38h ; '8'
0x180045f1d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180045f22  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180045f29  mov     rcx, [rcx+10h]
0x180045f2d  call    WPP_SF_sS
0x180045f32  lea     rdx, asc_180066850; "======================================="...
0x180045f39  mov     rcx, r15
0x180045f3c  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180045f41  test    al, al
0x180045f43  jnz     loc_18004633F
0x180045f49  cmp     qword ptr [r13+28h], 8
0x180045f4e  jb      short loc_180045F55
0x180045f50  mov     rcx, [r15]
0x180045f53  jmp     short loc_180045F58
0x180045f55  mov     rcx, r15; psz
0x180045f58  call    cs:__imp_SysAllocString
0x180045f5e  mov     rcx, [rbp+57h+var_A0]
0x180045f62  lea     r8, [rbp+57h+arg_0]
0x180045f66  mov     rbx, rax
0x180045f69  mov     rdx, [rcx]
0x180045f6c  mov     rax, [rdx+60h]
0x180045f70  mov     rdx, rbx
0x180045f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f78  mov     rcx, rbx; bstrString
0x180045f7b  mov     edi, eax
0x180045f7d  call    cs:__imp_SysFreeString
0x180045f83  test    edi, edi
0x180045f85  jnz     loc_1800462CB
0x180045f8b  lea     r12, [r13+30h]
0x180045f8f  mov     rbx, [rbp+57h+arg_8]
0x180045f93  mov     rdx, r12
0x180045f96  mov     rcx, rbx
0x180045f99  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045f9e  mov     rax, cs:WPP_GLOBAL_Control
0x180045fa5  cmp     rax, rsi
0x180045fa8  jz      short loc_18004600A
0x180045faa  cmp     byte ptr [rax+19h], 4
0x180045fae  jb      short loc_18004600A
0x180045fb0  test    byte ptr [rax+1Ch], 10h
0x180045fb4  jz      short loc_18004600A
0x180045fb6  cmp     qword ptr [r13+48h], 8
0x180045fbb  jb      short loc_180045FC3
0x180045fbd  mov     rdx, [r12]
0x180045fc1  jmp     short loc_180045FC6
0x180045fc3  mov     rdx, r12
0x180045fc6  lea     rcx, aGotWs; "got: %ws"
0x180045fcd  call    WppDbgPrint
0x180045fd2  cmp     qword ptr [r13+48h], 8
0x180045fd7  jb      short loc_180045FDF
0x180045fd9  mov     rax, [r12]
0x180045fdd  jmp     short loc_180045FE2
0x180045fdf  mov     rax, r12
0x180045fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fe9  lea     r9, aNpsds; "NPSDS"
0x180045ff0  mov     edx, 3Ah ; ':'
0x180045ff5  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180045ffa  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180046001  mov     rcx, [rcx+10h]
0x180046005  call    WPP_SF_sS
0x18004600a  lea     rdx, asc_1800667F0; "---------------------------------------"...
0x180046011  mov     rcx, r12
0x180046014  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180046019  test    al, al
0x18004601b  jnz     loc_1800460DA
0x180046021  lea     rdx, [r13+50h]
0x180046025  mov     rcx, rbx
0x180046028  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18004602d  mov     rcx, [rbp+57h+arg_8]
0x180046031  lea     rdx, [r13+70h]
0x180046035  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18004603a  xorps   xmm0, xmm0
0x18004603d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180046041  xor     eax, eax
0x180046043  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180046047  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004604b  call    cs:__imp_VariantInit
0x180046051  lea     r9, [rbp+57h+pvarg]
0x180046055  lea     r8, [r13+70h]
0x180046059  lea     rdx, [r13+50h]
0x18004605d  call    ?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z; ApplySettings::GetVariant(std::wstring &,std::wstring &,tagVARIANT &)
0x180046062  cmp     qword ptr [r13+48h], 8
0x180046067  mov     rax, [rbp+57h+arg_0]
0x18004606b  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18004606f  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180046074  mov     rcx, [rax]
0x180046077  mov     rbx, [rcx+40h]
0x18004607b  jb      short loc_180046083
0x18004607d  mov     rcx, [r12]
0x180046081  jmp     short loc_180046086
0x180046083  mov     rcx, r12; String
0x180046086  xor     edx, edx; EndPtr
0x180046088  lea     r8d, [rdx+0Ah]; Radix
0x18004608c  call    cs:__imp_wcstol
0x180046092  mov     rcx, [rbp+57h+arg_0]
  ... truncated ...
```
