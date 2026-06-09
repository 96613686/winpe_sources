# TestHookPolicyReader::ValidateAUTestCab(void)

- ea: `0x180018bc4`
- end: `0x180018ee3`
- name: `?ValidateAUTestCab@TestHookPolicyReader@@CA_NXZ`
- size: `799`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ac8`

## callees

- `0x18000fcc4`
- `0x180010260`
- `0x1800163c8`
- `0x180018bc4`
- `0x180018eec`
- `0x18001901c`
- `0x1800191d4`
- `0x1800192a4`
- `0x180019320`
- `0x18001a1b0`
- `0x18001a24c`
- `0x180027670`
- `0x180027bc8`
- `0x180027e14`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ea3`

## string_xrefs

- `0x180018c41`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x180018cd8`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x180018d4b`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`

## pseudocode

```c
char TestHookPolicyReader::ValidateAUTestCab(void)
{
  int v0; // eax
  _WORD *v1; // rbx
  char IsValidAUTestCabContent; // di
  __int64 v3; // rsi
  __int64 v4; // r8
  int v5; // eax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  int v10; // r14d
  __int128 *v11; // rdx
  int v12; // eax
  int v13; // esi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR WideCharStr[8]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h]
  _OWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v20[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[8]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v22[14]; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v23; // [rsp+100h] [rbp+0h] BYREF
  __int128 v24; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  __int128 v26; // [rsp+128h] [rbp+28h] BYREF
  __int64 v27; // [rsp+138h] [rbp+38h]
  WCHAR FileName[16]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  lpMem = 0;
  v23 = L"%WINDIR%\\SoftwareDistribution\\";
  v22[0] = &wistd::__function::__func<_lambda_d3dbae93822b452d3b55eca72542e259_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v22[1] = &v23;
  v22[13] = v22;
  v0 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
         &lpMem,
         v21);
  v1 = lpMem;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
      (const char *)(unsigned int)v0,
      (int)lpMem);
    IsValidAUTestCabContent = 0;
    goto LABEL_28;
  }
  v24 = 0;
  si128 = 0;
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)lpMem + v4) );
  std::wstring::_Construct<1,wchar_t const *>(&v24);
  std::operator+<wchar_t>(FileName, &v24, L"autest.cab");
  std::wstring::~wstring(&v24);
  v5 = TestHookPolicyReader::VerifyAUTestCabExists(FileName);
  v6 = retaddr;
  if ( v5 >= 0 )
  {
    v5 = PolicyUtils::Trust::VerifyFileSignature(FileName);
    v6 = retaddr;
    if ( v5 >= 0 )
    {
      v24 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v24) = 0;
      *(_OWORD *)WideCharStr = 0;
      v18 = 0;
      v8 = -1;
      do
        ++v8;
      while ( v1[v8] );
      std::wstring::_Construct<1,wchar_t const *>(WideCharStr);
      v9 = PolicyUtils::Strings::ConvertToMultiByte(WideCharStr, &v24);
      v10 = v9;
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
          (const char *)(unsigned int)v9,
          (int)lpMem);
      std::wstring::~wstring(WideCharStr);
      if ( v10 >= 0 )
      {
        v26 = 0;
        v27 = 0;
        memset(v20, 0, sizeof(v20));
        std::string::_Construct<1,char const *>(v20, "autest.txt", 10);
        memset(v19, 0, sizeof(v19));
        std::string::_Construct<1,char const *>(v19, "autest.cab", 10);
        v11 = &v24;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v11 = (__int128 *)v24;
        *(_OWORD *)WideCharStr = 0;
        v18 = 0;
        do
          ++v3;
        while ( *((_BYTE *)v11 + v3) );
        std::string::_Construct<1,char const *>(WideCharStr, v11, v3);
        v12 = PolicyUtils::Cabinet::Decompress(WideCharStr, v19, v20, &v26);
        v13 = v12;
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x94,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
            (const char *)(unsigned int)v12,
            (int)lpMem);
        std::string::~string(WideCharStr);
        std::string::~string(v19);
        std::string::~string(v20);
        if ( v13 >= 0 )
          IsValidAUTestCabContent = TestHookPolicyReader::IsValidAUTestCabContent(&v26);
        else
          IsValidAUTestCabContent = 0;
        std::vector<char>::~vector<char>(&v26);
      }
      else
      {
        IsValidAUTestCabContent = 0;
      }
      std::string::~string(&v24);
      goto LABEL_27;
    }
    v7 = 132;
  }
  else
  {
    v7 = 125;
  }
  wil::details::in1diag3::_Log_Hr(
    v6,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
    (const char *)(unsigned int)v5,
    (int)lpMem);
  IsValidAUTestCabContent = 0;
