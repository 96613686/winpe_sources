# StringCchCatW

- ea: `0x18000b5f0`
- end: `0x18000b6ab`
- name: `StringCchCatW`
- size: `187`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f00`
- `0x18000fce0`
- `0x180010028`
- `0x18002b680`
- `0x18002b8f8`

## callees

- `0x18000b5f0`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r11
  STRSAFE_LPWSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // rax
  size_t v9; // r9
  wchar_t *i; // rax
  wchar_t *v11; // rcx

  v3 = 2147483646;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v5 = cchDest;
  v6 = pszDest;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (cchDest - v5) & -(__int64)(v5 != 0);
  if ( v5 )
  {
    v9 = cchDest - v8;
    for ( i = &pszDest[v8]; v9; --v9 )
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *i++ = *pszSrc++;
      --v3;
    }
    v11 = i - 1;
    if ( v9 )
      v11 = i;
    v7 = v9 == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp+arg_0], rbx
0x18000b5f5  mov     [rsp+arg_8], rdi
0x18000b5fa  lea     rax, [rdx-1]
0x18000b5fe  mov     r10d, 7FFFFFFEh
0x18000b604  mov     r9, rdx
0x18000b607  mov     rbx, rcx
0x18000b60a  cmp     rax, r10
0x18000b60d  ja      loc_18000B699
0x18000b613  mov     r11, rdx
0x18000b616  mov     rax, rcx
0x18000b619  xor     edi, edi
0x18000b61b  cmp     [rax], di
0x18000b61e  jz      short loc_18000B62A
0x18000b620  add     rax, 2
0x18000b624  sub     r11, 1
0x18000b628  jnz     short loc_18000B61B
0x18000b62a  mov     rax, r11
0x18000b62d  mov     rcx, r9
0x18000b630  neg     rax
0x18000b633  mov     rax, r11
0x18000b636  sbb     edx, edx
0x18000b638  sub     rcx, r11
0x18000b63b  not     edx
0x18000b63d  and     edx, 80070057h
0x18000b643  neg     rax
0x18000b646  sbb     rax, rax
0x18000b649  and     rax, rcx
0x18000b64c  test    r11, r11
0x18000b64f  jz      short loc_18000B69E
0x18000b651  sub     r9, rax
0x18000b654  lea     rax, [rbx+rax*2]
0x18000b658  jz      short loc_18000B67C
0x18000b65a  test    r10, r10
0x18000b65d  jz      short loc_18000B67C
0x18000b65f  movzx   ecx, word ptr [r8]
0x18000b663  test    cx, cx
0x18000b666  jz      short loc_18000B67C
0x18000b668  mov     [rax], cx
0x18000b66b  add     r8, 2
0x18000b66f  add     rax, 2
0x18000b673  dec     r10
0x18000b676  sub     r9, 1
0x18000b67a  jnz     short loc_18000B65A
0x18000b67c  test    r9, r9
0x18000b67f  lea     rcx, [rax-2]
0x18000b683  cmovnz  rcx, rax
0x18000b687  neg     r9
0x18000b68a  sbb     edx, edx
0x18000b68c  not     edx
0x18000b68e  and     edx, 8007007Ah
0x18000b694  mov     [rcx], di
0x18000b697  jmp     short loc_18000B69E
0x18000b699  mov     edx, 80070057h
0x18000b69e  mov     rbx, [rsp+arg_0]
0x18000b6a3  mov     eax, edx
0x18000b6a5  mov     rdi, [rsp+arg_8]
0x18000b6aa  retn
```
