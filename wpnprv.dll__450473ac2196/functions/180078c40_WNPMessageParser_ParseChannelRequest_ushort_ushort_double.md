# WNPMessageParser::ParseChannelRequest(ushort * *,ushort * *,double *)

- ea: `0x180078c40`
- end: `0x18007949b`
- name: `?ParseChannelRequest@WNPMessageParser@@QEAAJPEAPEAG0PEAN@Z`
- size: `2139`
- prototype: `__int64 __fastcall(WNPMessageParser *__hidden this, unsigned __int16 **, unsigned __int16 **, double *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f850`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180076f44`
- `0x180078c40`
- `0x18007b718`
- `0x180084f88`
- `0x180091630`
- `0x180096010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180078de0`
- `XmlLite!CreateXmlReader` at `0x180078de0`
- `OLEAUT32!__imp_SysAllocString` at `0x180078f8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18007903a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800790db`
- `OLEAUT32!__imp_SysAllocString` at `0x180078f8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18007903a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800790db`
- `OLEAUT32!__imp_SysFreeString` at `0x180079424`
- `OLEAUT32!__imp_SysFreeString` at `0x180079439`
- `OLEAUT32!__imp_SysFreeString` at `0x180079452`
- `OLEAUT32!__imp_SysFreeString` at `0x180079424`
- `OLEAUT32!__imp_SysFreeString` at `0x180079439`
- `OLEAUT32!__imp_SysFreeString` at `0x180079452`

## pseudocode

```c
__int64 __fastcall WNPMessageParser::ParseChannelRequest(
        WNPMessageParser *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        double *a4)
{
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // r13
  int v10; // eax
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  wchar_t *v19; // rbx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  wchar_t *v23; // rax
  int v24; // eax
  int v25; // eax
  int v27; // [rsp+20h] [rbp-38h] BYREF
  void *ppvObject; // [rsp+28h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *String2; // [rsp+38h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-18h]
  struct IStream *v32; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_21a3201469733e5c8660b272590c09d0_Traceguids);
  }
  v32 = 0;
  v8 = 0;
  ppvObject = 0;
  v9 = 0;
  v27 = 0;
  String2 = 0;
  psz = 0;
  bstrString = 0;
  v10 = WNPMessageParser::ScanHeaders(this);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v10);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v11,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v11);
      goto LABEL_119;
    }
    goto LABEL_120;
  }
  v13 = WNPMessageParser::CreatePayloadStream(this, &v32);
  v11 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v13);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v11,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_117;
    v14 = 18;
    goto LABEL_21;
  }
  v16 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v11 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v16);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v11,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_117;
    v14 = 20;
    goto LABEL_21;
  }
  v17 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v32);
  v11 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
        (unsigned int)v17);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)v11,
      v27);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_117;
    v14 = 22;
    goto LABEL_21;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( (*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v27) )
            {
              v23 = bstrString;
LABEL_96:
              if ( !v8 || !v9 || !v23 )
              {
                v11 = -2147467259;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    33,
                    WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
                    2147500037LL);
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xE0,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
                  (const char *)0x80004005LL,
                  v27);
                v12 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                  goto LABEL_117;
                v14 = 34;
                v15 = 2147500037LL;
                goto LABEL_115;
              }
              v25 = WpnParseVarDate(v23, a4);
              v11 = v25;
              if ( v25 >= 0 )
              {
                *a2 = v8;
                v8 = 0;
                *a3 = v9;
                v9 = 0;
LABEL_116:
                v12 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_117;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
                  (unsigned int)v25);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xE5,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
                (const char *)v11,
                v27);
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                goto LABEL_117;
              v14 = 36;
LABEL_21:
              v15 = v11;
