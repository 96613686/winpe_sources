# _alloca_probe

- ea: `0x180014300`
- end: `0x18001434d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fd8`
- `0x180003c90`
- `0x180005e28`
- `0x1800099ac`
- `0x18000f500`
- `0x18000f68c`
- `0x18000f804`
- `0x18001008c`
- `0x180010440`
- `0x18001167c`
- `0x180011800`
- `0x180011b0c`
- `0x1800125c4`
- `0x1800128e8`
- `0x180012af8`
- `0x180012cac`
- `0x180013070`

## callees

- `0x180014300`

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
0x180014300  sub     rsp, 10h
0x180014304  mov     [rsp+10h+var_10], r10
0x180014308  mov     [rsp+10h+var_8], r11
0x18001430d  xor     r11, r11
0x180014310  lea     r10, [rsp+10h+arg_0]
0x180014315  sub     r10, rax
0x180014318  cmovb   r10, r11
0x18001431c  mov     r11, gs:10h
0x180014325  cmp     r10, r11
0x180014328  jnb     short loc_18001433F
0x18001432a  and     r10w, 0F000h
0x180014330  lea     r11, [r11-1000h]
0x180014337  test    [r11], r11b
0x18001433a  cmp     r10, r11
0x18001433d  jb      short loc_180014330
0x18001433f  mov     r10, [rsp+10h+var_10]
0x180014343  mov     r11, [rsp+10h+var_8]
0x180014348  add     rsp, 10h
0x18001434c  retn
```
