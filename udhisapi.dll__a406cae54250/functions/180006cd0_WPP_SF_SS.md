# WPP_SF_SS

- ea: `0x180006cd0`
- end: `0x180006d73`
- name: `WPP_SF_SS`
- size: `163`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000512c`
- `0x180005674`

## callees

- `0x180006cd0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180006d62`
- `ntdll!EtwTraceMessage` at `0x180006d62`

## pseudocode

```c
__int64 __fastcall WPP_SF_SS(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, __int64 a5)
{
  __int64 v5; // r8
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
  return EtwTraceMessage(a1, 43, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x180006cd0  mov     [rsp+arg_0], rbx
0x180006cd5  push    rdi
0x180006cd6  sub     rsp, 50h
0x180006cda  mov     r10, [rsp+58h+arg_20]
0x180006ce2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006ce6  xor     ebx, ebx
0x180006ce8  mov     r11d, 0Ah
0x180006cee  test    r10, r10
0x180006cf1  jz      short loc_180006D0A
0x180006cf3  mov     rax, r8
0x180006cf6  inc     rax
0x180006cf9  cmp     [r10+rax*2], bx
0x180006cfe  jnz     short loc_180006CF6
0x180006d00  lea     rax, ds:2[rax*2]
0x180006d08  jmp     short loc_180006D0D
0x180006d0a  mov     rax, r11
0x180006d0d  test    r10, r10
0x180006d10  lea     rdi, aNull_1; "NULL"
0x180006d17  cmovz   r10, rdi
0x180006d1b  test    r9, r9
0x180006d1e  jz      short loc_180006D35
0x180006d20  inc     r8
0x180006d23  cmp     [r9+r8*2], bx
0x180006d28  jnz     short loc_180006D20
0x180006d2a  lea     r11, ds:2[r8*2]
0x180006d32  test    r9, r9
0x180006d35  mov     [rsp+58h+var_18], rbx
0x180006d3a  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006d41  mov     [rsp+58h+var_20], rax
0x180006d46  cmovz   r9, rdi
0x180006d4a  mov     [rsp+58h+var_28], r10
0x180006d4f  mov     [rsp+58h+var_30], r11
0x180006d54  mov     [rsp+58h+var_38], r9
0x180006d59  movzx   r9d, dx
0x180006d5d  mov     edx, 2Bh ; '+'
0x180006d62  call    cs:__imp_EtwTraceMessage
0x180006d68  mov     rbx, [rsp+58h+arg_0]
0x180006d6d  add     rsp, 50h
0x180006d71  pop     rdi
0x180006d72  retn
```
