# AnsiToUnicode

- ea: `0x18000eea0`
- end: `0x18000eed3`
- name: `AnsiToUnicode`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007b40`
- `0x180007dc0`
- `0x180008030`
- `0x180008acc`

## callees

- `0x18000eea0`

## import_xrefs

- `ntdll!RtlMultiByteToUnicodeN` at `0x18000eec8`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000eec8`

## pseudocode

```c
NTSTATUS __fastcall AnsiToUnicode(WCHAR *a1, ULONG a2, const CHAR *a3)
{
  __int64 v3; // rax
  ULONG BytesInUnicodeString; // [rsp+58h] [rbp+20h] BYREF

  BytesInUnicodeString = 0;
  v3 = -1;
  do
    ++v3;
  while ( a3[v3] );
  return RtlMultiByteToUnicodeN(a1, a2, &BytesInUnicodeString, a3, v3 + 1);
}

```

## disassembly

```asm
0x18000eea0  sub     rsp, 38h
0x18000eea4  mov     [rsp+38h+BytesInUnicodeString], 0
0x18000eeac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eeb0  inc     rax
0x18000eeb3  cmp     byte ptr [r8+rax], 0
0x18000eeb8  jnz     short loc_18000EEB0
0x18000eeba  inc     eax
0x18000eebc  mov     r9, r8; MultiByteString
0x18000eebf  lea     r8, [rsp+38h+BytesInUnicodeString]; BytesInUnicodeString
0x18000eec4  mov     [rsp+38h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18000eec8  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000eece  add     rsp, 38h
0x18000eed2  retn
```
