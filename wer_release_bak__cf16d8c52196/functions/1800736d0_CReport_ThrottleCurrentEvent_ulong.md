# CReport::ThrottleCurrentEvent(ulong)

- ea: `0x1800736d0`
- end: `0x1800739ba`
- name: `?ThrottleCurrentEvent@CReport@@QEAAJK@Z`
- size: `746`
- prototype: `__int64 __fastcall(CReport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024998`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18001fe24`
- `0x1800736d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073776`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073776`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073873`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073873`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073856`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073919`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073919`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800738c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073939`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800738c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073939`

## pseudocode

```c
__int64 __fastcall CReport::ThrottleCurrentEvent(CReport *this, int a2)
{
  bool v4; // zf
  int v5; // ebx
  __int64 v6; // rsi
  __int64 i; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+28h] BYREF
  int v17; // [rsp+A8h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+38h] BYREF
  struct _FILETIME Data; // [rsp+B8h] [rbp+40h] BYREF

  SystemTimeAsFileTime = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v4 = *((_DWORD *)this + 1468) == 3;
  hKey = 0;
  Data = 0;
  v17 = a2;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 293, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    goto LABEL_5;
  }
  v6 = *((_QWORD *)this + 70);
  if ( (unsigned int)(a2 - 315360001) <= 0xED33FCFD )
    v17 = 315360000;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 2 )
    {
      v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpSubKey,
             L"%s\\%s\\%s",
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"Throttling",
             *((_QWORD *)this + 70));
      if ( v5 >= 0 )
      {
        phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0x20106u, 0, phkResult, 0);
        if ( Key || !hKey )
        {
          v5 = ERROR_HR_FROM_WIN32(Key);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_34;
          v9 = 296;
        }
        else
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          Data = SystemTimeAsFileTime;
          v12 = RegSetValueExW(hKey, L"LastTime", 0, 0xBu, (const BYTE *)&Data, 8u);
          if ( v12 )
          {
            v5 = ERROR_HR_FROM_WIN32(v12);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 297;
          }
          else
          {
            v13 = RegSetValueExW(hKey, L"Duration", 0, 4u, (const BYTE *)&v17, 4u);
            if ( !v13 )
            {
              v5 = 0;
              goto LABEL_34;
            }
            v5 = ERROR_HR_FROM_WIN32(v13);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 298;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v9 = 295;
      }
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_6898268820d636d20e115db2eaa75970_Traceguids, (unsigned int)v5);
      goto LABEL_34;
    }
    if ( !(unsigned int)_o__wcsicmp(v6, off_1800B0140[i]) )
      break;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v6);
LABEL_5:
  v5 = -2147019873;
