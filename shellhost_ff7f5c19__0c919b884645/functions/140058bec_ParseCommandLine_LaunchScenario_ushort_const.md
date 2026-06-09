# ParseCommandLine(LaunchScenario,ushort const *)

- ea: `0x140058bec`
- end: `0x1400599f4`
- name: `?ParseCommandLine@@YAHW4LaunchScenario@@PEBG@Z`
- size: `3592`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006ab0`
- `0x14005cae0`

## callees

- `0x1400038e0`
- `0x140004140`
- `0x1400049a0`
- `0x1400053f0`
- `0x140005a40`
- `0x140005da0`
- `0x140006100`
- `0x140006820`
- `0x1400088d0`
- `0x140009280`
- `0x140009910`
- `0x140009d6c`
- `0x140009f50`
- `0x14000a190`
- `0x14000a310`
- `0x14000a4f8`
- `0x14000a930`
- `0x14000ab50`
- `0x14000ae10`
- `0x14000b360`
- `0x14000b6a8`
- `0x14000f7e0`
- `0x140010668`
- `0x140028cd0`
- `0x140034830`
- `0x1400355b0`
- `0x14003c890`
- `0x14004cfc0`
- `0x14004df08`
- `0x14004df74`
- `0x14004e800`
- `0x14004e8f0`
- `0x140050608`
- `0x14005246c`
- `0x140053248`
- `0x1400584cc`
- `0x140058bec`
- `0x1400599fc`

## string_xrefs

- `0x140059039`: `shellHostComponentExtensionId`
- `0x140058fec`: `loadComponent`
- `0x1400590d3`: `--extensionId`
- `0x140059086`: `--extensionCategory`
- `0x140059369`: `activateWinRTClassFromExtensionPackage`
- `0x14005928c`: `uriString`
- `0x14005947f`: `--uri`
- `0x14005954a`: `communicationHWND`
- `0x140059621`: `extensionId`
- `0x1400595dc`: `extensionCategory`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall ParseCommandLine(int a1, __int64 a2)
{
  int v2; // r14d
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  void *v14; // rbx
  void *v15; // rax
  __int64 v16; // rax
  __int64 v17; // r15
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  void *v22; // rbx
  void *v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  void *v33; // rbx
  void *v34; // rax
  __int64 v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  void *v38; // rbx
  void *v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  void *v43; // rbx
  void *v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 v47; // rax
  void *v48; // rbx
  void *v49; // rax
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 *subcommands; // rax
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  const char *v67; // r9
  __int64 v69; // rax
  unsigned int v70; // eax
  void *v71; // rdx
  unsigned int v72; // r8d
  int v73; // [rsp+20h] [rbp-648h]
  __int64 v74; // [rsp+20h] [rbp-648h] BYREF
  _BYTE v75[8]; // [rsp+28h] [rbp-640h] BYREF
  _QWORD v76[3]; // [rsp+30h] [rbp-638h] BYREF
  __int64 (__fastcall **v77)(); // [rsp+48h] [rbp-620h] BYREF
  __int64 *v78; // [rsp+50h] [rbp-618h]
  __int64 *v79; // [rsp+58h] [rbp-610h]
  __int64 *v80; // [rsp+60h] [rbp-608h]
  __int128 *v81; // [rsp+68h] [rbp-600h]
  __int128 *v82; // [rsp+70h] [rbp-5F8h]
  __int128 *v83; // [rsp+78h] [rbp-5F0h]
  __int64 (__fastcall ***v84)(); // [rsp+80h] [rbp-5E8h]
  __int64 v85; // [rsp+88h] [rbp-5E0h] BYREF
  __int64 v86; // [rsp+90h] [rbp-5D8h] BYREF
  __int64 v87; // [rsp+98h] [rbp-5D0h] BYREF
  __int64 v88; // [rsp+A0h] [rbp-5C8h] BYREF
  __int64 v89; // [rsp+A8h] [rbp-5C0h] BYREF
  __int64 v90; // [rsp+B0h] [rbp-5B8h] BYREF
  __int64 v91; // [rsp+B8h] [rbp-5B0h] BYREF
  __int64 v92; // [rsp+C0h] [rbp-5A8h] BYREF
  __int64 v93; // [rsp+C8h] [rbp-5A0h] BYREF
  __int128 v94; // [rsp+D0h] [rbp-598h] BYREF
  __int64 v95; // [rsp+E0h] [rbp-588h]
  __int128 v96; // [rsp+E8h] [rbp-580h] BYREF
  __int64 v97; // [rsp+F8h] [rbp-570h]
  __int64 v98; // [rsp+100h] [rbp-568h] BYREF
  __int64 v99; // [rsp+108h] [rbp-560h] BYREF
  __int128 v100; // [rsp+110h] [rbp-558h] BYREF
  __int64 v101; // [rsp+120h] [rbp-548h]
  __int64 *v102; // [rsp+128h] [rbp-540h] BYREF
  __int64 *v103; // [rsp+130h] [rbp-538h]
  __int64 *v104; // [rsp+138h] [rbp-530h]
  __int64 *v105; // [rsp+140h] [rbp-528h]
  __int64 *v106; // [rsp+148h] [rbp-520h]
  __int64 *v107; // [rsp+150h] [rbp-518h]
  __int64 *v108; // [rsp+158h] [rbp-510h]
  __int128 *v109; // [rsp+160h] [rbp-508h]
  __int128 *v110; // [rsp+168h] [rbp-500h]
  __int128 *v111; // [rsp+170h] [rbp-4F8h]
  _QWORD v112[7]; // [rsp+180h] [rbp-4E8h] BYREF
  _QWORD *v113; // [rsp+1B8h] [rbp-4B0h]
  _BYTE v114[64]; // [rsp+1C0h] [rbp-4A8h] BYREF
  _BYTE v115[32]; // [rsp+200h] [rbp-468h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+220h] [rbp-448h] BYREF
  _BYTE v117[976]; // [rsp+260h] [rbp-408h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+668h] [rbp+0h]

  v2 = a1;
  v85 = a2;
  std::string::string(&v102, &qword_14006D7D8);
  std::string::string(&v77, &qword_14006D7D8);
  CLI::App::App((CLI::App *)v117);
  CLI::App::ignore_case((CLI::App *)v117, 1);
  v117[305] = 1;
  v117[794] = 1;
  v117[72] = 1;
  v91 = 0;
  v3 = std::string::string(&v77, &qword_14006D7D8);
  v4 = std::string::string(&v102, "--instance");
  v5 = CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v117, v4, &v91, v3, &v102);
  v96 = 0;
  v97 = 0;
  v6 = std::string::string(&v77, &qword_14006D7D8);
  v7 = std::string::string(&v102, "--stringProperties");
  CLI::App::add_option<std::vector<std::pair<winrt::hstring,winrt::hstring>>,std::vector<std::pair<winrt::hstring,winrt::hstring>>,0>(
    v117,
    v7,
    &v96,
    v6);
  v94 = 0;
  v95 = 0;
  v8 = std::string::string(&v77, &qword_14006D7D8);
  v9 = std::string::string(&v102, "--intProperties");
  CLI::App::add_option<std::vector<std::pair<winrt::hstring,int>>,std::vector<std::pair<winrt::hstring,int>>,0>(
    v117,
    v9,
    &v94,
    v8);
  v100 = 0;
  v101 = 0;
  v10 = std::string::string(&v77, &qword_14006D7D8);
  v11 = std::string::string(&v102, "--boolProperties");
  CLI::App::add_option<std::vector<std::pair<winrt::hstring,bool>>,std::vector<std::pair<winrt::hstring,bool>>,0>(
    v117,
    v11,
    &v100,
    v10);
  v90 = 0;
  v12 = std::string::string(&v77, &qword_14006D7D8);
  v13 = std::string::string(&v102, "--valueSet");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v117, v13, &v90, v12, v74);
  v76[0] = &v77;
  v14 = (void *)std::string::string(&v77, &qword_14006D7D8);
  v15 = (void *)std::string::string(&v102, "keepalive");
  v16 = CLI::App::add_subcommand((CLI::App *)v117, v15, v14);
  v17 = v16;
  v74 = v5;
  if ( !v5 )
  {
    v69 = std::string::string(&v77, "nullptr passed");
    CLI::OptionNotFound::OptionNotFound(pExceptionObject, v69);
    throw (CLI::OptionNotFound *)pExceptionObject;
  }
  std::_Tree<std::_Tset_traits<CLI::Option *,std::less<CLI::Option *>,std::allocator<CLI::Option *>,0>>::insert<0,0>(
    v16 + 752,
    v76,
    &v74);
  v75[0] = 0;
  v76[0] = v114;
  v18 = std::string::string(v114, &qword_14006D7D8);
  v19 = std::string::string(v112, "--stop");
  CLI::App::add_flag<bool,0>(v17, v19, v75, v18, v74);
  v98 = 1;
  v76[0] = v112;
  v20 = std::string::string(v112, &qword_14006D7D8);
  v21 = std::string::string(v114, "--frames");
  CLI::App::add_option<unsigned __int64,unsigned __int64,0>(v17, v21, &v98, v20);
  v112[0] = off_140069FD0;
  v112[1] = &v91;
  v112[2] = &v85;
  v112[3] = v75;
  v112[4] = &v98;
  v113 = v112;
  CLI::App::callback(v17, v112);
  v76[0] = v112;
  v22 = (void *)std::string::string(v112, &qword_14006D7D8);
  v23 = (void *)std::string::string(v114, "loadComponent");
  v24 = CLI::App::add_subcommand((CLI::App *)v117, v23, v22);
  v93 = 0;
  v76[0] = &v77;
  v25 = std::string::string(&v77, &qword_14006D7D8);
  v26 = std::string::string(&v102, "shellHostComponentExtensionId");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v24, v26, &v93, v25, v74);
  v89 = 0;
  v76[0] = &v77;
  v27 = std::string::string(&v77, &qword_14006D7D8);
  v28 = std::string::string(&v102, "--extensionCategory");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v24, v28, &v89, v27, v74);
  v88 = 0;
  v76[0] = &v77;
  v29 = std::string::string(&v77, &qword_14006D7D8);
  v30 = std::string::string(&v102, "--extensionId");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v24, v30, &v88, v29, v74);
  v87 = 0;
  v76[0] = &v77;
  v31 = std::string::string(&v77, &qword_14006D7D8);
  v32 = std::string::string(&v102, "--controlName");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v24, v32, &v87, v31, v74);
  v76[0] = &v77;
  v102 = &v91;
  v103 = &v85;
  v104 = &v93;
  v105 = &v89;
  v106 = &v88;
  v107 = &v87;
  v108 = &v90;
  v109 = &v96;
  v110 = &v94;
  v111 = &v100;
  v84 = 0;
  v84 = (__int64 (__fastcall ***)())std::_Global_new_std::_Func_impl_no_alloc__lambda_62f806f766e8baecd72c7e4ff4c91d9b__void___lambda_62f806f766e8baecd72c7e4ff4c91d9b___(&v102);
  CLI::App::callback(v24, &v77);
  v76[0] = v112;
  v33 = (void *)std::string::string(v112, &qword_14006D7D8);
  v34 = (void *)std::string::string(v114, "uri");
  v35 = CLI::App::add_subcommand((CLI::App *)v117, v34, v33);
  v86 = 0;
  v76[0] = &v77;
  v36 = std::string::string(&v77, &qword_14006D7D8);
  v37 = std::string::string(&v102, "uriString");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v35, v37, &v86, v36, v74);
  v76[0] = &v102;
  v77 = (__int64 (__fastcall **)())&v91;
  v78 = &v85;
  v79 = &v86;
  v80 = &v90;
  v81 = &v96;
  v82 = &v94;
  v83 = &v100;
  v109 = 0;
  v109 = (__int128 *)std::_Global_new_std::_Func_impl_no_alloc__lambda_5259556881c96990af9e39922a6284e5__void___lambda_5259556881c96990af9e39922a6284e5___(&v77);
  CLI::App::callback(v35, &v102);
  v76[0] = v112;
  v38 = (void *)std::string::string(v112, &qword_14006D7D8);
  v39 = (void *)std::string::string(v114, "activateWinRTClassFromExtensionPackage");
  v40 = CLI::App::add_subcommand((CLI::App *)v117, v39, v38);
  std::wstring::wstring(v115);
  v76[0] = &v77;
  v41 = std::string::string(&v77, &qword_14006D7D8);
  v42 = std::string::string(&v102, "runtimeClassName");
  CLI::App::add_option<std::wstring,std::wstring,0>(v40, v42, v115, v41);
  v77 = off_140069100;
  v78 = (__int64 *)v115;
  v84 = &v77;
  CLI::App::callback(v40, &v77);
  v76[0] = v112;
  v43 = (void *)std::string::string(v112, &qword_14006D7D8);
  v44 = (void *)std::string::string(v114, "ControlCenter");
  v45 = CLI::App::add_subcommand((CLI::App *)v117, v44, v43);
  v76[0] = &v77;
  v46 = std::string::string(&v77, &qword_14006D7D8);
  v47 = std::string::string(&v102, "--uri");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v45, v47, &v86, v46, v74);
  v77 = off_140069190;
  v78 = &v86;
  v84 = &v77;
  CLI::App::callback(v45, &v77);
  v76[0] = v112;
  v48 = (void *)std::string::string(v112, &qword_14006D7D8);
  v49 = (void *)std::string::string(v114, "UXFrameHost");
  v50 = CLI::App::add_subcommand((CLI::App *)v117, v49, v48);
  v99 = 0;
  v76[0] = &v77;
  v51 = std::string::string(&v77, &qword_14006D7D8);
  v52 = std::string::string(&v102, "communicationHWND");
  CLI::App::add_option<__int64,__int64,0>(v50, v52, &v99, v51);
  v92 = 0;
  v76[0] = &v77;
  v53 = std::string::string(&v77, &qword_14006D7D8);
  v54 = std::string::string(&v102, "windowingBehavior");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v50, v54, &v92, v53, v74);
  v76[0] = &v77;
  v55 = std::string::string(&v77, &qword_14006D7D8);
  v56 = std::string::string(&v102, "extensionCategory");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v50, v56, &v89, v55, v74);
  v76[0] = &v77;
  v57 = std::string::string(&v77, &qword_14006D7D8);
  v58 = std::string::string(&v102, "extensionId");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v50, v58, &v88, v57, v74);
  v76[0] = &v77;
  v59 = std::string::string(&v77, &qword_14006D7D8);
  v60 = std::string::string(&v102, "controlName");
  CLI::App::add_option<winrt::hstring,winrt::hstring,0>(v50, v60, &v87, v59, v74);
  v76[0] = &v77;
  v102 = &v99;
  v103 = &v92;
  v104 = &v85;
  v105 = &v89;
  v106 = &v88;
  v107 = &v87;
  v108 = &v90;
  v109 = &v96;
  v110 = &v94;
  v111 = &v100;
  v84 = 0;
  v84 = (__int64 (__fastcall ***)())std::_Global_new_std::_Func_impl_no_alloc__lambda_9adc38345accd8e78c07ef5e0da36432__void___lambda_9adc38345accd8e78c07ef5e0da36432___(&v102);
  CLI::App::callback(v50, &v77);
  try
  {
    ((void (*)(void))std::wstring::wstring)();
    CLI::App::parse((CLI::App *)v117);
  }
  catch ( CLI::ParseError )
  {
    ShellHostTelemetry::CommandLineParsingError();
    if ( !a1 )
    {
      v70 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::FailFast_Hr(retaddr, v71, v72, (const char *)v70, v73);
    }
    v2 = a1;
  }
  if ( !v2 )
  {
    v112[0] = off_140069F40;
    v113 = v112;
    subcommands = (__int64 *)CLI::App::get_subcommands(v117, v76, v112);
    v62 = *subcommands;
    v63 = subcommands[1];
    std::vector<CLI::App *>::_Tidy(v76);
    std::_Func_class<void,>::~_Func_class<void,>(v112);
    if ( v62 == v63 )
    {
      std::wstring::wstring(&v102, v85);
      v64 = std::wstring::wstring(v112, &v102);
      ParseLaunchArguments(v114, v64);
      OnControlCenterLaunchRequested((const struct LaunchData *)v114, v65, v66, v67);
      LaunchData::~LaunchData((LaunchData *)v114);
      std::wstring::~wstring(&v102);
    }
  }
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v92);
  std::wstring::~wstring(v115);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v86);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v87);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v88);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v89);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v93);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v90);
  std::vector<std::pair<winrt::hstring,bool>>::~vector<std::pair<winrt::hstring,bool>>(&v100);
  if ( (_QWORD)v94 )
  {
    std::_Destroy_range<std::allocator<std::pair<winrt::hstring,int>>>(v94, *((_QWORD *)&v94 + 1));
    std::_Deallocate<16>(v94, (v95 - v94) & 0xFFFFFFFFFFFFFFF0uLL);
    v94 = 0;
    v95 = 0;
  }
  if ( (_QWORD)v96 )
  {
    std::_Destroy_range<std::allocator<std::pair<winrt::hstring,winrt::hstring>>>(v96, *((_QWORD *)&v96 + 1));
    std::_Deallocate<16>(v96, (v97 - v96) & 0xFFFFFFFFFFFFFFF0uLL);
    v96 = 0;
    v97 = 0;
  }
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v91);
  CLI::App::~App((CLI::App *)v117);
  return 0;
}

```

