# WPP_SF_Sd

- ea: `0x180009bcc`
- end: `0x180009c3c`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a9b8`
- `0x18000abb0`
- `0x18000b4c8`
- `0x18000b584`
- `0x18000b7e0`

## callees

- `0x180009bcc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180009c31`
- `ntdll!EtwTraceMessage` at `0x180009c31`

## pseudocode

```c
__int64 __fastcall WPP_SF_Sd(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x180009bcc  sub     rsp, 58h
0x180009bd0  xor     r11d, r11d
0x180009bd3  test    r9, r9
0x180009bd6  jz      short loc_180009BF0
0x180009bd8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009bdc  inc     rax
0x180009bdf  cmp     [r9+rax*2], r11w
0x180009be4  jnz     short loc_180009BDC
0x180009be6  lea     rax, ds:2[rax*2]
0x180009bee  jmp     short loc_180009BF5
0x180009bf0  mov     eax, 0Ah
0x180009bf5  mov     [rsp+58h+var_18], r11
0x180009bfa  lea     r10, aNull_1; "NULL"
0x180009c01  test    r9, r9
0x180009c04  mov     [rsp+58h+var_20], 4
0x180009c0d  cmovz   r9, r10
0x180009c11  lea     r10, [rsp+58h+arg_20]
0x180009c19  mov     [rsp+58h+var_28], r10
0x180009c1e  mov     [rsp+58h+var_30], rax
0x180009c23  mov     [rsp+58h+var_38], r9
0x180009c28  movzx   r9d, dx
0x180009c2c  mov     edx, 2Bh ; '+'
0x180009c31  call    cs:__imp_EtwTraceMessage
0x180009c37  add     rsp, 58h
0x180009c3b  retn
```
