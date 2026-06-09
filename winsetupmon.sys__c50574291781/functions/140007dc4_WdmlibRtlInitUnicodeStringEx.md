# WdmlibRtlInitUnicodeStringEx

- ea: `0x140007dc4`
- end: `0x140007e0a`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002104c`
- `0x140021234`
- `0x1400213a0`
- `0x14002161c`
- `0x1400216f0`
- `0x140021a2c`
- `0x140021ad4`

## callees

- `0x140007dc4`

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
0x140007dc4  xor     r9d, r9d
0x140007dc7  test    rdx, rdx
0x140007dca  jz      short loc_140007DF2
0x140007dcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007dd0  inc     rax
0x140007dd3  cmp     [rdx+rax*2], r9w
0x140007dd8  jnz     short loc_140007DD0
0x140007dda  cmp     rax, 7FFEh
0x140007de0  jbe     short loc_140007DE9
0x140007de2  mov     eax, 0C0000106h
0x140007de7  retn
0x140007de9  add     ax, ax
0x140007dec  lea     r8d, [rax+2]
0x140007df0  jmp     short loc_140007DFB
0x140007df2  mov     rdx, r9
0x140007df5  mov     r8d, r9d
0x140007df8  mov     eax, r9d
0x140007dfb  mov     [rcx], ax
0x140007dfe  xor     eax, eax
0x140007e00  mov     [rcx+2], r8w
0x140007e05  mov     [rcx+8], rdx
0x140007e09  retn
```
