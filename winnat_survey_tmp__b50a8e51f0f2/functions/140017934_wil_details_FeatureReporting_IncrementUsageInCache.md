# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140017934`
- end: `0x140017a0a`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017a10`

## callees

- `0x140017934`

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
0x140017934  push    rbx
0x140017936  push    rsi
0x140017937  push    rdi
0x140017938  mov     r8d, [rcx]
0x14001793b  lea     r10, [r9+8]
0x14001793f  xor     edi, edi
0x140017941  mov     ebx, edx
0x140017943  cmp     edx, 4
0x140017946  mov     rsi, rcx
0x140017949  setz    dil
0x14001794d  mov     eax, r8d
0x140017950  mov     dword ptr [r9+4], 0
0x140017958  or      eax, 1
0x14001795b  mov     ecx, eax
0x14001795d  shr     ecx, 0Eh
0x140017960  and     ecx, 1
0x140017963  cmp     ecx, edi
0x140017965  jz      short loc_1400179A9
0x140017967  mov     r11d, eax
0x14001796a  shr     r11d, 5
0x14001796e  and     r11d, 1FFh
0x140017975  jbe     short loc_140017992
0x140017977  mov     ecx, ebx
0x140017979  mov     [r9+4], r11d
0x14001797d  neg     ecx
0x14001797f  lea     r10, [r9+8]
0x140017983  sbb     edx, edx
0x140017985  not     edx
0x140017987  and     edx, 4
0x14001798a  mov     [r10], edx
0x14001798d  and     eax, 0FFFFC01Fh
0x140017992  xor     edx, edx
0x140017994  mov     ecx, 4000h
0x140017999  cmp     ebx, 4
0x14001799c  cmovz   edx, ecx
0x14001799f  mov     ecx, eax
0x1400179a1  btr     ecx, 0Eh
0x1400179a5  mov     eax, edx
0x1400179a7  or      eax, ecx
0x1400179a9  mov     ecx, eax
0x1400179ab  shr     ecx, 5
0x1400179ae  and     ecx, 1FFh
0x1400179b4  lea     edx, [rcx+1]
0x1400179b7  cmp     edx, 1FFh
0x1400179bd  ja      short loc_1400179C9
0x1400179bf  cmp     edx, ecx
0x1400179c1  jb      short loc_1400179C9
0x1400179c3  lea     r10, [r9+8]
0x1400179c7  jmp     short loc_1400179D5
0x1400179c9  mov     edx, 1
0x1400179ce  mov     [r10], ebx
0x1400179d1  mov     [r9+4], ecx
0x1400179d5  shl     edx, 5
0x1400179d8  xor     edx, eax
0x1400179da  and     edx, 3FE0h
0x1400179e0  xor     edx, eax
0x1400179e2  mov     eax, r8d
0x1400179e5  lock cmpxchg [rsi], edx
0x1400179e9  jz      short loc_1400179F3
0x1400179eb  mov     r8d, eax
0x1400179ee  jmp     loc_14001794D
0x1400179f3  not     r8d
0x1400179f6  mov     dword ptr [r9+10h], 0
0x1400179fe  and     r8d, 1
0x140017a02  mov     [r9], r8d
0x140017a05  pop     rdi
0x140017a06  pop     rsi
0x140017a07  pop     rbx
0x140017a08  retn
```
