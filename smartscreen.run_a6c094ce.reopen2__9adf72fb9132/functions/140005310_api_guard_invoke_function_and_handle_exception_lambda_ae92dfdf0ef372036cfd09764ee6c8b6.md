# api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6__&_

- ea: `0x140005310`
- end: `0x1400054dd`
- name: `api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6__&_`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004e90`

## callees

- `0x140005310`
- `0x1400054f0`
- `0x140016c8c`
- `0x140016ce4`
- `0x140019844`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000533a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400053b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400053d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000533a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400053b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400053d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000539b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000539b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005411`
- `SmartScreen!ReportLaunch` at `0x14000543f`
- `SmartScreen!ReportLaunch` at `0x14000543f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6____(
        __int64 a1,
        HSTRING **a2)
{
  const WCHAR *StringRawBuffer; // rax
  HSTRING *v4; // rax
  PCWSTR v5; // rax
  const WCHAR *v6; // rdx
  HSTRING *v7; // rax
  PCWSTR v8; // rax
  __int128 *v9; // rdx
  __int128 *v10; // rcx
  wil *v11; // rcx
  __int64 result; // rax
  HSTRING string; // [rsp+20h] [rbp-68h] BYREF
  __int128 v14; // [rsp+28h] [rbp-60h] BYREF
  __m128i si128; // [rsp+38h] [rbp-50h]
  __int128 v16; // [rsp+48h] [rbp-40h] BYREF
  __int128 v17; // [rsp+58h] [rbp-30h]
  UINT32 length; // [rsp+68h] [rbp-20h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(*a2[1], 0);
  try
  {
    v4 = windows::rt::create_hstring(&string, StringRawBuffer);
    length = 0;
    v5 = WindowsGetStringRawBuffer(*v4, &length);
    v16 = 0;
    v17 = 0;
    if ( length )
      std::wstring::_Construct<1,unsigned short const *>(&v16, v5, length);
    else
      std::wstring::_Construct_empty(&v16);
    WindowsDeleteString(string);
    v6 = WindowsGetStringRawBuffer(**a2, 0);
    v7 = windows::rt::create_hstring(&string, v6);
    length = 0;
    v8 = WindowsGetStringRawBuffer(*v7, &length);
    v14 = 0;
    si128 = 0;
    if ( length )
      std::wstring::_Construct<1,unsigned short const *>(&v14, v8, length);
    else
      std::wstring::_Construct_empty(&v14);
    WindowsDeleteString(string);
    v9 = &v16;
    if ( *((_QWORD *)&v17 + 1) > 7u )
      v9 = (__int128 *)v16;
    v10 = &v14;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = (__int128 *)v14;
    ReportLaunch(v10, v9);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v14, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v14) = 0;
    if ( *((_QWORD *)&v17 + 1) > 7u )
      std::_Deallocate<16>(v16, 2LL * *((_QWORD *)&v17 + 1) + 2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v11);
  }
  return result;
}

```

## disassembly

