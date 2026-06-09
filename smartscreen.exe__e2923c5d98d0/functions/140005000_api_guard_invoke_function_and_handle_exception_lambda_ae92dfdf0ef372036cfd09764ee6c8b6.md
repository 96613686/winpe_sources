# api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6__&_

- ea: `0x140005000`
- end: `0x1400051a2`
- name: `api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6__&_`
- size: `418`
- prototype: `__int64 __fastcall(__int64, HSTRING **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004c00`

## callees

- `0x140005000`
- `0x1400051b0`
- `0x14001609c`
- `0x1400160f0`
- `0x140018b58`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000502a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000504a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000508e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400050ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000502a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000504a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000508e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400050ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000507f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400050e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000507f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400050e3`
- `SmartScreen!ReportLaunch` at `0x14000510b`
- `SmartScreen!ReportLaunch` at `0x14000510b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_ae92dfdf0ef372036cfd09764ee6c8b6____(
        __int64 a1,
        HSTRING **a2)
{
  HSTRING *v3; // rax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v5; // rdx
  HSTRING *v6; // rax
  PCWSTR v7; // rax
  __int128 *v8; // rdx
  __int128 *v9; // rcx
  wil *v10; // rcx
  __int64 result; // rax
  HSTRING string; // [rsp+20h] [rbp-68h] BYREF
  __int128 v13; // [rsp+28h] [rbp-60h] BYREF
  __m128i si128; // [rsp+38h] [rbp-50h]
  __int128 v15; // [rsp+48h] [rbp-40h] BYREF
  __int128 v16; // [rsp+58h] [rbp-30h]
  UINT32 length; // [rsp+68h] [rbp-20h] BYREF

  WindowsGetStringRawBuffer(*a2[1], 0);
  try
  {
    v3 = (HSTRING *)((__int64 (*)(void))windows::rt::create_hstring)();
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*v3, &length);
    v15 = 0;
    v16 = 0;
    if ( length )
      std::wstring::_Construct<1,unsigned short const *>(&v15, StringRawBuffer, length);
    else
      std::wstring::_Construct_empty(&v15);
    WindowsDeleteString(string);
    v5 = WindowsGetStringRawBuffer(**a2, 0);
    v6 = (HSTRING *)windows::rt::create_hstring(&string, v5);
    length = 0;
    v7 = WindowsGetStringRawBuffer(*v6, &length);
    v13 = 0;
    si128 = 0;
    if ( length )
      std::wstring::_Construct<1,unsigned short const *>(&v13, v7, length);
    else
      std::wstring::_Construct_empty(&v13);
    WindowsDeleteString(string);
    v8 = &v15;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      v8 = (__int128 *)v15;
    v9 = &v13;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (__int128 *)v13;
    ReportLaunch(v9, v8);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v13, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v13) = 0;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      std::_Deallocate<16>(v15, 2LL * *((_QWORD *)&v16 + 1) + 2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v10);
  }
  return result;
}

