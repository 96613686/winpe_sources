# path::from_string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140002734`
- end: `0x140002873`
- name: `?from_string@path@@SA?AV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002658`
- `0x140015dbc`

## callees

- `0x140002734`
- `0x14000287c`
- `0x140005260`
- `0x14000f834`
- `0x14001609c`
- `0x140025aa0`
- `0x140030094`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400027d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400027d0`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1400027a4`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1400027a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000286a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000286a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x14000283c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x14000283c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall path::from_string(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  const WCHAR *v7; // rcx
  HRESULT v8; // eax
  WCHAR *FileNameW; // rax
  PWSTR v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+20h] [rbp-50h]
  _BYTE v14[32]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h]
  PWSTR ppszPathOut; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v15 = a2;
  v6 = std::wstring::wstring(v14, a2, a3, a4);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct_empty(a1);
  ppszPathOut = 0;
  if ( *(_QWORD *)(v6 + 24) <= 7u )
    v7 = (const WCHAR *)v6;
  else
    v7 = *(const WCHAR **)v6;
  v8 = PathAllocCanonicalize(v7, 1u, &ppszPathOut);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)(unsigned int)v8,
      v13);
  FileNameW = PathFindFileNameW(ppszPathOut);
  v10 = ppszPathOut;
  if ( FileNameW != ppszPathOut )
  {
    if ( PathCleanupSpec(0, FileNameW) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
        (const char *)0x80070057LL,
        v13);
    v10 = ppszPathOut;
  }
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  std::wstring::_Assign<unsigned short>(a1);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  std::wstring::_Tidy_deallocate(v6);
  std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x140002734  mov     [rsp-28h+arg_10], rbx
0x140002739  push    rbp
0x14000273a  push    rsi
0x14000273b  push    rdi
0x14000273c  push    r14
0x14000273e  push    r15
0x140002740  mov     rbp, rsp
0x140002743  sub     rsp, 70h
0x140002747  mov     rax, cs:__security_cookie
0x14000274e  xor     rax, rsp
0x140002751  mov     [rbp+var_8], rax
0x140002755  mov     r14, rdx
0x140002758  mov     rdi, rcx
0x14000275b  mov     [rbp+var_48], rcx
0x14000275f  mov     [rbp+var_18], rdx
0x140002763  xor     r15d, r15d
0x140002766  lea     rcx, [rbp+var_38]
0x14000276a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000276f  mov     rbx, rax
0x140002772  mov     [rbp+var_40], rax
0x140002776  xorps   xmm0, xmm0
0x140002779  movups  xmmword ptr [rdi], xmm0
0x14000277c  mov     [rdi+10h], r15
0x140002780  mov     [rdi+18h], r15
0x140002784  mov     rcx, rdi
0x140002787  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14000278c  nop
0x14000278d  mov     [rbp+ppszPathOut], r15
0x140002791  cmp     qword ptr [rbx+18h], 7
0x140002796  jbe     short loc_1400027C7
0x140002798  mov     rcx, [rbx]; pszPathIn
0x14000279b  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x14000279f  mov     edx, 1; dwFlags
0x1400027a4  call    cs:__imp_PathAllocCanonicalize
0x1400027aa  mov     rcx, [rbp+28h]; this
0x1400027ae  test    eax, eax
0x1400027b0  jns     short loc_1400027CC
0x1400027b2  mov     r9d, eax; char *
0x1400027b5  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400027bc  mov     edx, 19Fh; void *
0x1400027c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400027c7  mov     rcx, rbx
0x1400027ca  jmp     short loc_14000279B
0x1400027cc  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1400027d0  call    cs:__imp_PathFindFileNameW
0x1400027d6  mov     rdx, [rbp+ppszPathOut]
0x1400027da  cmp     rax, rdx
0x1400027dd  jnz     short loc_140002833
0x1400027df  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400027e3  inc     r8
0x1400027e6  cmp     [rdx+r8*2], r15w
0x1400027eb  jnz     short loc_1400027E3
0x1400027ed  mov     rcx, rdi
0x1400027f0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400027f5  nop
0x1400027f6  mov     rcx, [rbp+ppszPathOut]; hMem
0x1400027fa  test    rcx, rcx
0x1400027fd  jnz     short loc_14000286A
0x1400027ff  mov     rcx, rbx
0x140002802  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140002807  nop
0x140002808  mov     rcx, r14
0x14000280b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140002810  mov     rax, rdi
0x140002813  mov     rcx, [rbp+var_8]
0x140002817  xor     rcx, rsp; StackCookie
0x14000281a  call    __security_check_cookie
0x14000281f  mov     rbx, [rsp+70h+arg_10]
0x140002827  add     rsp, 70h
0x14000282b  pop     r15
0x14000282d  pop     r14
0x14000282f  pop     rdi
0x140002830  pop     rsi
0x140002831  pop     rbp
0x140002832  retn
0x140002833  mov     rsi, [rbp+28h]
0x140002837  mov     rdx, rax; pszSpec
0x14000283a  xor     ecx, ecx; pszDir
0x14000283c  call    cs:__imp_PathCleanupSpec
0x140002842  shr     eax, 1Fh
0x140002845  test    al, al
0x140002847  jnz     short loc_14000284F
0x140002849  mov     rdx, [rbp+ppszPathOut]
0x14000284d  jmp     short loc_1400027DF
0x14000284f  mov     r9d, 80070057h; char *
0x140002855  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14000285c  mov     edx, 1A4h; void *
0x140002861  mov     rcx, rsi; this
0x140002864  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000286a  call    cs:__imp_LocalFree
0x140002870  jmp     short loc_1400027FF
```
