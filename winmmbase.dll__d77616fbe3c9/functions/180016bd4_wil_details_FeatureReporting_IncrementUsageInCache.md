# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180016bd4`
- end: `0x180016ca9`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016cb0`

## callees

- `0x180016bd4`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x180016bd4  push    rbx
0x180016bd6  push    rsi
0x180016bd7  push    rdi
0x180016bd8  mov     r8d, [rcx]
0x180016bdb  lea     r10, [r9+8]
0x180016bdf  xor     edi, edi
0x180016be1  mov     ebx, edx
0x180016be3  cmp     edx, 4
0x180016be6  mov     rsi, rcx
0x180016be9  setz    dil
0x180016bed  mov     eax, r8d
0x180016bf0  mov     dword ptr [r9+4], 0
0x180016bf8  or      eax, 1
0x180016bfb  mov     ecx, eax
0x180016bfd  shr     ecx, 0Eh
0x180016c00  and     ecx, 1
0x180016c03  cmp     ecx, edi
0x180016c05  jz      short loc_180016C49
0x180016c07  mov     r11d, eax
0x180016c0a  shr     r11d, 5
0x180016c0e  and     r11d, 1FFh
0x180016c15  jbe     short loc_180016C32
0x180016c17  mov     ecx, ebx
0x180016c19  mov     [r9+4], r11d
0x180016c1d  neg     ecx
0x180016c1f  lea     r10, [r9+8]
0x180016c23  sbb     edx, edx
0x180016c25  not     edx
0x180016c27  and     edx, 4
0x180016c2a  mov     [r10], edx
0x180016c2d  and     eax, 0FFFFC01Fh
0x180016c32  xor     edx, edx
0x180016c34  mov     ecx, 4000h
0x180016c39  cmp     ebx, 4
0x180016c3c  cmovz   edx, ecx
0x180016c3f  mov     ecx, eax
0x180016c41  btr     ecx, 0Eh
0x180016c45  mov     eax, edx
0x180016c47  or      eax, ecx
0x180016c49  mov     ecx, eax
0x180016c4b  shr     ecx, 5
0x180016c4e  and     ecx, 1FFh
0x180016c54  lea     edx, [rcx+1]
0x180016c57  cmp     edx, 1FFh
0x180016c5d  ja      short loc_180016C69
0x180016c5f  cmp     edx, ecx
0x180016c61  jb      short loc_180016C69
0x180016c63  lea     r10, [r9+8]
0x180016c67  jmp     short loc_180016C75
0x180016c69  mov     edx, 1
0x180016c6e  mov     [r10], ebx
0x180016c71  mov     [r9+4], ecx
0x180016c75  shl     edx, 5
0x180016c78  xor     edx, eax
0x180016c7a  and     edx, 3FE0h
0x180016c80  xor     edx, eax
0x180016c82  mov     eax, r8d
0x180016c85  lock cmpxchg [rsi], edx
0x180016c89  jz      short loc_180016C93
0x180016c8b  mov     r8d, eax
0x180016c8e  jmp     loc_180016BED
0x180016c93  not     r8d
0x180016c96  mov     dword ptr [r9+10h], 0
0x180016c9e  and     r8d, 1
0x180016ca2  mov     [r9], r8d
0x180016ca5  pop     rdi
0x180016ca6  pop     rsi
0x180016ca7  pop     rbx
0x180016ca8  retn
```
