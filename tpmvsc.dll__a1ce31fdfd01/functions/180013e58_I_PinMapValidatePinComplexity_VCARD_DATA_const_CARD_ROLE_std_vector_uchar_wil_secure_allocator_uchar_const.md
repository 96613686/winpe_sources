# I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x180013e58`
- end: `0x18001412a`
- name: `?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `722`
- prototype: `_BOOL8 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008324`
- `0x18000a1b8`
- `0x18000b85c`
- `0x180016954`

## callees

- `0x180001ec0`
- `0x1800023c0`
- `0x18000bc48`
- `0x18000c124`
- `0x18000c778`
- `0x18000ca24`
- `0x18000d2c4`
- `0x18000d368`
- `0x18000d5a0`
- `0x18000dca0`
- `0x18000de68`
- `0x180011ee4`
- `0x180013e58`
- `0x1800150c8`
- `0x1800152d0`
- `0x180015364`
- `0x1800153f8`
- `0x180015584`
- `0x1800155dc`
- `0x180015834`
- `0x18003431c`
- `0x1800348a0`

## import_xrefs

- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180013fb1`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180013fb1`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180013f72`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180013f72`

## string_xrefs

- `0x180013e96`: `I_PinMapValidatePinComplexity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BOOL8 __fastcall I_PinMapValidatePinComplexity(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // rax
  _QWORD *v11; // rbx
  char v12; // al
  _QWORD *v13; // r8
  __int64 v14; // rcx
  unsigned int v15; // edi
  int v16; // r9d
  BOOL v17; // ebx
  __int64 v18; // rcx
  int v19; // r9d
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v24; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  unsigned __int64 v28; // [rsp+80h] [rbp-80h]
  _QWORD v29[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[40]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v31[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[40]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v34; // [rsp+138h] [rbp+38h]
  char v35; // [rsp+13Ah] [rbp+3Ah]
  char v36[32]; // [rsp+150h] [rbp+50h] BYREF

  v21 = 1;
  v23 = 0;
  strcpy(v36, "I_PinMapValidatePinComplexity");
  v25[0] = v36;
  v25[1] = &v23;
  v25[2] = &v21;
  lambda_0dbc3d0341bd6fc26d102d280d377aff_::operator()(v25);
  v23 = 1;
  v24 = v25;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  if ( !*(_QWORD *)(a1 + 80) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  v8 = (unsigned int)I_PinMapCardRoleToIndex(a2);
  v9 = *(_QWORD *)(a1 + 80);
  std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(v29);
  std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(
    v26,
    *a3,
    a3[1]);
  if ( v29[3] >= v28 )
  {
    v10 = std::_String_val<std::_Simple_types<char>>::_Myptr(v26);
    std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Assign<char>(v29, v10, v27);
  }
  else
  {
    std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Swap_data(v29, v26);
  }
  std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Tidy_deallocate(v26);
  v31[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,wil::secure_allocator<unsigned short>,wil::secure_allocator<char>>::`vftable';
  v31[3] = std::locale::_Init(1);
  std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(v32);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v33);
  v34 = 0;
  v35 = 0;
  v11 = operator new(0x40u);
  v25[3] = v11;
  std::codecvt<unsigned short,char,_Mbstatet>::codecvt<unsigned short,char,_Mbstatet>(v11, 0);
  *v11 = &std::codecvt<unsigned short,char,_Mbstatet>::`local vftable';
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,wil::secure_allocator<unsigned short>,wil::secure_allocator<char>>::_Init(
    v31,
    v11);
  v12 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v29);
  v13 = v29;
  if ( v12 )
    v13 = (_QWORD *)v29[0];
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,wil::secure_allocator<unsigned short>,wil::secure_allocator<char>>::from_bytes(
    v31,
    v30,
    v13,
    (char *)v13 + v29[2]);
  v22 = 0;
  v15 = a2 - 1;
  if ( v15 )
  {
    if ( v15 != 1 )
    {
      WppTraceIndent(v14, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            (unsigned int)WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids,
            v16,
            87);
      }
      __fastfail(0x57u);
    }
    v17 = (unsigned int)(*((_DWORD *)a3 + 2) - *(_DWORD *)a3 - 4) <= 0x7B;
  }
  else
  {
    if ( (int)PinPolicy::PinPolicyRules::ValidatePin(v9 + 152 * v8 + 104, v30, &v22) < 0 )
    {
      WppTraceIndent(v18, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids,
          v19,
          13);
      }
      __fastfail(0xDu);
    }
    v17 = v22 == 0;
  }
  v21 = v17;
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::_Tidy_deallocate(v30);
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,wil::secure_allocator<unsigned short>,wil::secure_allocator<char>>::~wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,wil::secure_allocator<unsigned short>,wil::secure_allocator<char>>(v31);
  std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Tidy_deallocate(v29);
  WppTraceUnwinder__lambda_0dbc3d0341bd6fc26d102d280d377aff____::_WppTraceUnwinder__lambda_0dbc3d0341bd6fc26d102d280d377aff____(&v24);
  return v17;
}

```

## disassembly

```asm
0x180013e58  push    rbp
0x180013e5a  push    rbx
0x180013e5b  push    rsi
0x180013e5c  push    rdi
0x180013e5d  push    r14
0x180013e5f  push    r15
0x180013e61  lea     rbp, [rsp-88h]
0x180013e69  sub     rsp, 188h
0x180013e70  mov     rax, cs:__security_cookie
0x180013e77  xor     rax, rsp
0x180013e7a  mov     [rbp+0B0h+var_40], rax
0x180013e7e  mov     rsi, r8
0x180013e81  mov     edi, edx
0x180013e83  mov     rbx, rcx
0x180013e86  mov     [rsp+1B0h+var_180], 1
0x180013e8e  mov     [rsp+1B0h+var_178], 0
0x180013e96  movups  xmm0, xmmword ptr cs:aIPinmapvalidat_1; "I_PinMapValidatePinComplexity"
0x180013e9d  movups  xmmword ptr [rbp+0B0h+var_60], xmm0
0x180013ea1  movups  xmm1, xmmword ptr cs:aIPinmapvalidat_1+0Eh; "tePinComplexity"
0x180013ea8  movups  xmmword ptr [rbp+0B0h+var_60+0Eh], xmm1
0x180013eac  lea     rax, [rbp+0B0h+var_60]
0x180013eb0  mov     [rsp+1B0h+var_168], rax
0x180013eb5  lea     rax, [rsp+1B0h+var_178]
0x180013eba  mov     [rsp+1B0h+var_160], rax
0x180013ebf  lea     rax, [rsp+1B0h+var_180]
0x180013ec4  mov     [rsp+1B0h+var_158], rax
0x180013ec9  lea     rcx, [rsp+1B0h+var_168]
0x180013ece  call    _lambda_0dbc3d0341bd6fc26d102d280d377aff___operator__
0x180013ed3  mov     [rsp+1B0h+var_178], 1
0x180013edb  lea     rax, [rsp+1B0h+var_168]
0x180013ee0  mov     [rsp+1B0h+var_170], rax
0x180013ee5  test    rbx, rbx
0x180013ee8  jnz     short loc_180013EEF
0x180013eea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013eef  cmp     qword ptr [rbx+50h], 0
0x180013ef4  jnz     short loc_180013EFB
0x180013ef6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013efb  mov     ecx, edi
0x180013efd  call    I_PinMapCardRoleToIndex
0x180013f02  mov     r14d, eax
0x180013f05  mov     r15, [rbx+50h]
0x180013f09  lea     rcx, [rbp+0B0h+var_128]
0x180013f0d  call    ??0?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@QEAA@XZ; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(void)
0x180013f12  nop
0x180013f13  mov     r8, [rsi+8]
0x180013f17  mov     rdx, [rsi]
0x180013f1a  lea     rcx, [rsp+1B0h+var_148]
0x180013f1f  call    ??$?0PEBE$0A@@?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@QEAA@PEBE0AEBU?$secure_allocator@D@wil@@@Z; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(uchar const *,uchar const *,wil::secure_allocator<char> const &)
0x180013f24  nop
0x180013f25  mov     rcx, [rbp+0B0h+var_130]
0x180013f29  cmp     [rbp+0B0h+var_110], rcx
0x180013f2d  jnb     short loc_180013F3F
0x180013f2f  lea     rdx, [rsp+1B0h+var_148]
0x180013f34  lea     rcx, [rbp+0B0h+var_128]
0x180013f38  call    ?_Swap_data@?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@QEAAXAEAV12@@Z; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Swap_data(std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>> &)
0x180013f3d  jmp     short loc_180013F5B
0x180013f3f  lea     rcx, [rsp+1B0h+var_148]
0x180013f44  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEAAPEADXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180013f49  mov     rdx, rax
0x180013f4c  mov     r8, [rsp+1B0h+var_138]
0x180013f51  lea     rcx, [rbp+0B0h+var_128]
0x180013f55  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@AEAAAEAV01@QEBD_K@Z; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Assign<char>(char const * const,unsigned __int64)
0x180013f5a  nop
0x180013f5b  lea     rcx, [rsp+1B0h+var_148]
0x180013f60  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@AEAAXXZ; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Tidy_deallocate(void)
0x180013f65  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GU?$secure_allocator@G@wil@@U?$secure_allocator@D@4@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,wil::secure_allocator<ushort>,wil::secure_allocator<char>>::`vftable'
0x180013f6c  mov     [rbp+0B0h+var_E0], rax
0x180013f70  mov     cl, 1
0x180013f72  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180013f78  mov     [rbp+0B0h+var_C8], rax
0x180013f7c  lea     rcx, [rbp+0B0h+var_C0]
0x180013f80  call    ??0?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@QEAA@XZ; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(void)
0x180013f85  nop
0x180013f86  lea     rcx, [rbp+0B0h+var_A0]
0x180013f8a  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180013f8f  nop
0x180013f90  mov     [rbp+0B0h+var_78], 0
0x180013f96  mov     [rbp+0B0h+var_76], 0
0x180013f9a  mov     ecx, 40h ; '@'; Size
0x180013f9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013fa4  mov     rbx, rax
0x180013fa7  mov     [rsp+1B0h+var_150], rax
0x180013fac  xor     edx, edx
0x180013fae  mov     rcx, rax
0x180013fb1  call    cs:__imp_??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z; std::codecvt<ushort,char,_Mbstatet>::codecvt<ushort,char,_Mbstatet>(unsigned __int64)
0x180013fb7  lea     rax, ??_S?$codecvt@GDU_Mbstatet@@@std@@6B@; const std::codecvt<ushort,char,_Mbstatet>::`local vftable'
0x180013fbe  mov     [rbx], rax
0x180013fc1  mov     rdx, rbx
0x180013fc4  lea     rcx, [rbp+0B0h+var_E0]
0x180013fc8  call    ?_Init@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GU?$secure_allocator@G@wil@@U?$secure_allocator@D@4@@std@@AEAAXPEBV?$codecvt@GDU_Mbstatet@@@2@@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,wil::secure_allocator<ushort>,wil::secure_allocator<char>>::_Init(std::codecvt<ushort,char,_Mbstatet> const *)
0x180013fcd  nop
0x180013fce  lea     rcx, [rbp+0B0h+var_128]
0x180013fd2  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x180013fd7  lea     r8, [rbp+0B0h+var_128]
0x180013fdb  test    al, al
0x180013fdd  cmovnz  r8, [rbp+0B0h+var_128]
0x180013fe2  mov     r9, [rbp+0B0h+var_118]
0x180013fe6  add     r9, r8
0x180013fe9  lea     rdx, [rbp+0B0h+var_108]
0x180013fed  lea     rcx, [rbp+0B0h+var_E0]
0x180013ff1  call    ?from_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GU?$secure_allocator@G@wil@@U?$secure_allocator@D@4@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@2@PEBD0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,wil::secure_allocator<ushort>,wil::secure_allocator<char>>::from_bytes(char const *,char const *)
0x180013ff6  mov     [rsp+1B0h+var_17C], 0
0x180013ffe  sub     edi, 1
0x180014001  jz      short loc_18001406D
0x180014003  cmp     edi, 1
0x180014006  jz      short loc_18001405B
0x180014008  mov     edx, 2
0x18001400d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014012  lea     rax, WPP_GLOBAL_Control
0x180014019  mov     ebx, 57h ; 'W'
0x18001401e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014025  cmp     rcx, rax
0x180014028  jz      short loc_18001404D
0x18001402a  test    byte ptr [rcx+1Ch], 1
0x18001402e  jz      short loc_18001404D
0x180014030  cmp     byte ptr [rcx+19h], 1
0x180014034  jb      short loc_18001404D
0x180014036  lea     edx, [rbx-5]
0x180014039  mov     [rsp+1B0h+var_190], ebx
0x18001403d  lea     r8, WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids
0x180014044  mov     rcx, [rcx+10h]
0x180014048  call    WPP_SF_sD
0x18001404d  mov     rcx, rbx
0x180014050  int     29h; Win8: RtlFailFast(ecx)
0x180014052  mov     ebx, [rsp+1B0h+var_180]
0x180014056  jmp     loc_1800140E4
0x18001405b  mov     eax, [rsi+8]
0x18001405e  sub     eax, [rsi]
0x180014060  sub     eax, 4
0x180014063  xor     ebx, ebx
0x180014065  cmp     eax, 7Bh ; '{'
0x180014068  setbe   bl
0x18001406b  jmp     short loc_1800140E0
0x18001406d  imul    rcx, r14, 98h
0x180014074  add     rcx, 68h ; 'h'
0x180014078  add     rcx, r15
0x18001407b  lea     r8, [rsp+1B0h+var_17C]
0x180014080  lea     rdx, [rbp+0B0h+var_108]
0x180014084  call    ?ValidatePin@PinPolicyRules@PinPolicy@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@PEAW4PinValidationResult@2@@Z; PinPolicy::PinPolicyRules::ValidatePin(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &,PinPolicy::PinValidationResult *)
0x180014089  test    eax, eax
0x18001408b  jns     short loc_1800140D7
0x18001408d  mov     edx, 2
0x180014092  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014097  lea     rax, WPP_GLOBAL_Control
0x18001409e  mov     ebx, 0Dh
0x1800140a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140aa  cmp     rcx, rax
0x1800140ad  jz      short loc_1800140D2
0x1800140af  test    byte ptr [rcx+1Ch], 1
0x1800140b3  jz      short loc_1800140D2
0x1800140b5  cmp     byte ptr [rcx+19h], 1
0x1800140b9  jb      short loc_1800140D2
0x1800140bb  lea     edx, [rbx+44h]
0x1800140be  mov     [rsp+1B0h+var_190], ebx
0x1800140c2  lea     r8, WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids
0x1800140c9  mov     rcx, [rcx+10h]
0x1800140cd  call    WPP_SF_sD
0x1800140d2  mov     rcx, rbx
0x1800140d5  int     29h; Win8: RtlFailFast(ecx)
0x1800140d7  xor     ebx, ebx
0x1800140d9  cmp     [rsp+1B0h+var_17C], ebx
0x1800140dd  setz    bl
0x1800140e0  mov     [rsp+1B0h+var_180], ebx
0x1800140e4  lea     rcx, [rbp+0B0h+var_108]
0x1800140e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@AEAAXXZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::_Tidy_deallocate(void)
0x1800140ed  nop
0x1800140ee  lea     rcx, [rbp+0B0h+var_E0]
0x1800140f2  call    ??1?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GU?$secure_allocator@G@wil@@U?$secure_allocator@D@4@@std@@UEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,wil::secure_allocator<ushort>,wil::secure_allocator<char>>::~wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,wil::secure_allocator<ushort>,wil::secure_allocator<char>>(void)
0x1800140f7  nop
0x1800140f8  lea     rcx, [rbp+0B0h+var_128]
0x1800140fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@U?$secure_allocator@D@wil@@@std@@AEAAXXZ; std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Tidy_deallocate(void)
0x180014101  nop
0x180014102  lea     rcx, [rsp+1B0h+var_170]
0x180014107  call    WppTraceUnwinder__lambda_0dbc3d0341bd6fc26d102d280d377aff_______WppTraceUnwinder__lambda_0dbc3d0341bd6fc26d102d280d377aff____
0x18001410c  mov     eax, ebx
0x18001410e  mov     rcx, [rbp+0B0h+var_40]
0x180014112  xor     rcx, rsp; StackCookie
0x180014115  call    __security_check_cookie
0x18001411a  add     rsp, 188h
0x180014121  pop     r15
0x180014123  pop     r14
0x180014125  pop     rdi
0x180014126  pop     rsi
0x180014127  pop     rbx
0x180014128  pop     rbp
0x180014129  retn
```
