# CBsString::Append(ushort const *,ushort const *)

- ea: `0x180014ec8`
- end: `0x180014f30`
- name: `?Append@CBsString@@QEAAJPEBG0@Z`
- size: `104`
- prototype: `__int64 __fastcall(CBsString *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004928`
- `0x1800050dc`
- `0x18000572c`
- `0x18000e554`

## callees

- `0x180014ec8`
- `0x1800154c8`

## pseudocode

```c
__int64 __fastcall CBsString::Append(CBsString *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v6[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+58h] [rbp+10h] BYREF
  int v8; // [rsp+5Ch] [rbp+14h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v7 = v4;
  v6[0] = a2;
  do
    ++v3;
  while ( a3[v3] );
  v6[1] = a3;
  v8 = v3;
  return CBsString::_Append(this, 2u, (int)v3 + (int)v4, &v7, (const unsigned __int16 **const)v6);
}

```

## disassembly

```asm
0x180014ec8  sub     rsp, 48h
0x180014ecc  xor     r10d, r10d
0x180014ecf  test    rdx, rdx
0x180014ed2  jz      short loc_180014F26
0x180014ed4  test    r8, r8
0x180014ed7  jz      short loc_180014F26
0x180014ed9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014edd  mov     r9, rax
0x180014ee0  inc     r9
0x180014ee3  cmp     [rdx+r9*2], r10w
0x180014ee8  jnz     short loc_180014EE0
0x180014eea  mov     [rsp+48h+arg_8], r9d
0x180014eef  mov     [rsp+48h+var_18], rdx
0x180014ef4  inc     rax
0x180014ef7  cmp     [r8+rax*2], r10w
0x180014efc  jnz     short loc_180014EF4
0x180014efe  mov     [rsp+48h+var_10], r8
0x180014f03  mov     edx, 2; unsigned int
0x180014f08  lea     r8d, [rax+r9]; unsigned int
0x180014f0c  mov     [rsp+48h+arg_C], eax
0x180014f10  lea     rax, [rsp+48h+var_18]
0x180014f15  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180014f1a  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180014f1f  call    ?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z; CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x180014f24  jmp     short loc_180014F2B
0x180014f26  mov     eax, 80070057h
0x180014f2b  add     rsp, 48h
0x180014f2f  retn
```
