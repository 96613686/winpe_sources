# RtlStringCchCopyExW

- ea: `0x14000c158`
- end: `0x14000c22c`
- name: `RtlStringCchCopyExW`
- size: `212`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc, NTSTRSAFE_PWSTR *ppszDestEnd, size_t *pcchRemaining, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400249d4`

## callees

- `0x14000c158`
- `0x14000c234`

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
  __int64 v7; // rdx
  _WORD *v8; // rcx
  _WORD *v9; // r8
  signed int v10; // r10d
  wchar_t *v11; // r11
  __int64 v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rbx
  __int64 v15; // rax
  _WORD *v16; // rcx

  v10 = RtlStringExValidateDestW(pszDest, cchDest, (const size_t)pszSrc, 0);
  if ( v10 < 0 )
  {
    if ( v7 )
      *v8 = 0;
  }
  else
  {
    if ( v7 )
    {
      v12 = 2147483646;
      v13 = v8;
      v14 = 0;
      do
      {
        if ( !v12 )
          break;
        if ( !*v9 )
          break;
        *v13++ = *v9++;
        --v12;
        ++v14;
        --v7;
      }
      while ( v7 );
      v15 = v14 - 1;
      v10 = v7 == 0 ? 0x80000005 : 0;
      v16 = v13 - 1;
      if ( v7 )
      {
        v16 = v13;
        v15 = v14;
      }
      *v16 = 0;
      v11 += v15;
    }
    else
    {
      v10 = 0;
      if ( *v9 )
      {
        if ( !v11 )
          return -1073741811;
        v10 = -2147483643;
      }
    }
    if ( ppszDestEnd )
      *ppszDestEnd = v11;
  }
  return v10;
}

```

## disassembly

```asm
0x14000c158  mov     [rsp+arg_0], rbx
0x14000c15d  mov     [rsp+arg_8], rsi
0x14000c162  push    rdi
0x14000c163  sub     rsp, 20h
0x14000c167  mov     rdi, r9
0x14000c16a  mov     r11, rcx
0x14000c16d  xor     r9d, r9d; dwFlags
0x14000c170  call    RtlStringExValidateDestW
0x14000c175  xor     esi, esi
0x14000c177  mov     r10d, eax
0x14000c17a  test    eax, eax
0x14000c17c  js      loc_14000C204
0x14000c182  test    rdx, rdx
0x14000c185  jz      loc_14000C20E
0x14000c18b  mov     eax, 7FFFFFFEh
0x14000c190  mov     r9, rcx
0x14000c193  mov     ebx, esi
0x14000c195  test    rax, rax
0x14000c198  jz      short loc_14000C1BB
0x14000c19a  movzx   ecx, word ptr [r8]
0x14000c19e  test    cx, cx
0x14000c1a1  jz      short loc_14000C1BB
0x14000c1a3  mov     [r9], cx
0x14000c1a7  add     r8, 2
0x14000c1ab  add     r9, 2
0x14000c1af  dec     rax
0x14000c1b2  inc     rbx
0x14000c1b5  sub     rdx, 1
0x14000c1b9  jnz     short loc_14000C195
0x14000c1bb  mov     rax, rdx
0x14000c1be  mov     r10d, 80000005h
0x14000c1c4  neg     rax
0x14000c1c7  lea     rax, [rbx-1]
0x14000c1cb  sbb     ecx, ecx
0x14000c1cd  not     ecx
0x14000c1cf  and     r10d, ecx
0x14000c1d2  lea     rcx, [r9-2]
0x14000c1d6  test    rdx, rdx
0x14000c1d9  cmovnz  rcx, r9
0x14000c1dd  cmovnz  rax, rbx
0x14000c1e1  mov     [rcx], si
0x14000c1e4  lea     r11, [r11+rax*2]
0x14000c1e8  test    rdi, rdi
0x14000c1eb  jz      short loc_14000C1F0
0x14000c1ed  mov     [rdi], r11
0x14000c1f0  mov     rbx, [rsp+28h+arg_0]
0x14000c1f5  mov     eax, r10d
0x14000c1f8  mov     rsi, [rsp+28h+arg_8]
0x14000c1fd  add     rsp, 20h
0x14000c201  pop     rdi
0x14000c202  retn
0x14000c204  test    rdx, rdx
0x14000c207  jz      short loc_14000C1F0
0x14000c209  mov     [rcx], si
0x14000c20c  jmp     short loc_14000C1F0
0x14000c20e  mov     r10d, esi
0x14000c211  cmp     [r8], si
0x14000c215  jz      short loc_14000C1E8
0x14000c217  test    r11, r11
0x14000c21a  jnz     short loc_14000C224
0x14000c21c  mov     r10d, 0C000000Dh
0x14000c222  jmp     short loc_14000C1F0
0x14000c224  mov     r10d, 80000005h
0x14000c22a  jmp     short loc_14000C1E8
```
