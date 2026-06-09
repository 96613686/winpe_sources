# VmRepositoryUtilities::IsVmFilePathValid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,bool)

- ea: `0x1400a8270`
- end: `0x1400a82ff`
- name: `?IsVmFilePathValid@VmRepositoryUtilities@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1401d915c`

## callees

- `0x1400a8270`
- `0x1400a8308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400a82bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400a82bf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400a82a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400a82a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400a828a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400a828a`

## pseudocode

```c
bool __fastcall VmRepositoryUtilities::IsVmFilePathValid(VmRepositoryUtilities::Details *pszPath, __int64 a2, char a3)
{
  VmRepositoryUtilities::Details *v4; // rbx
  const WCHAR *v5; // rcx
  LPWSTR ExtensionW; // rax
  const unsigned __int16 *v7; // rdx

  v4 = pszPath;
  if ( *((_QWORD *)pszPath + 3) > 7u )
    pszPath = *(VmRepositoryUtilities::Details **)pszPath;
  if ( PathIsRelativeW((LPCWSTR)pszPath) )
    return 0;
  v5 = *((_QWORD *)v4 + 3) <= 7u ? (const WCHAR *)v4 : *(const WCHAR **)v4;
  ExtensionW = PathFindExtensionW(v5);
  if ( (unsigned int)_o__wcsicmp(ExtensionW, L".vsv") )
    return 0;
  if ( !a3 )
    return 1;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(VmRepositoryUtilities::Details **)v4;
  return VmRepositoryUtilities::Details::FileExists(v4, v7);
}

```

## disassembly

```asm
0x1400a8270  mov     [rsp+arg_0], rbx
0x1400a8275  push    rdi
0x1400a8276  sub     rsp, 20h
0x1400a827a  cmp     qword ptr [rcx+18h], 7
0x1400a827f  mov     dil, r8b
0x1400a8282  mov     rbx, rcx
0x1400a8285  jbe     short loc_1400A828A
0x1400a8287  mov     rcx, [rcx]; pszPath
0x1400a828a  call    cs:__imp_PathIsRelativeW
0x1400a8291  nop     dword ptr [rax+rax+00h]
0x1400a8296  test    eax, eax
0x1400a8298  jnz     short loc_1400A82F1
0x1400a829a  cmp     qword ptr [rbx+18h], 7
0x1400a829f  jbe     short loc_1400A82A6
0x1400a82a1  mov     rcx, [rbx]
0x1400a82a4  jmp     short loc_1400A82A9
0x1400a82a6  mov     rcx, rbx; pszPath
0x1400a82a9  call    cs:__imp_PathFindExtensionW
0x1400a82b0  nop     dword ptr [rax+rax+00h]
0x1400a82b5  mov     rcx, rax
0x1400a82b8  lea     rdx, ?SAVED_STATE_FILE_EXTENSION@@3QBGB; ".vsv"
0x1400a82bf  call    cs:__imp__o__wcsicmp
0x1400a82c6  nop     dword ptr [rax+rax+00h]
0x1400a82cb  test    eax, eax
0x1400a82cd  jnz     short loc_1400A82F1
0x1400a82cf  test    dil, dil
0x1400a82d2  jz      short loc_1400A82ED
0x1400a82d4  cmp     qword ptr [rbx+18h], 7
0x1400a82d9  jbe     short loc_1400A82DE
0x1400a82db  mov     rbx, [rbx]
0x1400a82de  mov     rcx, rbx; this
0x1400a82e1  call    ?FileExists@Details@VmRepositoryUtilities@@YA_NPEBG@Z; VmRepositoryUtilities::Details::FileExists(ushort const *)
0x1400a82e6  test    al, al
0x1400a82e8  setnz   al
0x1400a82eb  jmp     short loc_1400A82F3
0x1400a82ed  mov     al, 1
0x1400a82ef  jmp     short loc_1400A82F3
0x1400a82f1  xor     al, al
0x1400a82f3  mov     rbx, [rsp+28h+arg_0]
0x1400a82f8  add     rsp, 20h
0x1400a82fc  pop     rdi
0x1400a82fd  retn
```
