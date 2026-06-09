# RtlCompareMemory

- ea: `0x1400f3930`
- end: `0x1400f39aa`
- name: `RtlCompareMemory`
- size: `122`
- prototype: `SIZE_T __stdcall(const void *Source1, const void *Source2, SIZE_T Length)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400136dc`
- `0x140048bfc`
- `0x1400b023c`
- `0x1400c1b5c`
- `0x1400c3b48`
- `0x1400c937c`
- `0x1400dc6c4`
- `0x1400dc918`
- `0x1400fc8c8`
- `0x1400fca9c`

## callees

- `0x1400f3930`

## pseudocode

```c
SIZE_T __stdcall RtlCompareMemory(const void *Source1, const void *Source2, SIZE_T Length)
{
  _BYTE *v3; // rsi
  _BYTE *v4; // rdi
  __int64 v5; // rcx
  bool v6; // zf
  SIZE_T v7; // rcx
  bool v8; // zf
  bool v9; // zf
  SIZE_T v10; // r8
  SIZE_T v11; // rcx
  bool v13; // zf
  SIZE_T v14; // rcx

  v3 = Source1;
  v4 = Source2;
  if ( (((unsigned __int8)Source1 ^ (unsigned __int8)Source2) & 7) != 0 || Length < 8 )
  {
    v13 = Length == 0;
    if ( Length )
    {
      v14 = Length;
      do
      {
        if ( !v14 )
          break;
        v13 = *v3++ == *v4++;
        --v14;
      }
      while ( v13 );
      if ( !v13 )
        Length -= v14 + 1;
    }
    return Length;
  }
  else
  {
    v5 = -(int)Source1 & 7;
    if ( (_DWORD)v5 )
    {
      Length -= (unsigned int)v5;
      v6 = Length == 0;
      do
      {
        if ( !v5 )
          break;
        v6 = *v3++ == *v4++;
        --v5;
      }
      while ( v6 );
      if ( !v6 )
        goto LABEL_19;
    }
    v7 = Length & 0xFFFFFFFFFFFFFFF8uLL;
    if ( (Length & 0xFFFFFFFFFFFFFFF8uLL) != 0 )
    {
      Length -= v7;
      v7 >>= 3;
      v8 = v7 == 0;
      do
      {
        if ( !v7 )
          break;
        v8 = *(_QWORD *)v3 == *(_QWORD *)v4;
        v3 += 8;
        v4 += 8;
        --v7;
      }
      while ( v8 );
      if ( !v8 )
      {
        v3 -= 8;
        v4 -= 8;
        v7 = 8 * (v7 + 1);
      }
    }
    v9 = v7 + Length == 0;
    v10 = v7 + Length;
    if ( v10 )
    {
      v11 = v10;
      do
      {
        if ( !v11 )
          break;
        v9 = *v3++ == *v4++;
        --v11;
      }
      while ( v9 );
      if ( !v9 )
LABEL_19:
        --v4;
    }
    return v4 - (_BYTE *)Source2;
  }
}

```

## disassembly

```asm
0x1400f3930  push    rdi
0x1400f3931  push    rsi
0x1400f3932  mov     rsi, rcx
0x1400f3935  mov     rdi, rdx
0x1400f3938  xor     edx, ecx
0x1400f393a  and     edx, 7
0x1400f393d  jnz     short loc_1400F3992
0x1400f393f  cmp     r8, 8
0x1400f3943  jb      short loc_1400F3992
0x1400f3945  mov     r9, rdi
0x1400f3948  neg     ecx
0x1400f394a  and     ecx, 7
0x1400f394d  jz      short loc_1400F3956
0x1400f394f  sub     r8, rcx
0x1400f3952  repe cmpsb
0x1400f3954  jnz     short loc_1400F3986
0x1400f3956  mov     rcx, r8
0x1400f3959  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1400f395d  jz      short loc_1400F397A
0x1400f395f  sub     r8, rcx
0x1400f3962  shr     rcx, 3
0x1400f3966  repe cmpsq
0x1400f3969  jz      short loc_1400F397A
0x1400f396b  inc     rcx
0x1400f396e  sub     rsi, 8
0x1400f3972  sub     rdi, 8
0x1400f3976  shl     rcx, 3
0x1400f397a  add     r8, rcx
0x1400f397d  jz      short loc_1400F3989
0x1400f397f  mov     rcx, r8
0x1400f3982  repe cmpsb
0x1400f3984  jz      short loc_1400F3989
0x1400f3986  dec     rdi
0x1400f3989  sub     rdi, r9
0x1400f398c  mov     rax, rdi
0x1400f398f  pop     rsi
0x1400f3990  pop     rdi
0x1400f3991  retn
0x1400f3992  test    r8, r8
0x1400f3995  jz      short loc_1400F39A4
0x1400f3997  mov     rcx, r8
0x1400f399a  repe cmpsb
0x1400f399c  jz      short loc_1400F39A4
0x1400f399e  inc     rcx
0x1400f39a1  sub     r8, rcx
0x1400f39a4  mov     rax, r8
0x1400f39a7  pop     rsi
0x1400f39a8  pop     rdi
0x1400f39a9  retn
```
