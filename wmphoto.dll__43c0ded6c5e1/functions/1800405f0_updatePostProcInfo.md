# updatePostProcInfo

- ea: `0x1800405f0`
- end: `0x180040674`
- name: `updatePostProcInfo`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800263c0`

## callees

- `0x1800405f0`

## pseudocode

```c
unsigned __int64 __fastcall updatePostProcInfo(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r10
  unsigned __int64 result; // rax
  unsigned __int64 i; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r8

  v5 = 88 * a3 + *(_QWORD *)(a1 + 16 * a4 + 8);
  *(_DWORD *)v5 = *a2;
  result = 16;
  *(_BYTE *)(v5 + 4) = 0;
  while ( result < 0x100 )
  {
    if ( a2[result] )
    {
      *(_BYTE *)(v5 + 4) = 3;
      break;
    }
    result += 16LL;
  }
  for ( i = 0; i < 4; ++i )
  {
    v8 = 0;
    v9 = v5 + 4 * i;
    do
    {
      v10 = 1;
      *(_BYTE *)(v9 + v8 + 72) = 0;
      while ( v10 < 0x10 )
      {
        result = v10 + 16 * (i + 4 * v8);
        if ( a2[result] )
        {
          *(_BYTE *)(v9 + v8 + 72) = 3;
          break;
        }
        ++v10;
      }
      ++v8;
    }
    while ( v8 < 4 );
  }
  return result;
}

```

## disassembly

```asm
0x1800405f0  mov     eax, [rdx]
0x1800405f2  add     r9, r9
0x1800405f5  imul    r8, 58h ; 'X'
0x1800405f9  mov     r10, [rcx+r9*8+8]
0x1800405fe  mov     r11, rdx
0x180040601  add     r10, r8
0x180040604  mov     [r10], eax
0x180040607  mov     eax, 10h
0x18004060c  mov     byte ptr [r10+4], 0
0x180040611  cmp     rax, 100h
0x180040617  jnb     short loc_18004062A
0x180040619  cmp     dword ptr [rdx+rax*4], 0
0x18004061d  jnz     short loc_180040625
0x18004061f  add     rax, 10h
0x180040623  jmp     short loc_180040611
0x180040625  mov     byte ptr [r10+4], 3
0x18004062a  xor     edx, edx
0x18004062c  xor     ecx, ecx
0x18004062e  lea     r9, [r10+rdx*4]
0x180040632  mov     r8d, 1
0x180040638  mov     byte ptr [r9+rcx+48h], 0
0x18004063e  cmp     r8, 10h
0x180040642  jnb     short loc_180040661
0x180040644  lea     rax, [rdx+rcx*4]
0x180040648  shl     rax, 4
0x18004064c  add     rax, r8
0x18004064f  cmp     dword ptr [r11+rax*4], 0
0x180040654  jnz     short loc_18004065B
0x180040656  inc     r8
0x180040659  jmp     short loc_18004063E
0x18004065b  mov     byte ptr [r9+rcx+48h], 3
0x180040661  inc     rcx
0x180040664  cmp     rcx, 4
0x180040668  jb      short loc_180040632
0x18004066a  inc     rdx
0x18004066d  cmp     rdx, 4
0x180040671  jb      short loc_18004062C
0x180040673  retn
```
