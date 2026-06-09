# _alloca_probe

- ea: `0x180014870`
- end: `0x1800148be`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180005560`
- `0x180006cf4`
- `0x180007274`
- `0x18000739c`
- `0x18000bc80`
- `0x18000be54`
- `0x18000bfc0`
- `0x18000c058`
- `0x18000d66c`

## callees

- `0x180014870`

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
0x180014870  sub     rsp, 10h
0x180014874  mov     [rsp+10h+var_10], r10
0x180014878  mov     [rsp+10h+var_8], r11
0x18001487d  xor     r11, r11
0x180014880  lea     r10, [rsp+10h+arg_0]
0x180014885  sub     r10, rax
0x180014888  cmovb   r10, r11
0x18001488c  mov     r11, gs:10h
0x180014895  cmp     r10, r11
0x180014898  jnb     short cs20
0x18001489a  and     r10w, 0F000h
0x1800148a0  lea     r11, [r11-1000h]
0x1800148a7  mov     byte ptr [r11], 0
0x1800148ab  cmp     r10, r11
0x1800148ae  jnz     short cs10
0x1800148b0  mov     r10, [rsp+10h+var_10]
0x1800148b4  mov     r11, [rsp+10h+var_8]
0x1800148b9  add     rsp, 10h
0x1800148bd  retn
```
