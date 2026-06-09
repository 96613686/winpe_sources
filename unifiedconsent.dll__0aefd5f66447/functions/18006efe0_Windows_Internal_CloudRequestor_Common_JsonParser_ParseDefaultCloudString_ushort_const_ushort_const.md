# Windows::Internal::CloudRequestor::Common::JsonParser::ParseDefaultCloudString(ushort const *,ushort const *)

- ea: `0x18006efe0`
- end: `0x18006f339`
- name: `?ParseDefaultCloudString@JsonParser@Common@CloudRequestor@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800630b0`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x180005004`
- `0x18000ed24`
- `0x1800130a4`
- `0x180013efc`
- `0x1800163d0`
- `0x1800165b4`
- `0x180018198`
- `0x180023870`
- `0x180066c60`
- `0x18006cd78`
- `0x18006e64c`
- `0x18006ee90`
- `0x18006efe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f02f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f0b6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f0fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f194`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f1dc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f2c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f2d4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f02f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f0b6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f0fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f194`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f1dc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f2c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f2d4`

## string_xrefs

- `0x18006f14b`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`
- `0x18006f2f8`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`
- `0x18006f327`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CloudRequestor::Common::JsonParser::ParseDefaultCloudString(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  char v7; // al
  volatile signed __int32 *v8; // rbx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 v11; // rax
  void *v12; // rbx
  int v13; // eax
  HANDLE v14; // rax
  void *v15; // rbx
  int v16; // edi
  HANDLE v17; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char *v21; // [rsp+28h] [rbp-48h]
  LPVOID v22[2]; // [rsp+38h] [rbp-38h] BYREF
  int *v23; // [rsp+48h] [rbp-28h] BYREF
  int v24; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+54h] [rbp-1Ch]
  const wchar_t *v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v28; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+B8h] [rbp+48h] BYREF

  v28 = a3;
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v28);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( (_DWORD)v6 )
  {
    if ( a2[(unsigned int)v6] )
      abort();
    v24 = 1;
    v25 = v6;
    v26 = a2;
    v23 = &v24;
  }
  else
  {
    v23 = 0;
  }
  v22[0] = &v23;
  v22[1] = &v28;
  lpMem = &qword_18009CF78;
  _InterlockedIncrement64(&qword_18009CF78);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    v7 = _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(
           v22,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedAdd64(&qword_18009CF78, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009CF78, 0xFFFFFFFFFFFFFFFFuLL);
    v7 = winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_216e461b0f2bafa6414b8faed9d5cbb6_ &>(
           v5,
           v22);
  }
  if ( !v7 )
  {
    v19 = wil::verify_hresult<long>(2205483015LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
      (const char *)v19,
      (int)"DefaultCloud Parse Error",
      v21);
  }
  if ( aError[5] )
    abort();
  v24 = 1;
  v25 = 5;
  v26 = L"error";
  v23 = &v24;
  if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                          &v28,
                          &v23) )
  {
    if ( aError[5] )
      abort();
    v24 = 1;
    v25 = 5;
    v26 = L"error";
    v23 = &v24;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
      &v28,
      &lpMem,
      &v23);
    v8 = (volatile signed __int32 *)lpMem;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
      (const char *)0x80070057LL,
      (int)"Error to get default cloud: %ls",
      (const char *)lpMem);
    if ( v8 )
    {
      v9 = _InterlockedDecrement(v8 + 6);
      if ( v9 )
      {
        if ( v9 < 0 )
          goto LABEL_40;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
      }
    }
  }
  if ( aDefaultcloud[12] )
    abort();
  v24 = 1;
  v25 = 12;
  v26 = L"DefaultCloud";
  v23 = &v24;
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v28,
                           &v23) )
  {
    v20 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
      (const char *)v20,
      (int)"No defaultCloud found for given tenant",
      v21);
  }
  if ( aDefaultcloud[12] )
    abort();
  v24 = 1;
  v25 = 12;
  v26 = L"DefaultCloud";
  v23 = &v24;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
    &v28,
    &lpMem,
    &v23);
  if ( lpMem )
  {
    if ( *(_WORD *)(*((_QWORD *)lpMem + 2) + 2LL * *((unsigned int *)lpMem + 1) - 2) != 47 )
    {
      v11 = winrt::operator+(v22, &lpMem, L"/");
      winrt::hstring::operator=(&lpMem, v11);
      v12 = v22[0];
      if ( v22[0] )
      {
        v13 = _InterlockedDecrement((volatile signed __int32 *)v22[0] + 6);
        if ( v13 )
        {
          if ( v13 < 0 )
            abort();
        }
        else
        {
          v14 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v14, 0, v12);
        }
      }
    }
  }
  StringToLower(a1, &lpMem);
  v15 = lpMem;
  if ( lpMem )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( !v16 )
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, v15);
      goto LABEL_34;
    }
    if ( v16 < 0 )
LABEL_40:
      abort();
  }
LABEL_34:
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
  return a1;
}

```

