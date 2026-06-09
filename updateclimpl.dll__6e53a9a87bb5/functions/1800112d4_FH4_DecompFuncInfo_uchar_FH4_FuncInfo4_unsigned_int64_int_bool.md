# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x1800112d4`
- end: `0x180011400`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011a20`

## callees

- `0x1800112d4`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
  _BYTE *v6; // r10
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // edx
  _BYTE *v15; // r8
  _BYTE *v16; // r9
  __int64 v17; // rcx
  int *v18; // r9
  unsigned int v19; // r10d
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v11 = *v6 & 0xF;
    v6 -= *((char *)&FH4::s_negLengthTab + v11);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
  }
  if ( (v5 & 8) != 0 )
  {
    v12 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 2) = v12;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v13 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 3) = v13;
  }
  v14 = 0;
  v15 = v6 + 4;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = *(_DWORD *)v6;
  }
  else
  {
    *((_DWORD *)a2 + 4) = 0;
    if ( !*(_DWORD *)v6 )
      __fastfail(7u);
    v16 = (char *)a3 + *(int *)v6;
    v17 = *v16 & 0xF;
    v18 = (int *)&v16[-*((char *)&FH4::s_negLengthTab + v17)];
    v19 = (unsigned int)*(v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
    if ( v19 )
    {
      while ( 1 )
      {
        v20 = *v18;
        v21 = v18[1];
        v18 += 2;
        if ( v20 == a4 )
          break;
        if ( ++v14 >= v19 )
          goto LABEL_17;
      }
      *((_DWORD *)a2 + 4) = v21;
    }
  }
LABEL_17:
  if ( (v5 & 1) != 0 )
  {
    v22 = *v15 & 0xF;
    v15 -= *((char *)&FH4::s_negLengthTab + v22);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v22);
  }
  return v15 - (_BYTE *)this;
}

```

## disassembly

```asm
0x1800112d4  mov     rax, rsp
0x1800112d7  mov     [rax+8], rbx
0x1800112db  mov     [rax+10h], rbp
0x1800112df  mov     [rax+18h], rsi
0x1800112e3  mov     [rax+20h], rdi
0x1800112e7  mov     bl, [rcx]
0x1800112e9  lea     r10, [rcx+1]
0x1800112ed  mov     [rdx], bl
0x1800112ef  mov     esi, r9d
0x1800112f2  lea     rbp, cs:180000000h
0x1800112f9  mov     r9, r8
0x1800112fc  mov     r11, rdx
0x1800112ff  mov     rdi, rcx
0x180011302  test    bl, 4
0x180011305  jz      short loc_18001132A
0x180011307  movzx   ecx, byte ptr [r10]
0x18001130b  and     ecx, 0Fh
0x18001130e  movsx   rax, byte ptr [rcx+rbp+179D8h]
0x180011317  mov     cl, [rcx+rbp+179E8h]
0x18001131e  sub     r10, rax
0x180011321  mov     eax, [r10-4]
0x180011325  shr     eax, cl
0x180011327  mov     [rdx+4], eax
0x18001132a  test    bl, 8
0x18001132d  jz      short loc_180011339
0x18001132f  mov     eax, [r10]
0x180011332  add     r10, 4
0x180011336  mov     [rdx+8], eax
0x180011339  test    bl, 10h
0x18001133c  jz      short loc_180011348
0x18001133e  mov     eax, [r10]
0x180011341  add     r10, 4
0x180011345  mov     [rdx+0Ch], eax
0x180011348  xor     edx, edx
0x18001134a  lea     r8, [r10+4]
0x18001134e  cmp     [rsp+arg_20], dl
0x180011352  jnz     short loc_1800113B5
0x180011354  test    bl, 2
0x180011357  jz      short loc_1800113B5
0x180011359  mov     [r11+10h], edx
0x18001135d  cmp     [r10], edx
0x180011360  jz      short loc_1800113AC
0x180011362  movsxd  rax, dword ptr [r10]
0x180011365  add     r9, rax
0x180011368  movzx   ecx, byte ptr [r9]
0x18001136c  and     ecx, 0Fh
0x18001136f  movsx   rax, byte ptr [rcx+rbp+179D8h]
0x180011378  mov     cl, [rcx+rbp+179E8h]
0x18001137f  sub     r9, rax
0x180011382  mov     r10d, [r9-4]
0x180011386  shr     r10d, cl
0x180011389  test    r10d, r10d
0x18001138c  jz      short loc_1800113BC
0x18001138e  mov     eax, [r9]
0x180011391  mov     ecx, [r9+4]
0x180011395  lea     r9, [r9+8]
0x180011399  cmp     eax, esi
0x18001139b  jz      short loc_1800113A6
0x18001139d  inc     edx
0x18001139f  cmp     edx, r10d
0x1800113a2  jb      short loc_18001138E
0x1800113a4  jmp     short loc_1800113BC
0x1800113a6  mov     [r11+10h], ecx
0x1800113aa  jmp     short loc_1800113BC
0x1800113ac  mov     ecx, 7
0x1800113b1  int     29h; Win8: RtlFailFast(ecx)
0x1800113b3  jmp     short loc_1800113BC
0x1800113b5  mov     eax, [r10]
0x1800113b8  mov     [r11+10h], eax
0x1800113bc  test    bl, 1
0x1800113bf  jz      short loc_1800113E5
0x1800113c1  movzx   ecx, byte ptr [r8]
0x1800113c5  and     ecx, 0Fh
0x1800113c8  movsx   rdx, byte ptr [rcx+rbp+179D8h]
0x1800113d1  mov     cl, [rcx+rbp+179E8h]
0x1800113d8  sub     r8, rdx
0x1800113db  mov     edx, [r8-4]
0x1800113df  shr     edx, cl
0x1800113e1  mov     [r11+14h], edx
0x1800113e5  mov     rbx, [rsp+arg_0]
0x1800113ea  sub     r8, rdi
0x1800113ed  mov     rbp, [rsp+arg_8]
0x1800113f2  mov     rax, r8
0x1800113f5  mov     rsi, [rsp+arg_10]
0x1800113fa  mov     rdi, [rsp+arg_18]
0x1800113ff  retn
```
