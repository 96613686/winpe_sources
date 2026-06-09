# StringLengthWorkerA

- ea: `0x180003774`
- end: `0x1800037b3`
- name: `StringLengthWorkerA`
- size: `63`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002130`
- `0x180003614`
- `0x180003740`

## callees

- `0x180003774`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerA(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)
{
  __int64 v3; // rdx
  HRESULT result; // eax

  v3 = 260;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v3 )
      *pcchLength = 260 - v3;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003774  mov     r9d, 104h
0x18000377a  mov     edx, r9d
0x18000377d  cmp     byte ptr [rcx], 0
0x180003780  jz      short loc_18000378B
0x180003782  inc     rcx
0x180003785  sub     rdx, 1
0x180003789  jnz     short loc_18000377D
0x18000378b  mov     rax, rdx
0x18000378e  neg     rax
0x180003791  sbb     eax, eax
0x180003793  not     eax
0x180003795  and     eax, 80070057h
0x18000379a  test    r8, r8
0x18000379d  jz      short locret_1800037B2
0x18000379f  test    rdx, rdx
0x1800037a2  jz      short loc_1800037AB
0x1800037a4  sub     r9, rdx
0x1800037a7  mov     [r8], r9
0x1800037aa  retn
0x1800037ab  mov     qword ptr [r8], 0
0x1800037b2  retn
```
