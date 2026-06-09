# CEventThrottle::ReportDroppedIfNeeded(void)

- ea: `0x18000d0dc`
- end: `0x18000d2ef`
- name: `?ReportDroppedIfNeeded@CEventThrottle@@QEAAXXZ`
- size: `531`
- prototype: `void __fastcall(CEventThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d49c`

## callees

- `0x180001770`
- `0x180003714`
- `0x18000d000`
- `0x18000d0dc`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000d27b`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000d27b`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000d2cd`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000d2cd`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000d2c4`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000d2c4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d1ee`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d1ee`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d208`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d208`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18000d236`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18000d236`

## string_xrefs

- `0x18000d25c`: `Windows Search Service`

## pseudocode

```c
void __fastcall CEventThrottle::ReportDroppedIfNeeded(CEventThrottle *this)
{
  int v2; // eax
  bool v3; // di
  __int64 v4; // rax
  int TimeFormatW; // eax
  bool v6; // dl
  HANDLE v7; // rbx
  FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE LocalTime[20]; // [rsp+58h] [rbp-A8h] BYREF
  int v10; // [rsp+6Ch] [rbp-94h]
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR Strings[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v13[16]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v14[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR TimeStr[128]; // [rsp+E0h] [rbp-20h] BYREF

  if ( *(_DWORD *)this == 2 && *((int *)this + 4) > 0 )
  {
    v2 = *((_DWORD *)this + 5);
    memset(LocalTime, 0, sizeof(LocalTime));
    v10 = v2;
    if ( !CEventThrottle::Load(
            (CEventThrottle *)LocalTime,
            L"Software\\Microsoft\\Windows Search\\Tracing\\EventThrottleLastReported")
      || *(_DWORD *)LocalTime != *(_DWORD *)this
      || *(_QWORD *)&LocalTime[4] != *(_QWORD *)((char *)this + 4)
      || *(_DWORD *)&LocalTime[16] != *((_DWORD *)this + 4) )
    {
      v3 = (int)StringCchPrintfW(v13, 0x10u, L"%u", *((unsigned int *)this + 5)) >= 0
        && (int)StringCchPrintfW(v14, 0x10u, L"%d", *((unsigned int *)this + 4)) >= 0;
      SystemTime = 0;
      *(_OWORD *)LocalTime = 0;
      if ( v3 )
      {
        v4 = 10000LL * *(_QWORD *)((char *)this + 4);
        FileTime.dwLowDateTime = 10000 * *((_DWORD *)this + 1);
        FileTime.dwHighDateTime = HIDWORD(v4);
        if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
        {
          if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, (LPSYSTEMTIME)LocalTime) )
          {
            TimeFormatW = GetTimeFormatW(0x800u, 0, (const SYSTEMTIME *)LocalTime, 0, TimeStr, 128);
            v6 = 0;
            if ( TimeFormatW > 0 )
              v6 = v3;
            if ( v6 )
            {
              Strings[0] = &qword_180011360;
              Strings[1] = v13;
              Strings[2] = v14;
              Strings[3] = TimeStr;
              v7 = RegisterEventSourceW(0, L"Windows Search Service");
              if ( v7 )
              {
                ReportEventW(v7, 2u, 1u, 0x800003F7, 0, 4u, 0, Strings, 0);
                DeregisterEventSource(v7);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000d0dc  push    rbp
0x18000d0de  push    rbx
0x18000d0df  push    rdi
0x18000d0e0  push    r14
0x18000d0e2  lea     rbp, [rsp-0F8h]
0x18000d0ea  sub     rsp, 1F8h
0x18000d0f1  mov     rax, cs:__security_cookie
0x18000d0f8  xor     rax, rsp
0x18000d0fb  mov     [rbp+110h+var_30], rax
0x18000d102  cmp     dword ptr [rcx], 2
0x18000d105  mov     rbx, rcx
0x18000d108  jnz     loc_18000D2D3
0x18000d10e  cmp     dword ptr [rcx+10h], 0
0x18000d112  jle     loc_18000D2D3
0x18000d118  mov     eax, [rcx+14h]
0x18000d11b  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows Search\\Tr"...
0x18000d122  lea     rcx, [rsp+210h+LocalTime]; this
0x18000d127  mov     dword ptr [rsp+210h+LocalTime], 0
0x18000d12f  mov     qword ptr [rsp+210h+LocalTime+4], 0
0x18000d138  mov     qword ptr [rsp+210h+LocalTime+0Ch], 0
0x18000d141  mov     [rsp+210h+var_1A4], eax
0x18000d145  call    ?Load@CEventThrottle@@QEAA_NPEB_W@Z; CEventThrottle::Load(wchar_t const *)
0x18000d14a  test    al, al
0x18000d14c  jz      short loc_18000D16E
0x18000d14e  mov     eax, [rbx]
0x18000d150  cmp     dword ptr [rsp+210h+LocalTime], eax
0x18000d154  jnz     short loc_18000D16E
0x18000d156  mov     rax, [rbx+4]
0x18000d15a  cmp     qword ptr [rsp+210h+LocalTime+4], rax
0x18000d15f  jnz     short loc_18000D16E
0x18000d161  mov     eax, [rbx+10h]
0x18000d164  cmp     dword ptr [rsp+210h+LocalTime+10h], eax
0x18000d168  jz      loc_18000D2D3
0x18000d16e  mov     r9d, [rbx+14h]
0x18000d172  lea     r8, aU; "%u"
0x18000d179  mov     edi, 10h
0x18000d17e  lea     rcx, [rbp+110h+var_170]; wchar_t *
0x18000d182  mov     edx, edi; unsigned __int64
0x18000d184  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000d189  lea     r14d, [rdi-0Fh]
0x18000d18d  test    eax, eax
0x18000d18f  jns     short loc_18000D196
0x18000d191  xor     dil, dil
0x18000d194  jmp     short loc_18000D1B7
0x18000d196  mov     r9d, [rbx+10h]
0x18000d19a  lea     r8, aD; "%d"
0x18000d1a1  mov     rdx, rdi; unsigned __int64
0x18000d1a4  lea     rcx, [rbp+110h+var_150]; wchar_t *
0x18000d1a8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000d1ad  xor     ecx, ecx
0x18000d1af  mov     edi, r14d
0x18000d1b2  test    eax, eax
0x18000d1b4  cmovs   edi, ecx
0x18000d1b7  xorps   xmm0, xmm0
0x18000d1ba  xorps   xmm1, xmm1
0x18000d1bd  movups  xmmword ptr [rsp+210h+SystemTime.wYear], xmm0
0x18000d1c2  movups  xmmword ptr [rsp+210h+LocalTime], xmm1
0x18000d1c7  test    dil, dil
0x18000d1ca  jz      loc_18000D2D3
0x18000d1d0  imul    rax, [rbx+4], 2710h
0x18000d1d8  lea     rdx, [rsp+210h+SystemTime]; lpSystemTime
0x18000d1dd  mov     [rsp+210h+FileTime.dwLowDateTime], eax
0x18000d1e1  lea     rcx, [rsp+210h+FileTime]; lpFileTime
0x18000d1e6  shr     rax, 20h
0x18000d1ea  mov     [rsp+210h+FileTime.dwHighDateTime], eax
0x18000d1ee  call    cs:__imp_FileTimeToSystemTime
0x18000d1f4  test    eax, eax
0x18000d1f6  jz      loc_18000D2D3
0x18000d1fc  lea     r8, [rsp+210h+LocalTime]; lpLocalTime
0x18000d201  xor     ecx, ecx; lpTimeZoneInformation
0x18000d203  lea     rdx, [rsp+210h+SystemTime]; lpUniversalTime
0x18000d208  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000d20e  test    eax, eax
0x18000d210  jz      loc_18000D2D3
0x18000d216  lea     rax, [rbp+110h+TimeStr]
0x18000d21a  mov     [rsp+210h+cchTime], 80h; cchTime
0x18000d222  xor     r9d, r9d; lpFormat
0x18000d225  mov     [rsp+210h+lpTimeStr], rax; lpTimeStr
0x18000d22a  lea     r8, [rsp+210h+LocalTime]; lpTime
0x18000d22f  xor     edx, edx; dwFlags
0x18000d231  mov     ecx, 800h; Locale
0x18000d236  call    cs:__imp_GetTimeFormatW
0x18000d23c  xor     edx, edx
0x18000d23e  movzx   ecx, dil
0x18000d242  test    eax, eax
0x18000d244  cmovg   edx, ecx
0x18000d247  test    dl, dl
0x18000d249  jz      loc_18000D2D3
0x18000d24f  lea     rax, qword_180011360
0x18000d256  xor     ecx, ecx; lpUNCServerName
0x18000d258  mov     [rbp+110h+Strings], rax
0x18000d25c  lea     rdx, aWindowsSearchS_0; "Windows Search Service"
0x18000d263  lea     rax, [rbp+110h+var_170]
0x18000d267  mov     [rbp+110h+var_188], rax
0x18000d26b  lea     rax, [rbp+110h+var_150]
0x18000d26f  mov     [rbp+110h+var_180], rax
0x18000d273  lea     rax, [rbp+110h+TimeStr]
0x18000d277  mov     [rbp+110h+var_178], rax
0x18000d27b  call    cs:__imp_RegisterEventSourceW
0x18000d281  mov     rbx, rax
0x18000d284  test    rax, rax
0x18000d287  jz      short loc_18000D2D3
0x18000d289  mov     [rsp+210h+lpRawData], 0; lpRawData
0x18000d292  lea     rax, [rbp+110h+Strings]
0x18000d296  mov     [rsp+210h+lpStrings], rax; lpStrings
0x18000d29b  mov     r8d, r14d; wCategory
0x18000d29e  mov     [rsp+210h+dwDataSize], 0; dwDataSize
0x18000d2a6  mov     edx, 2; wType
0x18000d2ab  mov     word ptr [rsp+210h+cchTime], 4; wNumStrings
0x18000d2b2  mov     r9d, 800003F7h; dwEventID
0x18000d2b8  mov     rcx, rbx; hEventLog
0x18000d2bb  mov     [rsp+210h+lpTimeStr], 0; lpUserSid
0x18000d2c4  call    cs:__imp_ReportEventW
0x18000d2ca  mov     rcx, rbx; hEventLog
0x18000d2cd  call    cs:__imp_DeregisterEventSource
0x18000d2d3  mov     rcx, [rbp+110h+var_30]
0x18000d2da  xor     rcx, rsp; StackCookie
0x18000d2dd  call    __security_check_cookie
0x18000d2e2  add     rsp, 1F8h
0x18000d2e9  pop     r14
0x18000d2eb  pop     rdi
0x18000d2ec  pop     rbx
0x18000d2ed  pop     rbp
0x18000d2ee  retn
```
