# RtlStringCbCopyExW

- ea: `0x1400049ac`
- end: `0x140004a80`
- name: `RtlStringCbCopyExW`
- size: `212`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc, NTSTRSAFE_PWSTR *ppszDestEnd, size_t *pcbRemaining, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014be0`

## callees

- `0x1400049ac`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyExW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cbDest,
        NTSTRSAFE_PCWSTR pszSrc,
        NTSTRSAFE_PWSTR *ppszDestEnd,
        size_t *pcbRemaining,
        ULONG dwFlags)
{
  size_t v6; // r11
  char v9; // bl
  NTSTATUS v11; // edx
  __int64 v12; // rax
  size_t v13; // r8
  NTSTRSAFE_PWSTR v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  NTSTRSAFE_PWSTR v17; // rax
  size_t v18; // r11

  v6 = cbDest >> 1;
  v9 = cbDest;
  if ( !(cbDest >> 1) )
    return -1073741811;
  if ( v6 <= 0x7FFFFFFF )
  {
    v12 = 2147483646;
    v13 = cbDest >> 1;
    v14 = pszDest;
    v15 = 0;
    do
    {
      if ( !v12 )
        break;
      if ( !*pszSrc )
        break;
      *v14++ = *pszSrc++;
      --v12;
      ++v15;
      --v13;
    }
    while ( v13 );
    v16 = v15 - 1;
    if ( v13 )
      v16 = v15;
    v17 = v14 - 1;
    if ( v13 )
      v17 = v14;
    v18 = v6 - v16;
    *v17 = 0;
    v11 = v13 == 0 ? 0x80000005 : 0;
    if ( v13 || v11 == -2147483643 )
    {
      if ( ppszDestEnd )
        *ppszDestEnd = &pszDest[v16];
      if ( pcbRemaining )
        *pcbRemaining = (v9 & 1) + 2 * v18;
    }
  }
  else
  {
    v11 = -1073741811;
    *pszDest = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1400049ac  push    rbx
0x1400049ae  push    rsi
0x1400049af  push    rdi
0x1400049b0  push    r14
0x1400049b2  mov     r11, rdx
0x1400049b5  xor     r10d, r10d
0x1400049b8  shr     r11, 1
0x1400049bb  mov     r14, r9
0x1400049be  mov     rdi, r8
0x1400049c1  mov     rbx, rdx
0x1400049c4  mov     rsi, rcx
0x1400049c7  jz      loc_140004A69
0x1400049cd  cmp     r11, 7FFFFFFFh
0x1400049d4  jbe     short loc_1400049E0
0x1400049d6  mov     edx, 0C000000Dh
0x1400049db  jmp     loc_140004A73
0x1400049e0  mov     eax, 7FFFFFFEh
0x1400049e5  mov     r8, r11
0x1400049e8  mov     r9, rsi
0x1400049eb  mov     rdx, r10
0x1400049ee  test    rax, rax
0x1400049f1  jz      short loc_140004A13
0x1400049f3  movzx   ecx, word ptr [rdi]
0x1400049f6  test    cx, cx
0x1400049f9  jz      short loc_140004A13
0x1400049fb  mov     [r9], cx
0x1400049ff  add     rdi, 2
0x140004a03  add     r9, 2
0x140004a07  dec     rax
0x140004a0a  inc     rdx
0x140004a0d  sub     r8, 1
0x140004a11  jnz     short loc_1400049EE
0x140004a13  test    r8, r8
0x140004a16  lea     rcx, [rdx-1]
0x140004a1a  mov     rax, r8
0x140004a1d  mov     edi, 80000005h
0x140004a22  cmovnz  rcx, rdx
0x140004a26  neg     rax
0x140004a29  lea     rax, [r9-2]
0x140004a2d  sbb     edx, edx
0x140004a2f  test    r8, r8
0x140004a32  not     edx
0x140004a34  cmovnz  rax, r9
0x140004a38  sub     r11, rcx
0x140004a3b  mov     [rax], r10w
0x140004a3f  lea     rax, [rsi+rcx*2]
0x140004a43  and     edx, edi
0x140004a45  jns     short loc_140004A4B
0x140004a47  cmp     edx, edi
0x140004a49  jnz     short loc_140004A77
0x140004a4b  test    r14, r14
0x140004a4e  jz      short loc_140004A53
0x140004a50  mov     [r14], rax
0x140004a53  mov     rcx, [rsp+20h+pcbRemaining]
0x140004a58  test    rcx, rcx
0x140004a5b  jz      short loc_140004A77
0x140004a5d  and     ebx, 1
0x140004a60  lea     rax, [rbx+r11*2]
0x140004a64  mov     [rcx], rax
0x140004a67  jmp     short loc_140004A77
0x140004a69  mov     edx, 0C000000Dh
0x140004a6e  test    r11, r11
0x140004a71  jz      short loc_140004A77
0x140004a73  mov     [rcx], r10w
0x140004a77  mov     eax, edx
0x140004a79  pop     r14
0x140004a7b  pop     rdi
0x140004a7c  pop     rsi
0x140004a7d  pop     rbx
0x140004a7e  retn
```
