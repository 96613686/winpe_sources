# Brain::FindBetterPackage(bool,bool,UusPackage const &,std::function<void (std::filesystem::path const &,char const *)>)

- ea: `0x180039904`
- end: `0x180039ed8`
- name: `?FindBetterPackage@Brain@@CA?AV?$optional@VUusPackage@@@std@@_N0AEBVUusPackage@@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z`
- size: `1492`
- prototype: `UusPackage *__fastcall(UusPackage *this, char, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180037064`

## callees

- `0x1800089f4`
- `0x180009e64`
- `0x18000a748`
- `0x18000ae24`
- `0x180029644`
- `0x180032760`
- `0x180032a58`
- `0x180039858`
- `0x180039904`
- `0x18003babc`
- `0x1800427d0`
- `0x180047a30`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003996e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180039c88`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003996e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180039c88`

## pseudocode

```c
UusPackage *__fastcall Brain::FindBetterPackage(UusPackage *this, char a2, char a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r13
  char v6; // r14
  char v7; // r15
  UusPackage *v8; // rdi
  __int64 v9; // rsi
  const struct std::filesystem::path *RootFolder; // r12
  char v11; // r12
  _BYTE *v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, _BYTE *); // r8
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  int v16; // r8d
  int v17; // ecx
  __int64 v18; // rcx
  void (__fastcall *v19)(__int64, unsigned __int64); // rax
  const char *v21; // [rsp+20h] [rbp-288h]
  char v23; // [rsp+31h] [rbp-277h]
  __int128 v24; // [rsp+40h] [rbp-268h] BYREF
  __m128i si128; // [rsp+50h] [rbp-258h]
  __int64 v26; // [rsp+78h] [rbp-230h]
  UusPackage *v27; // [rsp+90h] [rbp-218h]
  __int128 *v28; // [rsp+A0h] [rbp-208h]
  _BYTE v29[56]; // [rsp+A8h] [rbp-200h] BYREF
  _BYTE *v30; // [rsp+E0h] [rbp-1C8h]
  __int64 v31; // [rsp+E8h] [rbp-1C0h]
  _BYTE *v32; // [rsp+F0h] [rbp-1B8h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-1B0h] BYREF
  __m128i v34; // [rsp+108h] [rbp-1A0h]
  __int128 v35; // [rsp+118h] [rbp-190h] BYREF
  __m128i v36; // [rsp+128h] [rbp-180h]
  _QWORD v37[6]; // [rsp+140h] [rbp-168h] BYREF
  _BYTE v38[8]; // [rsp+170h] [rbp-138h] BYREF
  unsigned __int64 v39; // [rsp+178h] [rbp-130h]
  char v40; // [rsp+198h] [rbp-110h]
  _QWORD v41[6]; // [rsp+1A0h] [rbp-108h] BYREF
  _BYTE v42[8]; // [rsp+1D0h] [rbp-D8h] BYREF
  unsigned __int64 v43; // [rsp+1D8h] [rbp-D0h]
  char v44; // [rsp+1F8h] [rbp-B0h]
  _QWORD v45[11]; // [rsp+200h] [rbp-A8h] BYREF
  char v46; // [rsp+258h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v5 = a4;
  v6 = a3;
  v7 = a2;
  v8 = this;
  v27 = this;
  v9 = a5;
  v31 = a5;
  LODWORD(v32) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v32, 0);
  try
  {
    v23 = v7;
    v46 = 0;
    RootFolder = (const struct std::filesystem::path *)UusState::GetRootFolder(&v24);
    if ( v46 )
    {
      (*(void (__fastcall **)(_QWORD *, _QWORD))v45[0])(v45, 0);
      v46 = 0;
    }
    UusExclusion::UusExclusion((UusExclusion *)v45, RootFolder);
    v46 = 1;
    std::wstring::_Tidy_deallocate(&v24);
    v11 = a2;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x224,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\Brain.cpp",
      "Failed to load exclusion list.",
      v21);
    v5 = a4;
    v6 = a3;
    v7 = v23;
    v8 = v27;
    v11 = v23;
    v9 = v31;
  }
  v32 = v29;
  v12 = 0;
  v30 = 0;
  v13 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v9 + 56);
  if ( v13 )
  {
    v12 = (_BYTE *)(**v13)(*(_QWORD *)(v9 + 56), v29);
    v30 = v12;
  }
  v32 = v29;
  v28 = &v24;
  v26 = 0;
  if ( v12 )
    v26 = (**(__int64 (__fastcall ***)(_BYTE *, __int128 *))v12)(v12, &v24);
  UusPackage::GetLatestPackage(v41, 0, &v24);
  if ( v30 )
  {
    LOBYTE(v14) = v30 != v29;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v30 + 32LL))(v30, v14);
    v30 = 0;
  }
  Brain::GetPreviewPackage((UusPackage *)v37);
  if ( !v7 || !v6 )
  {
    v35 = 0;
    v36.m128i_i64[0] = 0;
    v36.m128i_i64[1] = 7;
    LOWORD(v35) = 0;
    v33 = 0;
    v34.m128i_i64[0] = 0;
    v34.m128i_i64[1] = 7;
    LOWORD(v33) = 0;
    if ( !v7 )
    {
      if ( v40 )
      {
        UusVersion::GetString(v38, &v24);
        std::wstring::_Tidy_deallocate(&v35);
        v35 = v24;
        v36 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24) = 0;
        std::wstring::_Tidy_deallocate(&v24);
        if ( v40 )
        {
          (*(void (__fastcall **)(_QWORD *, _QWORD))v37[0])(v37, 0);
          v40 = 0;
        }
      }
    }
    if ( !v6 )
    {
      if ( v44 )
      {
        UusVersion::GetString(v42, &v24);
        std::wstring::_Tidy_deallocate(&v33);
        v33 = v24;
        v34 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24) = 0;
        std::wstring::_Tidy_deallocate(&v24);
        if ( v44 )
        {
          (*(void (__fastcall **)(_QWORD *, _QWORD))v41[0])(v41, 0);
          v44 = 0;
        }
      }
    }
    if ( v36.m128i_i64[0] || v34.m128i_i64[0] )
    {
      LODWORD(v32) = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v32, 0);
      LOBYTE(v16) = v11;
      uus::UndockedUpdateTelemetry::UusRestrictPreviewPackageScan(v17, (unsigned int)&v35, v16, 0, (__int64)&v33, v6);
    }
    std::wstring::_Tidy_deallocate(&v33);
    std::wstring::_Tidy_deallocate(&v35);
  }
  if ( !v44 || v43 <= *(_QWORD *)(v5 + 56) )
  {
LABEL_41:
    v15 = v39;
    goto LABEL_42;
  }
  if ( !v40 || (v15 = v39, v43 > v39) )
  {
    if ( !v46 || !UusExclusion::IsExcluded((UusExclusion *)v45, v43) )
    {
      *((_BYTE *)v8 + 88) = 0;
      if ( v44 )
      {
        UusPackage::UusPackage(v8, (const struct UusPackage *)v41);
        *((_BYTE *)v8 + 88) = 1;
      }
      goto LABEL_33;
    }
    goto LABEL_41;
  }
LABEL_42:
  if ( v40 && v15 > *(_QWORD *)(v5 + 56) && (!v46 || !UusExclusion::IsExcluded((UusExclusion *)v45, v15)) )
  {
    *((_BYTE *)v8 + 88) = 0;
    if ( v40 )
    {
      UusPackage::UusPackage(v8, (const struct UusPackage *)v37);
      *((_BYTE *)v8 + 88) = 1;
    }
LABEL_33:
    if ( v40 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v37[0])(v37, 0);
    if ( v44 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v41[0])(v41, 0);
    if ( v46 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v45[0])(v45, 0);
    v18 = *(_QWORD *)(v9 + 56);
    if ( v18 )
    {
      v19 = *(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v18 + 32LL);
LABEL_57:
      LOBYTE(v15) = v18 != v9;
      v19(v18, v15);
      *(_QWORD *)(v9 + 56) = 0;
      return v8;
    }
    return v8;
  }
  *((_BYTE *)v8 + 88) = 0;
  if ( v40 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v37[0])(v37, 0);
  if ( v44 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v41[0])(v41, 0);
  if ( v46 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v45[0])(v45, 0);
  v18 = *(_QWORD *)(v9 + 56);
  if ( v18 )
  {
    v19 = *(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v18 + 32LL);
    goto LABEL_57;
  }
  return v8;
}

```

