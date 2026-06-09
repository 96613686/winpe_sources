# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180016f90`
- end: `0x180017066`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001706c`

## callees

- `0x180016f90`

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
0x180016f90  push    rbx
0x180016f92  push    rsi
0x180016f93  push    rdi
0x180016f94  mov     r8d, [rcx]
0x180016f97  lea     r10, [r9+8]
0x180016f9b  xor     edi, edi
0x180016f9d  mov     ebx, edx
0x180016f9f  cmp     edx, 4
0x180016fa2  mov     rsi, rcx
0x180016fa5  setz    dil
0x180016fa9  mov     eax, r8d
0x180016fac  mov     dword ptr [r9+4], 0
0x180016fb4  or      eax, 1
0x180016fb7  mov     ecx, eax
0x180016fb9  shr     ecx, 0Eh
0x180016fbc  and     ecx, 1
0x180016fbf  cmp     ecx, edi
0x180016fc1  jz      short loc_180017005
0x180016fc3  mov     r11d, eax
0x180016fc6  shr     r11d, 5
0x180016fca  and     r11d, 1FFh
0x180016fd1  jbe     short loc_180016FEE
0x180016fd3  mov     ecx, ebx
0x180016fd5  mov     [r9+4], r11d
0x180016fd9  neg     ecx
0x180016fdb  lea     r10, [r9+8]
0x180016fdf  sbb     edx, edx
0x180016fe1  not     edx
0x180016fe3  and     edx, 4
0x180016fe6  mov     [r10], edx
0x180016fe9  and     eax, 0FFFFC01Fh
0x180016fee  xor     edx, edx
0x180016ff0  mov     ecx, 4000h
0x180016ff5  cmp     ebx, 4
0x180016ff8  cmovz   edx, ecx
0x180016ffb  mov     ecx, eax
0x180016ffd  btr     ecx, 0Eh
0x180017001  mov     eax, edx
0x180017003  or      eax, ecx
0x180017005  mov     ecx, eax
0x180017007  shr     ecx, 5
0x18001700a  and     ecx, 1FFh
0x180017010  lea     edx, [rcx+1]
0x180017013  cmp     edx, 1FFh
0x180017019  ja      short loc_180017025
0x18001701b  cmp     edx, ecx
0x18001701d  jb      short loc_180017025
0x18001701f  lea     r10, [r9+8]
0x180017023  jmp     short loc_180017031
0x180017025  mov     edx, 1
0x18001702a  mov     [r10], ebx
0x18001702d  mov     [r9+4], ecx
0x180017031  shl     edx, 5
0x180017034  xor     edx, eax
0x180017036  and     edx, 3FE0h
0x18001703c  xor     edx, eax
0x18001703e  mov     eax, r8d
0x180017041  lock cmpxchg [rsi], edx
0x180017045  jz      short loc_18001704F
0x180017047  mov     r8d, eax
0x18001704a  jmp     loc_180016FA9
0x18001704f  not     r8d
0x180017052  mov     dword ptr [r9+10h], 0
0x18001705a  and     r8d, 1
0x18001705e  mov     [r9], r8d
0x180017061  pop     rdi
0x180017062  pop     rsi
0x180017063  pop     rbx
0x180017064  retn
```
