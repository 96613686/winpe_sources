# ApiSetpSearchForHostOverrideIndex_V7

- ea: `0x140018d84`
- end: `0x140018e0e`
- name: `ApiSetpSearchForHostOverrideIndex_V7`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001860c`

## callees

- `0x140018d84`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x140018de6`
- `ntdll!RtlCompareUnicodeStrings` at `0x140018de6`

## pseudocode

```c
__int64 __fastcall ApiSetpSearchForHostOverrideIndex_V7(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        const WCHAR *a4,
        unsigned __int16 a5)
{
  unsigned int i; // ebx
  __int64 v10; // rcx
  __int64 v11; // rbp

  if ( a3 )
  {
    for ( i = 0; i < a3; ++i )
    {
      v10 = *(unsigned __int16 *)(a1 + 18);
      v11 = *(unsigned int *)(a1 + 104) + a2 * (unsigned __int64)*(unsigned __int16 *)(a1 + 114) - v10;
      if ( !RtlCompareUnicodeStrings(
              a4,
              a5,
              (PCWCH)(a1 + *(unsigned int *)(a1 + 36) + (unsigned __int64)*(unsigned int *)(a1 + v11 + 4) - v10),
              *(unsigned __int16 *)(a1 + v11 + 12),
              1u) )
        return a2;
      a2 = *(unsigned __int16 *)(a1 + v11);
    }
  }
  return 0xFFFF;
}

```

## disassembly

```asm
0x140018d84  push    rbx
0x140018d86  push    rbp
0x140018d87  push    rsi
0x140018d88  push    rdi
0x140018d89  push    r14
0x140018d8b  push    r15
0x140018d8d  sub     rsp, 38h
0x140018d91  mov     r15, r9
0x140018d94  mov     r14d, r8d
0x140018d97  mov     edi, edx
0x140018d99  mov     rsi, rcx
0x140018d9c  test    r8d, r8d
0x140018d9f  jz      short loc_140018DFC
0x140018da1  xor     ebx, ebx
0x140018da3  cmp     ebx, r14d
0x140018da6  jnb     short loc_140018DFC
0x140018da8  movzx   ecx, word ptr [rsi+12h]
0x140018dac  movzx   ebp, word ptr [rsi+72h]
0x140018db0  movzx   edx, [rsp+68h+arg_20]; String1Length
0x140018db8  mov     eax, edi
0x140018dba  imul    rbp, rax
0x140018dbe  mov     eax, [rsi+68h]
0x140018dc1  add     rbp, rax
0x140018dc4  mov     [rsp+68h+CaseInSensitive], 1; CaseInSensitive
0x140018dc9  mov     eax, [rsi+24h]
0x140018dcc  sub     rbp, rcx
0x140018dcf  mov     r8d, [rsi+rbp+4]
0x140018dd4  movzx   r9d, word ptr [rsi+rbp+0Ch]; String2Length
0x140018dda  add     r8, rax
0x140018ddd  sub     r8, rcx
0x140018de0  mov     rcx, r15; String1
0x140018de3  add     r8, rsi; String2
0x140018de6  call    cs:__imp_RtlCompareUnicodeStrings
0x140018dec  test    eax, eax
0x140018dee  jz      short loc_140018DF8
0x140018df0  movzx   edi, word ptr [rsi+rbp]
0x140018df4  inc     ebx
0x140018df6  jmp     short loc_140018DA3
0x140018df8  mov     eax, edi
0x140018dfa  jmp     short loc_140018E01
0x140018dfc  mov     eax, 0FFFFh
0x140018e01  add     rsp, 38h
0x140018e05  pop     r15
0x140018e07  pop     r14
0x140018e09  pop     rdi
0x140018e0a  pop     rsi
0x140018e0b  pop     rbp
0x140018e0c  pop     rbx
0x140018e0d  retn
```
