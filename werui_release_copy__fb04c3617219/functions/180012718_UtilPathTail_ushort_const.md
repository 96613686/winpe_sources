# UtilPathTail(ushort const *)

- ea: `0x180012718`
- end: `0x180012756`
- name: `?UtilPathTail@@YAPEBGPEBG@Z`
- size: `62`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff3c`
- `0x1800105c8`
- `0x1800111c0`

## callees

- `0x180012718`

## pseudocode

```c
const unsigned __int16 *__fastcall UtilPathTail(const unsigned __int16 *a1)
{
  const unsigned __int16 *result; // rax
  __int64 v2; // rcx
  const unsigned __int16 *v3; // rcx
  const unsigned __int16 *v4; // rdx

  result = a1;
  if ( a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( result[v2] );
    v3 = &result[v2];
    do
    {
      v4 = v3;
      if ( v3 <= result )
        break;
      if ( *--v3 == 92 )
        break;
    }
    while ( *v3 != 47 && *v3 != 58 );
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180012718  xor     edx, edx
0x18001271a  mov     rax, rcx
0x18001271d  test    rcx, rcx
0x180012720  jnz     short loc_180012723
0x180012722  retn
0x180012723  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012727  inc     rcx
0x18001272a  cmp     [rax+rcx*2], dx
0x18001272e  jnz     short loc_180012727
0x180012730  lea     rcx, [rax+rcx*2]
0x180012734  mov     rdx, rcx
0x180012737  cmp     rcx, rax
0x18001273a  jbe     short loc_180012752
0x18001273c  sub     rcx, 2
0x180012740  cmp     word ptr [rcx], 5Ch ; '\'
0x180012744  jz      short loc_180012752
0x180012746  cmp     word ptr [rcx], 2Fh ; '/'
0x18001274a  jz      short loc_180012752
0x18001274c  cmp     word ptr [rcx], 3Ah ; ':'
0x180012750  jnz     short loc_180012734
0x180012752  mov     rax, rdx
0x180012755  retn
```
