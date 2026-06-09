# RtlWideCharArrayCopyWorker

- ea: `0x140003ce0`
- end: `0x140003d2f`
- name: `RtlWideCharArrayCopyWorker`
- size: `79`
- prototype: `NTSTATUS __stdcall(wchar_t *pszDest, size_t cchDest, size_t *pcchNewDestLength, const wchar_t *pszSrc, size_t cchSrcLength)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005c48`

## callees

- `0x140003ce0`

## pseudocode

```c
NTSTATUS __stdcall RtlWideCharArrayCopyWorker(
        wchar_t *pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        const wchar_t *pszSrc,
        size_t cchSrcLength)
{
  NTSTATUS v6; // ebx
  size_t v7; // r11
  NTSTATUS result; // eax

  v6 = 0;
  v7 = 0;
  if ( cchDest )
  {
    while ( cchSrcLength )
    {
      --cchSrcLength;
      *pszDest++ = *pszSrc++;
      ++v7;
      if ( !--cchDest )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    if ( cchSrcLength )
      v6 = -2147483643;
  }
  result = v6;
  *pcchNewDestLength = v7;
  return result;
}

```

## disassembly

```asm
0x140003ce0  mov     [rsp+arg_0], rbx
0x140003ce5  mov     rax, [rsp+arg_20]
0x140003cea  xor     ebx, ebx
0x140003cec  xor     r11d, r11d
0x140003cef  mov     r10, rcx
0x140003cf2  test    rdx, rdx
0x140003cf5  jz      short loc_140003D18
0x140003cf7  test    rax, rax
0x140003cfa  jz      short loc_140003D23
0x140003cfc  movzx   ecx, word ptr [r9]
0x140003d00  dec     rax
0x140003d03  mov     [r10], cx
0x140003d07  add     r9, 2
0x140003d0b  add     r10, 2
0x140003d0f  inc     r11
0x140003d12  sub     rdx, 1
0x140003d16  jnz     short loc_140003CF7
0x140003d18  test    rax, rax
0x140003d1b  mov     ecx, 80000005h
0x140003d20  cmovnz  ebx, ecx
0x140003d23  mov     eax, ebx
0x140003d25  mov     [r8], r11
0x140003d28  mov     rbx, [rsp+arg_0]
0x140003d2d  retn
```
