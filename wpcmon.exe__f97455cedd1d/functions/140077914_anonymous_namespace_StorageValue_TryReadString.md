# _anonymous_namespace_::StorageValue::TryReadString

- ea: `0x140077914`
- end: `0x140077abf`
- name: `_anonymous_namespace_::StorageValue::TryReadString`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140077900`

## callees

- `0x140005530`
- `0x140009858`
- `0x14000b744`
- `0x14000ccac`
- `0x140075d74`
- `0x140077914`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400779b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077a7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077a95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400779b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077a7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077a95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400779d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400779d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall anonymous_namespace_::StorageValue::TryReadString(__int64 a1, HSTRING a2)
{
  __int64 v3; // rcx
  char **v4; // rax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v6; // r8
  __int64 v7; // rcx
  HSTRING string[3]; // [rsp+20h] [rbp-49h] BYREF
  HSTRING v10; // [rsp+38h] [rbp-31h] BYREF
  HSTRING *v11; // [rsp+40h] [rbp-29h]
  HSTRING v12; // [rsp+50h] [rbp-19h] BYREF
  HSTRING *v13; // [rsp+58h] [rbp-11h]
  __int128 v14; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]
  _OWORD v16[2]; // [rsp+88h] [rbp+1Fh] BYREF
  char **v17; // [rsp+A8h] [rbp+3Fh]

  string[0] = a2;
  v3 = *(_QWORD *)(a1 - 80);
  if ( !v3 )
  {
LABEL_6:
    v11 = 0;
    goto LABEL_7;
  }
  string[0] = 0;
  if ( (int) Windows::Data::Json::IJsonValueStatics::`vcall'{64,{flat}}(v3, string) < 0 )
  {
    if ( string[0] )
      WindowsDeleteString(string[0]);
    goto LABEL_6;
  }
  v10 = string[0];
  v11 = &v10;
LABEL_7:
  v13 = 0;
  if ( v11 )
  {
    v12 = *v11;
    *v11 = 0;
    v13 = &v12;
    if ( v11 )
    {
      if ( *v11 )
        WindowsDeleteString(*v11);
      v11 = 0;
    }
  }
  if ( v13 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*v13, 0);
    v14 = 0;
    si128 = 0;
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v14, StringRawBuffer, v6);
    v16[0] = v14;
    v16[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v14) = 0;
    v17 = (char **)v16;
    std::wstring::~wstring((char **)&v14);
    v4 = v17;
  }
  else
  {
    v4 = 0;
    v17 = 0;
  }
  if ( v4 )
  {
    v7 = std::wstring::wstring((__int64)(a2 + 2), (__int64)v4);
    v4 = v17;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)a2 + 5) = v7;
  if ( v4 )
  {
    std::wstring::~wstring(v4);
    v17 = 0;
  }
  if ( v13 )
  {
    if ( *v13 )
      WindowsDeleteString(*v13);
    v13 = 0;
  }
  if ( v11 && *v11 )
    WindowsDeleteString(*v11);
  return a2;
}

