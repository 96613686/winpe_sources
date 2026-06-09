# CDiscoveryStrategyDNSEmail::DiscoverURL(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180046970`
- end: `0x1800471e8`
- name: `?DiscoverURL@CDiscoveryStrategyDNSEmail@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `2168`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180046890`

## callees

- `0x1800044bf`
- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x1800208a8`
- `0x180020bf0`
- `0x18003b12c`
- `0x180046970`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470e0`
- `DNSAPI!DnsFree` at `0x18004719c`
- `DNSAPI!DnsFree` at `0x18004719c`
- `DNSAPI!DnsQuery_W` at `0x180046bd9`
- `DNSAPI!DnsQuery_W` at `0x180046bd9`
- `Normaliz!IdnToUnicode` at `0x180046f85`
- `Normaliz!IdnToUnicode` at `0x180046f85`
- `WININET!InternetCanonicalizeUrlW` at `0x180046d5f`
- `WININET!InternetCanonicalizeUrlW` at `0x180046d5f`
- `WININET!InternetCrackUrlW` at `0x180046e4f`
- `WININET!InternetCrackUrlW` at `0x180046e4f`
- `WININET!InternetCreateUrlW` at `0x180047085`
- `WININET!InternetCreateUrlW` at `0x180047085`

## pseudocode

