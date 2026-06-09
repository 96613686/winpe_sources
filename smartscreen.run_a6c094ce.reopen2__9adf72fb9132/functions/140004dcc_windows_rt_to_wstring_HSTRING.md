# windows::rt::to_wstring(HSTRING__ *)

- ea: `0x140004dcc`
- end: `0x140004e83`
- name: `?to_wstring@rt@windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z`
- size: `183`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14001615c`
- `0x140016aa0`
- `0x14001802c`
- `0x14001afcc`
- `0x140034650`
- `0x14003ca14`

## callees

- `0x140004dcc`
- `0x1400054f0`
- `0x140016c8c`
- `0x140016ce4`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004e55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING __fastcall windows::rt::to_wstring(HSTRING a1, HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  HSTRING *v4; // rax
  PCWSTR v5; // rax
  __int64 v6; // r8
  HSTRING string; // [rsp+20h] [rbp-28h] BYREF
  UINT32 length; // [rsp+2Ch] [rbp-1Ch] BYREF

  string = a1;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v4 = windows::rt::create_hstring(&string, StringRawBuffer);
  length = 0;
  v5 = WindowsGetStringRawBuffer(*v4, &length);
  v6 = length;
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  if ( v6 )
    std::wstring::_Construct<1,unsigned short const *>(a1, v5, v6);
  else
    std::wstring::_Construct_empty(a1);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x140004dcc  push    rbx
0x140004dce  sub     rsp, 40h
0x140004dd2  mov     rax, cs:__security_cookie
0x140004dd9  xor     rax, rsp
0x140004ddc  mov     [rsp+48h+var_18], rax
0x140004de1  mov     rax, rdx
0x140004de4  mov     rbx, rcx
0x140004de7  mov     [rsp+48h+string], rcx
0x140004dec  xor     edx, edx; length
0x140004dee  mov     rcx, rax; string
0x140004df1  call    cs:__imp_WindowsGetStringRawBuffer
0x140004df8  nop     dword ptr [rax+rax+00h]
0x140004dfd  mov     rdx, rax
0x140004e00  lea     rcx, [rsp+48h+string]
0x140004e05  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x140004e0a  nop
0x140004e0b  mov     [rsp+48h+length], 0
0x140004e13  lea     rdx, [rsp+48h+length]; length
0x140004e18  mov     rcx, [rax]; string
0x140004e1b  call    cs:__imp_WindowsGetStringRawBuffer
0x140004e22  nop     dword ptr [rax+rax+00h]
0x140004e27  mov     r8d, [rsp+48h+length]
0x140004e2c  xorps   xmm0, xmm0
0x140004e2f  movups  xmmword ptr [rbx], xmm0
0x140004e32  mov     qword ptr [rbx+10h], 0
0x140004e3a  mov     qword ptr [rbx+18h], 0
0x140004e42  mov     rcx, rbx
0x140004e45  test    r8, r8
0x140004e48  jnz     short loc_140004E78
0x140004e4a  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140004e4f  nop
0x140004e50  mov     rcx, [rsp+48h+string]; string
0x140004e55  call    cs:__imp_WindowsDeleteString
0x140004e5c  nop     dword ptr [rax+rax+00h]
0x140004e61  mov     rax, rbx
0x140004e64  mov     rcx, [rsp+48h+var_18]
0x140004e69  xor     rcx, rsp; StackCookie
0x140004e6c  call    __security_check_cookie
0x140004e71  add     rsp, 40h
0x140004e75  pop     rbx
0x140004e76  retn
0x140004e78  mov     rdx, rax
0x140004e7b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140004e80  jmp     short loc_140004E50
```
