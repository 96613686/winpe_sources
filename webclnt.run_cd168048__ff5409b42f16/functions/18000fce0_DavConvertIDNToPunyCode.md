# DavConvertIDNToPunyCode

- ea: `0x18000fce0`
- end: `0x18001001f`
- name: `DavConvertIDNToPunyCode`
- size: `831`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180007e10`
- `0x18000a770`
- `0x180010028`
- `0x180010478`
- `0x180012e2c`
- `0x180013054`
- `0x180021f00`

## callees

- `0x18000b5f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000b99c`
- `0x18000ba14`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fedc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ffec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ffec`
- `KERNEL32!LocalFree` at `0x18000ffff`
- `KERNEL32!LocalFree` at `0x18000ffff`
- `KERNEL32!LocalAlloc` at `0x18000fde8`
- `KERNEL32!LocalAlloc` at `0x18000fde8`
- `KERNEL32!IdnToAscii` at `0x18000fd7b`
- `KERNEL32!IdnToAscii` at `0x18000feab`
- `KERNEL32!IdnToAscii` at `0x18000fd7b`
- `KERNEL32!IdnToAscii` at `0x18000feab`

## pseudocode

```c
__int64 __fastcall DavConvertIDNToPunyCode(WCHAR *hMem, WCHAR *a2, unsigned int a3)
{
  unsigned int v3; // edi
  __int64 v6; // rbx
  const wchar_t *v7; // r12
  int v8; // r13d
  __int64 v9; // rbp
  WCHAR *v10; // r15
  __int64 v11; // rbx
  char v12; // al
  int v13; // edx
  __int64 v14; // rbx
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edi
  DWORD v19; // ecx

  v3 = 0;
  if ( hMem )
  {
    LODWORD(v6) = 0;
    if ( *hMem )
    {
      while ( 1 )
      {
        v7 = &hMem[(unsigned int)v6];
        if ( *v7 == 64 )
          break;
        v6 = (unsigned int)(v6 + 1);
        if ( !hMem[v6] )
          goto LABEL_9;
      }
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v6 + 2));
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          WPP_SF_d(v14, 0x14u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
        }
        return v3;
      }
      v8 = 1;
      LODWORD(v16) = 0;
      if ( *hMem != 64 )
      {
        do
        {
          v17 = (unsigned int)v16;
          v16 = (unsigned int)(v16 + 1);
          v10[v17] = hMem[v17];
        }
        while ( hMem[v16] != 64 );
      }
      v10[(unsigned int)v16] = 0;
    }
    else
    {
LABEL_9:
      v8 = 0;
      v7 = 0;
      LODWORD(v9) = 0;
      v10 = hMem;
    }
    v3 = IdnToAscii(2u, v10, v6, 0, 0);
    if ( !v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = GetLastError();
        v13 = 21;
LABEL_14:
        WPP_SF_Sd(v11, v13, (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, (_DWORD)v10, v12);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    if ( v3 == (_DWORD)v6 )
    {
      v3 = 0;
    }
    else
    {
      v18 = v9 + v3;
      if ( a3 < v18 + 1 || !a2 )
      {
        v3 = v18 + 2;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
            (_DWORD)hMem,
            v3);
        v19 = 122;
        goto LABEL_51;
      }
      v3 = IdnToAscii(2u, v10, v6, a2, a3);
      if ( !v3 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v12 = GetLastError();
          v13 = 22;
          goto LABEL_14;
        }
LABEL_52:
        if ( !v8 )
          return v3;
LABEL_53:
        LocalFree(v10);
        return v3;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          (_DWORD)v10,
          (__int64)a2);
      if ( v8 && v7 )
      {
        if ( StringCchCatW(a2, a3, v7) < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0x18u,
              (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
          SetLastError(0x54Fu);
          v3 = 0;
          goto LABEL_53;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0x19u,
            (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
            a2);
        v3 += v9;
      }
    }
    v19 = 0;
LABEL_51:
    SetLastError(v19);
    goto LABEL_52;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x13u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000fce0  mov     rax, rsp
0x18000fce3  mov     [rax+8], rbx
0x18000fce7  mov     [rax+20h], rbp
0x18000fceb  mov     [rax+18h], r8d
0x18000fcef  mov     [rax+10h], rdx
0x18000fcf3  push    rdi
0x18000fcf4  push    r12
0x18000fcf6  push    r13
0x18000fcf8  push    r14
0x18000fcfa  push    r15
0x18000fcfc  sub     rsp, 30h
0x18000fd00  xor     edi, edi
0x18000fd02  mov     r14, rcx
0x18000fd05  test    rcx, rcx
0x18000fd08  jnz     short loc_18000FD3D
0x18000fd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd11  lea     rbx, WPP_GLOBAL_Control
0x18000fd18  cmp     rcx, rbx
0x18000fd1b  jz      short loc_18000FD36
0x18000fd1d  test    byte ptr [rcx+1Ch], 1
0x18000fd21  jz      short loc_18000FD36
0x18000fd23  mov     rcx, [rcx+10h]
0x18000fd27  lea     edx, [rdi+13h]
0x18000fd2a  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000fd31  call    WPP_SF_
0x18000fd36  xor     eax, eax
0x18000fd38  jmp     loc_180010007
0x18000fd3d  mov     ebx, edi
0x18000fd3f  cmp     [rcx], di
0x18000fd42  jz      short loc_18000FD5F
0x18000fd44  mov     ecx, 40h ; '@'; uFlags
0x18000fd49  mov     eax, ebx
0x18000fd4b  lea     r12, [r14+rax*2]
0x18000fd4f  cmp     [r12], cx
0x18000fd54  jz      short loc_18000FDD4
0x18000fd56  inc     ebx
0x18000fd58  cmp     [r14+rbx*2], di
0x18000fd5d  jnz     short loc_18000FD49
0x18000fd5f  mov     r13d, edi
0x18000fd62  mov     r12, rdi
0x18000fd65  mov     ebp, edi
0x18000fd67  mov     r15, r14
0x18000fd6a  xor     r9d, r9d; lpASCIICharStr
0x18000fd6d  mov     [rsp+58h+cchASCIIChar], edi; cchASCIIChar
0x18000fd71  mov     r8d, ebx; cchUnicodeChar
0x18000fd74  mov     rdx, r15; lpUnicodeCharStr
0x18000fd77  lea     ecx, [r9+2]; dwFlags
0x18000fd7b  call    cs:__imp_IdnToAscii
0x18000fd81  mov     edi, eax
0x18000fd83  test    eax, eax
0x18000fd85  jnz     loc_18000FE6F
0x18000fd8b  mov     rax, cs:WPP_GLOBAL_Control
0x18000fd92  lea     rbx, WPP_GLOBAL_Control
0x18000fd99  cmp     rax, rbx
0x18000fd9c  jz      loc_18000FFF2
0x18000fda2  test    byte ptr [rax+1Ch], 1
0x18000fda6  jz      loc_18000FFF2
0x18000fdac  mov     rbx, [rax+10h]
0x18000fdb0  call    cs:__imp_GetLastError
0x18000fdb6  lea     edx, [rdi+15h]
0x18000fdb9  mov     r9, r15
0x18000fdbc  mov     [rsp+58h+cchASCIIChar], eax
0x18000fdc0  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000fdc7  mov     rcx, rbx
0x18000fdca  call    WPP_SF_Sd
0x18000fdcf  jmp     loc_18000FFF2
0x18000fdd4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000fdd8  inc     rbp
0x18000fddb  cmp     [r12+rbp*2], di
0x18000fde0  jnz     short loc_18000FDD8
0x18000fde2  lea     edx, [rbx+2]
0x18000fde5  add     rdx, rdx; uBytes
0x18000fde8  call    cs:__imp_LocalAlloc
0x18000fdee  mov     r15, rax
0x18000fdf1  test    rax, rax
0x18000fdf4  jnz     short loc_18000FE3C
0x18000fdf6  mov     rax, cs:WPP_GLOBAL_Control
0x18000fdfd  lea     rbx, WPP_GLOBAL_Control
0x18000fe04  cmp     rax, rbx
0x18000fe07  jz      loc_180010005
0x18000fe0d  test    byte ptr [rax+1Ch], 1
0x18000fe11  jz      loc_180010005
0x18000fe17  mov     rbx, [rax+10h]
0x18000fe1b  call    cs:__imp_GetLastError
0x18000fe21  lea     edx, [r15+14h]
0x18000fe25  mov     rcx, rbx
0x18000fe28  mov     r9d, eax
0x18000fe2b  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000fe32  call    WPP_SF_d
0x18000fe37  jmp     loc_180010005
0x18000fe3c  mov     r13d, 1
0x18000fe42  mov     edx, edi
0x18000fe44  lea     r8d, [r13+3Fh]
0x18000fe48  cmp     [r14], r8w
0x18000fe4c  jz      short loc_18000FE63
0x18000fe4e  mov     ecx, edx
0x18000fe50  inc     edx
0x18000fe52  movzx   eax, word ptr [r14+rcx*2]
0x18000fe57  mov     [r15+rcx*2], ax
0x18000fe5c  cmp     [r14+rdx*2], r8w
0x18000fe61  jnz     short loc_18000FE4E
0x18000fe63  mov     ecx, edx
0x18000fe65  mov     [r15+rcx*2], di
0x18000fe6a  jmp     loc_18000FD6A
0x18000fe6f  cmp     edi, ebx
0x18000fe71  jz      loc_18000FFE8
0x18000fe77  mov     ecx, dword ptr [rsp+58h+cchDest]
0x18000fe7b  add     edi, ebp
0x18000fe7d  lea     eax, [rdi+1]
0x18000fe80  cmp     ecx, eax
0x18000fe82  jb      loc_18000FFA9
0x18000fe88  cmp     [rsp+58h+lpASCIICharStr], 0
0x18000fe8e  jz      loc_18000FFA9
0x18000fe94  mov     r14, [rsp+58h+lpASCIICharStr]
0x18000fe99  mov     r8d, ebx; cchUnicodeChar
0x18000fe9c  mov     [rsp+58h+cchASCIIChar], ecx; cchASCIIChar
0x18000fea0  mov     r9, r14; lpASCIICharStr
0x18000fea3  mov     rdx, r15; lpUnicodeCharStr
0x18000fea6  mov     ecx, 2; dwFlags
0x18000feab  call    cs:__imp_IdnToAscii
0x18000feb1  mov     edi, eax
0x18000feb3  test    eax, eax
0x18000feb5  jnz     short loc_18000FEEA
0x18000feb7  mov     rax, cs:WPP_GLOBAL_Control
0x18000febe  lea     rbx, WPP_GLOBAL_Control
0x18000fec5  cmp     rax, rbx
0x18000fec8  jz      loc_18000FFF2
0x18000fece  test    byte ptr [rax+1Ch], 1
0x18000fed2  jz      loc_18000FFF2
0x18000fed8  mov     rbx, [rax+10h]
0x18000fedc  call    cs:__imp_GetLastError
0x18000fee2  lea     edx, [rdi+16h]
0x18000fee5  jmp     loc_18000FDB9
0x18000feea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fef1  lea     rbx, WPP_GLOBAL_Control
0x18000fef8  cmp     rcx, rbx
0x18000fefb  jz      short loc_18000FF20
0x18000fefd  test    byte ptr [rcx+1Ch], 2
0x18000ff01  jz      short loc_18000FF20
0x18000ff03  mov     rcx, [rcx+10h]
0x18000ff07  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000ff0e  mov     edx, 17h
0x18000ff13  mov     qword ptr [rsp+58h+cchASCIIChar], r14
0x18000ff18  mov     r9, r15
0x18000ff1b  call    WPP_SF_SS
0x18000ff20  test    r13d, r13d
0x18000ff23  jz      loc_18000FFEA
0x18000ff29  test    r12, r12
0x18000ff2c  jz      loc_18000FFEA
0x18000ff32  mov     edx, dword ptr [rsp+58h+cchDest]; cchDest
0x18000ff36  mov     r8, r12; pszSrc
0x18000ff39  mov     rcx, r14; pszDest
0x18000ff3c  call    StringCchCatW
0x18000ff41  test    eax, eax
0x18000ff43  jns     short loc_18000FF7B
0x18000ff45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff4c  cmp     rcx, rbx
0x18000ff4f  jz      short loc_18000FF6C
0x18000ff51  test    byte ptr [rcx+1Ch], 1
0x18000ff55  jz      short loc_18000FF6C
0x18000ff57  mov     rcx, [rcx+10h]
0x18000ff5b  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000ff62  mov     edx, 18h
0x18000ff67  call    WPP_SF_
0x18000ff6c  mov     ecx, 54Fh; dwErrCode
0x18000ff71  call    cs:__imp_SetLastError
0x18000ff77  xor     edi, edi
0x18000ff79  jmp     short loc_18000FFF7
0x18000ff7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff82  cmp     rcx, rbx
0x18000ff85  jz      short loc_18000FFA5
0x18000ff87  test    byte ptr [rcx+1Ch], 2
0x18000ff8b  jz      short loc_18000FFA5
0x18000ff8d  mov     rcx, [rcx+10h]
0x18000ff91  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000ff98  mov     edx, 19h
0x18000ff9d  mov     r9, r14
0x18000ffa0  call    WPP_SF_S
0x18000ffa5  add     edi, ebp
0x18000ffa7  jmp     short loc_18000FFEA
0x18000ffa9  add     edi, 2
0x18000ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffb3  lea     rbx, WPP_GLOBAL_Control
0x18000ffba  cmp     rcx, rbx
0x18000ffbd  jz      short loc_18000FFE1
0x18000ffbf  test    byte ptr [rcx+1Ch], 2
0x18000ffc3  jz      short loc_18000FFE1
0x18000ffc5  mov     rcx, [rcx+10h]
0x18000ffc9  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18000ffd0  mov     edx, 1Ah
0x18000ffd5  mov     [rsp+58h+cchASCIIChar], edi
0x18000ffd9  mov     r9, r14
0x18000ffdc  call    WPP_SF_Sd
0x18000ffe1  mov     ecx, 7Ah ; 'z'
0x18000ffe6  jmp     short loc_18000FFEC
0x18000ffe8  xor     edi, edi
0x18000ffea  xor     ecx, ecx; dwErrCode
0x18000ffec  call    cs:__imp_SetLastError
0x18000fff2  test    r13d, r13d
0x18000fff5  jz      short loc_180010005
0x18000fff7  test    r15, r15
0x18000fffa  jz      short loc_180010005
0x18000fffc  mov     rcx, r15; hMem
0x18000ffff  call    cs:__imp_LocalFree
0x180010005  mov     eax, edi
0x180010007  mov     rbx, [rsp+58h+arg_0]
0x18001000c  mov     rbp, [rsp+58h+arg_18]
0x180010011  add     rsp, 30h
0x180010015  pop     r15
0x180010017  pop     r14
0x180010019  pop     r13
0x18001001b  pop     r12
0x18001001d  pop     rdi
0x18001001e  retn
```
