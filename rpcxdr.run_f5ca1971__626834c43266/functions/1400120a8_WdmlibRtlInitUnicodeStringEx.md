# WdmlibRtlInitUnicodeStringEx

- ea: `0x1400120a8`
- end: `0x1400120ee`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140021c0c`
- `0x140021df4`
- `0x140021f60`
- `0x140022288`
- `0x1400222e8`
- `0x140022624`
- `0x1400226cc`

## callees

- `0x1400120a8`

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
0x1400120a8  xor     r9d, r9d
0x1400120ab  test    rdx, rdx
0x1400120ae  jz      short loc_1400120D6
0x1400120b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400120b4  inc     rax
0x1400120b7  cmp     [rdx+rax*2], r9w
0x1400120bc  jnz     short loc_1400120B4
0x1400120be  cmp     rax, 7FFEh
0x1400120c4  jbe     short loc_1400120CD
0x1400120c6  mov     eax, 0C0000106h
0x1400120cb  retn
0x1400120cd  add     ax, ax
0x1400120d0  lea     r8d, [rax+2]
0x1400120d4  jmp     short loc_1400120DF
0x1400120d6  mov     rdx, r9
0x1400120d9  mov     r8d, r9d
0x1400120dc  mov     eax, r9d
0x1400120df  mov     [rcx], ax
0x1400120e2  xor     eax, eax
0x1400120e4  mov     [rcx+2], r8w
0x1400120e9  mov     [rcx+8], rdx
0x1400120ed  retn
```
