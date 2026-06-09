# StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)

- ea: `0x14000cff8`
- end: `0x14000d1e0`
- name: `?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z`
- size: `488`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPWSTR pszDest@<rcx>, unsigned __int64@<rdx>, const wchar_t *@<r8>, wchar_t **@<r9>, unsigned __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010128`
- `0x1400109ec`

## callees

- `0x14000cf2c`
- `0x14000cff8`
- `0x140020760`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        size_t a2,
        const wchar_t *a3,
        wchar_t **a4,
        unsigned __int64 *a5,
        DWORD dwFlags)
{
  wchar_t *v6; // r10
  __int64 v8; // rbx
  STRSAFE_LPWSTR v9; // rsi
  size_t v10; // rdi
  const wchar_t *v11; // rax
  size_t v12; // r9
  signed __int64 v13; // r8
  wchar_t v14; // ax
  STRSAFE_LPWSTR v15; // rax
  __int64 v16; // rcx
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-48h] BYREF
  size_t pcchRemaining[8]; // [rsp+38h] [rbp-40h] BYREF

  v6 = pszDest;
  LODWORD(v8) = 0;
  if ( (dwFlags & 0x100) != 0 )
  {
    if ( !pszDest && a2 || a2 > 0x7FFFFFFF )
      LODWORD(v8) = -2147024809;
  }
  else if ( a2 - 1 > 0x7FFFFFFE )
  {
    LODWORD(v8) = -2147024809;
  }
  if ( (int)v8 < 0 )
  {
    if ( a2 )
      *pszDest = 0;
  }
  else
  {
    ppszDestEnd = pszDest;
    v9 = pszDest;
    pcchRemaining[0] = a2;
    v10 = a2;
    if ( (dwFlags & 0x100) != 0 )
    {
      v11 = &OutputString;
      if ( a3 )
        v11 = a3;
      a3 = v11;
    }
    v8 = 0;
    if ( (dwFlags & 0xFFFFE000) != 0 )
    {
      LODWORD(v8) = -2147024809;
      if ( a2 )
        *pszDest = 0;
    }
    else if ( a2 )
    {
      v12 = a2;
      v13 = (char *)a3 - (char *)pszDest;
      do
      {
        if ( !(2147483646 - a2 + v12) )
          break;
        v14 = *(STRSAFE_LPWSTR)((char *)pszDest + v13);
        if ( !v14 )
          break;
        *pszDest = v14;
        ++v8;
        ++pszDest;
        --v12;
      }
      while ( v12 );
      v15 = pszDest - 1;
      if ( v12 )
        v15 = pszDest;
      v16 = v8 - 1;
      if ( v12 )
        v16 = v8;
      *v15 = 0;
      v9 = &v6[v16];
      ppszDestEnd = v9;
      v10 = a2 - v16;
      pcchRemaining[0] = a2 - v16;
      LODWORD(v8) = v12 == 0 ? 0x8007007A : 0;
      if ( v12 )
      {
        if ( (dwFlags & 0x200) != 0 && v10 > 1 && 2 * v10 > 2 )
          memset(v9 + 1, (unsigned __int8)dwFlags, 2 * v10 - 2);
        goto LABEL_20;
      }
    }
    else
    {
      if ( !*a3 )
      {
LABEL_20:
        if ( a4 )
          *a4 = v9;
        if ( a5 )
          *a5 = v10;
        return (unsigned int)v8;
      }
      LODWORD(v8) = pszDest != 0 ? -2147024774 : -2147024809;
    }
    if ( (dwFlags & 0x1C00) != 0 && a2 )
    {
      StringExHandleOtherFlagsW(v6, 2 * a2, 0, &ppszDestEnd, pcchRemaining, dwFlags);
      v9 = ppszDestEnd;
      v10 = pcchRemaining[0];
    }
    if ( (_DWORD)v8 == -2147024774 )
      goto LABEL_20;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000cff8  push    rbx
0x14000cffa  push    rbp
0x14000cffb  push    rsi
0x14000cffc  push    rdi
0x14000cffd  push    r12
0x14000cfff  push    r14
0x14000d001  push    r15
0x14000d003  sub     rsp, 40h
0x14000d007  mov     r11d, [rsp+78h+arg_28]
0x14000d00f  mov     r10, rcx
0x14000d012  mov     r15, [rsp+78h+arg_20]
0x14000d01a  xor     r12d, r12d
0x14000d01d  mov     ecx, r11d
0x14000d020  mov     rbp, r9
0x14000d023  mov     ebx, r12d
0x14000d026  mov     r14d, 7FFFFFFEh
0x14000d02c  mov     r9d, 80070057h
0x14000d032  and     ecx, 100h
0x14000d038  jz      short loc_14000D052
0x14000d03a  test    r10, r10
0x14000d03d  jnz     short loc_14000D044
0x14000d03f  test    rdx, rdx
0x14000d042  jnz     short loc_14000D04D
0x14000d044  cmp     rdx, 7FFFFFFFh
0x14000d04b  jbe     short loc_14000D05D
0x14000d04d  mov     ebx, r9d
0x14000d050  jmp     short loc_14000D05D
0x14000d052  lea     rax, [rdx-1]
0x14000d056  cmp     rax, r14
0x14000d059  cmova   ebx, r9d
0x14000d05d  test    ebx, ebx
0x14000d05f  js      loc_14000D1C6
0x14000d065  mov     [rsp+78h+ppszDestEnd], r10
0x14000d06a  mov     rsi, r10
0x14000d06d  mov     [rsp+78h+var_40], rdx
0x14000d072  mov     rdi, rdx
0x14000d075  test    ecx, ecx
0x14000d077  jz      short loc_14000D08A
0x14000d079  test    r8, r8
0x14000d07c  lea     rax, OutputString
0x14000d083  cmovnz  rax, r8
0x14000d087  mov     r8, rax
0x14000d08a  mov     ebx, r12d
0x14000d08d  test    r11d, 0FFFFE000h
0x14000d094  jz      short loc_14000D102
0x14000d096  mov     ebx, r9d
0x14000d099  test    rdx, rdx
0x14000d09c  jz      short loc_14000D0A2
0x14000d09e  mov     [r10], r12w
0x14000d0a2  test    r11d, 1C00h
0x14000d0a9  jz      short loc_14000D0DC
0x14000d0ab  test    rdx, rdx
0x14000d0ae  jz      short loc_14000D0DC
0x14000d0b0  lea     rax, [rsp+78h+var_40]
0x14000d0b5  mov     [rsp+78h+dwFlags], r11d; dwFlags
0x14000d0ba  add     rdx, rdx; cbDest
0x14000d0bd  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x14000d0c2  lea     r9, [rsp+78h+ppszDestEnd]; ppszDestEnd
0x14000d0c7  xor     r8d, r8d; cchOriginalDestLength
0x14000d0ca  mov     rcx, r10; pszDest
0x14000d0cd  call    StringExHandleOtherFlagsW
0x14000d0d2  mov     rsi, [rsp+78h+ppszDestEnd]
0x14000d0d7  mov     rdi, [rsp+78h+var_40]
0x14000d0dc  cmp     ebx, 8007007Ah
0x14000d0e2  jnz     loc_14000D1CF
0x14000d0e8  test    rbp, rbp
0x14000d0eb  jz      short loc_14000D0F1
0x14000d0ed  mov     [rbp+0], rsi
0x14000d0f1  test    r15, r15
0x14000d0f4  jz      loc_14000D1CF
0x14000d0fa  mov     [r15], rdi
0x14000d0fd  jmp     loc_14000D1CF
0x14000d102  test    rdx, rdx
0x14000d105  jnz     short loc_14000D11D
0x14000d107  cmp     [r8], r12w
0x14000d10b  jz      short loc_14000D0E8
0x14000d10d  mov     rax, r10
0x14000d110  neg     rax
0x14000d113  sbb     ebx, ebx
0x14000d115  and     ebx, 23h
0x14000d118  add     ebx, r9d
0x14000d11b  jmp     short loc_14000D0A2
0x14000d11d  sub     r14, rdx
0x14000d120  mov     r9, rdx
0x14000d123  sub     r8, r10
0x14000d126  mov     rcx, r10
0x14000d129  lea     rax, [r14+r9]
0x14000d12d  test    rax, rax
0x14000d130  jz      short loc_14000D14C
0x14000d132  movzx   eax, word ptr [r8+rcx]
0x14000d137  test    ax, ax
0x14000d13a  jz      short loc_14000D14C
0x14000d13c  mov     [rcx], ax
0x14000d13f  inc     rbx
0x14000d142  add     rcx, 2
0x14000d146  sub     r9, 1
0x14000d14a  jnz     short loc_14000D129
0x14000d14c  test    r9, r9
0x14000d14f  lea     rax, [rcx-2]
0x14000d153  cmovnz  rax, rcx
0x14000d157  lea     rcx, [rbx-1]
0x14000d15b  cmovnz  rcx, rbx
0x14000d15f  mov     [rax], r12w
0x14000d163  mov     rax, r9
0x14000d166  neg     rax
0x14000d169  lea     rsi, [r10+rcx*2]
0x14000d16d  mov     [rsp+78h+ppszDestEnd], rsi
0x14000d172  sbb     ebx, ebx
0x14000d174  sub     rdi, rcx
0x14000d177  not     ebx
0x14000d179  mov     [rsp+78h+var_40], rdi
0x14000d17e  and     ebx, 8007007Ah
0x14000d184  test    r9, r9
0x14000d187  jz      loc_14000D0A2
0x14000d18d  bt      r11d, 9
0x14000d192  jnb     loc_14000D0E8
0x14000d198  cmp     rdi, 1
0x14000d19c  jbe     loc_14000D0E8
0x14000d1a2  lea     r8, [rdi+rdi]
0x14000d1a6  cmp     r8, 2
0x14000d1aa  jbe     loc_14000D0E8
0x14000d1b0  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x14000d1b4  movzx   edx, r11b; Val
0x14000d1b8  lea     rcx, [rsi+2]; void *
0x14000d1bc  call    memset
0x14000d1c1  jmp     loc_14000D0E8
0x14000d1c6  test    rdx, rdx
0x14000d1c9  jz      short loc_14000D1CF
0x14000d1cb  mov     [r10], r12w
0x14000d1cf  mov     eax, ebx
0x14000d1d1  add     rsp, 40h
0x14000d1d5  pop     r15
0x14000d1d7  pop     r14
0x14000d1d9  pop     r12
0x14000d1db  pop     rdi
0x14000d1dc  pop     rsi
0x14000d1dd  pop     rbp
0x14000d1de  pop     rbx
0x14000d1df  retn
```
