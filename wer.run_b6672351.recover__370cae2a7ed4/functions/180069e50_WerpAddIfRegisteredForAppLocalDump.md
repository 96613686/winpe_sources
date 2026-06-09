# WerpAddIfRegisteredForAppLocalDump

- ea: `0x180069e50`
- end: `0x18006a02f`
- name: `WerpAddIfRegisteredForAppLocalDump`
- size: `479`
- prototype: `__int64 __fastcall(void *, HANDLE ProcessHandle)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x18001e0d0`
- `0x1800256e0`
- `0x180042f00`
- `0x180045e58`
- `0x18004c134`
- `0x180053300`
- `0x180064728`
- `0x180069e50`
- `0x18009c110`
- `0x1800a8770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f3b`
- `ntdll!wcsstr` at `0x180069f98`
- `ntdll!wcsstr` at `0x180069f98`
- `USERENV!GetAppContainerFolderPath` at `0x180069f5d`
- `USERENV!GetAppContainerFolderPath` at `0x180069f5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069f2b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069f2b`

## pseudocode

```c
__int64 __fastcall WerpAddIfRegisteredForAppLocalDump(void *a1, HANDLE ProcessHandle, __int64 a3)
{
  unsigned int v6; // r8d
  struct CReport *ReportFromHandle; // rdi
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  LPWSTR *v10; // rax
  __int64 v11; // rax
  wchar_t *v12; // rbx
  __int64 v14; // [rsp+28h] [rbp-81h] BYREF
  __int64 v15; // [rsp+30h] [rbp-79h] BYREF
  PSID Sid; // [rsp+38h] [rbp-71h] BYREF
  wchar_t *Str[4]; // [rsp+40h] [rbp-69h] BYREF
  wchar_t pszDest[64]; // [rsp+60h] [rbp-49h] BYREF

  Sid = 0;
  v15 = 0;
  v14 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Str);
  if ( a1 && ProcessHandle && a3 )
  {
    if ( (int)WerpGetAppLocalDumpSubpath(ProcessHandle, pszDest, v6) >= 0 )
    {
      ReportFromHandle = GetReportFromHandle(a1);
      if ( ReportFromHandle )
      {
        if ( (int)UtilGetProcessAppContainerPackageSid(ProcessHandle) >= 0 )
        {
          v10 = (LPWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&v15);
          if ( ConvertSidToStringSidW(Sid, v10) )
          {
            v11 = ___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___0__Z(&v14);
            if ( (int)GetAppContainerFolderPath(v15, v11) >= 0
              && (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                        Str,
                        L"%ws\\%ws",
                        v14,
                        pszDest) >= 0 )
            {
              v12 = Str[0];
              if ( !wcsstr(Str[0], L"..") )
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                  (char *)ReportFromHandle + 46512,
                  v12);
            }
          }
          else
          {
            GetLastError();
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v9 = 167;
LABEL_19:
          WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
        }
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 166;
      goto LABEL_19;
    }
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Str);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v15);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&Sid);
  return 0;
}

```

## disassembly

