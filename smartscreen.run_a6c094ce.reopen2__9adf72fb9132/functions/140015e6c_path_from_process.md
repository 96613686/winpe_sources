# path_from_process

- ea: `0x140015e6c`
- end: `0x140015fc0`
- name: `path_from_process`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140024c44`

## callees

- `0x140002a80`
- `0x140015e6c`
- `0x140015fc8`
- `0x140016ca8`
- `0x140026c20`
- `0x140030510`
- `0x140064940`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140015ecf`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140015ecf`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015f02`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015f5f`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015f02`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015f5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall path_from_process(__int64 a1, void *a2)
{
  const char *v4; // r9
  DWORD LongPathNameW; // eax
  const char *v6; // r9
  LPWSTR lpszLongPath[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+30h] [rbp-D0h]
  DWORD dwSize[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  dwSize[1] = HIDWORD(a1);
  memset(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  if ( !QueryFullProcessImageNameW(a2, 0, ExeName, dwSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      v4);
  LongPathNameW = GetLongPathNameW(ExeName, ExeName, 0x105u);
  if ( LongPathNameW > 0x105 )
  {
    *(_OWORD *)lpszLongPath = 0;
    v9 = 0;
    std::vector<unsigned short>::_Construct_n<>(lpszLongPath, LongPathNameW);
    if ( !GetLongPathNameW(ExeName, lpszLongPath[0], lpszLongPath[1] - lpszLongPath[0]) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
        v6);
    std::wstring::wstring(a1, lpszLongPath[0]);
    std::vector<unsigned short>::_Tidy(lpszLongPath);
  }
  else
  {
    std::wstring::wstring(a1, ExeName);
  }
  return a1;
}

```

## disassembly

```asm
0x140015e6c  mov     [rsp-8+arg_10], rbx
0x140015e71  push    rbp
0x140015e72  push    rsi
0x140015e73  push    rdi
0x140015e74  lea     rbp, [rsp-170h]
0x140015e7c  sub     rsp, 270h
0x140015e83  mov     rax, cs:__security_cookie
0x140015e8a  xor     rax, rsp
0x140015e8d  mov     [rbp+180h+var_20], rax
0x140015e94  mov     rbx, rdx
0x140015e97  mov     rdi, rcx
0x140015e9a  mov     qword ptr [rsp+280h+dwSize], rcx
0x140015e9f  xor     edx, edx; Val
0x140015ea1  mov     r8d, 20Ah; Size
0x140015ea7  lea     rcx, [rsp+280h+ExeName]; void *
0x140015eac  call    memset
0x140015eb1  mov     [rsp+280h+dwSize], 105h
0x140015eb9  mov     rsi, [rbp+188h]
0x140015ec0  lea     r9, [rsp+280h+dwSize]; lpdwSize
0x140015ec5  lea     r8, [rsp+280h+ExeName]; lpExeName
0x140015eca  xor     edx, edx; dwFlags
0x140015ecc  mov     rcx, rbx; hProcess
0x140015ecf  call    cs:__imp_QueryFullProcessImageNameW
0x140015ed6  nop     dword ptr [rax+rax+00h]
0x140015edb  test    eax, eax
0x140015edd  jnz     short loc_140015EF2
0x140015edf  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140015ee6  lea     edx, [rax+5Ah]; void *
0x140015ee9  mov     rcx, rsi; this
0x140015eec  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015ef2  mov     r8d, 105h; cchBuffer
0x140015ef8  lea     rdx, [rsp+280h+ExeName]; lpszLongPath
0x140015efd  lea     rcx, [rsp+280h+ExeName]; lpszShortPath
0x140015f02  call    cs:__imp_GetLongPathNameW
0x140015f09  nop     dword ptr [rax+rax+00h]
0x140015f0e  cmp     eax, 105h
0x140015f13  ja      short loc_140015F24
0x140015f15  lea     rdx, [rsp+280h+ExeName]
0x140015f1a  mov     rcx, rdi
0x140015f1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140015f22  jmp     short loc_140015F9A
0x140015f24  xorps   xmm0, xmm0
0x140015f27  movdqu  xmmword ptr [rsp+280h+lpszLongPath], xmm0
0x140015f2d  mov     [rsp+280h+var_250], 0
0x140015f36  mov     edx, eax
0x140015f38  lea     rcx, [rsp+280h+lpszLongPath]
0x140015f3d  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x140015f42  nop
0x140015f43  mov     rdx, [rsp+280h+lpszLongPath]; lpszLongPath
0x140015f48  mov     rbx, [rbp+188h]
0x140015f4f  mov     r8, [rsp+280h+lpszLongPath+8]
0x140015f54  sub     r8, rdx
0x140015f57  sar     r8, 1; cchBuffer
0x140015f5a  lea     rcx, [rsp+280h+ExeName]; lpszShortPath
0x140015f5f  call    cs:__imp_GetLongPathNameW
0x140015f66  nop     dword ptr [rax+rax+00h]
0x140015f6b  test    eax, eax
0x140015f6d  jnz     short loc_140015F82
0x140015f6f  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140015f76  lea     edx, [rax+64h]; void *
0x140015f79  mov     rcx, rbx; this
0x140015f7c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015f82  mov     rdx, [rsp+280h+lpszLongPath]
0x140015f87  mov     rcx, rdi
0x140015f8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140015f8f  nop
0x140015f90  lea     rcx, [rsp+280h+lpszLongPath]
0x140015f95  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x140015f9a  mov     rax, rdi
0x140015f9d  mov     rcx, [rbp+180h+var_20]
0x140015fa4  xor     rcx, rsp; StackCookie
0x140015fa7  call    __security_check_cookie
0x140015fac  mov     rbx, [rsp+280h+arg_10]
0x140015fb4  add     rsp, 270h
0x140015fbb  pop     rdi
0x140015fbc  pop     rsi
0x140015fbd  pop     rbp
0x140015fbe  retn
```
