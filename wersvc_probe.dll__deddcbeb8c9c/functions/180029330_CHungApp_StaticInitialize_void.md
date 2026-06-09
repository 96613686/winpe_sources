# CHungApp::StaticInitialize(void)

- ea: `0x180029330`
- end: `0x180029687`
- name: `?StaticInitialize@CHungApp@@SAJXZ`
- size: `855`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180025b0c`

## callees

- `0x180006134`
- `0x180006a80`
- `0x180011ef8`
- `0x180029330`
- `0x18002bf44`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180029501`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180029501`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029348`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002943f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002952c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002943f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002952c`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180029435`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180029522`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180029435`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180029522`

## pseudocode

```c
__int64 CHungApp::StaticInitialize(void)
{
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 result; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int SystemWow64Directory2W; // eax
  signed int v9; // eax
  HKEY v10; // rcx
  unsigned int v11; // eax
  signed int v12; // eax
  HKEY v13; // rcx
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(&CHungApp::ms_systemPath, 0x104u);
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v4 = 104;
    goto LABEL_7;
  }
  if ( SystemDirectoryW > 0x104 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2147942522LL;
    v7 = 105;
LABEL_42:
    WPP_SF_(v6[2], v7, &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids);
    return 2147942522LL;
  }
  v2 = StringCchPrintfW(&CHungApp::ms_exePath, 0x104u, L"%s\\werfault.exe", &CHungApp::ms_systemPath);
  if ( (v2 & 0x80000000) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v4 = 106;
LABEL_7:
    WPP_SF_d(v3[2], v4, &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, v2);
    return v2;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  SystemWow64Directory2W = GetSystemWow64Directory2W(&CHungApp::ms_systemPath32, 260);
  if ( !SystemWow64Directory2W )
  {
    v9 = GetLastError();
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v4 = 107;
    goto LABEL_7;
  }
  if ( SystemWow64Directory2W > 0x104 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2147942522LL;
    v7 = 108;
    goto LABEL_42;
  }
  v2 = StringCchPrintfW(&CHungApp::ms_exePath32, 0x104u, L"%s\\werfault.exe", &CHungApp::ms_systemPath32);
  if ( (v2 & 0x80000000) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v4 = 109;
    goto LABEL_7;
  }
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 12 )
  {
    v11 = GetSystemWow64Directory2W(&CHungApp::ms_systemPathArm32, 260);
    if ( !v11 )
    {
      v12 = GetLastError();
      v2 = v12;
      if ( v12 > 0 )
        v2 = (unsigned __int16)v12 | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v2;
      v4 = 110;
      goto LABEL_7;
    }
    if ( v11 > 0x104 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 2147942522LL;
      v7 = 111;
      goto LABEL_42;
    }
    v2 = StringCchPrintfW(&CHungApp::ms_exePathArm32, 0x104u, L"%s\\werfault.exe", &CHungApp::ms_systemPathArm32);
    if ( (v2 & 0x80000000) != 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v2;
      v4 = 112;
      goto LABEL_7;
    }
  }
  CHungApp::ms_shortTerminationTimeout = ReadDwordCheckBounds(v10, L"TerminationTimeout", 0x2710u, 0x3E8u, 0x36EE80u);
  CHungApp::ms_longTerminationTimeout = ReadDwordCheckBounds(v13, L"LongTerminationTimeout", 0xEA60u, 0x3E8u, 0x36EE80u);
  CHungApp::ms_shortTerminationTimeoutFT = (struct _FILETIME)(-10000LL * CHungApp::ms_shortTerminationTimeout);
  result = 0;
  CHungApp::ms_longTerminationTimeoutFT = (struct _FILETIME)(-10000LL * CHungApp::ms_longTerminationTimeout);
  return result;
}

