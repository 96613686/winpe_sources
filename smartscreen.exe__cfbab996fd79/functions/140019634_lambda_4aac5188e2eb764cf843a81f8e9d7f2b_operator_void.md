# _lambda_4aac5188e2eb764cf843a81f8e9d7f2b_::operator()(void)

- ea: `0x140019634`
- end: `0x140019737`
- name: `??R_lambda_4aac5188e2eb764cf843a81f8e9d7f2b_@@QEBA?AV?$optional@H@std@@XZ`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140019444`

## callees

- `0x1400055ac`
- `0x140019634`
- `0x140019784`
- `0x140019844`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400196ea`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400196ea`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x140019691`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x140019691`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400196b3`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400196b3`

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
0x140019634  mov     [rsp-8+arg_10], rbx
0x140019639  mov     [rsp-8+arg_18], rdi
0x14001963e  push    rbp
0x14001963f  mov     rbp, rsp
0x140019642  sub     rsp, 50h
0x140019646  mov     rax, cs:__security_cookie
0x14001964d  xor     rax, rsp
0x140019650  mov     [rbp+var_8], rax
0x140019654  mov     rbx, rdx
0x140019657  mov     rdi, rcx
0x14001965a  mov     rdx, [rcx]
0x14001965d  xorps   xmm0, xmm0
0x140019660  movups  xmmword ptr [rbp+pszPath], xmm0
0x140019664  xorps   xmm1, xmm1
0x140019667  movdqu  xmmword ptr [rbp+cchPath], xmm1
0x14001966c  mov     r8, [rdx+10h]
0x140019670  cmp     qword ptr [rdx+18h], 7
0x140019675  jbe     short loc_14001967A
0x140019677  mov     rdx, [rdx]
0x14001967a  lea     rcx, [rbp+pszPath]
0x14001967e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140019683  nop
0x140019684  mov     rcx, [rdi]
0x140019687  cmp     qword ptr [rcx+18h], 7
0x14001968c  jbe     short loc_140019691
0x14001968e  mov     rcx, [rcx]; pszPath
0x140019691  call    cs:__imp_PathCchIsRoot
0x140019698  nop     dword ptr [rax+rax+00h]
0x14001969d  test    eax, eax
0x14001969f  jnz     short loc_1400196DC
0x1400196a1  lea     rcx, [rbp+pszPath]
0x1400196a5  cmp     [rbp+cchPath+8], 7
0x1400196aa  cmova   rcx, [rbp+pszPath]; pszPath
0x1400196af  mov     rdx, [rbp+cchPath]; cchPath
0x1400196b3  call    cs:__imp_PathCchStripToRoot
0x1400196ba  nop     dword ptr [rax+rax+00h]
0x1400196bf  mov     rcx, [rbp+8]; this
0x1400196c3  test    eax, eax
0x1400196c5  jns     short loc_1400196DC
0x1400196c7  mov     r9d, eax; char *
0x1400196ca  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400196d1  mov     edx, 0CDh; void *
0x1400196d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400196dc  lea     rcx, [rbp+pszPath]
0x1400196e0  cmp     [rbp+cchPath+8], 7
0x1400196e5  cmova   rcx, [rbp+pszPath]; lpRootPathName
0x1400196ea  call    cs:__imp_GetDriveTypeW
0x1400196f1  nop     dword ptr [rax+rax+00h]
0x1400196f6  mov     [rbx], eax
0x1400196f8  mov     byte ptr [rbx+4], 1
0x1400196fc  mov     rdx, [rbp+cchPath+8]
0x140019700  cmp     rdx, 7
0x140019704  jbe     short loc_140019717
0x140019706  lea     rdx, ds:2[rdx*2]
0x14001970e  mov     rcx, [rbp+pszPath]
0x140019712  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140019717  mov     rax, rbx
0x14001971a  mov     rcx, [rbp+var_8]
0x14001971e  xor     rcx, rsp; StackCookie
0x140019721  call    __security_check_cookie
0x140019726  mov     rbx, [rsp+50h+arg_10]
0x14001972b  mov     rdi, [rsp+50h+arg_18]
0x140019730  add     rsp, 50h
0x140019734  pop     rbp
0x140019735  retn
```
