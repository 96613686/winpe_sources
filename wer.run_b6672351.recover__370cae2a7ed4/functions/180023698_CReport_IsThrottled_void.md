# CReport::IsThrottled(void)

- ea: `0x180023698`
- end: `0x180023a23`
- name: `?IsThrottled@CReport@@QEAAHXZ`
- size: `907`
- prototype: `__int64 __fastcall(CReport *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f718`
- `0x18004aba8`

## callees

- `0x180009f9c`
- `0x18000cf50`
- `0x18000d554`
- `0x18000db80`
- `0x18000e31c`
- `0x1800201f0`
- `0x180020680`
- `0x180023698`
- `0x180023abc`
- `0x180023c28`
- `0x1800a3fa8`
- `0x1800a7ac8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800237df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800237df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023958`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023958`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800238da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002393a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800238da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002393a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002399a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002399a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023880`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023880`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReport::IsThrottled(CReport *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // r14d
  int v5; // esi
  int AllArgumentsAsString; // r15d
  __int64 v7; // r14
  __int64 i; // rsi
  int v9; // eax
  HKEY *phkResult; // rax
  enum THROTTLE_NAMESPACE_LEVEL *pvData; // [rsp+28h] [rbp-D8h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v17; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR v18[5]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v19[4]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v20; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v21; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v22; // [rsp+100h] [rbp+0h] BYREF
  enum THROTTLE_NAMESPACE_LEVEL *v23; // [rsp+120h] [rbp+20h]
  _BYTE v24[120]; // [rsp+128h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+1B0h] [rbp+B0h] BYREF
  int v26; // [rsp+1B4h] [rbp+B4h]
  unsigned int v27; // [rsp+1B8h] [rbp+B8h] BYREF
  int v28; // [rsp+1C0h] [rbp+C0h] BYREF
  int v29; // [rsp+1C8h] [rbp+C8h] BYREF

  v2 = 0;
  v26 = 0;
  v14 = 0;
  v27 = 0;
  pcbData = 0;
  SystemTimeAsFileTime = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  hkey = 0;
  CTpNamespaceTree::CTpNamespaceTree((CTpNamespaceTree *)v19);
  if ( *((_DWORD *)this + 1468) == 4 )
    v3 = COCATpTransport::CopyNamespaceInformation((struct CTpNamespaceTree *)v19, this);
  else
    v3 = CWatsonTpTransport::CopyNamespaceInformation((struct CTpNamespaceTree *)v19, this);
  if ( v3 >= 0 )
  {
    v4 = 0;
    v28 = 0;
    v5 = 0;
    v29 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v18);
    AllArgumentsAsString = CTpNamespaceTree::GetAllArgumentsAsString(v19, v18);
    if ( AllArgumentsAsString >= 0 )
    {
      LODWORD(pvData) = (_DWORD)v23;
      AllArgumentsAsString = CTpThrottlingSamplingStore::GetThrottleState(
                               v19[0],
                               v20,
                               v21,
                               v22,
                               v18[0],
                               pvData,
                               &v28,
                               &v29);
      v4 = v28;
      v5 = v29;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v18);
    if ( AllArgumentsAsString >= 0 )
    {
      if ( v4 || v5 )
      {
        v2 = 1;
        goto LABEL_32;
      }
      v2 = 0;
    }
  }
  if ( *((_DWORD *)this + 1468) == 3 )
  {
LABEL_12:
    v2 = 0;
  }
  else
  {
    v7 = *((_QWORD *)this + 70);
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      if ( !(unsigned int)_o__wcsicmp(v7, off_1800B5138[i]) )
        goto LABEL_12;
    }
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           lpSubKey,
           L"%s\\%s\\%s",
           L"Software\\Microsoft\\Windows\\Windows Error Reporting",
           L"Throttling",
           v7);
    if ( v9 >= 0 )
    {
      phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0x20119u, phkResult) )
      {
        if ( hkey )
        {
          pcbData = 8;
          if ( !RegGetValueW(hkey, 0, L"LastTime", 0x48u, 0, &v14, &pcbData) && pcbData == 8 )
          {
            pcbData = 4;
            if ( !RegGetValueW(hkey, 0, L"Duration", 0x18u, 0, &v27, &pcbData) && pcbData == 4 )
            {
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              if ( v27 == -1 || v14 + 10000000 * (unsigned __int64)v27 > *(_QWORD *)&SystemTimeAsFileTime )
              {
                v2 = 1;
              }
              else
              {
                v2 = 0;
                RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
              }
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        293,
        WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
        (unsigned int)v9);
    }
  }
LABEL_32:
  CTpArgumentSet::~CTpArgumentSet((CTpArgumentSet *)v24);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v22);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v21);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v20);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v19);
  if ( hkey )
    RegCloseKey(hkey);
  if ( (char *)lpSubKey[0] != &v17 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpSubKey[0]);
  return v2;
}

```

