# __alloca_probe

- ea: `0x1800c6030`
- end: `0x1800c607e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180079820`
- `0x180079ca8`
- `0x18007a13c`
- `0x18007a584`
- `0x18007aa04`
- `0x18007ae74`
- `0x18007b314`
- `0x18007b79c`
- `0x18007bc48`
- `0x18007c0dc`
- `0x180085fa4`
- `0x18009eb04`
- `0x1800a6fd0`
- `0x1800adb74`
- `0x1800aea84`
- `0x1800af098`
- `0x1800b9148`

## callees

- `0x1800c6030`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x1800c6030  sub     rsp, 10h
0x1800c6034  mov     [rsp+10h+var_10], r10
0x1800c6038  mov     [rsp+10h+var_8], r11
0x1800c603d  xor     r11, r11
0x1800c6040  lea     r10, [rsp+10h+arg_0]
0x1800c6045  sub     r10, rax
0x1800c6048  cmovb   r10, r11
0x1800c604c  mov     r11, gs:10h
0x1800c6055  cmp     r10, r11
0x1800c6058  jnb     short loc_1800C6070
0x1800c605a  and     r10w, 0F000h
0x1800c6060  lea     r11, [r11-1000h]
0x1800c6067  mov     byte ptr [r11], 0
0x1800c606b  cmp     r10, r11
0x1800c606e  jnz     short loc_1800C6060
0x1800c6070  mov     r10, [rsp+10h+var_10]
0x1800c6074  mov     r11, [rsp+10h+var_8]
0x1800c6079  add     rsp, 10h
0x1800c607d  retn
```
