# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180010680`
- end: `0x180010756`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001075c`

## callees

- `0x180010680`

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
0x180010680  push    rbx
0x180010682  push    rsi
0x180010683  push    rdi
0x180010684  mov     r8d, [rcx]
0x180010687  lea     r10, [r9+8]
0x18001068b  xor     edi, edi
0x18001068d  mov     ebx, edx
0x18001068f  cmp     edx, 4
0x180010692  mov     rsi, rcx
0x180010695  setz    dil
0x180010699  mov     eax, r8d
0x18001069c  mov     dword ptr [r9+4], 0
0x1800106a4  or      eax, 1
0x1800106a7  mov     ecx, eax
0x1800106a9  shr     ecx, 0Eh
0x1800106ac  and     ecx, 1
0x1800106af  cmp     ecx, edi
0x1800106b1  jz      short loc_1800106F5
0x1800106b3  mov     r11d, eax
0x1800106b6  shr     r11d, 5
0x1800106ba  and     r11d, 1FFh
0x1800106c1  jbe     short loc_1800106DE
0x1800106c3  mov     ecx, ebx
0x1800106c5  mov     [r9+4], r11d
0x1800106c9  neg     ecx
0x1800106cb  lea     r10, [r9+8]
0x1800106cf  sbb     edx, edx
0x1800106d1  not     edx
0x1800106d3  and     edx, 4
0x1800106d6  mov     [r10], edx
0x1800106d9  and     eax, 0FFFFC01Fh
0x1800106de  xor     edx, edx
0x1800106e0  mov     ecx, 4000h
0x1800106e5  cmp     ebx, 4
0x1800106e8  cmovz   edx, ecx
0x1800106eb  mov     ecx, eax
0x1800106ed  btr     ecx, 0Eh
0x1800106f1  mov     eax, edx
0x1800106f3  or      eax, ecx
0x1800106f5  mov     ecx, eax
0x1800106f7  shr     ecx, 5
0x1800106fa  and     ecx, 1FFh
0x180010700  lea     edx, [rcx+1]
0x180010703  cmp     edx, 1FFh
0x180010709  ja      short loc_180010715
0x18001070b  cmp     edx, ecx
0x18001070d  jb      short loc_180010715
0x18001070f  lea     r10, [r9+8]
0x180010713  jmp     short loc_180010721
0x180010715  mov     edx, 1
0x18001071a  mov     [r10], ebx
0x18001071d  mov     [r9+4], ecx
0x180010721  shl     edx, 5
0x180010724  xor     edx, eax
0x180010726  and     edx, 3FE0h
0x18001072c  xor     edx, eax
0x18001072e  mov     eax, r8d
0x180010731  lock cmpxchg [rsi], edx
0x180010735  jz      short loc_18001073F
0x180010737  mov     r8d, eax
0x18001073a  jmp     loc_180010699
0x18001073f  not     r8d
0x180010742  mov     dword ptr [r9+10h], 0
0x18001074a  and     r8d, 1
0x18001074e  mov     [r9], r8d
0x180010751  pop     rdi
0x180010752  pop     rsi
0x180010753  pop     rbx
0x180010754  retn
```
