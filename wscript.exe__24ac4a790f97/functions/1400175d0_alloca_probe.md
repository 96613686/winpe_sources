# _alloca_probe

- ea: `0x1400175d0`
- end: `0x14001761d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031fc`
- `0x140003464`
- `0x140003700`
- `0x140007f74`
- `0x140008eb0`
- `0x140009cf0`
- `0x140010ed0`
- `0x1400144dc`
- `0x1400146ac`
- `0x140014eb0`
- `0x140015000`
- `0x140015254`
- `0x14001550c`
- `0x140015794`
- `0x140015910`
- `0x140015a7c`
- `0x140015bc0`
- `0x140015d48`

## callees

- `0x1400175d0`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x1400175d0  sub     rsp, 10h
0x1400175d4  mov     [rsp+10h+var_10], r10
0x1400175d8  mov     [rsp+10h+var_8], r11
0x1400175dd  xor     r11, r11
0x1400175e0  lea     r10, [rsp+10h+arg_0]
0x1400175e5  sub     r10, rax
0x1400175e8  cmovb   r10, r11
0x1400175ec  mov     r11, gs:10h
0x1400175f5  cmp     r10, r11
0x1400175f8  jnb     short loc_14001760F
0x1400175fa  and     r10w, 0F000h
0x140017600  lea     r11, [r11-1000h]
0x140017607  test    [r11], r11b
0x14001760a  cmp     r10, r11
0x14001760d  jb      short loc_140017600
0x14001760f  mov     r10, [rsp+10h+var_10]
0x140017613  mov     r11, [rsp+10h+var_8]
0x140017618  add     rsp, 10h
0x14001761c  retn
```
