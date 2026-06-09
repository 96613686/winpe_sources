# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x14001ba78`
- end: `0x14001bba4`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c634`

## callees

- `0x14001ba78`

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
0x14001ba78  mov     rax, rsp
0x14001ba7b  mov     [rax+8], rbx
0x14001ba7f  mov     [rax+10h], rbp
0x14001ba83  mov     [rax+18h], rsi
0x14001ba87  mov     [rax+20h], rdi
0x14001ba8b  mov     bl, [rcx]
0x14001ba8d  lea     r10, [rcx+1]
0x14001ba91  mov     [rdx], bl
0x14001ba93  mov     esi, r9d
0x14001ba96  lea     rbp, __ImageBase
0x14001ba9d  mov     r9, r8
0x14001baa0  mov     r11, rdx
0x14001baa3  mov     rdi, rcx
0x14001baa6  test    bl, 4
0x14001baa9  jz      short loc_14001BACE
0x14001baab  movzx   ecx, byte ptr [r10]
0x14001baaf  and     ecx, 0Fh
0x14001bab2  movsx   rax, byte ptr [rcx+rbp+23B90h]
0x14001babb  mov     cl, [rcx+rbp+23BA0h]
0x14001bac2  sub     r10, rax
0x14001bac5  mov     eax, [r10-4]
0x14001bac9  shr     eax, cl
0x14001bacb  mov     [rdx+4], eax
0x14001bace  test    bl, 8
0x14001bad1  jz      short loc_14001BADD
0x14001bad3  mov     eax, [r10]
0x14001bad6  add     r10, 4
0x14001bada  mov     [rdx+8], eax
0x14001badd  test    bl, 10h
0x14001bae0  jz      short loc_14001BAEC
0x14001bae2  mov     eax, [r10]
0x14001bae5  add     r10, 4
0x14001bae9  mov     [rdx+0Ch], eax
0x14001baec  xor     edx, edx
0x14001baee  lea     r8, [r10+4]
0x14001baf2  cmp     [rsp+arg_20], dl
0x14001baf6  jnz     short loc_14001BB59
0x14001baf8  test    bl, 2
0x14001bafb  jz      short loc_14001BB59
0x14001bafd  mov     [r11+10h], edx
0x14001bb01  cmp     [r10], edx
0x14001bb04  jz      short loc_14001BB50
0x14001bb06  movsxd  rax, dword ptr [r10]
0x14001bb09  add     r9, rax
0x14001bb0c  movzx   ecx, byte ptr [r9]
0x14001bb10  and     ecx, 0Fh
0x14001bb13  movsx   rax, byte ptr [rcx+rbp+23B90h]
0x14001bb1c  mov     cl, [rcx+rbp+23BA0h]
0x14001bb23  sub     r9, rax
0x14001bb26  mov     r10d, [r9-4]
0x14001bb2a  shr     r10d, cl
0x14001bb2d  test    r10d, r10d
0x14001bb30  jz      short loc_14001BB60
0x14001bb32  mov     eax, [r9]
0x14001bb35  mov     ecx, [r9+4]
0x14001bb39  lea     r9, [r9+8]
0x14001bb3d  cmp     eax, esi
0x14001bb3f  jz      short loc_14001BB4A
0x14001bb41  inc     edx
0x14001bb43  cmp     edx, r10d
0x14001bb46  jb      short loc_14001BB32
0x14001bb48  jmp     short loc_14001BB60
0x14001bb4a  mov     [r11+10h], ecx
0x14001bb4e  jmp     short loc_14001BB60
0x14001bb50  mov     ecx, 7
0x14001bb55  int     29h; Win8: RtlFailFast(ecx)
0x14001bb57  jmp     short loc_14001BB60
0x14001bb59  mov     eax, [r10]
0x14001bb5c  mov     [r11+10h], eax
0x14001bb60  test    bl, 1
0x14001bb63  jz      short loc_14001BB89
0x14001bb65  movzx   ecx, byte ptr [r8]
0x14001bb69  and     ecx, 0Fh
0x14001bb6c  movsx   rdx, byte ptr [rcx+rbp+23B90h]
0x14001bb75  mov     cl, [rcx+rbp+23BA0h]
0x14001bb7c  sub     r8, rdx
0x14001bb7f  mov     edx, [r8-4]
0x14001bb83  shr     edx, cl
0x14001bb85  mov     [r11+14h], edx
0x14001bb89  mov     rbx, [rsp+arg_0]
0x14001bb8e  sub     r8, rdi
0x14001bb91  mov     rbp, [rsp+arg_8]
0x14001bb96  mov     rax, r8
0x14001bb99  mov     rsi, [rsp+arg_10]
0x14001bb9e  mov     rdi, [rsp+arg_18]
0x14001bba3  retn
```
