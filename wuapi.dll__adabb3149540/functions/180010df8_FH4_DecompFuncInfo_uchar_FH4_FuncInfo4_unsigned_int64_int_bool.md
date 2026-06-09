# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180010df8`
- end: `0x180010f24`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119b4`

## callees

- `0x180010df8`

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
0x180010df8  mov     rax, rsp
0x180010dfb  mov     [rax+8], rbx
0x180010dff  mov     [rax+10h], rbp
0x180010e03  mov     [rax+18h], rsi
0x180010e07  mov     [rax+20h], rdi
0x180010e0b  mov     bl, [rcx]
0x180010e0d  lea     r10, [rcx+1]
0x180010e11  mov     [rdx], bl
0x180010e13  mov     esi, r9d
0x180010e16  lea     rbp, cs:180000000h
0x180010e1d  mov     r9, r8
0x180010e20  mov     r11, rdx
0x180010e23  mov     rdi, rcx
0x180010e26  test    bl, 4
0x180010e29  jz      short loc_180010E4E
0x180010e2b  movzx   ecx, byte ptr [r10]
0x180010e2f  and     ecx, 0Fh
0x180010e32  movsx   rax, byte ptr [rcx+rbp+18818h]
0x180010e3b  mov     cl, [rcx+rbp+18828h]
0x180010e42  sub     r10, rax
0x180010e45  mov     eax, [r10-4]
0x180010e49  shr     eax, cl
0x180010e4b  mov     [rdx+4], eax
0x180010e4e  test    bl, 8
0x180010e51  jz      short loc_180010E5D
0x180010e53  mov     eax, [r10]
0x180010e56  add     r10, 4
0x180010e5a  mov     [rdx+8], eax
0x180010e5d  test    bl, 10h
0x180010e60  jz      short loc_180010E6C
0x180010e62  mov     eax, [r10]
0x180010e65  add     r10, 4
0x180010e69  mov     [rdx+0Ch], eax
0x180010e6c  xor     edx, edx
0x180010e6e  lea     r8, [r10+4]
0x180010e72  cmp     [rsp+arg_20], dl
0x180010e76  jnz     short loc_180010ED9
0x180010e78  test    bl, 2
0x180010e7b  jz      short loc_180010ED9
0x180010e7d  mov     [r11+10h], edx
0x180010e81  cmp     [r10], edx
0x180010e84  jz      short loc_180010ED0
0x180010e86  movsxd  rax, dword ptr [r10]
0x180010e89  add     r9, rax
0x180010e8c  movzx   ecx, byte ptr [r9]
0x180010e90  and     ecx, 0Fh
0x180010e93  movsx   rax, byte ptr [rcx+rbp+18818h]
0x180010e9c  mov     cl, [rcx+rbp+18828h]
0x180010ea3  sub     r9, rax
0x180010ea6  mov     r10d, [r9-4]
0x180010eaa  shr     r10d, cl
0x180010ead  test    r10d, r10d
0x180010eb0  jz      short loc_180010EE0
0x180010eb2  mov     eax, [r9]
0x180010eb5  mov     ecx, [r9+4]
0x180010eb9  lea     r9, [r9+8]
0x180010ebd  cmp     eax, esi
0x180010ebf  jz      short loc_180010ECA
0x180010ec1  inc     edx
0x180010ec3  cmp     edx, r10d
0x180010ec6  jb      short loc_180010EB2
0x180010ec8  jmp     short loc_180010EE0
0x180010eca  mov     [r11+10h], ecx
0x180010ece  jmp     short loc_180010EE0
0x180010ed0  mov     ecx, 7
0x180010ed5  int     29h; Win8: RtlFailFast(ecx)
0x180010ed7  jmp     short loc_180010EE0
0x180010ed9  mov     eax, [r10]
0x180010edc  mov     [r11+10h], eax
0x180010ee0  test    bl, 1
0x180010ee3  jz      short loc_180010F09
0x180010ee5  movzx   ecx, byte ptr [r8]
0x180010ee9  and     ecx, 0Fh
0x180010eec  movsx   rdx, byte ptr [rcx+rbp+18818h]
0x180010ef5  mov     cl, [rcx+rbp+18828h]
0x180010efc  sub     r8, rdx
0x180010eff  mov     edx, [r8-4]
0x180010f03  shr     edx, cl
0x180010f05  mov     [r11+14h], edx
0x180010f09  mov     rbx, [rsp+arg_0]
0x180010f0e  sub     r8, rdi
0x180010f11  mov     rbp, [rsp+arg_8]
0x180010f16  mov     rax, r8
0x180010f19  mov     rsi, [rsp+arg_10]
0x180010f1e  mov     rdi, [rsp+arg_18]
0x180010f23  retn
```
