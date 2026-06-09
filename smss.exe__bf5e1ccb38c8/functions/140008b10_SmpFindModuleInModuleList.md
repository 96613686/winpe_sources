# SmpFindModuleInModuleList

- ea: `0x140008b10`
- end: `0x140008ba1`
- name: `SmpFindModuleInModuleList`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008470`

## callees

- `0x140008b10`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140008b7b`
- `ntdll!RtlCompareUnicodeString` at `0x140008b7b`

## pseudocode

```c
__int64 __fastcall SmpFindModuleInModuleList(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v2; // rbx
  __int16 v4; // cx
  UNICODE_STRING String1; // [rsp+20h] [rbp-38h] BYREF

  v2 = SmpKnownDllsList;
  String1 = 0;
  while ( (__int64 *)v2 != &SmpKnownDllsList )
  {
    String1 = *(UNICODE_STRING *)(v2 + 16);
    if ( *(_WORD *)(v2 + 16) )
    {
      v4 = **(_WORD **)(v2 + 24);
      if ( v4 == 95 || v4 == 42 )
      {
        ++String1.Buffer;
        String1.Length -= 2;
        String1.MaximumLength -= 2;
      }
    }
    if ( !RtlCompareUnicodeString(&String1, a2, 1u) )
      return v2;
    v2 = *(_QWORD *)v2;
  }
  return 0;
}

```

## disassembly

```asm
0x140008b10  push    rbx
0x140008b12  push    rbp
0x140008b13  push    rsi
0x140008b14  push    rdi
0x140008b15  sub     rsp, 38h
0x140008b19  mov     rbx, cs:SmpKnownDllsList
0x140008b20  lea     rbp, SmpKnownDllsList
0x140008b27  xorps   xmm0, xmm0
0x140008b2a  mov     rdi, rdx
0x140008b2d  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140008b32  mov     esi, 0FFFEh
0x140008b37  cmp     rbx, rbp
0x140008b3a  jz      short loc_140008B96
0x140008b3c  movups  xmm0, xmmword ptr [rbx+10h]
0x140008b40  xor     eax, eax
0x140008b42  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140008b47  cmp     ax, [rbx+10h]
0x140008b4b  jnb     short loc_140008B70
0x140008b4d  mov     rax, [rbx+18h]
0x140008b51  movzx   ecx, word ptr [rax]
0x140008b54  cmp     cx, 5Fh ; '_'
0x140008b58  jz      short loc_140008B60
0x140008b5a  cmp     cx, 2Ah ; '*'
0x140008b5e  jnz     short loc_140008B70
0x140008b60  add     [rsp+58h+String1.Buffer], 2
0x140008b66  add     [rsp+58h+String1.Length], si
0x140008b6b  add     [rsp+58h+String1.MaximumLength], si
0x140008b70  mov     r8b, 1; CaseInSensitive
0x140008b73  lea     rcx, [rsp+58h+String1]; String1
0x140008b78  mov     rdx, rdi; String2
0x140008b7b  call    cs:__imp_RtlCompareUnicodeString
0x140008b81  test    eax, eax
0x140008b83  jz      short loc_140008B8A
0x140008b85  mov     rbx, [rbx]
0x140008b88  jmp     short loc_140008B37
0x140008b8a  mov     rax, rbx
0x140008b8d  add     rsp, 38h
0x140008b91  pop     rdi
0x140008b92  pop     rsi
0x140008b93  pop     rbp
0x140008b94  pop     rbx
0x140008b95  retn
0x140008b96  xor     eax, eax
0x140008b98  add     rsp, 38h
0x140008b9c  pop     rdi
0x140008b9d  pop     rsi
0x140008b9e  pop     rbp
0x140008b9f  pop     rbx
0x140008ba0  retn
```
