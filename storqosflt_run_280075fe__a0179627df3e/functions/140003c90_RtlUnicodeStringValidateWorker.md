# RtlUnicodeStringValidateWorker

- ea: `0x140003c90`
- end: `0x140003cd3`
- name: `RtlUnicodeStringValidateWorker`
- size: `67`
- prototype: `NTSTATUS __stdcall(PCUNICODE_STRING SourceString, const size_t cchMax, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039d0`
- `0x140003b70`
- `0x140003be0`

## callees

- `0x140003c90`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringValidateWorker(PCUNICODE_STRING SourceString, const size_t cchMax, ULONG dwFlags)
{
  USHORT Length; // dx
  USHORT MaximumLength; // r8

  Length = SourceString->Length;
  if ( (SourceString->Length & 1) != 0 )
    return -1073741811;
  MaximumLength = SourceString->MaximumLength;
  if ( (MaximumLength & 1) != 0
    || Length > MaximumLength
    || MaximumLength == 0xFFFF
    || !SourceString->Buffer && (Length || MaximumLength) )
  {
    return -1073741811;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140003c90  movzx   edx, word ptr [rcx]
0x140003c93  test    dl, 1
0x140003c96  jnz     short loc_140003CBF
0x140003c98  movzx   r8d, word ptr [rcx+2]
0x140003c9d  test    r8b, 1
0x140003ca1  jnz     short loc_140003CBF
0x140003ca3  cmp     dx, r8w
0x140003ca7  ja      short loc_140003CBF
0x140003ca9  mov     eax, 0FFFEh
0x140003cae  cmp     r8w, ax
0x140003cb2  ja      short loc_140003CBF
0x140003cb4  cmp     qword ptr [rcx+8], 0
0x140003cb9  jz      short loc_140003CC6
0x140003cbb  xor     eax, eax
0x140003cbd  retn
0x140003cbf  mov     eax, 0C000000Dh
0x140003cc4  retn
0x140003cc6  test    dx, dx
0x140003cc9  jnz     short loc_140003CBF
0x140003ccb  test    r8w, r8w
0x140003ccf  jnz     short loc_140003CBF
0x140003cd1  jmp     short loc_140003CBB
```
