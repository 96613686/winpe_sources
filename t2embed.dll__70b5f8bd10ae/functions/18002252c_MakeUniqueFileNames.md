# MakeUniqueFileNames

- ea: `0x18002252c`
- end: `0x180022769`
- name: `MakeUniqueFileNames`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001a1a4`

## callees

- `0x18001ba0c`
- `0x18001e698`
- `0x18001f3e4`
- `0x18001f440`
- `0x180021ffc`
- `0x18002218c`
- `0x18002252c`
- `0x18002a590`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180022667`
- `msvcrt!_itoa_s` at `0x180022667`
- `msvcrt!isalnum` at `0x1800225bb`
- `msvcrt!isalnum` at `0x1800225bb`
- `KERNEL32!GetTempPath2A` at `0x1800226e1`
- `KERNEL32!GetTempPath2A` at `0x1800226e1`
- `KERNEL32!IsDBCSLeadByte` at `0x180022588`
- `KERNEL32!IsDBCSLeadByte` at `0x180022588`
- `KERNEL32!GetTickCount` at `0x18002264e`
- `KERNEL32!GetTickCount` at `0x18002264e`

## pseudocode

```c
__int64 __fastcall MakeUniqueFileNames(__int64 a1, const CHAR *a2, const CHAR *a3, int a4, int a5)
{
  unsigned __int16 v8; // si
  unsigned __int16 v9; // bx
  int v10; // edi
  __int64 v11; // r14
  BYTE v12; // cl
  __int64 v13; // rcx
  char v14; // al
  __int64 v15; // rcx
  unsigned __int16 v16; // bx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int16 v19; // bx
  __int64 result; // rax
  DWORD TickCount; // eax
  const char *v22; // r8
  const char *v23; // r8
  size_t pcchLength; // [rsp+20h] [rbp-E0h] BYREF
  char pszDest[8]; // [rsp+28h] [rbp-D8h] BYREF
  char Buffer[32]; // [rsp+30h] [rbp-D0h] BYREF
  char v27[272]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a4 && !a5 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 1;
    while ( 1 )
    {
      v11 = v8;
      v12 = *(_BYTE *)(v8 + a1);
      if ( !v12 )
      {
LABEL_12:
        if ( v9 >= 8uLL )
          goto LABEL_16;
        pszDest[v9] = 120;
        v16 = v9 + 1;
        v17 = v16++;
        pszDest[v17] = 120;
        v18 = v16;
        v19 = v16 + 1;
        pszDest[v18] = 120;
        if ( v19 >= 8uLL )
LABEL_16:
          _report_rangecheckfailure();
        pszDest[v19] = 0;
        if ( !(unsigned int)GetDirectory(v27) )
          return 515;
LABEL_22:
        v22 = "ttf";
        if ( !v10 )
          v22 = "tmf";
        result = GetUniqueFileName(v27, pszDest, v22, a2);
        if ( !(_DWORD)result )
        {
          v23 = "fot";
          if ( !v10 )
            v23 = "tmt";
          return GetUniqueFileName(v27, pszDest, v23, a3);
        }
        return result;
      }
      if ( IsDBCSLeadByte(v12) )
        break;
      if ( isalnum(*(unsigned __int8 *)(v8 + a1)) )
      {
        v14 = *(_BYTE *)(v8 + a1);
LABEL_10:
        v15 = v9++;
        pszDest[v15] = v14;
      }
      ++v8;
      if ( v9 >= 4u )
        goto LABEL_12;
    }
    if ( (unsigned int)v9 + 1 >= 4 )
      goto LABEL_12;
    v13 = v9++;
    ++v8;
    pszDest[v13] = *(_BYTE *)(v11 + a1);
    v14 = *(_BYTE *)(v8 + a1);
    goto LABEL_10;
  }
  memset(Buffer, 0, 30);
  pcchLength = 0;
  TickCount = GetTickCount();
  _itoa_s(TickCount, Buffer, 0x1Eu, 16);
  if ( StringCchLengthA(Buffer, 0x1Eu, &pcchLength) >= 0
    && StringCchCopyA(pszDest, 8u, "tp") >= 0
    && StringCchCatA(pszDest, 8u, &pszDest[pcchLength + 6]) >= 0
    && StringCchCatA(pszDest, 8u, "xxx") >= 0 )
  {
    v10 = 0;
    if ( (unsigned int)GetTempPath2A(260, v27) )
      goto LABEL_22;
  }
  return 513;
}

```

