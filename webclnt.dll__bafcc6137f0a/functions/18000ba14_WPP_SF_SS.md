# WPP_SF_SS

- ea: `0x18000ba14`
- end: `0x18000bab9`
- name: `WPP_SF_SS`
- size: `165`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *, __int64)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005a38`
- `0x180006d20`
- `0x180009480`
- `0x1800099d0`
- `0x18000a770`
- `0x18000fce0`
- `0x180010ffc`
- `0x1800196d0`
- `0x18001bbe0`
- `0x18001ca70`
- `0x18001dfc0`
- `0x180029dcc`
- `0x18002a5e8`
- `0x18002a964`

## callees

- `0x18000ba14`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000baa3`
- `ntdll!EtwTraceMessage` at `0x18000baa3`

## pseudocode

```c
__int64 __fastcall WPP_SF_SS(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, __int64 a5)
{
  __int64 v5; // r10
  __int64 v6; // rax
  bool v7; // zf

  v5 = -1;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a5 + 2 * v6) );
  }
  v7 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = a4 == 0;
  }
  if ( v7 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000ba14  mov     [rsp+arg_0], rbx
0x18000ba19  mov     [rsp+arg_8], rsi
0x18000ba1e  push    rdi
0x18000ba1f  sub     rsp, 50h
0x18000ba23  mov     r11, [rsp+58h+arg_20]
0x18000ba2b  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000ba2f  xor     edi, edi
0x18000ba31  mov     ebx, 0Ah
0x18000ba36  test    r11, r11
0x18000ba39  jz      short loc_18000BA52
0x18000ba3b  mov     rax, r10
0x18000ba3e  inc     rax
0x18000ba41  cmp     [r11+rax*2], di
0x18000ba46  jnz     short loc_18000BA3E
0x18000ba48  lea     rax, ds:2[rax*2]
0x18000ba50  jmp     short loc_18000BA55
0x18000ba52  mov     rax, rbx
0x18000ba55  test    r11, r11
0x18000ba58  lea     rsi, aNull_0; "NULL"
0x18000ba5f  cmovz   r11, rsi
0x18000ba63  test    r9, r9
0x18000ba66  jz      short loc_18000BA7D
0x18000ba68  inc     r10
0x18000ba6b  cmp     [r9+r10*2], di
0x18000ba70  jnz     short loc_18000BA68
0x18000ba72  lea     rbx, ds:2[r10*2]
0x18000ba7a  test    r9, r9
0x18000ba7d  mov     [rsp+58h+var_18], rdi
0x18000ba82  cmovz   r9, rsi
0x18000ba86  mov     [rsp+58h+var_20], rax
0x18000ba8b  mov     [rsp+58h+var_28], r11
0x18000ba90  mov     [rsp+58h+var_30], rbx
0x18000ba95  mov     [rsp+58h+var_38], r9
0x18000ba9a  movzx   r9d, dx
0x18000ba9e  mov     edx, 2Bh ; '+'
0x18000baa3  call    cs:__imp_EtwTraceMessage
0x18000baa9  mov     rbx, [rsp+58h+arg_0]
0x18000baae  mov     rsi, [rsp+58h+arg_8]
0x18000bab3  add     rsp, 50h
0x18000bab7  pop     rdi
0x18000bab8  retn
```
