# ConvertGuidToString

- ea: `0x1400112f0`
- end: `0x140011532`
- name: `ConvertGuidToString`
- size: `578`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14000d8c4`
- `0x14000df30`
- `0x140010448`

## callees

- `0x140003e70`
- `0x140003f64`
- `0x14000402c`
- `0x1400040f4`
- `0x1400050b0`
- `0x1400112f0`
- `0x140011538`

## pseudocode

```c
__int64 __fastcall ConvertGuidToString(__int64 a1, wchar_t *a2, const wchar_t *a3)
{
  int v4; // r8d
  int v5; // r9d
  int v6; // r8d
  int v7; // r9d
  int v8; // r8d
  int v9; // r9d
  int v10; // r8d
  size_t v11; // r9
  unsigned int v12; // ebx
  unsigned int v13; // edi
  NTSTRSAFE_PWSTR v14; // rbx
  const wchar_t *v15; // rcx
  __int64 v16; // r11
  int pcchRemaininga; // [rsp+20h] [rbp-E0h]
  int pcchRemainingb; // [rsp+20h] [rbp-E0h]
  int pcchRemainingc; // [rsp+20h] [rbp-E0h]
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  ULONG dwFlags; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsb; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsc; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsd; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagse; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsf; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsg; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsh; // [rsp+28h] [rbp-D8h]
  ULONG dwFlagsa; // [rsp+28h] [rbp-D8h]
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+30h] [rbp-D0h] BYREF
  size_t cchDest; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszSrc[104]; // [rsp+40h] [rbp-C0h] BYREF

  ppszDestEnd = a2;
  cchDest = (unsigned int)a3;
  RtlStringCchCopyExW(a2, (unsigned int)a3, a3, &ppszDestEnd, &cchDest, dwFlags);
  ultoaW(*(_DWORD *)a1, (unsigned int)pszSrc, v4, v5, pcchRemaininga, 8);
  RtlStringCchCatExW(ppszDestEnd, cchDest, pszSrc, &ppszDestEnd, &cchDest, dwFlagsb);
  RtlStringCchCatExW(ppszDestEnd, cchDest, L"-", &ppszDestEnd, &cchDest, dwFlagsc);
  ultoaW(*(unsigned __int16 *)(a1 + 4), (unsigned int)pszSrc, v6, v7, pcchRemainingb, 4);
  RtlStringCchCatExW(ppszDestEnd, cchDest, pszSrc, &ppszDestEnd, &cchDest, dwFlagsd);
  RtlStringCchCatExW(ppszDestEnd, cchDest, L"-", &ppszDestEnd, &cchDest, dwFlagse);
  ultoaW(*(unsigned __int16 *)(a1 + 6), (unsigned int)pszSrc, v8, v9, pcchRemainingc, 4);
  RtlStringCchCatExW(ppszDestEnd, cchDest, pszSrc, &ppszDestEnd, &cchDest, dwFlagsf);
  RtlStringCchCatExW(ppszDestEnd, cchDest, L"-", &ppszDestEnd, &cchDest, dwFlagsg);
  v12 = 0;
  do
  {
    while ( 1 )
    {
      ultoaW(*(unsigned __int8 *)(v12 + a1 + 8), (unsigned int)pszSrc, v10, v11, (_DWORD)pcchRemaining, 2);
      RtlStringCchCatExW(ppszDestEnd, cchDest, pszSrc, &ppszDestEnd, &cchDest, dwFlagsh);
      v13 = v12 + 1;
      if ( v12 != 1 )
        break;
      RtlStringCchCatExW(ppszDestEnd, cchDest, L"-", &ppszDestEnd, &cchDest, dwFlagsa);
      v12 = 2;
    }
    ++v12;
  }
  while ( v13 < 8 );
  v14 = ppszDestEnd;
  v15 = ppszDestEnd;
  ppszDestEnd = 0;
  if ( RtlStringValidateDestAndLengthW(v15, cchDest, (size_t *)&ppszDestEnd, v11) >= 0 )
    RtlStringCopyWorkerW(&v14[(_QWORD)ppszDestEnd], v16 - (_QWORD)ppszDestEnd, 0, L"}", (size_t)pcchRemaining);
  return 0;
}

