# StringCchCopyNExW

- ea: `0x180015474`
- end: `0x180015553`
- name: `StringCchCopyNExW`
- size: `223`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800151f0`

## callees

- `0x180015474`

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
0x180015474  mov     [rsp+arg_0], rbx
0x180015479  mov     [rsp+arg_8], rdi
0x18001547e  xor     edi, edi
0x180015480  mov     rax, r8
0x180015483  mov     r10, rdx
0x180015486  mov     r11, rcx
0x180015489  test    rdx, rdx
0x18001548c  jz      loc_180015538
0x180015492  mov     ecx, 7FFFFFFFh
0x180015497  cmp     rdx, rcx
0x18001549a  jbe     short loc_1800154A6
0x18001549c  mov     edx, 80070057h
0x1800154a1  jmp     loc_180015542
0x1800154a6  cmp     r9, rcx
0x1800154a9  jnb     short loc_18001549C
0x1800154ab  mov     r8, r10
0x1800154ae  mov     rbx, r11
0x1800154b1  mov     rcx, rdi
0x1800154b4  test    r9, r9
0x1800154b7  jz      short loc_1800154D8
0x1800154b9  movzx   edx, word ptr [rax]
0x1800154bc  test    dx, dx
0x1800154bf  jz      short loc_1800154D8
0x1800154c1  mov     [rbx], dx
0x1800154c4  add     rax, 2
0x1800154c8  add     rbx, 2
0x1800154cc  dec     r9
0x1800154cf  inc     rcx
0x1800154d2  sub     r8, 1
0x1800154d6  jnz     short loc_1800154B4
0x1800154d8  test    r8, r8
0x1800154db  lea     r9, [rcx-1]
0x1800154df  mov     rax, r8
0x1800154e2  cmovnz  r9, rcx
0x1800154e6  neg     rax
0x1800154e9  lea     rcx, [rbx-2]
0x1800154ed  sbb     edx, edx
0x1800154ef  not     edx
0x1800154f1  and     edx, 8007007Ah
0x1800154f7  test    r8, r8
0x1800154fa  cmovnz  rcx, rbx
0x1800154fe  mov     [rcx], di
0x180015501  mov     ecx, 80000000h
0x180015506  lea     eax, [rdx+rcx]
0x180015509  test    ecx, eax
0x18001550b  jnz     short loc_180015515
0x18001550d  cmp     edx, 8007007Ah
0x180015513  jnz     short loc_180015546
0x180015515  mov     rcx, [rsp+arg_20]
0x18001551a  test    rcx, rcx
0x18001551d  jz      short loc_180015526
0x18001551f  lea     rax, [r11+r9*2]
0x180015523  mov     [rcx], rax
0x180015526  mov     rax, [rsp+arg_28]
0x18001552b  test    rax, rax
0x18001552e  jz      short loc_180015546
0x180015530  sub     r10, r9
0x180015533  mov     [rax], r10
0x180015536  jmp     short loc_180015546
0x180015538  mov     edx, 80070057h
0x18001553d  test    r10, r10
0x180015540  jz      short loc_180015546
0x180015542  mov     [r11], di
0x180015546  mov     rbx, [rsp+arg_0]
0x18001554b  mov     eax, edx
0x18001554d  mov     rdi, [rsp+arg_8]
0x180015552  retn
```