```

## disassembly

```asm
0x140005000  mov     [rsp+arg_0], rbx
0x140005005  push    rdi
0x140005006  sub     rsp, 80h
0x14000500d  mov     rax, cs:__security_cookie
0x140005014  xor     rax, rsp
0x140005017  mov     [rsp+88h+var_18], rax
0x14000501c  mov     rbx, rdx
0x14000501f  xor     edi, edi
0x140005021  mov     rcx, [rdx+8]
0x140005025  xor     edx, edx; length
0x140005027  mov     rcx, [rcx]; string
0x14000502a  call    cs:__imp_WindowsGetStringRawBuffer
0x140005030  mov     rdx, rax
0x140005033  lea     rcx, [rsp+88h+string]
0x140005038  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x14000503d  nop
0x14000503e  mov     [rsp+88h+length], edi
0x140005042  lea     rdx, [rsp+88h+length]; length
0x140005047  mov     rcx, [rax]; string
0x14000504a  call    cs:__imp_WindowsGetStringRawBuffer
0x140005050  mov     r8d, [rsp+88h+length]
0x140005055  xorps   xmm0, xmm0
0x140005058  movups  [rsp+88h+var_40], xmm0
0x14000505d  xorps   xmm1, xmm1
0x140005060  movdqu  [rsp+88h+var_30], xmm1
0x140005066  lea     rcx, [rsp+88h+var_40]
0x14000506b  test    r8, r8
0x14000506e  jnz     loc_14000515A
0x140005074  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140005079  nop
0x14000507a  mov     rcx, [rsp+88h+string]; string
0x14000507f  call    cs:__imp_WindowsDeleteString
0x140005085  nop
0x140005086  mov     rcx, [rbx]
0x140005089  xor     edx, edx; length
0x14000508b  mov     rcx, [rcx]; string
0x14000508e  call    cs:__imp_WindowsGetStringRawBuffer
0x140005094  mov     rdx, rax
0x140005097  lea     rcx, [rsp+88h+string]
0x14000509c  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x1400050a1  nop
0x1400050a2  mov     [rsp+88h+length], edi
0x1400050a6  lea     rdx, [rsp+88h+length]; length
0x1400050ab  mov     rcx, [rax]; string
0x1400050ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1400050b4  mov     r8d, [rsp+88h+length]
0x1400050b9  xorps   xmm0, xmm0
0x1400050bc  movups  [rsp+88h+var_60], xmm0
0x1400050c1  xorps   xmm1, xmm1
0x1400050c4  movdqu  [rsp+88h+var_50], xmm1
0x1400050ca  lea     rcx, [rsp+88h+var_60]
0x1400050cf  test    r8, r8
0x1400050d2  jnz     loc_140005167
0x1400050d8  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400050dd  nop
0x1400050de  mov     rcx, [rsp+88h+string]; string
0x1400050e3  call    cs:__imp_WindowsDeleteString
0x1400050e9  lea     rdx, [rsp+88h+var_40]
0x1400050ee  cmp     qword ptr [rsp+88h+var_30+8], 7
0x1400050f4  cmova   rdx, qword ptr [rsp+88h+var_40]
0x1400050fa  lea     rcx, [rsp+88h+var_60]
0x1400050ff  cmp     qword ptr [rsp+88h+var_50+8], 7
0x140005105  cmova   rcx, qword ptr [rsp+88h+var_60]
0x14000510b  call    cs:__imp_ReportLaunch
0x140005111  mov     rdx, qword ptr [rsp+88h+var_50+8]
0x140005116  cmp     rdx, 7
0x14000511a  ja      short loc_140005174
0x14000511c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140005124  movdqu  [rsp+88h+var_50], xmm0
0x14000512a  mov     word ptr [rsp+88h+var_60], di
0x14000512f  mov     rdx, qword ptr [rsp+88h+var_30+8]
0x140005134  cmp     rdx, 7
0x140005138  ja      short loc_140005188
0x14000513a  xor     eax, eax
0x14000513c  mov     rcx, [rsp+88h+var_18]
0x140005141  xor     rcx, rsp; StackCookie
0x140005144  call    __security_check_cookie
0x140005149  mov     rbx, [rsp+88h+arg_0]
0x140005151  add     rsp, 80h
0x140005158  pop     rdi
0x140005159  retn
0x14000515a  mov     rdx, rax
0x14000515d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140005162  jmp     loc_14000507A
0x140005167  mov     rdx, rax
0x14000516a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000516f  jmp     loc_1400050DE
0x140005174  lea     rdx, ds:2[rdx*2]
0x14000517c  mov     rcx, qword ptr [rsp+88h+var_60]
0x140005181  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140005186  jmp     short loc_14000511C
0x140005188  lea     rdx, ds:2[rdx*2]
0x140005190  mov     rcx, qword ptr [rsp+88h+var_40]
0x140005195  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000519a  jmp     short loc_14000513A
0x14000519c  mov     eax, [rsp+88h+length]
0x1400051a0  jmp     short loc_14000513C
```
