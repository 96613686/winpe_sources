# FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)

- ea: `0x140004468`
- end: `0x14000454c`
- name: `??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z`
- size: `228`
- prototype: `__int64 __fastcall(FH4::TryBlockMap4 *__hidden this, const struct FH4::FuncInfo4 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003624`
- `0x140003b64`
- `0x1400040e0`

## callees

- `0x140004468`

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
0x140004468  xor     eax, eax
0x14000446a  xorps   xmm0, xmm0
0x14000446d  mov     [rcx+8], rax
0x140004471  mov     r9, rcx
0x140004474  mov     [rcx+10h], rax
0x140004478  movups  xmmword ptr [rcx+18h], xmm0
0x14000447c  cmp     [rdx+0Ch], eax
0x14000447f  jz      loc_140004546
0x140004485  movsxd  rdx, dword ptr [rdx+0Ch]
0x140004489  add     rdx, r8
0x14000448c  lea     r8, cs:140000000h
0x140004493  mov     [rcx+8], rdx
0x140004497  movzx   ecx, byte ptr [rdx]
0x14000449a  and     ecx, 0Fh
0x14000449d  movsx   rax, byte ptr [rcx+r8+7460h]
0x1400044a6  mov     cl, [rcx+r8+7470h]
0x1400044ae  sub     rdx, rax
0x1400044b1  mov     eax, [rdx-4]
0x1400044b4  shr     eax, cl
0x1400044b6  mov     [r9+8], rdx
0x1400044ba  mov     [r9], eax
0x1400044bd  mov     [r9+10h], rdx
0x1400044c1  movzx   ecx, byte ptr [rdx]
0x1400044c4  and     ecx, 0Fh
0x1400044c7  movsx   rax, byte ptr [rcx+r8+7460h]
0x1400044d0  mov     cl, [rcx+r8+7470h]
0x1400044d8  sub     rdx, rax
0x1400044db  mov     eax, [rdx-4]
0x1400044de  shr     eax, cl
0x1400044e0  mov     [r9+8], rdx
0x1400044e4  mov     [r9+18h], eax
0x1400044e8  movzx   ecx, byte ptr [rdx]
0x1400044eb  and     ecx, 0Fh
0x1400044ee  movsx   rax, byte ptr [rcx+r8+7460h]
0x1400044f7  mov     cl, [rcx+r8+7470h]
0x1400044ff  sub     rdx, rax
0x140004502  mov     eax, [rdx-4]
0x140004505  shr     eax, cl
0x140004507  mov     [r9+8], rdx
0x14000450b  mov     [r9+1Ch], eax
0x14000450f  movzx   ecx, byte ptr [rdx]
0x140004512  and     ecx, 0Fh
0x140004515  movsx   rax, byte ptr [rcx+r8+7460h]
0x14000451e  mov     cl, [rcx+r8+7470h]
0x140004526  sub     rdx, rax
0x140004529  mov     eax, [rdx-4]
0x14000452c  shr     eax, cl
0x14000452e  mov     [r9+20h], eax
0x140004532  lea     rax, [rdx+4]
0x140004536  mov     [r9+8], rdx
0x14000453a  mov     ecx, [rdx]
0x14000453c  mov     [r9+8], rax
0x140004540  mov     [r9+24h], ecx
0x140004544  jmp     short loc_140004548
0x140004546  mov     [rcx], eax
0x140004548  mov     rax, r9
0x14000454b  retn
```
