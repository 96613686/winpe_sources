# GenerateNameFromTemplate(ushort *,_GENNAME_VARIABLES *,ushort *,ulong,ushort * *,int *,ulong *)

- ea: `0x180007ba4`
- end: `0x180007f80`
- name: `?GenerateNameFromTemplate@@YAKPEAGPEAU_GENNAME_VARIABLES@@0KPEAPEAGPEAHPEAK@Z`
- size: `988`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct _GENNAME_VARIABLES *, unsigned __int16 *, unsigned int, unsigned __int16 **, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007f90`

## callees

- `0x180007ba4`
- `0x180008574`
- `0x1800085fc`
- `0x180015660`
- `0x180015ca9`

## import_xrefs

- `SHLWAPI!StrCmpNIW` at `0x180007d78`
- `SHLWAPI!StrCmpNIW` at `0x180007ddd`
- `SHLWAPI!StrCmpNIW` at `0x180007e40`
- `SHLWAPI!StrCmpNIW` at `0x180007e90`
- `SHLWAPI!StrCmpNIW` at `0x180007d78`
- `SHLWAPI!StrCmpNIW` at `0x180007ddd`
- `SHLWAPI!StrCmpNIW` at `0x180007e40`
- `SHLWAPI!StrCmpNIW` at `0x180007e90`

## pseudocode

```c
__int64 __fastcall GenerateNameFromTemplate(unsigned __int16 *a1, struct _GENNAME_VARIABLES *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v4; // r12
  unsigned __int16 *v6; // r8
  unsigned int v7; // ecx
  int v8; // edx
  wchar_t v9; // ax
  wchar_t *v10; // rdi
  int v11; // r13d
  unsigned int v12; // ebx
  int v13; // ebp
  wchar_t v14; // si
  int v15; // eax
  unsigned int v16; // ecx
  __int64 v17; // rdx
  unsigned int v18; // edx
  __int64 v20; // rax
  signed __int64 v21; // rax
  unsigned __int16 v22; // cx
  __int64 v23; // [rsp+20h] [rbp-98h]
  int v24; // [rsp+30h] [rbp-88h]
  int v25; // [rsp+34h] [rbp-84h]
  unsigned __int16 *v26; // [rsp+38h] [rbp-80h]
  wchar_t v27[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t Buffer[12]; // [rsp+58h] [rbp-60h] BYREF

  v4 = a3;
  v6 = a3 + 63;
  v7 = 0;
  v8 = 0;
  v26 = v6;
  v9 = *a1;
  v10 = 0;
  v24 = 0;
  v11 = 0;
  v25 = 0;
  if ( !*a1 )
  {
LABEL_80:
    *v4 = 0;
    return v7;
  }
  while ( 1 )
  {
    ++a1;
    if ( v9 == 37 )
      break;
    v12 = 1;
    v27[0] = v9;
    v27[1] = 0;
    v10 = v27;
LABEL_74:
    v8 += v12;
    v25 = v8;
    v21 = (char *)v10 - (char *)v4;
    while ( 1 )
    {
      v22 = *(unsigned __int16 *)((char *)v4 + v21);
      if ( !v22 )
      {
LABEL_78:
        v7 = v24;
        goto LABEL_79;
      }
      if ( v4 >= v6 )
        break;
      *v4++ = v22;
      if ( !--v12 )
        goto LABEL_78;
    }
    v7 = 4;
    v24 = 4;
LABEL_79:
    v9 = *a1;
    if ( !*a1 )
      goto LABEL_80;
  }
  v12 = 0;
  v13 = 0;
  v14 = *a1;
  if ( *a1 >= 0x30u && v14 <= 0x39u )
  {
    if ( v14 == 48 )
    {
      v13 = 1;
      if ( *((_DWORD *)a2 + 8) == 123456789
        && *((_DWORD *)a2 + 9)
        && !wcscmp_0(*(const wchar_t **)a2, L"JOHNSMI")
        && !wcscmp_0(*((const wchar_t **)a2 + 3), L"123456789012") )
      {
        *((_DWORD *)a2 + 8) = 1;
        v14 = *a1;
      }
    }
    do
    {
      ++a1;
      v15 = v14;
      v14 = *a1;
      v12 = v15 + 2 * (5 * v12 - 24);
    }
    while ( *a1 >= 0x30u && v14 <= 0x39u );
  }
  if ( v14 == 35 )
  {
    if ( v12 > 9 )
      v12 = 9;
    if ( !v12 )
      v12 = 2;
    if ( v13 )
    {
      LODWORD(v23) = v12;
      StringCchPrintfW(Buffer, 0xAu, L"%s%d%s", L"%0", v23, L"d");
    }
    else
    {
      StringCchCopyW(Buffer, 0xAu, L"%d");
    }
    v16 = 10;
    if ( v12 > 1 )
    {
      v17 = v12 - 1;
      do
      {
        v16 *= 10;
        --v17;
      }
      while ( v17 );
    }
    v18 = *((_DWORD *)a2 + 8);
    if ( v18 >= v16 )
    {
      if ( !*((_DWORD *)a2 + 9) )
        return 2;
      while ( v18 > v16 )
        v18 /= 0xAu;
    }
    StringCchPrintfW(v27, 0xAu, Buffer, v18);
    v10 = v27;
    v20 = 2;
LABEL_72:
    a1 = (unsigned __int16 *)((char *)a1 + v20);
    v8 = v25;
    v6 = v26;
    goto LABEL_74;
  }
  if ( !StrCmpNIW(a1, L"First", 5) )
  {
    v10 = (wchar_t *)*((_QWORD *)a2 + 1);
    if ( v12 > 0x3F )
      v12 = 63;
    if ( !v12 )
      v12 = 63;
    if ( (!v10 || !*v10) && !v11 )
    {
      v10 = *(wchar_t **)a2;
      if ( !*(_QWORD *)a2 || !*v10 )
        return 3;
      v11 = 1;
    }
    v20 = 10;
    goto LABEL_72;
  }
  if ( !StrCmpNIW(a1, L"Last", 4) )
  {
    v10 = (wchar_t *)*((_QWORD *)a2 + 2);
    if ( v12 > 0x3F )
      v12 = 63;
    if ( !v12 )
      v12 = 63;
    if ( (!v10 || !*v10) && !v11 )
    {
      v10 = *(wchar_t **)a2;
      if ( !*(_QWORD *)a2 || !*v10 )
        return 3;
      v11 = 1;
    }
    v20 = 8;
    goto LABEL_72;
  }
  if ( !StrCmpNIW(a1, L"Username", 8) )
  {
    if ( v12 > 0x3F )
      v12 = 63;
    if ( !v12 )
      v12 = 63;
    if ( !v11 )
    {
      v10 = *(wchar_t **)a2;
      if ( !*(_QWORD *)a2 || !*v10 )
        return 3;
      v11 = 1;
    }
    v20 = 16;
    goto LABEL_72;
  }
  if ( !StrCmpNIW(a1, L"MAC", 3) )
  {
    v10 = (wchar_t *)*((_QWORD *)a2 + 3);
    if ( v12 > 0xC )
      v12 = 12;
    if ( !v12 )
      v12 = 12;
    if ( !v10 || !*v10 )
      return 3;
    v20 = 6;
    goto LABEL_72;
  }
  return 1;
}

```

## disassembly

```asm
0x180007ba4  mov     [rsp+arg_18], rbx
0x180007ba9  push    rbp
0x180007baa  push    rsi
0x180007bab  push    rdi
0x180007bac  push    r12
0x180007bae  push    r13
0x180007bb0  push    r14
0x180007bb2  push    r15
0x180007bb4  sub     rsp, 80h
0x180007bbb  mov     rax, cs:__security_cookie
0x180007bc2  xor     rax, rsp
0x180007bc5  mov     [rsp+0B8h+var_48], rax
0x180007bca  xor     esi, esi
0x180007bcc  mov     r14, rcx
0x180007bcf  mov     r12, r8
0x180007bd2  mov     r15, rdx
0x180007bd5  add     r8, 7Eh ; '~'
0x180007bd9  mov     ecx, esi
0x180007bdb  mov     edx, esi
0x180007bdd  mov     [rsp+0B8h+var_80], r8
0x180007be2  movzx   eax, word ptr [r14]
0x180007be6  mov     edi, esi
0x180007be8  mov     [rsp+0B8h+var_88], ecx
0x180007bec  mov     r13d, esi
0x180007bef  mov     [rsp+0B8h+var_84], edx
0x180007bf3  test    ax, ax
0x180007bf6  jz      loc_180007F38
0x180007bfc  lea     r9d, [rsi+2]
0x180007c00  lea     r11d, [rsi+9]
0x180007c04  add     r14, 2
0x180007c08  cmp     ax, 25h ; '%'
0x180007c0c  jnz     loc_180007EE7
0x180007c12  mov     ebx, esi
0x180007c14  mov     ebp, esi
0x180007c16  movzx   esi, word ptr [r14]
0x180007c1a  cmp     si, 30h ; '0'
0x180007c1e  jb      loc_180007CA8
0x180007c24  cmp     si, 39h ; '9'
0x180007c28  ja      short loc_180007CA8
0x180007c2a  cmp     si, 30h ; '0'
0x180007c2e  jnz     short loc_180007C89
0x180007c30  cmp     dword ptr [r15+20h], 75BCD15h
0x180007c38  mov     ebp, 1
0x180007c3d  jnz     short loc_180007C89
0x180007c3f  cmp     dword ptr [r15+24h], 0
0x180007c44  jz      short loc_180007C89
0x180007c46  mov     rcx, [r15]; String1
0x180007c49  lea     rdx, aJohnsmi; "JOHNSMI"
0x180007c50  call    wcscmp_0
0x180007c55  test    eax, eax
0x180007c57  jnz     short loc_180007C7F
0x180007c59  mov     rcx, [r15+18h]; String1
0x180007c5d  lea     rdx, a123456789012; "123456789012"
0x180007c64  call    wcscmp_0
0x180007c69  lea     r9d, [rbp+1]
0x180007c6d  lea     r11d, [rbp+8]
0x180007c71  test    eax, eax
0x180007c73  jnz     short loc_180007C89
0x180007c75  mov     [r15+20h], ebp
0x180007c79  movzx   esi, word ptr [r14]
0x180007c7d  jmp     short loc_180007C89
0x180007c7f  mov     r9d, 2
0x180007c85  lea     r11d, [r9+7]
0x180007c89  add     r14, r9
0x180007c8c  movzx   eax, si
0x180007c8f  lea     ebx, [rbx+rbx*4]
0x180007c92  lea     ebx, [rbx-18h]
0x180007c95  movzx   esi, word ptr [r14]
0x180007c99  lea     ebx, [rax+rbx*2]
0x180007c9c  cmp     si, 30h ; '0'
0x180007ca0  jb      short loc_180007CA8
0x180007ca2  cmp     si, 39h ; '9'
0x180007ca6  jbe     short loc_180007C89
0x180007ca8  cmp     si, 23h ; '#'
0x180007cac  jnz     loc_180007D68
0x180007cb2  cmp     ebx, r11d
0x180007cb5  lea     rcx, [rsp+0B8h+Buffer]; unsigned __int16 *
0x180007cba  cmova   ebx, r11d
0x180007cbe  xor     esi, esi
0x180007cc0  test    ebx, ebx
0x180007cc2  cmovz   ebx, r9d
0x180007cc6  lea     edx, [rsi+0Ah]; unsigned __int64
0x180007cc9  test    ebp, ebp
0x180007ccb  jz      short loc_180007CF2
0x180007ccd  lea     rax, aD_0; "d"
0x180007cd4  mov     [rsp+0B8h+var_90], rax
0x180007cd9  lea     r9, a0_0; "%0"
0x180007ce0  lea     r8, aSDS; "%s%d%s"
0x180007ce7  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180007ceb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007cf0  jmp     short loc_180007CFE
0x180007cf2  lea     r8, aD; "%d"
0x180007cf9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007cfe  mov     r10d, 0Ah
0x180007d04  mov     ecx, r10d
0x180007d07  cmp     ebx, 1
0x180007d0a  jbe     short loc_180007D1A
0x180007d0c  lea     edx, [rbx-1]
0x180007d0f  lea     ecx, [rcx+rcx*4]
0x180007d12  add     ecx, ecx
0x180007d14  sub     rdx, 1
0x180007d18  jnz     short loc_180007D0F
0x180007d1a  mov     edx, [r15+20h]
0x180007d1e  cmp     edx, ecx
0x180007d20  jb      short loc_180007D40
0x180007d22  cmp     [r15+24h], esi
0x180007d26  jnz     short loc_180007D3C
0x180007d28  mov     eax, 2
0x180007d2d  jmp     loc_180007F3F
0x180007d32  mov     eax, 0CCCCCCCDh
0x180007d37  mul     edx
0x180007d39  shr     edx, 3
0x180007d3c  cmp     edx, ecx
0x180007d3e  ja      short loc_180007D32
0x180007d40  mov     r9d, edx
0x180007d43  lea     r8, [rsp+0B8h+Buffer]; unsigned __int16 *
0x180007d48  mov     rdx, r10; unsigned __int64
0x180007d4b  lea     rcx, [rsp+0B8h+var_78]; Buffer
0x180007d50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d55  mov     r9d, 2
0x180007d5b  lea     rdi, [rsp+0B8h+var_78]
0x180007d60  mov     eax, r9d
0x180007d63  jmp     loc_180007ECF
0x180007d68  mov     r8d, 5; nChar
0x180007d6e  lea     rdx, psz2; "First"
0x180007d75  mov     rcx, r14; psz1
0x180007d78  call    cs:__imp_StrCmpNIW
0x180007d7e  xor     esi, esi
0x180007d80  test    eax, eax
0x180007d82  jnz     short loc_180007DCD
0x180007d84  mov     rdi, [r15+8]
0x180007d88  lea     r10d, [rsi+3Fh]
0x180007d8c  cmp     ebx, r10d
0x180007d8f  cmova   ebx, r10d
0x180007d93  test    ebx, ebx
0x180007d95  cmovz   ebx, r10d
0x180007d99  test    rdi, rdi
0x180007d9c  jz      short loc_180007DA3
0x180007d9e  cmp     [rdi], si
0x180007da1  jnz     short loc_180007DC3
0x180007da3  test    r13d, r13d
0x180007da6  jnz     short loc_180007DC3
0x180007da8  mov     rdi, [r15]
0x180007dab  test    rdi, rdi
0x180007dae  jz      loc_180007F72
0x180007db4  cmp     [rdi], si
0x180007db7  jz      loc_180007F72
0x180007dbd  mov     r13d, 1
0x180007dc3  mov     eax, 0Ah
0x180007dc8  jmp     loc_180007EC9
0x180007dcd  mov     r8d, 4; nChar
0x180007dd3  lea     rdx, aLast; "Last"
0x180007dda  mov     rcx, r14; psz1
0x180007ddd  call    cs:__imp_StrCmpNIW
0x180007de3  test    eax, eax
0x180007de5  jnz     short loc_180007E30
0x180007de7  mov     rdi, [r15+10h]
0x180007deb  lea     r10d, [rax+3Fh]
0x180007def  cmp     ebx, r10d
0x180007df2  cmova   ebx, r10d
0x180007df6  test    ebx, ebx
0x180007df8  cmovz   ebx, r10d
0x180007dfc  test    rdi, rdi
0x180007dff  jz      short loc_180007E06
0x180007e01  cmp     [rdi], si
0x180007e04  jnz     short loc_180007E26
0x180007e06  test    r13d, r13d
0x180007e09  jnz     short loc_180007E26
0x180007e0b  mov     rdi, [r15]
0x180007e0e  test    rdi, rdi
0x180007e11  jz      loc_180007F72
0x180007e17  cmp     [rdi], si
0x180007e1a  jz      loc_180007F72
0x180007e20  mov     r13d, 1
0x180007e26  mov     eax, 8
0x180007e2b  jmp     loc_180007EC9
0x180007e30  mov     r8d, 8; nChar
0x180007e36  lea     rdx, aUsername; "Username"
0x180007e3d  mov     rcx, r14; psz1
0x180007e40  call    cs:__imp_StrCmpNIW
0x180007e46  test    eax, eax
0x180007e48  jnz     short loc_180007E80
0x180007e4a  lea     r10d, [rax+3Fh]
0x180007e4e  cmp     ebx, r10d
0x180007e51  cmova   ebx, r10d
0x180007e55  test    ebx, ebx
0x180007e57  cmovz   ebx, r10d
0x180007e5b  test    r13d, r13d
0x180007e5e  jnz     short loc_180007E79
0x180007e60  mov     rdi, [r15]
0x180007e63  test    rdi, rdi
0x180007e66  jz      loc_180007F72
0x180007e6c  cmp     [rdi], si
0x180007e6f  jz      loc_180007F72
0x180007e75  lea     r13d, [rax+1]
0x180007e79  mov     eax, 10h
0x180007e7e  jmp     short loc_180007EC9
0x180007e80  mov     r8d, 3; nChar
0x180007e86  lea     rdx, aMac; "MAC"
0x180007e8d  mov     rcx, r14; psz1
0x180007e90  call    cs:__imp_StrCmpNIW
0x180007e96  test    eax, eax
0x180007e98  jnz     loc_180007F79
0x180007e9e  mov     rdi, [r15+18h]
0x180007ea2  lea     r10d, [rax+0Ch]
0x180007ea6  cmp     ebx, r10d
0x180007ea9  cmova   ebx, r10d
0x180007ead  test    ebx, ebx
0x180007eaf  cmovz   ebx, r10d
0x180007eb3  test    rdi, rdi
0x180007eb6  jz      loc_180007F72
0x180007ebc  cmp     [rdi], si
0x180007ebf  jz      loc_180007F72
0x180007ec5  lea     eax, [r10-6]
0x180007ec9  mov     r9d, 2
0x180007ecf  mov     ecx, [rsp+0B8h+var_88]
0x180007ed3  add     r14, rax
0x180007ed6  mov     edx, [rsp+0B8h+var_84]
0x180007eda  mov     r11d, 9
0x180007ee0  mov     r8, [rsp+0B8h+var_80]
0x180007ee5  jmp     short loc_180007EFB
0x180007ee7  mov     ebx, 1
0x180007eec  mov     [rsp+0B8h+var_78], ax
0x180007ef1  mov     [rsp+0B8h+var_76], si
0x180007ef6  lea     rdi, [rsp+0B8h+var_78]
0x180007efb  add     edx, ebx
0x180007efd  mov     [rsp+0B8h+var_84], edx
0x180007f01  test    ebx, ebx
0x180007f03  jz      short loc_180007F2B
0x180007f05  mov     rax, rdi
0x180007f08  sub     rax, r12
0x180007f0b  movzx   ecx, word ptr [rax+r12]
0x180007f10  test    cx, cx
0x180007f13  jz      short loc_180007F27
0x180007f15  cmp     r12, r8
0x180007f18  jnb     short loc_180007F67
0x180007f1a  mov     [r12], cx
0x180007f1f  add     r12, r9
0x180007f22  add     ebx, 0FFFFFFFFh
0x180007f25  jnz     short loc_180007F0B
0x180007f27  mov     ecx, [rsp+0B8h+var_88]
0x180007f2b  movzx   eax, word ptr [r14]
0x180007f2f  test    ax, ax
0x180007f32  jnz     loc_180007C04
0x180007f38  mov     [r12], si
0x180007f3d  mov     eax, ecx
0x180007f3f  mov     rcx, [rsp+0B8h+var_48]
0x180007f44  xor     rcx, rsp; StackCookie
0x180007f47  call    __security_check_cookie
0x180007f4c  mov     rbx, [rsp+0B8h+arg_18]
0x180007f54  add     rsp, 80h
0x180007f5b  pop     r15
0x180007f5d  pop     r14
0x180007f5f  pop     r13
0x180007f61  pop     r12
0x180007f63  pop     rdi
0x180007f64  pop     rsi
0x180007f65  pop     rbp
0x180007f66  retn
0x180007f67  mov     ecx, 4
0x180007f6c  mov     [rsp+0B8h+var_88], ecx
0x180007f70  jmp     short loc_180007F2B
0x180007f72  mov     eax, 3
0x180007f77  jmp     short loc_180007F3F
0x180007f79  mov     eax, 1
0x180007f7e  jmp     short loc_180007F3F
```
