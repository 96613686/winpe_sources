# AreDesktopIconsValid(void)

- ea: `0x1800407e8`
- end: `0x1800409ad`
- name: `?AreDesktopIconsValid@@YA_NXZ`
- size: `453`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180040f10`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x1800358c0`
- `0x18003633c`
- `0x1800407e8`

## import_xrefs

- `SHCORE!SHRegGetPathW` at `0x18004090e`
- `SHCORE!SHRegGetPathW` at `0x18004090e`
- `SHLWAPI!PathFileExistsW` at `0x18004092c`
- `SHLWAPI!PathFileExistsW` at `0x180040955`
- `SHLWAPI!PathFileExistsW` at `0x18004092c`
- `SHLWAPI!PathFileExistsW` at `0x180040955`
- `SHLWAPI!StrChrW` at `0x180040888`
- `SHLWAPI!StrChrW` at `0x180040888`
- `SHLWAPI!StrRChrW` at `0x180040941`
- `SHLWAPI!StrRChrW` at `0x180040941`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800408df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800408df`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040899`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040899`

## pseudocode

```c
bool AreDesktopIconsValid(void)
{
  const unsigned __int16 *const near *v0; // rax
  signed int v1; // ebx
  int v2; // esi
  const WCHAR *v3; // rax
  const WCHAR *v4; // rdi
  const unsigned __int16 *v5; // rax
  WCHAR *v6; // r8
  LSTATUS PathW; // eax
  PWSTR v8; // rax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String1[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR pszStart[264]; // [rsp+450h] [rbp+350h] BYREF

  v0 = c_rgszDesktopIcons;
  v1 = 0;
  v2 = 0;
  while ( *(_WORD *)v0 && v1 >= 0 )
  {
    memset_0(String1, 0, 0x208u);
    v1 = StringCchPrintfW(
           pszStart,
           0x104u,
           L"%s\\%s",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
           (&c_rgszDesktopIcons)[v2]);
    if ( v1 >= 0 )
    {
      v3 = StrChrW(pszStart, 0x3Au);
      v4 = v3;
      if ( v3 )
      {
        v5 = CharNextW(v3);
        v1 = StringCchCopyW(String1, 0x104u, v5);
        *v4 = 0;
      }
      if ( v1 >= 0 )
      {
        if ( CompareStringOrdinal(String1, -1, L"DefaultValue", -1, 1) == 2 )
          v6 = 0;
        else
          v6 = String1;
        PathW = SHRegGetPathW(HKEY_CURRENT_USER, pszStart, v6, pszPath, 0);
        v1 = PathW;
        if ( PathW > 0 )
          v1 = (unsigned __int16)PathW | 0x80070000;
        if ( v1 >= 0 && !PathFileExistsW(pszPath) )
        {
          v8 = StrRChrW(pszPath, 0, 0x2Cu);
          if ( v8 )
          {
            *v8 = 0;
            v1 = !PathFileExistsW(pszPath) ? 0x80004005 : 0;
          }
          else
          {
            v1 = -2147467259;
          }
        }
      }
    }
    v0 = (&c_rgszDesktopIcons)[++v2];
  }
  return v1 >= 0;
}