## disassembly

```asm
0x180023698  push    rbp
0x18002369a  push    rbx
0x18002369b  push    rsi
0x18002369c  push    rdi
0x18002369d  push    r14
0x18002369f  push    r15
0x1800236a1  lea     rbp, [rsp-78h]
0x1800236a6  sub     rsp, 178h
0x1800236ad  mov     rdi, rcx
0x1800236b0  xor     ebx, ebx
0x1800236b2  mov     qword ptr [rbp+0A0h+arg_0], rbx
0x1800236b9  mov     [rsp+1A0h+var_158], rbx
0x1800236be  mov     [rbp+0A0h+arg_8], ebx
0x1800236c4  mov     [rbp+0A0h+arg_0], ebx
0x1800236ca  mov     qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800236cf  lea     rcx, [rsp+1A0h+lpSubKey]; void *
0x1800236d4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800236d9  nop
0x1800236da  mov     [rsp+1A0h+hkey], rbx
0x1800236df  lea     rcx, [rbp+0A0h+var_100]; this
0x1800236e3  call    ??0CTpNamespaceTree@@QEAA@XZ; CTpNamespaceTree::CTpNamespaceTree(void)
0x1800236e8  nop
0x1800236e9  mov     rdx, rdi; struct CReport *
0x1800236ec  lea     rcx, [rbp+0A0h+var_100]; this
0x1800236f0  cmp     dword ptr [rdi+16F0h], 4
0x1800236f7  jnz     short loc_180023700
0x1800236f9  call    ?CopyNamespaceInformation@COCATpTransport@@SAJPEAVCTpNamespaceTree@@PEAVCReport@@@Z; COCATpTransport::CopyNamespaceInformation(CTpNamespaceTree *,CReport *)
0x1800236fe  jmp     short loc_180023705
0x180023700  call    ?CopyNamespaceInformation@CWatsonTpTransport@@SAJPEAVCTpNamespaceTree@@PEAVCReport@@@Z; CWatsonTpTransport::CopyNamespaceInformation(CTpNamespaceTree *,CReport *)
0x180023705  test    eax, eax
0x180023707  js      loc_1800237A6
0x18002370d  xor     r14d, r14d
0x180023710  mov     [rbp+0A0h+arg_10], r14d
0x180023717  xor     esi, esi
0x180023719  mov     [rbp+0A0h+arg_18], esi
0x18002371f  lea     rcx, [rsp+1A0h+var_128]; void *
0x180023724  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180023729  lea     rdx, [rsp+1A0h+var_128]
0x18002372e  lea     rcx, [rbp+0A0h+var_100]
0x180023732  call    ?GetAllArgumentsAsString@CTpNamespaceTree@@QEBAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpNamespaceTree::GetAllArgumentsAsString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180023737  mov     r15d, eax
0x18002373a  test    eax, eax
0x18002373c  js      short loc_18002378C
0x18002373e  mov     eax, dword ptr [rbp+0A0h+var_80]
0x180023741  mov     rdx, [rsp+1A0h+var_128]
0x180023746  lea     rcx, [rbp+0A0h+arg_18]
0x18002374d  mov     [rsp+1A0h+var_168], rcx; int *
0x180023752  lea     rcx, [rbp+0A0h+arg_10]
0x180023759  mov     [rsp+1A0h+pcbData], rcx; int *
0x18002375e  mov     dword ptr [rsp+1A0h+pvData], eax; enum THROTTLE_NAMESPACE_LEVEL *
0x180023762  mov     [rsp+1A0h+phkResult], rdx; LPCWSTR
0x180023767  mov     r9, [rbp+0A0h+var_A0]; wchar_t *
0x18002376b  mov     r8, [rbp+0A0h+var_C0]; wchar_t *
0x18002376f  mov     rdx, [rbp+0A0h+var_E0]; wchar_t *
0x180023773  mov     rcx, [rbp+0A0h+var_100]; wchar_t *
0x180023777  call    ?GetThrottleState@CTpThrottlingSamplingStore@@SAJPEB_W0000HPEAH1@Z; CTpThrottlingSamplingStore::GetThrottleState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *,int *)
0x18002377c  mov     r15d, eax
0x18002377f  mov     r14d, [rbp+0A0h+arg_10]
0x180023786  mov     esi, [rbp+0A0h+arg_18]
0x18002378c  lea     rcx, [rsp+1A0h+var_128]; void *
0x180023791  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180023796  test    r15d, r15d
0x180023799  js      short loc_1800237A6
0x18002379b  test    r14d, r14d
0x18002379e  jnz     short loc_1800237B6
0x1800237a0  test    esi, esi
0x1800237a2  jnz     short loc_1800237B6
0x1800237a4  xor     ebx, ebx
0x1800237a6  cmp     dword ptr [rdi+16F0h], 3
0x1800237ad  jnz     short loc_1800237C0
0x1800237af  xor     ebx, ebx
0x1800237b1  jmp     loc_1800239A7
0x1800237b6  mov     ebx, 1
0x1800237bb  jmp     loc_1800239A7
0x1800237c0  mov     r14, [rdi+230h]
0x1800237c7  xor     esi, esi
0x1800237c9  lea     edi, [rsi+1]
0x1800237cc  cmp     esi, 2
0x1800237cf  jnb     short loc_1800237F3
0x1800237d1  lea     rax, off_1800B5138; "APPCRASH"
0x1800237d8  mov     rdx, [rax+rsi*8]
0x1800237dc  mov     rcx, r14
0x1800237df  call    cs:__imp__o__wcsicmp
0x1800237e6  nop     dword ptr [rax+rax+00h]
0x1800237eb  test    eax, eax
0x1800237ed  jz      short loc_1800237AF
0x1800237ef  add     esi, edi
0x1800237f1  jmp     short loc_1800237CC
0x1800237f3  mov     [rsp+1A0h+phkResult], r14
0x1800237f8  lea     r9, aThrottling; "Throttling"
0x1800237ff  lea     r8, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x180023806  lea     rdx, aSSS; "%s\\%s\\%s"
0x18002380d  lea     rcx, [rsp+1A0h+lpSubKey]
0x180023812  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180023817  test    eax, eax
0x180023819  jns     short loc_180023859
0x18002381b  lea     rdx, WPP_GLOBAL_Control
0x180023822  mov     rcx, cs:WPP_GLOBAL_Control
0x180023829  cmp     rcx, rdx
0x18002382c  jz      loc_1800239A7
0x180023832  test    [rcx+1Ch], dil
0x180023836  jz      loc_1800239A7
0x18002383c  mov     edx, 125h
0x180023841  mov     r9d, eax
0x180023844  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18002384b  mov     rcx, [rcx+10h]
0x18002384f  call    WPP_SF_d
0x180023854  jmp     loc_1800239A7
0x180023859  lea     rcx, [rsp+1A0h+hkey]
0x18002385e  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180023863  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180023868  mov     r9d, 20119h; samDesired
0x18002386e  xor     r8d, r8d; ulOptions
0x180023871  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x180023876  mov     rsi, 0FFFFFFFF80000001h
0x18002387d  mov     rcx, rsi; hKey
0x180023880  call    cs:__imp_RegOpenKeyExW
0x180023887  nop     dword ptr [rax+rax+00h]
0x18002388c  test    eax, eax
0x18002388e  jnz     loc_1800239A7
0x180023894  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180023899  test    rcx, rcx
0x18002389c  jz      loc_1800239A7
0x1800238a2  mov     [rbp+0A0h+arg_0], 8
0x1800238ac  lea     rax, [rbp+0A0h+arg_0]
0x1800238b3  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800238b8  lea     rax, [rsp+1A0h+var_158]
0x1800238bd  mov     [rsp+1A0h+pvData], rax; pvData
0x1800238c2  mov     [rsp+1A0h+phkResult], 0; pdwType
0x1800238cb  mov     r9d, 48h ; 'H'; dwFlags
0x1800238d1  lea     r8, aLasttime; "LastTime"
0x1800238d8  xor     edx, edx; lpSubKey
0x1800238da  call    cs:__imp_RegGetValueW
0x1800238e1  nop     dword ptr [rax+rax+00h]
0x1800238e6  test    eax, eax
0x1800238e8  jnz     loc_1800239A7
0x1800238ee  cmp     [rbp+0A0h+arg_0], 8
0x1800238f5  jnz     loc_1800239A7
0x1800238fb  mov     [rbp+0A0h+arg_0], 4
0x180023905  lea     rax, [rbp+0A0h+arg_0]
0x18002390c  mov     [rsp+1A0h+pcbData], rax; pcbData
0x180023911  lea     rax, [rbp+0A0h+arg_8]
0x180023918  mov     [rsp+1A0h+pvData], rax; pvData
0x18002391d  mov     [rsp+1A0h+phkResult], 0; pdwType
0x180023926  mov     r9d, 18h; dwFlags
0x18002392c  lea     r8, aDuration; "Duration"
0x180023933  xor     edx, edx; lpSubKey
0x180023935  mov     rcx, [rsp+1A0h+hkey]; hkey
0x18002393a  call    cs:__imp_RegGetValueW
0x180023941  nop     dword ptr [rax+rax+00h]
0x180023946  test    eax, eax
0x180023948  jnz     short loc_1800239A7
0x18002394a  cmp     [rbp+0A0h+arg_0], 4
0x180023951  jnz     short loc_1800239A7
0x180023953  lea     rcx, [rsp+1A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180023958  call    cs:__imp_GetSystemTimeAsFileTime
0x18002395f  nop     dword ptr [rax+rax+00h]
0x180023964  cmp     [rbp+0A0h+arg_8], 0FFFFFFFFh
0x18002396b  jnz     short loc_180023971
0x18002396d  mov     ebx, edi
0x18002396f  jmp     short loc_1800239A7
0x180023971  mov     eax, [rbp+0A0h+arg_8]
0x180023977  imul    rcx, rax, 989680h
0x18002397e  add     rcx, [rsp+1A0h+var_158]
0x180023983  cmp     rcx, qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime]
0x180023988  ja      short loc_18002396D
0x18002398a  xor     ebx, ebx
0x18002398c  xor     r9d, r9d; Reserved
0x18002398f  xor     r8d, r8d; samDesired
0x180023992  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x180023997  mov     rcx, rsi; hKey
0x18002399a  call    cs:__imp_RegDeleteKeyExW
0x1800239a1  nop     dword ptr [rax+rax+00h]
0x1800239a6  nop
0x1800239a7  lea     rcx, [rbp+0A0h+var_78]; this
0x1800239ab  call    ??1CTpArgumentSet@@UEAA@XZ; CTpArgumentSet::~CTpArgumentSet(void)
0x1800239b0  lea     rcx, [rbp+0A0h+var_A0]; void *
0x1800239b4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800239b9  lea     rcx, [rbp+0A0h+var_C0]; void *
0x1800239bd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800239c2  lea     rcx, [rbp+0A0h+var_E0]; void *
0x1800239c6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800239cb  lea     rcx, [rbp+0A0h+var_100]; void *
0x1800239cf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800239d4  nop
0x1800239d5  mov     rcx, [rsp+1A0h+hkey]; hKey
0x1800239da  test    rcx, rcx
0x1800239dd  jz      short loc_1800239EC
0x1800239df  call    cs:__imp_RegCloseKey
0x1800239e6  nop     dword ptr [rax+rax+00h]
0x1800239eb  nop
0x1800239ec  lea     rax, [rsp+1A0h+var_138]
0x1800239f1  mov     r8, [rsp+1A0h+lpSubKey]; lpMem
0x1800239f6  cmp     r8, rax
0x1800239f9  jz      short loc_180023A10
0x1800239fb  xor     edx, edx; dwFlags
0x1800239fd  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180023a04  call    cs:__imp_HeapFree
0x180023a0b  nop     dword ptr [rax+rax+00h]
0x180023a10  mov     eax, ebx
0x180023a12  add     rsp, 178h
0x180023a19  pop     r15
0x180023a1b  pop     r14
0x180023a1d  pop     rdi
0x180023a1e  pop     rsi
0x180023a1f  pop     rbx
0x180023a20  pop     rbp
0x180023a21  retn
```
