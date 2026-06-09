# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000c96c`
- end: `0x18000ca35`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cb18`

## callees

- `0x18000c96c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
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
0x18000c96c  push    rbx
0x18000c96e  push    rsi
0x18000c96f  push    rdi
0x18000c970  mov     r8d, [rcx]
0x18000c973  lea     r10, [r9+8]
0x18000c977  xor     ebx, ebx
0x18000c979  mov     r11d, edx
0x18000c97c  cmp     edx, 5
0x18000c97f  mov     rdi, rcx
0x18000c982  mov     esi, 1
0x18000c987  setz    bl
0x18000c98a  mov     eax, r8d
0x18000c98d  mov     dword ptr [r9+4], 0
0x18000c995  or      eax, esi
0x18000c997  mov     ecx, eax
0x18000c999  shr     ecx, 16h
0x18000c99c  and     ecx, esi
0x18000c99e  cmp     ecx, ebx
0x18000c9a0  jz      short loc_18000C9DF
0x18000c9a2  mov     edx, eax
0x18000c9a4  shr     edx, 0Fh
0x18000c9a7  and     edx, 7Fh
0x18000c9aa  jbe     short loc_18000C9C7
0x18000c9ac  cmp     r11d, esi
0x18000c9af  mov     [r9+4], edx
0x18000c9b3  mov     ecx, 5
0x18000c9b8  lea     r10, [r9+8]
0x18000c9bc  cmovnz  ecx, esi
0x18000c9bf  and     eax, 0FFC07FFFh
0x18000c9c4  mov     [r10], ecx
0x18000c9c7  xor     edx, edx
0x18000c9c9  mov     ecx, 400000h
0x18000c9ce  cmp     r11d, 5
0x18000c9d2  cmovz   edx, ecx
0x18000c9d5  mov     ecx, eax
0x18000c9d7  btr     ecx, 16h
0x18000c9db  mov     eax, edx
0x18000c9dd  or      eax, ecx
0x18000c9df  mov     ecx, eax
0x18000c9e1  shr     ecx, 0Fh
0x18000c9e4  and     ecx, 7Fh
0x18000c9e7  lea     edx, [rcx+1]
0x18000c9ea  cmp     edx, 7Fh
0x18000c9ed  ja      short loc_18000C9F9
0x18000c9ef  cmp     edx, ecx
0x18000c9f1  jb      short loc_18000C9F9
0x18000c9f3  lea     r10, [r9+8]
0x18000c9f7  jmp     short loc_18000CA02
0x18000c9f9  mov     edx, esi
0x18000c9fb  mov     [r10], r11d
0x18000c9fe  mov     [r9+4], ecx
0x18000ca02  shl     edx, 0Fh
0x18000ca05  xor     edx, eax
0x18000ca07  and     edx, 3F8000h
0x18000ca0d  xor     edx, eax
0x18000ca0f  mov     eax, r8d
0x18000ca12  lock cmpxchg [rdi], edx
0x18000ca16  jz      short loc_18000CA20
0x18000ca18  mov     r8d, eax
0x18000ca1b  jmp     loc_18000C98A
0x18000ca20  not     r8d
0x18000ca23  mov     dword ptr [r9+10h], 0
0x18000ca2b  and     r8d, esi
0x18000ca2e  mov     [r9], r8d
0x18000ca31  pop     rdi
0x18000ca32  pop     rsi
0x18000ca33  pop     rbx
0x18000ca34  retn
```
