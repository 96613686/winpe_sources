# StringCchCatW

- ea: `0x140001d30`
- end: `0x140001ddd`
- name: `StringCchCatW`
- size: `173`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001340`
- `0x140001540`

## callees

- `0x140001d30`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r9
  STRSAFE_LPWSTR v6; // rax
  wchar_t *v7; // r8
  size_t v8; // rdx
  wchar_t *v9; // rcx
  HRESULT result; // eax

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
  if ( !v5 )
    return -2147024809;
  v7 = &pszDest[cchDest - v5];
  v8 = v5;
  do
  {
    if ( !v3 )
      break;
    if ( !*pszSrc )
      break;
    *v7++ = *pszSrc++;
    --v3;
    --v8;
  }
  while ( v8 );
  v9 = v7 - 1;
  if ( v8 )
    v9 = v7;
  *v9 = 0;
  result = -2147024774;
  if ( v8 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140001d30  mov     [rsp+arg_0], rbx
0x140001d35  lea     rax, [rdx-1]
0x140001d39  mov     r10d, 7FFFFFFEh
0x140001d3f  mov     rbx, r8
0x140001d42  mov     r11, rcx
0x140001d45  cmp     rax, r10
0x140001d48  ja      loc_140001DD5
0x140001d4e  mov     r9, rdx
0x140001d51  mov     rax, rcx
0x140001d54  cmp     word ptr [rax], 0
0x140001d58  jz      short loc_140001D64
0x140001d5a  add     rax, 2
0x140001d5e  sub     r9, 1
0x140001d62  jnz     short loc_140001D54
0x140001d64  xor     eax, eax
0x140001d66  mov     rcx, rdx
0x140001d69  sub     rcx, r9
0x140001d6c  mov     r8d, 80070057h
0x140001d72  test    r9, r9
0x140001d75  cmovz   rcx, rax
0x140001d79  cmovnz  r8d, eax
0x140001d7d  jz      short loc_140001DB9
0x140001d7f  lea     r8, [r11+rcx*2]
0x140001d83  sub     rdx, rcx
0x140001d86  jz      short loc_140001D95
0x140001d88  test    r10, r10
0x140001d8b  jz      short loc_140001D95
0x140001d8d  movzx   eax, word ptr [rbx]
0x140001d90  test    ax, ax
0x140001d93  jnz     short loc_140001DBE
0x140001d95  test    rdx, rdx
0x140001d98  lea     rcx, [r8-2]
0x140001d9c  cmovnz  rcx, r8
0x140001da0  xor     eax, eax
0x140001da2  mov     [rcx], ax
0x140001da5  xor     ecx, ecx
0x140001da7  test    rdx, rdx
0x140001daa  mov     eax, 8007007Ah
0x140001daf  cmovnz  eax, ecx
0x140001db2  mov     rbx, [rsp+arg_0]
0x140001db7  retn
0x140001db9  mov     eax, r8d
0x140001dbc  jmp     short loc_140001DB2
0x140001dbe  mov     [r8], ax
0x140001dc2  add     rbx, 2
0x140001dc6  add     r8, 2
0x140001dca  dec     r10
0x140001dcd  sub     rdx, 1
0x140001dd1  jnz     short loc_140001D88
0x140001dd3  jmp     short loc_140001D95
0x140001dd5  mov     r8d, 80070057h
0x140001ddb  jmp     short loc_140001DB9
```
