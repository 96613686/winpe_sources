# PathCchIsRoot

- ea: `0x180027608`
- end: `0x180027711`
- name: `PathCchIsRoot`
- size: `265`
- prototype: `BOOL __stdcall(PCWSTR pszPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180026018`
- `0x1800278cc`

## callees

- `0x180025960`
- `0x180026684`
- `0x18002671c`
- `0x180026c8c`
- `0x180027608`

## import_xrefs

- `msvcrt!iswalpha` at `0x180027636`
- `msvcrt!iswalpha` at `0x1800276bb`
- `msvcrt!iswalpha` at `0x180027636`
- `msvcrt!iswalpha` at `0x1800276bb`

## pseudocode

```c
BOOL __stdcall PathCchIsRoot(PCWSTR pszPath)
{
  WCHAR v2; // cx
  _WORD *v3; // rax
  int v4; // ecx

  if ( pszPath )
  {
    v2 = *pszPath;
    if ( v2 )
    {
      if ( iswalpha(v2) && StrIsEqualCaseInsensitive(pszPath + 1, L":\\", 3) || *pszPath == 92 && !pszPath[1] )
        return 1;
      if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
      {
        v3 = 0;
        v4 = 0;
        while ( *v3 )
        {
          if ( *v3 == 92 && (++v4 > 1 || !v3[1]) )
            return 0;
          ++v3;
        }
        return 1;
      }
      if ( IsExtendedLengthDosDevicePath(pszPath)
        && iswalpha(pszPath[4])
        && StrIsEqualCaseInsensitive(pszPath + 5, L":\\", 3)
        || PathIsVolumeGUIDWorker(pszPath) && pszPath[48] == 92 && !pszPath[49] )
      {
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027608  mov     [rsp+arg_8], rbx
0x18002760d  mov     [rsp+arg_10], rsi
0x180027612  push    rdi
0x180027613  sub     rsp, 20h
0x180027617  xor     esi, esi
0x180027619  mov     rbx, rcx
0x18002761c  mov     [rsp+28h+arg_0], rsi
0x180027621  test    rcx, rcx
0x180027624  jz      loc_1800276FF
0x18002762a  movzx   ecx, word ptr [rcx]; C
0x18002762d  test    cx, cx
0x180027630  jz      loc_1800276FF
0x180027636  call    cs:__imp_iswalpha
0x18002763c  lea     rdi, [rbx+2]
0x180027640  test    eax, eax
0x180027642  jz      short loc_18002765F
0x180027644  lea     r8d, [rsi+3]; int
0x180027648  mov     rcx, rdi; unsigned __int16 *
0x18002764b  lea     rdx, asc_18002EB24; ":\\"
0x180027652  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x180027657  test    al, al
0x180027659  jnz     loc_1800276F8
0x18002765f  cmp     word ptr [rbx], 5Ch ; '\'
0x180027663  jnz     short loc_18002766E
0x180027665  cmp     [rdi], si
0x180027668  jz      loc_1800276F8
0x18002766e  lea     r8, IsBackslash
0x180027675  mov     rcx, rbx; unsigned __int16 *
0x180027678  lea     rdx, [rsp+28h+arg_0]
0x18002767d  call    PathIsUnc2
0x180027682  test    eax, eax
0x180027684  jz      short loc_1800276AB
0x180027686  mov     rax, [rsp+28h+arg_0]
0x18002768b  mov     ecx, esi
0x18002768d  cmp     [rax], si
0x180027690  jz      short loc_1800276F8
0x180027692  cmp     word ptr [rax], 5Ch ; '\'
0x180027696  jnz     short loc_1800276A5
0x180027698  inc     ecx
0x18002769a  cmp     ecx, 1
0x18002769d  jg      short loc_1800276FF
0x18002769f  cmp     [rax+2], si
0x1800276a3  jz      short loc_1800276FF
0x1800276a5  add     rax, 2
0x1800276a9  jmp     short loc_18002768D
0x1800276ab  mov     rcx, rbx; unsigned __int16 *
0x1800276ae  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x1800276b3  test    al, al
0x1800276b5  jz      short loc_1800276DF
0x1800276b7  movzx   ecx, word ptr [rbx+8]; C
0x1800276bb  call    cs:__imp_iswalpha
0x1800276c1  test    eax, eax
0x1800276c3  jz      short loc_1800276DF
0x1800276c5  lea     rcx, [rbx+0Ah]; unsigned __int16 *
0x1800276c9  mov     r8d, 3; int
0x1800276cf  lea     rdx, asc_18002EB24; ":\\"
0x1800276d6  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x1800276db  test    al, al
0x1800276dd  jnz     short loc_1800276F8
0x1800276df  mov     rcx, rbx; unsigned __int16 *
0x1800276e2  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x1800276e7  test    al, al
0x1800276e9  jz      short loc_1800276FF
0x1800276eb  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x1800276f0  jnz     short loc_1800276FF
0x1800276f2  cmp     [rbx+62h], si
0x1800276f6  jnz     short loc_1800276FF
0x1800276f8  mov     eax, 1
0x1800276fd  jmp     short loc_180027701
0x1800276ff  xor     eax, eax
0x180027701  mov     rbx, [rsp+28h+arg_8]
0x180027706  mov     rsi, [rsp+28h+arg_10]
0x18002770b  add     rsp, 20h
0x18002770f  pop     rdi
0x180027710  retn
```
