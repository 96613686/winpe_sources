# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800105b0`
- end: `0x18001067a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001075c`

## callees

- `0x1800105b0`

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
0x1800105b0  push    rbx
0x1800105b2  push    rsi
0x1800105b3  push    rdi
0x1800105b4  mov     r8d, [rcx]
0x1800105b7  lea     r10, [r9+8]
0x1800105bb  xor     ebx, ebx
0x1800105bd  mov     r11d, edx
0x1800105c0  cmp     edx, 5
0x1800105c3  mov     rdi, rcx
0x1800105c6  mov     esi, 1
0x1800105cb  setz    bl
0x1800105ce  mov     eax, r8d
0x1800105d1  mov     dword ptr [r9+4], 0
0x1800105d9  or      eax, esi
0x1800105db  mov     ecx, eax
0x1800105dd  shr     ecx, 16h
0x1800105e0  and     ecx, esi
0x1800105e2  cmp     ecx, ebx
0x1800105e4  jz      short loc_180010623
0x1800105e6  mov     edx, eax
0x1800105e8  shr     edx, 0Fh
0x1800105eb  and     edx, 7Fh
0x1800105ee  jbe     short loc_18001060B
0x1800105f0  cmp     r11d, esi
0x1800105f3  mov     [r9+4], edx
0x1800105f7  mov     ecx, 5
0x1800105fc  lea     r10, [r9+8]
0x180010600  cmovnz  ecx, esi
0x180010603  and     eax, 0FFC07FFFh
0x180010608  mov     [r10], ecx
0x18001060b  xor     edx, edx
0x18001060d  mov     ecx, 400000h
0x180010612  cmp     r11d, 5
0x180010616  cmovz   edx, ecx
0x180010619  mov     ecx, eax
0x18001061b  btr     ecx, 16h
0x18001061f  mov     eax, edx
0x180010621  or      eax, ecx
0x180010623  mov     ecx, eax
0x180010625  shr     ecx, 0Fh
0x180010628  and     ecx, 7Fh
0x18001062b  lea     edx, [rcx+1]
0x18001062e  cmp     edx, 7Fh
0x180010631  ja      short loc_18001063D
0x180010633  cmp     edx, ecx
0x180010635  jb      short loc_18001063D
0x180010637  lea     r10, [r9+8]
0x18001063b  jmp     short loc_180010646
0x18001063d  mov     edx, esi
0x18001063f  mov     [r10], r11d
0x180010642  mov     [r9+4], ecx
0x180010646  shl     edx, 0Fh
0x180010649  xor     edx, eax
0x18001064b  and     edx, 3F8000h
0x180010651  xor     edx, eax
0x180010653  mov     eax, r8d
0x180010656  lock cmpxchg [rdi], edx
0x18001065a  jz      short loc_180010664
0x18001065c  mov     r8d, eax
0x18001065f  jmp     loc_1800105CE
0x180010664  not     r8d
0x180010667  mov     dword ptr [r9+10h], 0
0x18001066f  and     r8d, esi
0x180010672  mov     [r9], r8d
0x180010675  pop     rdi
0x180010676  pop     rsi
0x180010677  pop     rbx
0x180010678  retn
```
