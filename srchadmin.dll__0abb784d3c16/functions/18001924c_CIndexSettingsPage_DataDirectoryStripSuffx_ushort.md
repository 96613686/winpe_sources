# CIndexSettingsPage::_DataDirectoryStripSuffx(ushort *)

- ea: `0x18001924c`
- end: `0x1800192d5`
- name: `?_DataDirectoryStripSuffx@CIndexSettingsPage@@AEAAJPEAG@Z`
- size: `137`
- prototype: `__int64 __fastcall(CIndexSettingsPage *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800194e8`
- `0x180019598`

## callees

- `0x18001924c`

## import_xrefs

- `SHLWAPI!PathRemoveBackslashW` at `0x180019275`
- `SHLWAPI!PathRemoveBackslashW` at `0x180019275`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800192ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800192ad`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_DataDirectoryStripSuffx(CIndexSettingsPage *this, unsigned __int16 *a2)
{
  __int64 v2; // rbx
  LPWSTR v4; // rax
  int v5; // ecx
  unsigned __int16 *v6; // rbx
  __int64 result; // rax

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  if ( (int)v2 <= 12 )
    return 2147942413LL;
  v4 = PathRemoveBackslashW(a2);
  v5 = v2 - 1;
  if ( *v4 )
    v5 = v2;
  v6 = &a2[v5];
  if ( CompareStringW(0x7Fu, 1u, v6 - 11, 11, L"Search\\Data", 11) != 2 )
    return 2147942413LL;
  result = 0;
  *(v6 - 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18001924c  mov     [rsp+arg_0], rbx
0x180019251  mov     [rsp+arg_8], rsi
0x180019256  push    rdi
0x180019257  sub     rsp, 30h
0x18001925b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001925f  mov     rdi, rdx
0x180019262  xor     esi, esi
0x180019264  inc     rbx
0x180019267  cmp     [rdx+rbx*2], si
0x18001926b  jnz     short loc_180019264
0x18001926d  cmp     ebx, 0Ch
0x180019270  jle     short loc_1800192B8
0x180019272  mov     rcx, rdi; pszPath
0x180019275  call    cs:__imp_PathRemoveBackslashW
0x18001927b  lea     ecx, [rbx-1]
0x18001927e  mov     r9d, 0Bh; cchCount1
0x180019284  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180019289  cmp     [rax], si
0x18001928c  lea     edx, [r9-0Ah]; dwCmpFlags
0x180019290  cmovnz  ecx, ebx
0x180019293  movsxd  rax, ecx
0x180019296  lea     ecx, [rdx+7Eh]; Locale
0x180019299  lea     rbx, [rdi+rax*2]
0x18001929d  lea     rax, pszFile; "Search\\Data"
0x1800192a4  lea     r8, [rbx-16h]; lpString1
0x1800192a8  mov     [rsp+38h+lpString2], rax; lpString2
0x1800192ad  call    cs:__imp_CompareStringW
0x1800192b3  cmp     eax, 2
0x1800192b6  jz      short loc_1800192BF
0x1800192b8  mov     eax, 8007000Dh
0x1800192bd  jmp     short loc_1800192C5
0x1800192bf  mov     eax, esi
0x1800192c1  mov     [rbx-18h], si
0x1800192c5  mov     rbx, [rsp+38h+arg_0]
0x1800192ca  mov     rsi, [rsp+38h+arg_8]
0x1800192cf  add     rsp, 30h
0x1800192d3  pop     rdi
0x1800192d4  retn
```
