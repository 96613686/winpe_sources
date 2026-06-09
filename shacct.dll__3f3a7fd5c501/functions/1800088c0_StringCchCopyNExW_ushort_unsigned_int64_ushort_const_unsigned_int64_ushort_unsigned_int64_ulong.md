# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1800088c0`
- end: `0x1800089b5`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `245`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, size_t pcchNewDestLength, unsigned __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004fd0`
- `0x180005300`

## callees

- `0x180008430`
- `0x1800088c0`
- `0x18000cb84`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy,
        size_t pcchNewDestLength)
{
  HRESULT v7; // ebx
  const wchar_t *v8; // rcx
  size_t v9; // rdx
  unsigned int v10; // eax
  size_t v11; // rdi
  bool v12; // cf

  if ( (pszDest || !cchDest) && cchDest <= 0x7FFFFFFF )
  {
    if ( cchToCopy < 0x7FFFFFFF )
    {
      v8 = (const wchar_t *)&qword_18001B188;
      if ( pszSrc )
        v8 = pszSrc;
      v9 = 0;
      if ( pszSrc )
        v9 = cchToCopy;
      if ( cchDest )
      {
        pcchNewDestLength = 0;
        v7 = StringCopyWorkerW(pszDest, cchDest, &pcchNewDestLength, v8, v9);
        if ( v7 >= 0 )
        {
          v12 = cchDest == pcchNewDestLength;
          v11 = cchDest - pcchNewDestLength;
          if ( !v12 && v11 != 1 && 2 * v11 > 2 )
            memset_0(&pszDest[pcchNewDestLength + 1], 0, 2 * v11 - 2);
        }
      }
      else
      {
        v7 = 0;
        if ( v9 && *v8 )
        {
          v10 = -2147024774;
          if ( !pszDest )
            return (unsigned int)-2147024809;
          return v10;
        }
      }
    }
    else
    {
      v7 = -2147024809;
      if ( cchDest )
        *pszDest = 0;
    }
  }
  else
  {
    v7 = -2147024809;
    *pszDest = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800088c0  mov     [rsp+arg_0], rbx
0x1800088c5  mov     [rsp+arg_8], rsi
0x1800088ca  push    rdi
0x1800088cb  sub     rsp, 30h
0x1800088cf  mov     rdi, rdx
0x1800088d2  mov     rsi, rcx
0x1800088d5  test    rcx, rcx
0x1800088d8  jnz     short loc_1800088DF
0x1800088da  test    rdx, rdx
0x1800088dd  jnz     short loc_1800088E8
0x1800088df  cmp     rdi, 7FFFFFFFh
0x1800088e6  jbe     short loc_1800088F7
0x1800088e8  xor     eax, eax
0x1800088ea  mov     ebx, 80070057h
0x1800088ef  mov     [rcx], ax
0x1800088f2  jmp     loc_1800089A3
0x1800088f7  cmp     r9, 7FFFFFFFh
0x1800088fe  jb      short loc_180008918
0x180008900  mov     ebx, 80070057h
0x180008905  test    rdi, rdi
0x180008908  jz      loc_1800089A3
0x18000890e  xor     eax, eax
0x180008910  mov     [rcx], ax
0x180008913  jmp     loc_1800089A3
0x180008918  test    r8, r8
0x18000891b  lea     rcx, qword_18001B188
0x180008922  cmovnz  rcx, r8
0x180008926  xor     eax, eax
0x180008928  test    r8, r8
0x18000892b  mov     edx, eax
0x18000892d  cmovnz  rdx, r9
0x180008931  test    rdi, rdi
0x180008934  jnz     short loc_180008956
0x180008936  mov     ebx, eax
0x180008938  test    rdx, rdx
0x18000893b  jz      short loc_1800089A3
0x18000893d  cmp     [rcx], ax
0x180008940  jz      short loc_1800089A3
0x180008942  mov     ebx, 80070057h
0x180008947  test    rsi, rsi
0x18000894a  mov     eax, 8007007Ah
0x18000894f  cmovz   eax, ebx
0x180008952  mov     ebx, eax
0x180008954  jmp     short loc_1800089A3
0x180008956  mov     [rsp+38h+cchToCopy], rdx; cchToCopy
0x18000895b  lea     r8, [rsp+38h+pcchNewDestLength]; pcchNewDestLength
0x180008960  mov     r9, rcx; pszSrc
0x180008963  mov     [rsp+38h+pcchNewDestLength], rax
0x180008968  mov     rdx, rdi; cchDest
0x18000896b  mov     rcx, rsi; pszDest
0x18000896e  call    StringCopyWorkerW
0x180008973  mov     ebx, eax
0x180008975  test    eax, eax
0x180008977  js      short loc_1800089A3
0x180008979  mov     rax, [rsp+38h+pcchNewDestLength]
0x18000897e  sub     rdi, rax
0x180008981  cmp     rdi, 1
0x180008985  jbe     short loc_1800089A3
0x180008987  lea     r8, [rdi+rdi]
0x18000898b  cmp     r8, 2
0x18000898f  jbe     short loc_1800089A3
0x180008991  inc     rax
0x180008994  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180008998  xor     edx, edx; Val
0x18000899a  lea     rcx, [rsi+rax*2]; void *
0x18000899e  call    memset_0
0x1800089a3  mov     rsi, [rsp+38h+arg_8]
0x1800089a8  mov     eax, ebx
0x1800089aa  mov     rbx, [rsp+38h+arg_0]
0x1800089af  add     rsp, 30h
0x1800089b3  pop     rdi
0x1800089b4  retn
```
