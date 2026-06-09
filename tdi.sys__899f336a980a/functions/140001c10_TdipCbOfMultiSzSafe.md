# TdipCbOfMultiSzSafe

- ea: `0x140001c10`
- end: `0x140001c4d`
- name: `TdipCbOfMultiSzSafe`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001340`
- `0x140001540`
- `0x1400041d0`

## callees

- `0x140001c10`

## pseudocode

```c
__int64 __fastcall TdipCbOfMultiSzSafe(_WORD *a1)
{
  int v2; // edx
  __int64 v3; // rax
  __int64 v4; // rax
  bool v5; // zf

  if ( !a1 )
    return 0;
  v2 = 0;
  if ( *a1 )
  {
    do
    {
      v3 = -1;
      do
        ++v3;
      while ( a1[v3] );
      v4 = (unsigned int)(v3 + 1);
      v2 += v4;
      v5 = a1[v4] == 0;
      a1 += v4;
    }
    while ( !v5 );
  }
  return (unsigned int)(2 * v2);
}

```

## disassembly

```asm
0x140001c10  test    rcx, rcx
0x140001c13  jnz     short loc_140001C19
0x140001c15  xor     eax, eax
0x140001c17  retn
0x140001c19  xor     edx, edx
0x140001c1b  cmp     [rcx], dx
0x140001c1e  jz      short loc_140001C49
0x140001c20  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001c27  nop     word ptr [rax+rax+00000000h]
0x140001c30  inc     rax
0x140001c33  cmp     word ptr [rcx+rax*2], 0
0x140001c38  jnz     short loc_140001C30
0x140001c3a  inc     eax
0x140001c3c  add     edx, eax
0x140001c3e  cmp     word ptr [rcx+rax*2], 0
0x140001c43  lea     rcx, [rcx+rax*2]
0x140001c47  jnz     short loc_140001C20
0x140001c49  lea     eax, [rdx+rdx]
0x140001c4c  retn
```
