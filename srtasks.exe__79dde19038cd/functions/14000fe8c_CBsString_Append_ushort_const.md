# CBsString::Append(ushort const *)

- ea: `0x14000fe8c`
- end: `0x14000fed4`
- name: `?Append@CBsString@@QEAAJPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CBsString *this, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140006018`
- `0x1400066e0`
- `0x1400068d4`
- `0x14000de58`
- `0x14000f7a0`
- `0x140010324`

## callees

- `0x14000fe8c`
- `0x1400104ac`

## pseudocode

```c
__int64 __fastcall CBsString::Append(CBsString *this, unsigned __int16 *a2)
{
  __int64 v3; // r8
  unsigned int v4; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v5; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v5 = a2;
  v4 = v3;
  return CBsString::_Append(this, 1u, v3, &v4, (const unsigned __int16 **const)&v5);
}

```

## disassembly

```asm
0x14000fe8c  sub     rsp, 38h
0x14000fe90  xor     eax, eax
0x14000fe92  test    rdx, rdx
0x14000fe95  jnz     short loc_14000FE9E
0x14000fe97  mov     eax, 80070057h
0x14000fe9c  jmp     short loc_14000FECF
0x14000fe9e  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000fea2  inc     r8; unsigned int
0x14000fea5  cmp     [rdx+r8*2], ax
0x14000feaa  jnz     short loc_14000FEA2
0x14000feac  mov     [rsp+38h+arg_10], rdx
0x14000feb1  lea     rax, [rsp+38h+arg_10]
0x14000feb6  mov     edx, 1; unsigned int
0x14000febb  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x14000fec0  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x14000fec5  mov     [rsp+38h+arg_8], r8d
0x14000feca  call    ?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z; CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x14000fecf  add     rsp, 38h
0x14000fed3  retn
```
