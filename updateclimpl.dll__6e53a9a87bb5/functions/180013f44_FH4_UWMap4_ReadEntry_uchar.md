# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x180013f44`
- end: `0x180013fe2`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013ab0`
- `0x180014010`
- `0x1800140e4`

## callees

- `0x180013f44`

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
0x180013f44  mov     r8, [rdx]
0x180013f47  lea     r11, cs:180000000h
0x180013f4e  mov     r10, rcx
0x180013f51  mov     r9, rdx
0x180013f54  movzx   ecx, byte ptr [r8]
0x180013f58  and     ecx, 0Fh
0x180013f5b  movsx   rax, byte ptr [rcx+r11+179D8h]
0x180013f64  mov     cl, [rcx+r11+179E8h]
0x180013f6c  sub     r8, rax
0x180013f6f  mov     eax, [r8-4]
0x180013f73  shr     eax, cl
0x180013f75  mov     ecx, eax
0x180013f77  mov     [rdx], r8
0x180013f7a  and     ecx, 3
0x180013f7d  shr     eax, 2
0x180013f80  mov     [r10+14h], ecx
0x180013f84  mov     [r10+10h], eax
0x180013f88  cmp     ecx, 1
0x180013f8b  jz      short loc_180013FA8
0x180013f8d  cmp     ecx, 2
0x180013f90  jz      short loc_180013FA8
0x180013f92  cmp     ecx, 3
0x180013f95  jnz     short locret_180013FE1
0x180013f97  mov     rax, [rdx]
0x180013f9a  mov     ecx, [rax]
0x180013f9c  add     rax, 4
0x180013fa0  mov     [rdx], rax
0x180013fa3  mov     [r10+18h], ecx
0x180013fa7  retn
0x180013fa8  mov     rax, [rdx]
0x180013fab  mov     ecx, [rax]
0x180013fad  add     rax, 4
0x180013fb1  mov     [rdx], rax
0x180013fb4  mov     [r10+18h], ecx
0x180013fb8  mov     rdx, [rdx]
0x180013fbb  movzx   ecx, byte ptr [rdx]
0x180013fbe  and     ecx, 0Fh
0x180013fc1  movsx   rax, byte ptr [rcx+r11+179D8h]
0x180013fca  mov     cl, [rcx+r11+179E8h]
0x180013fd2  sub     rdx, rax
0x180013fd5  mov     eax, [rdx-4]
0x180013fd8  shr     eax, cl
0x180013fda  mov     [r9], rdx
0x180013fdd  mov     [r10+1Ch], eax
0x180013fe1  retn
```
