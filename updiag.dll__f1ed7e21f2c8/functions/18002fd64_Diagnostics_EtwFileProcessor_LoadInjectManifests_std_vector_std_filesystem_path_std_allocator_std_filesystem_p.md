# Diagnostics::EtwFileProcessor::LoadInjectManifests(std::vector<std::filesystem::path,std::allocator<std::filesystem::path>> const &)

- ea: `0x18002fd64`
- end: `0x18003003f`
- name: `?LoadInjectManifests@EtwFileProcessor@Diagnostics@@CA?AV?$vector@V?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@V?$allocator@V?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@@2@@std@@AEBV?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@4@@Z`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800301cc`

## callees

- `0x180018b04`
- `0x180018d28`
- `0x180018eec`
- `0x18001adcc`
- `0x18002fd64`
- `0x1800468c4`
- `0x1800544c8`
- `0x180066998`
- `0x18006704c`
- `0x1800670a4`
- `0x18008fe00`
- `0x180095af0`

## import_xrefs

- `tdh!TdhLoadManifestFromBinary` at `0x18002fee9`
- `tdh!TdhLoadManifestFromBinary` at `0x18002fee9`

## string_xrefs

- `0x18002ff7e`: `TdhLoadManifestFromBinary failed for inject ETL: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Diagnostics::EtwFileProcessor::LoadInjectManifests(__int64 a1, __int64 *a2)
{
  int v3; // edi
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // rax
  int v7; // edi
  __int128 *v8; // rax
  struct std::error_code *v9; // r8
  bool v10; // si
  const struct std::filesystem::path *v11; // r9
  __int128 *p_Src; // rdx
  unsigned int ManifestFromBinary; // eax
  const char *v14; // r9
  _OWORD *v15; // rsi
  __m128i v16; // xmm1
  _OWORD *v17; // rax
  const char *v18; // rax
  __int64 *v19; // rdx
  __int64 v21; // [rsp+30h] [rbp-99h]
  __int128 Src; // [rsp+38h] [rbp-91h] BYREF
  __m128i v23; // [rsp+48h] [rbp-81h]
  char v24[8]; // [rsp+58h] [rbp-71h] BYREF
  void ***v25; // [rsp+60h] [rbp-69h]
  __int128 v26; // [rsp+68h] [rbp-61h] BYREF
  __int64 v27; // [rsp+78h] [rbp-51h]
  __int64 v28; // [rsp+80h] [rbp-49h]
  __int128 v29; // [rsp+90h] [rbp-39h]
  __int64 v30; // [rsp+A0h] [rbp-29h]
  __int128 v31; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v32; // [rsp+C0h] [rbp-9h] BYREF
  __m128i v33; // [rsp+D0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v30 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = 1;
  v4 = *a2;
  v5 = a2[1];
  if ( *a2 != v5 )
  {
    do
    {
      std::wstring::wstring((__int64)&Src, v4);
      v6 = std::wstring::append(&Src);
      v32 = 0;
      v33 = 0u;
      v32 = *(_OWORD *)v6;
      v33 = *(__m128i *)(v6 + 16);
      *(_QWORD *)(v6 + 16) = 0;
      *(_QWORD *)(v6 + 24) = 7;
      *(_WORD *)v6 = 0;
      v7 = v3 | 6;
      std::wstring::~wstring((__int64)&Src);
      v8 = &v32;
      if ( v33.m128i_i64[1] > 7uLL )
        v8 = (__int128 *)v32;
      *(_QWORD *)&v29 = v8;
      *((_QWORD *)&v29 + 1) = v33.m128i_i64[0];
      v31 = v29;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v26, &v31);
      v3 = v7 | 8;
      LODWORD(v21) = v3;
      *(_QWORD *)v24 = 0;
      v25 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      v10 = std::filesystem::exists((std::filesystem *)&v26, (const struct std::filesystem::path *)v24, v9);
      if ( *(_DWORD *)v24 )
        std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v24, (const struct std::error_code *)&v26, v11);
      std::wstring::~wstring((__int64)&v26);
      if ( v10 )
      {
        Src = v32;
        v23 = v33;
        v33.m128i_i64[0] = 0;
        v33.m128i_i64[1] = 7;
        LOWORD(v32) = 0;
        *(_QWORD *)&v31 = &Src;
        p_Src = &Src;
        if ( _mm_srli_si128(v23, 8).m128i_u64[0] > 7 )
          p_Src = (__int128 *)Src;
        ManifestFromBinary = TdhLoadManifestFromBinary(p_Src);
        v14 = (const char *)ManifestFromBinary;
        if ( ManifestFromBinary )
        {
          if ( ManifestFromBinary != 183 )
          {
            v18 = (const char *)&Src;
            if ( v23.m128i_i64[1] > 7uLL )
              v18 = (const char *)Src;
            wil::details::in1diag3::Log_Win32Msg(
              retaddr,
              (void *)0x16E,
              (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
              v14,
              (unsigned int)"TdhLoadManifestFromBinary failed for inject ETL: %ls",
              v18,
              v21);
          }
          *(_QWORD *)&v31 = 0;
          v3 |= 0x10u;
          std::wstring::~wstring((__int64)&Src);
          v15 = 0;
          v17 = 0;
        }
        else
        {
          v15 = operator new(0x20u);
          *(_QWORD *)&v31 = v15;
          v26 = Src;
          v16 = v23;
          v23.m128i_i64[0] = 0;
          v23.m128i_i64[1] = 7;
          LOWORD(Src) = 0;
          *v15 = v26;
          v15[1] = v16;
          v27 = 0;
          v28 = 7;
          LOWORD(v26) = 0;
          std::wstring::~wstring((__int64)&v26);
          *(_QWORD *)&v31 = v15;
          v3 |= 0x10u;
          std::wstring::~wstring((__int64)&Src);
          v17 = v15;
        }
        if ( v15 )
        {
          v19 = *(__int64 **)(a1 + 8);
          if ( v19 == *(__int64 **)(a1 + 16) )
          {
            std::vector<std::unique_ptr<Diagnostics::TdhManifest>>::_Emplace_reallocate<std::unique_ptr<Diagnostics::TdhManifest>>(
              (__int64 **)a1,
              v19,
              (__int64 *)&v31);
          }
          else
          {
            *(_QWORD *)&v31 = 0;
            *v19 = (__int64)v17;
            *(_QWORD *)(a1 + 8) += 8LL;
          }
        }
        std::unique_ptr<Diagnostics::TdhManifest>::~unique_ptr<Diagnostics::TdhManifest>((const char **)&v31);
      }
      std::wstring::~wstring((__int64)&v32);
      v4 += 32;
    }
    while ( v4 != v5 );
  }
  return a1;
}

