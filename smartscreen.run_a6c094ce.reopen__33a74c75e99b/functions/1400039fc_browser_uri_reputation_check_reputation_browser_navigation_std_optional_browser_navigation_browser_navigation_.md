# browser::uri_reputation::check_reputation(browser::navigation,std::optional<browser::navigation>,browser::navigation_type,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1400039fc`
- end: `0x140003e98`
- name: `?check_reputation@uri_reputation@browser@@YA?AV?$tuple@V?$unique_function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0V?$function@$$A6A?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ@2@@Z@@_NV?$function@$$A6A?AV?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@XZ@std@@@std@@Unavigation@2@V?$optional@Unavigation@browser@@@4@W4navigation_type@2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `1180`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ce24`

## callees

- `0x140002f70`
- `0x140002fe4`
- `0x140003044`
- `0x1400033a0`
- `0x1400039fc`
- `0x140004370`
- `0x1400154d8`
- `0x140015b94`
- `0x140016c8c`
- `0x140016ca8`
- `0x140018bd0`
- `0x140018e4c`
- `0x140018fc0`
- `0x1400190c0`
- `0x140019844`
- `0x14001c58c`
- `0x140022d04`
- `0x140026c20`
- `0x14003dd2c`
- `0x140042940`
- `0x1400429a8`
- `0x14006a010`

## import_xrefs

