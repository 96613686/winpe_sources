# StringCchCopyNExW

- ea: `0x18000fd7c`
- end: `0x18000fe57`
- name: `StringCchCopyNExW`
- size: `219`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000efbc`

## callees

- `0x18000fd7c`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  HRESULT v8; // r8d
  size_t v9; // r9
  size_t v10; // rcx
  signed __int64 v11; // rbx
  STRSAFE_LPWSTR v12; // r8
  __int64 v13; // rdi
  wchar_t v14; // ax
  STRSAFE_LPWSTR v15; // rax
  __int64 v16; // rax

  if ( cchDest - 1 > 0x7FFFFFFE )
  {
    v8 = -2147024809;
    if ( cchDest )
      goto LABEL_19;
  }
  else
  {
    if ( cchToCopy >= 0x7FFFFFFF )
    {
      v8 = -2147024809;
LABEL_19:
      *pszDest = 0;
      return v8;
    }
    v9 = cchToCopy - cchDest;
    v10 = cchDest;
    v11 = (char *)pszSrc - (char *)pszDest;
    v12 = pszDest;
    v13 = 0;
    do
    {
      if ( !(v9 + v10) )
        break;
      v14 = *(STRSAFE_LPWSTR)((char *)v12 + v11);
      if ( !v14 )
        break;
      *v12 = v14;
      ++v13;
      ++v12;
      --v10;
    }
    while ( v10 );
    v15 = v12 - 1;
    if ( v10 )
      v15 = v12;
    *v15 = 0;
    v16 = v13 - 1;
    if ( v10 )
      v16 = v13;
    v8 = v10 == 0 ? 0x8007007A : 0;
    if ( v10 || v8 == -2147024774 )
    {
      if ( ppszDestEnd )
        *ppszDestEnd = &pszDest[v16];
      if ( pcchRemaining )
        *pcchRemaining = cchDest - v16;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000fd7c  mov     [rsp+arg_0], rbx
0x18000fd81  push    rdi
0x18000fd82  sub     rsp, 10h
0x18000fd86  lea     rax, [rdx-1]
0x18000fd8a  mov     r10, rdx
0x18000fd8d  xor     edx, edx
0x18000fd8f  mov     rbx, r8
0x18000fd92  mov     r11, rcx
0x18000fd95  cmp     rax, 7FFFFFFEh
0x18000fd9b  ja      loc_18000FE3A
0x18000fda1  cmp     r9, 7FFFFFFFh
0x18000fda8  jb      short loc_18000FDB5
0x18000fdaa  mov     r8d, 80070057h
0x18000fdb0  jmp     loc_18000FE45
0x18000fdb5  sub     r9, r10
0x18000fdb8  mov     rcx, r10
0x18000fdbb  sub     rbx, r11
0x18000fdbe  mov     r8, r11
0x18000fdc1  mov     rdi, rdx
0x18000fdc4  lea     rax, [r9+rcx]
0x18000fdc8  test    rax, rax
0x18000fdcb  jz      short loc_18000FDE8
0x18000fdcd  movzx   eax, word ptr [rbx+r8]
0x18000fdd2  test    ax, ax
0x18000fdd5  jz      short loc_18000FDE8
0x18000fdd7  mov     [r8], ax
0x18000fddb  inc     rdi
0x18000fdde  add     r8, 2
0x18000fde2  sub     rcx, 1
0x18000fde6  jnz     short loc_18000FDC4
0x18000fde8  test    rcx, rcx
0x18000fdeb  lea     rax, [r8-2]
0x18000fdef  mov     r9d, 8007007Ah
0x18000fdf5  cmovnz  rax, r8
0x18000fdf9  mov     [rax], dx
0x18000fdfc  lea     rax, [rdi-1]
0x18000fe00  cmovnz  rax, rdi
0x18000fe04  neg     rcx
0x18000fe07  sbb     r8d, r8d
0x18000fe0a  sub     r10, rax
0x18000fe0d  not     r8d
0x18000fe10  lea     rcx, [r11+rax*2]
0x18000fe14  and     r8d, r9d
0x18000fe17  jns     short loc_18000FE1E
0x18000fe19  cmp     r8d, r9d
0x18000fe1c  jnz     short loc_18000FE48
0x18000fe1e  mov     rax, [rsp+18h+ppszDestEnd]
0x18000fe23  test    rax, rax
0x18000fe26  jz      short loc_18000FE2B
0x18000fe28  mov     [rax], rcx
0x18000fe2b  mov     rax, [rsp+18h+pcchRemaining]
0x18000fe30  test    rax, rax
0x18000fe33  jz      short loc_18000FE48
0x18000fe35  mov     [rax], r10
0x18000fe38  jmp     short loc_18000FE48
0x18000fe3a  mov     r8d, 80070057h
0x18000fe40  test    r10, r10
0x18000fe43  jz      short loc_18000FE48
0x18000fe45  mov     [rcx], dx
0x18000fe48  mov     rbx, [rsp+18h+arg_0]
0x18000fe4d  mov     eax, r8d
0x18000fe50  add     rsp, 10h
0x18000fe54  pop     rdi
0x18000fe55  retn
```
