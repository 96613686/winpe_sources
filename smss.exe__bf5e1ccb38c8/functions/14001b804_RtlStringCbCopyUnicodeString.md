# RtlStringCbCopyUnicodeString

- ea: `0x14001b804`
- end: `0x14001b89e`
- name: `RtlStringCbCopyUnicodeString`
- size: `154`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b67c`

## callees

- `0x14001b804`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyUnicodeString(NTSTRSAFE_PWSTR pszDest, size_t cbDest, PCUNICODE_STRING SourceString)
{
  size_t v3; // rdx
  NTSTRSAFE_PWSTR v5; // r9
  USHORT MaximumLength; // ax
  PWSTR Buffer; // r8
  unsigned __int64 v8; // rcx
  NTSTRSAFE_PWSTR v9; // rcx

  v3 = cbDest >> 1;
  v5 = pszDest;
  if ( v3 - 1 > 0x7FFE )
    return -1073741811;
  if ( (SourceString->Length & 1) != 0
    || (MaximumLength = SourceString->MaximumLength, (MaximumLength & 1) != 0)
    || SourceString->Length > MaximumLength
    || MaximumLength == 0xFFFF
    || (Buffer = SourceString->Buffer) == 0 && (SourceString->Length || MaximumLength) )
  {
    *pszDest = 0;
    return -1073741811;
  }
  v8 = (unsigned __int64)SourceString->Length >> 1;
  do
  {
    if ( !v8 )
      break;
    --v8;
    *v5++ = *Buffer++;
    --v3;
  }
  while ( v3 );
  v9 = v5 - 1;
  if ( v3 )
    v9 = v5;
  *v9 = 0;
  return v3 == 0 ? 0x80000005 : 0;
}

```

## disassembly

```asm
0x14001b804  shr     rdx, 1
0x14001b807  mov     r10, r8
0x14001b80a  mov     r9, rcx
0x14001b80d  lea     rax, [rdx-1]
0x14001b811  cmp     rax, 7FFEh
0x14001b817  ja      short loc_14001B896
0x14001b819  xor     r11d, r11d
0x14001b81c  test    byte ptr [r8], 1
0x14001b820  jnz     short loc_14001B892
0x14001b822  movzx   eax, word ptr [r8+2]
0x14001b827  test    al, 1
0x14001b829  jnz     short loc_14001B892
0x14001b82b  cmp     [r8], ax
0x14001b82f  ja      short loc_14001B892
0x14001b831  mov     ecx, 0FFFEh
0x14001b836  cmp     ax, cx
0x14001b839  ja      short loc_14001B892
0x14001b83b  mov     r8, [r8+8]
0x14001b83f  test    r8, r8
0x14001b842  jnz     short loc_14001B84F
0x14001b844  cmp     [r10], r11w
0x14001b848  jnz     short loc_14001B892
0x14001b84a  test    ax, ax
0x14001b84d  jnz     short loc_14001B892
0x14001b84f  movzx   ecx, word ptr [r10]
0x14001b853  shr     rcx, 1
0x14001b856  test    rcx, rcx
0x14001b859  jz      short loc_14001B874
0x14001b85b  movzx   eax, word ptr [r8]
0x14001b85f  dec     rcx
0x14001b862  mov     [r9], ax
0x14001b866  add     r8, 2
0x14001b86a  add     r9, 2
0x14001b86e  sub     rdx, 1
0x14001b872  jnz     short loc_14001B856
0x14001b874  test    rdx, rdx
0x14001b877  lea     rcx, [r9-2]
0x14001b87b  cmovnz  rcx, r9
0x14001b87f  neg     rdx
0x14001b882  mov     [rcx], r11w
0x14001b886  sbb     ecx, ecx
0x14001b888  not     ecx
0x14001b88a  and     ecx, 80000005h
0x14001b890  jmp     short loc_14001B89B
0x14001b892  mov     [r9], r11w
0x14001b896  mov     ecx, 0C000000Dh
0x14001b89b  mov     eax, ecx
0x14001b89d  retn
```
