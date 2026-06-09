# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001a2ac`
- end: `0x18001a375`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aac4`

## callees

- `0x18001a2ac`

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
0x18001a2ac  push    rbx
0x18001a2ae  push    rsi
0x18001a2af  push    rdi
0x18001a2b0  mov     r8d, [rcx]
0x18001a2b3  lea     r10, [r9+8]
0x18001a2b7  xor     ebx, ebx
0x18001a2b9  mov     r11d, edx
0x18001a2bc  cmp     edx, 5
0x18001a2bf  mov     rdi, rcx
0x18001a2c2  mov     esi, 1
0x18001a2c7  setz    bl
0x18001a2ca  mov     eax, r8d
0x18001a2cd  mov     dword ptr [r9+4], 0
0x18001a2d5  or      eax, esi
0x18001a2d7  mov     ecx, eax
0x18001a2d9  shr     ecx, 16h
0x18001a2dc  and     ecx, esi
0x18001a2de  cmp     ecx, ebx
0x18001a2e0  jz      short loc_18001A31F
0x18001a2e2  mov     edx, eax
0x18001a2e4  shr     edx, 0Fh
0x18001a2e7  and     edx, 7Fh
0x18001a2ea  jbe     short loc_18001A307
0x18001a2ec  cmp     r11d, esi
0x18001a2ef  mov     [r9+4], edx
0x18001a2f3  mov     ecx, 5
0x18001a2f8  lea     r10, [r9+8]
0x18001a2fc  cmovnz  ecx, esi
0x18001a2ff  and     eax, 0FFC07FFFh
0x18001a304  mov     [r10], ecx
0x18001a307  xor     edx, edx
0x18001a309  mov     ecx, 400000h
0x18001a30e  cmp     r11d, 5
0x18001a312  cmovz   edx, ecx
0x18001a315  mov     ecx, eax
0x18001a317  btr     ecx, 16h
0x18001a31b  mov     eax, edx
0x18001a31d  or      eax, ecx
0x18001a31f  mov     ecx, eax
0x18001a321  shr     ecx, 0Fh
0x18001a324  and     ecx, 7Fh
0x18001a327  lea     edx, [rcx+1]
0x18001a32a  cmp     edx, 7Fh
0x18001a32d  ja      short loc_18001A339
0x18001a32f  cmp     edx, ecx
0x18001a331  jb      short loc_18001A339
0x18001a333  lea     r10, [r9+8]
0x18001a337  jmp     short loc_18001A342
0x18001a339  mov     edx, esi
0x18001a33b  mov     [r10], r11d
0x18001a33e  mov     [r9+4], ecx
0x18001a342  shl     edx, 0Fh
0x18001a345  xor     edx, eax
0x18001a347  and     edx, 3F8000h
0x18001a34d  xor     edx, eax
0x18001a34f  mov     eax, r8d
0x18001a352  lock cmpxchg [rdi], edx
0x18001a356  jz      short loc_18001A360
0x18001a358  mov     r8d, eax
0x18001a35b  jmp     loc_18001A2CA
0x18001a360  not     r8d
0x18001a363  mov     dword ptr [r9+10h], 0
0x18001a36b  and     r8d, esi
0x18001a36e  mov     [r9], r8d
0x18001a371  pop     rdi
0x18001a372  pop     rsi
0x18001a373  pop     rbx
0x18001a374  retn
```
