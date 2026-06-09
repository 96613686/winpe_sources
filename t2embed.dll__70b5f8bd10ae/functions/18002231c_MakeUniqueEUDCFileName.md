# MakeUniqueEUDCFileName

- ea: `0x18002231c`
- end: `0x180022524`
- name: `MakeUniqueEUDCFileName`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180022de8`

## callees

- `0x18001ba0c`
- `0x18001e698`
- `0x18001f3e4`
- `0x18001f440`
- `0x180021ffc`
- `0x18002218c`
- `0x18002231c`
- `0x18002a590`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180022450`
- `msvcrt!_itoa_s` at `0x180022450`
- `msvcrt!isalnum` at `0x1800223a8`
- `msvcrt!isalnum` at `0x1800223a8`
- `KERNEL32!GetTempPath2A` at `0x1800224c6`
- `KERNEL32!GetTempPath2A` at `0x1800224c6`
- `KERNEL32!IsDBCSLeadByte` at `0x180022375`
- `KERNEL32!IsDBCSLeadByte` at `0x180022375`
- `KERNEL32!GetTickCount` at `0x180022437`
- `KERNEL32!GetTickCount` at `0x180022437`

## pseudocode

```c
__int64 __fastcall MakeUniqueEUDCFileName(__int64 a1, const CHAR *a2, int a3, int a4)
{
  unsigned __int16 v6; // si
  unsigned __int16 v7; // bx
  int v8; // edi
  __int64 v9; // r14
  BYTE v10; // cl
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // rcx
  unsigned __int16 v14; // bx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 v17; // bx
  DWORD TickCount; // eax
  const char *v20; // r8
  size_t pcchLength; // [rsp+20h] [rbp-E0h] BYREF
  char pszDest[8]; // [rsp+28h] [rbp-D8h] BYREF
  char Buffer[32]; // [rsp+30h] [rbp-D0h] BYREF
  char v24[272]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a3 && !a4 )
  {
    v6 = 0;
    v7 = 0;
    v8 = 1;
    while ( 1 )
    {
      v9 = v6;
      v10 = *(_BYTE *)(v6 + a1);
      if ( !v10 )
      {
LABEL_12:
        if ( v7 >= 8uLL )
          goto LABEL_16;
        pszDest[v7] = 120;
        v14 = v7 + 1;
        v15 = v14++;
        pszDest[v15] = 120;
        v16 = v14;
        v17 = v14 + 1;
        pszDest[v16] = 120;
        if ( v17 >= 8uLL )
LABEL_16:
          _report_rangecheckfailure();
        pszDest[v17] = 0;
        if ( !(unsigned int)GetDirectory(v24) )
          return 515;
LABEL_22:
        v20 = "tte";
        if ( !v8 )
          v20 = "tme";
        return GetUniqueFileName(v24, pszDest, v20, a2);
      }
      if ( IsDBCSLeadByte(v10) )
        break;
      if ( isalnum(*(unsigned __int8 *)(v6 + a1)) )
      {
        v12 = *(_BYTE *)(v6 + a1);
LABEL_10:
        v13 = v7++;
        pszDest[v13] = v12;
      }
      ++v6;
      if ( v7 >= 4u )
        goto LABEL_12;
    }
    if ( (unsigned int)v7 + 1 >= 4 )
      goto LABEL_12;
    v11 = v7++;
    ++v6;
    pszDest[v11] = *(_BYTE *)(v9 + a1);
    v12 = *(_BYTE *)(v6 + a1);
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
    v8 = 0;
    if ( (unsigned int)GetTempPath2A(260, v24) )
      goto LABEL_22;
  }
  return 513;
}

```

## disassembly

