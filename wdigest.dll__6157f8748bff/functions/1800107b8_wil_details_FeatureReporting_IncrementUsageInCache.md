# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800107b8`
- end: `0x18001088d`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b008`

## callees

- `0x1800107b8`

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
0x1800107b8  push    rbx
0x1800107ba  push    rsi
0x1800107bb  push    rdi
0x1800107bc  mov     r8d, [rcx]
0x1800107bf  lea     r10, [r9+8]
0x1800107c3  xor     edi, edi
0x1800107c5  mov     ebx, edx
0x1800107c7  cmp     edx, 4
0x1800107ca  mov     rsi, rcx
0x1800107cd  setz    dil
0x1800107d1  mov     eax, r8d
0x1800107d4  mov     dword ptr [r9+4], 0
0x1800107dc  or      eax, 1
0x1800107df  mov     ecx, eax
0x1800107e1  shr     ecx, 0Eh
0x1800107e4  and     ecx, 1
0x1800107e7  cmp     ecx, edi
0x1800107e9  jz      short loc_18001082D
0x1800107eb  mov     r11d, eax
0x1800107ee  shr     r11d, 5
0x1800107f2  and     r11d, 1FFh
0x1800107f9  jbe     short loc_180010816
0x1800107fb  mov     ecx, ebx
0x1800107fd  mov     [r9+4], r11d
0x180010801  neg     ecx
0x180010803  lea     r10, [r9+8]
0x180010807  sbb     edx, edx
0x180010809  not     edx
0x18001080b  and     edx, 4
0x18001080e  mov     [r10], edx
0x180010811  and     eax, 0FFFFC01Fh
0x180010816  xor     edx, edx
0x180010818  mov     ecx, 4000h
0x18001081d  cmp     ebx, 4
0x180010820  cmovz   edx, ecx
0x180010823  mov     ecx, eax
0x180010825  btr     ecx, 0Eh
0x180010829  mov     eax, edx
0x18001082b  or      eax, ecx
0x18001082d  mov     ecx, eax
0x18001082f  shr     ecx, 5
0x180010832  and     ecx, 1FFh
0x180010838  lea     edx, [rcx+1]
0x18001083b  cmp     edx, 1FFh
0x180010841  ja      short loc_18001084D
0x180010843  cmp     edx, ecx
0x180010845  jb      short loc_18001084D
0x180010847  lea     r10, [r9+8]
0x18001084b  jmp     short loc_180010859
0x18001084d  mov     edx, 1
0x180010852  mov     [r10], ebx
0x180010855  mov     [r9+4], ecx
0x180010859  shl     edx, 5
0x18001085c  xor     edx, eax
0x18001085e  and     edx, 3FE0h
0x180010864  xor     edx, eax
0x180010866  mov     eax, r8d
0x180010869  lock cmpxchg [rsi], edx
0x18001086d  jz      short loc_180010877
0x18001086f  mov     r8d, eax
0x180010872  jmp     loc_1800107D1
0x180010877  not     r8d
0x18001087a  mov     dword ptr [r9+10h], 0
0x180010882  and     r8d, 1
0x180010886  mov     [r9], r8d
0x180010889  pop     rdi
0x18001088a  pop     rsi
0x18001088b  pop     rbx
0x18001088c  retn
```
