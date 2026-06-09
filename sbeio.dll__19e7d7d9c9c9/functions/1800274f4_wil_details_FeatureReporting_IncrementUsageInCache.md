# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800274f4`
- end: `0x1800275c9`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800275d0`

## callees

- `0x1800274f4`

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
0x1800274f4  push    rbx
0x1800274f6  push    rsi
0x1800274f7  push    rdi
0x1800274f8  mov     r8d, [rcx]
0x1800274fb  lea     r10, [r9+8]
0x1800274ff  xor     edi, edi
0x180027501  mov     ebx, edx
0x180027503  cmp     edx, 4
0x180027506  mov     rsi, rcx
0x180027509  setz    dil
0x18002750d  mov     eax, r8d
0x180027510  mov     dword ptr [r9+4], 0
0x180027518  or      eax, 1
0x18002751b  mov     ecx, eax
0x18002751d  shr     ecx, 0Eh
0x180027520  and     ecx, 1
0x180027523  cmp     ecx, edi
0x180027525  jz      short loc_180027569
0x180027527  mov     r11d, eax
0x18002752a  shr     r11d, 5
0x18002752e  and     r11d, 1FFh
0x180027535  jbe     short loc_180027552
0x180027537  mov     ecx, ebx
0x180027539  mov     [r9+4], r11d
0x18002753d  neg     ecx
0x18002753f  lea     r10, [r9+8]
0x180027543  sbb     edx, edx
0x180027545  not     edx
0x180027547  and     edx, 4
0x18002754a  mov     [r10], edx
0x18002754d  and     eax, 0FFFFC01Fh
0x180027552  xor     edx, edx
0x180027554  mov     ecx, 4000h
0x180027559  cmp     ebx, 4
0x18002755c  cmovz   edx, ecx
0x18002755f  mov     ecx, eax
0x180027561  btr     ecx, 0Eh
0x180027565  mov     eax, edx
0x180027567  or      eax, ecx
0x180027569  mov     ecx, eax
0x18002756b  shr     ecx, 5
0x18002756e  and     ecx, 1FFh
0x180027574  lea     edx, [rcx+1]
0x180027577  cmp     edx, 1FFh
0x18002757d  ja      short loc_180027589
0x18002757f  cmp     edx, ecx
0x180027581  jb      short loc_180027589
0x180027583  lea     r10, [r9+8]
0x180027587  jmp     short loc_180027595
0x180027589  mov     edx, 1
0x18002758e  mov     [r10], ebx
0x180027591  mov     [r9+4], ecx
0x180027595  shl     edx, 5
0x180027598  xor     edx, eax
0x18002759a  and     edx, 3FE0h
0x1800275a0  xor     edx, eax
0x1800275a2  mov     eax, r8d
0x1800275a5  lock cmpxchg [rsi], edx
0x1800275a9  jz      short loc_1800275B3
0x1800275ab  mov     r8d, eax
0x1800275ae  jmp     loc_18002750D
0x1800275b3  not     r8d
0x1800275b6  mov     dword ptr [r9+10h], 0
0x1800275be  and     r8d, 1
0x1800275c2  mov     [r9], r8d
0x1800275c5  pop     rdi
0x1800275c6  pop     rsi
0x1800275c7  pop     rbx
0x1800275c8  retn
```
