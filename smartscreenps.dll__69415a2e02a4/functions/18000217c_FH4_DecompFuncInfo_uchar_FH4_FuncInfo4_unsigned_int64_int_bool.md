# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x18000217c`
- end: `0x180002288`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `268`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ca0`

## callees

- `0x18000217c`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
  _BYTE *v6; // r10
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  _BYTE *v12; // rdx
  _BYTE *v13; // r8
  __int64 v14; // rcx
  _DWORD *v15; // r8
  unsigned int v16; // r10d
  int v17; // ecx
  __int64 v18; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v9 = *v6 & 0xF;
    v6 -= *((char *)&FH4::s_negLengthTab + v9);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v9);
  }
  if ( (v5 & 8) != 0 )
  {
    v10 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 2) = v10;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v11 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 3) = v11;
  }
  v12 = v6 + 4;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = *(_DWORD *)v6;
  }
  else
  {
    *((_DWORD *)a2 + 4) = 0;
    if ( !*(_DWORD *)v6 )
      __fastfail(7u);
    v13 = (char *)a3 + *(int *)v6;
    v14 = *v13 & 0xF;
    v15 = &v13[-*((char *)&FH4::s_negLengthTab + v14)];
    v16 = *(v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    v17 = 0;
    if ( v16 )
    {
      while ( *v15 != a4 )
      {
        v15 += 2;
        if ( ++v17 >= v16 )
          goto LABEL_17;
      }
      *((_DWORD *)a2 + 4) = v15[1];
    }
  }
LABEL_17:
  if ( (v5 & 1) != 0 )
  {
    v18 = *v12 & 0xF;
    v12 -= *((char *)&FH4::s_negLengthTab + v18);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v18);
  }
  return v12 - (_BYTE *)this;
}

```

## disassembly

```asm
0x18000217c  push    rbx
0x18000217e  push    rbp
0x18000217f  push    rsi
0x180002180  push    rdi
0x180002181  mov     bl, [rcx]
0x180002183  lea     r10, [rcx+1]
0x180002187  mov     [rdx], bl
0x180002189  mov     esi, r9d
0x18000218c  lea     rbp, cs:180000000h
0x180002193  mov     r11, rdx
0x180002196  mov     rdi, rcx
0x180002199  test    bl, 4
0x18000219c  jz      short loc_1800021C1
0x18000219e  movzx   ecx, byte ptr [r10]
0x1800021a2  and     ecx, 0Fh
0x1800021a5  movsx   rax, byte ptr [rcx+rbp+14640h]
0x1800021ae  mov     cl, [rcx+rbp+14650h]
0x1800021b5  sub     r10, rax
0x1800021b8  mov     eax, [r10-4]
0x1800021bc  shr     eax, cl
0x1800021be  mov     [rdx+4], eax
0x1800021c1  test    bl, 8
0x1800021c4  jz      short loc_1800021D0
0x1800021c6  mov     eax, [r10]
0x1800021c9  add     r10, 4
0x1800021cd  mov     [rdx+8], eax
0x1800021d0  test    bl, 10h
0x1800021d3  jz      short loc_1800021DF
0x1800021d5  mov     eax, [r10]
0x1800021d8  add     r10, 4
0x1800021dc  mov     [rdx+0Ch], eax
0x1800021df  xor     r9d, r9d
0x1800021e2  lea     rdx, [r10+4]
0x1800021e6  cmp     [rsp+20h+arg_20], r9b
0x1800021eb  jnz     short loc_18000224F
0x1800021ed  test    bl, 2
0x1800021f0  jz      short loc_18000224F
0x1800021f2  mov     [r11+10h], r9d
0x1800021f6  cmp     [r10], r9d
0x1800021f9  jz      short loc_180002246
0x1800021fb  movsxd  rax, dword ptr [r10]
0x1800021fe  add     r8, rax
0x180002201  movzx   ecx, byte ptr [r8]
0x180002205  and     ecx, 0Fh
0x180002208  movsx   rax, byte ptr [rcx+rbp+14640h]
0x180002211  mov     cl, [rcx+rbp+14650h]
0x180002218  sub     r8, rax
0x18000221b  mov     r10d, [r8-4]
0x18000221f  shr     r10d, cl
0x180002222  mov     ecx, r9d
0x180002225  test    r10d, r10d
0x180002228  jz      short loc_180002256
0x18000222a  mov     r9d, [r8+4]
0x18000222e  cmp     [r8], esi
0x180002231  jz      short loc_180002240
0x180002233  add     r8, 8
0x180002237  inc     ecx
0x180002239  cmp     ecx, r10d
0x18000223c  jb      short loc_18000222A
0x18000223e  jmp     short loc_180002256
0x180002240  mov     [r11+10h], r9d
0x180002244  jmp     short loc_180002256
0x180002246  mov     ecx, 7
0x18000224b  int     29h; Win8: RtlFailFast(ecx)
0x18000224d  jmp     short loc_180002256
0x18000224f  mov     eax, [r10]
0x180002252  mov     [r11+10h], eax
0x180002256  test    bl, 1
0x180002259  jz      short loc_18000227D
0x18000225b  movzx   ecx, byte ptr [rdx]
0x18000225e  and     ecx, 0Fh
0x180002261  movsx   rax, byte ptr [rcx+rbp+14640h]
0x18000226a  mov     cl, [rcx+rbp+14650h]
0x180002271  sub     rdx, rax
0x180002274  mov     eax, [rdx-4]
0x180002277  shr     eax, cl
0x180002279  mov     [r11+14h], eax
0x18000227d  sub     rdx, rdi
0x180002280  mov     rax, rdx
0x180002283  pop     rdi
0x180002284  pop     rsi
0x180002285  pop     rbp
0x180002286  pop     rbx
0x180002287  retn
```