LABEL_34:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800736d0  push    rbp
0x1800736d2  push    rbx
0x1800736d3  push    rsi
0x1800736d4  push    rdi
0x1800736d5  mov     rbp, rsp
0x1800736d8  sub     rsp, 78h
0x1800736dc  mov     rdi, rcx
0x1800736df  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800736e7  lea     rcx, [rbp+lpSubKey]; void *
0x1800736eb  mov     ebx, edx
0x1800736ed  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800736f2  cmp     dword ptr [rdi+16F0h], 3
0x1800736f9  mov     [rbp+hKey], 0
0x180073701  mov     [rbp+Data], 0
0x180073709  mov     [rbp+arg_8], ebx
0x18007370c  jnz     short loc_180073746
0x18007370e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073715  lea     rax, WPP_GLOBAL_Control
0x18007371c  cmp     rcx, rax
0x18007371f  jz      short loc_18007373C
0x180073721  test    byte ptr [rcx+1Ch], 1
0x180073725  jz      short loc_18007373C
0x180073727  mov     rcx, [rcx+10h]
0x18007372b  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073732  mov     edx, 125h
0x180073737  call    WPP_SF_
0x18007373c  mov     ebx, 8007139Fh
0x180073741  jmp     loc_18007399D
0x180073746  mov     rsi, [rdi+230h]
0x18007374d  lea     eax, [rbx-12CC0301h]
0x180073753  cmp     eax, 0ED33FCFDh
0x180073758  ja      short loc_180073761
0x18007375a  mov     [rbp+arg_8], 12CC0300h
0x180073761  xor     ebx, ebx
0x180073763  cmp     ebx, 2
0x180073766  jnb     short loc_1800737B7
0x180073768  lea     rax, off_1800B0140; "APPCRASH"
0x18007376f  mov     rcx, rsi
0x180073772  mov     rdx, [rax+rbx*8]
0x180073776  call    cs:__imp__o__wcsicmp
0x18007377c  test    eax, eax
0x18007377e  jz      short loc_180073784
0x180073780  inc     ebx
0x180073782  jmp     short loc_180073763
0x180073784  mov     rcx, cs:WPP_GLOBAL_Control
0x18007378b  lea     rax, WPP_GLOBAL_Control
0x180073792  cmp     rcx, rax
0x180073795  jz      short loc_18007373C
0x180073797  test    byte ptr [rcx+1Ch], 1
0x18007379b  jz      short loc_18007373C
0x18007379d  mov     rcx, [rcx+10h]
0x1800737a1  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x1800737a8  mov     edx, 126h
0x1800737ad  mov     r9, rsi
0x1800737b0  call    WPP_SF_S
0x1800737b5  jmp     short loc_18007373C
0x1800737b7  mov     rax, [rdi+230h]
0x1800737be  lea     r9, aThrottling; "Throttling"
0x1800737c5  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x1800737cc  mov     qword ptr [rsp+78h+dwOptions], rax
0x1800737d1  lea     rdx, aSSS; "%s\\%s\\%s"
0x1800737d8  lea     rcx, [rbp+lpSubKey]
0x1800737dc  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800737e1  mov     ebx, eax
0x1800737e3  test    eax, eax
0x1800737e5  jns     short loc_180073812
0x1800737e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800737ee  lea     rax, WPP_GLOBAL_Control
0x1800737f5  cmp     rcx, rax
0x1800737f8  jz      loc_18007399D
0x1800737fe  test    byte ptr [rcx+1Ch], 1
0x180073802  jz      loc_18007399D
0x180073808  mov     edx, 127h
0x18007380d  jmp     loc_18007398A
0x180073812  lea     rcx, [rbp+hKey]
0x180073816  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18007381b  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18007381f  mov     rdi, 0FFFFFFFF80000001h
0x180073826  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18007382f  xor     r9d, r9d; lpClass
0x180073832  mov     [rsp+78h+phkResult], rax; phkResult
0x180073837  xor     r8d, r8d; Reserved
0x18007383a  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180073843  mov     rcx, rdi; hKey
0x180073846  mov     [rsp+78h+samDesired], 20106h; samDesired
0x18007384e  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180073856  call    cs:__imp_RegCreateKeyExW
0x18007385c  test    eax, eax
0x18007385e  jnz     loc_180073963
0x180073864  cmp     [rbp+hKey], 0
0x180073869  jz      loc_180073963
0x18007386f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073873  call    cs:__imp_GetSystemTimeAsFileTime
0x180073879  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007387d  lea     rdx, aLasttime; "LastTime"
0x180073884  mov     rcx, [rbp+hKey]; hKey
0x180073888  mov     r9d, 0Bh; dwType
0x18007388e  mov     [rbp+Data], rax
0x180073892  xor     r8d, r8d; Reserved
0x180073895  lea     rax, [rbp+Data]
0x180073899  mov     [rsp+78h+samDesired], 8; cbData
0x1800738a1  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800738a6  call    cs:__imp_RegSetValueExW
0x1800738ac  test    eax, eax
0x1800738ae  jz      short loc_1800738F7
0x1800738b0  mov     ecx, eax; unsigned int
0x1800738b2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800738b7  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800738bb  mov     rcx, rdi; hKey
0x1800738be  xor     r9d, r9d; Reserved
0x1800738c1  xor     r8d, r8d; samDesired
0x1800738c4  mov     ebx, eax
0x1800738c6  call    cs:__imp_RegDeleteKeyExW
0x1800738cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800738d3  lea     rax, WPP_GLOBAL_Control
0x1800738da  cmp     rcx, rax
0x1800738dd  jz      loc_18007399D
0x1800738e3  test    byte ptr [rcx+1Ch], 1
0x1800738e7  jz      loc_18007399D
0x1800738ed  mov     edx, 129h
0x1800738f2  jmp     loc_18007398A
0x1800738f7  mov     rcx, [rbp+hKey]; hKey
0x1800738fb  lea     rax, [rbp+arg_8]
0x1800738ff  mov     r9d, 4; dwType
0x180073905  lea     rdx, aDuration; "Duration"
0x18007390c  mov     [rsp+78h+samDesired], r9d; cbData
0x180073911  xor     r8d, r8d; Reserved
0x180073914  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180073919  call    cs:__imp_RegSetValueExW
0x18007391f  test    eax, eax
0x180073921  jz      short loc_18007395F
0x180073923  mov     ecx, eax; unsigned int
0x180073925  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007392a  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18007392e  mov     rcx, rdi; hKey
0x180073931  xor     r9d, r9d; Reserved
0x180073934  xor     r8d, r8d; samDesired
0x180073937  mov     ebx, eax
0x180073939  call    cs:__imp_RegDeleteKeyExW
0x18007393f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073946  lea     rax, WPP_GLOBAL_Control
0x18007394d  cmp     rcx, rax
0x180073950  jz      short loc_18007399D
0x180073952  test    byte ptr [rcx+1Ch], 1
0x180073956  jz      short loc_18007399D
0x180073958  mov     edx, 12Ah
0x18007395d  jmp     short loc_18007398A
0x18007395f  xor     ebx, ebx
0x180073961  jmp     short loc_18007399D
0x180073963  mov     ecx, eax; unsigned int
0x180073965  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007396a  mov     ebx, eax
0x18007396c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073973  lea     rax, WPP_GLOBAL_Control
0x18007397a  cmp     rcx, rax
0x18007397d  jz      short loc_18007399D
0x18007397f  test    byte ptr [rcx+1Ch], 1
0x180073983  jz      short loc_18007399D
0x180073985  mov     edx, 128h
0x18007398a  mov     rcx, [rcx+10h]
0x18007398e  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073995  mov     r9d, ebx
0x180073998  call    WPP_SF_d
0x18007399d  lea     rcx, [rbp+hKey]
0x1800739a1  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800739a6  lea     rcx, [rbp+lpSubKey]; void *
0x1800739aa  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800739af  mov     eax, ebx
0x1800739b1  add     rsp, 78h
0x1800739b5  pop     rdi
0x1800739b6  pop     rsi
0x1800739b7  pop     rbx
0x1800739b8  pop     rbp
0x1800739b9  retn
```
