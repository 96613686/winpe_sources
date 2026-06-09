# StringCchCatA

- ea: `0x180002830`
- end: `0x180002891`
- name: `StringCchCatA`
- size: `97`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d0`
- `0x180003614`
- `0x180005f70`
- `0x180006158`
- `0x180006514`

## callees

- `0x180002680`
- `0x180002830`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  size_t v4; // r9
  STRSAFE_LPSTR v5; // rax
  size_t v6; // rcx
  HRESULT result; // eax
  size_t v8; // [rsp+20h] [rbp-18h]

  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v4 = cchDest;
  v5 = pszDest;
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
    {
      v6 = 0;
      result = -2147024809;
      goto LABEL_7;
    }
  }
  v6 = cchDest - v4;
  result = 0;
LABEL_7:
  if ( result >= 0 )
    return StringCopyWorkerA(&pszDest[v6], cchDest - v6, (size_t *)pszSrc, pszSrc, v8);
  return result;
}

```

## disassembly

```asm
0x180002830  sub     rsp, 38h
0x180002834  lea     rax, [rdx-1]
0x180002838  mov     r10, rcx
0x18000283b  cmp     rax, 7FFFFFFEh
0x180002841  ja      short loc_18000288A
0x180002843  mov     r9, rdx
0x180002846  mov     rax, rcx
0x180002849  nop     dword ptr [rax+00000000h]
0x180002850  cmp     byte ptr [rax], 0
0x180002853  jz      short loc_180002869
0x180002855  inc     rax
0x180002858  sub     r9, 1
0x18000285c  jnz     short loc_180002850
0x18000285e  xor     eax, eax
0x180002860  mov     ecx, eax
0x180002862  mov     eax, 80070057h
0x180002867  jmp     short loc_180002871
0x180002869  mov     rcx, rdx
0x18000286c  sub     rcx, r9
0x18000286f  xor     eax, eax
0x180002871  test    eax, eax
0x180002873  jns     short loc_18000287A
0x180002875  add     rsp, 38h
0x180002879  retn
0x18000287a  sub     rdx, rcx; cchDest
0x18000287d  mov     r9, r8; pszSrc
0x180002880  add     rcx, r10; pszDest
0x180002883  call    StringCopyWorkerA
0x180002888  jmp     short loc_180002875
0x18000288a  mov     eax, 80070057h
0x18000288f  jmp     short loc_180002875
```