- `SmartScreen!GetEnforcementLevel` at `0x140003a90`
- `SmartScreen!GetEnforcementLevel` at `0x140003a90`
- `SmartScreen!FreeExperience` at `0x140003e43`
- `SmartScreen!FreeExperience` at `0x140003e43`
- `SmartScreen!CheckReputation` at `0x140003bd7`
- `SmartScreen!CheckReputation` at `0x140003bd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall browser::uri_reputation::check_reputation(__int64 a1, __int64 *a2, __int64 a3, int a4, path *a5)
{
  int v8; // r15d
  int v9; // ebx
  int v10; // r12d
  path *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  _QWORD *v15; // rdx
  __int64 *v17; // [rsp+50h] [rbp-B0h]
  os_smartscreen::ux::UrlRepExperience *v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+60h] [rbp-A0h]
  __int64 *v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[56]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-38h]
  char v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  _BYTE v26[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[240]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v28[352]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v29[4]; // [rsp+350h] [rbp+250h] BYREF
  char v30; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v31[3]; // [rsp+371h] [rbp+271h] BYREF
  _DWORD v32[3]; // [rsp+374h] [rbp+274h] BYREF
  __int64 v33; // [rsp+380h] [rbp+280h] BYREF
  __int128 v34; // [rsp+390h] [rbp+290h] BYREF
  __int128 v35; // [rsp+3A0h] [rbp+2A0h]
  _QWORD v36[7]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _QWORD *v37; // [rsp+3E8h] [rbp+2E8h]
  _BYTE v38[32]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v39[240]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v40[240]; // [rsp+500h] [rbp+400h] BYREF

  v33 = a1;
  v29[1] = a2;
  v29[2] = a3;
  v29[3] = a5;
  v8 = 1;
  v9 = 0;
  if ( a4 )
  {
    LOBYTE(v9) = a4 != 1;
    ++v9;
  }
  v32[0] = 0;
  v31[0] = 0;
  GetEnforcementLevel(v32, v31, 0);
  v21 = 0;
  v20 = 0;
  v19 = 0;
  if ( *((_BYTE *)a2 + 64) )
  {
    v21 = a2 + 4;
    if ( (unsigned __int64)a2[7] > 7 )
      v21 = (__int64 *)a2[4];
  }
  if ( *(_BYTE *)(a3 + 72) )
  {
    v20 = *(_QWORD *)(a3 + 24) <= 7u ? a3 : *(_QWORD *)a3;
    if ( *(_BYTE *)(a3 + 64) )
    {
      v19 = a3 + 32;
      if ( *(_QWORD *)(a3 + 56) > 7u )
        v19 = *(_QWORD *)(a3 + 32);
    }
  }
  if ( (unsigned __int64)a2[3] <= 7 )
    v17 = a2;
  else
    v17 = (__int64 *)*a2;
  v33 = 0;
  v30 = 0;
  v29[0] = 0;
  v34 = 0;
  v35 = 0;
  std::wstring::_Construct_empty(&v34);
  if ( (int)GetHostFromUri((const WCHAR *)a2, (__int64)&v34) < 0
    || ((v10 = v32[0], *((_QWORD *)a5 + 3) <= 7u) ? (v11 = a5) : (v11 = *(path **)a5),
        (int)CheckReputation(v17, v21, v20, v19, v9, v11, v32[0], &v33, &v30, v29) < 0) )
  {
    *(_QWORD *)a1 = off_14006BA78;
    *(_QWORD *)(a1 + 56) = a1;
    *(_BYTE *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = off_14006BA58;
  }
  else
  {
    v36[0] = off_14006D3A8;
    v37 = v36;
    if ( v29[0] )
    {
      v12 = std::wstring::wstring(v26, v29[0]);
      anonymous_namespace_::StringUtil::ToUtf8(v38, v12);
      path::~path((path *)v26);
      os_smartscreen::ux::UrlRepExperience::UrlRepExperience((os_smartscreen::ux::UrlRepExperience *)v39);
      if ( (int)os_smartscreen::ux::UrlRepExperience::FromJson(v38, v39) < 0 )
      {
        *(_QWORD *)a1 = off_14006F178;
        *(_QWORD *)(a1 + 56) = a1;
        *(_BYTE *)(a1 + 64) = 0;
        *(_QWORD *)(a1 + 72) = off_14006BA58;
        os_smartscreen::ux::UrlRepExperience::~UrlRepExperience((os_smartscreen::ux::UrlRepExperience *)v39);
        std::string::_Tidy_deallocate(v38);
        std::_Func_class<void,>::~_Func_class<void,>(v36);
        path::~path((path *)&v34);
        goto LABEL_34;
      }
      v18 = (os_smartscreen::ux::UrlRepExperience *)os_smartscreen::ux::UrlRepExperience::UrlRepExperience(
                                                      (os_smartscreen::ux::UrlRepExperience *)v27,
                                                      (const struct os_smartscreen::ux::UrlRepExperience *)v39);
      os_smartscreen::ux::UrlRepExperience::UrlRepExperience(v40, v18);
      os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(v18);
      if ( v10 )
      {
        if ( v10 != 1 )
          v8 = 2;
      }
      else
      {
        v8 = 0;
      }
      v32[0] = v8;
      v13 = lambda_a932841438ede1183e14688560a7a758_::_lambda_a932841438ede1183e14688560a7a758_(v28, v40, a2, v32, &v34);
      std::function_std::optional_os_smartscreen::ux::UrlRepExperience____cdecl_void__::operator___lambda_a932841438ede1183e14688560a7a758__0_(
        v36,
        v13);
      lambda_a932841438ede1183e14688560a7a758_::__lambda_a932841438ede1183e14688560a7a758_((os_smartscreen::ux::UrlRepExperience *)v28);
      os_smartscreen::ux::UrlRepExperience::~UrlRepExperience((os_smartscreen::ux::UrlRepExperience *)v40);
      os_smartscreen::ux::UrlRepExperience::~UrlRepExperience((os_smartscreen::ux::UrlRepExperience *)v39);
      std::string::_Tidy_deallocate(v38);
    }
    v14 = v33;
    v23 = 0;
    std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(v22, v36);
    v24 = v30;
    v25 = v14;
    *(_QWORD *)(a1 + 56) = 0;
    std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(a1, v22);
    *(_BYTE *)(a1 + 64) = v24;
    *(_QWORD *)(a1 + 80) = v25;
    *(_QWORD *)(a1 + 72) = off_14006B9E8;
    std::_Func_class<void,>::~_Func_class<void,>(v22);
    if ( v37 )
    {
      v15 = v36;
      LOBYTE(v15) = v37 != v36;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v37 + 32LL))(v37, v15);
      v37 = 0;
    }
  }
  if ( *((_QWORD *)&v35 + 1) > 7u )
    std::_Deallocate<16>(v34, 2LL * *((_QWORD *)&v35 + 1) + 2);
LABEL_34:
  FreeExperience(v29[0]);
  browser::navigation::~navigation((browser::navigation *)a2);
  std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(a3);
  path::~path(a5);
  return a1;
}

```

