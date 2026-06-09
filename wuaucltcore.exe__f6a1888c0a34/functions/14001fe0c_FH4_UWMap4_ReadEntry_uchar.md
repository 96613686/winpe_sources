# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x14001fe0c`
- end: `0x14001feaa`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f8d0`
- `0x14001fed8`
- `0x14001ffac`

## callees

- `0x14001fe0c`

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
0x14001fe0c  mov     r8, [rdx]
0x14001fe0f  lea     r11, __ImageBase
0x14001fe16  mov     r10, rcx
0x14001fe19  mov     r9, rdx
0x14001fe1c  movzx   ecx, byte ptr [r8]
0x14001fe20  and     ecx, 0Fh
0x14001fe23  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001fe2c  mov     cl, [rcx+r11+23BA0h]
0x14001fe34  sub     r8, rax
0x14001fe37  mov     eax, [r8-4]
0x14001fe3b  shr     eax, cl
0x14001fe3d  mov     ecx, eax
0x14001fe3f  mov     [rdx], r8
0x14001fe42  and     ecx, 3
0x14001fe45  shr     eax, 2
0x14001fe48  mov     [r10+14h], ecx
0x14001fe4c  mov     [r10+10h], eax
0x14001fe50  cmp     ecx, 1
0x14001fe53  jz      short loc_14001FE70
0x14001fe55  cmp     ecx, 2
0x14001fe58  jz      short loc_14001FE70
0x14001fe5a  cmp     ecx, 3
0x14001fe5d  jnz     short locret_14001FEA9
0x14001fe5f  mov     rax, [rdx]
0x14001fe62  mov     ecx, [rax]
0x14001fe64  add     rax, 4
0x14001fe68  mov     [rdx], rax
0x14001fe6b  mov     [r10+18h], ecx
0x14001fe6f  retn
0x14001fe70  mov     rax, [rdx]
0x14001fe73  mov     ecx, [rax]
0x14001fe75  add     rax, 4
0x14001fe79  mov     [rdx], rax
0x14001fe7c  mov     [r10+18h], ecx
0x14001fe80  mov     rdx, [rdx]
0x14001fe83  movzx   ecx, byte ptr [rdx]
0x14001fe86  and     ecx, 0Fh
0x14001fe89  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001fe92  mov     cl, [rcx+r11+23BA0h]
0x14001fe9a  sub     rdx, rax
0x14001fe9d  mov     eax, [rdx-4]
0x14001fea0  shr     eax, cl
0x14001fea2  mov     [r9], rdx
0x14001fea5  mov     [r10+1Ch], eax
0x14001fea9  retn
```
