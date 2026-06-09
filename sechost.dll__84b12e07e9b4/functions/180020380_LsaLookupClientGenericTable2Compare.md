# LsaLookupClientGenericTable2Compare

- ea: `0x180020380`
- end: `0x1800203d9`
- name: `LsaLookupClientGenericTable2Compare`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020380`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002039b`
- `ntdll!RtlCompareUnicodeString` at `0x1800203b3`
- `ntdll!RtlCompareUnicodeString` at `0x18002039b`
- `ntdll!RtlCompareUnicodeString` at `0x1800203b3`

## pseudocode

```c
__int64 __fastcall LsaLookupClientGenericTable2Compare(__int64 a1, __int64 a2)
{
  LONG v4; // r9d

  v4 = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 40), (PCUNICODE_STRING)(a2 + 40), 1u);
  if ( v4 )
    return v4 > 0;
  v4 = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 24), (PCUNICODE_STRING)(a2 + 24), 1u);
  if ( v4 )
    return v4 > 0;
  else
    return 2;
}

```

## disassembly

```asm
0x180020380  mov     [rsp+arg_0], rbx
0x180020385  push    rdi
0x180020386  sub     rsp, 20h
0x18002038a  mov     rbx, rdx
0x18002038d  mov     rdi, rcx
0x180020390  add     rdx, 28h ; '('; String2
0x180020394  add     rcx, 28h ; '('; String1
0x180020398  mov     r8b, 1; CaseInsensitive
0x18002039b  call    cs:__imp_RtlCompareUnicodeString
0x1800203a1  mov     r9d, eax
0x1800203a4  test    eax, eax
0x1800203a6  jnz     short loc_1800203C6
0x1800203a8  lea     rdx, [rbx+18h]; String2
0x1800203ac  mov     r8b, 1; CaseInsensitive
0x1800203af  lea     rcx, [rdi+18h]; String1
0x1800203b3  call    cs:__imp_RtlCompareUnicodeString
0x1800203b9  mov     r9d, eax
0x1800203bc  test    eax, eax
0x1800203be  jnz     short loc_1800203C6
0x1800203c0  lea     eax, [r9+2]
0x1800203c4  jmp     short loc_1800203CE
0x1800203c6  xor     eax, eax
0x1800203c8  test    r9d, r9d
0x1800203cb  setnle  al
0x1800203ce  mov     rbx, [rsp+28h+arg_0]
0x1800203d3  add     rsp, 20h
0x1800203d7  pop     rdi
0x1800203d8  retn
```
