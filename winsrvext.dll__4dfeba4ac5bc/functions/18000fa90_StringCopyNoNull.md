# StringCopyNoNull

- ea: `0x18000fa90`
- end: `0x18000fae0`
- name: `StringCopyNoNull`
- size: `80`
- prototype: `void __fastcall(_WORD *, unsigned int, _WORD *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e6b4`
- `0x18000ff10`

## callees

- `0x18000fa90`

## pseudocode

```c
void __fastcall StringCopyNoNull(_WORD *a1, unsigned int a2, _WORD *a3, unsigned int a4)
{
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // rax
  _WORD *v6; // rax

  v4 = (unsigned __int64)a2 >> 1;
  if ( v4 )
  {
    v5 = (unsigned __int64)a4 >> 1;
    if ( v5 <= 0x7FFFFFFE )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*a3 )
          break;
        *a1++ = *a3++;
        --v5;
        --v4;
      }
      while ( v4 );
      v6 = a1 - 1;
      if ( v4 )
        v6 = a1;
      *v6 = 0;
    }
    else
    {
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000fa90  mov     r10d, edx
0x18000fa93  shr     r10, 1
0x18000fa96  jz      short locret_18000FADF
0x18000fa98  mov     eax, r9d
0x18000fa9b  xor     edx, edx
0x18000fa9d  shr     rax, 1
0x18000faa0  cmp     rax, 7FFFFFFEh
0x18000faa6  jbe     short loc_18000FAAD
0x18000faa8  mov     [rcx], dx
0x18000faab  retn
0x18000faad  test    rax, rax
0x18000fab0  jz      short loc_18000FAD1
0x18000fab2  movzx   r9d, word ptr [r8]
0x18000fab6  test    r9w, r9w
0x18000faba  jz      short loc_18000FAD1
0x18000fabc  mov     [rcx], r9w
0x18000fac0  add     r8, 2
0x18000fac4  add     rcx, 2
0x18000fac8  dec     rax
0x18000facb  sub     r10, 1
0x18000facf  jnz     short loc_18000FAAD
0x18000fad1  test    r10, r10
0x18000fad4  lea     rax, [rcx-2]
0x18000fad8  cmovnz  rax, rcx
0x18000fadc  mov     [rax], dx
0x18000fadf  retn
```
