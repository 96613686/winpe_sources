# VmRepositoryUtilities::IsVmFilePathValid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,bool)

- ea: `0x1400bab74`
- end: `0x1400bac03`
- name: `?IsVmFilePathValid@VmRepositoryUtilities@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1401e97cc`

## callees

- `0x1400bab74`
- `0x1400bac0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400babc3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400babc3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400bab8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400bab8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400babad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400babad`

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
0x1400bab74  mov     [rsp+arg_0], rbx
0x1400bab79  push    rdi
0x1400bab7a  sub     rsp, 20h
0x1400bab7e  cmp     qword ptr [rcx+18h], 7
0x1400bab83  mov     dil, r8b
0x1400bab86  mov     rbx, rcx
0x1400bab89  jbe     short loc_1400BAB8E
0x1400bab8b  mov     rcx, [rcx]; pszPath
0x1400bab8e  call    cs:__imp_PathIsRelativeW
0x1400bab95  nop     dword ptr [rax+rax+00h]
0x1400bab9a  test    eax, eax
0x1400bab9c  jnz     short loc_1400BABF5
0x1400bab9e  cmp     qword ptr [rbx+18h], 7
0x1400baba3  jbe     short loc_1400BABAA
0x1400baba5  mov     rcx, [rbx]
0x1400baba8  jmp     short loc_1400BABAD
0x1400babaa  mov     rcx, rbx; pszPath
0x1400babad  call    cs:__imp_PathFindExtensionW
0x1400babb4  nop     dword ptr [rax+rax+00h]
0x1400babb9  mov     rcx, rax
0x1400babbc  lea     rdx, ?SAVED_STATE_FILE_EXTENSION@@3QBGB; ".vsv"
0x1400babc3  call    cs:__imp__o__wcsicmp
0x1400babca  nop     dword ptr [rax+rax+00h]
0x1400babcf  test    eax, eax
0x1400babd1  jnz     short loc_1400BABF5
0x1400babd3  test    dil, dil
0x1400babd6  jz      short loc_1400BABF1
0x1400babd8  cmp     qword ptr [rbx+18h], 7
0x1400babdd  jbe     short loc_1400BABE2
0x1400babdf  mov     rbx, [rbx]
0x1400babe2  mov     rcx, rbx; this
0x1400babe5  call    ?FileExists@Details@VmRepositoryUtilities@@YA_NPEBG@Z; VmRepositoryUtilities::Details::FileExists(ushort const *)
0x1400babea  test    al, al
0x1400babec  setnz   al
0x1400babef  jmp     short loc_1400BABF7
0x1400babf1  mov     al, 1
0x1400babf3  jmp     short loc_1400BABF7
0x1400babf5  xor     al, al
0x1400babf7  mov     rbx, [rsp+28h+arg_0]
0x1400babfc  add     rsp, 20h
0x1400bac00  pop     rdi
0x1400bac01  retn
```
