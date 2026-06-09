# browser::uri_reputation::check_reputation(browser::navigation,std::optional<browser::navigation>,browser::navigation_type,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140003848`
- end: `0x140003cd1`
- name: `?check_reputation@uri_reputation@browser@@YA?AV?$tuple@V?$unique_function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0V?$function@$$A6A?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ@2@@Z@@_NV?$function@$$A6A?AV?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@XZ@std@@@std@@Unavigation@2@V?$optional@Unavigation@browser@@@4@W4navigation_type@2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, int, path *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003b788`

## callees

- `0x140002e70`
- `0x140002edc`
- `0x140002f3c`
- `0x140003274`
- `0x140003848`
- `0x140004190`
- `0x140014994`
- `0x140014ffc`
- `0x14001609c`
- `0x1400160b4`
- `0x140017f18`
- `0x140018190`
- `0x140018300`
- `0x1400183fc`
- `0x140018b58`
- `0x14001b594`
- `0x140021b90`
- `0x140025aa0`
- `0x14003c65c`
- `0x1400411dc`
- `0x140041244`
- `0x140068010`

## import_xrefs

- `SmartScreen!GetEnforcementLevel` at `0x1400038dc`
- `SmartScreen!GetEnforcementLevel` at `0x1400038dc`
- `SmartScreen!FreeExperience` at `0x140003c83`
- `SmartScreen!FreeExperience` at `0x140003c83`
- `SmartScreen!CheckReputation` at `0x140003a1d`
- `SmartScreen!CheckReputation` at `0x140003a1d`

## pseudocode

