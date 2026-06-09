# SIPolicyAppIdTaggingEnforceDLL

- ea: `0x18001919c`
- end: `0x180019203`
- name: `SIPolicyAppIdTaggingEnforceDLL`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b550`
- `0x180049860`

## callees

- `0x18001919c`
- `0x18001ae2c`

## pseudocode

```c
char __fastcall SIPolicyAppIdTaggingEnforceDLL(__int64 a1)
{
  char v2; // [rsp+50h] [rbp+8h] BYREF
  int v3; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v4; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v2 = 0;
  v4 = 1;
  if ( (int)SIPolicyQueryOneSecurityPolicy(
              a1,
              (const UNICODE_STRING *)&qword_180036630,
              (__int64)&qword_180036690,
              (__int64)&qword_1800365E0,
              &v3,
              &v2,
              &v4) < 0
    || v3 )
  {
    return 0;
  }
  else
  {
    return v2;
  }
}

```

## disassembly

```asm
0x18001919c  mov     r11, rsp
0x18001919f  sub     rsp, 48h
0x1800191a3  lea     rax, [r11+18h]
0x1800191a7  mov     [rsp+48h+arg_8], 0
0x1800191af  mov     [r11-18h], rax
0x1800191b3  lea     r9, qword_1800365E0
0x1800191ba  lea     rax, [r11+8]
0x1800191be  mov     [rsp+48h+arg_0], 0
0x1800191c3  mov     [r11-20h], rax
0x1800191c7  lea     r8, qword_180036690
0x1800191ce  lea     rax, [r11+10h]
0x1800191d2  mov     [rsp+48h+arg_10], 1
0x1800191da  lea     rdx, qword_180036630
0x1800191e1  mov     [r11-28h], rax
0x1800191e5  call    SIPolicyQueryOneSecurityPolicy
0x1800191ea  test    eax, eax
0x1800191ec  js      short loc_1800191FB
0x1800191ee  cmp     [rsp+48h+arg_8], 0
0x1800191f3  jnz     short loc_1800191FB
0x1800191f5  mov     al, [rsp+48h+arg_0]
0x1800191f9  jmp     short loc_1800191FD
0x1800191fb  xor     al, al
0x1800191fd  add     rsp, 48h
0x180019201  retn
```
