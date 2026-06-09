# RtlUnicodeStringCopy

- ea: `0x140003be0`
- end: `0x140003c86`
- name: `RtlUnicodeStringCopy`
- size: `166`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a10`
- `0x1400046d0`

## callees

- `0x140003be0`
- `0x140003c90`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringCopy(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)
{
  ULONG v2; // r8d
  NTSTATUS result; // eax
  size_t v6; // rdx
  ULONG v7; // r8d
  __int64 v8; // r9
  _WORD *v9; // r10
  int v10; // r11d
  PWSTR Buffer; // r8
  unsigned __int64 v12; // rax
  __int16 v13; // dx

  result = RtlUnicodeStringValidateWorker(DestinationString, (const size_t)SourceString, v2);
  if ( result >= 0 )
  {
    v10 = RtlUnicodeStringValidateWorker(SourceString, v6, v7);
    if ( v10 < 0 )
    {
      v13 = 0;
    }
    else
    {
      Buffer = 0;
      v12 = 0;
      if ( SourceString )
      {
        Buffer = SourceString->Buffer;
        v12 = (unsigned __int64)SourceString->Length >> 1;
      }
      v10 = 0;
      v13 = 0;
      if ( v8 )
      {
        while ( v12 )
        {
          --v12;
          *v9++ = *Buffer++;
          ++v13;
          if ( !--v8 )
            goto LABEL_8;
        }
      }
      else
      {
LABEL_8:
        if ( v12 )
          v10 = -2147483643;
      }
    }
    result = v10;
    DestinationString->Length = 2 * v13;
  }
  return result;
}

```

## disassembly

```asm
0x140003be0  mov     [rsp+arg_0], rbx
0x140003be5  push    rdi
0x140003be6  sub     rsp, 20h
0x140003bea  mov     rdi, rdx
0x140003bed  mov     rbx, rcx
0x140003bf0  call    RtlUnicodeStringValidateWorker
0x140003bf5  test    eax, eax
0x140003bf7  js      short loc_140003C76
0x140003bf9  xor     r10d, r10d
0x140003bfc  xor     r9d, r9d
0x140003bff  test    rcx, rcx
0x140003c02  jz      short loc_140003C10
0x140003c04  movzx   r9d, word ptr [rcx+2]
0x140003c09  mov     r10, [rcx+8]
0x140003c0d  shr     r9, 1
0x140003c10  mov     rcx, rdi; SourceString
0x140003c13  call    RtlUnicodeStringValidateWorker
0x140003c18  mov     r11d, eax
0x140003c1b  test    eax, eax
0x140003c1d  js      short loc_140003C82
0x140003c1f  xor     r8d, r8d
0x140003c22  xor     eax, eax
0x140003c24  test    rdi, rdi
0x140003c27  jz      short loc_140003C33
0x140003c29  movzx   eax, word ptr [rdi]
0x140003c2c  mov     r8, [rdi+8]
0x140003c30  shr     rax, 1
0x140003c33  xor     r11d, r11d
0x140003c36  xor     edx, edx
0x140003c38  test    r9, r9
0x140003c3b  jz      short loc_140003C61
0x140003c3d  nop     dword ptr [rax]
0x140003c40  test    rax, rax
0x140003c43  jz      short loc_140003C6D
0x140003c45  movzx   ecx, word ptr [r8]
0x140003c49  dec     rax
0x140003c4c  mov     [r10], cx
0x140003c50  add     r8, 2
0x140003c54  add     r10, 2
0x140003c58  inc     rdx
0x140003c5b  sub     r9, 1
0x140003c5f  jnz     short loc_140003C40
0x140003c61  test    rax, rax
0x140003c64  mov     ecx, 80000005h
0x140003c69  cmovnz  r11d, ecx
0x140003c6d  add     dx, dx
0x140003c70  mov     eax, r11d
0x140003c73  mov     [rbx], dx
0x140003c76  mov     rbx, [rsp+28h+arg_0]
0x140003c7b  add     rsp, 20h
0x140003c7f  pop     rdi
0x140003c80  retn
0x140003c82  xor     edx, edx
0x140003c84  jmp     short loc_140003C6D
```