## disassembly

```asm
0x180039904  mov     r11, rsp
0x180039907  mov     [r11+20h], r9
0x18003990b  mov     [r11+18h], r8b
0x18003990f  push    rbx
0x180039910  push    rsi
0x180039911  push    rdi
0x180039912  push    r12
0x180039914  push    r13
0x180039916  push    r14
0x180039918  push    r15
0x18003991a  sub     rsp, 270h
0x180039921  mov     rax, cs:__security_cookie
0x180039928  xor     rax, rsp
0x18003992b  mov     [rsp+2A8h+var_48], rax
0x180039933  mov     r13, r9
0x180039936  mov     r14b, r8b
0x180039939  mov     r15b, dl
0x18003993c  mov     [rsp+2A8h+var_278], dl
0x180039940  mov     rdi, rcx
0x180039943  mov     [r11-218h], rcx
0x18003994a  mov     rsi, [rsp+2A8h+arg_20]
0x180039952  mov     [r11-1C0h], rsi
0x180039959  xor     ebx, ebx
0x18003995b  mov     dword ptr [rsp+2A8h+var_1B8], ebx
0x180039962  xor     r8d, r8d
0x180039965  lea     rdx, [r11-1B8h]
0x18003996c  xor     ecx, ecx
0x18003996e  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180039974  mov     [rsp+2A8h+var_277], r15b
0x180039979  mov     [rsp+2A8h+var_50], bl
0x180039980  lea     rcx, [rsp+2A8h+var_268]
0x180039985  call    ?GetRootFolder@UusState@@SA?AVpath@filesystem@std@@XZ; UusState::GetRootFolder(void)
0x18003998a  mov     r12, rax
0x18003998d  cmp     [rsp+2A8h+var_50], bl
0x180039994  jz      short loc_1800399B7
0x180039996  mov     rax, [rsp+2A8h+var_A8]
0x18003999e  xor     edx, edx
0x1800399a0  lea     rcx, [rsp+2A8h+var_A8]
0x1800399a8  mov     rax, [rax]
0x1800399ab  call    _guard_dispatch_icall
0x1800399b0  mov     [rsp+2A8h+var_50], bl
0x1800399b7  mov     rdx, r12; struct std::filesystem::path *
0x1800399ba  lea     rcx, [rsp+2A8h+var_A8]; this
0x1800399c2  call    ??0UusExclusion@@QEAA@AEBVpath@filesystem@std@@@Z; UusExclusion::UusExclusion(std::filesystem::path const &)
0x1800399c7  mov     [rsp+2A8h+var_50], 1
0x1800399cf  lea     rcx, [rsp+2A8h+var_268]
0x1800399d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800399d9  nop
0x1800399da  mov     r12b, [rsp+2A8h+var_278]
0x1800399df  jmp     short loc_180039A0B
0x1800399e1  xor     ebx, ebx
0x1800399e3  mov     r13, [rsp+2A8h+arg_18]
0x1800399eb  mov     r14b, [rsp+2A8h+arg_10]
0x1800399f3  mov     r15b, [rsp+2A8h+var_277]
0x1800399f8  mov     rdi, [rsp+2A8h+var_218]
0x180039a00  mov     r12b, r15b
0x180039a03  mov     rsi, [rsp+2A8h+var_1C0]
0x180039a0b  lea     rax, [rsp+2A8h+var_200]
0x180039a13  mov     [rsp+2A8h+var_1B8], rax
0x180039a1b  mov     rcx, rbx
0x180039a1e  mov     [rsp+2A8h+var_1C8], rbx
0x180039a26  mov     r8, [rsi+38h]
0x180039a2a  test    r8, r8
0x180039a2d  jz      short loc_180039A50
0x180039a2f  mov     rax, [r8]
0x180039a32  lea     rdx, [rsp+2A8h+var_200]
0x180039a3a  mov     rcx, r8
0x180039a3d  mov     rax, [rax]
0x180039a40  call    _guard_dispatch_icall
0x180039a45  mov     rcx, rax
0x180039a48  mov     [rsp+2A8h+var_1C8], rax
0x180039a50  lea     rax, [rsp+2A8h+var_200]
0x180039a58  mov     [rsp+2A8h+var_1B8], rax
0x180039a60  lea     rax, [rsp+2A8h+var_268]
0x180039a65  mov     [rsp+2A8h+var_208], rax
0x180039a6d  mov     [rsp+2A8h+var_230], rbx
0x180039a72  test    rcx, rcx
0x180039a75  jz      short loc_180039A8C
0x180039a77  mov     rax, [rcx]
0x180039a7a  lea     rdx, [rsp+2A8h+var_268]
0x180039a7f  mov     rax, [rax]
0x180039a82  call    _guard_dispatch_icall
0x180039a87  mov     [rsp+2A8h+var_230], rax
0x180039a8c  lea     r8, [rsp+2A8h+var_268]
0x180039a91  xor     edx, edx
0x180039a93  lea     rcx, [rsp+2A8h+var_108]
0x180039a9b  call    ?GetLatestPackage@UusPackage@@SA?AV?$optional@VUusPackage@@@std@@PEAV?$map@_KVUusPackage@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KVUusPackage@@@std@@@3@@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z; UusPackage::GetLatestPackage(std::map<unsigned __int64,UusPackage> *,std::function<void (std::filesystem::path const &,char const *)>)
0x180039aa0  nop
0x180039aa1  mov     rcx, [rsp+2A8h+var_1C8]
0x180039aa9  test    rcx, rcx
0x180039aac  jz      short loc_180039AD0
0x180039aae  lea     rax, [rsp+2A8h+var_200]
0x180039ab6  cmp     rcx, rax
0x180039ab9  setnz   dl
0x180039abc  mov     rax, [rcx]
0x180039abf  mov     rax, [rax+20h]
0x180039ac3  call    _guard_dispatch_icall
0x180039ac8  mov     [rsp+2A8h+var_1C8], rbx
0x180039ad0  lea     rcx, [rsp+2A8h+var_168]; this
0x180039ad8  call    ?GetPreviewPackage@Brain@@CA?AV?$optional@VUusPackage@@@std@@XZ; Brain::GetPreviewPackage(void)
0x180039add  nop
0x180039ade  test    r15b, r15b
0x180039ae1  jz      short loc_180039AEC
0x180039ae3  test    r14b, r14b
0x180039ae6  jnz     loc_180039CCF
0x180039aec  xorps   xmm0, xmm0
0x180039aef  movups  [rsp+2A8h+var_190], xmm0
0x180039af7  mov     qword ptr [rsp+2A8h+var_180], rbx
0x180039aff  mov     eax, 7
0x180039b04  mov     qword ptr [rsp+2A8h+var_180+8], rax
0x180039b0c  mov     word ptr [rsp+2A8h+var_190], bx
0x180039b14  movups  [rsp+2A8h+var_1B0], xmm0
0x180039b1c  mov     qword ptr [rsp+2A8h+var_1A0], rbx
0x180039b24  mov     qword ptr [rsp+2A8h+var_1A0+8], rax
0x180039b2c  mov     word ptr [rsp+2A8h+var_1B0], bx
0x180039b34  test    r15b, r15b
0x180039b37  jnz     loc_180039BCA
0x180039b3d  cmp     [rsp+2A8h+var_110], bl
0x180039b44  jz      loc_180039BCA
0x180039b4a  lea     rdx, [rsp+2A8h+var_268]
0x180039b4f  lea     rcx, [rsp+2A8h+var_138]
0x180039b57  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180039b5c  lea     rcx, [rsp+2A8h+var_190]
0x180039b64  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039b69  movups  xmm0, [rsp+2A8h+var_268]
0x180039b6e  movups  [rsp+2A8h+var_190], xmm0
0x180039b76  movups  xmm1, [rsp+2A8h+var_258]
0x180039b7b  movups  [rsp+2A8h+var_180], xmm1
0x180039b83  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180039b8b  movdqu  [rsp+2A8h+var_258], xmm0
0x180039b91  mov     word ptr [rsp+2A8h+var_268], bx
0x180039b96  lea     rcx, [rsp+2A8h+var_268]
0x180039b9b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039ba0  cmp     [rsp+2A8h+var_110], bl
0x180039ba7  jz      short loc_180039BCA
0x180039ba9  mov     rax, [rsp+2A8h+var_168]
0x180039bb1  xor     edx, edx
0x180039bb3  lea     rcx, [rsp+2A8h+var_168]
0x180039bbb  mov     rax, [rax]
0x180039bbe  call    _guard_dispatch_icall
0x180039bc3  mov     [rsp+2A8h+var_110], bl
0x180039bca  test    r14b, r14b
0x180039bcd  jnz     loc_180039C60
0x180039bd3  cmp     [rsp+2A8h+var_B0], bl
0x180039bda  jz      loc_180039C60
0x180039be0  lea     rdx, [rsp+2A8h+var_268]
0x180039be5  lea     rcx, [rsp+2A8h+var_D8]
0x180039bed  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180039bf2  lea     rcx, [rsp+2A8h+var_1B0]
0x180039bfa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039bff  movups  xmm0, [rsp+2A8h+var_268]
0x180039c04  movups  [rsp+2A8h+var_1B0], xmm0
0x180039c0c  movups  xmm1, [rsp+2A8h+var_258]
0x180039c11  movups  [rsp+2A8h+var_1A0], xmm1
0x180039c19  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180039c21  movdqu  [rsp+2A8h+var_258], xmm0
0x180039c27  mov     word ptr [rsp+2A8h+var_268], bx
0x180039c2c  lea     rcx, [rsp+2A8h+var_268]
0x180039c31  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c36  cmp     [rsp+2A8h+var_B0], bl
0x180039c3d  jz      short loc_180039C60
0x180039c3f  mov     rax, [rsp+2A8h+var_108]
0x180039c47  xor     edx, edx
0x180039c49  lea     rcx, [rsp+2A8h+var_108]
0x180039c51  mov     rax, [rax]
0x180039c54  call    _guard_dispatch_icall
0x180039c59  mov     [rsp+2A8h+var_B0], bl
0x180039c60  cmp     qword ptr [rsp+2A8h+var_180], rbx
0x180039c68  jnz     short loc_180039C74
0x180039c6a  cmp     qword ptr [rsp+2A8h+var_1A0], rbx
0x180039c72  jz      short loc_180039CB4
0x180039c74  mov     dword ptr [rsp+2A8h+var_1B8], ebx
0x180039c7b  xor     r8d, r8d
0x180039c7e  lea     rdx, [rsp+2A8h+var_1B8]
0x180039c86  xor     ecx, ecx
0x180039c88  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180039c8e  mov     [rsp+2A8h+var_280], r14b
0x180039c93  lea     rax, [rsp+2A8h+var_1B0]
0x180039c9b  mov     [rsp+2A8h+var_288], rax
0x180039ca0  xor     r9d, r9d
0x180039ca3  mov     r8b, r12b
0x180039ca6  lea     rdx, [rsp+2A8h+var_190]
0x180039cae  call    ?UusRestrictPreviewPackageScan@UndockedUpdateTelemetry@uus@@SAX_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0010@Z; uus::UndockedUpdateTelemetry::UusRestrictPreviewPackageScan(bool,std::wstring const &,bool,bool,std::wstring const &,bool)
0x180039cb3  nop
0x180039cb4  lea     rcx, [rsp+2A8h+var_1B0]
0x180039cbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039cc1  nop
0x180039cc2  lea     rcx, [rsp+2A8h+var_190]
0x180039cca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039ccf  cmp     [rsp+2A8h+var_B0], bl
0x180039cd6  jz      loc_180039DCE
0x180039cdc  mov     rax, [rsp+2A8h+var_D0]
0x180039ce4  cmp     rax, [r13+38h]
0x180039ce8  jbe     loc_180039DCE
0x180039cee  cmp     [rsp+2A8h+var_110], bl
0x180039cf5  jz      short loc_180039D08
0x180039cf7  mov     rdx, [rsp+2A8h+var_130]
0x180039cff  cmp     rax, rdx
0x180039d02  jbe     loc_180039DD6
0x180039d08  cmp     [rsp+2A8h+var_50], bl
0x180039d0f  jz      short loc_180039D29
0x180039d11  mov     rdx, rax; unsigned __int64
0x180039d14  lea     rcx, [rsp+2A8h+var_A8]; this
0x180039d1c  call    ?IsExcluded@UusExclusion@@QEBA_N_K@Z; UusExclusion::IsExcluded(unsigned __int64)
0x180039d21  test    al, al
0x180039d23  jnz     loc_180039DCE
0x180039d29  mov     [rdi+58h], bl
0x180039d2c  cmp     [rsp+2A8h+var_B0], bl
0x180039d33  jz      short loc_180039D49
0x180039d35  lea     rdx, [rsp+2A8h+var_108]; struct UusPackage *
0x180039d3d  mov     rcx, rdi; this
0x180039d40  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x180039d45  mov     byte ptr [rdi+58h], 1
0x180039d49  cmp     [rsp+2A8h+var_110], bl
0x180039d50  jz      short loc_180039D6D
0x180039d52  mov     rax, [rsp+2A8h+var_168]
0x180039d5a  xor     edx, edx
0x180039d5c  lea     rcx, [rsp+2A8h+var_168]
0x180039d64  mov     rax, [rax]
0x180039d67  call    _guard_dispatch_icall
0x180039d6c  nop
0x180039d6d  cmp     [rsp+2A8h+var_B0], bl
0x180039d74  jz      short loc_180039D91
0x180039d76  mov     rax, [rsp+2A8h+var_108]
0x180039d7e  xor     edx, edx
0x180039d80  lea     rcx, [rsp+2A8h+var_108]
0x180039d88  mov     rax, [rax]
0x180039d8b  call    _guard_dispatch_icall
0x180039d90  nop
0x180039d91  cmp     [rsp+2A8h+var_50], bl
0x180039d98  jz      short loc_180039DB5
0x180039d9a  mov     rax, [rsp+2A8h+var_A8]
0x180039da2  xor     edx, edx
0x180039da4  lea     rcx, [rsp+2A8h+var_A8]
0x180039dac  mov     rax, [rax]
0x180039daf  call    _guard_dispatch_icall
0x180039db4  nop
0x180039db5  mov     rcx, [rsi+38h]
0x180039db9  test    rcx, rcx
0x180039dbc  jz      loc_180039EB2
0x180039dc2  mov     rax, [rcx]
0x180039dc5  mov     rax, [rax+20h]
0x180039dc9  jmp     loc_180039EA3
0x180039dce  mov     rdx, [rsp+2A8h+var_130]; unsigned __int64
0x180039dd6  cmp     [rsp+2A8h+var_110], bl
0x180039ddd  jz      short loc_180039E24
0x180039ddf  cmp     rdx, [r13+38h]
0x180039de3  jbe     short loc_180039E24
0x180039de5  cmp     [rsp+2A8h+var_50], bl
0x180039dec  jz      short loc_180039DFF
0x180039dee  lea     rcx, [rsp+2A8h+var_A8]; this
0x180039df6  call    ?IsExcluded@UusExclusion@@QEBA_N_K@Z; UusExclusion::IsExcluded(unsigned __int64)
0x180039dfb  test    al, al
0x180039dfd  jnz     short loc_180039E24
0x180039dff  mov     [rdi+58h], bl
0x180039e02  cmp     [rsp+2A8h+var_110], bl
0x180039e09  jz      short loc_180039E1F
0x180039e0b  lea     rdx, [rsp+2A8h+var_168]; struct UusPackage *
0x180039e13  mov     rcx, rdi; this
0x180039e16  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x180039e1b  mov     byte ptr [rdi+58h], 1
0x180039e1f  jmp     loc_180039D49
0x180039e24  mov     [rdi+58h], bl
0x180039e27  cmp     [rsp+2A8h+var_110], bl
0x180039e2e  jz      short loc_180039E4B
0x180039e30  mov     rax, [rsp+2A8h+var_168]
0x180039e38  xor     edx, edx
0x180039e3a  lea     rcx, [rsp+2A8h+var_168]
0x180039e42  mov     rax, [rax]
0x180039e45  call    _guard_dispatch_icall
0x180039e4a  nop
0x180039e4b  cmp     [rsp+2A8h+var_B0], bl
0x180039e52  jz      short loc_180039E6F
0x180039e54  mov     rax, [rsp+2A8h+var_108]
0x180039e5c  xor     edx, edx
0x180039e5e  lea     rcx, [rsp+2A8h+var_108]
0x180039e66  mov     rax, [rax]
0x180039e69  call    _guard_dispatch_icall
0x180039e6e  nop
0x180039e6f  cmp     [rsp+2A8h+var_50], bl
0x180039e76  jz      short loc_180039E93
0x180039e78  mov     rax, [rsp+2A8h+var_A8]
0x180039e80  xor     edx, edx
0x180039e82  lea     rcx, [rsp+2A8h+var_A8]
0x180039e8a  mov     rax, [rax]
0x180039e8d  call    _guard_dispatch_icall
0x180039e92  nop
0x180039e93  mov     rcx, [rsi+38h]
0x180039e97  test    rcx, rcx
0x180039e9a  jz      short loc_180039EB2
0x180039e9c  mov     r8, [rcx]
0x180039e9f  mov     rax, [r8+20h]
0x180039ea3  cmp     rcx, rsi
0x180039ea6  setnz   dl
0x180039ea9  call    _guard_dispatch_icall
0x180039eae  mov     [rsi+38h], rbx
0x180039eb2  mov     rax, rdi
0x180039eb5  mov     rcx, [rsp+2A8h+var_48]
0x180039ebd  xor     rcx, rsp; StackCookie
0x180039ec0  call    __security_check_cookie
  ... truncated ...
```