## disassembly

```asm
0x1400039fc  mov     [rsp-8+arg_18], rbx
0x140003a01  push    rbp
0x140003a02  push    rsi
0x140003a03  push    rdi
0x140003a04  push    r12
0x140003a06  push    r13
0x140003a08  push    r14
0x140003a0a  push    r15
0x140003a0c  lea     rbp, [rsp-500h]
0x140003a14  sub     rsp, 600h
0x140003a1b  mov     rax, cs:__security_cookie
0x140003a22  xor     rax, rsp
0x140003a25  mov     [rbp+530h+var_40], rax
0x140003a2c  mov     rsi, r8
0x140003a2f  mov     r14, rdx
0x140003a32  mov     rdi, rcx
0x140003a35  mov     [rbp+530h+var_2B0], rcx
0x140003a3c  mov     [rbp+530h+var_2D8], rdx
0x140003a43  mov     [rbp+530h+var_2D0], r8
0x140003a4a  mov     r13, [rbp+530h+arg_20]
0x140003a51  mov     [rbp+530h+var_2C8], r13
0x140003a58  xor     r12d, r12d
0x140003a5b  lea     r15d, [r12+1]
0x140003a60  mov     ebx, r12d
0x140003a63  test    r9d, r9d
0x140003a66  jz      short loc_140003A71
0x140003a68  cmp     r9d, r15d
0x140003a6b  setnz   bl
0x140003a6e  add     ebx, r15d
0x140003a71  mov     [rbp+530h+var_2BC], r12d
0x140003a78  mov     [rbp+530h+var_2BF], r12b
0x140003a7f  xor     r8d, r8d
0x140003a82  lea     rdx, [rbp+530h+var_2BF]
0x140003a89  lea     rcx, [rbp+530h+var_2BC]
0x140003a90  call    cs:__imp_GetEnforcementLevel
0x140003a97  nop     dword ptr [rax+rax+00h]
0x140003a9c  mov     [rsp+630h+var_5C8], r12
0x140003aa1  mov     [rsp+630h+var_5D0], r12
0x140003aa6  mov     [rsp+630h+var_5D8], r12
0x140003aab  cmp     [r14+40h], r12b
0x140003aaf  jz      short loc_140003AC9
0x140003ab1  lea     rax, [r14+20h]
0x140003ab5  mov     [rsp+630h+var_5C8], rax
0x140003aba  cmp     qword ptr [rax+18h], 7
0x140003abf  jbe     short loc_140003AC9
0x140003ac1  mov     rax, [rax]
0x140003ac4  mov     [rsp+630h+var_5C8], rax
0x140003ac9  cmp     [rsi+48h], r12b
0x140003acd  jz      short loc_140003B03
0x140003acf  cmp     qword ptr [rsi+18h], 7
0x140003ad4  jbe     short loc_140003AE0
0x140003ad6  mov     rax, [rsi]
0x140003ad9  mov     [rsp+630h+var_5D0], rax
0x140003ade  jmp     short loc_140003AE5
0x140003ae0  mov     [rsp+630h+var_5D0], rsi
0x140003ae5  cmp     [rsi+40h], r12b
0x140003ae9  jz      short loc_140003B03
0x140003aeb  lea     rax, [rsi+20h]
0x140003aef  mov     [rsp+630h+var_5D8], rax
0x140003af4  cmp     qword ptr [rax+18h], 7
0x140003af9  jbe     short loc_140003B03
0x140003afb  mov     rax, [rax]
0x140003afe  mov     [rsp+630h+var_5D8], rax
0x140003b03  cmp     qword ptr [r14+18h], 7
0x140003b08  jbe     short loc_140003B17
0x140003b0a  mov     r12, [r14]
0x140003b0d  mov     [rsp+630h+var_5E0], r12
0x140003b12  xor     r12d, r12d
0x140003b15  jmp     short loc_140003B1C
0x140003b17  mov     [rsp+630h+var_5E0], r14
0x140003b1c  mov     [rbp+530h+var_2B0], r12
0x140003b23  mov     [rbp+530h+var_2C0], r12b
0x140003b2a  mov     [rbp+530h+var_2E0], r12
0x140003b31  lea     rax, [rbp+530h+var_2E0]
0x140003b38  mov     [rsp+630h+var_5B8], rax
0x140003b3d  mov     [rbp+530h+var_5B0], r15b
0x140003b41  xorps   xmm0, xmm0
0x140003b44  movups  [rbp+530h+var_2A0], xmm0
0x140003b4b  xorps   xmm1, xmm1
0x140003b4e  movdqu  [rbp+530h+var_290], xmm1
0x140003b56  lea     rcx, [rbp+530h+var_2A0]
0x140003b5d  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140003b62  nop
0x140003b63  lea     rdx, [rbp+530h+var_2A0]
0x140003b6a  mov     rcx, r14
0x140003b6d  call    ?GetHostFromUri@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetHostFromUri(std::wstring const &,std::wstring &)
0x140003b72  test    eax, eax
0x140003b74  js      loc_140003DFD
0x140003b7a  mov     r12d, [rbp+530h+var_2BC]
0x140003b81  cmp     qword ptr [r13+18h], 7
0x140003b86  jbe     short loc_140003B8E
0x140003b88  mov     rax, [r13+0]
0x140003b8c  jmp     short loc_140003B91
0x140003b8e  mov     rax, r13
0x140003b91  lea     rcx, [rbp+530h+var_2E0]
0x140003b98  mov     [rsp+630h+var_5E8], rcx
0x140003b9d  lea     rcx, [rbp+530h+var_2C0]
0x140003ba4  mov     [rsp+630h+var_5F0], rcx
0x140003ba9  lea     rcx, [rbp+530h+var_2B0]
0x140003bb0  mov     [rsp+630h+var_5F8], rcx
0x140003bb5  mov     [rsp+630h+var_600], r12d
0x140003bba  mov     [rsp+630h+var_608], rax
0x140003bbf  mov     dword ptr [rsp+630h+var_610], ebx
0x140003bc3  mov     r9, [rsp+630h+var_5D8]
0x140003bc8  mov     r8, [rsp+630h+var_5D0]
0x140003bcd  mov     rdx, [rsp+630h+var_5C8]
0x140003bd2  mov     rcx, [rsp+630h+var_5E0]
0x140003bd7  call    cs:__imp_CheckReputation
0x140003bde  nop     dword ptr [rax+rax+00h]
0x140003be3  test    eax, eax
0x140003be5  js      loc_140003DFA
0x140003beb  lea     rax, off_14006D3A8
0x140003bf2  mov     [rbp+530h+var_280], rax
0x140003bf9  lea     rax, [rbp+530h+var_280]
0x140003c00  mov     [rbp+530h+var_248], rax
0x140003c07  mov     rdx, [rbp+530h+var_2E0]
0x140003c0e  test    rdx, rdx
0x140003c11  jz      loc_140003D6E
0x140003c17  lea     rcx, [rbp+530h+var_550]
0x140003c1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003c20  nop
0x140003c21  mov     rdx, rax
0x140003c24  lea     rcx, [rbp+530h+var_240]
0x140003c2b  call    _anonymous_namespace___StringUtil__ToUtf8
0x140003c30  nop
0x140003c31  lea     rcx, [rbp+530h+var_550]; this
0x140003c35  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003c3a  lea     rcx, [rbp+530h+var_220]; this
0x140003c41  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(void)
0x140003c46  nop
0x140003c47  lea     rdx, [rbp+530h+var_220]
0x140003c4e  lea     rcx, [rbp+530h+var_240]
0x140003c55  call    ?FromJson@UrlRepExperience@ux@os_smartscreen@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAU123@@Z; os_smartscreen::ux::UrlRepExperience::FromJson(std::string const &,os_smartscreen::ux::UrlRepExperience *)
0x140003c5a  test    eax, eax
0x140003c5c  jns     short loc_140003CB3
0x140003c5e  lea     rax, off_14006F178
0x140003c65  mov     [rdi], rax
0x140003c68  mov     [rdi+38h], rdi
0x140003c6c  mov     byte ptr [rdi+40h], 0
0x140003c70  lea     rax, off_14006BA58
0x140003c77  mov     [rdi+48h], rax
0x140003c7b  lea     rcx, [rbp+530h+var_220]; this
0x140003c82  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003c87  nop
0x140003c88  lea     rcx, [rbp+530h+var_240]
0x140003c8f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140003c94  nop
0x140003c95  lea     rcx, [rbp+530h+var_280]
0x140003c9c  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140003ca1  nop
0x140003ca2  lea     rcx, [rbp+530h+var_2A0]; this
0x140003ca9  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003cae  jmp     loc_140003E3C
0x140003cb3  lea     rdx, [rbp+530h+var_220]; struct os_smartscreen::ux::UrlRepExperience *
0x140003cba  lea     rcx, [rbp+530h+var_530]; this
0x140003cbe  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(os_smartscreen::ux::UrlRepExperience const &)
0x140003cc3  mov     rbx, rax
0x140003cc6  mov     [rsp+630h+var_5E0], rax
0x140003ccb  mov     rdx, rax
0x140003cce  lea     rcx, [rbp+530h+var_130]
0x140003cd5  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@$$QEAU012@@Z; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(os_smartscreen::ux::UrlRepExperience &&)
0x140003cda  nop
0x140003cdb  mov     rcx, rbx; this
0x140003cde  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003ce3  nop
0x140003ce4  test    r12d, r12d
0x140003ce7  jz      short loc_140003CF7
0x140003ce9  sub     r12d, 1
0x140003ced  jz      short loc_140003CFA
0x140003cef  mov     r15d, 2
0x140003cf5  jmp     short loc_140003CFA
0x140003cf7  xor     r15d, r15d
0x140003cfa  mov     [rbp+530h+var_2BC], r15d
0x140003d01  lea     rax, [rbp+530h+var_2A0]
0x140003d08  mov     [rsp+630h+var_610], rax
0x140003d0d  lea     r9, [rbp+530h+var_2BC]
0x140003d14  mov     r8, r14
0x140003d17  lea     rdx, [rbp+530h+var_130]
0x140003d1e  lea     rcx, [rbp+530h+var_440]
0x140003d25  call    _lambda_a932841438ede1183e14688560a7a758____lambda_a932841438ede1183e14688560a7a758_
0x140003d2a  nop
0x140003d2b  mov     rdx, rax
0x140003d2e  lea     rcx, [rbp+530h+var_280]
0x140003d35  call    std__function_std__optional_os_smartscreen__ux__UrlRepExperience____cdecl_void____operator___lambda_a932841438ede1183e14688560a7a758__0_
0x140003d3a  nop
0x140003d3b  lea     rcx, [rbp+530h+var_440]; this
0x140003d42  call    _lambda_a932841438ede1183e14688560a7a758_____lambda_a932841438ede1183e14688560a7a758_
0x140003d47  nop
0x140003d48  lea     rcx, [rbp+530h+var_130]; this
0x140003d4f  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003d54  nop
0x140003d55  lea     rcx, [rbp+530h+var_220]; this
0x140003d5c  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003d61  nop
0x140003d62  lea     rcx, [rbp+530h+var_240]
0x140003d69  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140003d6e  mov     rbx, [rbp+530h+var_2B0]
0x140003d75  xor     r15d, r15d
0x140003d78  mov     [rbp+530h+var_568], r15
0x140003d7c  lea     rdx, [rbp+530h+var_280]
0x140003d83  lea     rcx, [rbp+530h+var_5A0]
0x140003d87  call    ?_Reset_move@?$_Func_class@V?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,> &&)
0x140003d8c  mov     al, [rbp+530h+var_2C0]
0x140003d92  mov     [rbp+530h+var_560], al
0x140003d95  mov     [rbp+530h+var_558], rbx
0x140003d99  mov     [rdi+38h], r15
0x140003d9d  lea     rdx, [rbp+530h+var_5A0]
0x140003da1  mov     rcx, rdi
0x140003da4  call    ?_Reset_move@?$_Func_class@V?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,> &&)
0x140003da9  mov     al, [rbp+530h+var_560]
0x140003dac  mov     [rdi+40h], al
0x140003daf  mov     rax, [rbp+530h+var_558]
0x140003db3  mov     [rdi+50h], rax
0x140003db7  lea     rax, off_14006B9E8
0x140003dbe  mov     [rdi+48h], rax
0x140003dc2  lea     rcx, [rbp+530h+var_5A0]
0x140003dc6  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140003dcb  nop
0x140003dcc  mov     rcx, [rbp+530h+var_248]
0x140003dd3  test    rcx, rcx
0x140003dd6  jz      short loc_140003E1A
0x140003dd8  mov     rax, [rcx]
0x140003ddb  lea     rdx, [rbp+530h+var_280]
0x140003de2  cmp     rcx, rdx
0x140003de5  setnz   dl
0x140003de8  mov     rax, [rax+20h]
0x140003dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003df1  mov     [rbp+530h+var_248], r15
0x140003df8  jmp     short loc_140003E1A
0x140003dfa  xor     r12d, r12d
0x140003dfd  lea     rax, off_14006BA78
0x140003e04  mov     [rdi], rax
0x140003e07  mov     [rdi+38h], rdi
0x140003e0b  mov     [rdi+40h], r12b
0x140003e0f  lea     rax, off_14006BA58
0x140003e16  mov     [rdi+48h], rax
0x140003e1a  mov     rdx, qword ptr [rbp+530h+var_290+8]
0x140003e21  cmp     rdx, 7
0x140003e25  jbe     short loc_140003E3C
0x140003e27  lea     rdx, ds:2[rdx*2]
0x140003e2f  mov     rcx, qword ptr [rbp+530h+var_2A0]
0x140003e36  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003e3b  nop
0x140003e3c  mov     rcx, [rbp+530h+var_2E0]
0x140003e43  call    cs:__imp_FreeExperience
0x140003e4a  nop     dword ptr [rax+rax+00h]
0x140003e4f  nop
0x140003e50  mov     rcx, r14; this
0x140003e53  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x140003e58  nop
0x140003e59  mov     rcx, rsi
0x140003e5c  call    ??1?$_Optional_destruct_base@UExperienceContent@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(void)
0x140003e61  nop
0x140003e62  mov     rcx, r13; this
0x140003e65  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003e6a  mov     rax, rdi
0x140003e6d  mov     rcx, [rbp+530h+var_40]
0x140003e74  xor     rcx, rsp; StackCookie
0x140003e77  call    __security_check_cookie
0x140003e7c  mov     rbx, [rsp+630h+arg_18]
0x140003e84  add     rsp, 600h
0x140003e8b  pop     r15
0x140003e8d  pop     r14
0x140003e8f  pop     r13
0x140003e91  pop     r12
0x140003e93  pop     rdi
0x140003e94  pop     rsi
0x140003e95  pop     rbp
0x140003e96  retn
```
