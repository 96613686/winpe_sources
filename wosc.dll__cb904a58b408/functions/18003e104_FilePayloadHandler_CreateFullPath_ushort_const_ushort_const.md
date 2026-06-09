# FilePayloadHandler::CreateFullPath(ushort const *,ushort const *)

- ea: `0x18003e104`
- end: `0x18003e1e6`
- name: `?CreateFullPath@FilePayloadHandler@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003cd38`
- `0x18003e6c0`
- `0x18003e9f0`
- `0x18003eed0`

## callees

- `0x180003110`
- `0x180003c88`
- `0x1800101fc`
- `0x180014928`
- `0x18002b254`
- `0x18003e104`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003e132`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003e132`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003e194`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003e194`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FilePayloadHandler::CreateFullPath(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  LPWSTR FileNameW; // rax
  HRESULT v7; // eax
  int v9; // [rsp+20h] [rbp-268h]
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  FileNameW = PathFindFileNameW(a3);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0xDA,
    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
    (const char *)0x80070057LL,
    FileNameW == a3,
    (bool)"The specified OneSettings Payload file name contains more than just the file name (%ws)",
    (const char *)a3);
  memset_0(pszPathOut, 0, 0x208u);
  v7 = PathCchCombine(pszPathOut, 0x104u, a2, a3);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      (const char *)(unsigned int)v7,
      v9);
  std::wstring::wstring(a1, pszPathOut);
  return a1;
}

```

## disassembly

```asm
0x18003e104  push    rbx
0x18003e106  push    rsi
0x18003e107  push    rdi
0x18003e108  sub     rsp, 270h
0x18003e10f  mov     rax, cs:__security_cookie
0x18003e116  xor     rax, rsp
0x18003e119  mov     [rsp+288h+var_28], rax
0x18003e121  mov     rsi, rcx
0x18003e124  mov     [rsp+288h+var_240], rcx
0x18003e129  mov     rcx, r8; pszPath
0x18003e12c  mov     rdi, r8
0x18003e12f  mov     rbx, rdx
0x18003e132  call    cs:__imp_PathFindFileNameW
0x18003e138  mov     rcx, [rsp+288h]; this
0x18003e140  lea     rdx, aTheSpecifiedOn_1; "The specified OneSettings Payload file "...
0x18003e147  cmp     rax, rdi
0x18003e14a  mov     [rsp+288h+var_258], rdi; char *
0x18003e14f  mov     qword ptr [rsp+288h+var_260], rdx; bool
0x18003e154  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003e15b  setz    al
0x18003e15e  mov     r9d, 80070057h; char *
0x18003e164  mov     edx, 0DAh; void *
0x18003e169  mov     [rsp+288h+var_268], al; int
0x18003e16d  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003e172  xor     edx, edx; Val
0x18003e174  lea     rcx, [rsp+288h+pszPathOut]; void *
0x18003e179  mov     r8d, 208h; Size
0x18003e17f  call    memset_0
0x18003e184  mov     r9, rdi; pszMore
0x18003e187  lea     rcx, [rsp+288h+pszPathOut]; pszPathOut
0x18003e18c  mov     r8, rbx; pszPathIn
0x18003e18f  mov     edx, 104h; cchPathOut
0x18003e194  call    cs:__imp_PathCchCombine
0x18003e19a  test    eax, eax
0x18003e19c  js      short loc_18003E1C9
0x18003e19e  lea     rdx, [rsp+288h+pszPathOut]
0x18003e1a3  mov     rcx, rsi
0x18003e1a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e1ab  mov     rax, rsi
0x18003e1ae  mov     rcx, [rsp+288h+var_28]
0x18003e1b6  xor     rcx, rsp; StackCookie
0x18003e1b9  call    __security_check_cookie
0x18003e1be  add     rsp, 270h
0x18003e1c5  pop     rdi
0x18003e1c6  pop     rsi
0x18003e1c7  pop     rbx
0x18003e1c8  retn
0x18003e1c9  mov     rcx, [rsp+288h]; this
0x18003e1d1  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003e1d8  mov     r9d, eax; char *
0x18003e1db  mov     edx, 0DDh; void *
0x18003e1e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
