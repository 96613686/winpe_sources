# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x140004fb4`
- end: `0x140005052`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004b20`
- `0x140005080`
- `0x140005154`

## callees

- `0x140004fb4`

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
0x140004fb4  mov     r8, [rdx]
0x140004fb7  lea     r11, cs:140000000h
0x140004fbe  mov     r10, rcx
0x140004fc1  mov     r9, rdx
0x140004fc4  movzx   ecx, byte ptr [r8]
0x140004fc8  and     ecx, 0Fh
0x140004fcb  movsx   rax, byte ptr [rcx+r11+7460h]
0x140004fd4  mov     cl, [rcx+r11+7470h]
0x140004fdc  sub     r8, rax
0x140004fdf  mov     eax, [r8-4]
0x140004fe3  shr     eax, cl
0x140004fe5  mov     ecx, eax
0x140004fe7  mov     [rdx], r8
0x140004fea  and     ecx, 3
0x140004fed  shr     eax, 2
0x140004ff0  mov     [r10+14h], ecx
0x140004ff4  mov     [r10+10h], eax
0x140004ff8  cmp     ecx, 1
0x140004ffb  jz      short loc_140005018
0x140004ffd  cmp     ecx, 2
0x140005000  jz      short loc_140005018
0x140005002  cmp     ecx, 3
0x140005005  jnz     short locret_140005051
0x140005007  mov     rax, [rdx]
0x14000500a  mov     ecx, [rax]
0x14000500c  add     rax, 4
0x140005010  mov     [rdx], rax
0x140005013  mov     [r10+18h], ecx
0x140005017  retn
0x140005018  mov     rax, [rdx]
0x14000501b  mov     ecx, [rax]
0x14000501d  add     rax, 4
0x140005021  mov     [rdx], rax
0x140005024  mov     [r10+18h], ecx
0x140005028  mov     rdx, [rdx]
0x14000502b  movzx   ecx, byte ptr [rdx]
0x14000502e  and     ecx, 0Fh
0x140005031  movsx   rax, byte ptr [rcx+r11+7460h]
0x14000503a  mov     cl, [rcx+r11+7470h]
0x140005042  sub     rdx, rax
0x140005045  mov     eax, [rdx-4]
0x140005048  shr     eax, cl
0x14000504a  mov     [r9], rdx
0x14000504d  mov     [r10+1Ch], eax
0x140005051  retn
```
