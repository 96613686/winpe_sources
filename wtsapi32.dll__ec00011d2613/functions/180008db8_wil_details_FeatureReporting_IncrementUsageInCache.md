# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180008db8`
- end: `0x180008e8d`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e94`

## callees

- `0x180008db8`

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
0x180008db8  push    rbx
0x180008dba  push    rsi
0x180008dbb  push    rdi
0x180008dbc  mov     r8d, [rcx]
0x180008dbf  lea     r10, [r9+8]
0x180008dc3  xor     edi, edi
0x180008dc5  mov     ebx, edx
0x180008dc7  cmp     edx, 4
0x180008dca  mov     rsi, rcx
0x180008dcd  setz    dil
0x180008dd1  mov     eax, r8d
0x180008dd4  mov     dword ptr [r9+4], 0
0x180008ddc  or      eax, 1
0x180008ddf  mov     ecx, eax
0x180008de1  shr     ecx, 0Eh
0x180008de4  and     ecx, 1
0x180008de7  cmp     ecx, edi
0x180008de9  jz      short loc_180008E2D
0x180008deb  mov     r11d, eax
0x180008dee  shr     r11d, 5
0x180008df2  and     r11d, 1FFh
0x180008df9  jbe     short loc_180008E16
0x180008dfb  mov     ecx, ebx
0x180008dfd  mov     [r9+4], r11d
0x180008e01  neg     ecx
0x180008e03  lea     r10, [r9+8]
0x180008e07  sbb     edx, edx
0x180008e09  not     edx
0x180008e0b  and     edx, 4
0x180008e0e  mov     [r10], edx
0x180008e11  and     eax, 0FFFFC01Fh
0x180008e16  xor     edx, edx
0x180008e18  mov     ecx, 4000h
0x180008e1d  cmp     ebx, 4
0x180008e20  cmovz   edx, ecx
0x180008e23  mov     ecx, eax
0x180008e25  btr     ecx, 0Eh
0x180008e29  mov     eax, edx
0x180008e2b  or      eax, ecx
0x180008e2d  mov     ecx, eax
0x180008e2f  shr     ecx, 5
0x180008e32  and     ecx, 1FFh
0x180008e38  lea     edx, [rcx+1]
0x180008e3b  cmp     edx, 1FFh
0x180008e41  ja      short loc_180008E4D
0x180008e43  cmp     edx, ecx
0x180008e45  jb      short loc_180008E4D
0x180008e47  lea     r10, [r9+8]
0x180008e4b  jmp     short loc_180008E59
0x180008e4d  mov     edx, 1
0x180008e52  mov     [r10], ebx
0x180008e55  mov     [r9+4], ecx
0x180008e59  shl     edx, 5
0x180008e5c  xor     edx, eax
0x180008e5e  and     edx, 3FE0h
0x180008e64  xor     edx, eax
0x180008e66  mov     eax, r8d
0x180008e69  lock cmpxchg [rsi], edx
0x180008e6d  jz      short loc_180008E77
0x180008e6f  mov     r8d, eax
0x180008e72  jmp     loc_180008DD1
0x180008e77  not     r8d
0x180008e7a  mov     dword ptr [r9+10h], 0
0x180008e82  and     r8d, 1
0x180008e86  mov     [r9], r8d
0x180008e89  pop     rdi
0x180008e8a  pop     rsi
0x180008e8b  pop     rbx
0x180008e8c  retn
```
