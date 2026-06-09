# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140011d60`
- end: `0x140011e36`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011e3c`

## callees

- `0x140011d60`

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
0x140011d60  push    rbx
0x140011d62  push    rsi
0x140011d63  push    rdi
0x140011d64  mov     r8d, [rcx]
0x140011d67  lea     r10, [r9+8]
0x140011d6b  xor     edi, edi
0x140011d6d  mov     ebx, edx
0x140011d6f  cmp     edx, 4
0x140011d72  mov     rsi, rcx
0x140011d75  setz    dil
0x140011d79  mov     eax, r8d
0x140011d7c  mov     dword ptr [r9+4], 0
0x140011d84  or      eax, 1
0x140011d87  mov     ecx, eax
0x140011d89  shr     ecx, 0Eh
0x140011d8c  and     ecx, 1
0x140011d8f  cmp     ecx, edi
0x140011d91  jz      short loc_140011DD5
0x140011d93  mov     r11d, eax
0x140011d96  shr     r11d, 5
0x140011d9a  and     r11d, 1FFh
0x140011da1  jbe     short loc_140011DBE
0x140011da3  mov     ecx, ebx
0x140011da5  mov     [r9+4], r11d
0x140011da9  neg     ecx
0x140011dab  lea     r10, [r9+8]
0x140011daf  sbb     edx, edx
0x140011db1  not     edx
0x140011db3  and     edx, 4
0x140011db6  mov     [r10], edx
0x140011db9  and     eax, 0FFFFC01Fh
0x140011dbe  xor     edx, edx
0x140011dc0  mov     ecx, 4000h
0x140011dc5  cmp     ebx, 4
0x140011dc8  cmovz   edx, ecx
0x140011dcb  mov     ecx, eax
0x140011dcd  btr     ecx, 0Eh
0x140011dd1  mov     eax, edx
0x140011dd3  or      eax, ecx
0x140011dd5  mov     ecx, eax
0x140011dd7  shr     ecx, 5
0x140011dda  and     ecx, 1FFh
0x140011de0  lea     edx, [rcx+1]
0x140011de3  cmp     edx, 1FFh
0x140011de9  ja      short loc_140011DF5
0x140011deb  cmp     edx, ecx
0x140011ded  jb      short loc_140011DF5
0x140011def  lea     r10, [r9+8]
0x140011df3  jmp     short loc_140011E01
0x140011df5  mov     edx, 1
0x140011dfa  mov     [r10], ebx
0x140011dfd  mov     [r9+4], ecx
0x140011e01  shl     edx, 5
0x140011e04  xor     edx, eax
0x140011e06  and     edx, 3FE0h
0x140011e0c  xor     edx, eax
0x140011e0e  mov     eax, r8d
0x140011e11  lock cmpxchg [rsi], edx
0x140011e15  jz      short loc_140011E1F
0x140011e17  mov     r8d, eax
0x140011e1a  jmp     loc_140011D79
0x140011e1f  not     r8d
0x140011e22  mov     dword ptr [r9+10h], 0
0x140011e2a  and     r8d, 1
0x140011e2e  mov     [r9], r8d
0x140011e31  pop     rdi
0x140011e32  pop     rsi
0x140011e33  pop     rbx
0x140011e34  retn
```
