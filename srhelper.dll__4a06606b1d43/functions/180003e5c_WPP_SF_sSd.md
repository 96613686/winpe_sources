# WPP_SF_sSd

- ea: `0x180003e5c`
- end: `0x180003f13`
- name: `WPP_SF_sSd`
- size: `183`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const char *, __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002054`
- `0x1800022e4`
- `0x1800029d8`
- `0x180002e9c`
- `0x180003360`
- `0x180003550`
- `0x18000deac`
- `0x18000e3b8`
- `0x18000e554`

## callees

- `0x180003e5c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180003f02`
- `ntdll!EtwTraceMessage` at `0x180003f02`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, __int64 a5)
{
  __int64 v5; // rax
  __int64 v6; // r10

  v5 = -1;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a5 + 2 * v6) );
  }
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
  }
  if ( !a4 )
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x180003e5c  mov     [rsp+arg_0], rbx
0x180003e61  push    rdi
0x180003e62  sub     rsp, 60h
0x180003e66  mov     r11, [rsp+68h+arg_20]
0x180003e6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003e72  xor     edi, edi
0x180003e74  test    r11, r11
0x180003e77  jz      short loc_180003E90
0x180003e79  mov     r10, rax
0x180003e7c  inc     r10
0x180003e7f  cmp     [r11+r10*2], di
0x180003e84  jnz     short loc_180003E7C
0x180003e86  lea     r10, ds:2[r10*2]
0x180003e8e  jmp     short loc_180003E96
0x180003e90  mov     r10d, 0Ah
0x180003e96  test    r11, r11
0x180003e99  lea     rbx, aNull_0; "NULL"
0x180003ea0  cmovz   r11, rbx
0x180003ea4  test    r9, r9
0x180003ea7  jz      short loc_180003EB7
0x180003ea9  inc     rax
0x180003eac  cmp     [r9+rax], dil
0x180003eb0  jnz     short loc_180003EA9
0x180003eb2  inc     rax
0x180003eb5  jmp     short loc_180003EBC
0x180003eb7  mov     eax, 5
0x180003ebc  mov     [rsp+68h+var_18], rdi
0x180003ec1  lea     rbx, aNull; "NULL"
0x180003ec8  mov     [rsp+68h+var_20], 4
0x180003ed1  test    r9, r9
0x180003ed4  cmovz   r9, rbx
0x180003ed8  lea     rbx, [rsp+68h+arg_28]
0x180003ee0  mov     [rsp+68h+var_28], rbx
0x180003ee5  mov     [rsp+68h+var_30], r10
0x180003eea  mov     [rsp+68h+var_38], r11
0x180003eef  mov     [rsp+68h+var_40], rax
0x180003ef4  mov     [rsp+68h+var_48], r9
0x180003ef9  movzx   r9d, dx
0x180003efd  mov     edx, 2Bh ; '+'
0x180003f02  call    cs:__imp_EtwTraceMessage
0x180003f08  mov     rbx, [rsp+68h+arg_0]
0x180003f0d  add     rsp, 60h
0x180003f11  pop     rdi
0x180003f12  retn
```