## disassembly

```asm
0x18002252c  mov     [rsp-8+arg_18], rbx
0x180022531  push    rbp
0x180022532  push    rsi
0x180022533  push    rdi
0x180022534  push    r12
0x180022536  push    r13
0x180022538  push    r14
0x18002253a  push    r15
0x18002253c  lea     rbp, [rsp-70h]
0x180022541  sub     rsp, 170h
0x180022548  mov     rax, cs:__security_cookie
0x18002254f  xor     rax, rsp
0x180022552  mov     [rbp+0A0h+var_40], rax
0x180022556  mov     r13, r8
0x180022559  mov     r12, rdx
0x18002255c  mov     r15, rcx
0x18002255f  test    r9d, r9d
0x180022562  jz      loc_18002263A
0x180022568  cmp     [rbp+0A0h+arg_20], 0
0x18002256f  jnz     loc_18002263A
0x180022575  xor     esi, esi
0x180022577  xor     ebx, ebx
0x180022579  lea     edi, [rsi+1]
0x18002257c  movzx   r14d, si
0x180022580  mov     cl, [r14+r15]; TestChar
0x180022584  test    cl, cl
0x180022586  jz      short loc_1800225E0
0x180022588  call    cs:__imp_IsDBCSLeadByte
0x18002258e  test    eax, eax
0x180022590  jz      short loc_1800225B6
0x180022592  movzx   eax, bx
0x180022595  add     eax, edi
0x180022597  cmp     eax, 4
0x18002259a  jnb     short loc_1800225E0
0x18002259c  mov     al, [r14+r15]
0x1800225a0  movzx   ecx, bx
0x1800225a3  add     bx, di
0x1800225a6  add     si, di
0x1800225a9  mov     [rsp+rcx+1A0h+pszDest], al
0x1800225ad  movzx   eax, si
0x1800225b0  mov     al, [rax+r15]
0x1800225b4  jmp     short loc_1800225C9
0x1800225b6  movzx   ecx, byte ptr [r14+r15]; C
0x1800225bb  call    cs:__imp_isalnum
0x1800225c1  test    eax, eax
0x1800225c3  jz      short loc_1800225D3
0x1800225c5  mov     al, [r14+r15]
0x1800225c9  movzx   ecx, bx
0x1800225cc  add     bx, di
0x1800225cf  mov     [rsp+rcx+1A0h+pszDest], al
0x1800225d3  add     si, di
0x1800225d6  mov     eax, 4
0x1800225db  cmp     bx, ax
0x1800225de  jb      short loc_18002257C
0x1800225e0  movzx   eax, bx
0x1800225e3  mov     esi, 8
0x1800225e8  cmp     rax, rsi
0x1800225eb  jnb     short loc_180022634
0x1800225ed  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x1800225f2  add     bx, di
0x1800225f5  movzx   eax, bx
0x1800225f8  add     bx, di
0x1800225fb  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x180022600  movzx   eax, bx
0x180022603  add     bx, di
0x180022606  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x18002260b  movzx   eax, bx
0x18002260e  cmp     rax, rsi
0x180022611  jnb     short loc_180022634
0x180022613  lea     rcx, [rsp+1A0h+var_150]; pszDest
0x180022618  mov     [rsp+rax+1A0h+pszDest], 0
0x18002261d  call    GetDirectory
0x180022622  test    eax, eax
0x180022624  jnz     loc_1800226EB
0x18002262a  mov     eax, 203h
0x18002262f  jmp     loc_180022742
0x180022634  call    __report_rangecheckfailure
0x18002263a  xorps   xmm0, xmm0
0x18002263d  xor     eax, eax
0x18002263f  movups  xmmword ptr [rsp+1A0h+Buffer], xmm0
0x180022644  mov     [rsp+1A0h+pcchLength], rax
0x180022649  movups  xmmword ptr [rsp+1A0h+Buffer+0Eh], xmm0
0x18002264e  call    cs:__imp_GetTickCount
0x180022654  mov     ebx, 1Eh
0x180022659  lea     rdx, [rsp+1A0h+Buffer]; Buffer
0x18002265e  mov     r8d, ebx; BufferCount
0x180022661  mov     ecx, eax; Value
0x180022663  lea     r9d, [rbx-0Eh]; Radix
0x180022667  call    cs:__imp__itoa_s
0x18002266d  lea     r8, [rsp+1A0h+pcchLength]; pcchLength
0x180022672  mov     edx, ebx; cchMax
0x180022674  lea     rcx, [rsp+1A0h+Buffer]; psz
0x180022679  call    StringCchLengthA
0x18002267e  test    eax, eax
0x180022680  js      loc_18002273D
0x180022686  lea     esi, [rbx-16h]
0x180022689  mov     edx, esi; cchDest
0x18002268b  lea     r8, aTp; "tp"
0x180022692  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x180022697  call    StringCchCopyA
0x18002269c  test    eax, eax
0x18002269e  js      loc_18002273D
0x1800226a4  mov     rax, [rsp+1A0h+pcchLength]
0x1800226a9  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x1800226ae  mov     edx, esi; cchDest
0x1800226b0  lea     r8, [rsp+rax+1A0h+pszSrc]; pszSrc
0x1800226b5  call    StringCchCatA
0x1800226ba  test    eax, eax
0x1800226bc  js      short loc_18002273D
0x1800226be  lea     r8, aXxx; "xxx"
0x1800226c5  mov     edx, esi; cchDest
0x1800226c7  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x1800226cc  call    StringCchCatA
0x1800226d1  test    eax, eax
0x1800226d3  js      short loc_18002273D
0x1800226d5  lea     rdx, [rsp+1A0h+var_150]
0x1800226da  mov     ecx, 104h
0x1800226df  xor     edi, edi
0x1800226e1  call    cs:__imp_GetTempPath2A
0x1800226e7  test    eax, eax
0x1800226e9  jz      short loc_18002273D
0x1800226eb  lea     rax, aTmf; "tmf"
0x1800226f2  test    edi, edi
0x1800226f4  lea     r8, aTtf; "ttf"
0x1800226fb  mov     r9, r12; lpFileName
0x1800226fe  cmovz   r8, rax; STRSAFE_LPCSTR
0x180022702  lea     rdx, [rsp+1A0h+pszDest]; STRSAFE_LPCSTR
0x180022707  lea     rcx, [rsp+1A0h+var_150]; pszSrc
0x18002270c  call    GetUniqueFileName
0x180022711  test    eax, eax
0x180022713  jnz     short loc_180022742
0x180022715  test    edi, edi
0x180022717  lea     rax, aTmt; "tmt"
0x18002271e  lea     r8, aFot; "fot"
0x180022725  mov     r9, r13; lpFileName
0x180022728  cmovz   r8, rax; STRSAFE_LPCSTR
0x18002272c  lea     rdx, [rsp+1A0h+pszDest]; STRSAFE_LPCSTR
0x180022731  lea     rcx, [rsp+1A0h+var_150]; pszSrc
0x180022736  call    GetUniqueFileName
0x18002273b  jmp     short loc_180022742
0x18002273d  mov     eax, 201h
0x180022742  mov     rcx, [rbp+0A0h+var_40]
0x180022746  xor     rcx, rsp; StackCookie
0x180022749  call    __security_check_cookie
0x18002274e  mov     rbx, [rsp+1A0h+arg_18]
0x180022756  add     rsp, 170h
0x18002275d  pop     r15
0x18002275f  pop     r14
0x180022761  pop     r13
0x180022763  pop     r12
0x180022765  pop     rdi
0x180022766  pop     rsi
0x180022767  pop     rbp
0x180022768  retn
```