```

## disassembly

```asm
0x18002fd64  mov     [rsp-8+arg_10], rbx
0x18002fd69  push    rbp
0x18002fd6a  push    rsi
0x18002fd6b  push    rdi
0x18002fd6c  push    r12
0x18002fd6e  push    r13
0x18002fd70  push    r14
0x18002fd72  push    r15
0x18002fd74  lea     rbp, [rsp-27h]
0x18002fd79  sub     rsp, 0F0h
0x18002fd80  mov     rax, cs:__security_cookie
0x18002fd87  xor     rax, rsp
0x18002fd8a  mov     [rbp+57h+var_40], rax
0x18002fd8e  mov     rbx, rcx
0x18002fd91  mov     [rbp+57h+var_80], rcx
0x18002fd95  xor     r12d, r12d
0x18002fd98  mov     dword ptr [rsp+120h+var_F0], r12d
0x18002fd9d  xorps   xmm0, xmm0
0x18002fda0  movups  xmmword ptr [rcx], xmm0
0x18002fda3  mov     [rcx], r12
0x18002fda6  mov     [rcx+8], r12
0x18002fdaa  mov     [rcx+10h], r12
0x18002fdae  lea     edi, [r12+1]
0x18002fdb3  mov     dword ptr [rsp+120h+var_F0], edi
0x18002fdb7  mov     r14, [rdx]
0x18002fdba  mov     r15, [rdx+8]
0x18002fdbe  cmp     r14, r15
0x18002fdc1  jz      loc_180030000
0x18002fdc7  lea     r13d, [r12+7]
0x18002fdcc  mov     rdx, r14
0x18002fdcf  lea     rcx, [rsp+120h+Src]
0x18002fdd4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002fdd9  or      edi, 2
0x18002fddc  mov     dword ptr [rsp+120h+var_F0], edi
0x18002fde0  mov     r8d, 0Bh
0x18002fde6  lea     rdx, aInjectEtl; "_inject.etl"
0x18002fded  lea     rcx, [rsp+120h+Src]; Src
0x18002fdf2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18002fdf7  xorps   xmm0, xmm0
0x18002fdfa  movups  [rbp+57h+var_60], xmm0
0x18002fdfe  mov     qword ptr [rbp+57h+var_50], r12
0x18002fe02  mov     qword ptr [rbp+57h+var_50+8], r12
0x18002fe06  movups  xmm0, xmmword ptr [rax]
0x18002fe09  movups  [rbp+57h+var_60], xmm0
0x18002fe0d  movups  xmm1, xmmword ptr [rax+10h]
0x18002fe11  movups  [rbp+57h+var_50], xmm1
0x18002fe15  mov     [rax+10h], r12
0x18002fe19  mov     [rax+18h], r13
0x18002fe1d  mov     [rax], r12w
0x18002fe21  or      edi, 4
0x18002fe24  mov     dword ptr [rsp+120h+var_F0], edi
0x18002fe28  lea     rcx, [rsp+120h+Src]
0x18002fe2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fe32  lea     rax, [rbp+57h+var_60]
0x18002fe36  cmp     qword ptr [rbp+57h+var_50+8], r13
0x18002fe3a  cmova   rax, qword ptr [rbp+57h+var_60]
0x18002fe3f  mov     qword ptr [rbp+57h+var_90], rax
0x18002fe43  mov     rax, qword ptr [rbp+57h+var_50]
0x18002fe47  mov     qword ptr [rbp+57h+var_90+8], rax
0x18002fe4b  movaps  xmm0, [rbp+57h+var_90]
0x18002fe4f  movdqa  [rbp+57h+var_70], xmm0
0x18002fe54  lea     rdx, [rbp+57h+var_70]
0x18002fe58  lea     rcx, [rbp+57h+var_B8]
0x18002fe5c  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18002fe61  or      edi, 8
0x18002fe64  mov     dword ptr [rsp+120h+var_F0], edi
0x18002fe68  mov     qword ptr [rbp+57h+var_C8], r12
0x18002fe6c  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18002fe73  mov     [rbp+57h+var_C0], rax
0x18002fe77  lea     rdx, [rbp+57h+var_C8]; struct std::filesystem::path *
0x18002fe7b  lea     rcx, [rbp+57h+var_B8]; this
0x18002fe7f  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18002fe84  mov     sil, al
0x18002fe87  cmp     dword ptr [rbp+57h+var_C8], r12d
0x18002fe8b  jnz     loc_18003002A
0x18002fe91  lea     rcx, [rbp+57h+var_B8]
0x18002fe95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fe9a  test    sil, sil
0x18002fe9d  jz      loc_18002FFEA
0x18002fea3  movups  xmm0, [rbp+57h+var_60]
0x18002fea7  movups  [rsp+120h+Src], xmm0
0x18002feac  movups  xmm1, [rbp+57h+var_50]
0x18002feb0  movups  [rsp+120h+var_D8], xmm1
0x18002feb5  mov     qword ptr [rbp+57h+var_50], r12
0x18002feb9  mov     qword ptr [rbp+57h+var_50+8], r13
0x18002febd  mov     word ptr [rbp+57h+var_60], r12w
0x18002fec2  lea     rax, [rsp+120h+Src]
0x18002fec7  mov     qword ptr [rbp+57h+var_70], rax
0x18002fecb  lea     rdx, [rsp+120h+Src]
0x18002fed0  movq    rcx, xmm0
0x18002fed5  psrldq  xmm1, 8
0x18002feda  movq    rax, xmm1
0x18002fedf  cmp     rax, r13
0x18002fee2  cmova   rdx, rcx
0x18002fee6  mov     rcx, rdx
0x18002fee9  call    cs:__imp_TdhLoadManifestFromBinary
0x18002feef  mov     r9d, eax; char *
0x18002fef2  test    eax, eax
0x18002fef4  jnz     short loc_18002FF5D
0x18002fef6  lea     ecx, [rax+20h]; Size
0x18002fef9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fefe  mov     rsi, rax
0x18002ff01  mov     qword ptr [rbp+57h+var_70], rax
0x18002ff05  movups  xmm2, [rsp+120h+Src]
0x18002ff0a  movups  [rbp+57h+var_B8], xmm2
0x18002ff0e  movups  xmm1, [rsp+120h+var_D8]
0x18002ff13  movups  [rbp+57h+var_A8], xmm1
0x18002ff17  mov     qword ptr [rsp+120h+var_D8], r12
0x18002ff1c  mov     qword ptr [rbp+57h+var_D8+8], r13
0x18002ff20  mov     word ptr [rsp+120h+Src], r12w
0x18002ff26  movups  xmmword ptr [rax], xmm2
0x18002ff29  movups  xmmword ptr [rax+10h], xmm1
0x18002ff2d  mov     qword ptr [rbp+57h+var_A8], r12
0x18002ff31  mov     qword ptr [rbp+57h+var_A8+8], r13
0x18002ff35  mov     word ptr [rbp+57h+var_B8], r12w
0x18002ff3a  lea     rcx, [rbp+57h+var_B8]
0x18002ff3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ff43  mov     qword ptr [rbp+57h+var_70], rsi
0x18002ff47  or      edi, 10h
0x18002ff4a  mov     dword ptr [rsp+120h+var_F0], edi
0x18002ff4e  lea     rcx, [rsp+120h+Src]
0x18002ff53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ff58  mov     rax, rsi
0x18002ff5b  jmp     short loc_18002FFB6
0x18002ff5d  cmp     r9d, 0B7h
0x18002ff64  jz      short loc_18002FF9B
0x18002ff66  lea     rax, [rsp+120h+Src]
0x18002ff6b  cmp     qword ptr [rbp+57h+var_D8+8], r13
0x18002ff6f  cmova   rax, qword ptr [rsp+120h+Src]
0x18002ff75  mov     rcx, [rbp+5Fh]; this
0x18002ff79  mov     [rsp+120h+var_F8], rax; char *
0x18002ff7e  lea     rax, aTdhloadmanifes; "TdhLoadManifestFromBinary failed for in"...
0x18002ff85  mov     qword ptr [rsp+120h+var_100], rax; unsigned int
0x18002ff8a  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002ff91  mov     edx, 16Eh; void *
0x18002ff96  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002ff9b  mov     qword ptr [rbp+57h+var_70], r12
0x18002ff9f  or      edi, 10h
0x18002ffa2  mov     dword ptr [rsp+120h+var_F0], edi
0x18002ffa6  lea     rcx, [rsp+120h+Src]
0x18002ffab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ffb0  mov     rsi, r12
0x18002ffb3  mov     rax, r12
0x18002ffb6  test    rsi, rsi
0x18002ffb9  jz      short loc_18002FFE0
0x18002ffbb  mov     rdx, [rbx+8]
0x18002ffbf  cmp     rdx, [rbx+10h]
0x18002ffc3  jz      short loc_18002FFD3
0x18002ffc5  mov     qword ptr [rbp+57h+var_70], r12
0x18002ffc9  mov     [rdx], rax
0x18002ffcc  add     qword ptr [rbx+8], 8
0x18002ffd1  jmp     short loc_18002FFE0
0x18002ffd3  lea     r8, [rbp+57h+var_70]
0x18002ffd7  mov     rcx, rbx
0x18002ffda  call    ??$_Emplace_reallocate@V?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@@?$vector@V?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@V?$allocator@V?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Diagnostics::TdhManifest>>::_Emplace_reallocate<std::unique_ptr<Diagnostics::TdhManifest>>(std::unique_ptr<Diagnostics::TdhManifest> * const,std::unique_ptr<Diagnostics::TdhManifest> &&)
0x18002ffdf  nop
0x18002ffe0  lea     rcx, [rbp+57h+var_70]
0x18002ffe4  call    ??1?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@QEAA@XZ; std::unique_ptr<Diagnostics::TdhManifest>::~unique_ptr<Diagnostics::TdhManifest>(void)
0x18002ffe9  nop
0x18002ffea  lea     rcx, [rbp+57h+var_60]
0x18002ffee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fff3  add     r14, 20h ; ' '
0x18002fff7  cmp     r14, r15
0x18002fffa  jnz     loc_18002FDCC
0x180030000  mov     rax, rbx
0x180030003  mov     rcx, [rbp+57h+var_40]
0x180030007  xor     rcx, rsp; StackCookie
0x18003000a  call    __security_check_cookie
0x18003000f  mov     rbx, [rsp+120h+arg_10]
0x180030017  add     rsp, 0F0h
0x18003001e  pop     r15
0x180030020  pop     r14
0x180030022  pop     r13
0x180030024  pop     r12
0x180030026  pop     rdi
0x180030027  pop     rsi
0x180030028  pop     rbp
0x180030029  retn
0x18003002a  lea     r8, [rbp+57h+var_B8]; struct std::error_code *
0x18003002e  lea     rdx, [rbp+57h+var_C8]; char *
0x180030032  lea     rcx, aExists; "exists"
0x180030039  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
