# XamlResourceUtils::LoadWString(HINSTANCE__ *,int)

- ea: `0x140025c84`
- end: `0x140025d25`
- name: `?LoadWString@XamlResourceUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@H@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140022168`
- `0x140025c48`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14001efd0`
- `0x140022dcc`
- `0x140025c84`

## import_xrefs

- `USER32!LoadStringW` at `0x140025cd1`
- `USER32!LoadStringW` at `0x140025cd1`

## string_xrefs

- `0x140025ce9`: `enduser\ezap\xamlcommon\xamlresourceutils.cpp`

## pseudocode

```c
__int64 __fastcall XamlResourceUtils::LoadWString(__int64 a1, HINSTANCE a2, UINT a3)
{
  const char *v6; // r9
  WCHAR Buffer[256]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !LoadStringW(a2, a3, Buffer, 256) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlresourceutils.cpp",
      v6);
  std::wstring::wstring(a1, Buffer);
  return a1;
}

```

## disassembly

```asm
0x140025c84  push    rbx
0x140025c86  push    rsi
0x140025c87  push    rdi
0x140025c88  sub     rsp, 240h
0x140025c8f  mov     rax, cs:__security_cookie
0x140025c96  xor     rax, rsp
0x140025c99  mov     [rsp+258h+var_28], rax
0x140025ca1  mov     edi, r8d
0x140025ca4  mov     [rsp+258h+var_230], rcx
0x140025ca9  mov     rbx, rdx
0x140025cac  mov     rsi, rcx
0x140025caf  xor     edx, edx; Val
0x140025cb1  lea     rcx, [rsp+258h+Buffer]; void *
0x140025cb6  mov     r8d, 200h; Size
0x140025cbc  call    memset_0
0x140025cc1  mov     r9d, 100h; cchBufferMax
0x140025cc7  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x140025ccc  mov     edx, edi; uID
0x140025cce  mov     rcx, rbx; hInstance
0x140025cd1  call    cs:__imp_LoadStringW
0x140025cd8  nop     dword ptr [rax+rax+00h]
0x140025cdd  test    eax, eax
0x140025cdf  jnz     short loc_140025CF9
0x140025ce1  mov     rcx, [rsp+258h]; this
0x140025ce9  lea     r8, aEnduserEzapXam_1; "enduser\\ezap\\xamlcommon\\xamlresource"...
0x140025cf0  lea     edx, [rax+4Eh]; void *
0x140025cf3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140025cf9  lea     rdx, [rsp+258h+Buffer]
0x140025cfe  mov     rcx, rsi
0x140025d01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140025d06  mov     rax, rsi
0x140025d09  mov     rcx, [rsp+258h+var_28]
0x140025d11  xor     rcx, rsp; StackCookie
0x140025d14  call    __security_check_cookie
0x140025d19  add     rsp, 240h
0x140025d20  pop     rdi
0x140025d21  pop     rsi
0x140025d22  pop     rbx
0x140025d23  retn
```