```c
__int64 __fastcall CDiscoveryStrategyDNSEmail::DiscoverURL(__int64 a1, _QWORD *a2, __int64 a3)
{
  PVOID *v5; // r14
  __int64 v6; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rbx
  DNS_RECORDA *i; // rbx
  unsigned __int64 v10; // rbx
  __int64 v11; // r15
  __int64 v12; // rbx
  unsigned int v13; // eax
  const WCHAR *v14; // rax
  int W; // ebx
  unsigned int v16; // r14d
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  const WCHAR *pNameAdministrator; // rbx
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // eax
  signed int v29; // eax
  PVOID *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // r8
  signed int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // rax
  signed int LastError; // eax
  unsigned int v39; // ebx
  unsigned int v40; // eax
  signed int v41; // eax
  unsigned int v42; // eax
  __int16 v44; // [rsp+38h] [rbp-3610h] BYREF
  DWORD dwBufferLength; // [rsp+40h] [rbp-3608h] BYREF
  DWORD dwUrlLength; // [rsp+44h] [rbp-3604h] BYREF
  PDNS_RECORD ppQueryResults[3]; // [rsp+48h] [rbp-3600h] BYREF
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+60h] [rbp-35E8h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-3578h]
  _QWORD *v50; // [rsp+D8h] [rbp-3570h]
  _BYTE v51[32]; // [rsp+E0h] [rbp-3568h] BYREF
  WCHAR ASCIICharStr[264]; // [rsp+100h] [rbp-3548h] BYREF
  WCHAR UnicodeCharStr[264]; // [rsp+310h] [rbp-3338h] BYREF
  WCHAR v54[2088]; // [rsp+520h] [rbp-3128h] BYREF
  WCHAR szUrl[2088]; // [rsp+1570h] [rbp-20D8h] BYREF
  WCHAR szBuffer[2092]; // [rsp+25C0h] [rbp-1088h] BYREF

  v49 = -2;
  v50 = a2;
  std::wstring::wstring(v51);
  memset_0(UnicodeCharStr, 0, 0x208u);
  memset_0(v54, 0, 0x1048u);
  ppQueryResults[0] = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  memset_0(szUrl, 0, 0x1048u);
  memset_0(ASCIICharStr, 0, 0x208u);
  dwUrlLength = 2084;
  dwBufferLength = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
      CurrentThreadActivityIdPrefix,
      v6);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v44 = 64;
  v8 = a2[2];
  if ( !v8 )
    goto LABEL_96;
  for ( i = (DNS_RECORDA *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) + 2 * (v8 - 1));
        ;
        i = (DNS_RECORDA *)((char *)i - 2) )
  {
    ppQueryResults[1] = i;
    if ( LOWORD(i->pNext) == 64 && !(unsigned int)std::char_traits<unsigned short>::compare(i, &v44, 1) )
      break;
    if ( i == (DNS_RECORDA *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) )
      goto LABEL_96;
  }
  v10 = ((__int64)i - std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2)) >> 1;
  v11 = -1;
  if ( v10 == -1 || v10 >= a2[2] - 2LL )
  {
LABEL_96:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 2u )
    {
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
        v42,
        -2147220974);
    }
    W = -2147220974;
  }
  else
  {
    std::wstring::assign(v51, L"_msradc.");
    std::wstring::append(v51, a2, v10 + 1, -1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
        v13,
        v12);
    }
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    W = DnsQuery_W(v14, 0x10u, 0x1080u, 0, ppQueryResults, 0);
    if ( W )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( W > 0 )
          v16 = (unsigned __int16)W | 0x80070000;
        else
          v16 = W;
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids, v17, v16);
      }
      if ( W > 0 )
        W = (unsigned __int16)W | 0x80070000;
    }
    else if ( ppQueryResults[0] )
    {
      if ( ppQueryResults[0]->Data.A.IpAddress == 1 )
      {
        pNameAdministrator = (const WCHAR *)ppQueryResults[0]->Data.SOA.pNameAdministrator;
        std::wstring::assign(a3, pNameAdministrator);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
            v21,
            (__int64)pNameAdministrator);
        }
        dwBufferLength = 2084;
        if ( InternetCanonicalizeUrlW(pNameAdministrator, szBuffer, &dwBufferLength, 0) )
        {
          UrlComponents.dwStructSize = 104;
          UrlComponents.dwHostNameLength = 260;
          UrlComponents.lpszHostName = ASCIICharStr;
          UrlComponents.lpszUrlPath = v54;
          UrlComponents.dwUrlPathLength = 2084;
          UrlComponents.dwSchemeLength = 1;
          UrlComponents.dwUserNameLength = 1;
          UrlComponents.dwPasswordLength = 1;
          UrlComponents.dwExtraInfoLength = 1;
          if ( InternetCrackUrlW(szBuffer, 0, 0, &UrlComponents) )
          {
            v30 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v31 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                  v31,
                  (__int64)ASCIICharStr);
                v30 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 5u )
              {
                v32 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                  v32,
                  (__int64)v54);
              }
            }
            v33 = -1;
            do
              ++v33;
            while ( ASCIICharStr[v33] );
            dwBufferLength = v33;
            if ( IdnToUnicode(2u, ASCIICharStr, v33, UnicodeCharStr, 260) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v36 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  (unsigned int)WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                  v36,
                  (__int64)UnicodeCharStr);
              }
              UrlComponents.lpszHostName = UnicodeCharStr;
              v37 = -1;
              do
                ++v37;
              while ( UnicodeCharStr[v37] );
              UrlComponents.dwHostNameLength = v37;
              do
                ++v11;
              while ( v54[v11] );
              UrlComponents.dwUrlPathLength = v11;
              if ( InternetCreateUrlW(&UrlComponents, 0, szUrl, &dwUrlLength) )
              {
                std::wstring::assign(a3, szUrl);
                FeedSubscriptionTelemetry::_Type = 1;
                W = 0;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  LastError = GetLastError();
                  v39 = LastError;
                  if ( LastError > 0 )
                    v39 = (unsigned __int16)LastError | 0x80070000;
                  v40 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    23,
                    WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                    v40,
                    v39);
                }
                v41 = GetLastError();
                W = v41;
                if ( v41 > 0 )
                  W = (unsigned __int16)v41 | 0x80070000;
              }
            }
            else
            {
              v34 = GetLastError();
              W = v34;
              if ( v34 > 0 )
                W = (unsigned __int16)v34 | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v35 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                  v35,
                  W);
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v26 = GetLastError();
              v27 = v26;
              if ( v26 > 0 )
                v27 = (unsigned __int16)v26 | 0x80070000;
              v28 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
                v28,
                v27);
            }
            v29 = GetLastError();
            W = v29;
            if ( v29 > 0 )
              W = (unsigned __int16)v29 | 0x80070000;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v22 = GetLastError();
            v23 = v22;
            if ( v22 > 0 )
              v23 = (unsigned __int16)v22 | 0x80070000;
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
              v24,
              v23);
          }
          v25 = GetLastError();
          W = v25;
          if ( v25 > 0 )
            W = (unsigned __int16)v25 | 0x80070000;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
            v19,
            -2147220983);
        }
        W = -2147220983;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids,
          v18,
          -2147418113);
      }
      W = -2147418113;
    }
  }
  if ( ppQueryResults[0] )
    DnsFree(ppQueryResults[0], DnsFreeRecordList);
  std::wstring::~wstring(v51);
  std::wstring::~wstring(a2);
  return (unsigned int)W;
}

```

