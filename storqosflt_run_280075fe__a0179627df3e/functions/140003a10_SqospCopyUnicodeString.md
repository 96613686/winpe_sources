# SqospCopyUnicodeString

- ea: `0x140003a10`
- end: `0x140003a70`
- name: `SqospCopyUnicodeString`
- size: `96`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400046d0`
- `0x140006424`
- `0x1400111bc`

## callees

- `0x140003a10`
- `0x140003a80`
- `0x140003be0`

## pseudocode

```c
__int64 __fastcall SqospCopyUnicodeString(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)
{
  __int64 Length; // rdx
  __int64 result; // rax
  unsigned int v6; // esi

  Length = SourceString->Length;
  if ( (_WORD)Length == 0xFFFE )
    return 3221225734LL;
  LOWORD(Length) = Length + 2;
  result = SqospAllocateUnicodeString(DestinationString, Length);
  v6 = result;
  if ( (int)result >= 0 )
  {
    RtlUnicodeStringCopy(DestinationString, SourceString);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140003a10  mov     [rsp+arg_8], rbx
0x140003a15  push    rdi
0x140003a16  sub     rsp, 20h
0x140003a1a  mov     rbx, rdx
0x140003a1d  mov     eax, 0FFFEh
0x140003a22  movzx   edx, word ptr [rdx]
0x140003a25  mov     rdi, rcx
0x140003a28  cmp     dx, ax
0x140003a2b  jz      short loc_140003A5F
0x140003a2d  add     dx, 2
0x140003a31  mov     [rsp+28h+arg_0], rsi
0x140003a36  call    SqospAllocateUnicodeString
0x140003a3b  mov     esi, eax
0x140003a3d  test    eax, eax
0x140003a3f  js      short loc_140003A4E
0x140003a41  mov     rdx, rbx; SourceString
0x140003a44  mov     rcx, rdi; DestinationString
0x140003a47  call    RtlUnicodeStringCopy
0x140003a4c  mov     eax, esi
0x140003a4e  mov     rsi, [rsp+28h+arg_0]
0x140003a53  mov     rbx, [rsp+28h+arg_8]
0x140003a58  add     rsp, 20h
0x140003a5c  pop     rdi
0x140003a5d  retn
0x140003a5f  mov     rbx, [rsp+28h+arg_8]
0x140003a64  mov     eax, 0C0000106h
0x140003a69  add     rsp, 20h
0x140003a6d  pop     rdi
0x140003a6e  retn
```
