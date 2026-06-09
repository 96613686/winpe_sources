# StringCchCopyNExW

- ea: `0x18000a958`
- end: `0x18000aa37`
- name: `StringCchCopyNExW`
- size: `223`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a780`

## callees

- `0x18000a958`

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
  HRESULT v10; // edx
  size_t v11; // r8
  STRSAFE_LPWSTR v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r9
  STRSAFE_LPWSTR v15; // rcx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF || cchToCopy >= 0x7FFFFFFF )
  {
    v10 = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v11 = cchDest;
    v12 = pszDest;
    v13 = 0;
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *v12++ = *pszSrc++;
      --cchToCopy;
      ++v13;
      --v11;
    }
    while ( v11 );
    v14 = v13 - 1;
    if ( v11 )
      v14 = v13;
    v15 = v12 - 1;
    v10 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v15 = v12;
    *v15 = 0;
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024774 )
    {
      if ( ppszDestEnd )
        *ppszDestEnd = &pszDest[v14];
      if ( pcchRemaining )
        *pcchRemaining = cchDest - v14;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000a958  mov     [rsp+arg_0], rbx
0x18000a95d  mov     [rsp+arg_8], rdi
0x18000a962  xor     edi, edi
0x18000a964  mov     rax, r8
0x18000a967  mov     r10, rdx
0x18000a96a  mov     r11, rcx
0x18000a96d  test    rdx, rdx
0x18000a970  jz      loc_18000AA1C
0x18000a976  mov     ecx, 7FFFFFFFh
0x18000a97b  cmp     rdx, rcx
0x18000a97e  jbe     short loc_18000A98A
0x18000a980  mov     edx, 80070057h
0x18000a985  jmp     loc_18000AA26
0x18000a98a  cmp     r9, rcx
0x18000a98d  jnb     short loc_18000A980
0x18000a98f  mov     r8, r10
0x18000a992  mov     rbx, r11
0x18000a995  mov     rcx, rdi
0x18000a998  test    r9, r9
0x18000a99b  jz      short loc_18000A9BC
0x18000a99d  movzx   edx, word ptr [rax]
0x18000a9a0  test    dx, dx
0x18000a9a3  jz      short loc_18000A9BC
0x18000a9a5  mov     [rbx], dx
0x18000a9a8  add     rax, 2
0x18000a9ac  add     rbx, 2
0x18000a9b0  dec     r9
0x18000a9b3  inc     rcx
0x18000a9b6  sub     r8, 1
0x18000a9ba  jnz     short loc_18000A998
0x18000a9bc  test    r8, r8
0x18000a9bf  lea     r9, [rcx-1]
0x18000a9c3  mov     rax, r8
0x18000a9c6  cmovnz  r9, rcx
0x18000a9ca  neg     rax
0x18000a9cd  lea     rcx, [rbx-2]
0x18000a9d1  sbb     edx, edx
0x18000a9d3  not     edx
0x18000a9d5  and     edx, 8007007Ah
0x18000a9db  test    r8, r8
0x18000a9de  cmovnz  rcx, rbx
0x18000a9e2  mov     [rcx], di
0x18000a9e5  mov     ecx, 80000000h
0x18000a9ea  lea     eax, [rdx+rcx]
0x18000a9ed  test    ecx, eax
0x18000a9ef  jnz     short loc_18000A9F9
0x18000a9f1  cmp     edx, 8007007Ah
0x18000a9f7  jnz     short loc_18000AA2A
0x18000a9f9  mov     rcx, [rsp+arg_20]
0x18000a9fe  test    rcx, rcx
0x18000aa01  jz      short loc_18000AA0A
0x18000aa03  lea     rax, [r11+r9*2]
0x18000aa07  mov     [rcx], rax
0x18000aa0a  mov     rax, [rsp+arg_28]
0x18000aa0f  test    rax, rax
0x18000aa12  jz      short loc_18000AA2A
0x18000aa14  sub     r10, r9
0x18000aa17  mov     [rax], r10
0x18000aa1a  jmp     short loc_18000AA2A
0x18000aa1c  mov     edx, 80070057h
0x18000aa21  test    r10, r10
0x18000aa24  jz      short loc_18000AA2A
0x18000aa26  mov     [r11], di
0x18000aa2a  mov     rbx, [rsp+arg_0]
0x18000aa2f  mov     eax, edx
0x18000aa31  mov     rdi, [rsp+arg_8]
0x18000aa36  retn
```
