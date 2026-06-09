# RtlStringCchCopyExW

- ea: `0x140003f64`
- end: `0x140004023`
- name: `RtlStringCchCopyExW`
- size: `191`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc, NTSTRSAFE_PWSTR *ppszDestEnd, size_t *pcchRemaining, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400112f0`

## callees

- `0x140003f64`
- `0x14000402c`

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
  size_t v7; // rbx
  wchar_t *v8; // rdi
  NTSTATUS v9; // r8d
  size_t v11; // [rsp+20h] [rbp-18h]
  size_t pcchNewDestLength; // [rsp+50h] [rbp+18h] BYREF

  pcchNewDestLength = (size_t)pszSrc;
  v7 = cchDest;
  v8 = pszDest;
  if ( !pszDest && cchDest || cchDest > 0x7FFFFFFF )
  {
    v9 = -1073741811;
    *pszDest = 0;
    return v9;
  }
  if ( cchDest )
  {
    pcchNewDestLength = 0;
    v9 = RtlStringCopyWorkerW(pszDest, cchDest, &pcchNewDestLength, L"{", v11);
    v7 -= pcchNewDestLength;
    v8 += pcchNewDestLength;
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147483643 )
      return v9;
  }
  else
  {
    if ( !pszDest )
      return -1073741811;
    v9 = -2147483643;
  }
  if ( ppszDestEnd )
    *ppszDestEnd = v8;
  if ( pcchRemaining )
    *pcchRemaining = v7;
  return v9;
}

```

## disassembly

```asm
0x140003f64  mov     [rsp+arg_0], rbx
0x140003f69  mov     [rsp+arg_8], rsi
0x140003f6e  mov     [rsp+pcchNewDestLength], r8
0x140003f73  push    rdi
0x140003f74  sub     rsp, 30h
0x140003f78  mov     rsi, r9
0x140003f7b  mov     rbx, rdx
0x140003f7e  mov     rdi, rcx
0x140003f81  test    rcx, rcx
0x140003f84  jnz     short loc_140003F8B
0x140003f86  test    rdx, rdx
0x140003f89  jnz     short loc_140003F94
0x140003f8b  cmp     rbx, 7FFFFFFFh
0x140003f92  jbe     short loc_140003FA1
0x140003f94  xor     eax, eax
0x140003f96  mov     r8d, 0C000000Dh
0x140003f9c  mov     [rcx], ax
0x140003f9f  jmp     short loc_14000400F
0x140003fa1  test    rbx, rbx
0x140003fa4  jnz     short loc_140003FBB
0x140003fa6  test    rdi, rdi
0x140003fa9  jnz     short loc_140003FB3
0x140003fab  mov     r8d, 0C000000Dh
0x140003fb1  jmp     short loc_14000400F
0x140003fb3  mov     r8d, 80000005h
0x140003fb9  jmp     short loc_140003FFA
0x140003fbb  lea     r9, pszSrc; "{"
0x140003fc2  mov     [rsp+38h+pcchNewDestLength], 0
0x140003fcb  lea     r8, [rsp+38h+pcchNewDestLength]; pcchNewDestLength
0x140003fd0  call    RtlStringCopyWorkerW
0x140003fd5  mov     rcx, [rsp+38h+pcchNewDestLength]
0x140003fda  mov     r8d, eax
0x140003fdd  mov     eax, 80000000h
0x140003fe2  sub     rbx, rcx
0x140003fe5  lea     rdi, [rdi+rcx*2]
0x140003fe9  lea     ecx, [r8+rax]
0x140003fed  test    eax, ecx
0x140003fef  jnz     short loc_140003FFA
0x140003ff1  cmp     r8d, 80000005h
0x140003ff8  jnz     short loc_14000400F
0x140003ffa  test    rsi, rsi
0x140003ffd  jz      short loc_140004002
0x140003fff  mov     [rsi], rdi
0x140004002  mov     rax, [rsp+38h+pcchRemaining]
0x140004007  test    rax, rax
0x14000400a  jz      short loc_14000400F
0x14000400c  mov     [rax], rbx
0x14000400f  mov     rbx, [rsp+38h+arg_0]
0x140004014  mov     eax, r8d
0x140004017  mov     rsi, [rsp+38h+arg_8]
0x14000401c  add     rsp, 30h
0x140004020  pop     rdi
0x140004021  retn
```
