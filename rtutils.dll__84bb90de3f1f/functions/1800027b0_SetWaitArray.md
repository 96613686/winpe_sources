# SetWaitArray

- ea: `0x1800027b0`
- end: `0x180002822`
- name: `SetWaitArray`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002910`
- `0x180002ae0`
- `0x180004c10`

## callees

- `0x1800027b0`

## pseudocode

```c
__int64 *__fastcall SetWaitArray(__int64 a1)
{
  unsigned __int64 v1; // r8
  unsigned int v2; // r9d
  __int64 *result; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx

  v1 = a1 + 832;
  qword_180010230 = *(_QWORD *)(a1 + 88);
  v2 = 3;
  result = (__int64 *)(a1 + 352);
  g_posBase = 2;
  g_posLast = 3;
  if ( a1 + 352 < (unsigned __int64)(a1 + 832) )
  {
    do
    {
      v4 = *result;
      if ( *result )
      {
        if ( (*(_BYTE *)(v4 + 56) & 8) != 0 )
        {
          v5 = v2++;
          g_hWaitHandles[v5] = *(HANDLE *)(v4 + 1080);
        }
      }
      ++result;
    }
    while ( (unsigned __int64)result < v1 );
    g_posLast = v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800027b0  mov     rax, [rcx+58h]
0x1800027b4  lea     r8, [rcx+340h]
0x1800027bb  mov     cs:qword_180010230, rax
0x1800027c2  mov     r9d, 3
0x1800027c8  lea     rax, [rcx+160h]
0x1800027cf  mov     cs:g_posBase, 2
0x1800027d9  mov     cs:g_posLast, r9d
0x1800027e0  cmp     rax, r8
0x1800027e3  jnb     short locret_180002808
0x1800027e5  lea     r10, g_hWaitHandles
0x1800027ec  nop     dword ptr [rax+00h]
0x1800027f0  mov     rcx, [rax]
0x1800027f3  test    rcx, rcx
0x1800027f6  jnz     short loc_180002809
0x1800027f8  add     rax, 8
0x1800027fc  cmp     rax, r8
0x1800027ff  jb      short loc_1800027F0
0x180002801  mov     cs:g_posLast, r9d
0x180002808  retn
0x180002809  test    byte ptr [rcx+38h], 8
0x18000280d  jz      short loc_1800027F8
0x18000280f  mov     rcx, [rcx+438h]
0x180002816  mov     edx, r9d
0x180002819  inc     r9d
0x18000281c  mov     [r10+rdx*8], rcx
0x180002820  jmp     short loc_1800027F8
```
