# _alloca_probe

- ea: `0x14001c930`
- end: `0x14001c97e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cdc`
- `0x140003df4`
- `0x140004090`
- `0x14000e49c`
- `0x14000fa90`
- `0x140012d44`
- `0x140014a20`
- `0x140014b48`
- `0x1400170a4`
- `0x14001b130`

## callees

- `0x14001c930`

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
0x14001c930  sub     rsp, 10h
0x14001c934  mov     [rsp+10h+var_10], r10
0x14001c938  mov     [rsp+10h+var_8], r11
0x14001c93d  xor     r11, r11
0x14001c940  lea     r10, [rsp+10h+arg_0]
0x14001c945  sub     r10, rax
0x14001c948  cmovb   r10, r11
0x14001c94c  mov     r11, gs:10h
0x14001c955  cmp     r10, r11
0x14001c958  jnb     short loc_14001C970
0x14001c95a  and     r10w, 0F000h
0x14001c960  lea     r11, [r11-1000h]
0x14001c967  mov     byte ptr [r11], 0
0x14001c96b  cmp     r10, r11
0x14001c96e  jnz     short loc_14001C960
0x14001c970  mov     r10, [rsp+10h+var_10]
0x14001c974  mov     r11, [rsp+10h+var_8]
0x14001c979  add     rsp, 10h
0x14001c97d  retn
```
