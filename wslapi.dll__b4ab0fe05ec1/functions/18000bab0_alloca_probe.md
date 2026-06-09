# _alloca_probe

- ea: `0x18000bab0`
- end: `0x18000bafe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e2c`
- `0x180002eec`
- `0x180002fe8`
- `0x180005b80`
- `0x180005eb4`
- `0x180008118`
- `0x180009778`

## callees

- `0x18000bab0`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x18000bab0  sub     rsp, 10h
0x18000bab4  mov     [rsp+10h+var_10], r10
0x18000bab8  mov     [rsp+10h+var_8], r11
0x18000babd  xor     r11, r11
0x18000bac0  lea     r10, [rsp+10h+arg_0]
0x18000bac5  sub     r10, rax
0x18000bac8  cmovb   r10, r11
0x18000bacc  mov     r11, gs:10h
0x18000bad5  cmp     r10, r11
0x18000bad8  jnb     short cs20
0x18000bada  and     r10w, 0F000h
0x18000bae0  lea     r11, [r11-1000h]
0x18000bae7  mov     byte ptr [r11], 0
0x18000baeb  cmp     r10, r11
0x18000baee  jnz     short cs10
0x18000baf0  mov     r10, [rsp+10h+var_10]
0x18000baf4  mov     r11, [rsp+10h+var_8]
0x18000baf9  add     rsp, 10h
0x18000bafd  retn
```
