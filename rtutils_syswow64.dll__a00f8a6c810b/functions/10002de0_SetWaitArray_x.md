# SetWaitArray(x)

- ea: `0x10002de0`
- end: `0x10002e29`
- name: `_SetWaitArray@4`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x10002320`
- `0x10002700`
- `0x100066c0`

## callees

- `0x10002de0`

## pseudocode

```c
int *__fastcall SetWaitArray(int a1)
{
  unsigned int v1; // edx
  int *result; // eax
  int v3; // esi
  int v4; // ecx

  v1 = a1 + 548;
  dword_1000B168 = *(_DWORD *)(a1 + 56);
  result = (int *)(a1 + 308);
  g_posBase = 2;
  v3 = 3;
  g_posLast = 3;
  if ( a1 + 308 < (unsigned int)(a1 + 548) )
  {
    do
    {
      v4 = *result;
      if ( *result )
      {
        if ( (*(_BYTE *)(v4 + 32) & 8) != 0 )
          *(&g_hWaitHandles + v3++) = *(HANDLE *)(v4 + 1040);
      }
      ++result;
    }
    while ( (unsigned int)result < v1 );
    g_posLast = v3;
  }
  return result;
}

```

## disassembly

```asm
0x10002de0  mov     eax, [ecx+38h]
0x10002de3  lea     edx, [ecx+224h]
0x10002de9  mov     dword_1000B168, eax
0x10002dee  lea     eax, [ecx+134h]
0x10002df4  mov     _g_posBase, 2
0x10002dfe  push    esi
0x10002dff  mov     esi, 3
0x10002e04  mov     _g_posLast, esi
0x10002e0a  cmp     eax, edx
0x10002e0c  jnb     short loc_10002E27
0x10002e0e  mov     edi, edi
0x10002e10  mov     ecx, [eax]
0x10002e12  test    ecx, ecx
0x10002e14  jnz     loc_1000572B
0x10002e1a  add     eax, 4
0x10002e1d  cmp     eax, edx
0x10002e1f  jb      short loc_10002E10
0x10002e21  mov     _g_posLast, esi
0x10002e27  pop     esi
0x10002e28  retn
0x1000572b  test    byte ptr [ecx+20h], 8
0x1000572f  jz      loc_10002E1A
0x10005735  mov     ecx, [ecx+410h]
0x1000573b  mov     _g_hWaitHandles[esi*4], ecx
0x10005742  inc     esi
0x10005743  jmp     loc_10002E1A
```