## disassembly

```asm
0x18006efe0  mov     [rsp-28h+arg_0], rbx
0x18006efe5  mov     [rsp-28h+arg_10], r8
0x18006efea  push    rbp
0x18006efeb  push    rsi
0x18006efec  push    rdi
0x18006efed  push    r12
0x18006efef  push    r14
0x18006eff1  mov     rbp, rsp
0x18006eff4  sub     rsp, 70h
0x18006eff8  mov     rbx, rdx
0x18006effb  mov     rsi, rcx
0x18006effe  xor     r14d, r14d
0x18006f001  lea     rcx, [rbp+arg_10]; this
0x18006f005  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18006f00a  nop
0x18006f00b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006f00f  mov     rdx, rdi
0x18006f012  inc     rdx
0x18006f015  cmp     [rbx+rdx*2], r14w
0x18006f01a  jnz     short loc_18006F012
0x18006f01c  test    edx, edx
0x18006f01e  jnz     short loc_18006F026
0x18006f020  mov     [rbp+var_28], r14
0x18006f024  jmp     short loc_18006F04C
0x18006f026  mov     eax, edx
0x18006f028  cmp     [rbx+rax*2], r14w
0x18006f02d  jz      short loc_18006F036
0x18006f02f  call    cs:__imp_abort
0x18006f036  mov     [rbp+var_20], 1
0x18006f03d  mov     [rbp+var_1C], edx
0x18006f040  mov     [rbp+var_10], rbx
0x18006f044  lea     rax, [rbp+var_20]
0x18006f048  mov     [rbp+var_28], rax
0x18006f04c  lea     rax, [rbp+var_28]
0x18006f050  mov     [rbp+var_38], rax
0x18006f054  lea     rax, [rbp+arg_10]
0x18006f058  mov     [rbp+var_30], rax
0x18006f05c  lea     rax, qword_18009CF78
0x18006f063  mov     [rbp+lpMem], rax
0x18006f067  lock inc cs:qword_18009CF78
0x18006f06f  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, r14; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18006f076  jz      short loc_18006F093
0x18006f078  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18006f07f  lea     rcx, [rbp+var_38]
0x18006f083  call    ??R_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18006f088  nop
0x18006f089  lock add cs:qword_18009CF78, rdi
0x18006f091  jmp     short loc_18006F0A4
0x18006f093  lock add cs:qword_18009CF78, rdi
0x18006f09b  lea     rdx, [rbp+var_38]
0x18006f09f  call    ??$call@AEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@Z
0x18006f0a4  test    al, al
0x18006f0a6  jz      loc_18006F2DB
0x18006f0ac  cmp     word ptr cs:aError+0Ah, r14w; ""
0x18006f0b4  jz      short loc_18006F0BD
0x18006f0b6  call    cs:__imp_abort
0x18006f0bd  mov     [rbp+var_20], 1
0x18006f0c4  mov     ebx, 5
0x18006f0c9  mov     [rbp+var_1C], ebx
0x18006f0cc  lea     r12, aError; "error"
0x18006f0d3  mov     [rbp+var_10], r12
0x18006f0d7  lea     rax, [rbp+var_20]
0x18006f0db  mov     [rbp+var_28], rax
0x18006f0df  lea     rdx, [rbp+var_28]
0x18006f0e3  lea     rcx, [rbp+arg_10]
0x18006f0e7  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18006f0ec  test    al, al
0x18006f0ee  jz      loc_18006F18A
0x18006f0f4  cmp     word ptr cs:aError+0Ah, r14w; ""
0x18006f0fc  jz      short loc_18006F105
0x18006f0fe  call    cs:__imp_abort
0x18006f105  mov     [rbp+var_20], 1
0x18006f10c  mov     [rbp+var_1C], ebx
0x18006f10f  mov     [rbp+var_10], r12
0x18006f113  lea     rax, [rbp+var_20]
0x18006f117  mov     [rbp+var_28], rax
0x18006f11b  lea     r8, [rbp+var_28]
0x18006f11f  lea     rdx, [rbp+lpMem]
0x18006f123  lea     rcx, [rbp+arg_10]
0x18006f127  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18006f12c  mov     rbx, [rbp+lpMem]
0x18006f130  mov     rcx, [rbp+28h]; this
0x18006f134  mov     [rsp+70h+var_48], rbx; char *
0x18006f139  lea     rax, aErrorToGetDefa; "Error to get default cloud: %ls"
0x18006f140  mov     qword ptr [rsp+70h+var_50], rax; int
0x18006f145  mov     r9d, 80070057h; char *
0x18006f14b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\clouddirect\\common"...
0x18006f152  mov     edx, 59h ; 'Y'; void *
0x18006f157  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f15c  test    rbx, rbx
0x18006f15f  jz      short loc_18006F18A
0x18006f161  mov     eax, edi
0x18006f163  lock xadd [rbx+18h], eax
0x18006f168  sub     eax, 1
0x18006f16b  jnz     short loc_18006F182
0x18006f16d  nop
0x18006f16e  call    WINRT_IMPL_GetProcessHeap
0x18006f173  mov     rcx, rax; hHeap
0x18006f176  mov     r8, rbx; lpMem
0x18006f179  xor     edx, edx; dwFlags
0x18006f17b  call    WINRT_IMPL_HeapFree
0x18006f180  jmp     short loc_18006F18A
0x18006f182  test    eax, eax
0x18006f184  js      loc_18006F2D4
0x18006f18a  cmp     word ptr cs:aDefaultcloud+18h, r14w; ""
0x18006f192  jz      short loc_18006F19B
0x18006f194  call    cs:__imp_abort
0x18006f19b  mov     [rbp+var_20], 1
0x18006f1a2  mov     ebx, 0Ch
0x18006f1a7  mov     [rbp+var_1C], ebx
0x18006f1aa  lea     r12, aDefaultcloud; "DefaultCloud"
0x18006f1b1  mov     [rbp+var_10], r12
0x18006f1b5  lea     rax, [rbp+var_20]
0x18006f1b9  mov     [rbp+var_28], rax
0x18006f1bd  lea     rdx, [rbp+var_28]
0x18006f1c1  lea     rcx, [rbp+arg_10]
0x18006f1c5  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18006f1ca  test    al, al
0x18006f1cc  jz      loc_18006F30A
0x18006f1d2  cmp     word ptr cs:aDefaultcloud+18h, r14w; ""
0x18006f1da  jz      short loc_18006F1E3
0x18006f1dc  call    cs:__imp_abort
0x18006f1e3  mov     [rbp+var_20], 1
0x18006f1ea  mov     [rbp+var_1C], ebx
0x18006f1ed  mov     [rbp+var_10], r12
0x18006f1f1  lea     rax, [rbp+var_20]
0x18006f1f5  mov     [rbp+var_28], rax
0x18006f1f9  lea     r8, [rbp+var_28]
0x18006f1fd  lea     rdx, [rbp+lpMem]
0x18006f201  lea     rcx, [rbp+arg_10]
0x18006f205  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18006f20a  nop
0x18006f20b  mov     rax, [rbp+lpMem]
0x18006f20f  test    rax, rax
0x18006f212  jz      short loc_18006F26B
0x18006f214  mov     edx, [rax+4]
0x18006f217  mov     rcx, [rax+10h]
0x18006f21b  cmp     word ptr [rcx+rdx*2-2], 2Fh ; '/'
0x18006f221  jz      short loc_18006F26B
0x18006f223  lea     r8, asc_180082844; "/"
0x18006f22a  lea     rdx, [rbp+lpMem]
0x18006f22e  lea     rcx, [rbp+var_38]
0x18006f232  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEBG@Z; winrt::operator+(winrt::hstring const &,ushort const *)
0x18006f237  mov     rdx, rax
0x18006f23a  lea     rcx, [rbp+lpMem]
0x18006f23e  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18006f243  mov     rbx, [rbp+var_38]
0x18006f247  test    rbx, rbx
0x18006f24a  jz      short loc_18006F26B
0x18006f24c  mov     eax, edi
0x18006f24e  lock xadd [rbx+18h], eax
0x18006f253  sub     eax, 1
0x18006f256  jnz     short loc_18006F2C5
0x18006f258  nop
0x18006f259  call    WINRT_IMPL_GetProcessHeap
0x18006f25e  mov     rcx, rax; hHeap
0x18006f261  mov     r8, rbx; lpMem
0x18006f264  xor     edx, edx; dwFlags
0x18006f266  call    WINRT_IMPL_HeapFree
0x18006f26b  lea     rdx, [rbp+lpMem]
0x18006f26f  mov     rcx, rsi
0x18006f272  call    ?StringToLower@@YA?AUhstring@winrt@@AEBU12@@Z; StringToLower(winrt::hstring const &)
0x18006f277  nop
0x18006f278  mov     rbx, [rbp+lpMem]
0x18006f27c  test    rbx, rbx
0x18006f27f  jz      short loc_18006F29F
0x18006f281  lock xadd [rbx+18h], edi
0x18006f286  sub     edi, 1
0x18006f289  jnz     short loc_18006F2D0
0x18006f28b  nop
0x18006f28c  call    WINRT_IMPL_GetProcessHeap
0x18006f291  mov     rcx, rax; hHeap
0x18006f294  mov     r8, rbx; lpMem
0x18006f297  xor     edx, edx; dwFlags
0x18006f299  call    WINRT_IMPL_HeapFree
0x18006f29e  nop
0x18006f29f  cmp     [rbp+arg_10], r14
0x18006f2a3  jz      short loc_18006F2AE
0x18006f2a5  lea     rcx, [rbp+arg_10]
0x18006f2a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18006f2ae  mov     rax, rsi
0x18006f2b1  mov     rbx, [rsp+70h+arg_0]
0x18006f2b9  add     rsp, 70h
0x18006f2bd  pop     r14
0x18006f2bf  pop     r12
0x18006f2c1  pop     rdi
0x18006f2c2  pop     rsi
0x18006f2c3  pop     rbp
0x18006f2c4  retn
0x18006f2c5  test    eax, eax
0x18006f2c7  jns     short loc_18006F26B
0x18006f2c9  call    cs:__imp_abort
0x18006f2d0  test    edi, edi
0x18006f2d2  jns     short loc_18006F29F
0x18006f2d4  call    cs:__imp_abort
0x18006f2db  mov     ecx, 83750007h
0x18006f2e0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006f2e5  mov     r9d, eax; char *
0x18006f2e8  mov     rcx, [rbp+28h]; this
0x18006f2ec  lea     rax, aDefaultcloudPa; "DefaultCloud Parse Error"
0x18006f2f3  mov     qword ptr [rsp+70h+var_50], rax; int
0x18006f2f8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\clouddirect\\common"...
0x18006f2ff  mov     edx, 53h ; 'S'; void *
0x18006f304  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f30a  mov     ecx, 80070057h
0x18006f30f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006f314  mov     r9d, eax; char *
0x18006f317  mov     rcx, [rbp+28h]; this
0x18006f31b  lea     rax, aNoDefaultcloud; "No defaultCloud found for given tenant"
0x18006f322  mov     qword ptr [rsp+70h+var_50], rax; int
0x18006f327  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\clouddirect\\common"...
0x18006f32e  mov     edx, 68h ; 'h'; void *
0x18006f333  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