```c
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
  if ( (int)GetHostFromUri(a2, &v34) < 0
    || ((v10 = v32[0], *((_QWORD *)a5 + 3) <= 7u) ? (v11 = a5) : (v11 = *(path **)a5),
        (int)CheckReputation(v17, v21, v20, v19, v9, v11, v32[0], &v33, &v30, v29) < 0) )
  {
    *(_QWORD *)a1 = off_140069A78;
    *(_QWORD *)(a1 + 56) = a1;
    *(_BYTE *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = off_140069A58;
  }
  else
  {
    v36[0] = off_14006B3A8;
    v37 = v36;
    if ( v29[0] )
    {
      v12 = std::wstring::wstring(v26, v29[0]);
      anonymous_namespace_::StringUtil::ToUtf8(v38, v12);
      path::~path((path *)v26);
      os_smartscreen::ux::UrlRepExperience::UrlRepExperience((os_smartscreen::ux::UrlRepExperience *)v39);
      if ( (int)os_smartscreen::ux::UrlRepExperience::FromJson(v38, v39) < 0 )
      {
        *(_QWORD *)a1 = off_14006D178;
        *(_QWORD *)(a1 + 56) = a1;
        *(_BYTE *)(a1 + 64) = 0;
        *(_QWORD *)(a1 + 72) = off_140069A58;
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
    *(_QWORD *)(a1 + 72) = off_1400699E8;
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
0x140003848  mov     [rsp-8+arg_18], rbx
0x14000384d  push    rbp
0x14000384e  push    rsi
0x14000384f  push    rdi
0x140003850  push    r12
0x140003852  push    r13
0x140003854  push    r14
0x140003856  push    r15
0x140003858  lea     rbp, [rsp-500h]
0x140003860  sub     rsp, 600h
0x140003867  mov     rax, cs:__security_cookie
0x14000386e  xor     rax, rsp
0x140003871  mov     [rbp+530h+var_40], rax
0x140003878  mov     rsi, r8
0x14000387b  mov     r14, rdx
0x14000387e  mov     rdi, rcx
0x140003881  mov     [rbp+530h+var_2B0], rcx
0x140003888  mov     [rbp+530h+var_2D8], rdx
0x14000388f  mov     [rbp+530h+var_2D0], r8
0x140003896  mov     r13, [rbp+530h+arg_20]
0x14000389d  mov     [rbp+530h+var_2C8], r13
0x1400038a4  xor     r12d, r12d
0x1400038a7  lea     r15d, [r12+1]
0x1400038ac  mov     ebx, r12d
0x1400038af  test    r9d, r9d
0x1400038b2  jz      short loc_1400038BD
0x1400038b4  cmp     r9d, r15d
0x1400038b7  setnz   bl
0x1400038ba  add     ebx, r15d
0x1400038bd  mov     [rbp+530h+var_2BC], r12d
0x1400038c4  mov     [rbp+530h+var_2BF], r12b
0x1400038cb  xor     r8d, r8d
0x1400038ce  lea     rdx, [rbp+530h+var_2BF]
0x1400038d5  lea     rcx, [rbp+530h+var_2BC]
0x1400038dc  call    cs:__imp_GetEnforcementLevel
0x1400038e2  mov     [rsp+630h+var_5C8], r12
0x1400038e7  mov     [rsp+630h+var_5D0], r12
0x1400038ec  mov     [rsp+630h+var_5D8], r12
0x1400038f1  cmp     [r14+40h], r12b
0x1400038f5  jz      short loc_14000390F
0x1400038f7  lea     rax, [r14+20h]
0x1400038fb  mov     [rsp+630h+var_5C8], rax
0x140003900  cmp     qword ptr [rax+18h], 7
0x140003905  jbe     short loc_14000390F
0x140003907  mov     rax, [rax]
0x14000390a  mov     [rsp+630h+var_5C8], rax
0x14000390f  cmp     [rsi+48h], r12b
0x140003913  jz      short loc_140003949
0x140003915  cmp     qword ptr [rsi+18h], 7
0x14000391a  jbe     short loc_140003926
0x14000391c  mov     rax, [rsi]
0x14000391f  mov     [rsp+630h+var_5D0], rax
0x140003924  jmp     short loc_14000392B
0x140003926  mov     [rsp+630h+var_5D0], rsi
0x14000392b  cmp     [rsi+40h], r12b
0x14000392f  jz      short loc_140003949
0x140003931  lea     rax, [rsi+20h]
0x140003935  mov     [rsp+630h+var_5D8], rax
0x14000393a  cmp     qword ptr [rax+18h], 7
0x14000393f  jbe     short loc_140003949
0x140003941  mov     rax, [rax]
0x140003944  mov     [rsp+630h+var_5D8], rax
0x140003949  cmp     qword ptr [r14+18h], 7
0x14000394e  jbe     short loc_14000395D
0x140003950  mov     r12, [r14]
0x140003953  mov     [rsp+630h+var_5E0], r12
0x140003958  xor     r12d, r12d
0x14000395b  jmp     short loc_140003962
0x14000395d  mov     [rsp+630h+var_5E0], r14
0x140003962  mov     [rbp+530h+var_2B0], r12
0x140003969  mov     [rbp+530h+var_2C0], r12b
0x140003970  mov     [rbp+530h+var_2E0], r12
0x140003977  lea     rax, [rbp+530h+var_2E0]
0x14000397e  mov     [rsp+630h+var_5B8], rax
0x140003983  mov     [rbp+530h+var_5B0], r15b
0x140003987  xorps   xmm0, xmm0
0x14000398a  movups  [rbp+530h+var_2A0], xmm0
0x140003991  xorps   xmm1, xmm1
0x140003994  movdqu  [rbp+530h+var_290], xmm1
0x14000399c  lea     rcx, [rbp+530h+var_2A0]
0x1400039a3  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400039a8  nop
0x1400039a9  lea     rdx, [rbp+530h+var_2A0]
0x1400039b0  mov     rcx, r14
0x1400039b3  call    ?GetHostFromUri@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetHostFromUri(std::wstring const &,std::wstring &)
0x1400039b8  test    eax, eax
0x1400039ba  js      loc_140003C3D
0x1400039c0  mov     r12d, [rbp+530h+var_2BC]
0x1400039c7  cmp     qword ptr [r13+18h], 7
0x1400039cc  jbe     short loc_1400039D4
0x1400039ce  mov     rax, [r13+0]
0x1400039d2  jmp     short loc_1400039D7
0x1400039d4  mov     rax, r13
0x1400039d7  lea     rcx, [rbp+530h+var_2E0]
0x1400039de  mov     [rsp+630h+var_5E8], rcx
0x1400039e3  lea     rcx, [rbp+530h+var_2C0]
0x1400039ea  mov     [rsp+630h+var_5F0], rcx
0x1400039ef  lea     rcx, [rbp+530h+var_2B0]
0x1400039f6  mov     [rsp+630h+var_5F8], rcx
0x1400039fb  mov     [rsp+630h+var_600], r12d
0x140003a00  mov     [rsp+630h+var_608], rax
0x140003a05  mov     dword ptr [rsp+630h+var_610], ebx
0x140003a09  mov     r9, [rsp+630h+var_5D8]
0x140003a0e  mov     r8, [rsp+630h+var_5D0]
0x140003a13  mov     rdx, [rsp+630h+var_5C8]
0x140003a18  mov     rcx, [rsp+630h+var_5E0]
0x140003a1d  call    cs:__imp_CheckReputation
0x140003a23  test    eax, eax
0x140003a25  js      loc_140003C3A
0x140003a2b  lea     rax, off_14006B3A8
0x140003a32  mov     [rbp+530h+var_280], rax
0x140003a39  lea     rax, [rbp+530h+var_280]
0x140003a40  mov     [rbp+530h+var_248], rax
0x140003a47  mov     rdx, [rbp+530h+var_2E0]
0x140003a4e  test    rdx, rdx
0x140003a51  jz      loc_140003BAE
0x140003a57  lea     rcx, [rbp+530h+var_550]
0x140003a5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003a60  nop
0x140003a61  mov     rdx, rax
0x140003a64  lea     rcx, [rbp+530h+var_240]
0x140003a6b  call    _anonymous_namespace___StringUtil__ToUtf8
0x140003a70  nop
0x140003a71  lea     rcx, [rbp+530h+var_550]; this
0x140003a75  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003a7a  lea     rcx, [rbp+530h+var_220]; this
0x140003a81  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(void)
0x140003a86  nop
0x140003a87  lea     rdx, [rbp+530h+var_220]
0x140003a8e  lea     rcx, [rbp+530h+var_240]
0x140003a95  call    ?FromJson@UrlRepExperience@ux@os_smartscreen@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAU123@@Z; os_smartscreen::ux::UrlRepExperience::FromJson(std::string const &,os_smartscreen::ux::UrlRepExperience *)
0x140003a9a  test    eax, eax
0x140003a9c  jns     short loc_140003AF3
0x140003a9e  lea     rax, off_14006D178
0x140003aa5  mov     [rdi], rax
0x140003aa8  mov     [rdi+38h], rdi
0x140003aac  mov     byte ptr [rdi+40h], 0
0x140003ab0  lea     rax, off_140069A58
0x140003ab7  mov     [rdi+48h], rax
0x140003abb  lea     rcx, [rbp+530h+var_220]; this
0x140003ac2  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003ac7  nop
0x140003ac8  lea     rcx, [rbp+530h+var_240]
0x140003acf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140003ad4  nop
0x140003ad5  lea     rcx, [rbp+530h+var_280]
0x140003adc  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140003ae1  nop
0x140003ae2  lea     rcx, [rbp+530h+var_2A0]; this
0x140003ae9  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003aee  jmp     loc_140003C7C
0x140003af3  lea     rdx, [rbp+530h+var_220]; struct os_smartscreen::ux::UrlRepExperience *
0x140003afa  lea     rcx, [rbp+530h+var_530]; this
0x140003afe  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(os_smartscreen::ux::UrlRepExperience const &)
0x140003b03  mov     rbx, rax
0x140003b06  mov     [rsp+630h+var_5E0], rax
0x140003b0b  mov     rdx, rax
0x140003b0e  lea     rcx, [rbp+530h+var_130]
0x140003b15  call    ??0UrlRepExperience@ux@os_smartscreen@@QEAA@$$QEAU012@@Z; os_smartscreen::ux::UrlRepExperience::UrlRepExperience(os_smartscreen::ux::UrlRepExperience &&)
0x140003b1a  nop
0x140003b1b  mov     rcx, rbx; this
0x140003b1e  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003b23  nop
0x140003b24  test    r12d, r12d
0x140003b27  jz      short loc_140003B37
0x140003b29  sub     r12d, 1
0x140003b2d  jz      short loc_140003B3A
0x140003b2f  mov     r15d, 2
0x140003b35  jmp     short loc_140003B3A
0x140003b37  xor     r15d, r15d
0x140003b3a  mov     [rbp+530h+var_2BC], r15d
0x140003b41  lea     rax, [rbp+530h+var_2A0]
0x140003b48  mov     [rsp+630h+var_610], rax
0x140003b4d  lea     r9, [rbp+530h+var_2BC]
0x140003b54  mov     r8, r14
0x140003b57  lea     rdx, [rbp+530h+var_130]
0x140003b5e  lea     rcx, [rbp+530h+var_440]
0x140003b65  call    _lambda_a932841438ede1183e14688560a7a758____lambda_a932841438ede1183e14688560a7a758_
0x140003b6a  nop
0x140003b6b  mov     rdx, rax
0x140003b6e  lea     rcx, [rbp+530h+var_280]
0x140003b75  call    std__function_std__optional_os_smartscreen__ux__UrlRepExperience____cdecl_void____operator___lambda_a932841438ede1183e14688560a7a758__0_
0x140003b7a  nop
0x140003b7b  lea     rcx, [rbp+530h+var_440]; this
0x140003b82  call    _lambda_a932841438ede1183e14688560a7a758_____lambda_a932841438ede1183e14688560a7a758_
0x140003b87  nop
0x140003b88  lea     rcx, [rbp+530h+var_130]; this
0x140003b8f  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003b94  nop
0x140003b95  lea     rcx, [rbp+530h+var_220]; this
0x140003b9c  call    ??1UrlRepExperience@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::UrlRepExperience::~UrlRepExperience(void)
0x140003ba1  nop
0x140003ba2  lea     rcx, [rbp+530h+var_240]
0x140003ba9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140003bae  mov     rbx, [rbp+530h+var_2B0]
0x140003bb5  xor     r15d, r15d
0x140003bb8  mov     [rbp+530h+var_568], r15
0x140003bbc  lea     rdx, [rbp+530h+var_280]
0x140003bc3  lea     rcx, [rbp+530h+var_5A0]
0x140003bc7  call    ?_Reset_move@?$_Func_class@V?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,> &&)
0x140003bcc  mov     al, [rbp+530h+var_2C0]
0x140003bd2  mov     [rbp+530h+var_560], al
0x140003bd5  mov     [rbp+530h+var_558], rbx
0x140003bd9  mov     [rdi+38h], r15
0x140003bdd  lea     rdx, [rbp+530h+var_5A0]
0x140003be1  mov     rcx, rdi
0x140003be4  call    ?_Reset_move@?$_Func_class@V?$optional@UUrlRepExperience@ux@os_smartscreen@@@std@@$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,>::_Reset_move(std::_Func_class<std::optional<os_smartscreen::ux::UrlRepExperience>,> &&)
0x140003be9  mov     al, [rbp+530h+var_560]
0x140003bec  mov     [rdi+40h], al
0x140003bef  mov     rax, [rbp+530h+var_558]
0x140003bf3  mov     [rdi+50h], rax
0x140003bf7  lea     rax, off_1400699E8
0x140003bfe  mov     [rdi+48h], rax
0x140003c02  lea     rcx, [rbp+530h+var_5A0]
0x140003c06  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140003c0b  nop
0x140003c0c  mov     rcx, [rbp+530h+var_248]
0x140003c13  test    rcx, rcx
0x140003c16  jz      short loc_140003C5A
0x140003c18  mov     rax, [rcx]
0x140003c1b  lea     rdx, [rbp+530h+var_280]
0x140003c22  cmp     rcx, rdx
0x140003c25  setnz   dl
0x140003c28  mov     rax, [rax+20h]
0x140003c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c31  mov     [rbp+530h+var_248], r15
0x140003c38  jmp     short loc_140003C5A
0x140003c3a  xor     r12d, r12d
0x140003c3d  lea     rax, off_140069A78
0x140003c44  mov     [rdi], rax
0x140003c47  mov     [rdi+38h], rdi
0x140003c4b  mov     [rdi+40h], r12b
0x140003c4f  lea     rax, off_140069A58
0x140003c56  mov     [rdi+48h], rax
0x140003c5a  mov     rdx, qword ptr [rbp+530h+var_290+8]
0x140003c61  cmp     rdx, 7
0x140003c65  jbe     short loc_140003C7C
0x140003c67  lea     rdx, ds:2[rdx*2]
0x140003c6f  mov     rcx, qword ptr [rbp+530h+var_2A0]
0x140003c76  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003c7b  nop
0x140003c7c  mov     rcx, [rbp+530h+var_2E0]
0x140003c83  call    cs:__imp_FreeExperience
0x140003c89  nop
0x140003c8a  mov     rcx, r14; this
0x140003c8d  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x140003c92  nop
0x140003c93  mov     rcx, rsi
0x140003c96  call    ??1?$_Optional_destruct_base@UExperienceContent@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(void)
0x140003c9b  nop
0x140003c9c  mov     rcx, r13; this
0x140003c9f  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003ca4  mov     rax, rdi
0x140003ca7  mov     rcx, [rbp+530h+var_40]
0x140003cae  xor     rcx, rsp; StackCookie
0x140003cb1  call    __security_check_cookie
0x140003cb6  mov     rbx, [rsp+630h+arg_18]
0x140003cbe  add     rsp, 600h
0x140003cc5  pop     r15
0x140003cc7  pop     r14
0x140003cc9  pop     r13
0x140003ccb  pop     r12
0x140003ccd  pop     rdi
0x140003cce  pop     rsi
0x140003ccf  pop     rbp
0x140003cd0  retn
```