LABEL_115:
              WPP_SF_d(v12[2], v14, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v15);
              goto LABEL_116;
            }
            if ( v27 != 1 )
              break;
            v24 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                    ppvObject,
                    &String2,
                    0);
            v11 = v24;
            if ( v24 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  23,
                  WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
                  (unsigned int)v24);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xA0,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
                (const char *)v11,
                v27);
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                goto LABEL_117;
              v14 = 24;
              goto LABEL_21;
            }
          }
          if ( v27 == 3 )
            break;
          if ( v27 == 15 )
          {
            String2 = 0;
            psz = 0;
          }
        }
      }
      while ( !String2 );
      v18 = (*(__int64 (__fastcall **)(void *, OLECHAR **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(ppvObject, &psz, 0);
      v11 = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            (unsigned int)v18);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)v11,
          v27);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_117;
        v14 = 26;
        goto LABEL_21;
      }
      v19 = String2;
      v20 = *String2;
      v21 = 105 - v20;
      if ( v20 == 105 )
      {
        v22 = String2[1];
        v21 = 100 - v22;
        if ( v22 == 100 )
          v21 = -String2[2];
      }
      if ( v21 )
        break;
      v8 = SysAllocString(psz);
      if ( !v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            2147942414LL);
        }
        v11 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)0x8007000ELL,
          v27);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_117;
        v14 = 28;
        goto LABEL_57;
      }
LABEL_70:
      if ( v9 )
      {
        v23 = bstrString;
        if ( bstrString )
          goto LABEL_96;
      }
    }
    if ( !wcscmp_0(L"url", String2) )
    {
      v9 = SysAllocString(psz);
      if ( !v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            2147942414LL);
        }
        v11 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)0x8007000ELL,
          v27);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_117;
        v14 = 30;
LABEL_57:
        v15 = 2147942414LL;
        goto LABEL_115;
      }
      goto LABEL_69;
    }
    if ( !wcscmp_0(L"exp", v19) )
    {
      bstrString = SysAllocString(psz);
      if ( !bstrString )
        break;
    }
LABEL_69:
    if ( v8 )
      goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942414LL);
  }
  v11 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xC3,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
    (const char *)0x8007000ELL,
    v27);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v14 = 32;
    goto LABEL_57;
  }
