# StringCchLengthW

- ea: `0x14000e944`
- end: `0x14000e9a0`
- name: `StringCchLengthW`
- size: `92`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140010870`
- `0x140010a00`
- `0x140011420`
- `0x1400119d8`
- `0x140011a84`
- `0x140011b2c`

## callees

- `0x14000e944`

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
0x14000e944  xor     r10d, r10d
0x14000e947  test    rcx, rcx
0x14000e94a  jz      short loc_14000E992
0x14000e94c  mov     r9d, 105h
0x14000e952  mov     edx, r9d
0x14000e955  cmp     [rcx], r10w
0x14000e959  jz      short loc_14000E965
0x14000e95b  add     rcx, 2
0x14000e95f  sub     rdx, 1
0x14000e963  jnz     short loc_14000E955
0x14000e965  mov     rax, rdx
0x14000e968  neg     rax
0x14000e96b  sbb     eax, eax
0x14000e96d  not     eax
0x14000e96f  and     eax, 80070057h
0x14000e974  test    r8, r8
0x14000e977  jz      short loc_14000E98B
0x14000e979  test    rdx, rdx
0x14000e97c  jz      short loc_14000E986
0x14000e97e  sub     r9, rdx
0x14000e981  mov     [r8], r9
0x14000e984  retn
0x14000e986  mov     [r8], r10
0x14000e989  jmp     short loc_14000E99C
0x14000e98b  test    rdx, rdx
0x14000e98e  jnz     short locret_14000E99F
0x14000e990  jmp     short loc_14000E997
0x14000e992  mov     eax, 80070057h
0x14000e997  test    r8, r8
0x14000e99a  jz      short locret_14000E99F
0x14000e99c  mov     [r8], r10
0x14000e99f  retn
```
