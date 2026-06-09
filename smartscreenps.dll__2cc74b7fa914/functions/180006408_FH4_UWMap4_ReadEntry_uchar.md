# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x180006408`
- end: `0x1800064a4`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `156`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ef4`
- `0x1800064d4`
- `0x1800065a8`

## callees

- `0x180006408`

## pseudocode

```c
void __fastcall FH4::UWMap4::ReadEntry(FH4::UWMap4 *this, unsigned __int8 **a2)
{
  __int64 v4; // rcx
  unsigned __int8 *v5; // r8
  unsigned int v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int *v10; // rdx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax

  v4 = **a2 & 0xF;
  v5 = &(*a2)[-*((char *)&FH4::s_negLengthTab + v4)];
  v6 = *((_DWORD *)v5 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v4);
  *a2 = v5;
  v7 = v6 & 3;
  *((_DWORD *)this + 4) = v6 >> 2;
  *((_DWORD *)this + 5) = v7;
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    v9 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v9;
    v10 = (int *)*a2;
    v11 = *(_BYTE *)v10 & 0xF;
    v12 = (unsigned __int8 *)v10 - *((char *)&FH4::s_negLengthTab + v11);
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *a2 = v12;
    *((_DWORD *)this + 7) = v13;
  }
  else if ( v7 == 3 )
  {
    v8 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v8;
  }
}

```

## disassembly

```asm
0x180006408  mov     r8, [rdx]
0x18000640b  lea     r11, cs:180000000h
0x180006412  mov     r10, rcx
0x180006415  mov     r9, rdx
0x180006418  movzx   ecx, byte ptr [r8]
0x18000641c  and     ecx, 0Fh
0x18000641f  movsx   rax, byte ptr [rcx+r11+14640h]
0x180006428  mov     cl, [rcx+r11+14650h]
0x180006430  sub     r8, rax
0x180006433  mov     eax, [r8-4]
0x180006437  shr     eax, cl
0x180006439  mov     ecx, eax
0x18000643b  mov     [rdx], r8
0x18000643e  and     ecx, 3
0x180006441  shr     eax, 2
0x180006444  mov     [r10+10h], eax
0x180006448  mov     [r10+14h], ecx
0x18000644c  lea     eax, [rcx-1]
0x18000644f  cmp     eax, 1
0x180006452  jbe     short loc_18000646A
0x180006454  cmp     ecx, 3
0x180006457  jnz     short locret_1800064A3
0x180006459  mov     rax, [rdx]
0x18000645c  mov     ecx, [rax]
0x18000645e  add     rax, 4
0x180006462  mov     [rdx], rax
0x180006465  mov     [r10+18h], ecx
0x180006469  retn
0x18000646a  mov     rax, [rdx]
0x18000646d  mov     ecx, [rax]
0x18000646f  add     rax, 4
0x180006473  mov     [rdx], rax
0x180006476  mov     [r10+18h], ecx
0x18000647a  mov     rdx, [rdx]
0x18000647d  movzx   ecx, byte ptr [rdx]
0x180006480  and     ecx, 0Fh
0x180006483  movsx   rax, byte ptr [rcx+r11+14640h]
0x18000648c  mov     cl, [rcx+r11+14650h]
0x180006494  sub     rdx, rax
0x180006497  mov     eax, [rdx-4]
0x18000649a  shr     eax, cl
0x18000649c  mov     [r9], rdx
0x18000649f  mov     [r10+1Ch], eax
0x1800064a3  retn
```