LABEL_117:
  if ( v32 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_119:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_120:
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    ppvObject = 0;
  }
  if ( v8 )
  {
    SysFreeString(v8);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    SysFreeString(v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 37, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180078c40  push    rbp
0x180078c42  push    rbx
0x180078c43  push    rsi
0x180078c44  push    rdi
0x180078c45  push    r12
0x180078c47  push    r13
0x180078c49  push    r14
0x180078c4b  push    r15
0x180078c4d  mov     rbp, rsp
0x180078c50  sub     rsp, 58h
0x180078c54  mov     rsi, r9
0x180078c57  mov     r14, r8
0x180078c5a  mov     r15, rdx
0x180078c5d  mov     rdi, rcx
0x180078c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c67  lea     rax, WPP_GLOBAL_Control
0x180078c6e  cmp     rcx, rax
0x180078c71  jz      short loc_180078C94
0x180078c73  test    byte ptr [rcx+1Ch], 2
0x180078c77  jz      short loc_180078C94
0x180078c79  cmp     byte ptr [rcx+19h], 6
0x180078c7d  jb      short loc_180078C94
0x180078c7f  mov     rcx, [rcx+10h]
0x180078c83  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078c8a  mov     edx, 0Eh
0x180078c8f  call    WPP_SF_
0x180078c94  xor     eax, eax
0x180078c96  mov     rcx, rdi; this
0x180078c99  mov     [rbp+var_10], rax
0x180078c9d  mov     r12d, eax
0x180078ca0  mov     [rbp+ppvObject], rax
0x180078ca4  mov     r13d, eax
0x180078ca7  mov     [rbp+var_38], eax
0x180078caa  mov     [rbp+String2], rax
0x180078cae  mov     [rbp+psz], rax
0x180078cb2  mov     [rbp+bstrString], rax
0x180078cb6  call    ?ScanHeaders@WNPMessageParser@@AEAAJXZ; WNPMessageParser::ScanHeaders(void)
0x180078cbb  mov     ebx, eax
0x180078cbd  test    eax, eax
0x180078cbf  jns     loc_180078D4A
0x180078cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ccc  lea     rsi, WPP_GLOBAL_Control
0x180078cd3  cmp     rcx, rsi
0x180078cd6  jz      short loc_180078CFB
0x180078cd8  test    byte ptr [rcx+1Ch], 2
0x180078cdc  jz      short loc_180078CFB
0x180078cde  cmp     byte ptr [rcx+19h], 2
0x180078ce2  jb      short loc_180078CFB
0x180078ce4  mov     rcx, [rcx+10h]
0x180078ce8  lea     edx, [r13+0Fh]
0x180078cec  mov     r9d, eax
0x180078cef  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078cf6  call    WPP_SF_d
0x180078cfb  mov     rcx, [rbp+40h]; this
0x180078cff  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078d06  mov     r9d, ebx; char *
0x180078d09  mov     edx, 88h; void *
0x180078d0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d1a  cmp     rcx, rsi
0x180078d1d  jz      loc_1800793F5
0x180078d23  test    byte ptr [rcx+1Ch], 80h
0x180078d27  jz      loc_1800793F5
0x180078d2d  mov     rcx, [rcx+10h]
0x180078d31  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078d38  mov     edx, 10h
0x180078d3d  mov     r9d, ebx
0x180078d40  call    WPP_SF_d
0x180078d45  jmp     loc_1800793EE
0x180078d4a  lea     rdx, [rbp+var_10]; struct IStream **
0x180078d4e  mov     rcx, rdi; this
0x180078d51  call    ?CreatePayloadStream@WNPMessageParser@@AEAAJPEAPEAUIStream@@@Z; WNPMessageParser::CreatePayloadStream(IStream * *)
0x180078d56  mov     ebx, eax
0x180078d58  test    eax, eax
0x180078d5a  jns     short loc_180078DD2
0x180078d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d63  lea     rsi, WPP_GLOBAL_Control
0x180078d6a  cmp     rcx, rsi
0x180078d6d  jz      short loc_180078D93
0x180078d6f  test    byte ptr [rcx+1Ch], 2
0x180078d73  jz      short loc_180078D93
0x180078d75  cmp     byte ptr [rcx+19h], 2
0x180078d79  jb      short loc_180078D93
0x180078d7b  mov     rcx, [rcx+10h]
0x180078d7f  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078d86  mov     edx, 11h
0x180078d8b  mov     r9d, eax
0x180078d8e  call    WPP_SF_d
0x180078d93  mov     rcx, [rbp+40h]; this
0x180078d97  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078d9e  mov     r9d, ebx; char *
0x180078da1  mov     edx, 8Dh; void *
0x180078da6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180078db2  cmp     rcx, rsi
0x180078db5  jz      loc_1800793D6
0x180078dbb  test    byte ptr [rcx+1Ch], 80h
0x180078dbf  jz      loc_1800793D6
0x180078dc5  mov     edx, 12h
0x180078dca  mov     r9d, ebx
0x180078dcd  jmp     loc_1800793BF
0x180078dd2  xor     r8d, r8d; pMalloc
0x180078dd5  lea     rdx, [rbp+ppvObject]; ppvObject
0x180078dd9  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180078de0  call    cs:__imp_CreateXmlReader
0x180078de6  mov     ebx, eax
0x180078de8  test    eax, eax
0x180078dea  jns     short loc_180078E5F
0x180078dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180078df3  lea     rsi, WPP_GLOBAL_Control
0x180078dfa  cmp     rcx, rsi
0x180078dfd  jz      short loc_180078E23
0x180078dff  test    byte ptr [rcx+1Ch], 2
0x180078e03  jz      short loc_180078E23
0x180078e05  cmp     byte ptr [rcx+19h], 2
0x180078e09  jb      short loc_180078E23
0x180078e0b  mov     rcx, [rcx+10h]
0x180078e0f  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078e16  mov     edx, 13h
0x180078e1b  mov     r9d, eax
0x180078e1e  call    WPP_SF_d
0x180078e23  mov     rcx, [rbp+40h]; this
0x180078e27  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078e2e  mov     r9d, ebx; char *
0x180078e31  mov     edx, 91h; void *
0x180078e36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078e42  cmp     rcx, rsi
0x180078e45  jz      loc_1800793D6
0x180078e4b  test    byte ptr [rcx+1Ch], 80h
0x180078e4f  jz      loc_1800793D6
0x180078e55  mov     edx, 14h
0x180078e5a  jmp     loc_180078DCA
0x180078e5f  mov     rcx, [rbp+ppvObject]
0x180078e63  mov     rdx, [rbp+var_10]
0x180078e67  mov     rax, [rcx]
0x180078e6a  mov     rax, [rax+18h]
0x180078e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e73  mov     ebx, eax
0x180078e75  test    eax, eax
0x180078e77  jns     short loc_180078EEC
0x180078e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180078e80  lea     rsi, WPP_GLOBAL_Control
0x180078e87  cmp     rcx, rsi
0x180078e8a  jz      short loc_180078EB0
0x180078e8c  test    byte ptr [rcx+1Ch], 2
0x180078e90  jz      short loc_180078EB0
0x180078e92  cmp     byte ptr [rcx+19h], 2
0x180078e96  jb      short loc_180078EB0
0x180078e98  mov     rcx, [rcx+10h]
0x180078e9c  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078ea3  mov     edx, 15h
0x180078ea8  mov     r9d, eax
0x180078eab  call    WPP_SF_d
0x180078eb0  mov     rcx, [rbp+40h]; this
0x180078eb4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078ebb  mov     r9d, ebx; char *
0x180078ebe  mov     edx, 95h; void *
0x180078ec3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ecf  cmp     rcx, rsi
0x180078ed2  jz      loc_1800793D6
0x180078ed8  test    byte ptr [rcx+1Ch], 80h
0x180078edc  jz      loc_1800793D6
0x180078ee2  mov     edx, 16h
0x180078ee7  jmp     loc_180078DCA
0x180078eec  mov     rcx, [rbp+ppvObject]
0x180078ef0  lea     rdx, [rbp+var_38]
0x180078ef4  mov     rax, [rcx]
0x180078ef7  mov     rax, [rax+30h]
0x180078efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f00  test    eax, eax
0x180078f02  jnz     loc_180079293
0x180078f08  mov     ecx, [rbp+var_38]
0x180078f0b  sub     ecx, 1
0x180078f0e  jz      loc_180079112
0x180078f14  sub     ecx, 2
0x180078f17  jz      short loc_180078F30
0x180078f19  cmp     ecx, 0Ch
0x180078f1c  jnz     short loc_180078EEC
0x180078f1e  mov     [rbp+String2], 0
0x180078f26  mov     [rbp+psz], 0
0x180078f2e  jmp     short loc_180078EEC
0x180078f30  cmp     [rbp+String2], 0
0x180078f35  jz      short loc_180078EEC
0x180078f37  mov     rcx, [rbp+ppvObject]
0x180078f3b  lea     rdx, [rbp+psz]
0x180078f3f  xor     r8d, r8d
0x180078f42  mov     rax, [rcx]
0x180078f45  mov     rax, [rax+80h]
0x180078f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f51  mov     ebx, eax
0x180078f53  test    eax, eax
0x180078f55  js      loc_180079220
0x180078f5b  mov     rbx, [rbp+String2]
0x180078f5f  mov     ecx, 69h ; 'i'
0x180078f64  movzx   eax, word ptr [rbx]
0x180078f67  sub     ecx, eax
0x180078f69  jnz     short loc_180078F83
0x180078f6b  movzx   eax, word ptr [rbx+2]
0x180078f6f  mov     ecx, 64h ; 'd'
0x180078f74  sub     ecx, eax
0x180078f76  jnz     short loc_180078F83
0x180078f78  xor     eax, eax
0x180078f7a  movzx   ecx, ax
0x180078f7d  movzx   eax, word ptr [rbx+4]
0x180078f81  sub     ecx, eax
0x180078f83  test    ecx, ecx
0x180078f85  jnz     loc_18007901F
0x180078f8b  mov     rcx, [rbp+psz]; psz
0x180078f8f  call    cs:__imp_SysAllocString
0x180078f95  mov     r12, rax
0x180078f98  test    rax, rax
0x180078f9b  jnz     loc_1800790F7
0x180078fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180078fa8  lea     rsi, WPP_GLOBAL_Control
0x180078faf  mov     edi, 8007000Eh
0x180078fb4  cmp     rcx, rsi
0x180078fb7  jz      short loc_180078FDB
0x180078fb9  test    byte ptr [rcx+1Ch], 2
0x180078fbd  jz      short loc_180078FDB
0x180078fbf  cmp     byte ptr [rcx+19h], 2
0x180078fc3  jb      short loc_180078FDB
0x180078fc5  mov     rcx, [rcx+10h]
0x180078fc9  lea     edx, [rax+1Bh]
0x180078fcc  mov     r9d, edi
0x180078fcf  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180078fd6  call    WPP_SF_d
0x180078fdb  mov     rcx, [rbp+40h]; this
0x180078fdf  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078fe6  mov     r9d, edi; char *
0x180078fe9  mov     edx, 0B1h; void *
0x180078fee  mov     ebx, edi
0x180078ff0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ffc  cmp     rcx, rsi
0x180078fff  jz      loc_1800793D6
0x180079005  test    byte ptr [rcx+1Ch], 80h
0x180079009  jz      loc_1800793D6
0x18007900f  mov     edx, 1Ch
0x180079014  mov     r9d, 8007000Eh
0x18007901a  jmp     loc_1800793BF
0x18007901f  mov     rdx, rbx; String2
0x180079022  lea     rcx, aUrl; "url"
0x180079029  call    wcscmp_0
0x18007902e  test    eax, eax
0x180079030  jnz     loc_1800790C4
0x180079036  mov     rcx, [rbp+psz]; psz
0x18007903a  call    cs:__imp_SysAllocString
0x180079040  mov     r13, rax
0x180079043  test    rax, rax
0x180079046  jnz     loc_1800790EE
0x18007904c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079053  lea     rsi, WPP_GLOBAL_Control
0x18007905a  mov     edi, 8007000Eh
0x18007905f  cmp     rcx, rsi
0x180079062  jz      short loc_180079086
0x180079064  test    byte ptr [rcx+1Ch], 2
0x180079068  jz      short loc_180079086
0x18007906a  cmp     byte ptr [rcx+19h], 2
0x18007906e  jb      short loc_180079086
0x180079070  mov     rcx, [rcx+10h]
0x180079074  lea     edx, [rax+1Dh]
0x180079077  mov     r9d, edi
0x18007907a  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180079081  call    WPP_SF_d
0x180079086  mov     rcx, [rbp+40h]; this
0x18007908a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180079091  mov     r9d, edi; char *
0x180079094  mov     edx, 0BAh; void *
0x180079099  mov     ebx, edi
0x18007909b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800790a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800790a7  cmp     rcx, rsi
0x1800790aa  jz      loc_1800793D6
0x1800790b0  test    byte ptr [rcx+1Ch], 80h
0x1800790b4  jz      loc_1800793D6
0x1800790ba  mov     edx, 1Eh
0x1800790bf  jmp     loc_180079014
0x1800790c4  mov     rdx, rbx; String2
0x1800790c7  lea     rcx, aExp; "exp"
0x1800790ce  call    wcscmp_0
0x1800790d3  test    eax, eax
0x1800790d5  jnz     short loc_1800790EE
0x1800790d7  mov     rcx, [rbp+psz]; psz
0x1800790db  call    cs:__imp_SysAllocString
0x1800790e1  mov     [rbp+bstrString], rax
0x1800790e5  test    rax, rax
0x1800790e8  jz      loc_1800791A6
0x1800790ee  test    r12, r12
0x1800790f1  jz      loc_180078EEC
0x1800790f7  test    r13, r13
0x1800790fa  jz      loc_180078EEC
0x180079100  mov     rax, [rbp+bstrString]
0x180079104  test    rax, rax
0x180079107  jnz     loc_180079297
0x18007910d  jmp     loc_180078EEC
0x180079112  mov     rcx, [rbp+ppvObject]
0x180079116  lea     rdx, [rbp+String2]
0x18007911a  xor     r8d, r8d
  ... truncated ...
```
