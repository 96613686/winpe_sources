# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140010574`
- end: `0x14001064a`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001186c`

## callees

- `0x140010574`

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
0x140010574  push    rbx
0x140010576  push    rsi
0x140010577  push    rdi
0x140010578  mov     r8d, [rcx]
0x14001057b  lea     r10, [r9+8]
0x14001057f  xor     edi, edi
0x140010581  mov     ebx, edx
0x140010583  cmp     edx, 4
0x140010586  mov     rsi, rcx
0x140010589  setz    dil
0x14001058d  mov     eax, r8d
0x140010590  mov     dword ptr [r9+4], 0
0x140010598  or      eax, 1
0x14001059b  mov     ecx, eax
0x14001059d  shr     ecx, 0Eh
0x1400105a0  and     ecx, 1
0x1400105a3  cmp     ecx, edi
0x1400105a5  jz      short loc_1400105E9
0x1400105a7  mov     r11d, eax
0x1400105aa  shr     r11d, 5
0x1400105ae  and     r11d, 1FFh
0x1400105b5  jbe     short loc_1400105D2
0x1400105b7  mov     ecx, ebx
0x1400105b9  mov     [r9+4], r11d
0x1400105bd  neg     ecx
0x1400105bf  lea     r10, [r9+8]
0x1400105c3  sbb     edx, edx
0x1400105c5  not     edx
0x1400105c7  and     edx, 4
0x1400105ca  mov     [r10], edx
0x1400105cd  and     eax, 0FFFFC01Fh
0x1400105d2  xor     edx, edx
0x1400105d4  mov     ecx, 4000h
0x1400105d9  cmp     ebx, 4
0x1400105dc  cmovz   edx, ecx
0x1400105df  mov     ecx, eax
0x1400105e1  btr     ecx, 0Eh
0x1400105e5  mov     eax, edx
0x1400105e7  or      eax, ecx
0x1400105e9  mov     ecx, eax
0x1400105eb  shr     ecx, 5
0x1400105ee  and     ecx, 1FFh
0x1400105f4  lea     edx, [rcx+1]
0x1400105f7  cmp     edx, 1FFh
0x1400105fd  ja      short loc_140010609
0x1400105ff  cmp     edx, ecx
0x140010601  jb      short loc_140010609
0x140010603  lea     r10, [r9+8]
0x140010607  jmp     short loc_140010615
0x140010609  mov     edx, 1
0x14001060e  mov     [r10], ebx
0x140010611  mov     [r9+4], ecx
0x140010615  shl     edx, 5
0x140010618  xor     edx, eax
0x14001061a  and     edx, 3FE0h
0x140010620  xor     edx, eax
0x140010622  mov     eax, r8d
0x140010625  lock cmpxchg [rsi], edx
0x140010629  jz      short loc_140010633
0x14001062b  mov     r8d, eax
0x14001062e  jmp     loc_14001058D
0x140010633  not     r8d
0x140010636  mov     dword ptr [r9+10h], 0
0x14001063e  and     r8d, 1
0x140010642  mov     [r9], r8d
0x140010645  pop     rdi
0x140010646  pop     rsi
0x140010647  pop     rbx
0x140010648  retn
```
