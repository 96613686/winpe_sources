# windows::rt::to_wstring(HSTRING__ *)

- ea: `0x140004b54`
- end: `0x140004bf8`
- name: `?to_wstring@rt@windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140015590`
- `0x140015eb4`
- `0x140016830`
- `0x14001a1dc`
- `0x1400331a0`
- `0x14003b390`

## callees

- `0x140004b54`
- `0x1400051b0`
- `0x14001609c`
- `0x1400160f0`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140004b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004bd1`

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
0x140004b54  push    rbx
0x140004b56  sub     rsp, 40h
0x140004b5a  mov     rax, cs:__security_cookie
0x140004b61  xor     rax, rsp
0x140004b64  mov     [rsp+48h+var_18], rax
0x140004b69  mov     rax, rdx
0x140004b6c  mov     rbx, rcx
0x140004b6f  mov     [rsp+48h+string], rcx
0x140004b74  xor     edx, edx; length
0x140004b76  mov     rcx, rax; string
0x140004b79  call    cs:__imp_WindowsGetStringRawBuffer
0x140004b7f  mov     rdx, rax
0x140004b82  lea     rcx, [rsp+48h+string]
0x140004b87  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; windows::rt::create_hstring(ushort const *)
0x140004b8c  nop
0x140004b8d  mov     [rsp+48h+length], 0
0x140004b95  lea     rdx, [rsp+48h+length]; length
0x140004b9a  mov     rcx, [rax]; string
0x140004b9d  call    cs:__imp_WindowsGetStringRawBuffer
0x140004ba3  mov     r8d, [rsp+48h+length]
0x140004ba8  xorps   xmm0, xmm0
0x140004bab  movups  xmmword ptr [rbx], xmm0
0x140004bae  mov     qword ptr [rbx+10h], 0
0x140004bb6  mov     qword ptr [rbx+18h], 0
0x140004bbe  mov     rcx, rbx
0x140004bc1  test    r8, r8
0x140004bc4  jnz     short loc_140004BED
0x140004bc6  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140004bcb  nop
0x140004bcc  mov     rcx, [rsp+48h+string]; string
0x140004bd1  call    cs:__imp_WindowsDeleteString
0x140004bd7  mov     rax, rbx
0x140004bda  mov     rcx, [rsp+48h+var_18]
0x140004bdf  xor     rcx, rsp; StackCookie
0x140004be2  call    __security_check_cookie
0x140004be7  add     rsp, 40h
0x140004beb  pop     rbx
0x140004bec  retn
0x140004bed  mov     rdx, rax
0x140004bf0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140004bf5  jmp     short loc_140004BCC
```