```

## disassembly

```asm
0x1800407e8  push    rbp
0x1800407ea  push    rbx
0x1800407eb  push    rsi
0x1800407ec  push    rdi
0x1800407ed  push    r14
0x1800407ef  lea     rbp, [rsp-570h]
0x1800407f7  sub     rsp, 670h
0x1800407fe  mov     rax, cs:__security_cookie
0x180040805  xor     rax, rsp
0x180040808  mov     [rbp+590h+var_30], rax
0x18004080f  mov     rax, cs:?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x180040816  xor     r14d, r14d
0x180040819  mov     ebx, r14d
0x18004081c  mov     esi, r14d
0x18004081f  jmp     loc_18004097E
0x180040824  test    ebx, ebx
0x180040826  js      loc_180040988
0x18004082c  xor     edx, edx; Val
0x18004082e  lea     rcx, [rbp+590h+String1]; void *
0x180040835  mov     r8d, 208h; Size
0x18004083b  call    memset_0
0x180040840  lea     rcx, ?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x180040847  movsxd  rax, esi
0x18004084a  lea     r9, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180040851  mov     edx, 104h; unsigned __int64
0x180040856  lea     r8, aSS; "%s\\%s"
0x18004085d  mov     rax, [rcx+rax*8]
0x180040861  lea     rcx, [rbp+590h+pszStart]; unsigned __int16 *
0x180040868  mov     qword ptr [rsp+690h+bIgnoreCase], rax
0x18004086d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040872  mov     ebx, eax
0x180040874  test    eax, eax
0x180040876  js      loc_18004096E
0x18004087c  mov     edx, 3Ah ; ':'; wMatch
0x180040881  lea     rcx, [rbp+590h+pszStart]; pszStart
0x180040888  call    cs:__imp_StrChrW
0x18004088e  mov     rdi, rax
0x180040891  test    rax, rax
0x180040894  jz      short loc_1800408B9
0x180040896  mov     rcx, rax; lpsz
0x180040899  call    cs:__imp_CharNextW
0x18004089f  mov     edx, 104h; unsigned __int64
0x1800408a4  lea     rcx, [rbp+590h+String1]; unsigned __int16 *
0x1800408ab  mov     r8, rax; unsigned __int16 *
0x1800408ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800408b3  mov     ebx, eax
0x1800408b5  mov     [rdi], r14w
0x1800408b9  test    ebx, ebx
0x1800408bb  js      loc_18004096E
0x1800408c1  or      edi, 0FFFFFFFFh
0x1800408c4  mov     [rsp+690h+bIgnoreCase], 1; bIgnoreCase
0x1800408cc  mov     r9d, edi; cchCount2
0x1800408cf  lea     r8, aDefaultvalue; "DefaultValue"
0x1800408d6  mov     edx, edi; cchCount1
0x1800408d8  lea     rcx, [rbp+590h+String1]; lpString1
0x1800408df  call    cs:__imp_CompareStringOrdinal
0x1800408e5  mov     [rsp+690h+bIgnoreCase], r14d; dwFlags
0x1800408ea  lea     r9, [rsp+690h+pszPath]; pszPath
0x1800408ef  lea     rdx, [rbp+590h+pszStart]; pcszSubKey
0x1800408f6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800408fd  cmp     eax, 2
0x180040900  jnz     short loc_180040907
0x180040902  xor     r8d, r8d
0x180040905  jmp     short loc_18004090E
0x180040907  lea     r8, [rbp+590h+String1]; pcszValue
0x18004090e  call    cs:__imp_SHRegGetPathW
0x180040914  mov     ebx, eax
0x180040916  test    eax, eax
0x180040918  jle     short loc_180040923
0x18004091a  movzx   ebx, ax
0x18004091d  or      ebx, 80070000h
0x180040923  test    ebx, ebx
0x180040925  js      short loc_18004096E
0x180040927  lea     rcx, [rsp+690h+pszPath]; pszPath
0x18004092c  call    cs:__imp_PathFileExistsW
0x180040932  test    eax, eax
0x180040934  jnz     short loc_18004096E
0x180040936  xor     edx, edx; pszEnd
0x180040938  lea     r8d, [rax+2Ch]; wMatch
0x18004093c  lea     rcx, [rsp+690h+pszPath]; pszStart
0x180040941  call    cs:__imp_StrRChrW
0x180040947  test    rax, rax
0x18004094a  jz      short loc_180040969
0x18004094c  lea     rcx, [rsp+690h+pszPath]; pszPath
0x180040951  mov     [rax], r14w
0x180040955  call    cs:__imp_PathFileExistsW
0x18004095b  neg     eax
0x18004095d  sbb     ebx, ebx
0x18004095f  not     ebx
0x180040961  and     ebx, 80004005h
0x180040967  jmp     short loc_18004096E
0x180040969  mov     ebx, 80004005h
0x18004096e  inc     esi
0x180040970  lea     rcx, ?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x180040977  movsxd  rax, esi
0x18004097a  mov     rax, [rcx+rax*8]
0x18004097e  cmp     [rax], r14w
0x180040982  jnz     loc_180040824
0x180040988  shr     ebx, 1Fh
0x18004098b  xor     bl, 1
0x18004098e  mov     al, bl
0x180040990  mov     rcx, [rbp+590h+var_30]
0x180040997  xor     rcx, rsp; StackCookie
0x18004099a  call    __security_check_cookie
0x18004099f  add     rsp, 670h
0x1800409a6  pop     r14
0x1800409a8  pop     rdi
0x1800409a9  pop     rsi
0x1800409aa  pop     rbx
0x1800409ab  pop     rbp
0x1800409ac  retn
```
