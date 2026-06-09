# WdmlibRtlInitUnicodeStringEx

- ea: `0x140004f04`
- end: `0x140004f4a`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140018e4c`
- `0x140019034`
- `0x1400191a0`
- `0x1400194c8`
- `0x140019528`
- `0x140019864`
- `0x14001990c`

## callees

- `0x140004f04`

## pseudocode

```c
NTSTATUS __stdcall WdmlibRtlInitUnicodeStringEx(PUNICODE_STRING DestinationString, PCWSTR SourceString)
{
  unsigned __int64 v2; // rax
  NTSTATUS result; // eax
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // r8

  if ( SourceString )
  {
    v2 = -1;
    do
      ++v2;
    while ( SourceString[v2] );
    if ( v2 > 0x7FFE )
      return -1073741562;
    v4 = 2 * v2;
    v5 = v4 + 2;
  }
  else
  {
    SourceString = 0;
    v5 = 0;
    v4 = 0;
  }
  DestinationString->Length = v4;
  result = 0;
  DestinationString->MaximumLength = v5;
  DestinationString->Buffer = (wchar_t *)SourceString;
  return result;
}

```

## disassembly

```asm
0x140004f04  xor     r9d, r9d
0x140004f07  test    rdx, rdx
0x140004f0a  jz      short loc_140004F32
0x140004f0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004f10  inc     rax
0x140004f13  cmp     [rdx+rax*2], r9w
0x140004f18  jnz     short loc_140004F10
0x140004f1a  cmp     rax, 7FFEh
0x140004f20  jbe     short loc_140004F29
0x140004f22  mov     eax, 0C0000106h
0x140004f27  retn
0x140004f29  add     ax, ax
0x140004f2c  lea     r8d, [rax+2]
0x140004f30  jmp     short loc_140004F3B
0x140004f32  mov     rdx, r9
0x140004f35  mov     r8d, r9d
0x140004f38  mov     eax, r9d
0x140004f3b  mov     [rcx], ax
0x140004f3e  xor     eax, eax
0x140004f40  mov     [rcx+2], r8w
0x140004f45  mov     [rcx+8], rdx
0x140004f49  retn
```
