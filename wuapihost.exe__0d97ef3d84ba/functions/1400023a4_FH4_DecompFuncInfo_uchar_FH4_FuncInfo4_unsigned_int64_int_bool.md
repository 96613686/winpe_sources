# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x1400023a4`
- end: `0x1400024d0`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002af0`

## callees

- `0x1400023a4`

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
0x1400023a4  mov     rax, rsp
0x1400023a7  mov     [rax+8], rbx
0x1400023ab  mov     [rax+10h], rbp
0x1400023af  mov     [rax+18h], rsi
0x1400023b3  mov     [rax+20h], rdi
0x1400023b7  mov     bl, [rcx]
0x1400023b9  lea     r10, [rcx+1]
0x1400023bd  mov     [rdx], bl
0x1400023bf  mov     esi, r9d
0x1400023c2  lea     rbp, cs:140000000h
0x1400023c9  mov     r9, r8
0x1400023cc  mov     r11, rdx
0x1400023cf  mov     rdi, rcx
0x1400023d2  test    bl, 4
0x1400023d5  jz      short loc_1400023FA
0x1400023d7  movzx   ecx, byte ptr [r10]
0x1400023db  and     ecx, 0Fh
0x1400023de  movsx   rax, byte ptr [rcx+rbp+7460h]
0x1400023e7  mov     cl, [rcx+rbp+7470h]
0x1400023ee  sub     r10, rax
0x1400023f1  mov     eax, [r10-4]
0x1400023f5  shr     eax, cl
0x1400023f7  mov     [rdx+4], eax
0x1400023fa  test    bl, 8
0x1400023fd  jz      short loc_140002409
0x1400023ff  mov     eax, [r10]
0x140002402  add     r10, 4
0x140002406  mov     [rdx+8], eax
0x140002409  test    bl, 10h
0x14000240c  jz      short loc_140002418
0x14000240e  mov     eax, [r10]
0x140002411  add     r10, 4
0x140002415  mov     [rdx+0Ch], eax
0x140002418  xor     edx, edx
0x14000241a  lea     r8, [r10+4]
0x14000241e  cmp     [rsp+arg_20], dl
0x140002422  jnz     short loc_140002485
0x140002424  test    bl, 2
0x140002427  jz      short loc_140002485
0x140002429  mov     [r11+10h], edx
0x14000242d  cmp     [r10], edx
0x140002430  jz      short loc_14000247C
0x140002432  movsxd  rax, dword ptr [r10]
0x140002435  add     r9, rax
0x140002438  movzx   ecx, byte ptr [r9]
0x14000243c  and     ecx, 0Fh
0x14000243f  movsx   rax, byte ptr [rcx+rbp+7460h]
0x140002448  mov     cl, [rcx+rbp+7470h]
0x14000244f  sub     r9, rax
0x140002452  mov     r10d, [r9-4]
0x140002456  shr     r10d, cl
0x140002459  test    r10d, r10d
0x14000245c  jz      short loc_14000248C
0x14000245e  mov     eax, [r9]
0x140002461  mov     ecx, [r9+4]
0x140002465  lea     r9, [r9+8]
0x140002469  cmp     eax, esi
0x14000246b  jz      short loc_140002476
0x14000246d  inc     edx
0x14000246f  cmp     edx, r10d
0x140002472  jb      short loc_14000245E
0x140002474  jmp     short loc_14000248C
0x140002476  mov     [r11+10h], ecx
0x14000247a  jmp     short loc_14000248C
0x14000247c  mov     ecx, 7
0x140002481  int     29h; Win8: RtlFailFast(ecx)
0x140002483  jmp     short loc_14000248C
0x140002485  mov     eax, [r10]
0x140002488  mov     [r11+10h], eax
0x14000248c  test    bl, 1
0x14000248f  jz      short loc_1400024B5
0x140002491  movzx   ecx, byte ptr [r8]
0x140002495  and     ecx, 0Fh
0x140002498  movsx   rdx, byte ptr [rcx+rbp+7460h]
0x1400024a1  mov     cl, [rcx+rbp+7470h]
0x1400024a8  sub     r8, rdx
0x1400024ab  mov     edx, [r8-4]
0x1400024af  shr     edx, cl
0x1400024b1  mov     [r11+14h], edx
0x1400024b5  mov     rbx, [rsp+arg_0]
0x1400024ba  sub     r8, rdi
0x1400024bd  mov     rbp, [rsp+arg_8]
0x1400024c2  mov     rax, r8
0x1400024c5  mov     rsi, [rsp+arg_10]
0x1400024ca  mov     rdi, [rsp+arg_18]
0x1400024cf  retn
```