```

## disassembly

```asm
0x140077914  mov     [rsp-8+arg_10], rbx
0x140077919  mov     [rsp-8+arg_18], rdi
0x14007791e  push    rbp
0x14007791f  lea     rbp, [rsp-57h]
0x140077924  sub     rsp, 0C0h
0x14007792b  mov     rax, cs:__security_cookie
0x140077932  xor     rax, rsp
0x140077935  mov     [rbp+57h+var_10], rax
0x140077939  mov     rbx, rdx
0x14007793c  mov     [rbp+57h+string], rdx
0x140077940  xor     edi, edi
0x140077942  mov     rcx, [rcx-50h]
0x140077946  test    rcx, rcx
0x140077949  jz      short loc_14007797D
0x14007794b  mov     [rbp+57h+string], rdi
0x14007794f  lea     rdx, [rbp+57h+string]
0x140077953  call    ??_9IJsonValueStatics@Json@Data@Windows@@$BEA@AA; [thunk]: Windows::Data::Json::IJsonValueStatics::`vcall'{64,{flat}}
0x140077958  test    eax, eax
0x14007795a  js      short loc_14007796E
0x14007795c  mov     rax, [rbp+57h+string]
0x140077960  mov     [rbp+57h+var_88], rax
0x140077964  lea     rax, [rbp+57h+var_88]
0x140077968  mov     [rbp+57h+var_80], rax
0x14007796c  jmp     short loc_140077981
0x14007796e  mov     rcx, [rbp+57h+string]; string
0x140077972  test    rcx, rcx
0x140077975  jz      short loc_14007797D
0x140077977  call    cs:__imp_WindowsDeleteString
0x14007797d  mov     [rbp+57h+var_80], rdi
0x140077981  mov     [rbp+57h+var_68], rdi
0x140077985  mov     rcx, [rbp+57h+var_80]
0x140077989  test    rcx, rcx
0x14007798c  jz      short loc_1400779BB
0x14007798e  mov     rax, [rcx]
0x140077991  mov     [rbp+57h+var_70], rax
0x140077995  mov     [rcx], rdi
0x140077998  lea     rax, [rbp+57h+var_70]
0x14007799c  mov     [rbp+57h+var_68], rax
0x1400779a0  mov     rcx, [rbp+57h+var_80]
0x1400779a4  test    rcx, rcx
0x1400779a7  jz      short loc_1400779BB
0x1400779a9  mov     rcx, [rcx]; string
0x1400779ac  test    rcx, rcx
0x1400779af  jz      short loc_1400779B7
0x1400779b1  call    cs:__imp_WindowsDeleteString
0x1400779b7  mov     [rbp+57h+var_80], rdi
0x1400779bb  mov     rcx, [rbp+57h+var_68]
0x1400779bf  test    rcx, rcx
0x1400779c2  jnz     short loc_1400779CD
0x1400779c4  mov     rax, rdi
0x1400779c7  mov     [rbp+57h+var_18], rax
0x1400779cb  jmp     short loc_140077A37
0x1400779cd  xor     edx, edx; length
0x1400779cf  mov     rcx, [rcx]; string
0x1400779d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1400779d8  xorps   xmm0, xmm0
0x1400779db  movups  [rbp+57h+var_60], xmm0
0x1400779df  xorps   xmm1, xmm1
0x1400779e2  movdqu  [rbp+57h+var_50], xmm1
0x1400779e7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400779eb  inc     r8
0x1400779ee  cmp     [rax+r8*2], di
0x1400779f3  jnz     short loc_1400779EB
0x1400779f5  mov     rdx, rax
0x1400779f8  lea     rcx, [rbp+57h+var_60]
0x1400779fc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140077a01  movups  xmm1, [rbp+57h+var_60]
0x140077a05  movups  [rbp+57h+var_38], xmm1
0x140077a09  movups  xmm0, [rbp+57h+var_50]
0x140077a0d  movups  [rbp+57h+var_28], xmm0
0x140077a11  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140077a19  movdqu  [rbp+57h+var_50], xmm1
0x140077a1e  mov     word ptr [rbp+57h+var_60], di
0x140077a22  lea     rax, [rbp+57h+var_38]
0x140077a26  mov     [rbp+57h+var_18], rax
0x140077a2a  lea     rcx, [rbp+57h+var_60]
0x140077a2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140077a33  mov     rax, [rbp+57h+var_18]
0x140077a37  test    rax, rax
0x140077a3a  jz      short loc_140077A51
0x140077a3c  lea     rcx, [rbx+8]
0x140077a40  mov     rdx, rax
0x140077a43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140077a48  mov     rcx, rax
0x140077a4b  mov     rax, [rbp+57h+var_18]
0x140077a4f  jmp     short loc_140077A54
0x140077a51  mov     rcx, rdi
0x140077a54  mov     [rbx+28h], rcx
0x140077a58  test    rax, rax
0x140077a5b  jz      short loc_140077A69
0x140077a5d  mov     rcx, rax
0x140077a60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140077a65  mov     [rbp+57h+var_18], rdi
0x140077a69  mov     rax, [rbp+57h+var_68]
0x140077a6d  test    rax, rax
0x140077a70  jz      short loc_140077A84
0x140077a72  mov     rcx, [rax]; string
0x140077a75  test    rcx, rcx
0x140077a78  jz      short loc_140077A80
0x140077a7a  call    cs:__imp_WindowsDeleteString
0x140077a80  mov     [rbp+57h+var_68], rdi
0x140077a84  mov     rax, [rbp+57h+var_80]
0x140077a88  test    rax, rax
0x140077a8b  jz      short loc_140077A9B
0x140077a8d  mov     rcx, [rax]; string
0x140077a90  test    rcx, rcx
0x140077a93  jz      short loc_140077A9B
0x140077a95  call    cs:__imp_WindowsDeleteString
0x140077a9b  mov     rax, rbx
0x140077a9e  mov     rcx, [rbp+57h+var_10]
0x140077aa2  xor     rcx, rsp; StackCookie
0x140077aa5  call    __security_check_cookie
0x140077aaa  lea     r11, [rsp+0C0h+var_s0]
0x140077ab2  mov     rbx, [r11+20h]
0x140077ab6  mov     rdi, [r11+28h]
0x140077aba  mov     rsp, r11
0x140077abd  pop     rbp
0x140077abe  retn
```
