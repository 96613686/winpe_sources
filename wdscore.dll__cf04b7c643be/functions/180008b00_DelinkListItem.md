# DelinkListItem

- ea: `0x180008b00`
- end: `0x180008b3e`
- name: `DelinkListItem`
- size: `62`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003108`
- `0x180004e6c`
- `0x180007330`
- `0x1800087e0`
- `0x180008abc`

## callees

- `0x180008b00`

## pseudocode

```c
__int64 __fastcall DelinkListItem(_QWORD *a1, __int64 a2)
{
  __int64 *v2; // r8
  __int64 result; // rax
  __int64 v4; // rcx

  v2 = (__int64 *)(a2 + 8);
  if ( *a1 == a2 )
  {
    result = *v2;
    *a1 = *v2;
  }
  if ( a1[1] == a2 )
  {
    result = *(_QWORD *)(a2 + 16);
    a1[1] = result;
  }
  v4 = *(_QWORD *)(a2 + 16);
  if ( v4 )
  {
    result = *v2;
    *(_QWORD *)(v4 + 8) = *v2;
  }
  if ( *v2 )
  {
    result = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(*v2 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180008b00  lea     r8, [rdx+8]
0x180008b04  cmp     [rcx], rdx
0x180008b07  jnz     short loc_180008B0F
0x180008b09  mov     rax, [r8]
0x180008b0c  mov     [rcx], rax
0x180008b0f  cmp     [rcx+8], rdx
0x180008b13  jnz     short loc_180008B1D
0x180008b15  mov     rax, [rdx+10h]
0x180008b19  mov     [rcx+8], rax
0x180008b1d  mov     rcx, [rdx+10h]
0x180008b21  test    rcx, rcx
0x180008b24  jz      short loc_180008B2D
0x180008b26  mov     rax, [r8]
0x180008b29  mov     [rcx+8], rax
0x180008b2d  mov     rcx, [r8]
0x180008b30  test    rcx, rcx
0x180008b33  jz      short locret_180008B3D
0x180008b35  mov     rax, [rdx+10h]
0x180008b39  mov     [rcx+10h], rax
0x180008b3d  retn
```
