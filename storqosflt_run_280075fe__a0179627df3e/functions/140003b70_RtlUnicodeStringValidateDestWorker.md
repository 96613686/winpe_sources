# RtlUnicodeStringValidateDestWorker

- ea: `0x140003b70`
- end: `0x140003bcd`
- name: `RtlUnicodeStringValidateDestWorker`
- size: `93`
- prototype: `NTSTATUS __stdcall(PCUNICODE_STRING DestinationString, wchar_t **ppszDest, size_t *pcchDest, size_t *pcchDestLength, const size_t cchMax, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046d0`
- `0x140005c48`
- `0x140005d04`

## callees

- `0x140003b70`
- `0x140003c90`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringValidateDestWorker(
        PCUNICODE_STRING DestinationString,
        wchar_t **ppszDest,
        size_t *pcchDest,
        size_t *pcchDestLength,
        const size_t cchMax,
        ULONG dwFlags)
{
  NTSTATUS result; // eax
  unsigned __int16 *v8; // rcx
  unsigned __int64 *v9; // r10
  unsigned __int64 *v10; // r11

  *ppszDest = 0;
  *pcchDest = 0;
  if ( pcchDestLength )
    *pcchDestLength = 0;
  result = RtlUnicodeStringValidateWorker(DestinationString, (const size_t)ppszDest, (ULONG)pcchDest);
  if ( result >= 0 && v8 )
  {
    *ppszDest = (wchar_t *)*((_QWORD *)v8 + 1);
    *v10 = (unsigned __int64)v8[1] >> 1;
    if ( v9 )
      *v9 = (unsigned __int64)*v8 >> 1;
  }
  return result;
}

```

## disassembly

```asm
0x140003b70  push    rbx
0x140003b72  sub     rsp, 20h
0x140003b76  xor     eax, eax
0x140003b78  mov     r10, r9
0x140003b7b  mov     [rdx], rax
0x140003b7e  mov     r11, r8
0x140003b81  mov     [r8], rax
0x140003b84  mov     rbx, rdx
0x140003b87  test    r9, r9
0x140003b8a  jnz     short loc_140003BBA
0x140003b8c  call    RtlUnicodeStringValidateWorker
0x140003b91  mov     r9d, eax
0x140003b94  test    eax, eax
0x140003b96  js      short loc_140003BB3
0x140003b98  test    rcx, rcx
0x140003b9b  jz      short loc_140003BB3
0x140003b9d  mov     rdx, [rcx+8]
0x140003ba1  mov     [rbx], rdx
0x140003ba4  movzx   edx, word ptr [rcx+2]
0x140003ba8  shr     rdx, 1
0x140003bab  mov     [r11], rdx
0x140003bae  test    r10, r10
0x140003bb1  jnz     short loc_140003BBF
0x140003bb3  add     rsp, 20h
0x140003bb7  pop     rbx
0x140003bb8  retn
0x140003bba  mov     [r9], rax
0x140003bbd  jmp     short loc_140003B8C
0x140003bbf  movzx   eax, word ptr [rcx]
0x140003bc2  shr     rax, 1
0x140003bc5  mov     [r10], rax
0x140003bc8  mov     eax, r9d
0x140003bcb  jmp     short loc_140003BB3
```
