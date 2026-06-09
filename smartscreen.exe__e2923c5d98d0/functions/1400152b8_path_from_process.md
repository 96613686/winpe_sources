# path_from_process

- ea: `0x1400152b8`
- end: `0x1400153f9`
- name: `path_from_process`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140023aac`

## callees

- `0x140002968`
- `0x1400152b8`
- `0x140015400`
- `0x1400160b4`
- `0x140025aa0`
- `0x14002f250`
- `0x140062c80`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001531b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001531b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015348`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14001539f`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140015348`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14001539f`

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
0x1400152b8  mov     [rsp-8+arg_10], rbx
0x1400152bd  push    rbp
0x1400152be  push    rsi
0x1400152bf  push    rdi
0x1400152c0  lea     rbp, [rsp-170h]
0x1400152c8  sub     rsp, 270h
0x1400152cf  mov     rax, cs:__security_cookie
0x1400152d6  xor     rax, rsp
0x1400152d9  mov     [rbp+180h+var_20], rax
0x1400152e0  mov     rbx, rdx
0x1400152e3  mov     rdi, rcx
0x1400152e6  mov     qword ptr [rsp+280h+dwSize], rcx
0x1400152eb  xor     edx, edx; Val
0x1400152ed  mov     r8d, 20Ah; Size
0x1400152f3  lea     rcx, [rsp+280h+ExeName]; void *
0x1400152f8  call    memset
0x1400152fd  mov     [rsp+280h+dwSize], 105h
0x140015305  mov     rsi, [rbp+188h]
0x14001530c  lea     r9, [rsp+280h+dwSize]; lpdwSize
0x140015311  lea     r8, [rsp+280h+ExeName]; lpExeName
0x140015316  xor     edx, edx; dwFlags
0x140015318  mov     rcx, rbx; hProcess
0x14001531b  call    cs:__imp_QueryFullProcessImageNameW
0x140015321  test    eax, eax
0x140015323  jnz     short loc_140015338
0x140015325  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001532c  lea     edx, [rax+5Ah]; void *
0x14001532f  mov     rcx, rsi; this
0x140015332  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015338  mov     r8d, 105h; cchBuffer
0x14001533e  lea     rdx, [rsp+280h+ExeName]; lpszLongPath
0x140015343  lea     rcx, [rsp+280h+ExeName]; lpszShortPath
0x140015348  call    cs:__imp_GetLongPathNameW
0x14001534e  cmp     eax, 105h
0x140015353  ja      short loc_140015364
0x140015355  lea     rdx, [rsp+280h+ExeName]
0x14001535a  mov     rcx, rdi
0x14001535d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140015362  jmp     short loc_1400153D4
0x140015364  xorps   xmm0, xmm0
0x140015367  movdqu  xmmword ptr [rsp+280h+lpszLongPath], xmm0
0x14001536d  mov     [rsp+280h+var_250], 0
0x140015376  mov     edx, eax
0x140015378  lea     rcx, [rsp+280h+lpszLongPath]
0x14001537d  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x140015382  nop
0x140015383  mov     rdx, [rsp+280h+lpszLongPath]; lpszLongPath
0x140015388  mov     rbx, [rbp+188h]
0x14001538f  mov     r8, [rsp+280h+lpszLongPath+8]
0x140015394  sub     r8, rdx
0x140015397  sar     r8, 1; cchBuffer
0x14001539a  lea     rcx, [rsp+280h+ExeName]; lpszShortPath
0x14001539f  call    cs:__imp_GetLongPathNameW
0x1400153a5  test    eax, eax
0x1400153a7  jnz     short loc_1400153BC
0x1400153a9  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400153b0  lea     edx, [rax+64h]; void *
0x1400153b3  mov     rcx, rbx; this
0x1400153b6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400153bc  mov     rdx, [rsp+280h+lpszLongPath]
0x1400153c1  mov     rcx, rdi
0x1400153c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400153c9  nop
0x1400153ca  lea     rcx, [rsp+280h+lpszLongPath]
0x1400153cf  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1400153d4  mov     rax, rdi
0x1400153d7  mov     rcx, [rbp+180h+var_20]
0x1400153de  xor     rcx, rsp; StackCookie
0x1400153e1  call    __security_check_cookie
0x1400153e6  mov     rbx, [rsp+280h+arg_10]
0x1400153ee  add     rsp, 270h
0x1400153f5  pop     rdi
0x1400153f6  pop     rsi
0x1400153f7  pop     rbp
0x1400153f8  retn
```
