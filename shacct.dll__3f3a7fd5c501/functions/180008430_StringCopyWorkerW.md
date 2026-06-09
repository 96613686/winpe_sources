# StringCopyWorkerW

- ea: `0x180008430`
- end: `0x1800084a4`
- name: `StringCopyWorkerW`
- size: `116`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088c0`

## callees

- `0x180008430`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  HRESULT v5; // edi
  size_t v6; // rbx
  HRESULT result; // eax

  v5 = 0;
  v6 = 0;
  if ( cchDest )
  {
    while ( cchToCopy && *pszSrc )
    {
      *pszDest++ = *pszSrc++;
      --cchToCopy;
      ++v6;
      if ( !--cchDest )
        goto LABEL_7;
    }
  }
  else
  {
LABEL_7:
    --pszDest;
    v5 = -2147024774;
    --v6;
  }
  result = v5;
  *pszDest = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v6;
  return result;
}

```

## disassembly

```asm
0x180008430  mov     [rsp+arg_0], rbx
0x180008435  mov     [rsp+arg_8], rdi
0x18000843a  xor     edi, edi
0x18000843c  xor     ebx, ebx
0x18000843e  mov     r11, rcx
0x180008441  test    rdx, rdx
0x180008444  jz      short loc_18000847D
0x180008446  mov     r10, [rsp+arg_20]
0x18000844b  nop     dword ptr [rax+rax+00h]
0x180008450  test    r10, r10
0x180008453  jz      short loc_180008489
0x180008455  movzx   eax, word ptr [r9]
0x180008459  test    ax, ax
0x18000845c  jz      short loc_180008478
0x18000845e  mov     [r11], ax
0x180008462  add     r9, 2
0x180008466  add     r11, 2
0x18000846a  dec     r10
0x18000846d  inc     rbx
0x180008470  sub     rdx, 1
0x180008474  jnz     short loc_180008450
0x180008476  jmp     short loc_18000847D
0x180008478  test    rdx, rdx
0x18000847b  jnz     short loc_180008489
0x18000847d  sub     r11, 2
0x180008481  mov     edi, 8007007Ah
0x180008486  dec     rbx
0x180008489  xor     ecx, ecx
0x18000848b  mov     eax, edi
0x18000848d  mov     [r11], cx
0x180008491  test    r8, r8
0x180008494  jz      short loc_180008499
0x180008496  mov     [r8], rbx
0x180008499  mov     rbx, [rsp+arg_0]
0x18000849e  mov     rdi, [rsp+arg_8]
0x1800084a3  retn
```
