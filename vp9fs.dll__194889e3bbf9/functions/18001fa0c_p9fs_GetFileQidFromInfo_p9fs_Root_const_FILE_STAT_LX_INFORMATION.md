# p9fs::GetFileQidFromInfo(p9fs::Root const &,_FILE_STAT_LX_INFORMATION &)

- ea: `0x18001fa0c`
- end: `0x18001fb1f`
- name: `?GetFileQidFromInfo@p9fs@@YA?AV?$BasicExpected@UFileAttributes@p9fs@@J@util@@AEBURoot@1@AEAU_FILE_STAT_LX_INFORMATION@@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021fdc`

## callees

- `0x180004120`
- `0x18001fa0c`

## import_xrefs

- `lxutil!LxUtilFsConvertMode` at `0x18001fa96`
- `lxutil!LxUtilFsConvertMode` at `0x18001fa96`
- `lxutil!LxUtilFsIsAppExecLink` at `0x18001fa4c`
- `lxutil!LxUtilFsIsAppExecLink` at `0x18001fa4c`

## pseudocode

```c
__int64 __fastcall p9fs::GetFileQidFromInfo(__int64 a1, unsigned int *a2, __int64 a3)
{
  bool v3; // zf
  bool v6; // r8
  int v7; // eax
  char v8; // cl
  int v9; // eax
  __int128 v11; // [rsp+40h] [rbp-40h]
  __int64 v12; // [rsp+50h] [rbp-30h]
  int v13; // [rsp+68h] [rbp-18h] BYREF

  v3 = (*(_BYTE *)(a3 + 72) & 4) == 0;
  v13 = 0;
  if ( v3 )
  {
    v9 = LxUtilFsConvertMode(a2 + 8, a3, 1, a2[24], a2[25], a2[26], &v13);
    if ( v9 < 0 )
    {
      *(_BYTE *)a1 = 0;
      *(_DWORD *)(a1 + 8) = v9;
      return a1;
    }
  }
  else
  {
    v13 = *(_DWORD *)(a3 + 84);
  }
  v6 = (unsigned __int8)LxUtilFsIsAppExecLink(*(unsigned int *)(a3 + 56), *(unsigned int *)(a3 + 60)) != 0;
  v7 = v13 & 0xF000;
  if ( v7 == 40960 )
    v8 = 2;
  else
    v8 = v7 != 0x4000 ? 0 : 0x80;
  *(_QWORD *)&v11 = *(_QWORD *)a3;
  DWORD2(v11) = 0;
  *(_WORD *)((char *)&v11 + 13) = 0;
  BYTE12(v11) = v8;
  LODWORD(v12) = v13;
  HIBYTE(v11) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 15));
  *(_WORD *)((char *)&v12 + 5) = 0;
  HIBYTE(v12) = 0;
  BYTE4(v12) = v6;
  *(_OWORD *)(a1 + 8) = v11;
  *(_BYTE *)a1 = 1;
  *(_QWORD *)(a1 + 24) = v12;
  return a1;
}

```

## disassembly

```asm
0x18001fa0c  push    rbp
0x18001fa0e  push    rbx
0x18001fa0f  push    rdi
0x18001fa10  mov     rbp, rsp
0x18001fa13  sub     rsp, 80h
0x18001fa1a  mov     rax, cs:__security_cookie
0x18001fa21  xor     rax, rsp
0x18001fa24  mov     [rbp+var_10], rax
0x18001fa28  test    byte ptr [r8+48h], 4
0x18001fa2d  mov     rdi, r8
0x18001fa30  mov     r9, rdx
0x18001fa33  mov     [rbp+var_18], 0
0x18001fa3a  mov     rbx, rcx
0x18001fa3d  jz      short loc_18001FA6D
0x18001fa3f  mov     eax, [r8+54h]
0x18001fa43  mov     [rbp+var_18], eax
0x18001fa46  mov     edx, [rdi+3Ch]
0x18001fa49  mov     ecx, [rdi+38h]
0x18001fa4c  call    cs:__imp_LxUtilFsIsAppExecLink
0x18001fa52  mov     edx, [rbp+var_18]
0x18001fa55  test    al, al
0x18001fa57  mov     eax, edx
0x18001fa59  setnz   r8b
0x18001fa5d  and     eax, 0F000h
0x18001fa62  cmp     eax, 0A000h
0x18001fa67  jnz     short loc_18001FAA8
0x18001fa69  mov     cl, 2
0x18001fa6b  jmp     short loc_18001FAB5
0x18001fa6d  lea     rcx, [rdx+20h]
0x18001fa71  mov     r8d, 1
0x18001fa77  mov     edx, [rdx+68h]
0x18001fa7a  lea     rax, [rbp+var_18]
0x18001fa7e  mov     [rsp+80h+var_50], rax
0x18001fa83  mov     [rsp+80h+var_58], edx
0x18001fa87  mov     edx, [r9+64h]
0x18001fa8b  mov     r9d, [r9+60h]
0x18001fa8f  mov     [rsp+80h+var_60], edx
0x18001fa93  mov     rdx, rdi
0x18001fa96  call    cs:__imp_LxUtilFsConvertMode
0x18001fa9c  test    eax, eax
0x18001fa9e  jns     short loc_18001FA46
0x18001faa0  mov     byte ptr [rbx], 0
0x18001faa3  mov     [rbx+8], eax
0x18001faa6  jmp     short loc_18001FB05
0x18001faa8  cmp     eax, 4000h
0x18001faad  setnz   cl
0x18001fab0  dec     cl
0x18001fab2  and     cl, 80h
0x18001fab5  mov     rax, [rdi]
0x18001fab8  xorps   xmm0, xmm0
0x18001fabb  mov     qword ptr [rbp+var_40], rax
0x18001fabf  movups  [rbp+var_28], xmm0
0x18001fac3  mov     eax, dword ptr [rbp+var_28+8]
0x18001fac6  mov     dword ptr [rbp+var_40+8], eax
0x18001fac9  movzx   eax, word ptr [rbp+var_28+0Dh]
0x18001facd  mov     word ptr [rbp+var_40+0Dh], ax
0x18001fad1  psrldq  xmm0, 0Fh
0x18001fad6  movd    eax, xmm0
0x18001fada  mov     byte ptr [rbp+var_40+0Ch], cl
0x18001fadd  mov     dword ptr [rbp+var_30], edx
0x18001fae0  mov     byte ptr [rbp+var_40+0Fh], al
0x18001fae3  xor     eax, eax
0x18001fae5  movups  xmm0, [rbp+var_40]
0x18001fae9  mov     word ptr [rbp+var_30+5], ax
0x18001faed  mov     byte ptr [rbp+var_30+7], al
0x18001faf0  mov     byte ptr [rbp+var_30+4], r8b
0x18001faf4  movsd   xmm1, [rbp+var_30]
0x18001faf9  movups  xmmword ptr [rbx+8], xmm0
0x18001fafd  mov     byte ptr [rbx], 1
0x18001fb00  movsd   qword ptr [rbx+18h], xmm1
0x18001fb05  mov     rax, rbx
0x18001fb08  mov     rcx, [rbp+var_10]
0x18001fb0c  xor     rcx, rsp; StackCookie
0x18001fb0f  call    __security_check_cookie
0x18001fb14  add     rsp, 80h
0x18001fb1b  pop     rdi
0x18001fb1c  pop     rbx
0x18001fb1d  pop     rbp
0x18001fb1e  retn
```
