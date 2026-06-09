# GetLoadedHiveKeyNameInternal(wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x180009e30`
- end: `0x18000a1ff`
- name: `?GetLoadedHiveKeyNameInternal@@YAJPEB_WPEA_W_K@Z`
- size: `975`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180006f84`

## callees

- `0x180007568`
- `0x180007bcc`
- `0x180008248`
- `0x180009a88`
- `0x180009be8`
- `0x180009cb4`
- `0x180009e30`
- `0x18001b756`
- `0x18001b762`
- `0x18001b7b0`

## string_xrefs

- `0x180009e8b`: `Not-null check failed: FullOfflineHiveFilePath`
- `0x180009fc4`: `lusSanitizedFilePath.Length != 0`
- `0x18000a1c2`: `::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)`

## pseudocode

```c
__int64 __fastcall GetLoadedHiveKeyNameInternal(const wchar_t *a1, wchar_t *a2)
{
  wchar_t *v2; // rdi
  const wchar_t *v3; // rbx
  const char *v4; // rax
  __int64 result; // rax
  __int64 v6; // rbx
  wchar_t *v7; // rsi
  char v8; // r8
  __int64 v9; // rax
  __int128 *v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned __int64 i; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  wchar_t *v16; // rcx
  __int128 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h]
  const char *v19; // [rsp+38h] [rbp-C8h]
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  _QWORD v22[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v23[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+88h] [rbp-78h] BYREF
  void *Buf1; // [rsp+98h] [rbp-68h]
  __int64 v26; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[512]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v28; // [rsp+2B0h] [rbp+1B0h]
  __int64 v29; // [rsp+2B8h] [rbp+1B8h]
  wchar_t *v30; // [rsp+2C0h] [rbp+1C0h]

  v2 = a2;
  v3 = a1;
  if ( !a1 )
  {
    v18 = 27;
    *(_QWORD *)&v17 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    *((_QWORD *)&v17 + 1) = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: FullOfflineHiveFilePath";
LABEL_3:
    v19 = v4;
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v18 = 28;
    *(_QWORD *)&v17 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    *((_QWORD *)&v17 + 1) = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: KeyNameBuffer";
    goto LABEL_3;
  }
  v29 = 510;
  v30 = (wchar_t *)v27;
  memcpy_0(v27, L"{bf1a281b-ad7b-4476-ac95-f47682990ce7}", 0x4Cu);
  v28 = 76;
  Buf1 = 0;
  v24 = 0;
  result = RtlInitLUnicodeStringFromNullTerminatedString(v3, &v24);
  if ( (int)result >= 0 )
  {
    v6 = v24;
    v7 = (wchar_t *)Buf1;
    v17 = 0;
    v18 = 0;
    if ( (unsigned __int64)v24 < 8
      || (memcmp_0(Buf1, L"\\\\?\\", 8u)
        ? (v8 = 0, v9 = 0, a1 = 0, a2 = 0)
        : (a1 = (const wchar_t *)(v6 - 8), v8 = 1, v9 = v6 - 8, a2 = v7 + 4),
          !v8) )
    {
      a1 = (const wchar_t *)*((_QWORD *)&v24 + 1);
      v9 = v6;
      a2 = v7;
    }
    *(_QWORD *)&v24 = v9;
    *((_QWORD *)&v24 + 1) = a1;
    Buf1 = a2;
    if ( !v9 )
    {
      v18 = 44;
      *(_QWORD *)&v17 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
      *((_QWORD *)&v17 + 1) = "GetLoadedHiveKeyNameInternal";
      v4 = "lusSanitizedFilePath.Length != 0";
      goto LABEL_3;
    }
    v10 = &v24;
    if ( (v9 & 0xFFFFFFFFFFFFFFFEuLL) >= 0x1B2 )
    {
      v26 = 0;
      result = RtlHashEncodedLBlob(&v24, RtlDecodeUtf16LE, FsnpDowncaseChar, &v26, v17, *((_QWORD *)&v17 + 1), v18);
      if ( (int)result < 0 )
        return result;
      v22[1] = 8;
      v22[0] = 6;
      v22[2] = L"..{";
      v23[0] = 6;
      v23[2] = L"}..";
      v23[1] = 8;
      v21 = 0;
      v20 = 0;
      result = Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(&v24, 0, 97, &v20, 0, 0, 0);
      if ( (int)result < 0 )
        return result;
      result = ((__int64 (__fastcall *)(__int128 *, unsigned __int64, __int64, __int128 *))Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>)(
                 &v24,
                 ((unsigned __int64)v24 >> 1) - 98,
                 98,
                 &v17);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 &v20,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v22,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(
                 v15,
                 v26,
                 v27);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v23,
                 v27);
      if ( (int)result < 0 )
        return result;
      v10 = &v17;
    }
    result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
               v10,
               v27);
    if ( (int)result < 0 )
      return result;
    v12 = 38;
    for ( i = v28 >> 1; v12 < i; ++v12 )
    {
      v11 = (__int64)v30;
      if ( v30[v12] == 92 )
        v30[v12] = 47;
    }
    if ( i > 0x7FFFFFFE )
    {
      v14 = -1073741811;
      *v2 = 0;
LABEL_38:
      v18 = 95;
      *(_QWORD *)&v17 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
      *((_QWORD *)&v17 + 1) = "GetLoadedHiveKeyNameInternal";
      v19 = "::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)";
      RtlReportErrorOrigination(v12, v11, v14);
      return v14;
    }
    v16 = v30;
    v11 = 256;
    do
    {
      if ( !i )
        break;
      if ( !*v16 )
        break;
      *v2++ = *v16++;
      --i;
      --v11;
    }
    while ( v11 );
    v12 = (unsigned __int64)(v2 - 1);
    v14 = v11 == 0 ? 0x80000005 : 0;
    if ( v11 )
      v12 = (unsigned __int64)v2;
    *(_WORD *)v12 = 0;
    if ( !v11 )
      goto LABEL_38;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009e30  mov     [rsp-8+arg_10], rbx
