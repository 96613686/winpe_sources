# UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(HSTRING__ * *,uint,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x180039e64`
- end: `0x18003a3ad`
- name: `?RunAnalyzers@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAUHSTRING__@@IPEAU3@110@Z`
- size: `1353`
- prototype: `__int64 __fastcall(HSTRING *, unsigned int, HSTRING, HSTRING, HSTRING, HSTRING *)`
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000c9fc`
- `0x18000d4f8`
- `0x18000d6a0`

## callees

- `0x18000ad5c`
- `0x1800185a8`
- `0x180018d28`
- `0x180018eec`
- `0x180019080`
- `0x1800194b0`
- `0x18001abd4`
- `0x180038ddc`
- `0x180038ebc`
- `0x180038fe8`
- `0x1800393e0`
- `0x180039bd4`
- `0x180039da4`
- `0x180039e64`
- `0x18003a3b4`
- `0x18003c384`
- `0x1800415ac`
- `0x180041624`
- `0x1800416a4`
- `0x180049258`
- `0x180064504`
- `0x18006704c`
- `0x180072f30`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a164`

## string_xrefs

- `0x18003a39f`: `create_directories`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(
        HSTRING *a1,
        unsigned int a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        HSTRING *a6)
{
  __int64 result; // rax
  struct std::error_code *v11; // r8
  bool v12; // r8
  const struct std::filesystem::path *v13; // r9
  bool v14; // bl
  unsigned int i; // ebx
  __int128 v16; // rdi
  char v17; // al
  PCWSTR v18; // rax
  const WCHAR *v19; // rdx
  HSTRING v20; // rax
  const char *v21; // r9
  char v22[8]; // [rsp+20h] [rbp-1E8h] BYREF
  void ***v23; // [rsp+28h] [rbp-1E0h]
  PCWSTR v24[2]; // [rsp+30h] [rbp-1D8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-1C8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-1B8h]
  UINT32 length; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-1A0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp-198h] BYREF
  __int64 v30; // [rsp+78h] [rbp-190h]
  __int128 v31; // [rsp+80h] [rbp-188h] BYREF
  __m128i v32; // [rsp+90h] [rbp-178h]
  HSTRING string; // [rsp+A0h] [rbp-168h] BYREF
  __int128 v34; // [rsp+A8h] [rbp-160h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-150h]
  PCNZWCH sourceString[5]; // [rsp+C8h] [rbp-140h] BYREF
  _BYTE v37[48]; // [rsp+F0h] [rbp-118h] BYREF
  _BYTE v38[16]; // [rsp+120h] [rbp-E8h] BYREF
  _BYTE v39[40]; // [rsp+130h] [rbp-D8h] BYREF
  _BYTE v40[16]; // [rsp+158h] [rbp-B0h] BYREF
  _BYTE v41[24]; // [rsp+168h] [rbp-A0h] BYREF
  char v42; // [rsp+180h] [rbp-88h]
  char v43; // [rsp+188h] [rbp-80h]
  _BYTE v44[40]; // [rsp+190h] [rbp-78h] BYREF
  char v45; // [rsp+1B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  if ( a6 )
  {
    v28 = 0;
    try
    {
      web::json::value::object();
      v45 = 0;
      v34 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v34) = 0;
      if ( a4 )
      {
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(a4, &length);
        v30 = length;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v31, &StringRawBuffer);
        std::wstring::~wstring(&v34);
        v34 = v31;
        si128 = v32;
        v32 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v31) = 0;
        std::wstring::~wstring(&v31);
        *(_QWORD *)v22 = 0;
        v23 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        std::filesystem::create_directories((std::filesystem *)&v34, (const struct std::filesystem::path *)v22, v11);
        if ( *(_DWORD *)v22 )
          std::filesystem::_Throw_fs_error(
            (std::filesystem *)"create_directories",
            v22,
            (const struct std::error_code *)&v34,
            v13);
      }
      else
      {
        v31 = 0;
        v32 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v31, L"updiag", 6);
        unique_temp_directory::unique_temp_directory((struct std::error_code *)v44);
        std::wstring::~wstring(&v31);
        v45 = 1;
        std::wstring::operator=(&v34);
      }
      v43 = 0;
      if ( a3 )
      {
        v14 = a4 != 0;
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(a3, &length);
        v30 = length;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v31, &StringRawBuffer);
        if ( v43 )
        {
          if ( v42 )
            std::vector<std::filesystem::path>::~vector<std::filesystem::path>(v41);
          std::_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>(v40);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(v39);
          std::list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>::~list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>(v38);
          std::wstring::~wstring(v37);
          v43 = 0;
        }
        Diagnostics::NerdHerd::NerdHerd(
          (Diagnostics::NerdHerd *)v37,
          (const struct std::filesystem::path *)&v34,
          (const struct std::filesystem::path *)&v31,
          v14);
        v43 = 1;
        std::wstring::~wstring(&v31);
      }
      else
      {
        Diagnostics::NerdHerd::NerdHerd((Diagnostics::NerdHerd *)v37, (const struct std::filesystem::path *)&v34, v12);
        v43 = 1;
      }
      if ( a1 && a2 )
      {
        for ( i = 0; i < a2; ++i )
        {
          length = 0;
          *(_QWORD *)&v16 = WindowsGetStringRawBuffer(a1[i], &length);
          *((_QWORD *)&v16 + 1) = length;
          *(_QWORD *)v22 = &v28;
          v25[0] = v16;
          v25[1] = length;
          if ( Diagnostics::NerdHerd::findGroup(v25) )
          {
            Diagnostics::NerdHerd::RunAnalyzersByFlags__UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers_::_28_::_lambda_1___(v37);
          }
          else
          {
            v26 = v16;
            Diagnostics::NerdHerd::RunAnalyzer(v37);
            v17 = v30;
            if ( (_BYTE)v30 )
            {
              v18 = StringRawBuffer;
              StringRawBuffer = 0;
              v24[0] = v18;
              v31 = v16;
              UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers_::_28_::_lambda_1_::operator()(v22, &v31, v24);
              v17 = v30;
            }
            if ( v17 )
            {
              if ( StringRawBuffer )
                (*(void (__fastcall **)(PCWSTR, __int64))(*(_QWORD *)StringRawBuffer + 192LL))(StringRawBuffer, 1);
            }
          }
        }
      }
      else
      {
        *(_QWORD *)v22 = &v28;
        Diagnostics::NerdHerd::RunAnalyzersByFlags__UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers_::_30_::_lambda_2___(v37);
      }
      (*(void (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v28 + 80LL))(v28, sourceString);
      string = 0;
      v19 = (const WCHAR *)sourceString;
      if ( sourceString[3] > (PCNZWCH)7 )
        v19 = sourceString[0];
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        &string,
        v19,
        0xFFFFFFFF);
      v20 = string;
      string = 0;
      *a6 = v20;
      std::wstring::~wstring(sourceString);
      if ( v43 )
      {
        if ( v42 )
          std::vector<std::filesystem::path>::~vector<std::filesystem::path>(v41);
        std::_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>(v40);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(v39);
        std::list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>::~list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>(v38);
        std::wstring::~wstring(v37);
      }
      std::wstring::~wstring(&v34);
      if ( v45 )
        unique_temp_directory::~unique_temp_directory((unique_temp_directory *)v44);
      if ( v28 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 192LL))(v28, 1);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x52,
                             (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\DiagDeepDive.cpp",
                             v21);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\DiagDeepDive.cpp",
      (const char *)0x80070057LL,
      *(int *)v22);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180039e64  push    rbx