## disassembly

```asm
0x140058bec  mov     r11, rsp
0x140058bef  mov     [r11+18h], rbx
0x140058bf3  mov     [rsp+arg_0], ecx
0x140058bf7  push    rsi
0x140058bf8  push    rdi
0x140058bf9  push    r12
0x140058bfb  push    r14
0x140058bfd  push    r15
0x140058bff  sub     rsp, 640h
0x140058c06  mov     rax, cs:__security_cookie
0x140058c0d  xor     rax, rsp
0x140058c10  mov     [rsp+668h+var_38], rax
0x140058c18  mov     r14d, ecx
0x140058c1b  mov     [r11-5E0h], rdx
0x140058c22  lea     rax, [r11-540h]
0x140058c29  mov     [rsp+668h+var_648], rax
0x140058c2e  lea     r12, qword_14006D7D8
0x140058c35  mov     rdx, r12
0x140058c38  lea     rcx, [r11-540h]
0x140058c3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058c44  mov     rbx, rax
0x140058c47  mov     rdx, r12
0x140058c4a  lea     rcx, [rsp+668h+var_620]
0x140058c4f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058c54  nop
0x140058c55  mov     r8, rbx
0x140058c58  mov     rdx, rax
0x140058c5b  lea     rcx, [rsp+668h+var_408]; this
0x140058c63  call    ??0App@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; CLI::App::App(std::string,std::string)
0x140058c68  nop
0x140058c69  mov     dl, 1; bool
0x140058c6b  lea     rcx, [rsp+668h+var_408]; this
0x140058c73  call    ?ignore_case@App@CLI@@QEAAPEAV12@_N@Z; CLI::App::ignore_case(bool)
0x140058c78  mov     [rsp+668h+var_2D7], 1
0x140058c80  mov     [rsp+668h+var_EE], 1
0x140058c88  mov     [rsp+668h+var_3C0], 1
0x140058c90  xor     esi, esi
0x140058c92  mov     [rsp+668h+var_5B0], rsi
0x140058c9a  lea     rax, [rsp+668h+var_620]
0x140058c9f  mov     [rsp+668h+var_638], rax
0x140058ca4  mov     rdx, r12
0x140058ca7  lea     rcx, [rsp+668h+var_620]
0x140058cac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058cb1  mov     rbx, rax
0x140058cb4  lea     rdx, aInstance; "--instance"
0x140058cbb  lea     rcx, [rsp+668h+var_540]
0x140058cc3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058cc8  nop
0x140058cc9  mov     r9, rbx
0x140058ccc  lea     r8, [rsp+668h+var_5B0]
0x140058cd4  mov     rdx, rax
0x140058cd7  lea     rcx, [rsp+668h+var_408]
0x140058cdf  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x140058ce4  mov     rdi, rax
0x140058ce7  xorps   xmm0, xmm0
0x140058cea  movdqu  [rsp+668h+var_580], xmm0
0x140058cf3  mov     [rsp+668h+var_570], rsi
0x140058cfb  lea     rax, [rsp+668h+var_620]
0x140058d00  mov     [rsp+668h+var_638], rax
0x140058d05  mov     rdx, r12
0x140058d08  lea     rcx, [rsp+668h+var_620]
0x140058d0d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058d12  mov     rbx, rax
0x140058d15  lea     rdx, aStringproperti; "--stringProperties"
0x140058d1c  lea     rcx, [rsp+668h+var_540]
0x140058d24  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058d29  nop
0x140058d2a  mov     r9, rbx
0x140058d2d  lea     r8, [rsp+668h+var_580]
0x140058d35  mov     rdx, rax
0x140058d38  lea     rcx, [rsp+668h+var_408]
0x140058d40  call    ??$add_option@V?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@V12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@4@0@Z; CLI::App::add_option<std::vector<std::pair<winrt::hstring,winrt::hstring>>,std::vector<std::pair<winrt::hstring,winrt::hstring>>,0>(std::string,std::vector<std::pair<winrt::hstring,winrt::hstring>> &,std::string)
0x140058d45  xorps   xmm0, xmm0
0x140058d48  movdqu  [rsp+668h+var_598], xmm0
0x140058d51  mov     [rsp+668h+var_588], rsi
0x140058d59  lea     rax, [rsp+668h+var_620]
0x140058d5e  mov     [rsp+668h+var_638], rax
0x140058d63  mov     rdx, r12
0x140058d66  lea     rcx, [rsp+668h+var_620]
0x140058d6b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058d70  mov     rbx, rax
0x140058d73  lea     rdx, aIntproperties; "--intProperties"
0x140058d7a  lea     rcx, [rsp+668h+var_540]
0x140058d82  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058d87  nop
0x140058d88  mov     r9, rbx
0x140058d8b  lea     r8, [rsp+668h+var_598]
0x140058d93  mov     rdx, rax
0x140058d96  lea     rcx, [rsp+668h+var_408]
0x140058d9e  call    ??$add_option@V?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@std@@V12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@0@Z; CLI::App::add_option<std::vector<std::pair<winrt::hstring,int>>,std::vector<std::pair<winrt::hstring,int>>,0>(std::string,std::vector<std::pair<winrt::hstring,int>> &,std::string)
0x140058da3  xorps   xmm0, xmm0
0x140058da6  movdqu  [rsp+668h+var_558], xmm0
0x140058daf  mov     [rsp+668h+var_548], rsi
0x140058db7  lea     rax, [rsp+668h+var_620]
0x140058dbc  mov     [rsp+668h+var_638], rax
0x140058dc1  mov     rdx, r12
0x140058dc4  lea     rcx, [rsp+668h+var_620]
0x140058dc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058dce  mov     rbx, rax
0x140058dd1  lea     rdx, aBoolproperties; "--boolProperties"
0x140058dd8  lea     rcx, [rsp+668h+var_540]
0x140058de0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058de5  nop
0x140058de6  mov     r9, rbx
0x140058de9  lea     r8, [rsp+668h+var_558]
0x140058df1  mov     rdx, rax
0x140058df4  lea     rcx, [rsp+668h+var_408]
0x140058dfc  call    ??$add_option@V?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@std@@V12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@0@Z; CLI::App::add_option<std::vector<std::pair<winrt::hstring,bool>>,std::vector<std::pair<winrt::hstring,bool>>,0>(std::string,std::vector<std::pair<winrt::hstring,bool>> &,std::string)
0x140058e01  mov     [rsp+668h+var_5B8], rsi
0x140058e09  lea     rax, [rsp+668h+var_620]
0x140058e0e  mov     [rsp+668h+var_638], rax
0x140058e13  mov     rdx, r12
0x140058e16  lea     rcx, [rsp+668h+var_620]
0x140058e1b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058e20  mov     rbx, rax
0x140058e23  lea     rdx, aValueset; "--valueSet"
0x140058e2a  lea     rcx, [rsp+668h+var_540]
0x140058e32  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058e37  nop
0x140058e38  mov     r9, rbx
0x140058e3b  lea     r8, [rsp+668h+var_5B8]
0x140058e43  mov     rdx, rax
0x140058e46  lea     rcx, [rsp+668h+var_408]
0x140058e4e  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x140058e53  lea     rax, [rsp+668h+var_620]
0x140058e58  mov     [rsp+668h+var_638], rax
0x140058e5d  mov     rdx, r12
0x140058e60  lea     rcx, [rsp+668h+var_620]
0x140058e65  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058e6a  mov     rbx, rax
0x140058e6d  lea     rdx, aKeepalive_0; "keepalive"
0x140058e74  lea     rcx, [rsp+668h+var_540]
0x140058e7c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058e81  nop
0x140058e82  mov     r8, rbx; void *
0x140058e85  mov     rdx, rax; void *
0x140058e88  lea     rcx, [rsp+668h+var_408]; this
0x140058e90  call    ?add_subcommand@App@CLI@@QEAAPEAV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; CLI::App::add_subcommand(std::string,std::string)
0x140058e95  mov     r15, rax
0x140058e98  mov     [rsp+668h+var_648], rdi
0x140058e9d  test    rdi, rdi
0x140058ea0  jz      loc_1400599BE
0x140058ea6  lea     rcx, [rax+2F0h]
0x140058ead  lea     r8, [rsp+668h+var_648]
0x140058eb2  lea     rdx, [rsp+668h+var_638]
0x140058eb7  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAVOption@CLI@@U?$less@PEAVOption@CLI@@@std@@V?$allocator@PEAVOption@CLI@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVOption@CLI@@@std@@@std@@@std@@_N@1@AEBQEAVOption@CLI@@@Z; std::_Tree<std::_Tset_traits<CLI::Option *,std::less<CLI::Option *>,std::allocator<CLI::Option *>,0>>::insert<0,0>(CLI::Option * const &)
0x140058ebc  mov     [rsp+668h+var_640], sil
0x140058ec1  lea     rax, [rsp+668h+var_4A8]
0x140058ec9  mov     [rsp+668h+var_638], rax
0x140058ece  mov     rdx, r12
0x140058ed1  lea     rcx, [rsp+668h+var_4A8]
0x140058ed9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058ede  mov     rbx, rax
0x140058ee1  lea     rdx, aStop; "--stop"
0x140058ee8  lea     rcx, [rsp+668h+var_4E8]
0x140058ef0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058ef5  nop
0x140058ef6  mov     r9, rbx
0x140058ef9  lea     r8, [rsp+668h+var_640]
0x140058efe  mov     rdx, rax
0x140058f01  mov     rcx, r15
0x140058f04  call    ??$add_flag@_N$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEA_N0@Z; CLI::App::add_flag<bool,0>(std::string,bool &,std::string)
0x140058f09  mov     [rsp+668h+var_568], 1
0x140058f15  lea     rax, [rsp+668h+var_4E8]
0x140058f1d  mov     [rsp+668h+var_638], rax
0x140058f22  mov     rdx, r12
0x140058f25  lea     rcx, [rsp+668h+var_4E8]
0x140058f2d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058f32  mov     rbx, rax
0x140058f35  lea     rdx, aFrames; "--frames"
0x140058f3c  lea     rcx, [rsp+668h+var_4A8]
0x140058f44  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058f49  nop
0x140058f4a  mov     r9, rbx
0x140058f4d  lea     r8, [rsp+668h+var_568]
0x140058f55  mov     rdx, rax
0x140058f58  mov     rcx, r15
0x140058f5b  call    ??$add_option@_K_K$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEA_K0@Z; CLI::App::add_option<unsigned __int64,unsigned __int64,0>(std::string,unsigned __int64 &,std::string)
0x140058f60  lea     rax, off_140069FD0
0x140058f67  mov     [rsp+668h+var_4E8], rax
0x140058f6f  lea     rax, [rsp+668h+var_5B0]
0x140058f77  mov     [rsp+668h+var_4E0], rax
0x140058f7f  lea     rax, [rsp+668h+var_5E0]
0x140058f87  mov     [rsp+668h+var_4D8], rax
0x140058f8f  lea     rax, [rsp+668h+var_640]
0x140058f94  mov     [rsp+668h+var_4D0], rax
0x140058f9c  lea     rax, [rsp+668h+var_568]
0x140058fa4  mov     [rsp+668h+var_4C8], rax
0x140058fac  lea     rax, [rsp+668h+var_4E8]
0x140058fb4  mov     [rsp+668h+var_4B0], rax
0x140058fbc  lea     rdx, [rsp+668h+var_4E8]
0x140058fc4  mov     rcx, r15
0x140058fc7  call    ?callback@App@CLI@@QEAAPEAV12@V?$function@$$A6AXXZ@std@@@Z; CLI::App::callback(std::function<void (void)>)
0x140058fcc  lea     rax, [rsp+668h+var_4E8]
0x140058fd4  mov     [rsp+668h+var_638], rax
0x140058fd9  mov     rdx, r12
0x140058fdc  lea     rcx, [rsp+668h+var_4E8]
0x140058fe4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140058fe9  mov     rbx, rax
0x140058fec  lea     rdx, aLoadcomponent; "loadComponent"
0x140058ff3  lea     rcx, [rsp+668h+var_4A8]
0x140058ffb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140059000  nop
0x140059001  mov     r8, rbx; void *
0x140059004  mov     rdx, rax; void *
0x140059007  lea     rcx, [rsp+668h+var_408]; this
0x14005900f  call    ?add_subcommand@App@CLI@@QEAAPEAV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; CLI::App::add_subcommand(std::string,std::string)
0x140059014  mov     rdi, rax
0x140059017  mov     [rsp+668h+var_5A0], rsi
0x14005901f  lea     rax, [rsp+668h+var_620]
0x140059024  mov     [rsp+668h+var_638], rax
0x140059029  mov     rdx, r12
0x14005902c  lea     rcx, [rsp+668h+var_620]
0x140059031  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140059036  mov     rbx, rax
0x140059039  lea     rdx, aShellhostcompo; "shellHostComponentExtensionId"
0x140059040  lea     rcx, [rsp+668h+var_540]
0x140059048  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005904d  nop
0x14005904e  mov     r9, rbx
0x140059051  lea     r8, [rsp+668h+var_5A0]
0x140059059  mov     rdx, rax
0x14005905c  mov     rcx, rdi
0x14005905f  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x140059064  mov     [rsp+668h+var_5C0], rsi
0x14005906c  lea     rax, [rsp+668h+var_620]
0x140059071  mov     [rsp+668h+var_638], rax
0x140059076  mov     rdx, r12
0x140059079  lea     rcx, [rsp+668h+var_620]
0x14005907e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140059083  mov     rbx, rax
0x140059086  lea     rdx, aExtensioncateg_1; "--extensionCategory"
0x14005908d  lea     rcx, [rsp+668h+var_540]
0x140059095  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005909a  nop
0x14005909b  mov     r9, rbx
0x14005909e  lea     r8, [rsp+668h+var_5C0]
0x1400590a6  mov     rdx, rax
0x1400590a9  mov     rcx, rdi
0x1400590ac  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x1400590b1  mov     [rsp+668h+var_5C8], rsi
0x1400590b9  lea     rax, [rsp+668h+var_620]
0x1400590be  mov     [rsp+668h+var_638], rax
0x1400590c3  mov     rdx, r12
0x1400590c6  lea     rcx, [rsp+668h+var_620]
0x1400590cb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400590d0  mov     rbx, rax
0x1400590d3  lea     rdx, aExtensionid; "--extensionId"
0x1400590da  lea     rcx, [rsp+668h+var_540]
0x1400590e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400590e7  nop
0x1400590e8  mov     r9, rbx
0x1400590eb  lea     r8, [rsp+668h+var_5C8]
0x1400590f3  mov     rdx, rax
0x1400590f6  mov     rcx, rdi
0x1400590f9  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x1400590fe  mov     [rsp+668h+var_5D0], rsi
0x140059106  lea     rax, [rsp+668h+var_620]
0x14005910b  mov     [rsp+668h+var_638], rax
0x140059110  mov     rdx, r12
0x140059113  lea     rcx, [rsp+668h+var_620]
0x140059118  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005911d  mov     rbx, rax
0x140059120  lea     rdx, aControlname; "--controlName"
0x140059127  lea     rcx, [rsp+668h+var_540]
0x14005912f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140059134  nop
0x140059135  mov     r9, rbx
0x140059138  lea     r8, [rsp+668h+var_5D0]
0x140059140  mov     rdx, rax
0x140059143  mov     rcx, rdi
0x140059146  call    ??$add_option@Uhstring@winrt@@U12@$0A@@App@CLI@@QEAAPEAVOption@1@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUhstring@winrt@@0@Z; CLI::App::add_option<winrt::hstring,winrt::hstring,0>(std::string,winrt::hstring &,std::string)
0x14005914b  lea     rax, [rsp+668h+var_620]
0x140059150  mov     [rsp+668h+var_638], rax
0x140059155  lea     rax, [rsp+668h+var_5B0]
0x14005915d  mov     [rsp+668h+var_540], rax
0x140059165  lea     rax, [rsp+668h+var_5E0]
0x14005916d  mov     [rsp+668h+var_538], rax
0x140059175  lea     rax, [rsp+668h+var_5A0]
0x14005917d  mov     [rsp+668h+var_530], rax
0x140059185  lea     rax, [rsp+668h+var_5C0]
0x14005918d  mov     [rsp+668h+var_528], rax
0x140059195  lea     rax, [rsp+668h+var_5C8]
0x14005919d  mov     [rsp+668h+var_520], rax
0x1400591a5  lea     rax, [rsp+668h+var_5D0]
0x1400591ad  mov     [rsp+668h+var_518], rax
0x1400591b5  lea     rax, [rsp+668h+var_5B8]
0x1400591bd  mov     [rsp+668h+var_510], rax
0x1400591c5  lea     rax, [rsp+668h+var_580]
0x1400591cd  mov     [rsp+668h+var_508], rax
0x1400591d5  lea     rax, [rsp+668h+var_598]
0x1400591dd  mov     [rsp+668h+var_500], rax
0x1400591e5  lea     rax, [rsp+668h+var_558]
0x1400591ed  mov     [rsp+668h+var_4F8], rax
0x1400591f5  mov     [rsp+668h+var_5E8], rsi
0x1400591fd  lea     rcx, [rsp+668h+var_540]
0x140059205  call    std___Global_new_std___Func_impl_no_alloc__lambda_62f806f766e8baecd72c7e4ff4c91d9b__void___lambda_62f806f766e8baecd72c7e4ff4c91d9b___
0x14005920a  mov     [rsp+668h+var_5E8], rax
0x140059212  lea     rdx, [rsp+668h+var_620]
0x140059217  mov     rcx, rdi
  ... truncated ...
```