## disassembly

```asm
0x180046970  push    rdi
0x180046972  push    r12
0x180046974  push    r13
0x180046976  push    r14
0x180046978  push    r15
0x18004697a  mov     eax, 3620h
0x18004697f  call    _alloca_probe
0x180046984  sub     rsp, rax
0x180046987  mov     [rsp+3648h+var_3578], 0FFFFFFFFFFFFFFFEh
0x180046993  mov     [rsp+3648h+arg_0], rbx
0x18004699b  mov     [rsp+3648h+arg_18], rsi
0x1800469a3  mov     rax, cs:__security_cookie
0x1800469aa  xor     rax, rsp
0x1800469ad  mov     [rsp+3648h+var_30], rax
0x1800469b5  mov     r12, r8
0x1800469b8  mov     r13, rdx
0x1800469bb  mov     [rsp+3648h+var_3570], rdx
0x1800469c3  lea     rcx, [rsp+3648h+var_3568]
0x1800469cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800469d0  nop
0x1800469d1  mov     esi, 208h
0x1800469d6  mov     r8d, esi; Size
0x1800469d9  xor     edx, edx; Val
0x1800469db  lea     rcx, [rsp+3648h+UnicodeCharStr]; void *
0x1800469e3  call    memset_0
0x1800469e8  mov     ebx, 1048h
0x1800469ed  mov     r8d, ebx; Size
0x1800469f0  xor     edx, edx; Val
0x1800469f2  lea     rcx, [rsp+3648h+var_3128]; void *
0x1800469fa  call    memset_0
0x1800469ff  xor     edi, edi
0x180046a01  mov     [rsp+3648h+var_3600], rdi
0x180046a06  xor     edx, edx; Val
0x180046a08  lea     r8d, [rdi+68h]; Size
0x180046a0c  lea     rcx, [rsp+3648h+UrlComponents]; void *
0x180046a11  call    memset_0
0x180046a16  mov     r8d, ebx; Size
0x180046a19  xor     edx, edx; Val
0x180046a1b  lea     rcx, [rsp+3648h+szUrl]; void *
0x180046a23  call    memset_0
0x180046a28  mov     r8d, esi; Size
0x180046a2b  xor     edx, edx; Val
0x180046a2d  lea     rcx, [rsp+3648h+ASCIICharStr]; void *
0x180046a35  call    memset_0
0x180046a3a  mov     [rsp+3648h+dwUrlLength], 824h
0x180046a42  mov     [rsp+3648h+dwBufferLength], edi
0x180046a46  lea     rax, WPP_GLOBAL_Control
0x180046a4d  mov     r14, cs:WPP_GLOBAL_Control
0x180046a54  cmp     r14, rax
0x180046a57  jz      short loc_180046AA5
0x180046a59  test    byte ptr [r14+1Ch], 1
0x180046a5e  jz      short loc_180046AA5
0x180046a60  cmp     byte ptr [r14+19h], 4
0x180046a65  jb      short loc_180046AA5
0x180046a67  mov     rcx, r13
0x180046a6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046a6f  mov     rbx, rax
0x180046a72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046a77  lea     edx, [rdi+0Ah]
0x180046a7a  mov     [rsp+3648h+ppQueryResults], rbx
0x180046a7f  mov     r9d, eax
0x180046a82  lea     rsi, WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids
0x180046a89  mov     r8, rsi
0x180046a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a93  mov     rcx, [rcx+10h]
0x180046a97  call    WPP_SF_DS
0x180046a9c  mov     r14, cs:WPP_GLOBAL_Control
0x180046aa3  jmp     short loc_180046AAC
0x180046aa5  lea     rsi, WPP_adfbe14e098037e1f9877b60f0d7beaf_Traceguids
0x180046aac  mov     r15d, 40h ; '@'
0x180046ab2  mov     [rsp+3648h+var_3610], r15w
0x180046ab8  mov     rbx, [r13+10h]
0x180046abc  cmp     rbx, 1
0x180046ac0  jb      loc_180047132
0x180046ac6  mov     rcx, r13
0x180046ac9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046ace  dec     rbx
0x180046ad1  lea     rbx, [rax+rbx*2]
0x180046ad5  mov     [rsp+3648h+var_35F8], rbx
0x180046ada  cmp     [rbx], r15w
0x180046ade  jnz     loc_18004711C
0x180046ae4  mov     r8d, 1
0x180046aea  lea     rdx, [rsp+3648h+var_3610]
0x180046aef  mov     rcx, rbx
0x180046af2  call    ?compare@?$char_traits@G@std@@SAHPEBG0_K@Z; std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x180046af7  test    eax, eax
0x180046af9  jnz     loc_18004711C
0x180046aff  mov     rcx, r13
0x180046b02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046b07  sub     rbx, rax
0x180046b0a  sar     rbx, 1
0x180046b0d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180046b11  cmp     rbx, r15
0x180046b14  jz      loc_180047132
0x180046b1a  mov     rax, [r13+10h]
0x180046b1e  sub     rax, 2
0x180046b22  cmp     rbx, rax
0x180046b25  jnb     loc_180047132
0x180046b2b  lea     rdx, aMsradc; "_msradc."
0x180046b32  lea     rcx, [rsp+3648h+var_3568]
0x180046b3a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180046b3f  lea     r8, [rbx+1]
0x180046b43  mov     r9, r15
0x180046b46  mov     rdx, r13
0x180046b49  lea     rcx, [rsp+3648h+var_3568]
0x180046b51  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180046b56  mov     rax, cs:WPP_GLOBAL_Control
0x180046b5d  lea     r14, WPP_GLOBAL_Control
0x180046b64  cmp     rax, r14
0x180046b67  jz      short loc_180046BA9
0x180046b69  test    byte ptr [rax+1Ch], 1
0x180046b6d  jz      short loc_180046BA9
0x180046b6f  cmp     byte ptr [rax+19h], 4
0x180046b73  jb      short loc_180046BA9
0x180046b75  lea     rcx, [rsp+3648h+var_3568]
0x180046b7d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046b82  mov     rbx, rax
0x180046b85  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046b8a  lea     edx, [r15+0Dh]
0x180046b8e  mov     [rsp+3648h+ppQueryResults], rbx
0x180046b93  mov     r9d, eax
0x180046b96  mov     r8, rsi
0x180046b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ba0  mov     rcx, [rcx+10h]
0x180046ba4  call    WPP_SF_DS
0x180046ba9  mov     ebx, 10h
0x180046bae  lea     rcx, [rsp+3648h+var_3568]
0x180046bb6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046bbb  mov     rcx, rax; pszName
0x180046bbe  mov     [rsp+3648h+pReserved], rdi; pReserved
0x180046bc3  lea     rax, [rsp+3648h+var_3600]
0x180046bc8  mov     [rsp+3648h+ppQueryResults], rax; ppQueryResults
0x180046bcd  xor     r9d, r9d; pExtra
0x180046bd0  mov     r8d, 1080h; Options
0x180046bd6  movzx   edx, bx; wType
0x180046bd9  call    cs:__imp_DnsQuery_W
0x180046bdf  mov     ebx, eax
0x180046be1  test    eax, eax
0x180046be3  jz      short loc_180046C4C
0x180046be5  mov     rax, cs:WPP_GLOBAL_Control
0x180046bec  cmp     rax, r14
0x180046bef  jz      short loc_180046C36
0x180046bf1  test    byte ptr [rax+1Ch], 8
0x180046bf5  jz      short loc_180046C36
0x180046bf7  cmp     byte ptr [rax+19h], 2
0x180046bfb  jb      short loc_180046C36
0x180046bfd  test    ebx, ebx
0x180046bff  jg      short loc_180046C06
0x180046c01  mov     r14d, ebx
0x180046c04  jmp     short loc_180046C11
0x180046c06  movzx   r14d, bx
0x180046c0a  or      r14d, 80070000h
0x180046c11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046c16  mov     edx, 0Dh
0x180046c1b  mov     dword ptr [rsp+3648h+ppQueryResults], r14d
0x180046c20  mov     r9d, eax
0x180046c23  mov     r8, rsi
0x180046c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c2d  mov     rcx, [rcx+10h]
0x180046c31  call    WPP_SF_Dd
0x180046c36  test    ebx, ebx
0x180046c38  jle     short loc_180046C43
0x180046c3a  movzx   ebx, bx
0x180046c3d  or      ebx, 80070000h
0x180046c43  mov     [rsp+3648h+var_3618], ebx
0x180046c47  jmp     loc_18004718D
0x180046c4c  mov     rax, [rsp+3648h+var_3600]
0x180046c51  test    rax, rax
0x180046c54  jnz     short loc_180046CA4
0x180046c56  mov     rax, cs:WPP_GLOBAL_Control
0x180046c5d  cmp     rax, r14
0x180046c60  jz      short loc_180046C96
0x180046c62  test    byte ptr [rax+1Ch], 8
0x180046c66  jz      short loc_180046C96
0x180046c68  cmp     byte ptr [rax+19h], 2
0x180046c6c  jb      short loc_180046C96
0x180046c6e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046c73  mov     edx, 0Eh
0x180046c78  mov     dword ptr [rsp+3648h+ppQueryResults], 8000FFFFh
0x180046c80  mov     r9d, eax
0x180046c83  mov     r8, rsi
0x180046c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c8d  mov     rcx, [rcx+10h]
0x180046c91  call    WPP_SF_Dd
0x180046c96  mov     ebx, 8000FFFFh
0x180046c9b  mov     [rsp+3648h+var_3618], ebx
0x180046c9f  jmp     loc_18004718D
0x180046ca4  cmp     dword ptr [rax+20h], 1
0x180046ca8  jz      short loc_180046CF8
0x180046caa  mov     rax, cs:WPP_GLOBAL_Control
0x180046cb1  cmp     rax, r14
0x180046cb4  jz      short loc_180046CEA
0x180046cb6  test    byte ptr [rax+1Ch], 8
0x180046cba  jz      short loc_180046CEA
0x180046cbc  cmp     byte ptr [rax+19h], 2
0x180046cc0  jb      short loc_180046CEA
0x180046cc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046cc7  mov     edx, 0Fh
0x180046ccc  mov     dword ptr [rsp+3648h+ppQueryResults], 80040209h
0x180046cd4  mov     r9d, eax
0x180046cd7  mov     r8, rsi
0x180046cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ce1  mov     rcx, [rcx+10h]
0x180046ce5  call    WPP_SF_Dd
0x180046cea  mov     ebx, 80040209h
0x180046cef  mov     [rsp+3648h+var_3618], ebx
0x180046cf3  jmp     loc_18004718D
0x180046cf8  mov     rbx, [rax+28h]
0x180046cfc  mov     rdx, rbx
0x180046cff  mov     rcx, r12
0x180046d02  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180046d07  mov     rax, cs:WPP_GLOBAL_Control
0x180046d0e  cmp     rax, r14
0x180046d11  jz      short loc_180046D44
0x180046d13  test    byte ptr [rax+1Ch], 1
0x180046d17  jz      short loc_180046D44
0x180046d19  cmp     byte ptr [rax+19h], 5
0x180046d1d  jb      short loc_180046D44
0x180046d1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046d24  mov     edx, 10h
0x180046d29  mov     [rsp+3648h+ppQueryResults], rbx
0x180046d2e  mov     r9d, eax
0x180046d31  mov     r8, rsi
0x180046d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d3b  mov     rcx, [rcx+10h]
0x180046d3f  call    WPP_SF_DS
0x180046d44  mov     [rsp+3648h+dwBufferLength], 824h
0x180046d4c  xor     r9d, r9d; dwFlags
0x180046d4f  lea     r8, [rsp+3648h+dwBufferLength]; lpdwBufferLength
0x180046d54  lea     rdx, [rsp+3648h+szBuffer]; lpszBuffer
0x180046d5c  mov     rcx, rbx; lpszUrl
0x180046d5f  call    cs:__imp_InternetCanonicalizeUrlW
0x180046d65  test    eax, eax
0x180046d67  jnz     short loc_180046DD8
0x180046d69  mov     rax, cs:WPP_GLOBAL_Control
0x180046d70  cmp     rax, r14
0x180046d73  jz      short loc_180046DBA
0x180046d75  test    byte ptr [rax+1Ch], 8
0x180046d79  jz      short loc_180046DBA
0x180046d7b  cmp     byte ptr [rax+19h], 2
0x180046d7f  jb      short loc_180046DBA
0x180046d81  call    cs:__imp_GetLastError
0x180046d87  mov     ebx, eax
0x180046d89  test    eax, eax
0x180046d8b  jle     short loc_180046D96
0x180046d8d  movzx   ebx, ax
0x180046d90  or      ebx, 80070000h
0x180046d96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046d9b  mov     edx, 11h
0x180046da0  mov     dword ptr [rsp+3648h+ppQueryResults], ebx
0x180046da4  mov     r9d, eax
0x180046da7  mov     r8, rsi
0x180046daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180046db1  mov     rcx, [rcx+10h]
0x180046db5  call    WPP_SF_Dd
0x180046dba  call    cs:__imp_GetLastError
0x180046dc0  mov     ebx, eax
0x180046dc2  test    eax, eax
0x180046dc4  jle     short loc_180046DCF
0x180046dc6  movzx   ebx, ax
0x180046dc9  or      ebx, 80070000h
0x180046dcf  mov     [rsp+3648h+var_3618], ebx
0x180046dd3  jmp     loc_18004718D
0x180046dd8  mov     [rsp+3648h+UrlComponents.dwStructSize], 68h ; 'h'
0x180046de0  mov     ebx, 104h
0x180046de5  mov     [rsp+3648h+UrlComponents.dwHostNameLength], ebx
0x180046dec  lea     rax, [rsp+3648h+ASCIICharStr]
0x180046df4  mov     [rsp+3648h+UrlComponents.lpszHostName], rax
0x180046df9  lea     rax, [rsp+3648h+var_3128]
0x180046e01  mov     [rsp+3648h+UrlComponents.lpszUrlPath], rax
0x180046e09  mov     [rsp+3648h+UrlComponents.dwUrlPathLength], 824h
0x180046e14  mov     [rsp+3648h+UrlComponents.dwSchemeLength], 1
0x180046e1c  mov     [rsp+3648h+UrlComponents.dwUserNameLength], 1
0x180046e27  mov     [rsp+3648h+UrlComponents.dwPasswordLength], 1
0x180046e32  mov     [rsp+3648h+UrlComponents.dwExtraInfoLength], 1
0x180046e3d  lea     r9, [rsp+3648h+UrlComponents]; lpUrlComponents
0x180046e42  xor     r8d, r8d; dwFlags
0x180046e45  xor     edx, edx; dwUrlLength
0x180046e47  lea     rcx, [rsp+3648h+szBuffer]; lpszUrl
0x180046e4f  call    cs:__imp_InternetCrackUrlW
0x180046e55  test    eax, eax
0x180046e57  jnz     short loc_180046EC8
0x180046e59  mov     rax, cs:WPP_GLOBAL_Control
0x180046e60  cmp     rax, r14
0x180046e63  jz      short loc_180046EAA
0x180046e65  test    byte ptr [rax+1Ch], 8
0x180046e69  jz      short loc_180046EAA
0x180046e6b  cmp     byte ptr [rax+19h], 2
0x180046e6f  jb      short loc_180046EAA
0x180046e71  call    cs:__imp_GetLastError
0x180046e77  mov     ebx, eax
0x180046e79  test    eax, eax
0x180046e7b  jle     short loc_180046E86
0x180046e7d  movzx   ebx, ax
0x180046e80  or      ebx, 80070000h
0x180046e86  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046e8b  mov     edx, 12h
0x180046e90  mov     dword ptr [rsp+3648h+ppQueryResults], ebx
0x180046e94  mov     r9d, eax
0x180046e97  mov     r8, rsi
  ... truncated ...
```