LABEL_27:
  std::wstring::~wstring(FileName);
LABEL_28:
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  return IsValidAUTestCabContent;
}

```

## disassembly

```asm
0x180018bc4  mov     [rsp-8+arg_0], rbx
0x180018bc9  mov     [rsp-8+arg_8], rsi
0x180018bce  mov     [rsp-8+arg_10], rdi
0x180018bd3  push    rbp
0x180018bd4  push    r14
0x180018bd6  push    r15
0x180018bd8  lea     rbp, [rsp-70h]
0x180018bdd  sub     rsp, 170h
0x180018be4  mov     rax, cs:__security_cookie
0x180018beb  xor     rax, rsp
0x180018bee  mov     [rbp+80h+var_20], rax
0x180018bf2  xor     r15d, r15d
0x180018bf5  mov     [rsp+180h+lpMem], r15; int
0x180018bfa  lea     rax, aWindirSoftware; "%WINDIR%\\SoftwareDistribution\\"
0x180018c01  mov     [rbp+80h+var_80], rax
0x180018c05  lea     rax, ??_7?$__func@V_lambda_d3dbae93822b452d3b55eca72542e259_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_d3dbae93822b452d3b55eca72542e259_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180018c0c  mov     [rbp+80h+var_F0], rax
0x180018c10  lea     rax, [rbp+80h+var_80]
0x180018c14  mov     [rbp+80h+var_E8], rax
0x180018c18  lea     rax, [rbp+80h+var_F0]
0x180018c1c  mov     [rbp+80h+var_88], rax
0x180018c20  lea     rdx, [rbp+80h+var_F8]
0x180018c24  lea     rcx, [rsp+180h+lpMem]
0x180018c29  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x180018c2e  mov     rcx, [rbp+88h]; this
0x180018c35  mov     rbx, [rsp+180h+lpMem]
0x180018c3a  test    eax, eax
0x180018c3c  jns     short loc_180018C59
0x180018c3e  mov     r9d, eax; char *
0x180018c41  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018c48  lea     edx, [r15+77h]; void *
0x180018c4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018c51  mov     dil, r15b
0x180018c54  jmp     loc_180018E9E
0x180018c59  xorps   xmm0, xmm0
0x180018c5c  movups  [rbp+80h+var_78], xmm0
0x180018c60  xorps   xmm1, xmm1
0x180018c63  movdqu  [rbp+80h+var_68], xmm1
0x180018c68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018c6c  mov     r8, rsi
0x180018c6f  inc     r8
0x180018c72  cmp     [rbx+r8*2], r15w
0x180018c77  jnz     short loc_180018C6F
0x180018c79  mov     rdx, rbx
0x180018c7c  lea     rcx, [rbp+80h+var_78]
0x180018c80  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180018c85  nop
0x180018c86  lea     r8, aAutestCab; "autest.cab"
0x180018c8d  lea     rdx, [rbp+80h+var_78]
0x180018c91  lea     rcx, [rbp+80h+FileName]
0x180018c95  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180018c9a  nop
0x180018c9b  lea     rcx, [rbp+80h+var_78]; void *
0x180018c9f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018ca4  lea     rcx, [rbp+80h+FileName]; lpFileName
0x180018ca8  call    ?VerifyAUTestCabExists@TestHookPolicyReader@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; TestHookPolicyReader::VerifyAUTestCabExists(std::wstring const &)
0x180018cad  mov     rcx, [rbp+88h]
0x180018cb4  test    eax, eax
0x180018cb6  jns     short loc_180018CBF
0x180018cb8  mov     edx, 7Dh ; '}'
0x180018cbd  jmp     short loc_180018CD8
0x180018cbf  lea     rcx, [rbp+80h+FileName]
0x180018cc3  call    ?VerifyFileSignature@Trust@PolicyUtils@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; PolicyUtils::Trust::VerifyFileSignature(std::wstring const &,ulong)
0x180018cc8  mov     rcx, [rbp+88h]; this
0x180018ccf  test    eax, eax
0x180018cd1  jns     short loc_180018CF2
0x180018cd3  mov     edx, 84h; void *
0x180018cd8  lea     rdi, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018cdf  mov     r9d, eax; char *
0x180018ce2  mov     r8, rdi; unsigned int
0x180018ce5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018cea  mov     dil, r15b
0x180018ced  jmp     loc_180018E94
0x180018cf2  xorps   xmm0, xmm0
0x180018cf5  movups  [rbp+80h+var_78], xmm0
0x180018cf9  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180018d01  movdqu  [rbp+80h+var_68], xmm1
0x180018d06  mov     byte ptr [rbp+80h+var_78], r15b
0x180018d0a  movups  xmmword ptr [rsp+180h+WideCharStr], xmm0
0x180018d0f  xorps   xmm1, xmm1
0x180018d12  movdqu  [rsp+180h+var_148], xmm1
0x180018d18  mov     r8, rsi
0x180018d1b  inc     r8
0x180018d1e  cmp     [rbx+r8*2], r15w
0x180018d23  jnz     short loc_180018D1B
0x180018d25  mov     rdx, rbx
0x180018d28  lea     rcx, [rsp+180h+WideCharStr]
0x180018d2d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180018d32  nop
0x180018d33  lea     rdx, [rbp+80h+var_78]; void *
0x180018d37  lea     rcx, [rsp+180h+WideCharStr]; lpWideCharStr
0x180018d3c  call    ?ConvertToMultiByte@Strings@PolicyUtils@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PolicyUtils::Strings::ConvertToMultiByte(std::wstring const &,std::string &)
0x180018d41  mov     r14d, eax
0x180018d44  mov     rcx, [rbp+88h]; this
0x180018d4b  lea     rdi, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018d52  test    eax, eax
0x180018d54  jns     short loc_180018D66
0x180018d56  mov     r9d, eax; char *
0x180018d59  mov     r8, rdi; unsigned int
0x180018d5c  mov     edx, 8Bh; void *
0x180018d61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018d66  shr     r14d, 1Fh
0x180018d6a  lea     rcx, [rsp+180h+WideCharStr]; void *
0x180018d6f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d74  test    r14b, r14b
0x180018d77  jz      short loc_180018D81
0x180018d79  mov     dil, r15b
0x180018d7c  jmp     loc_180018E8A
0x180018d81  xorps   xmm0, xmm0
0x180018d84  xorps   xmm1, xmm1
0x180018d87  movdqu  [rbp+80h+var_58], xmm1
0x180018d8c  mov     [rbp+80h+var_48], r15
0x180018d90  movups  [rsp+180h+var_118], xmm0
0x180018d95  movdqu  [rsp+180h+var_108], xmm1
0x180018d9b  mov     r14d, 0Ah
0x180018da1  mov     r8d, r14d
0x180018da4  lea     rdx, aAutestTxt; "autest.txt"
0x180018dab  lea     rcx, [rsp+180h+var_118]
0x180018db0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180018db5  nop
0x180018db6  xorps   xmm0, xmm0
0x180018db9  movups  [rsp+180h+var_138], xmm0
0x180018dbe  xorps   xmm1, xmm1
0x180018dc1  movdqu  [rsp+180h+var_128], xmm1
0x180018dc7  mov     r8d, r14d
0x180018dca  lea     rdx, aAutestCab_0; "autest.cab"
0x180018dd1  lea     rcx, [rsp+180h+var_138]
0x180018dd6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180018ddb  nop
0x180018ddc  lea     rdx, [rbp+80h+var_78]
0x180018de0  cmp     qword ptr [rbp+80h+var_68+8], 0Fh
0x180018de5  cmova   rdx, qword ptr [rbp+80h+var_78]
0x180018dea  xorps   xmm0, xmm0
0x180018ded  movups  xmmword ptr [rsp+180h+WideCharStr], xmm0
0x180018df2  xorps   xmm1, xmm1
0x180018df5  movdqu  [rsp+180h+var_148], xmm1
0x180018dfb  inc     rsi
0x180018dfe  cmp     [rdx+rsi], r15b
0x180018e02  jnz     short loc_180018DFB
0x180018e04  mov     r8, rsi
0x180018e07  lea     rcx, [rsp+180h+WideCharStr]
0x180018e0c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180018e11  nop
0x180018e12  lea     r9, [rbp+80h+var_58]
0x180018e16  lea     r8, [rsp+180h+var_118]
0x180018e1b  lea     rdx, [rsp+180h+var_138]
0x180018e20  lea     rcx, [rsp+180h+WideCharStr]
0x180018e25  call    ?Decompress@Cabinet@PolicyUtils@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00AEAV?$vector@EV?$allocator@E@std@@@4@@Z; PolicyUtils::Cabinet::Decompress(std::string const &,std::string const &,std::string const &,std::vector<uchar> &)
0x180018e2a  mov     esi, eax
0x180018e2c  mov     rcx, [rbp+88h]; this
0x180018e33  test    eax, eax
0x180018e35  jns     short loc_180018E47
0x180018e37  mov     r9d, eax; char *
0x180018e3a  mov     r8, rdi; unsigned int
0x180018e3d  mov     edx, 94h; void *
0x180018e42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018e47  shr     esi, 1Fh
0x180018e4a  lea     rcx, [rsp+180h+WideCharStr]
0x180018e4f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018e54  nop
0x180018e55  lea     rcx, [rsp+180h+var_138]
0x180018e5a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018e5f  nop
0x180018e60  lea     rcx, [rsp+180h+var_118]
0x180018e65  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018e6a  test    sil, sil
0x180018e6d  jz      short loc_180018E74
0x180018e6f  mov     dil, r15b
0x180018e72  jmp     short loc_180018E80
0x180018e74  lea     rcx, [rbp+80h+var_58]
0x180018e78  call    ?IsValidAUTestCabContent@TestHookPolicyReader@@CA_NAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; TestHookPolicyReader::IsValidAUTestCabContent(std::vector<uchar> const &)
0x180018e7d  mov     dil, al
0x180018e80  lea     rcx, [rbp+80h+var_58]
0x180018e84  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180018e89  nop
0x180018e8a  lea     rcx, [rbp+80h+var_78]
0x180018e8e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018e93  nop
0x180018e94  lea     rcx, [rbp+80h+FileName]; void *
0x180018e98  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018e9d  nop
0x180018e9e  test    rbx, rbx
0x180018ea1  jz      short loc_180018EB7
0x180018ea3  call    cs:__imp_GetProcessHeap
0x180018ea9  mov     rcx, rax; hHeap
0x180018eac  mov     r8, rbx; lpMem
0x180018eaf  xor     edx, edx; dwFlags
0x180018eb1  call    cs:__imp_HeapFree
0x180018eb7  mov     al, dil
0x180018eba  mov     rcx, [rbp+80h+var_20]
0x180018ebe  xor     rcx, rsp; StackCookie
0x180018ec1  call    __security_check_cookie
0x180018ec6  lea     r11, [rsp+180h+var_10]
0x180018ece  mov     rbx, [r11+20h]
0x180018ed2  mov     rsi, [r11+28h]
0x180018ed6  mov     rdi, [r11+30h]
0x180018eda  mov     rsp, r11
0x180018edd  pop     r15
0x180018edf  pop     r14
0x180018ee1  pop     rbp
0x180018ee2  retn
```