```asm
0x180069e50  mov     [rsp-8+arg_10], rbx
0x180069e55  push    rbp
0x180069e56  push    rsi
0x180069e57  push    rdi
0x180069e58  lea     rbp, [rsp-47h]
0x180069e5d  sub     rsp, 0F0h
0x180069e64  mov     rax, cs:__security_cookie
0x180069e6b  xor     rax, rsp
0x180069e6e  mov     [rbp+57h+var_20], rax
0x180069e72  mov     rdi, rcx
0x180069e75  mov     [rbp+57h+Sid], 0
0x180069e7d  lea     rcx, [rbp+57h+Str]; void *
0x180069e81  mov     [rbp+57h+var_D0], 0
0x180069e89  mov     rsi, r8
0x180069e8c  mov     [rsp+100h+var_D8], 0
0x180069e95  mov     rbx, rdx
0x180069e98  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180069e9d  test    rdi, rdi
0x180069ea0  jz      loc_180069FBA
0x180069ea6  test    rbx, rbx
0x180069ea9  jz      loc_180069FBA
0x180069eaf  test    rsi, rsi
0x180069eb2  jz      loc_180069FBA
0x180069eb8  lea     rdx, [rbp+57h+pszDest]; pszDest
0x180069ebc  mov     rcx, rbx; hProcess
0x180069ebf  call    ?WerpGetAppLocalDumpSubpath@@YAJPEAXPEA_WK@Z; WerpGetAppLocalDumpSubpath(void *,wchar_t *,ulong)
0x180069ec4  test    eax, eax
0x180069ec6  js      loc_180069FE8
0x180069ecc  mov     rcx, rdi; void *
0x180069ecf  call    ?GetReportFromHandle@@YAPEAVCReport@@PEAX@Z; GetReportFromHandle(void *)
0x180069ed4  mov     rdi, rax
0x180069ed7  test    rax, rax
0x180069eda  jnz     short loc_180069F07
0x180069edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ee3  lea     rax, WPP_GLOBAL_Control
0x180069eea  cmp     rcx, rax
0x180069eed  jz      loc_180069FE8
0x180069ef3  test    byte ptr [rcx+1Ch], 1
0x180069ef7  jz      loc_180069FE8
0x180069efd  mov     edx, 0A7h
0x180069f02  jmp     loc_180069FD8
0x180069f07  lea     rdx, [rbp+57h+Sid]
0x180069f0b  mov     rcx, rbx; ProcessHandle
0x180069f0e  call    ?UtilGetProcessAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180069f13  test    eax, eax
0x180069f15  js      loc_180069FE8
0x180069f1b  lea     rcx, [rbp+57h+var_D0]
0x180069f1f  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180069f24  mov     rcx, [rbp+57h+Sid]; Sid
0x180069f28  mov     rdx, rax; StringSid
0x180069f2b  call    cs:__imp_ConvertSidToStringSidW
0x180069f32  nop     dword ptr [rax+rax+00h]
0x180069f37  test    eax, eax
0x180069f39  jnz     short loc_180069F4C
0x180069f3b  call    cs:__imp_GetLastError
0x180069f42  nop     dword ptr [rax+rax+00h]
0x180069f47  jmp     loc_180069FE8
0x180069f4c  lea     rcx, [rsp+100h+var_D8]
0x180069f51  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180069f56  mov     rcx, [rbp+57h+var_D0]
0x180069f5a  mov     rdx, rax
0x180069f5d  call    cs:__imp_GetAppContainerFolderPath
0x180069f64  nop     dword ptr [rax+rax+00h]
0x180069f69  test    eax, eax
0x180069f6b  js      short loc_180069FE8
0x180069f6d  mov     r8, [rsp+100h+var_D8]
0x180069f72  lea     r9, [rbp+57h+pszDest]
0x180069f76  lea     rdx, aWsWs_0; "%ws\\%ws"
0x180069f7d  lea     rcx, [rbp+57h+Str]
0x180069f81  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180069f86  test    eax, eax
0x180069f88  js      short loc_180069FE8
0x180069f8a  mov     rbx, [rbp+57h+Str]
0x180069f8e  lea     rdx, SubStr; ".."
0x180069f95  mov     rcx, rbx; Str
0x180069f98  call    cs:__imp_wcsstr
0x180069f9f  nop     dword ptr [rax+rax+00h]
0x180069fa4  test    rax, rax
0x180069fa7  jnz     short loc_180069FE8
0x180069fa9  lea     rcx, [rdi+0B5B0h]
0x180069fb0  mov     rdx, rbx
0x180069fb3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180069fb8  jmp     short loc_180069FE8
0x180069fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fc1  lea     rax, WPP_GLOBAL_Control
0x180069fc8  cmp     rcx, rax
0x180069fcb  jz      short loc_180069FE8
0x180069fcd  test    byte ptr [rcx+1Ch], 1
0x180069fd1  jz      short loc_180069FE8
0x180069fd3  mov     edx, 0A6h
0x180069fd8  mov     rcx, [rcx+10h]
0x180069fdc  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x180069fe3  call    WPP_SF_
0x180069fe8  lea     rcx, [rbp+57h+Str]; void *
0x180069fec  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180069ff1  lea     rcx, [rsp+100h+var_D8]
0x180069ff6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069ffb  lea     rcx, [rbp+57h+var_D0]
0x180069fff  call    ??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x18006a004  lea     rcx, [rbp+57h+Sid]; void *
0x18006a008  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18006a00d  xor     eax, eax
0x18006a00f  mov     rcx, [rbp+57h+var_20]
0x18006a013  xor     rcx, rsp; StackCookie
0x18006a016  call    __security_check_cookie
0x18006a01b  mov     rbx, [rsp+100h+arg_10]
0x18006a023  add     rsp, 0F0h
0x18006a02a  pop     rdi
0x18006a02b  pop     rsi
0x18006a02c  pop     rbp
0x18006a02d  retn
```
