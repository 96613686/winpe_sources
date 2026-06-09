# OsEventsPublish6009

- ea: `0x1800c2528`
- end: `0x1800c27cb`
- name: `OsEventsPublish6009`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e4e4`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x1800208e0`
- `0x18002afa8`
- `0x18002d204`
- `0x18002d6dc`
- `0x1800771dc`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800c1e70`
- `0x1800c2528`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c26d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c26d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800c256a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800c256a`

## pseudocode

```c
void OsEventsPublish6009()
{
  __int64 v0; // rbx
  __int64 dwMinorVersion; // r9
  _QWORD *v2; // rax
  HKEY *phkResult; // rax
  __int64 v4; // r8
  size_t v5; // [rsp+30h] [rbp-D0h]
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v8; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v9; // [rsp+70h] [rbp-90h]
  WCHAR *szCSDVersion; // [rsp+78h] [rbp-88h]
  __int64 v11; // [rsp+80h] [rbp-80h]
  const wchar_t *v12; // [rsp+88h] [rbp-78h]
  _QWORD v13[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v14[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v16[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v17; // [rsp+218h] [rbp+118h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    v0 = *(_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,unsigned int,10,wchar_t>(
                      &v8,
                      v16,
                      &v17,
                      VersionInformation.dwMajorVersion);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            v7,
                            v16,
                            (v0 - (__int64)v16) >> 1)
      && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                            v7,
                            46) )
    {
      dwMinorVersion = VersionInformation.dwMinorVersion;
      if ( VersionInformation.dwMinorVersion >= 0xA )
      {
LABEL_7:
        utl::_ToCharsConstBase<utl::to_wchars_result,unsigned int,10,wchar_t>(&v8, v16, &v17, dwMinorVersion);
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v7)
          && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                v7,
                                46) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
          v2 = (_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,unsigned int,10,wchar_t>(
                           &v8,
                           v16,
                           &v17,
                           VersionInformation.dwBuildNumber);
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  v14,
                                  v16,
                                  (__int64)(*v2 - (_QWORD)v16) >> 1) )
          {
            v6 = 0;
            phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>((HKEY *)&v6);
            if ( !RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion",
                    0,
                    1u,
                    phkResult) )
            {
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13);
              v13[1] = v13[0];
              v8 = v6;
              *(_WORD *)v13[0] = 0;
              v9 = L"CurrentType";
              szCSDVersion = 0;
              ____AppendFnImpl__WU__char_traits__W_utl__V__allocator__W_2_V_lambda_1___1_____AppendRegSzImpl_V__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl___W_tlx__YAJAEAV__basic_string__WU__char_traits__W_utl__V__allocator__W_2__2_PEAUHKEY____PEB_WPEAK_Z__tlx__YAJAEAV__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl____QEAV_lambda_1___1_____AppendRegSzImpl_V__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl___W_0_YAJ0PEAUHKEY____PEB_WPEAK_Z__Z(
                v13,
                &v8);
              v8 = v7[0];
              v9 = (const WCHAR *)v14[0];
              szCSDVersion = VersionInformation.szCSDVersion;
              v11 = v13[0];
              v12 = L"0";
              LODWORD(v5) = 0;
              LogElfEvent(0x80001779, 4, v4, 5u, (__int64)&v8, 0, v5);
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v13);
            }
            tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v6);
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v14);
        }
        goto LABEL_14;
      }
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                              v7,
                              48) )
      {
        dwMinorVersion = VersionInformation.dwMinorVersion;
        goto LABEL_7;
      }
    }
LABEL_14:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v7);
  }
}

```

## disassembly