```asm
0x18002231c  mov     [rsp-8+arg_10], rbx
0x180022321  push    rbp
0x180022322  push    rsi
0x180022323  push    rdi
0x180022324  push    r12
0x180022326  push    r13
0x180022328  push    r14
0x18002232a  push    r15
0x18002232c  lea     rbp, [rsp-70h]
0x180022331  sub     rsp, 170h
0x180022338  mov     rax, cs:__security_cookie
0x18002233f  xor     rax, rsp
0x180022342  mov     [rbp+0A0h+var_40], rax
0x180022346  mov     r12, rdx
0x180022349  mov     r15, rcx
0x18002234c  test    r8d, r8d
0x18002234f  jz      loc_180022423
0x180022355  test    r9d, r9d
0x180022358  jnz     loc_180022423
0x18002235e  xor     esi, esi
0x180022360  lea     r13d, [r9+4]
0x180022364  xor     ebx, ebx
0x180022366  lea     edi, [rsi+1]
0x180022369  movzx   r14d, si
0x18002236d  mov     cl, [r14+r15]; TestChar
0x180022371  test    cl, cl
0x180022373  jz      short loc_1800223C9
0x180022375  call    cs:__imp_IsDBCSLeadByte
0x18002237b  test    eax, eax
0x18002237d  jz      short loc_1800223A3
0x18002237f  movzx   eax, bx
0x180022382  add     eax, edi
0x180022384  cmp     eax, r13d
0x180022387  jnb     short loc_1800223C9
0x180022389  mov     al, [r14+r15]
0x18002238d  movzx   ecx, bx
0x180022390  add     bx, di
0x180022393  add     si, di
0x180022396  mov     [rsp+rcx+1A0h+pszDest], al
0x18002239a  movzx   eax, si
0x18002239d  mov     al, [rax+r15]
0x1800223a1  jmp     short loc_1800223B6
0x1800223a3  movzx   ecx, byte ptr [r14+r15]; C
0x1800223a8  call    cs:__imp_isalnum
0x1800223ae  test    eax, eax
0x1800223b0  jz      short loc_1800223C0
0x1800223b2  mov     al, [r14+r15]
0x1800223b6  movzx   ecx, bx
0x1800223b9  add     bx, di
0x1800223bc  mov     [rsp+rcx+1A0h+pszDest], al
0x1800223c0  add     si, di
0x1800223c3  cmp     bx, r13w
0x1800223c7  jb      short loc_180022369
0x1800223c9  movzx   eax, bx
0x1800223cc  mov     esi, 8
0x1800223d1  cmp     rax, rsi
0x1800223d4  jnb     short loc_18002241D
0x1800223d6  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x1800223db  add     bx, di
0x1800223de  movzx   eax, bx
0x1800223e1  add     bx, di
0x1800223e4  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x1800223e9  movzx   eax, bx
0x1800223ec  add     bx, di
0x1800223ef  mov     [rsp+rax+1A0h+pszDest], 78h ; 'x'
0x1800223f4  movzx   eax, bx
0x1800223f7  cmp     rax, rsi
0x1800223fa  jnb     short loc_18002241D
0x1800223fc  lea     rcx, [rsp+1A0h+var_150]; pszDest
0x180022401  mov     [rsp+rax+1A0h+pszDest], 0
0x180022406  call    GetDirectory
0x18002240b  test    eax, eax
0x18002240d  jnz     loc_1800224D0
0x180022413  mov     eax, 203h
0x180022418  jmp     loc_1800224FD
0x18002241d  call    __report_rangecheckfailure
0x180022423  xorps   xmm0, xmm0
0x180022426  xor     eax, eax
0x180022428  movups  xmmword ptr [rsp+1A0h+Buffer], xmm0
0x18002242d  mov     [rsp+1A0h+pcchLength], rax
0x180022432  movups  xmmword ptr [rsp+1A0h+Buffer+0Eh], xmm0
0x180022437  call    cs:__imp_GetTickCount
0x18002243d  mov     ebx, 1Eh
0x180022442  lea     rdx, [rsp+1A0h+Buffer]; Buffer
0x180022447  mov     r8d, ebx; BufferCount
0x18002244a  mov     ecx, eax; Value
0x18002244c  lea     r9d, [rbx-0Eh]; Radix
0x180022450  call    cs:__imp__itoa_s
0x180022456  lea     r8, [rsp+1A0h+pcchLength]; pcchLength
0x18002245b  mov     edx, ebx; cchMax
0x18002245d  lea     rcx, [rsp+1A0h+Buffer]; psz
0x180022462  call    StringCchLengthA
0x180022467  test    eax, eax
0x180022469  js      loc_1800224F8
0x18002246f  lea     esi, [rbx-16h]
0x180022472  mov     edx, esi; cchDest
0x180022474  lea     r8, aTp; "tp"
0x18002247b  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x180022480  call    StringCchCopyA
0x180022485  test    eax, eax
0x180022487  js      short loc_1800224F8
0x180022489  mov     rax, [rsp+1A0h+pcchLength]
0x18002248e  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x180022493  mov     edx, esi; cchDest
0x180022495  lea     r8, [rsp+rax+1A0h+pszSrc]; pszSrc
0x18002249a  call    StringCchCatA
0x18002249f  test    eax, eax
0x1800224a1  js      short loc_1800224F8
0x1800224a3  lea     r8, aXxx; "xxx"
0x1800224aa  mov     edx, esi; cchDest
0x1800224ac  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x1800224b1  call    StringCchCatA
0x1800224b6  test    eax, eax
0x1800224b8  js      short loc_1800224F8
0x1800224ba  lea     rdx, [rsp+1A0h+var_150]
0x1800224bf  mov     ecx, 104h
0x1800224c4  xor     edi, edi
0x1800224c6  call    cs:__imp_GetTempPath2A
0x1800224cc  test    eax, eax
0x1800224ce  jz      short loc_1800224F8
0x1800224d0  test    edi, edi
0x1800224d2  lea     rax, aTme; "tme"
0x1800224d9  lea     r8, aTte; "tte"
0x1800224e0  mov     r9, r12; lpFileName
0x1800224e3  cmovz   r8, rax; STRSAFE_LPCSTR
0x1800224e7  lea     rdx, [rsp+1A0h+pszDest]; STRSAFE_LPCSTR
0x1800224ec  lea     rcx, [rsp+1A0h+var_150]; pszSrc
0x1800224f1  call    GetUniqueFileName
0x1800224f6  jmp     short loc_1800224FD
0x1800224f8  mov     eax, 201h
0x1800224fd  mov     rcx, [rbp+0A0h+var_40]
0x180022501  xor     rcx, rsp; StackCookie
0x180022504  call    __security_check_cookie
0x180022509  mov     rbx, [rsp+1A0h+arg_10]
0x180022511  add     rsp, 170h
0x180022518  pop     r15
0x18002251a  pop     r14
0x18002251c  pop     r13
0x18002251e  pop     r12
0x180022520  pop     rdi
0x180022521  pop     rsi
0x180022522  pop     rbp
0x180022523  retn
```