0x180009e35  push    rbp
0x180009e36  push    rsi
0x180009e37  push    rdi
0x180009e38  push    r14
0x180009e3a  push    r15
0x180009e3c  lea     rbp, [rsp-1E0h]
0x180009e44  sub     rsp, 2E0h
0x180009e4b  mov     rax, cs:__security_cookie
0x180009e52  xor     rax, rsp
0x180009e55  mov     [rbp+200h+var_30], rax
0x180009e5c  xor     r14d, r14d
0x180009e5f  mov     rdi, rdx
0x180009e62  mov     rbx, rcx
0x180009e65  test    rcx, rcx
0x180009e68  jnz     short loc_180009EAC
0x180009e6a  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180009e71  mov     [rsp+300h+var_2D0], 1Bh
0x180009e7a  mov     qword ptr [rsp+300h+var_2E0], rax
0x180009e7f  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180009e86  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x180009e8b  lea     rax, aNotNullCheckFa; "Not-null check failed: FullOfflineHiveF"...
0x180009e92  mov     r8d, 0C000000Dh
0x180009e98  mov     [rsp+300h+var_2C8], rax
0x180009e9d  call    RtlReportErrorOrigination
0x180009ea2  mov     eax, 0C000000Dh
0x180009ea7  jmp     loc_18000A1D9
0x180009eac  test    rdi, rdi
0x180009eaf  jnz     short loc_180009EDB
0x180009eb1  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180009eb8  mov     [rsp+300h+var_2D0], 1Ch
0x180009ec1  mov     qword ptr [rsp+300h+var_2E0], rax
0x180009ec6  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180009ecd  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x180009ed2  lea     rax, aNotNullCheckFa_7; "Not-null check failed: KeyNameBuffer"
0x180009ed9  jmp     short loc_180009E92
0x180009edb  lea     rax, [rbp+200h+var_250]
0x180009edf  mov     [rbp+200h+var_48], 1FEh
0x180009eea  mov     esi, 4Ch ; 'L'
0x180009eef  mov     [rbp+200h+var_40], rax
0x180009ef6  mov     r8d, esi; Size
0x180009ef9  lea     rdx, aBf1a281bAd7b44; "{bf1a281b-ad7b-4476-ac95-f47682990ce7}"
0x180009f00  lea     rcx, [rbp+200h+var_250]; void *
0x180009f04  call    memcpy_0
0x180009f09  xorps   xmm0, xmm0
0x180009f0c  mov     [rbp+200h+var_50], rsi
0x180009f13  xor     eax, eax
0x180009f15  lea     rdx, [rbp+200h+var_278]
0x180009f19  mov     rcx, rbx
0x180009f1c  mov     [rbp+200h+Buf1], rax
0x180009f20  movups  [rbp+200h+var_278], xmm0
0x180009f24  call    RtlInitLUnicodeStringFromNullTerminatedString
0x180009f29  test    eax, eax
0x180009f2b  js      loc_18000A1D9
0x180009f31  mov     rbx, qword ptr [rbp+200h+var_278]
0x180009f35  xor     eax, eax
0x180009f37  mov     rsi, [rbp+200h+Buf1]
0x180009f3b  xorps   xmm0, xmm0
0x180009f3e  movups  [rsp+300h+var_2E0], xmm0
0x180009f43  mov     [rsp+300h+var_2D0], rax
0x180009f48  lea     r15d, [rax+8]
0x180009f4c  cmp     rbx, r15
0x180009f4f  jb      short loc_180009F88
0x180009f51  mov     r8d, r15d; Size
0x180009f54  lea     rdx, Buf2; "\\\\?\\"
0x180009f5b  mov     rcx, rsi; Buf1
0x180009f5e  call    memcmp_0
0x180009f63  test    eax, eax
0x180009f65  jnz     short loc_180009F77
0x180009f67  lea     rcx, [rbx-8]
0x180009f6b  mov     r8b, 1
0x180009f6e  mov     rax, rcx
0x180009f71  lea     rdx, [rsi+8]
0x180009f75  jmp     short loc_180009F83
0x180009f77  mov     r8b, r14b
0x180009f7a  mov     rax, r14
0x180009f7d  mov     rcx, r14
0x180009f80  mov     rdx, r14
0x180009f83  test    r8b, r8b
0x180009f86  jnz     short loc_180009F92
0x180009f88  mov     rcx, qword ptr [rbp+200h+var_278+8]
0x180009f8c  mov     rax, rbx
0x180009f8f  mov     rdx, rsi
0x180009f92  mov     qword ptr [rbp+200h+var_278], rax
0x180009f96  mov     qword ptr [rbp+200h+var_278+8], rcx
0x180009f9a  mov     [rbp+200h+Buf1], rdx
0x180009f9e  test    rax, rax
0x180009fa1  jnz     short loc_180009FD0
0x180009fa3  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180009faa  mov     [rsp+300h+var_2D0], 2Ch ; ','
0x180009fb3  mov     qword ptr [rsp+300h+var_2E0], rax
0x180009fb8  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180009fbf  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x180009fc4  lea     rax, aLussanitizedfi; "lusSanitizedFilePath.Length != 0"
0x180009fcb  jmp     loc_180009E92
0x180009fd0  and     rax, 0FFFFFFFFFFFFFFFEh
0x180009fd4  lea     rcx, [rbp+200h+var_278]
0x180009fd8  cmp     rax, 1B2h
0x180009fde  jnb     short loc_18000A03B
0x180009fe0  lea     rdx, [rbp+200h+var_250]
0x180009fe4  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180009fe9  test    eax, eax
0x180009feb  js      loc_18000A1D9
0x180009ff1  mov     rax, [rbp+200h+var_50]
0x180009ff8  mov     ecx, 26h ; '&'
0x180009ffd  shr     rax, 1
0x18000a000  cmp     rax, rcx
0x18000a003  jbe     short loc_18000A021
0x18000a005  mov     rdx, [rbp+200h+var_40]
0x18000a00c  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x18000a011  jnz     short loc_18000A019
0x18000a013  mov     word ptr [rdx+rcx*2], 2Fh ; '/'
0x18000a019  inc     rcx
0x18000a01c  cmp     rcx, rax
0x18000a01f  jb      short loc_18000A005
0x18000a021  cmp     rax, 7FFFFFFEh
0x18000a027  jbe     loc_18000A14D
0x18000a02d  mov     ebx, 0C000000Dh
0x18000a032  mov     [rdi], r14w
0x18000a036  jmp     loc_18000A19E
0x18000a03b  lea     r9, [rbp+200h+var_260]
0x18000a03f  mov     [rbp+200h+var_260], r14
0x18000a043  lea     r8, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x18000a04a  lea     rdx, RtlDecodeUtf16LE
0x18000a051  call    RtlHashEncodedLBlob
0x18000a056  test    eax, eax
0x18000a058  js      loc_18000A1D9
0x18000a05e  mov     ecx, 6
0x18000a063  mov     [rsp+300h+var_2A0], r15
0x18000a068  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0CO@@0CO@@0HL@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "..{"
0x18000a06f  mov     [rsp+300h+var_2A8], rcx
0x18000a074  mov     [rsp+300h+var_298], rax
0x18000a079  lea     r9, [rsp+300h+var_2C0]
0x18000a07e  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0HN@@0CO@@0CO@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "}.."
0x18000a085  mov     [rsp+300h+var_290], rcx
0x18000a08a  mov     [rbp+200h+var_280], rax
0x18000a08e  lea     r8d, [rcx+5Bh]
0x18000a092  xor     eax, eax
0x18000a094  mov     [rsp+300h+var_288], r15
0x18000a099  xorps   xmm0, xmm0
0x18000a09c  mov     [rsp+300h+var_2B0], rax
0x18000a0a1  xorps   xmm1, xmm1
0x18000a0a4  mov     [rsp+300h+var_2D0], rax
0x18000a0a9  xor     edx, edx
0x18000a0ab  lea     rcx, [rbp+200h+var_278]
0x18000a0af  movups  [rsp+300h+var_2C0], xmm0
0x18000a0b4  movups  [rsp+300h+var_2E0], xmm1
0x18000a0b9  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x18000a0be  test    eax, eax
0x18000a0c0  js      loc_18000A1D9
0x18000a0c6  mov     rdx, qword ptr [rbp+200h+var_278]
0x18000a0ca  lea     r9, [rsp+300h+var_2E0]
0x18000a0cf  shr     rdx, 1
0x18000a0d2  lea     rcx, [rbp+200h+var_278]
0x18000a0d6  mov     r8d, 62h ; 'b'
0x18000a0dc  sub     rdx, r8
0x18000a0df  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x18000a0e4  test    eax, eax
0x18000a0e6  js      loc_18000A1D9
0x18000a0ec  lea     rdx, [rbp+200h+var_250]
0x18000a0f0  lea     rcx, [rsp+300h+var_2C0]
0x18000a0f5  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18000a0fa  test    eax, eax
0x18000a0fc  js      loc_18000A1D9
0x18000a102  lea     rdx, [rbp+200h+var_250]
0x18000a106  lea     rcx, [rsp+300h+var_2A8]
0x18000a10b  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18000a110  test    eax, eax
0x18000a112  js      loc_18000A1D9
0x18000a118  mov     rdx, [rbp+200h+var_260]
0x18000a11c  lea     r8, [rbp+200h+var_250]
0x18000a120  call    ??$AppendInteger@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@_K@Rtl@StringUtil@Windows@@YAJK_KPEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(ulong,unsigned __int64,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18000a125  test    eax, eax
0x18000a127  js      loc_18000A1D9
0x18000a12d  lea     rdx, [rbp+200h+var_250]
0x18000a131  lea     rcx, [rsp+300h+var_290]
0x18000a136  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18000a13b  test    eax, eax
0x18000a13d  js      loc_18000A1D9
0x18000a143  lea     rcx, [rsp+300h+var_2E0]
0x18000a148  jmp     loc_180009FE0
0x18000a14d  mov     rcx, [rbp+200h+var_40]
0x18000a154  mov     edx, 100h
0x18000a159  test    rax, rax
0x18000a15c  jz      short loc_18000A17D
0x18000a15e  movzx   r8d, word ptr [rcx]
0x18000a162  test    r8w, r8w
0x18000a166  jz      short loc_18000A17D
0x18000a168  mov     [rdi], r8w
0x18000a16c  add     rcx, 2
0x18000a170  add     rdi, 2
0x18000a174  dec     rax
0x18000a177  sub     rdx, 1
0x18000a17b  jnz     short loc_18000A159
0x18000a17d  mov     rax, rdx
0x18000a180  lea     rcx, [rdi-2]
0x18000a184  neg     rax
0x18000a187  sbb     ebx, ebx
0x18000a189  not     ebx
0x18000a18b  and     ebx, 80000005h
0x18000a191  test    rdx, rdx
0x18000a194  cmovnz  rcx, rdi
0x18000a198  mov     [rcx], r14w
0x18000a19c  jnz     short loc_18000A1D7
0x18000a19e  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x18000a1a5  mov     [rsp+300h+var_2D0], 5Fh ; '_'
0x18000a1ae  mov     qword ptr [rsp+300h+var_2E0], rax
0x18000a1b3  mov     r8d, ebx
0x18000a1b6  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x18000a1bd  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x18000a1c2  lea     rax, aRtlstringcchco; "::RtlStringCchCopyNW(KeyNameBuffer, Key"...
0x18000a1c9  mov     [rsp+300h+var_2C8], rax
0x18000a1ce  call    RtlReportErrorOrigination
0x18000a1d3  mov     eax, ebx
0x18000a1d5  jmp     short loc_18000A1D9
0x18000a1d7  xor     eax, eax
0x18000a1d9  mov     rcx, [rbp+200h+var_30]
0x18000a1e0  xor     rcx, rsp; StackCookie
0x18000a1e3  call    __security_check_cookie
0x18000a1e8  mov     rbx, [rsp+300h+arg_10]
0x18000a1f0  add     rsp, 2E0h
0x18000a1f7  pop     r15
0x18000a1f9  pop     r14
0x18000a1fb  pop     rdi
0x18000a1fc  pop     rsi
0x18000a1fd  pop     rbp
0x18000a1fe  retn
```
