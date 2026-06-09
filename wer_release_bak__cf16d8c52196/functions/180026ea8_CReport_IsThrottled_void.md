# CReport::IsThrottled(void)

- ea: `0x180026ea8`
- end: `0x180027202`
- name: `?IsThrottled@CReport@@QEAAHXZ`
- size: `858`
- prototype: `__int64 __fastcall(CReport *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb2c`
- `0x18004892c`

## callees

- `0x180008e94`
- `0x18000bc10`
- `0x18000c110`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000eb3c`
- `0x18001f8c8`
- `0x18001fe24`
- `0x180026ea8`
- `0x180027294`
- `0x18009f594`
- `0x1800a2ef4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026fef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026fef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800271ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800271ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180027150`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180027150`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027138`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027138`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002718c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002718c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800271cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800271cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002708a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002708a`

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
      if ( !(unsigned int)_o__wcsicmp(v7, off_1800B0140[i]) )
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
        292,
        WPP_6898268820d636d20e115db2eaa75970_Traceguids,
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
0x180026ea8  push    rbp
0x180026eaa  push    rbx
0x180026eab  push    rsi
0x180026eac  push    rdi
0x180026ead  push    r14
0x180026eaf  push    r15
0x180026eb1  lea     rbp, [rsp-78h]
0x180026eb6  sub     rsp, 178h
0x180026ebd  mov     rdi, rcx
0x180026ec0  xor     ebx, ebx
0x180026ec2  mov     qword ptr [rbp+0A0h+arg_0], rbx
0x180026ec9  mov     [rsp+1A0h+var_158], rbx
0x180026ece  mov     [rbp+0A0h+arg_8], ebx
0x180026ed4  mov     [rbp+0A0h+arg_0], ebx
0x180026eda  mov     qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180026edf  lea     rcx, [rsp+1A0h+lpSubKey]; void *
0x180026ee4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180026ee9  nop
0x180026eea  mov     [rsp+1A0h+hkey], rbx
0x180026eef  lea     rcx, [rbp+0A0h+var_100]; this
0x180026ef3  call    ??0CTpNamespaceTree@@QEAA@XZ; CTpNamespaceTree::CTpNamespaceTree(void)
0x180026ef8  nop
0x180026ef9  mov     rdx, rdi; struct CReport *
0x180026efc  lea     rcx, [rbp+0A0h+var_100]; this
0x180026f00  cmp     dword ptr [rdi+16F0h], 4
0x180026f07  jnz     short loc_180026F10
0x180026f09  call    ?CopyNamespaceInformation@COCATpTransport@@SAJPEAVCTpNamespaceTree@@PEAVCReport@@@Z; COCATpTransport::CopyNamespaceInformation(CTpNamespaceTree *,CReport *)
0x180026f0e  jmp     short loc_180026F15
0x180026f10  call    ?CopyNamespaceInformation@CWatsonTpTransport@@SAJPEAVCTpNamespaceTree@@PEAVCReport@@@Z; CWatsonTpTransport::CopyNamespaceInformation(CTpNamespaceTree *,CReport *)
0x180026f15  test    eax, eax
0x180026f17  js      loc_180026FB6
0x180026f1d  xor     r14d, r14d
0x180026f20  mov     [rbp+0A0h+arg_10], r14d
0x180026f27  xor     esi, esi
0x180026f29  mov     [rbp+0A0h+arg_18], esi
0x180026f2f  lea     rcx, [rsp+1A0h+var_128]; void *
0x180026f34  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180026f39  lea     rdx, [rsp+1A0h+var_128]
0x180026f3e  lea     rcx, [rbp+0A0h+var_100]
0x180026f42  call    ?GetAllArgumentsAsString@CTpNamespaceTree@@QEBAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpNamespaceTree::GetAllArgumentsAsString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180026f47  mov     r15d, eax
0x180026f4a  test    eax, eax
0x180026f4c  js      short loc_180026F9C
0x180026f4e  mov     eax, dword ptr [rbp+0A0h+var_80]
0x180026f51  mov     rdx, [rsp+1A0h+var_128]
0x180026f56  lea     rcx, [rbp+0A0h+arg_18]
0x180026f5d  mov     [rsp+1A0h+var_168], rcx; int *
0x180026f62  lea     rcx, [rbp+0A0h+arg_10]
0x180026f69  mov     [rsp+1A0h+pcbData], rcx; int *
0x180026f6e  mov     dword ptr [rsp+1A0h+pvData], eax; enum THROTTLE_NAMESPACE_LEVEL *
0x180026f72  mov     [rsp+1A0h+phkResult], rdx; LPCWSTR
0x180026f77  mov     r9, [rbp+0A0h+var_A0]; wchar_t *
0x180026f7b  mov     r8, [rbp+0A0h+var_C0]; wchar_t *
0x180026f7f  mov     rdx, [rbp+0A0h+var_E0]; wchar_t *
0x180026f83  mov     rcx, [rbp+0A0h+var_100]; wchar_t *
0x180026f87  call    ?GetThrottleState@CTpThrottlingSamplingStore@@SAJPEB_W0000HPEAH1@Z; CTpThrottlingSamplingStore::GetThrottleState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *,int *)
0x180026f8c  mov     r15d, eax
0x180026f8f  mov     r14d, [rbp+0A0h+arg_10]
0x180026f96  mov     esi, [rbp+0A0h+arg_18]
0x180026f9c  lea     rcx, [rsp+1A0h+var_128]; void *
0x180026fa1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180026fa6  test    r15d, r15d
0x180026fa9  js      short loc_180026FB6
0x180026fab  test    r14d, r14d
0x180026fae  jnz     short loc_180026FC6
0x180026fb0  test    esi, esi
0x180026fb2  jnz     short loc_180026FC6
0x180026fb4  xor     ebx, ebx
0x180026fb6  cmp     dword ptr [rdi+16F0h], 3
0x180026fbd  jnz     short loc_180026FD0
0x180026fbf  xor     ebx, ebx
0x180026fc1  jmp     loc_180027193
0x180026fc6  mov     ebx, 1
0x180026fcb  jmp     loc_180027193
0x180026fd0  mov     r14, [rdi+230h]
0x180026fd7  xor     esi, esi
0x180026fd9  lea     edi, [rsi+1]
0x180026fdc  cmp     esi, 2
0x180026fdf  jnb     short loc_180026FFD
0x180026fe1  lea     rax, off_1800B0140; "APPCRASH"
0x180026fe8  mov     rdx, [rax+rsi*8]
0x180026fec  mov     rcx, r14
0x180026fef  call    cs:__imp__o__wcsicmp
0x180026ff5  test    eax, eax
0x180026ff7  jz      short loc_180026FBF
0x180026ff9  add     esi, edi
0x180026ffb  jmp     short loc_180026FDC
0x180026ffd  mov     [rsp+1A0h+phkResult], r14
0x180027002  lea     r9, aThrottling; "Throttling"
0x180027009  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x180027010  lea     rdx, aSSS; "%s\\%s\\%s"
0x180027017  lea     rcx, [rsp+1A0h+lpSubKey]
0x18002701c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180027021  test    eax, eax
0x180027023  jns     short loc_180027063
0x180027025  lea     rdx, WPP_GLOBAL_Control
0x18002702c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027033  cmp     rcx, rdx
0x180027036  jz      loc_180027193
0x18002703c  test    [rcx+1Ch], dil
0x180027040  jz      loc_180027193
0x180027046  mov     edx, 124h
0x18002704b  mov     r9d, eax
0x18002704e  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180027055  mov     rcx, [rcx+10h]
0x180027059  call    WPP_SF_d
0x18002705e  jmp     loc_180027193
0x180027063  lea     rcx, [rsp+1A0h+hkey]
0x180027068  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002706d  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180027072  mov     r9d, 20119h; samDesired
0x180027078  xor     r8d, r8d; ulOptions
0x18002707b  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x180027080  mov     rsi, 0FFFFFFFF80000001h
0x180027087  mov     rcx, rsi; hKey
0x18002708a  call    cs:__imp_RegOpenKeyExW
0x180027090  test    eax, eax
0x180027092  jnz     loc_180027193
0x180027098  mov     rcx, [rsp+1A0h+hkey]; hkey
0x18002709d  test    rcx, rcx
0x1800270a0  jz      loc_180027193
0x1800270a6  mov     [rbp+0A0h+arg_0], 8
0x1800270b0  lea     rax, [rbp+0A0h+arg_0]
0x1800270b7  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800270bc  lea     rax, [rsp+1A0h+var_158]
0x1800270c1  mov     [rsp+1A0h+pvData], rax; pvData
0x1800270c6  mov     [rsp+1A0h+phkResult], 0; pdwType
0x1800270cf  mov     r9d, 48h ; 'H'; dwFlags
0x1800270d5  lea     r8, aLasttime; "LastTime"
0x1800270dc  xor     edx, edx; lpSubKey
0x1800270de  call    cs:__imp_RegGetValueW
0x1800270e4  test    eax, eax
0x1800270e6  jnz     loc_180027193
0x1800270ec  cmp     [rbp+0A0h+arg_0], 8
0x1800270f3  jnz     loc_180027193
0x1800270f9  mov     [rbp+0A0h+arg_0], 4
0x180027103  lea     rax, [rbp+0A0h+arg_0]
0x18002710a  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18002710f  lea     rax, [rbp+0A0h+arg_8]
0x180027116  mov     [rsp+1A0h+pvData], rax; pvData
0x18002711b  mov     [rsp+1A0h+phkResult], 0; pdwType
0x180027124  mov     r9d, 18h; dwFlags
0x18002712a  lea     r8, aDuration; "Duration"
0x180027131  xor     edx, edx; lpSubKey
0x180027133  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180027138  call    cs:__imp_RegGetValueW
0x18002713e  test    eax, eax
0x180027140  jnz     short loc_180027193
0x180027142  cmp     [rbp+0A0h+arg_0], 4
0x180027149  jnz     short loc_180027193
0x18002714b  lea     rcx, [rsp+1A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027150  call    cs:__imp_GetSystemTimeAsFileTime
0x180027156  cmp     [rbp+0A0h+arg_8], 0FFFFFFFFh
0x18002715d  jnz     short loc_180027163
0x18002715f  mov     ebx, edi
0x180027161  jmp     short loc_180027193
0x180027163  mov     eax, [rbp+0A0h+arg_8]
0x180027169  imul    rcx, rax, 989680h
0x180027170  add     rcx, [rsp+1A0h+var_158]
0x180027175  cmp     rcx, qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18002717a  ja      short loc_18002715F
0x18002717c  xor     ebx, ebx
0x18002717e  xor     r9d, r9d; Reserved
0x180027181  xor     r8d, r8d; samDesired
0x180027184  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x180027189  mov     rcx, rsi; hKey
0x18002718c  call    cs:__imp_RegDeleteKeyExW
0x180027192  nop
0x180027193  lea     rcx, [rbp+0A0h+var_78]; this
0x180027197  call    ??1CTpArgumentSet@@UEAA@XZ; CTpArgumentSet::~CTpArgumentSet(void)
0x18002719c  lea     rcx, [rbp+0A0h+var_A0]; void *
0x1800271a0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800271a5  lea     rcx, [rbp+0A0h+var_C0]; void *
0x1800271a9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800271ae  lea     rcx, [rbp+0A0h+var_E0]; void *
0x1800271b2  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800271b7  lea     rcx, [rbp+0A0h+var_100]; void *
0x1800271bb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800271c0  nop
0x1800271c1  mov     rcx, [rsp+1A0h+hkey]; hKey
0x1800271c6  test    rcx, rcx
0x1800271c9  jz      short loc_1800271D2
0x1800271cb  call    cs:__imp_RegCloseKey
0x1800271d1  nop
0x1800271d2  lea     rax, [rsp+1A0h+var_138]
0x1800271d7  mov     r8, [rsp+1A0h+lpSubKey]; lpMem
0x1800271dc  cmp     r8, rax
0x1800271df  jz      short loc_1800271F0
0x1800271e1  xor     edx, edx; dwFlags
0x1800271e3  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800271ea  call    cs:__imp_HeapFree
0x1800271f0  mov     eax, ebx
0x1800271f2  add     rsp, 178h
0x1800271f9  pop     r15
0x1800271fb  pop     r14
0x1800271fd  pop     rdi
0x1800271fe  pop     rsi
0x1800271ff  pop     rbx
0x180027200  pop     rbp
0x180027201  retn
```