```asm
0x140005310  mov     [rsp+arg_0], rbx
0x140005315  push    rdi
0x140005316  sub     rsp, 80h
0x14000531d  mov     rax, cs:__security_cookie
0x140005324  xor     rax, rsp
0x140005327  mov     [rsp+88h+var_18], rax
0x14000532c  mov     rbx, rdx
0x14000532f  xor     edi, edi
0x140005331  mov     rcx, [rdx+8]
0x140005335  xor     edx, edx; length
0x140005337  mov     rcx, [rcx]; string
0x14000533a  call    cs:__imp_WindowsGetStringRawBuffer
0x140005341  nop     dword ptr [rax+rax+00h]
0x140005346  mov     rdx, rax
0x140005349  lea     rcx, [rsp+88h+string]
0x14000534e  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x140005353  nop
0x140005354  mov     [rsp+88h+length], edi
0x140005358  lea     rdx, [rsp+88h+length]; length
0x14000535d  mov     rcx, [rax]; string
0x140005360  call    cs:__imp_WindowsGetStringRawBuffer
0x140005367  nop     dword ptr [rax+rax+00h]
0x14000536c  mov     r8d, [rsp+88h+length]
0x140005371  xorps   xmm0, xmm0
0x140005374  movups  [rsp+88h+var_40], xmm0
0x140005379  xorps   xmm1, xmm1
0x14000537c  movdqu  [rsp+88h+var_30], xmm1
0x140005382  lea     rcx, [rsp+88h+var_40]
0x140005387  test    r8, r8
0x14000538a  jnz     loc_140005495
0x140005390  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140005395  nop
0x140005396  mov     rcx, [rsp+88h+string]; string
0x14000539b  call    cs:__imp_WindowsDeleteString
0x1400053a2  nop     dword ptr [rax+rax+00h]
0x1400053a7  nop
0x1400053a8  mov     rcx, [rbx]
0x1400053ab  xor     edx, edx; length
0x1400053ad  mov     rcx, [rcx]; string
0x1400053b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1400053b7  nop     dword ptr [rax+rax+00h]
0x1400053bc  mov     rdx, rax
0x1400053bf  lea     rcx, [rsp+88h+string]
0x1400053c4  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x1400053c9  nop
0x1400053ca  mov     [rsp+88h+length], edi
0x1400053ce  lea     rdx, [rsp+88h+length]; length
0x1400053d3  mov     rcx, [rax]; string
0x1400053d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1400053dd  nop     dword ptr [rax+rax+00h]
0x1400053e2  mov     r8d, [rsp+88h+length]
0x1400053e7  xorps   xmm0, xmm0
0x1400053ea  movups  [rsp+88h+var_60], xmm0
0x1400053ef  xorps   xmm1, xmm1
0x1400053f2  movdqu  [rsp+88h+var_50], xmm1
0x1400053f8  lea     rcx, [rsp+88h+var_60]
0x1400053fd  test    r8, r8
0x140005400  jnz     loc_1400054A2
0x140005406  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14000540b  nop
0x14000540c  mov     rcx, [rsp+88h+string]; string
0x140005411  call    cs:__imp_WindowsDeleteString
0x140005418  nop     dword ptr [rax+rax+00h]
0x14000541d  lea     rdx, [rsp+88h+var_40]
0x140005422  cmp     qword ptr [rsp+88h+var_30+8], 7
0x140005428  cmova   rdx, qword ptr [rsp+88h+var_40]
0x14000542e  lea     rcx, [rsp+88h+var_60]
0x140005433  cmp     qword ptr [rsp+88h+var_50+8], 7
0x140005439  cmova   rcx, qword ptr [rsp+88h+var_60]
0x14000543f  call    cs:__imp_ReportLaunch
0x140005446  nop     dword ptr [rax+rax+00h]
0x14000544b  mov     rdx, qword ptr [rsp+88h+var_50+8]
0x140005450  cmp     rdx, 7
0x140005454  ja      short loc_1400054AF
0x140005456  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14000545e  movdqu  [rsp+88h+var_50], xmm0
0x140005464  mov     word ptr [rsp+88h+var_60], di
0x140005469  mov     rdx, qword ptr [rsp+88h+var_30+8]
0x14000546e  cmp     rdx, 7
0x140005472  ja      short loc_1400054C3
0x140005474  xor     eax, eax
0x140005476  mov     rcx, [rsp+88h+var_18]
0x14000547b  xor     rcx, rsp; StackCookie
0x14000547e  call    __security_check_cookie
0x140005483  mov     rbx, [rsp+88h+arg_0]
0x14000548b  add     rsp, 80h
0x140005492  pop     rdi
0x140005493  retn
0x140005495  mov     rdx, rax
0x140005498  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000549d  jmp     loc_140005396
0x1400054a2  mov     rdx, rax
0x1400054a5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400054aa  jmp     loc_14000540C
0x1400054af  lea     rdx, ds:2[rdx*2]
0x1400054b7  mov     rcx, qword ptr [rsp+88h+var_60]
0x1400054bc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400054c1  jmp     short loc_140005456
0x1400054c3  lea     rdx, ds:2[rdx*2]
0x1400054cb  mov     rcx, qword ptr [rsp+88h+var_40]
0x1400054d0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400054d5  jmp     short loc_140005474
0x1400054d7  mov     eax, [rsp+88h+length]
0x1400054db  jmp     short loc_140005476
```
