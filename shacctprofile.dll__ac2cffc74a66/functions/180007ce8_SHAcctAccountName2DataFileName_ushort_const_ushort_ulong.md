# SHAcctAccountName2DataFileName(ushort const *,ushort *,ulong)

- ea: `0x180007ce8`
- end: `0x180007f11`
- name: `?SHAcctAccountName2DataFileName@@YAJPEBGPEAGK@Z`
- size: `553`
- prototype: `__int64 __fastcall(WCHAR *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000834c`
- `0x18000855c`

## callees

- `0x180002230`
- `0x1800058f4`
- `0x180007ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ebe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180007e34`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180007e34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e49`
- `SHLWAPI!StrChrW` at `0x180007d95`
- `SHLWAPI!StrChrW` at `0x180007d95`

## pseudocode

```c
__int64 __fastcall SHAcctAccountName2DataFileName(WCHAR *a1, unsigned __int16 *a2)
{
  __int64 v3; // r14
  WCHAR *v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  signed int v9; // ebx
  PWSTR v10; // rsi
  unsigned __int64 v11; // rcx
  WCHAR *v12; // r8
  __int64 v13; // rdx
  WCHAR *v14; // rax
  WCHAR *v15; // rcx
  WCHAR *v16; // rcx
  WCHAR *v17; // rax
  WCHAR *v18; // rcx
  signed int LastError; // eax
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[20]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR String2[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStart[520]; // [rsp+250h] [rbp+150h] BYREF

  if ( !a1 )
    return (unsigned int)-2147024809;
  v3 = 2147483646;
  v4 = pszStart;
  v5 = 513;
  v6 = 2147483646;
  v7 = 513;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  v9 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v8 = v4;
  *v8 = 0;
  if ( v7 )
  {
    v10 = StrChrW(pszStart, 0x5Cu);
    if ( !v10 )
      return (unsigned int)StringCchCopyW(a2, 0x104u, pszStart);
    v11 = v10 - pszStart;
    if ( v11 <= 0x7FFFFFFE )
    {
      v12 = pszStart;
      v13 = 256;
      v14 = String2;
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v11;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      if ( v13 )
        v15 = v14;
      v9 = v13 == 0 ? 0x8007007A : 0;
      *v15 = 0;
    }
    else
    {
      v9 = -2147024809;
      String2[0] = 0;
    }
    if ( v9 >= 0 )
    {
      nSize = 16;
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        if ( lstrcmpiW(Buffer, String2) )
        {
          *v10 = 43;
        }
        else
        {
          v16 = v10 + 1;
          v17 = pszStart;
          do
          {
            if ( !v3 )
              break;
            if ( !*v16 )
              break;
            *v17++ = *v16++;
            --v3;
            --v5;
          }
          while ( v5 );
          v18 = v17 - 1;
          if ( v5 )
            v18 = v17;
          v9 = v5 == 0 ? 0x8007007A : 0;
          *v18 = 0;
        }
        if ( v9 >= 0 )
          return (unsigned int)StringCchCopyW(a2, 0x104u, pszStart);
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
          return (unsigned int)-2147467259;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007ce8  mov     [rsp-8+arg_0], rbx
0x180007ced  mov     [rsp-8+arg_10], rsi
0x180007cf2  push    rbp
0x180007cf3  push    rdi
0x180007cf4  push    r12
0x180007cf6  push    r14
0x180007cf8  push    r15
0x180007cfa  lea     rbp, [rsp-570h]
0x180007d02  sub     rsp, 670h
0x180007d09  mov     rax, cs:__security_cookie
0x180007d10  xor     rax, rsp
0x180007d13  mov     [rbp+590h+var_30], rax
0x180007d1a  xor     r12d, r12d
0x180007d1d  mov     r15, rdx
0x180007d20  test    rcx, rcx
0x180007d23  jz      loc_180007EDF
0x180007d29  mov     r14d, 7FFFFFFEh
0x180007d2f  lea     r8, [rbp+590h+pszStart]
0x180007d36  mov     edi, 201h
0x180007d3b  mov     eax, r14d
0x180007d3e  mov     edx, edi
0x180007d40  test    rax, rax
0x180007d43  jz      short loc_180007D64
0x180007d45  movzx   r9d, word ptr [rcx]
0x180007d49  test    r9w, r9w
0x180007d4d  jz      short loc_180007D64
0x180007d4f  mov     [r8], r9w
0x180007d53  add     rcx, 2
0x180007d57  add     r8, 2
0x180007d5b  dec     rax
0x180007d5e  sub     rdx, 1
0x180007d62  jnz     short loc_180007D40
0x180007d64  mov     rax, rdx
0x180007d67  lea     rcx, [r8-2]
0x180007d6b  neg     rax
0x180007d6e  sbb     ebx, ebx
0x180007d70  not     ebx
0x180007d72  and     ebx, 8007007Ah
0x180007d78  test    rdx, rdx
0x180007d7b  cmovnz  rcx, r8
0x180007d7f  mov     [rcx], r12w
0x180007d83  jz      loc_180007EE4
0x180007d89  mov     edx, 5Ch ; '\'; wMatch
0x180007d8e  lea     rcx, [rbp+590h+pszStart]; pszStart
0x180007d95  call    cs:__imp_StrChrW
0x180007d9b  mov     rsi, rax
0x180007d9e  test    rax, rax
0x180007da1  jz      loc_180007EA6
0x180007da7  lea     rax, [rbp+590h+pszStart]
0x180007dae  mov     rcx, rsi
0x180007db1  sub     rcx, rax
0x180007db4  sar     rcx, 1
0x180007db7  cmp     rcx, r14
0x180007dba  jbe     short loc_180007DC9
0x180007dbc  mov     ebx, 80070057h
0x180007dc1  mov     [rsp+690h+String2], r12w
0x180007dc7  jmp     short loc_180007E1A
0x180007dc9  lea     r8, [rbp+590h+pszStart]
0x180007dd0  mov     edx, 100h
0x180007dd5  lea     rax, [rsp+690h+String2]
0x180007dda  test    rcx, rcx
0x180007ddd  jz      short loc_180007DFE
0x180007ddf  movzx   r9d, word ptr [r8]
0x180007de3  test    r9w, r9w
0x180007de7  jz      short loc_180007DFE
0x180007de9  mov     [rax], r9w
0x180007ded  add     r8, 2
0x180007df1  add     rax, 2
0x180007df5  dec     rcx
0x180007df8  sub     rdx, 1
0x180007dfc  jnz     short loc_180007DDA
0x180007dfe  test    rdx, rdx
0x180007e01  lea     rcx, [rax-2]
0x180007e05  cmovnz  rcx, rax
0x180007e09  neg     rdx
0x180007e0c  sbb     ebx, ebx
0x180007e0e  not     ebx
0x180007e10  and     ebx, 8007007Ah
0x180007e16  mov     [rcx], r12w
0x180007e1a  test    ebx, ebx
0x180007e1c  js      loc_180007EE4
0x180007e22  lea     rdx, [rsp+690h+nSize]; nSize
0x180007e27  mov     [rsp+690h+nSize], 10h
0x180007e2f  lea     rcx, [rsp+690h+Buffer]; lpBuffer
0x180007e34  call    cs:__imp_GetComputerNameW
0x180007e3a  cmp     eax, 1
0x180007e3d  jnz     short loc_180007EBE
0x180007e3f  lea     rdx, [rsp+690h+String2]; lpString2
0x180007e44  lea     rcx, [rsp+690h+Buffer]; lpString1
0x180007e49  call    cs:__imp_lstrcmpiW
0x180007e4f  test    eax, eax
0x180007e51  jnz     short loc_180007E9D
0x180007e53  lea     rcx, [rsi+2]
0x180007e57  lea     rax, [rbp+590h+pszStart]
0x180007e5e  test    r14, r14
0x180007e61  jz      short loc_180007E7F
0x180007e63  movzx   edx, word ptr [rcx]
0x180007e66  test    dx, dx
0x180007e69  jz      short loc_180007E7F
0x180007e6b  mov     [rax], dx
0x180007e6e  add     rcx, 2
0x180007e72  add     rax, 2
0x180007e76  dec     r14
0x180007e79  sub     rdi, 1
0x180007e7d  jnz     short loc_180007E5E
0x180007e7f  test    rdi, rdi
0x180007e82  lea     rcx, [rax-2]
0x180007e86  cmovnz  rcx, rax
0x180007e8a  neg     rdi
0x180007e8d  sbb     ebx, ebx
0x180007e8f  not     ebx
0x180007e91  and     ebx, 8007007Ah
0x180007e97  mov     [rcx], r12w
0x180007e9b  jmp     short loc_180007EA2
0x180007e9d  mov     word ptr [rsi], 2Bh ; '+'
0x180007ea2  test    ebx, ebx
0x180007ea4  js      short loc_180007EE4
0x180007ea6  lea     r8, [rbp+590h+pszStart]; unsigned __int16 *
0x180007ead  mov     edx, 104h; unsigned __int64
0x180007eb2  mov     rcx, r15; unsigned __int16 *
0x180007eb5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007eba  mov     ebx, eax
0x180007ebc  jmp     short loc_180007EE4
0x180007ebe  call    cs:__imp_GetLastError
0x180007ec4  mov     ebx, eax
0x180007ec6  test    eax, eax
0x180007ec8  jle     short loc_180007ED3
0x180007eca  movzx   ebx, ax
0x180007ecd  or      ebx, 80070000h
0x180007ed3  test    ebx, ebx
0x180007ed5  mov     eax, 80004005h
0x180007eda  cmovns  ebx, eax
0x180007edd  jmp     short loc_180007EE4
0x180007edf  mov     ebx, 80070057h
0x180007ee4  mov     eax, ebx
0x180007ee6  mov     rcx, [rbp+590h+var_30]
0x180007eed  xor     rcx, rsp; StackCookie
0x180007ef0  call    __security_check_cookie
0x180007ef5  lea     r11, [rsp+690h+var_20]
0x180007efd  mov     rbx, [r11+30h]
0x180007f01  mov     rsi, [r11+40h]
0x180007f05  mov     rsp, r11
0x180007f08  pop     r15
0x180007f0a  pop     r14
0x180007f0c  pop     r12
0x180007f0e  pop     rdi
0x180007f0f  pop     rbp
0x180007f10  retn
```
