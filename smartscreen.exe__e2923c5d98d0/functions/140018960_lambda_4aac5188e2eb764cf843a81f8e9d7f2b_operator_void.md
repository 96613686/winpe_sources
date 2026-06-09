# _lambda_4aac5188e2eb764cf843a81f8e9d7f2b_::operator()(void)

- ea: `0x140018960`
- end: `0x140018a50`
- name: `??R_lambda_4aac5188e2eb764cf843a81f8e9d7f2b_@@QEBA?AV?$optional@H@std@@XZ`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140018780`

## callees

- `0x140005260`
- `0x140018960`
- `0x140018a9c`
- `0x140018b58`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140018a0a`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140018a0a`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x1400189bd`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x1400189bd`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400189d9`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400189d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_4aac5188e2eb764cf843a81f8e9d7f2b_::operator()(const WCHAR **a1, __int64 a2)
{
  const WCHAR *v4; // rdx
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  WCHAR *v7; // rcx
  HRESULT v8; // eax
  const WCHAR *v9; // rcx
  int v11; // [rsp+20h] [rbp-30h]
  PWSTR pszPath[2]; // [rsp+28h] [rbp-28h] BYREF
  size_t cchPath[2]; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v4 = *a1;
  *(_OWORD *)pszPath = 0;
  *(_OWORD *)cchPath = 0;
  v5 = *((_QWORD *)v4 + 2);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const WCHAR **)v4;
  std::wstring::_Construct<2,unsigned short const *>(pszPath, v4, v5);
  v6 = *a1;
  if ( *((_QWORD *)*a1 + 3) > 7u )
    v6 = *(const WCHAR **)v6;
  if ( !PathCchIsRoot(v6) )
  {
    v7 = (WCHAR *)pszPath;
    if ( cchPath[1] > 7 )
      v7 = pszPath[0];
    v8 = PathCchStripToRoot(v7, cchPath[0]);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
        (const char *)(unsigned int)v8,
        v11);
  }
  v9 = (const WCHAR *)pszPath;
  if ( cchPath[1] > 7 )
    v9 = pszPath[0];
  *(_DWORD *)a2 = GetDriveTypeW(v9);
  *(_BYTE *)(a2 + 4) = 1;
  if ( cchPath[1] > 7 )
    std::_Deallocate<16>(pszPath[0], 2 * cchPath[1] + 2);
  return a2;
}

```

## disassembly

```asm
0x140018960  mov     [rsp-8+arg_10], rbx
0x140018965  mov     [rsp-8+arg_18], rdi
0x14001896a  push    rbp
0x14001896b  mov     rbp, rsp
0x14001896e  sub     rsp, 50h
0x140018972  mov     rax, cs:__security_cookie
0x140018979  xor     rax, rsp
0x14001897c  mov     [rbp+var_8], rax
0x140018980  mov     rbx, rdx
0x140018983  mov     rdi, rcx
0x140018986  mov     rdx, [rcx]
0x140018989  xorps   xmm0, xmm0
0x14001898c  movups  xmmword ptr [rbp+pszPath], xmm0
0x140018990  xorps   xmm1, xmm1
0x140018993  movdqu  xmmword ptr [rbp+cchPath], xmm1
0x140018998  mov     r8, [rdx+10h]
0x14001899c  cmp     qword ptr [rdx+18h], 7
0x1400189a1  jbe     short loc_1400189A6
0x1400189a3  mov     rdx, [rdx]
0x1400189a6  lea     rcx, [rbp+pszPath]
0x1400189aa  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400189af  nop
0x1400189b0  mov     rcx, [rdi]
0x1400189b3  cmp     qword ptr [rcx+18h], 7
0x1400189b8  jbe     short loc_1400189BD
0x1400189ba  mov     rcx, [rcx]; pszPath
0x1400189bd  call    cs:__imp_PathCchIsRoot
0x1400189c3  test    eax, eax
0x1400189c5  jnz     short loc_1400189FC
0x1400189c7  lea     rcx, [rbp+pszPath]
0x1400189cb  cmp     [rbp+cchPath+8], 7
0x1400189d0  cmova   rcx, [rbp+pszPath]; pszPath
0x1400189d5  mov     rdx, [rbp+cchPath]; cchPath
0x1400189d9  call    cs:__imp_PathCchStripToRoot
0x1400189df  mov     rcx, [rbp+8]; this
0x1400189e3  test    eax, eax
0x1400189e5  jns     short loc_1400189FC
0x1400189e7  mov     r9d, eax; char *
0x1400189ea  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400189f1  mov     edx, 0CDh; void *
0x1400189f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400189fc  lea     rcx, [rbp+pszPath]
0x140018a00  cmp     [rbp+cchPath+8], 7
0x140018a05  cmova   rcx, [rbp+pszPath]; lpRootPathName
0x140018a0a  call    cs:__imp_GetDriveTypeW
0x140018a10  mov     [rbx], eax
0x140018a12  mov     byte ptr [rbx+4], 1
0x140018a16  mov     rdx, [rbp+cchPath+8]
0x140018a1a  cmp     rdx, 7
0x140018a1e  jbe     short loc_140018A31
0x140018a20  lea     rdx, ds:2[rdx*2]
0x140018a28  mov     rcx, [rbp+pszPath]
0x140018a2c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140018a31  mov     rax, rbx
0x140018a34  mov     rcx, [rbp+var_8]
0x140018a38  xor     rcx, rsp; StackCookie
0x140018a3b  call    __security_check_cookie
0x140018a40  mov     rbx, [rsp+50h+arg_10]
0x140018a45  mov     rdi, [rsp+50h+arg_18]
0x140018a4a  add     rsp, 50h
0x140018a4e  pop     rbp
0x140018a4f  retn
```