0x180039e66  push    rsi
0x180039e67  push    rdi
0x180039e68  push    r12
0x180039e6a  push    r13
0x180039e6c  push    r14
0x180039e6e  push    r15
0x180039e70  sub     rsp, 1D0h
0x180039e77  mov     rax, cs:__security_cookie
0x180039e7e  xor     rax, rsp
0x180039e81  mov     [rsp+208h+var_48], rax
0x180039e89  mov     rbx, r9
0x180039e8c  mov     rdi, r8
0x180039e8f  mov     r14d, edx
0x180039e92  mov     r12, rcx
0x180039e95  mov     r15, [rsp+208h+arg_28]
0x180039e9d  xor     r13d, r13d
0x180039ea0  test    r15, r15
0x180039ea3  jnz     short loc_180039ECC
0x180039ea5  mov     rcx, [rsp+208h]; this
0x180039ead  mov     ebx, 80070057h
0x180039eb2  mov     r9d, ebx; char *
0x180039eb5  lea     r8, aCW1SSrcCalliop_2; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180039ebc  lea     edx, [r15+0Ah]; void *
0x180039ec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ec5  mov     eax, ebx
0x180039ec7  jmp     loc_18003A36F
0x180039ecc  mov     [rsp+208h+var_1A0], r13
0x180039ed1  mov     dl, 1
0x180039ed3  lea     rcx, [rsp+208h+var_1A0]
0x180039ed8  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180039edd  nop
0x180039ede  mov     [rsp+208h+var_50], r13b
0x180039ee6  xorps   xmm0, xmm0
0x180039ee9  movups  [rsp+208h+var_160], xmm0
0x180039ef1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180039ef9  movdqu  [rsp+208h+var_150], xmm1
0x180039f02  mov     word ptr [rsp+208h+var_160], r13w
0x180039f0b  test    rbx, rbx
0x180039f0e  jz      loc_180039FCB
0x180039f14  mov     [rsp+208h+length], r13d
0x180039f19  lea     rdx, [rsp+208h+length]; length
0x180039f1e  mov     rcx, rbx; string
0x180039f21  call    cs:__imp_WindowsGetStringRawBuffer
0x180039f27  mov     [rsp+208h+var_198], rax
0x180039f2c  mov     eax, [rsp+208h+length]
0x180039f30  mov     [rsp+208h+var_190], rax
0x180039f35  lea     rdx, [rsp+208h+var_198]
0x180039f3a  lea     rcx, [rsp+208h+var_188]
0x180039f42  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180039f47  lea     rcx, [rsp+208h+var_160]
0x180039f4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039f54  movups  xmm0, [rsp+208h+var_188]
0x180039f5c  movups  [rsp+208h+var_160], xmm0
0x180039f64  movups  xmm1, [rsp+208h+var_178]
0x180039f6c  movups  [rsp+208h+var_150], xmm1
0x180039f74  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180039f7c  movdqu  [rsp+208h+var_178], xmm0
0x180039f85  mov     word ptr [rsp+208h+var_188], r13w
0x180039f8e  lea     rcx, [rsp+208h+var_188]
0x180039f96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039f9b  mov     qword ptr [rsp+208h+var_1E8], r13
0x180039fa0  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180039fa7  mov     [rsp+208h+var_1E0], rax
0x180039fac  lea     rdx, [rsp+208h+var_1E8]; struct std::filesystem::path *
0x180039fb1  lea     rcx, [rsp+208h+var_160]; this
0x180039fb9  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x180039fbe  cmp     dword ptr [rsp+208h+var_1E8], r13d
0x180039fc3  jnz     loc_18003A392
0x180039fc9  jmp     short loc_18003A03A
0x180039fcb  movups  [rsp+208h+var_188], xmm0
0x180039fd3  xorps   xmm1, xmm1
0x180039fd6  movdqu  [rsp+208h+var_178], xmm1
0x180039fdf  mov     r8d, 6
0x180039fe5  lea     rdx, aUpdiag; "updiag"
0x180039fec  lea     rcx, [rsp+208h+var_188]
0x180039ff4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180039ff9  nop
0x180039ffa  lea     rdx, [rsp+208h+var_188]
0x18003a002  lea     rcx, [rsp+208h+var_78]; struct std::error_code *
0x18003a00a  call    ??0unique_temp_directory@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; unique_temp_directory::unique_temp_directory(std::wstring const &)
0x18003a00f  nop
0x18003a010  lea     rcx, [rsp+208h+var_188]
0x18003a018  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a01d  mov     [rsp+208h+var_50], 1
0x18003a025  lea     rdx, [rsp+208h+var_78]
0x18003a02d  lea     rcx, [rsp+208h+var_160]; void *
0x18003a035  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003a03a  mov     [rsp+208h+var_80], r13b
0x18003a042  test    rdi, rdi
0x18003a045  jz      loc_18003A119
0x18003a04b  test    rbx, rbx
0x18003a04e  setnz   bl
0x18003a051  mov     [rsp+208h+length], r13d
0x18003a056  lea     rdx, [rsp+208h+length]; length
0x18003a05b  mov     rcx, rdi; string
0x18003a05e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a064  mov     [rsp+208h+var_198], rax
0x18003a069  mov     eax, [rsp+208h+length]
0x18003a06d  mov     [rsp+208h+var_190], rax
0x18003a072  lea     rdx, [rsp+208h+var_198]
0x18003a077  lea     rcx, [rsp+208h+var_188]
0x18003a07f  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003a084  nop
0x18003a085  cmp     [rsp+208h+var_80], r13b
0x18003a08d  jz      short loc_18003A0E2
0x18003a08f  cmp     [rsp+208h+var_88], r13b
0x18003a097  jz      short loc_18003A0A6
0x18003a099  lea     rcx, [rsp+208h+var_A0]
0x18003a0a1  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x18003a0a6  lea     rcx, [rsp+208h+var_B0]
0x18003a0ae  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$optional@Vpath@filesystem@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$optional@Vpath@filesystem@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>(void)
0x18003a0b3  lea     rcx, [rsp+208h+var_D8]
0x18003a0bb  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@USpanStartData@EtwFileProcessor@Diagnostics@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(void)
0x18003a0c0  lea     rcx, [rsp+208h+var_E8]
0x18003a0c8  call    ??1?$list@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@VISourceHandler@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@VISourceHandler@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>::~list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>(void)
0x18003a0cd  lea     rcx, [rsp+208h+var_118]
0x18003a0d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a0da  mov     [rsp+208h+var_80], r13b
0x18003a0e2  mov     r9b, bl; bool
0x18003a0e5  lea     r8, [rsp+208h+var_188]; struct std::filesystem::path *
0x18003a0ed  lea     rdx, [rsp+208h+var_160]; struct std::filesystem::path *
0x18003a0f5  lea     rcx, [rsp+208h+var_118]; this
0x18003a0fd  call    ??0NerdHerd@Diagnostics@@QEAA@AEBVpath@filesystem@std@@0_N@Z; Diagnostics::NerdHerd::NerdHerd(std::filesystem::path const &,std::filesystem::path const &,bool)
0x18003a102  mov     [rsp+208h+var_80], 1
0x18003a10a  lea     rcx, [rsp+208h+var_188]
0x18003a112  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a117  jmp     short loc_18003A136
0x18003a119  lea     rdx, [rsp+208h+var_160]; struct std::filesystem::path *
0x18003a121  lea     rcx, [rsp+208h+var_118]; this
0x18003a129  call    ??0NerdHerd@Diagnostics@@QEAA@AEBVpath@filesystem@std@@_N@Z; Diagnostics::NerdHerd::NerdHerd(std::filesystem::path const &,bool)
0x18003a12e  mov     [rsp+208h+var_80], 1
0x18003a136  test    r12, r12
0x18003a139  jz      loc_18003A23C
0x18003a13f  test    r14d, r14d
0x18003a142  jz      loc_18003A23C
0x18003a148  mov     ebx, r13d
0x18003a14b  cmp     ebx, r14d
0x18003a14e  jnb     loc_18003A25F
0x18003a154  mov     [rsp+208h+length], r13d
0x18003a159  mov     ecx, ebx
0x18003a15b  lea     rdx, [rsp+208h+length]; length
0x18003a160  mov     rcx, [r12+rcx*8]; string
0x18003a164  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a16a  mov     rdi, rax
0x18003a16d  mov     esi, [rsp+208h+length]
0x18003a171  lea     rax, [rsp+208h+var_1A0]
0x18003a176  mov     qword ptr [rsp+208h+var_1E8], rax
0x18003a17b  mov     [rsp+208h+var_1C8], rdi
0x18003a180  mov     [rsp+208h+var_1C0], rsi
0x18003a185  lea     rcx, [rsp+208h+var_1C8]
0x18003a18a  call    ?findGroup@NerdHerd@Diagnostics@@CAPEBUAnalyzerGroup@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Diagnostics::NerdHerd::findGroup(std::wstring_view)
0x18003a18f  lea     rcx, [rsp+208h+var_118]; void *
0x18003a197  test    rax, rax
0x18003a19a  jz      short loc_18003A1B2
0x18003a19c  lea     r9, [rsp+208h+var_1E8]
0x18003a1a1  mov     r8, [rax]
0x18003a1a4  mov     rdx, [rax+18h]
0x18003a1a8  call    Diagnostics__NerdHerd__RunAnalyzersByFlags__UpdateDiagnosticsInternal__DiagDeepDive__RunAnalyzers____28____lambda_1___
0x18003a1ad  jmp     loc_18003A235
0x18003a1b2  mov     [rsp+208h+var_1B8], rdi
0x18003a1b7  mov     [rsp+208h+var_1B0], rsi
0x18003a1bc  xor     r9d, r9d
0x18003a1bf  lea     r8, [rsp+208h+var_1B8]
0x18003a1c4  lea     rdx, [rsp+208h+var_198]
0x18003a1c9  call    ?RunAnalyzer@NerdHerd@Diagnostics@@QEAA?AV?$optional@Vvalue@json@web@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@4@PEB_W@Z; Diagnostics::NerdHerd::RunAnalyzer(std::wstring_view,wchar_t const *)
0x18003a1ce  nop
0x18003a1cf  mov     rax, [rsp+208h+var_190]
0x18003a1d4  test    al, al
0x18003a1d6  jz      short loc_18003A213
0x18003a1d8  mov     rax, [rsp+208h+var_198]
0x18003a1dd  mov     [rsp+208h+var_198], r13
0x18003a1e2  mov     [rsp+208h+var_1D8], rax
0x18003a1e7  mov     qword ptr [rsp+208h+var_188], rdi
0x18003a1ef  mov     qword ptr [rsp+208h+var_188+8], rsi
0x18003a1f7  lea     r8, [rsp+208h+var_1D8]
0x18003a1fc  lea     rdx, [rsp+208h+var_188]
0x18003a204  lea     rcx, [rsp+208h+var_1E8]
0x18003a209  call    _UpdateDiagnosticsInternal__DiagDeepDive__RunAnalyzers____28____lambda_1___operator__
0x18003a20e  mov     rax, [rsp+208h+var_190]
0x18003a213  test    al, al
0x18003a215  jz      short loc_18003A235
0x18003a217  mov     rcx, [rsp+208h+var_198]
0x18003a21c  test    rcx, rcx
0x18003a21f  jz      short loc_18003A235
0x18003a221  mov     rax, [rcx]
0x18003a224  mov     edx, 1
0x18003a229  mov     rax, [rax+0C0h]
0x18003a230  call    _guard_dispatch_icall
0x18003a235  inc     ebx
0x18003a237  jmp     loc_18003A14B
0x18003a23c  lea     rax, [rsp+208h+var_1A0]
0x18003a241  mov     qword ptr [rsp+208h+var_1E8], rax
0x18003a246  lea     r9, [rsp+208h+var_1E8]
0x18003a24b  mov     r8, cs:off_1800AFB50; "Default"
0x18003a252  lea     rcx, [rsp+208h+var_118]; void *
0x18003a25a  call    Diagnostics__NerdHerd__RunAnalyzersByFlags__UpdateDiagnosticsInternal__DiagDeepDive__RunAnalyzers____30____lambda_2___
0x18003a25f  mov     rcx, [rsp+208h+var_1A0]
0x18003a264  mov     rax, [rcx]
0x18003a267  lea     rdx, [rsp+208h+sourceString]
0x18003a26f  mov     rax, [rax+50h]
0x18003a273  call    _guard_dispatch_icall
0x18003a278  nop
0x18003a279  mov     [rsp+208h+string], r13
0x18003a281  lea     rdx, [rsp+208h+sourceString]
0x18003a289  cmp     [rsp+208h+var_128], 7
0x18003a292  cmova   rdx, [rsp+208h+sourceString]; sourceString
0x18003a29b  or      r8, 0FFFFFFFFFFFFFFFFh; length
0x18003a29f  lea     rcx, [rsp+208h+string]; string
0x18003a2a7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18003a2ac  mov     rax, [rsp+208h+string]
0x18003a2b4  mov     [rsp+208h+string], r13
0x18003a2bc  mov     [r15], rax
0x18003a2bf  lea     rcx, [rsp+208h+sourceString]
0x18003a2c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a2cc  nop
0x18003a2cd  cmp     [rsp+208h+var_80], r13b
0x18003a2d5  jz      short loc_18003A323
0x18003a2d7  cmp     [rsp+208h+var_88], r13b
0x18003a2df  jz      short loc_18003A2EE
0x18003a2e1  lea     rcx, [rsp+208h+var_A0]
0x18003a2e9  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x18003a2ee  lea     rcx, [rsp+208h+var_B0]
0x18003a2f6  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$optional@Vpath@filesystem@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$optional@Vpath@filesystem@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,std::optional<std::filesystem::path>,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,std::optional<std::filesystem::path>>>,0>>(void)
0x18003a2fb  lea     rcx, [rsp+208h+var_D8]
0x18003a303  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@USpanStartData@EtwFileProcessor@Diagnostics@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(void)
0x18003a308  lea     rcx, [rsp+208h+var_E8]
0x18003a310  call    ??1?$list@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@VISourceHandler@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@VISourceHandler@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>::~list<std::pair<std::wstring_view const,std::shared_ptr<ISourceHandler>>>(void)
0x18003a315  lea     rcx, [rsp+208h+var_118]
0x18003a31d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a322  nop
0x18003a323  lea     rcx, [rsp+208h+var_160]
0x18003a32b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a330  nop
0x18003a331  cmp     [rsp+208h+var_50], r13b
0x18003a339  jz      short loc_18003A349
0x18003a33b  lea     rcx, [rsp+208h+var_78]; this
0x18003a343  call    ??1unique_temp_directory@@QEAA@XZ; unique_temp_directory::~unique_temp_directory(void)
0x18003a348  nop
0x18003a349  mov     rcx, [rsp+208h+var_1A0]
0x18003a34e  test    rcx, rcx
0x18003a351  jz      short loc_18003A367
0x18003a353  mov     rax, [rcx]
0x18003a356  mov     edx, 1
0x18003a35b  mov     rax, [rax+0C0h]
0x18003a362  call    _guard_dispatch_icall
0x18003a367  xor     eax, eax
0x18003a369  jmp     short loc_18003A36F
0x18003a36b  mov     eax, [rsp+208h+length]
0x18003a36f  mov     rcx, [rsp+208h+var_48]
0x18003a377  xor     rcx, rsp; StackCookie
0x18003a37a  call    __security_check_cookie
0x18003a37f  add     rsp, 1D0h
0x18003a386  pop     r15
0x18003a388  pop     r14
0x18003a38a  pop     r13
0x18003a38c  pop     r12
0x18003a38e  pop     rdi
0x18003a38f  pop     rsi
0x18003a390  pop     rbx
0x18003a391  retn
0x18003a392  lea     r8, [rsp+208h+var_160]; struct std::error_code *
0x18003a39a  lea     rdx, [rsp+208h+var_1E8]; char *
0x18003a39f  lea     rcx, aCreateDirector; "create_directories"
0x18003a3a6  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
