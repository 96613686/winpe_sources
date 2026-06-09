# path::from_string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140002830`
- end: `0x140002988`
- name: `?from_string@path@@SA?AV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000274c`
- `0x14001699c`

## callees

- `0x140002830`
- `0x140002990`
- `0x1400055ac`
- `0x140010054`
- `0x140016c8c`
- `0x140026c20`
- `0x140031414`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400028d2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400028d2`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1400028a0`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1400028a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002979`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140002945`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140002945`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall path::from_string(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  const WCHAR *v5; // rcx
  HRESULT v6; // eax
  WCHAR *FileNameW; // rax
  PWSTR v8; // rdx
  __int64 v9; // r8
  int v11; // [rsp+20h] [rbp-50h]
  _BYTE v12[32]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]
  PWSTR ppszPathOut; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v13 = a2;
  v4 = std::wstring::wstring(v12);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct_empty(a1);
  ppszPathOut = 0;
  if ( *(_QWORD *)(v4 + 24) <= 7u )
    v5 = (const WCHAR *)v4;
  else
    v5 = *(const WCHAR **)v4;
  v6 = PathAllocCanonicalize(v5, 1u, &ppszPathOut);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)(unsigned int)v6,
      v11);
  FileNameW = PathFindFileNameW(ppszPathOut);
  v8 = ppszPathOut;
  if ( FileNameW != ppszPathOut )
  {
    if ( PathCleanupSpec(0, FileNameW) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
        (const char *)0x80070057LL,
        v11);
    v8 = ppszPathOut;
  }
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  std::wstring::_Assign<unsigned short>(a1);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  std::wstring::_Tidy_deallocate(v4);
  std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x140002830  mov     [rsp-28h+arg_10], rbx
0x140002835  push    rbp
0x140002836  push    rsi
0x140002837  push    rdi
0x140002838  push    r14
0x14000283a  push    r15
0x14000283c  mov     rbp, rsp
0x14000283f  sub     rsp, 70h
0x140002843  mov     rax, cs:__security_cookie
0x14000284a  xor     rax, rsp
0x14000284d  mov     [rbp+var_8], rax
0x140002851  mov     r14, rdx
0x140002854  mov     rdi, rcx
0x140002857  mov     [rbp+var_48], rcx
0x14000285b  mov     [rbp+var_18], rdx
0x14000285f  xor     r15d, r15d
0x140002862  lea     rcx, [rbp+var_38]
0x140002866  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000286b  mov     rbx, rax
0x14000286e  mov     [rbp+var_40], rax
0x140002872  xorps   xmm0, xmm0
0x140002875  movups  xmmword ptr [rdi], xmm0
0x140002878  mov     [rdi+10h], r15
0x14000287c  mov     [rdi+18h], r15
0x140002880  mov     rcx, rdi
0x140002883  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140002888  nop
0x140002889  mov     [rbp+ppszPathOut], r15
0x14000288d  cmp     qword ptr [rbx+18h], 7
0x140002892  jbe     short loc_1400028C9
0x140002894  mov     rcx, [rbx]; pszPathIn
0x140002897  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x14000289b  mov     edx, 1; dwFlags
0x1400028a0  call    cs:__imp_PathAllocCanonicalize
0x1400028a7  nop     dword ptr [rax+rax+00h]
0x1400028ac  mov     rcx, [rbp+28h]; this
0x1400028b0  test    eax, eax
0x1400028b2  jns     short loc_1400028CE
0x1400028b4  mov     r9d, eax; char *
0x1400028b7  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400028be  mov     edx, 19Fh; void *
0x1400028c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400028c9  mov     rcx, rbx
0x1400028cc  jmp     short loc_140002897
0x1400028ce  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1400028d2  call    cs:__imp_PathFindFileNameW
0x1400028d9  nop     dword ptr [rax+rax+00h]
0x1400028de  mov     rdx, [rbp+ppszPathOut]
0x1400028e2  cmp     rax, rdx
0x1400028e5  jnz     short loc_14000293C
0x1400028e7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400028eb  inc     r8
0x1400028ee  cmp     [rdx+r8*2], r15w
0x1400028f3  jnz     short loc_1400028EB
0x1400028f5  mov     rcx, rdi
0x1400028f8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400028fd  nop
0x1400028fe  mov     rcx, [rbp+ppszPathOut]; hMem
0x140002902  test    rcx, rcx
0x140002905  jnz     short loc_140002979
0x140002907  mov     rcx, rbx
0x14000290a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000290f  nop
0x140002910  mov     rcx, r14
0x140002913  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140002918  mov     rax, rdi
0x14000291b  mov     rcx, [rbp+var_8]
0x14000291f  xor     rcx, rsp; StackCookie
0x140002922  call    __security_check_cookie
0x140002927  mov     rbx, [rsp+70h+arg_10]
0x14000292f  add     rsp, 70h
0x140002933  pop     r15
0x140002935  pop     r14
0x140002937  pop     rdi
0x140002938  pop     rsi
0x140002939  pop     rbp
0x14000293a  retn
0x14000293c  mov     rsi, [rbp+28h]
0x140002940  mov     rdx, rax; pszSpec
0x140002943  xor     ecx, ecx; pszDir
0x140002945  call    cs:__imp_PathCleanupSpec
0x14000294c  nop     dword ptr [rax+rax+00h]
0x140002951  shr     eax, 1Fh
0x140002954  test    al, al
0x140002956  jnz     short loc_14000295E
0x140002958  mov     rdx, [rbp+ppszPathOut]
0x14000295c  jmp     short loc_1400028E7
0x14000295e  mov     r9d, 80070057h; char *
0x140002964  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14000296b  mov     edx, 1A4h; void *
0x140002970  mov     rcx, rsi; this
0x140002973  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140002979  call    cs:__imp_LocalFree
0x140002980  nop     dword ptr [rax+rax+00h]
0x140002985  jmp     short loc_140002907
```