```

## disassembly

```asm
0x1400112f0  mov     [rsp-8+arg_0], rbx
0x1400112f5  push    rbp
0x1400112f6  push    rsi
0x1400112f7  push    rdi
0x1400112f8  lea     rbp, [rsp-20h]
0x1400112fd  sub     rsp, 120h
0x140011304  mov     rax, cs:__security_cookie
0x14001130b  xor     rax, rsp
0x14001130e  mov     [rbp+30h+var_20], rax
0x140011312  mov     rsi, rcx
0x140011315  mov     [rsp+130h+ppszDestEnd], rdx
0x14001131a  mov     rax, rdx
0x14001131d  lea     rcx, [rsp+130h+cchDest]
0x140011322  mov     [rsp+130h+pcchRemaining], rcx; pcchRemaining
0x140011327  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x14001132c  mov     edx, r8d; cchDest
0x14001132f  mov     rcx, rax; pszDest
0x140011332  mov     [rsp+130h+cchDest], rdx
0x140011337  call    RtlStringCchCopyExW
0x14001133c  mov     ecx, [rsi]
0x14001133e  lea     rdx, [rsp+130h+pszSrc]
0x140011343  mov     qword ptr [rsp+130h+dwFlags], 8; dwFlags
0x14001134c  call    ultoaW
0x140011351  mov     rdx, [rsp+130h+cchDest]; cchDest
0x140011356  lea     rax, [rsp+130h+cchDest]
0x14001135b  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x140011360  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x140011365  lea     r8, [rsp+130h+pszSrc]; pszSrc
0x14001136a  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x14001136f  call    RtlStringCchCatExW
0x140011374  mov     rdx, [rsp+130h+cchDest]; cchDest
0x140011379  lea     rax, [rsp+130h+cchDest]
0x14001137e  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x140011383  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x140011388  lea     r8, asc_1400074C0; "-"
0x14001138f  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x140011394  call    RtlStringCchCatExW
0x140011399  movzx   ecx, word ptr [rsi+4]
0x14001139d  lea     rdx, [rsp+130h+pszSrc]
0x1400113a2  mov     ebx, 4
0x1400113a7  mov     qword ptr [rsp+130h+dwFlags], rbx; dwFlags
0x1400113ac  call    ultoaW
0x1400113b1  mov     rdx, [rsp+130h+cchDest]; cchDest
0x1400113b6  lea     rax, [rsp+130h+cchDest]
0x1400113bb  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x1400113c0  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x1400113c5  lea     r8, [rsp+130h+pszSrc]; pszSrc
0x1400113ca  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x1400113cf  call    RtlStringCchCatExW
0x1400113d4  mov     rdx, [rsp+130h+cchDest]; cchDest
0x1400113d9  lea     rax, [rsp+130h+cchDest]
0x1400113de  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x1400113e3  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x1400113e8  lea     r8, asc_1400074C0; "-"
0x1400113ef  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x1400113f4  call    RtlStringCchCatExW
0x1400113f9  movzx   ecx, word ptr [rsi+6]
0x1400113fd  lea     rdx, [rsp+130h+pszSrc]
0x140011402  mov     qword ptr [rsp+130h+dwFlags], rbx; dwFlags
0x140011407  call    ultoaW
0x14001140c  mov     rdx, [rsp+130h+cchDest]; cchDest
0x140011411  lea     rax, [rsp+130h+cchDest]
0x140011416  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x14001141b  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x140011420  lea     r8, [rsp+130h+pszSrc]; pszSrc
0x140011425  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x14001142a  call    RtlStringCchCatExW
0x14001142f  mov     rdx, [rsp+130h+cchDest]; cchDest
0x140011434  lea     rax, [rsp+130h+cchDest]
0x140011439  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x14001143e  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x140011443  lea     r8, asc_1400074C0; "-"
0x14001144a  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x14001144f  call    RtlStringCchCatExW
0x140011454  xor     ebx, ebx
0x140011456  mov     eax, ebx
0x140011458  lea     rdx, [rsp+130h+pszSrc]
0x14001145d  mov     qword ptr [rsp+130h+dwFlags], 2; dwFlags
0x140011466  movzx   ecx, byte ptr [rax+rsi+8]
0x14001146b  call    ultoaW
0x140011470  mov     rdx, [rsp+130h+cchDest]; cchDest
0x140011475  lea     rax, [rsp+130h+cchDest]
0x14001147a  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x14001147f  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x140011484  lea     r8, [rsp+130h+pszSrc]; pszSrc
0x140011489  mov     [rsp+130h+pcchRemaining], rax; cchToCopy
0x14001148e  call    RtlStringCchCatExW
0x140011493  lea     edi, [rbx+1]
0x140011496  cmp     ebx, 1
0x140011499  jnz     short loc_1400114C4
0x14001149b  mov     rdx, [rsp+130h+cchDest]; cchDest
0x1400114a0  lea     rax, [rsp+130h+cchDest]
0x1400114a5  mov     rcx, [rsp+130h+ppszDestEnd]; pszDest
0x1400114aa  lea     r9, [rsp+130h+ppszDestEnd]; ppszDestEnd
0x1400114af  lea     r8, asc_1400074C0; "-"
0x1400114b6  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x1400114bb  call    RtlStringCchCatExW
0x1400114c0  mov     ebx, edi
0x1400114c2  jmp     short loc_140011456
0x1400114c4  mov     ebx, edi
0x1400114c6  cmp     edi, 8
0x1400114c9  jb      short loc_140011456
0x1400114cb  mov     rbx, [rsp+130h+ppszDestEnd]
0x1400114d0  lea     r8, [rsp+130h+ppszDestEnd]; pcchDestLength
0x1400114d5  mov     r11, [rsp+130h+cchDest]
0x1400114da  mov     rcx, rbx; pszDest
0x1400114dd  mov     rdx, r11; cchDest
0x1400114e0  mov     [rsp+130h+ppszDestEnd], 0
0x1400114e9  call    RtlStringValidateDestAndLengthW
0x1400114ee  test    eax, eax
0x1400114f0  js      short loc_140011510
0x1400114f2  mov     rax, [rsp+130h+ppszDestEnd]
0x1400114f7  lea     r9, asc_1400074C4; "}"
0x1400114fe  sub     r11, rax
0x140011501  xor     r8d, r8d; pcchNewDestLength
0x140011504  mov     rdx, r11; cchDest
0x140011507  lea     rcx, [rbx+rax*2]; pszDest
0x14001150b  call    RtlStringCopyWorkerW
0x140011510  xor     eax, eax
0x140011512  mov     rcx, [rbp+30h+var_20]
0x140011516  xor     rcx, rsp; StackCookie
0x140011519  call    __security_check_cookie
0x14001151e  mov     rbx, [rsp+130h+arg_0]
0x140011526  add     rsp, 120h
0x14001152d  pop     rdi
0x14001152e  pop     rsi
0x14001152f  pop     rbp
0x140011530  retn
```