```

## disassembly

```asm
0x180029330  mov     [rsp+arg_0], rbx
0x180029335  push    rdi
0x180029336  sub     rsp, 60h
0x18002933a  mov     edi, 104h
0x18002933f  lea     rcx, ?ms_systemPath@CHungApp@@0PA_WA; lpBuffer
0x180029346  mov     edx, edi; uSize
0x180029348  call    cs:__imp_GetSystemDirectoryW
0x18002934e  test    eax, eax
0x180029350  jnz     short loc_18002939F
0x180029352  call    cs:__imp_GetLastError
0x180029358  mov     ebx, eax
0x18002935a  test    eax, eax
0x18002935c  jle     short loc_180029367
0x18002935e  movzx   ebx, ax
0x180029361  or      ebx, 80070000h
0x180029367  mov     rcx, cs:WPP_GLOBAL_Control
0x18002936e  lea     rax, WPP_GLOBAL_Control
0x180029375  cmp     rcx, rax
0x180029378  jz      short loc_180029398
0x18002937a  test    byte ptr [rcx+1Ch], 1
0x18002937e  jz      short loc_180029398
0x180029380  mov     edx, 68h ; 'h'
0x180029385  mov     rcx, [rcx+10h]
0x180029389  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x180029390  mov     r9d, ebx
0x180029393  call    WPP_SF_d
0x180029398  mov     eax, ebx
0x18002939a  jmp     loc_18002967C
0x18002939f  cmp     eax, edi
0x1800293a1  jbe     short loc_1800293CE
0x1800293a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293aa  lea     rax, WPP_GLOBAL_Control
0x1800293b1  cmp     rcx, rax
0x1800293b4  jz      loc_18002959E
0x1800293ba  test    byte ptr [rcx+1Ch], 1
0x1800293be  jz      loc_18002959E
0x1800293c4  mov     edx, 69h ; 'i'
0x1800293c9  jmp     loc_18002958E
0x1800293ce  lea     r9, ?ms_systemPath@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPath
0x1800293d5  mov     rdx, rdi; unsigned __int64
0x1800293d8  lea     r8, aSWerfaultExe; "%s\\werfault.exe"
0x1800293df  lea     rcx, ?ms_exePath@CHungApp@@0PA_WA; wchar_t *
0x1800293e6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800293eb  mov     ebx, eax
0x1800293ed  test    eax, eax
0x1800293ef  jns     short loc_180029414
0x1800293f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293f8  lea     rax, WPP_GLOBAL_Control
0x1800293ff  cmp     rcx, rax
0x180029402  jz      short loc_180029398
0x180029404  test    byte ptr [rcx+1Ch], 1
0x180029408  jz      short loc_180029398
0x18002940a  mov     edx, 6Ah ; 'j'
0x18002940f  jmp     loc_180029385
0x180029414  xorps   xmm0, xmm0
0x180029417  lea     rcx, ?ms_systemPath32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPath32
0x18002941e  mov     r8d, 14Ch
0x180029424  mov     edx, edi
0x180029426  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x18002942b  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180029430  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x180029435  call    cs:__imp_GetSystemWow64Directory2W
0x18002943b  test    eax, eax
0x18002943d  jnz     short loc_18002947F
0x18002943f  call    cs:__imp_GetLastError
0x180029445  mov     ebx, eax
0x180029447  test    eax, eax
0x180029449  jle     short loc_180029454
0x18002944b  movzx   ebx, ax
0x18002944e  or      ebx, 80070000h
0x180029454  mov     rcx, cs:WPP_GLOBAL_Control
0x18002945b  lea     rax, WPP_GLOBAL_Control
0x180029462  cmp     rcx, rax
0x180029465  jz      loc_180029398
0x18002946b  test    byte ptr [rcx+1Ch], 1
0x18002946f  jz      loc_180029398
0x180029475  mov     edx, 6Bh ; 'k'
0x18002947a  jmp     loc_180029385
0x18002947f  cmp     eax, edi
0x180029481  jbe     short loc_1800294AE
0x180029483  mov     rcx, cs:WPP_GLOBAL_Control
0x18002948a  lea     rax, WPP_GLOBAL_Control
0x180029491  cmp     rcx, rax
0x180029494  jz      loc_18002959E
0x18002949a  test    byte ptr [rcx+1Ch], 1
0x18002949e  jz      loc_18002959E
0x1800294a4  mov     edx, 6Ch ; 'l'
0x1800294a9  jmp     loc_18002958E
0x1800294ae  lea     r9, ?ms_systemPath32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPath32
0x1800294b5  mov     rdx, rdi; unsigned __int64
0x1800294b8  lea     r8, aSWerfaultExe; "%s\\werfault.exe"
0x1800294bf  lea     rcx, ?ms_exePath32@CHungApp@@0PA_WA; wchar_t *
0x1800294c6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800294cb  mov     ebx, eax
0x1800294cd  test    eax, eax
0x1800294cf  jns     short loc_1800294FC
0x1800294d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294d8  lea     rax, WPP_GLOBAL_Control
0x1800294df  cmp     rcx, rax
0x1800294e2  jz      loc_180029398
0x1800294e8  test    byte ptr [rcx+1Ch], 1
0x1800294ec  jz      loc_180029398
0x1800294f2  mov     edx, 6Dh ; 'm'
0x1800294f7  jmp     loc_180029385
0x1800294fc  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x180029501  call    cs:__imp_GetSystemInfo
0x180029507  cmp     word ptr [rsp+68h+SystemInfo], 0Ch
0x18002950d  jnz     loc_1800295F6
0x180029513  mov     r8d, 1C4h
0x180029519  lea     rcx, ?ms_systemPathArm32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPathArm32
0x180029520  mov     edx, edi
0x180029522  call    cs:__imp_GetSystemWow64Directory2W
0x180029528  test    eax, eax
0x18002952a  jnz     short loc_18002956C
0x18002952c  call    cs:__imp_GetLastError
0x180029532  mov     ebx, eax
0x180029534  test    eax, eax
0x180029536  jle     short loc_180029541
0x180029538  movzx   ebx, ax
0x18002953b  or      ebx, 80070000h
0x180029541  mov     rcx, cs:WPP_GLOBAL_Control
0x180029548  lea     rax, WPP_GLOBAL_Control
0x18002954f  cmp     rcx, rax
0x180029552  jz      loc_180029398
0x180029558  test    byte ptr [rcx+1Ch], 1
0x18002955c  jz      loc_180029398
0x180029562  mov     edx, 6Eh ; 'n'
0x180029567  jmp     loc_180029385
0x18002956c  cmp     eax, edi
0x18002956e  jbe     short loc_1800295A8
0x180029570  mov     rcx, cs:WPP_GLOBAL_Control
0x180029577  lea     rax, WPP_GLOBAL_Control
0x18002957e  cmp     rcx, rax
0x180029581  jz      short loc_18002959E
0x180029583  test    byte ptr [rcx+1Ch], 1
0x180029587  jz      short loc_18002959E
0x180029589  mov     edx, 6Fh ; 'o'
0x18002958e  mov     rcx, [rcx+10h]
0x180029592  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x180029599  call    WPP_SF_
0x18002959e  mov     eax, 8007007Ah
0x1800295a3  jmp     loc_18002967C
0x1800295a8  lea     r9, ?ms_systemPathArm32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPathArm32
0x1800295af  mov     rdx, rdi; unsigned __int64
0x1800295b2  lea     r8, aSWerfaultExe; "%s\\werfault.exe"
0x1800295b9  lea     rcx, ?ms_exePathArm32@CHungApp@@0PA_WA; wchar_t *
0x1800295c0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800295c5  mov     ebx, eax
0x1800295c7  test    eax, eax
0x1800295c9  jns     short loc_1800295F6
0x1800295cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295d2  lea     rax, WPP_GLOBAL_Control
0x1800295d9  cmp     rcx, rax
0x1800295dc  jz      loc_180029398
0x1800295e2  test    byte ptr [rcx+1Ch], 1
0x1800295e6  jz      loc_180029398
0x1800295ec  mov     edx, 70h ; 'p'
0x1800295f1  jmp     loc_180029385
0x1800295f6  mov     ebx, 3E8h
0x1800295fb  lea     rdx, aTerminationtim; "TerminationTimeout"
0x180029602  mov     edi, 36EE80h
0x180029607  mov     r9d, ebx; unsigned int
0x18002960a  mov     r8d, 2710h; unsigned int
0x180029610  mov     [rsp+68h+var_48], edi; unsigned int
0x180029614  call    ?ReadDwordCheckBounds@@YAKPEAUHKEY__@@PEB_WKKK@Z; ReadDwordCheckBounds(HKEY__ *,wchar_t const *,ulong,ulong,ulong)
0x180029619  mov     r9d, ebx; unsigned int
0x18002961c  mov     cs:?ms_shortTerminationTimeout@CHungApp@@0KA, eax; ulong CHungApp::ms_shortTerminationTimeout
0x180029622  mov     r8d, 0EA60h; unsigned int
0x180029628  mov     [rsp+68h+var_48], edi; unsigned int
0x18002962c  lea     rdx, aLongterminatio; "LongTerminationTimeout"
0x180029633  call    ?ReadDwordCheckBounds@@YAKPEAUHKEY__@@PEB_WKKK@Z; ReadDwordCheckBounds(HKEY__ *,wchar_t const *,ulong,ulong,ulong)
0x180029638  mov     ecx, eax
0x18002963a  mov     eax, cs:?ms_shortTerminationTimeout@CHungApp@@0KA; ulong CHungApp::ms_shortTerminationTimeout
0x180029640  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180029647  mov     cs:?ms_longTerminationTimeout@CHungApp@@0KA, ecx; ulong CHungApp::ms_longTerminationTimeout
0x18002964d  mov     rdx, rax
0x180029650  mov     cs:?ms_shortTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A.dwLowDateTime, eax; _FILETIME CHungApp::ms_shortTerminationTimeoutFT ...
0x180029656  imul    rcx, 0FFFFFFFFFFFFD8F0h
0x18002965d  shr     rdx, 20h
0x180029661  mov     rax, rcx
0x180029664  mov     cs:?ms_shortTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A.dwHighDateTime, edx; _FILETIME CHungApp::ms_shortTerminationTimeoutFT ...
0x18002966a  shr     rax, 20h
0x18002966e  mov     cs:?ms_longTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A.dwHighDateTime, eax; _FILETIME CHungApp::ms_longTerminationTimeoutFT ...
0x180029674  xor     eax, eax
0x180029676  mov     cs:?ms_longTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A.dwLowDateTime, ecx; _FILETIME CHungApp::ms_longTerminationTimeoutFT ...
0x18002967c  mov     rbx, [rsp+68h+arg_0]
0x180029681  add     rsp, 60h
0x180029685  pop     rdi
0x180029686  retn
```
