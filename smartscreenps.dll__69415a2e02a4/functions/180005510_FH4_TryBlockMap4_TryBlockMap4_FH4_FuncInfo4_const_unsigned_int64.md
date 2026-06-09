# FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)

- ea: `0x180005510`
- end: `0x1800055f4`
- name: `??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z`
- size: `228`
- prototype: `__int64 __fastcall(FH4::TryBlockMap4 *__hidden this, const struct FH4::FuncInfo4 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004304`
- `0x180004a60`
- `0x1800051a8`

## callees

- `0x180005510`

## pseudocode

```c
FH4::TryBlockMap4 *__fastcall FH4::TryBlockMap4::TryBlockMap4(
        FH4::TryBlockMap4 *this,
        const struct FH4::FuncInfo4 *a2,
        __int64 a3)
{
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  _BYTE *v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  _BYTE *v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  _BYTE *v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  _DWORD *v15; // rdx

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  if ( *((_DWORD *)a2 + 3) )
  {
    v4 = (_BYTE *)(a3 + *((int *)a2 + 3));
    *((_QWORD *)this + 1) = v4;
    v5 = *v4 & 0xF;
    v6 = &v4[-*((char *)&FH4::s_negLengthTab + v5)];
    v7 = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v6;
    *(_DWORD *)this = v7;
    *((_QWORD *)this + 2) = v6;
    v8 = *v6 & 0xF;
    v9 = &v6[-*((char *)&FH4::s_negLengthTab + v8)];
    v10 = *((_DWORD *)v9 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v8);
    *((_QWORD *)this + 1) = v9;
    *((_DWORD *)this + 6) = v10;
    v11 = *v9 & 0xF;
    v12 = &v9[-*((char *)&FH4::s_negLengthTab + v11)];
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *((_QWORD *)this + 1) = v12;
    *((_DWORD *)this + 7) = v13;
    v14 = *v12 & 0xF;
    v15 = &v12[-*((char *)&FH4::s_negLengthTab + v14)];
    *((_DWORD *)this + 8) = *(v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    *((_QWORD *)this + 1) = v15;
    LODWORD(v14) = *v15;
    *((_QWORD *)this + 1) = v15 + 1;
    *((_DWORD *)this + 9) = v14;
  }
  else
  {
    *(_DWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180005510  xor     eax, eax
0x180005512  xorps   xmm0, xmm0
0x180005515  mov     [rcx+8], rax
0x180005519  mov     r9, rcx
0x18000551c  mov     [rcx+10h], rax
0x180005520  movups  xmmword ptr [rcx+18h], xmm0
0x180005524  cmp     [rdx+0Ch], eax
0x180005527  jz      loc_1800055EE
0x18000552d  movsxd  rdx, dword ptr [rdx+0Ch]
0x180005531  add     rdx, r8
0x180005534  lea     r8, cs:180000000h
0x18000553b  mov     [rcx+8], rdx
0x18000553f  movzx   ecx, byte ptr [rdx]
0x180005542  and     ecx, 0Fh
0x180005545  movsx   rax, byte ptr [rcx+r8+14640h]
0x18000554e  mov     cl, [rcx+r8+14650h]
0x180005556  sub     rdx, rax
0x180005559  mov     eax, [rdx-4]
0x18000555c  shr     eax, cl
0x18000555e  mov     [r9+8], rdx
0x180005562  mov     [r9], eax
0x180005565  mov     [r9+10h], rdx
0x180005569  movzx   ecx, byte ptr [rdx]
0x18000556c  and     ecx, 0Fh
0x18000556f  movsx   rax, byte ptr [rcx+r8+14640h]
0x180005578  mov     cl, [rcx+r8+14650h]
0x180005580  sub     rdx, rax
0x180005583  mov     eax, [rdx-4]
0x180005586  shr     eax, cl
0x180005588  mov     [r9+8], rdx
0x18000558c  mov     [r9+18h], eax
0x180005590  movzx   ecx, byte ptr [rdx]
0x180005593  and     ecx, 0Fh
0x180005596  movsx   rax, byte ptr [rcx+r8+14640h]
0x18000559f  mov     cl, [rcx+r8+14650h]
0x1800055a7  sub     rdx, rax
0x1800055aa  mov     eax, [rdx-4]
0x1800055ad  shr     eax, cl
0x1800055af  mov     [r9+8], rdx
0x1800055b3  mov     [r9+1Ch], eax
0x1800055b7  movzx   ecx, byte ptr [rdx]
0x1800055ba  and     ecx, 0Fh
0x1800055bd  movsx   rax, byte ptr [rcx+r8+14640h]
0x1800055c6  mov     cl, [rcx+r8+14650h]
0x1800055ce  sub     rdx, rax
0x1800055d1  mov     eax, [rdx-4]
0x1800055d4  shr     eax, cl
0x1800055d6  mov     [r9+20h], eax
0x1800055da  lea     rax, [rdx+4]
0x1800055de  mov     [r9+8], rdx
0x1800055e2  mov     ecx, [rdx]
0x1800055e4  mov     [r9+8], rax
0x1800055e8  mov     [r9+24h], ecx
0x1800055ec  jmp     short loc_1800055F0
0x1800055ee  mov     [rcx], eax
0x1800055f0  mov     rax, r9
0x1800055f3  retn
```
