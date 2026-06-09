# StringLengthWorkerW

- ea: `0x180009500`
- end: `0x18000953a`
- name: `StringLengthWorkerW`
- size: `58`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009444`
- `0x180009dc0`

## callees

- `0x180009500`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t v3; // r9
  HRESULT result; // eax

  v3 = cchMax;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --cchMax;
  }
  while ( cchMax );
  result = cchMax == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( cchMax )
      *pcchLength = v3 - cchMax;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009500  mov     r9, rdx
0x180009503  xor     r10d, r10d
0x180009506  cmp     [rcx], r10w
0x18000950a  jz      short loc_180009516
0x18000950c  add     rcx, 2
0x180009510  sub     rdx, 1
0x180009514  jnz     short loc_180009506
0x180009516  mov     rax, rdx
0x180009519  neg     rax
0x18000951c  sbb     eax, eax
0x18000951e  not     eax
0x180009520  and     eax, 80070057h
0x180009525  test    r8, r8
0x180009528  jz      short locret_180009539
0x18000952a  test    rdx, rdx
0x18000952d  jz      short loc_180009536
0x18000952f  sub     r9, rdx
0x180009532  mov     [r8], r9
0x180009535  retn
0x180009536  mov     [r8], r10
0x180009539  retn
```