```asm
0x1800c2528  mov     [rsp-8+arg_0], rbx
0x1800c252d  push    rbp
0x1800c252e  lea     rbp, [rsp-120h]
0x1800c2536  sub     rsp, 220h
0x1800c253d  mov     rax, cs:__security_cookie
0x1800c2544  xor     rax, rsp
0x1800c2547  mov     [rbp+120h+var_8], rax
0x1800c254e  xor     edx, edx; Val
0x1800c2550  lea     rcx, [rbp+120h+VersionInformation.dwMajorVersion]; void *
0x1800c2554  mov     r8d, 118h; Size
0x1800c255a  call    memset_0
0x1800c255f  lea     rcx, [rbp+120h+VersionInformation]; lpVersionInformation
0x1800c2563  mov     [rbp+120h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800c256a  call    cs:__imp_GetVersionExW
0x1800c2570  test    eax, eax
0x1800c2572  jz      loc_1800C27AB
0x1800c2578  mov     r9d, [rbp+120h+VersionInformation.dwMajorVersion]
0x1800c257c  lea     r8, [rbp+120h+var_8]
0x1800c2583  lea     rdx, [rbp+120h+var_30]
0x1800c258a  lea     rcx, [rsp+220h+var_1B8]
0x1800c258f  call    ??$_ToCharsConstBase@Uto_wchars_result@utl@@I$09_W@utl@@YA?AUto_wchars_result@0@PEA_W0I@Z; utl::_ToCharsConstBase<utl::to_wchars_result,uint,10,wchar_t>(wchar_t *,wchar_t *,uint)
0x1800c2594  lea     rcx, [rsp+220h+var_1D8]; void *
0x1800c2599  mov     rbx, [rax]
0x1800c259c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c25a1  lea     rax, [rbp+120h+var_30]
0x1800c25a8  sub     rbx, rax
0x1800c25ab  lea     rdx, [rbp+120h+var_30]
0x1800c25b2  sar     rbx, 1
0x1800c25b5  lea     rcx, [rsp+220h+var_1D8]
0x1800c25ba  mov     r8, rbx
0x1800c25bd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800c25c2  test    al, al
0x1800c25c4  jz      loc_1800C27A1
0x1800c25ca  mov     ebx, 2Eh ; '.'
0x1800c25cf  lea     rcx, [rsp+220h+var_1D8]
0x1800c25d4  mov     edx, ebx
0x1800c25d6  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800c25db  test    al, al
0x1800c25dd  jz      loc_1800C27A1
0x1800c25e3  mov     r9d, [rbp+120h+VersionInformation.dwMinorVersion]
0x1800c25e7  cmp     r9d, 0Ah
0x1800c25eb  jnb     short loc_1800C2606
0x1800c25ed  lea     edx, [rbx+2]
0x1800c25f0  lea     rcx, [rsp+220h+var_1D8]
0x1800c25f5  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800c25fa  test    al, al
0x1800c25fc  jz      loc_1800C27A1
0x1800c2602  mov     r9d, [rbp+120h+VersionInformation.dwMinorVersion]
0x1800c2606  lea     r8, [rbp+120h+var_8]
0x1800c260d  lea     rdx, [rbp+120h+var_30]
0x1800c2614  lea     rcx, [rsp+220h+var_1B8]
0x1800c2619  call    ??$_ToCharsConstBase@Uto_wchars_result@utl@@I$09_W@utl@@YA?AUto_wchars_result@0@PEA_W0I@Z; utl::_ToCharsConstBase<utl::to_wchars_result,uint,10,wchar_t>(wchar_t *,wchar_t *,uint)
0x1800c261e  lea     rcx, [rbp+120h+var_30]
0x1800c2625  lea     rdx, [rbp+120h+var_30]
0x1800c262c  mov     r8, [rax]
0x1800c262f  sub     r8, rcx
0x1800c2632  lea     rcx, [rsp+220h+var_1D8]
0x1800c2637  sar     r8, 1
0x1800c263a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800c263f  test    al, al
0x1800c2641  jz      loc_1800C27A1
0x1800c2647  mov     edx, ebx
0x1800c2649  lea     rcx, [rsp+220h+var_1D8]
0x1800c264e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800c2653  test    al, al
0x1800c2655  jz      loc_1800C27A1
0x1800c265b  lea     rcx, [rbp+120h+var_170]; void *
0x1800c265f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c2664  mov     r9d, [rbp+120h+VersionInformation.dwBuildNumber]
0x1800c2668  lea     r8, [rbp+120h+var_8]
0x1800c266f  lea     rdx, [rbp+120h+var_30]
0x1800c2676  lea     rcx, [rsp+220h+var_1B8]
0x1800c267b  call    ??$_ToCharsConstBase@Uto_wchars_result@utl@@I$09_W@utl@@YA?AUto_wchars_result@0@PEA_W0I@Z; utl::_ToCharsConstBase<utl::to_wchars_result,uint,10,wchar_t>(wchar_t *,wchar_t *,uint)
0x1800c2680  lea     rcx, [rbp+120h+var_30]
0x1800c2687  lea     rdx, [rbp+120h+var_30]
0x1800c268e  mov     r8, [rax]
0x1800c2691  sub     r8, rcx
0x1800c2694  lea     rcx, [rbp+120h+var_170]
0x1800c2698  sar     r8, 1
0x1800c269b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800c26a0  test    al, al
0x1800c26a2  jz      loc_1800C2798
0x1800c26a8  lea     rcx, [rsp+220h+var_1E0]
0x1800c26ad  mov     [rsp+220h+var_1E0], 0
0x1800c26b6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c26bb  mov     r9d, 1; samDesired
0x1800c26c1  mov     [rsp+220h+phkResult], rax; phkResult
0x1800c26c6  xor     r8d, r8d; ulOptions
0x1800c26c9  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800c26d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c26d7  call    cs:__imp_RegOpenKeyExW
0x1800c26dd  test    eax, eax
0x1800c26df  jnz     loc_1800C278E
0x1800c26e5  lea     rcx, [rbp+120h+var_190]; void *
0x1800c26e9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c26ee  mov     rcx, [rbp+120h+var_190]
0x1800c26f2  xor     eax, eax
0x1800c26f4  mov     rdx, [rsp+220h+var_1E0]
0x1800c26f9  mov     [rbp+120h+var_188], rcx
0x1800c26fd  mov     [rsp+220h+var_1B8], rdx
0x1800c2702  lea     rdx, [rsp+220h+var_1B8]
0x1800c2707  mov     [rcx], ax
0x1800c270a  lea     rax, aCurrenttype; "CurrentType"
0x1800c2711  lea     rcx, [rbp+120h+var_190]
0x1800c2715  mov     [rsp+220h+var_1B0], rax
0x1800c271a  mov     [rsp+220h+var_1A8], 0
0x1800c2723  call    ??$_AppendFnImpl@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@V_lambda_1_@?1???$_AppendRegSzImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_W@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@PEAUHKEY__@@PEB_WPEAK@Z@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@$$QEAV_lambda_1_@?1???$_AppendRegSzImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_W@0@YAJ0PEAUHKEY__@@PEB_WPEAK@Z@@Z; tlx::_AppendFnImpl<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>,`tlx::_AppendRegSzImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,HKEY__ *,wchar_t const *,ulong *)'::`2'::_lambda_1_>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,`tlx::_AppendRegSzImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,HKEY__ *,wchar_t const *,ulong *)'::`2'::_lambda_1_ &&)
0x1800c2728  mov     rax, [rsp+220h+var_1D8]
0x1800c272d  mov     edx, 4; int
0x1800c2732  mov     [rsp+220h+var_1B8], rax
0x1800c2737  mov     ecx, 80001779h; int
0x1800c273c  mov     rax, [rbp+120h+var_170]
0x1800c2740  mov     [rsp+220h+var_1B0], rax
0x1800c2745  lea     rax, [rbp+120h+VersionInformation.szCSDVersion]
0x1800c2749  mov     [rsp+220h+var_1A8], rax
0x1800c274e  lea     r9d, [rdx+1]; int
0x1800c2752  mov     rax, [rbp+120h+var_190]
0x1800c2756  mov     [rbp+120h+var_1A0], rax
0x1800c275a  lea     rax, a0_0; "0"
0x1800c2761  mov     [rbp+120h+var_198], rax
0x1800c2765  lea     rax, [rsp+220h+var_1B8]
0x1800c276a  mov     dword ptr [rsp+220h+var_1F0], 0; size_t
0x1800c2772  mov     [rsp+220h+Src], 0; Src
0x1800c277b  mov     [rsp+220h+phkResult], rax; __int64
0x1800c2780  call    LogElfEvent
0x1800c2785  lea     rcx, [rbp+120h+var_190]; void *
0x1800c2789  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c278e  lea     rcx, [rsp+220h+var_1E0]
0x1800c2793  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800c2798  lea     rcx, [rbp+120h+var_170]; void *
0x1800c279c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c27a1  lea     rcx, [rsp+220h+var_1D8]; void *
0x1800c27a6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c27ab  mov     rcx, [rbp+120h+var_8]
0x1800c27b2  xor     rcx, rsp; StackCookie
0x1800c27b5  call    __security_check_cookie
0x1800c27ba  mov     rbx, [rsp+220h+arg_0]
0x1800c27c2  add     rsp, 220h
0x1800c27c9  pop     rbp
0x1800c27ca  retn
```
