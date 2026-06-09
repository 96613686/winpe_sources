# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180008ce8`
- end: `0x180008db1`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e94`

## callees

- `0x180008ce8`

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
0x180008ce8  push    rbx
0x180008cea  push    rsi
0x180008ceb  push    rdi
0x180008cec  mov     r8d, [rcx]
0x180008cef  lea     r10, [r9+8]
0x180008cf3  xor     ebx, ebx
0x180008cf5  mov     r11d, edx
0x180008cf8  cmp     edx, 5
0x180008cfb  mov     rdi, rcx
0x180008cfe  mov     esi, 1
0x180008d03  setz    bl
0x180008d06  mov     eax, r8d
0x180008d09  mov     dword ptr [r9+4], 0
0x180008d11  or      eax, esi
0x180008d13  mov     ecx, eax
0x180008d15  shr     ecx, 16h
0x180008d18  and     ecx, esi
0x180008d1a  cmp     ecx, ebx
0x180008d1c  jz      short loc_180008D5B
0x180008d1e  mov     edx, eax
0x180008d20  shr     edx, 0Fh
0x180008d23  and     edx, 7Fh
0x180008d26  jbe     short loc_180008D43
0x180008d28  cmp     r11d, esi
0x180008d2b  mov     [r9+4], edx
0x180008d2f  mov     ecx, 5
0x180008d34  lea     r10, [r9+8]
0x180008d38  cmovnz  ecx, esi
0x180008d3b  and     eax, 0FFC07FFFh
0x180008d40  mov     [r10], ecx
0x180008d43  xor     edx, edx
0x180008d45  mov     ecx, 400000h
0x180008d4a  cmp     r11d, 5
0x180008d4e  cmovz   edx, ecx
0x180008d51  mov     ecx, eax
0x180008d53  btr     ecx, 16h
0x180008d57  mov     eax, edx
0x180008d59  or      eax, ecx
0x180008d5b  mov     ecx, eax
0x180008d5d  shr     ecx, 0Fh
0x180008d60  and     ecx, 7Fh
0x180008d63  lea     edx, [rcx+1]
0x180008d66  cmp     edx, 7Fh
0x180008d69  ja      short loc_180008D75
0x180008d6b  cmp     edx, ecx
0x180008d6d  jb      short loc_180008D75
0x180008d6f  lea     r10, [r9+8]
0x180008d73  jmp     short loc_180008D7E
0x180008d75  mov     edx, esi
0x180008d77  mov     [r10], r11d
0x180008d7a  mov     [r9+4], ecx
0x180008d7e  shl     edx, 0Fh
0x180008d81  xor     edx, eax
0x180008d83  and     edx, 3F8000h
0x180008d89  xor     edx, eax
0x180008d8b  mov     eax, r8d
0x180008d8e  lock cmpxchg [rdi], edx
0x180008d92  jz      short loc_180008D9C
0x180008d94  mov     r8d, eax
0x180008d97  jmp     loc_180008D06
0x180008d9c  not     r8d
0x180008d9f  mov     dword ptr [r9+10h], 0
0x180008da7  and     r8d, esi
0x180008daa  mov     [r9], r8d
0x180008dad  pop     rdi
0x180008dae  pop     rsi
0x180008daf  pop     rbx
0x180008db0  retn
```
