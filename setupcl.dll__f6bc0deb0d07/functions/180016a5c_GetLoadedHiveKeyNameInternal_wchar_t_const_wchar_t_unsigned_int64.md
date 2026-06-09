# GetLoadedHiveKeyNameInternal(wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x180016a5c`
- end: `0x180016d7f`
- name: `?GetLoadedHiveKeyNameInternal@@YAJPEB_WPEA_W_K@Z`
- size: `803`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180016e50`

## callees

- `0x1800165c8`
- `0x1800166bc`
- `0x1800168e0`
- `0x1800169d0`
- `0x180016a5c`
- `0x180016da0`
- `0x180016dc4`
- `0x180016f70`
- `0x180017028`
- `0x1800179ad`
- `0x1800179e0`

## string_xrefs

- `0x180016aba`: `Not-null check failed: FullOfflineHiveFilePath`
- `0x180016bb0`: `lusSanitizedFilePath.Length != 0`
- `0x180016c4c`: `::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)`

## pseudocode

```c
__int64 __fastcall GetLoadedHiveKeyNameInternal(const wchar_t *a1, wchar_t *a2)
{
  const char *v4; // rax
  __int64 v5; // r8
  __int64 result; // rax
  __int64 v7; // rax
  __int128 v8; // xmm1
  const char **v9; // rcx
  wchar_t *v10; // rdx
  unsigned __int64 v11; // rax
  unsigned __int64 i; // r9
  int v13; // eax
  __int64 v14; // rcx
  const char *v15; // [rsp+20h] [rbp-E0h] BYREF
  const char *v16; // [rsp+28h] [rbp-D8h]
  __int64 v17; // [rsp+30h] [rbp-D0h]
  const char *v18; // [rsp+38h] [rbp-C8h]
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  _QWORD v21[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v22[3]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+88h] [rbp-78h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[512]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v28; // [rsp+2B0h] [rbp+1B0h]
  __int64 v29; // [rsp+2B8h] [rbp+1B8h]
  wchar_t *v30; // [rsp+2C0h] [rbp+1C0h]

  v23 = 0;
  if ( !a1 )
  {
    v17 = 27;
    v15 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    v16 = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: FullOfflineHiveFilePath";
LABEL_3:
    v5 = 3221225485LL;
LABEL_4:
    v18 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v23,
             &v15,
             v5);
  }
  if ( !a2 )
  {
    v17 = 28;
    v15 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    v16 = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: KeyNameBuffer";
    goto LABEL_3;
  }
  v29 = 510;
  v30 = (wchar_t *)v27;
  memcpy_0(v27, L"{bf1a281b-ad7b-4476-ac95-f47682990ce7}", 0x4Cu);
  v28 = 76;
  v25 = 0;
  v24 = 0;
  result = RtlInitLUnicodeStringFromNullTerminatedString(a1, &v24);
  if ( (int)result >= 0 )
  {
    v7 = Windows::StringUtil::TrimLongPathPrefix<_LUNICODE_STRING>((__int64)&v15, (unsigned __int64 *)&v24);
    v8 = *(_OWORD *)v7;
    v24 = v8;
    v25 = *(_QWORD *)(v7 + 16);
    if ( !(_QWORD)v8 )
    {
      v17 = 44;
      v15 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
      v16 = "GetLoadedHiveKeyNameInternal";
      v4 = "lusSanitizedFilePath.Length != 0";
      goto LABEL_3;
    }
    v9 = (const char **)&v24;
    if ( ((unsigned __int64)v8 & 0xFFFFFFFFFFFFFFFEuLL) >= 0x1B2 )
    {
      v26 = 0;
      result = RtlHashEncodedLBlob(&v24, RtlDecodeUtf16LE, FsnpDowncaseChar, &v26);
      if ( (int)result < 0 )
        return result;
      v21[2] = L"..{";
      v21[0] = 6;
      v22[2] = L"}..";
      v22[0] = 6;
      v21[1] = 8;
      v22[1] = 8;
      v20 = 0;
      v19 = 0;
      result = Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(&v24, 0, 97, &v19, 0, 0, 0);
      if ( (int)result < 0 )
        return result;
      result = ((__int64 (__fastcall *)(__int128 *, unsigned __int64, __int64, const char **))Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>)(
                 &v24,
                 ((unsigned __int64)v24 >> 1) - 98,
                 98,
                 &v15);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 &v19,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v21,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(
                 v14,
                 v26,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v22,
                 v27);
      if ( (int)result < 0 )
        return result;
      v9 = &v15;
    }
    result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
               v9,
               v27);
    if ( (int)result >= 0 )
    {
      v11 = 38;
      for ( i = v28 >> 1; v11 < i; ++v11 )
      {
        v10 = v30;
        if ( v30[v11] == 92 )
          v30[v11] = 47;
      }
      v13 = RtlStringCchCopyNW(a2, (unsigned __int64)v10, v30, i);
      v5 = (unsigned int)v13;
      if ( v13 < 0 )
      {
        v17 = 95;
        v15 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
        v16 = "GetLoadedHiveKeyNameInternal";
        v4 = "::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)";
        goto LABEL_4;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016a5c  mov     [rsp-8+arg_10], rbx
0x180016a61  mov     [rsp-8+arg_18], rdi
0x180016a66  push    rbp
0x180016a67  lea     rbp, [rsp-1E0h]
0x180016a6f  sub     rsp, 2E0h
0x180016a76  mov     rax, cs:__security_cookie
0x180016a7d  xor     rax, rsp
0x180016a80  mov     [rbp+1E0h+var_10], rax
0x180016a87  mov     [rbp+1E0h+var_258], 0
0x180016a8e  mov     rdi, rdx
0x180016a91  mov     rbx, rcx
0x180016a94  test    rcx, rcx
0x180016a97  jnz     short loc_180016ADF
0x180016a99  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180016aa0  mov     [rsp+2E0h+var_2B0], 1Bh
0x180016aa9  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180016aae  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180016ab5  mov     qword ptr [rsp+2E0h+var_2C0+8], rax
0x180016aba  lea     rax, aNotNullCheckFa; "Not-null check failed: FullOfflineHiveF"...
0x180016ac1  mov     r8d, 0C000000Dh
0x180016ac7  lea     rdx, [rsp+2E0h+var_2C0]
0x180016acc  mov     [rsp+2E0h+var_2A8], rax
0x180016ad1  lea     rcx, [rbp+1E0h+var_258]
0x180016ad5  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180016ada  jmp     loc_180016D5B
0x180016adf  test    rdi, rdi
0x180016ae2  jnz     short loc_180016B0E
0x180016ae4  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180016aeb  mov     [rsp+2E0h+var_2B0], 1Ch
0x180016af4  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180016af9  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180016b00  mov     qword ptr [rsp+2E0h+var_2C0+8], rax
0x180016b05  lea     rax, aNotNullCheckFa_1; "Not-null check failed: KeyNameBuffer"
0x180016b0c  jmp     short loc_180016AC1
0x180016b0e  lea     rax, [rbp+1E0h+var_230]
0x180016b12  mov     [rbp+1E0h+var_28], 1FEh
0x180016b1d  mov     r8d, 4Ch ; 'L'; Size
0x180016b23  mov     [rbp+1E0h+var_20], rax
0x180016b2a  lea     rdx, aBf1a281bAd7b44; "{bf1a281b-ad7b-4476-ac95-f47682990ce7}"
0x180016b31  lea     rcx, [rbp+1E0h+var_230]; void *
0x180016b35  call    memcpy_0
0x180016b3a  xorps   xmm0, xmm0
0x180016b3d  mov     [rbp+1E0h+var_30], 4Ch ; 'L'
0x180016b48  xor     eax, eax
0x180016b4a  lea     rdx, [rbp+1E0h+var_250]
0x180016b4e  mov     rcx, rbx
0x180016b51  mov     [rbp+1E0h+var_240], rax
0x180016b55  movups  [rbp+1E0h+var_250], xmm0
0x180016b59  call    RtlInitLUnicodeStringFromNullTerminatedString
0x180016b5e  test    eax, eax
0x180016b60  js      loc_180016D5B
0x180016b66  lea     rdx, [rbp+1E0h+var_250]
0x180016b6a  lea     rcx, [rsp+2E0h+var_2C0]
0x180016b6f  call    ??$TrimLongPathPrefix@U_LUNICODE_STRING@@@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@AEBU2@@Z; Windows::StringUtil::TrimLongPathPrefix<_LUNICODE_STRING>(_LUNICODE_STRING const &)
0x180016b74  movups  xmm1, xmmword ptr [rax]
0x180016b77  movups  [rbp+1E0h+var_250], xmm1
0x180016b7b  movsd   xmm0, qword ptr [rax+10h]
0x180016b80  movq    rax, xmm1
0x180016b85  movsd   [rbp+1E0h+var_240], xmm0
0x180016b8a  test    rax, rax
0x180016b8d  jnz     short loc_180016BBC
0x180016b8f  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180016b96  mov     [rsp+2E0h+var_2B0], 2Ch ; ','
0x180016b9f  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180016ba4  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180016bab  mov     qword ptr [rsp+2E0h+var_2C0+8], rax
0x180016bb0  lea     rax, aLussanitizedfi; "lusSanitizedFilePath.Length != 0"
0x180016bb7  jmp     loc_180016AC1
0x180016bbc  and     rax, 0FFFFFFFFFFFFFFFEh
0x180016bc0  lea     rcx, [rbp+1E0h+var_250]
0x180016bc4  cmp     rax, 1B2h
0x180016bca  jnb     loc_180016C58
0x180016bd0  lea     rdx, [rbp+1E0h+var_230]
0x180016bd4  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180016bd9  test    eax, eax
0x180016bdb  js      loc_180016D5B
0x180016be1  mov     r9, [rbp+1E0h+var_30]
0x180016be8  mov     eax, 26h ; '&'
0x180016bed  shr     r9, 1; unsigned __int64
0x180016bf0  cmp     r9, rax
0x180016bf3  jbe     short loc_180016C11
0x180016bf5  mov     rdx, [rbp+1E0h+var_20]; unsigned __int64
0x180016bfc  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x180016c01  jnz     short loc_180016C09
0x180016c03  mov     word ptr [rdx+rax*2], 2Fh ; '/'
0x180016c09  inc     rax
0x180016c0c  cmp     rax, r9
0x180016c0f  jb      short loc_180016BF5
0x180016c11  mov     r8, [rbp+1E0h+var_20]; wchar_t *
0x180016c18  mov     rcx, rdi; wchar_t *
0x180016c1b  call    ?RtlStringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; RtlStringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180016c20  mov     r8d, eax
0x180016c23  test    eax, eax
0x180016c25  jns     loc_180016D59
0x180016c2b  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180016c32  mov     [rsp+2E0h+var_2B0], 5Fh ; '_'
0x180016c3b  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180016c40  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180016c47  mov     qword ptr [rsp+2E0h+var_2C0+8], rax
0x180016c4c  lea     rax, aRtlstringcchco; "::RtlStringCchCopyNW(KeyNameBuffer, Key"...
0x180016c53  jmp     loc_180016AC7
0x180016c58  lea     r9, [rbp+1E0h+var_238]
0x180016c5c  mov     [rbp+1E0h+var_238], 0
0x180016c64  lea     r8, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x180016c6b  lea     rdx, RtlDecodeUtf16LE
0x180016c72  call    RtlHashEncodedLBlob
0x180016c77  test    eax, eax
0x180016c79  js      loc_180016D5B
0x180016c7f  mov     edx, 6
0x180016c84  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0CO@@0CO@@0HL@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "..{"
0x180016c8b  mov     [rsp+2E0h+var_278], rax
0x180016c90  lea     r9, [rsp+2E0h+var_2A0]
0x180016c95  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0HN@@0CO@@0CO@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "}.."
0x180016c9c  mov     [rsp+2E0h+var_288], rdx
0x180016ca1  mov     [rbp+1E0h+var_260], rax
0x180016ca5  xorps   xmm0, xmm0
0x180016ca8  lea     ecx, [rdx+2]
0x180016cab  mov     [rsp+2E0h+var_270], rdx
0x180016cb0  xor     eax, eax
0x180016cb2  mov     [rsp+2E0h+var_280], rcx
0x180016cb7  mov     [rsp+2E0h+var_268], rcx
0x180016cbc  lea     r8d, [rcx+59h]
0x180016cc0  xorps   xmm1, xmm1
0x180016cc3  mov     [rsp+2E0h+var_290], rax
0x180016cc8  lea     rcx, [rbp+1E0h+var_250]
0x180016ccc  mov     [rsp+2E0h+var_2B0], rax
0x180016cd1  xor     edx, edx
0x180016cd3  movups  [rsp+2E0h+var_2A0], xmm0
0x180016cd8  movups  [rsp+2E0h+var_2C0], xmm1
0x180016cdd  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x180016ce2  test    eax, eax
0x180016ce4  js      short loc_180016D5B
0x180016ce6  mov     rdx, qword ptr [rbp+1E0h+var_250]
0x180016cea  lea     r9, [rsp+2E0h+var_2C0]
0x180016cef  shr     rdx, 1
0x180016cf2  lea     rcx, [rbp+1E0h+var_250]
0x180016cf6  mov     r8d, 62h ; 'b'
0x180016cfc  sub     rdx, r8
0x180016cff  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x180016d04  test    eax, eax
0x180016d06  js      short loc_180016D5B
0x180016d08  lea     rdx, [rbp+1E0h+var_230]
0x180016d0c  lea     rcx, [rsp+2E0h+var_2A0]
0x180016d11  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180016d16  test    eax, eax
0x180016d18  js      short loc_180016D5B
0x180016d1a  lea     rdx, [rbp+1E0h+var_230]
0x180016d1e  lea     rcx, [rsp+2E0h+var_288]
0x180016d23  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180016d28  test    eax, eax
0x180016d2a  js      short loc_180016D5B
0x180016d2c  mov     rdx, [rbp+1E0h+var_238]
0x180016d30  lea     r8, [rbp+1E0h+var_230]
0x180016d34  call    ??$AppendInteger@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@_K@Rtl@StringUtil@Windows@@YAJK_KPEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(ulong,unsigned __int64,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180016d39  test    eax, eax
0x180016d3b  js      short loc_180016D5B
0x180016d3d  lea     rdx, [rbp+1E0h+var_230]
0x180016d41  lea     rcx, [rsp+2E0h+var_270]
0x180016d46  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180016d4b  test    eax, eax
0x180016d4d  js      short loc_180016D5B
0x180016d4f  lea     rcx, [rsp+2E0h+var_2C0]
0x180016d54  jmp     loc_180016BD0
0x180016d59  xor     eax, eax
0x180016d5b  mov     rcx, [rbp+1E0h+var_10]
0x180016d62  xor     rcx, rsp; StackCookie
0x180016d65  call    __security_check_cookie
0x180016d6a  lea     r11, [rsp+2E0h+var_s0]
0x180016d72  mov     rbx, [r11+20h]
0x180016d76  mov     rdi, [r11+28h]
0x180016d7a  mov     rsp, r11
0x180016d7d  pop     rbp
0x180016d7e  retn
```
