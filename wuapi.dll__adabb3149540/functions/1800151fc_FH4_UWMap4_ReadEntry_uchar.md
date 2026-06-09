# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x1800151fc`
- end: `0x18001529a`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014cc0`
- `0x1800152c8`
- `0x18001539c`

## callees

- `0x1800151fc`

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
  *((_DWORD *)this + 5) = v7;
  *((_DWORD *)this + 4) = v6 >> 2;
  if ( v7 == 1 || v7 == 2 )
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
0x1800151fc  mov     r8, [rdx]
0x1800151ff  lea     r11, cs:180000000h
0x180015206  mov     r10, rcx
0x180015209  mov     r9, rdx
0x18001520c  movzx   ecx, byte ptr [r8]
0x180015210  and     ecx, 0Fh
0x180015213  movsx   rax, byte ptr [rcx+r11+18818h]
0x18001521c  mov     cl, [rcx+r11+18828h]
0x180015224  sub     r8, rax
0x180015227  mov     eax, [r8-4]
0x18001522b  shr     eax, cl
0x18001522d  mov     ecx, eax
0x18001522f  mov     [rdx], r8
0x180015232  and     ecx, 3
0x180015235  shr     eax, 2
0x180015238  mov     [r10+14h], ecx
0x18001523c  mov     [r10+10h], eax
0x180015240  cmp     ecx, 1
0x180015243  jz      short loc_180015260
0x180015245  cmp     ecx, 2
0x180015248  jz      short loc_180015260
0x18001524a  cmp     ecx, 3
0x18001524d  jnz     short locret_180015299
0x18001524f  mov     rax, [rdx]
0x180015252  mov     ecx, [rax]
0x180015254  add     rax, 4
0x180015258  mov     [rdx], rax
0x18001525b  mov     [r10+18h], ecx
0x18001525f  retn
0x180015260  mov     rax, [rdx]
0x180015263  mov     ecx, [rax]
0x180015265  add     rax, 4
0x180015269  mov     [rdx], rax
0x18001526c  mov     [r10+18h], ecx
0x180015270  mov     rdx, [rdx]
0x180015273  movzx   ecx, byte ptr [rdx]
0x180015276  and     ecx, 0Fh
0x180015279  movsx   rax, byte ptr [rcx+r11+18818h]
0x180015282  mov     cl, [rcx+r11+18828h]
0x18001528a  sub     rdx, rax
0x18001528d  mov     eax, [rdx-4]
0x180015290  shr     eax, cl
0x180015292  mov     [r9], rdx
0x180015295  mov     [r10+1Ch], eax
0x180015299  retn
```
