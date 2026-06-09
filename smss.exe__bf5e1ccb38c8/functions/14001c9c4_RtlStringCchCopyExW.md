# RtlStringCchCopyExW

- ea: `0x14001c9c4`
- end: `0x14001cab6`
- name: `RtlStringCchCopyExW`
- size: `242`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc, NTSTRSAFE_PWSTR *ppszDestEnd, size_t *pcchRemaining, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c14c`

## callees

- `0x14001c9c4`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyExW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        NTSTRSAFE_PCWSTR pszSrc,
        NTSTRSAFE_PWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        ULONG dwFlags)
{
  NTSTRSAFE_PWSTR v8; // r11
  NTSTATUS v9; // r8d
  __int64 v10; // rax
  size_t v11; // r9
  NTSTRSAFE_PWSTR v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  NTSTRSAFE_PWSTR v15; // rcx
  size_t v16; // rax
  size_t v17; // r10

  v8 = pszDest;
  if ( !cchDest )
    return -1073741811;
  if ( cchDest > 0x7FFFFFFF )
  {
    v9 = -1073741811;
    *pszDest = 0;
    return v9;
  }
  v10 = 2147483646;
  v11 = cchDest;
  v12 = pszDest;
  v13 = 0;
  do
  {
    if ( !v10 )
      break;
    if ( !*pszSrc )
      break;
    *v12++ = *pszSrc++;
    --v10;
    ++v13;
    --v11;
  }
  while ( v11 );
  v14 = v13 - 1;
  if ( v11 )
    v14 = v13;
  v15 = v12 - 1;
  v9 = v11 != 0 ? 0 : 0x80000005;
  if ( v11 )
    v15 = v12;
  v16 = cchDest - v14;
  *v15 = 0;
  if ( v11 )
  {
    v8 += v14;
    v17 = cchDest - v14;
  }
  else
  {
    v17 = cchDest & 0x7FFFFFFFFFFFFFFFLL;
    if ( v17 )
    {
      *v8 = 0;
    }
    else
    {
      v17 = v16;
      v8 += v14;
    }
    if ( v9 != -2147483643 )
      return v9;
  }
  if ( ppszDestEnd )
    *ppszDestEnd = v8;
  if ( pcchRemaining )
    *pcchRemaining = v17;
  return v9;
}

```

## disassembly

```asm
0x14001c9c4  push    rbx
0x14001c9c6  push    rsi
0x14001c9c7  push    rdi
0x14001c9c8  xor     esi, esi
0x14001c9ca  mov     rdi, r9
0x14001c9cd  mov     r10, rdx
0x14001c9d0  mov     r11, rcx
0x14001c9d3  test    rdx, rdx
0x14001c9d6  jz      loc_14001CAA1
0x14001c9dc  cmp     rdx, 7FFFFFFFh
0x14001c9e3  jbe     short loc_14001C9F0
0x14001c9e5  mov     r8d, 0C000000Dh
0x14001c9eb  jmp     loc_14001CAAC
0x14001c9f0  mov     eax, 7FFFFFFEh
0x14001c9f5  mov     r9, r10
0x14001c9f8  mov     rbx, r11
0x14001c9fb  mov     rcx, rsi
0x14001c9fe  test    rax, rax
0x14001ca01  jz      short loc_14001CA23
0x14001ca03  movzx   edx, word ptr [r8]
0x14001ca07  test    dx, dx
0x14001ca0a  jz      short loc_14001CA23
0x14001ca0c  mov     [rbx], dx
0x14001ca0f  add     r8, 2
0x14001ca13  add     rbx, 2
0x14001ca17  dec     rax
0x14001ca1a  inc     rcx
0x14001ca1d  sub     r9, 1
0x14001ca21  jnz     short loc_14001C9FE
0x14001ca23  test    r9, r9
0x14001ca26  lea     rdx, [rcx-1]
0x14001ca2a  mov     rax, r9
0x14001ca2d  cmovnz  rdx, rcx
0x14001ca31  neg     rax
0x14001ca34  lea     rcx, [rbx-2]
0x14001ca38  mov     rax, r10
0x14001ca3b  sbb     r8d, r8d
0x14001ca3e  not     r8d
0x14001ca41  and     r8d, 80000005h
0x14001ca48  test    r9, r9
0x14001ca4b  cmovnz  rcx, rbx
0x14001ca4f  sub     rax, rdx
0x14001ca52  mov     [rcx], si
0x14001ca55  lea     rcx, [r11+rdx*2]
0x14001ca59  test    r9, r9
0x14001ca5c  jnz     short loc_14001CA84
0x14001ca5e  mov     rdx, 7FFFFFFFFFFFFFFFh
0x14001ca68  and     r10, rdx
0x14001ca6b  jbe     short loc_14001CA73
0x14001ca6d  mov     [r11], si
0x14001ca71  jmp     short loc_14001CA79
0x14001ca73  mov     r10, rax
0x14001ca76  mov     r11, rcx
0x14001ca79  cmp     r8d, 80000005h
0x14001ca80  jnz     short loc_14001CAAF
0x14001ca82  jmp     short loc_14001CA8A
0x14001ca84  mov     r11, rcx
0x14001ca87  mov     r10, rax
0x14001ca8a  test    rdi, rdi
0x14001ca8d  jz      short loc_14001CA92
0x14001ca8f  mov     [rdi], r11
0x14001ca92  mov     rax, [rsp+18h+pcchRemaining]
0x14001ca97  test    rax, rax
0x14001ca9a  jz      short loc_14001CAAF
0x14001ca9c  mov     [rax], r10
0x14001ca9f  jmp     short loc_14001CAAF
0x14001caa1  mov     r8d, 0C000000Dh
0x14001caa7  test    r10, r10
0x14001caaa  jz      short loc_14001CAAF
0x14001caac  mov     [rcx], si
0x14001caaf  mov     eax, r8d
0x14001cab2  pop     rdi
0x14001cab3  pop     rsi
0x14001cab4  pop     rbx
0x14001cab5  retn
```
