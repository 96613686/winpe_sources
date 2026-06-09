# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000f5ac`
- end: `0x18000f681`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f688`

## callees

- `0x18000f5ac`

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
0x18000f5ac  push    rbx
0x18000f5ae  push    rsi
0x18000f5af  push    rdi
0x18000f5b0  mov     r8d, [rcx]
0x18000f5b3  lea     r10, [r9+8]
0x18000f5b7  xor     edi, edi
0x18000f5b9  mov     ebx, edx
0x18000f5bb  cmp     edx, 4
0x18000f5be  mov     rsi, rcx
0x18000f5c1  setz    dil
0x18000f5c5  mov     eax, r8d
0x18000f5c8  mov     dword ptr [r9+4], 0
0x18000f5d0  or      eax, 1
0x18000f5d3  mov     ecx, eax
0x18000f5d5  shr     ecx, 0Eh
0x18000f5d8  and     ecx, 1
0x18000f5db  cmp     ecx, edi
0x18000f5dd  jz      short loc_18000F621
0x18000f5df  mov     r11d, eax
0x18000f5e2  shr     r11d, 5
0x18000f5e6  and     r11d, 1FFh
0x18000f5ed  jbe     short loc_18000F60A
0x18000f5ef  mov     ecx, ebx
0x18000f5f1  mov     [r9+4], r11d
0x18000f5f5  neg     ecx
0x18000f5f7  lea     r10, [r9+8]
0x18000f5fb  sbb     edx, edx
0x18000f5fd  not     edx
0x18000f5ff  and     edx, 4
0x18000f602  mov     [r10], edx
0x18000f605  and     eax, 0FFFFC01Fh
0x18000f60a  xor     edx, edx
0x18000f60c  mov     ecx, 4000h
0x18000f611  cmp     ebx, 4
0x18000f614  cmovz   edx, ecx
0x18000f617  mov     ecx, eax
0x18000f619  btr     ecx, 0Eh
0x18000f61d  mov     eax, edx
0x18000f61f  or      eax, ecx
0x18000f621  mov     ecx, eax
0x18000f623  shr     ecx, 5
0x18000f626  and     ecx, 1FFh
0x18000f62c  lea     edx, [rcx+1]
0x18000f62f  cmp     edx, 1FFh
0x18000f635  ja      short loc_18000F641
0x18000f637  cmp     edx, ecx
0x18000f639  jb      short loc_18000F641
0x18000f63b  lea     r10, [r9+8]
0x18000f63f  jmp     short loc_18000F64D
0x18000f641  mov     edx, 1
0x18000f646  mov     [r10], ebx
0x18000f649  mov     [r9+4], ecx
0x18000f64d  shl     edx, 5
0x18000f650  xor     edx, eax
0x18000f652  and     edx, 3FE0h
0x18000f658  xor     edx, eax
0x18000f65a  mov     eax, r8d
0x18000f65d  lock cmpxchg [rsi], edx
0x18000f661  jz      short loc_18000F66B
0x18000f663  mov     r8d, eax
0x18000f666  jmp     loc_18000F5C5
0x18000f66b  not     r8d
0x18000f66e  mov     dword ptr [r9+10h], 0
0x18000f676  and     r8d, 1
0x18000f67a  mov     [r9], r8d
0x18000f67d  pop     rdi
0x18000f67e  pop     rsi
0x18000f67f  pop     rbx
0x18000f680  retn
```
