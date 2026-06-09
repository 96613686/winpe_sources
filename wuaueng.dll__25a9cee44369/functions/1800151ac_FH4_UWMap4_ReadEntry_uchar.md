# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x1800151ac`
- end: `0x18001524a`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014c70`
- `0x180015278`
- `0x18001534c`

## callees

- `0x1800151ac`

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
0x1800151ac  mov     r8, [rdx]
0x1800151af  lea     r11, cs:180000000h
0x1800151b6  mov     r10, rcx
0x1800151b9  mov     r9, rdx
0x1800151bc  movzx   ecx, byte ptr [r8]
0x1800151c0  and     ecx, 0Fh
0x1800151c3  movsx   rax, byte ptr [rcx+r11+18818h]
0x1800151cc  mov     cl, [rcx+r11+18828h]
0x1800151d4  sub     r8, rax
0x1800151d7  mov     eax, [r8-4]
0x1800151db  shr     eax, cl
0x1800151dd  mov     ecx, eax
0x1800151df  mov     [rdx], r8
0x1800151e2  and     ecx, 3
0x1800151e5  shr     eax, 2
0x1800151e8  mov     [r10+14h], ecx
0x1800151ec  mov     [r10+10h], eax
0x1800151f0  cmp     ecx, 1
0x1800151f3  jz      short loc_180015210
0x1800151f5  cmp     ecx, 2
0x1800151f8  jz      short loc_180015210
0x1800151fa  cmp     ecx, 3
0x1800151fd  jnz     short locret_180015249
0x1800151ff  mov     rax, [rdx]
0x180015202  mov     ecx, [rax]
0x180015204  add     rax, 4
0x180015208  mov     [rdx], rax
0x18001520b  mov     [r10+18h], ecx
0x18001520f  retn
0x180015210  mov     rax, [rdx]
0x180015213  mov     ecx, [rax]
0x180015215  add     rax, 4
0x180015219  mov     [rdx], rax
0x18001521c  mov     [r10+18h], ecx
0x180015220  mov     rdx, [rdx]
0x180015223  movzx   ecx, byte ptr [rdx]
0x180015226  and     ecx, 0Fh
0x180015229  movsx   rax, byte ptr [rcx+r11+18818h]
0x180015232  mov     cl, [rcx+r11+18828h]
0x18001523a  sub     rdx, rax
0x18001523d  mov     eax, [rdx-4]
0x180015240  shr     eax, cl
0x180015242  mov     [r9], rdx
0x180015245  mov     [r10+1Ch], eax
0x180015249  retn
```
