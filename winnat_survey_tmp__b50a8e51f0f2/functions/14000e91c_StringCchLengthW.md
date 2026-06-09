# StringCchLengthW

- ea: `0x14000e91c`
- end: `0x14000e978`
- name: `StringCchLengthW`
- size: `92`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140010810`
- `0x1400109a0`
- `0x1400113c0`
- `0x140011978`
- `0x140011a24`
- `0x140011acc`

## callees

- `0x14000e91c`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  __int64 v3; // rdx
  HRESULT result; // eax

  if ( !psz )
  {
    result = -2147024809;
    goto LABEL_12;
  }
  v3 = 261;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( !pcchLength )
  {
    if ( v3 )
      return result;
LABEL_12:
    if ( !pcchLength )
      return result;
    goto LABEL_13;
  }
  if ( v3 )
  {
    *pcchLength = 261 - v3;
    return result;
  }
  *pcchLength = 0;
LABEL_13:
  *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x14000e91c  xor     r10d, r10d
0x14000e91f  test    rcx, rcx
0x14000e922  jz      short loc_14000E96A
0x14000e924  mov     r9d, 105h
0x14000e92a  mov     edx, r9d
0x14000e92d  cmp     [rcx], r10w
0x14000e931  jz      short loc_14000E93D
0x14000e933  add     rcx, 2
0x14000e937  sub     rdx, 1
0x14000e93b  jnz     short loc_14000E92D
0x14000e93d  mov     rax, rdx
0x14000e940  neg     rax
0x14000e943  sbb     eax, eax
0x14000e945  not     eax
0x14000e947  and     eax, 80070057h
0x14000e94c  test    r8, r8
0x14000e94f  jz      short loc_14000E963
0x14000e951  test    rdx, rdx
0x14000e954  jz      short loc_14000E95E
0x14000e956  sub     r9, rdx
0x14000e959  mov     [r8], r9
0x14000e95c  retn
0x14000e95e  mov     [r8], r10
0x14000e961  jmp     short loc_14000E974
0x14000e963  test    rdx, rdx
0x14000e966  jnz     short locret_14000E977
0x14000e968  jmp     short loc_14000E96F
0x14000e96a  mov     eax, 80070057h
0x14000e96f  test    r8, r8
0x14000e972  jz      short locret_14000E977
0x14000e974  mov     [r8], r10
0x14000e977  retn
```
