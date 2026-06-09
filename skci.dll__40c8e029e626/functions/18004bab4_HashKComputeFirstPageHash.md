# HashKComputeFirstPageHash

- ea: `0x18004bab4`
- end: `0x18004bd3d`
- name: `HashKComputeFirstPageHash`
- size: `649`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800461f8`
- `0x180046d9c`

## callees

- `0x180033950`
- `0x180033980`
- `0x18004bab4`
- `0x18004c00c`
- `0x18004c0c8`
- `0x18004c1ac`
- `0x18004c254`
- `0x18004c2e0`

## pseudocode

```c
__int64 __fastcall HashKComputeFirstPageHash(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        __int64 a10,
        _OWORD *a11,
        int *a12)
{
  _OWORD *v12; // r12
  __int64 result; // rax
  __int64 v18; // rsi
  unsigned int v19; // eax
  int v20; // edi
  int v21; // r13d
  int v22; // r15d
  unsigned int v23; // ebx
  unsigned int v24; // r14d
  __int64 v25; // r12
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // r14d
  int v29; // eax
  __int64 v30; // rax
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+44h] [rbp-BCh]
  unsigned int v36; // [rsp+48h] [rbp-B8h]
  int v37; // [rsp+4Ch] [rbp-B4h]
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+70h] [rbp-90h]
  _OWORD *v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h]
  _DWORD *v43; // [rsp+90h] [rbp-70h]
  int *v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+A0h] [rbp-60h] BYREF
  char v46[236]; // [rsp+A4h] [rbp-5Ch] BYREF
  _OWORD v47[4]; // [rsp+190h] [rbp+90h] BYREF

  v12 = a11;
  v42 = a5;
  v43 = a9;
  v44 = a12;
  v41 = a11;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  memset_0(v47, 0, sizeof(v47));
  memset_0(v46, 0, sizeof(v46));
  v45 = a1;
  v34 = 1;
  result = HashpParsePEHeader(a2, a3, a4, 0, (__int64)&v38, (__int64)v47, (__int64)&v34);
  if ( (int)result >= 0 )
  {
    v18 = DWORD2(v40);
    v19 = DWORD2(v40);
    v20 = DWORD1(v39);
    if ( (unsigned int)v39 < DWORD2(v40) )
      v19 = v39;
    v21 = -1;
    v22 = v38;
    v36 = v19;
    if ( DWORD1(v39) )
      v23 = *(_DWORD *)(*((_QWORD *)&v39 + 1) + 20LL);
    else
      v23 = v40;
    v24 = 0;
    HashpInitHash(&v45, 0);
    if ( (_DWORD)v18 )
    {
      v25 = *((_QWORD *)&v39 + 1);
      do
      {
        if ( v21 >= v20 )
          break;
        v26 = v18;
        if ( v23 < (unsigned int)v18 )
          v26 = v23;
        if ( v24 + v26 > (unsigned int)v18 )
          v26 = v18 - v24;
        HashpEmitExcludeRange((unsigned int)&v45, (unsigned int)v47, v34, v22, v26);
        v24 += v26;
        v22 += v26;
        v23 -= v26;
        if ( v23 )
        {
          v20 = DWORD1(v39);
        }
        else
        {
          v27 = v36;
          v35 = v21;
          v37 = v21++;
          HashpPadHash(&v45, v24, v36);
          v28 = v27 + v24 - 1;
          v29 = -v27;
          v20 = DWORD1(v39);
          v24 = v29 & v28;
          if ( v21 >= DWORD1(v39) - 1 )
          {
            if ( v21 < SDWORD1(v39) )
              v23 = *(_DWORD *)(v25 + 40LL * v35 + 56);
          }
          else
          {
            v30 = v37 + 2LL;
            if ( *(_DWORD *)(v25 + 40 * v30 + 16) )
              v23 = v38 + *(_DWORD *)(v25 + 40 * v30 + 20) - v22;
          }
        }
      }
      while ( v24 != (_DWORD)v18 );
      v12 = v41;
    }
    HashpPadHash(&v45, v24, v18);
    HashpFinalizeHash(&v45, v42);
    if ( v43 )
      *v43 = v22 - v38;
    if ( v12 )
    {
      v31 = v47[1];
      *v12 = v47[0];
      v32 = v47[2];
      v12[1] = v31;
      v33 = v47[3];
      v12[2] = v32;
      v12[3] = v33;
    }
    if ( v44 )
      *v44 = v34;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004bab4  push    rbp
0x18004bab6  push    rbx
0x18004bab7  push    rsi
0x18004bab8  push    rdi
0x18004bab9  push    r12
0x18004babb  push    r13
0x18004babd  push    r14
0x18004babf  push    r15
0x18004bac1  lea     rbp, [rsp-0E8h]
0x18004bac9  sub     rsp, 1E8h
0x18004bad0  mov     rax, cs:__security_cookie
0x18004bad7  xor     rax, rsp
0x18004bada  mov     [rbp+120h+var_50], rax
0x18004bae1  mov     rax, [rbp+120h+arg_20]
0x18004bae8  xorps   xmm0, xmm0
0x18004baeb  mov     r12, [rbp+120h+arg_50]
0x18004baf2  mov     rdi, rdx
0x18004baf5  mov     [rbp+120h+var_198], rax
0x18004baf9  xor     edx, edx; Val
0x18004bafb  mov     rax, [rbp+120h+arg_40]
0x18004bb02  mov     esi, r8d
0x18004bb05  mov     [rbp+120h+var_190], rax
0x18004bb09  mov     ebx, ecx
0x18004bb0b  mov     rax, [rbp+120h+arg_58]
0x18004bb12  lea     rcx, [rbp+120h+var_90]; void *
0x18004bb19  lea     r8d, [rdx+40h]; Size
0x18004bb1d  mov     [rbp+120h+var_188], rax
0x18004bb21  mov     r14d, r9d
0x18004bb24  mov     [rbp+120h+var_1A0], r12
0x18004bb28  movups  [rsp+220h+var_1D0], xmm0
0x18004bb2d  movups  [rsp+220h+var_1C0], xmm0
0x18004bb32  movups  [rsp+220h+var_1B0], xmm0
0x18004bb37  call    memset_0
0x18004bb3c  xor     edx, edx; Val
0x18004bb3e  lea     rcx, [rbp+120h+var_17C]; void *
0x18004bb42  mov     r8d, 0ECh; Size
0x18004bb48  call    memset_0
0x18004bb4d  lea     rax, [rsp+220h+var_1E0]
0x18004bb52  mov     [rbp+120h+var_180], ebx
0x18004bb55  mov     [rsp+220h+var_1F0], rax
0x18004bb5a  xor     r9d, r9d
0x18004bb5d  lea     rax, [rbp+120h+var_90]
0x18004bb64  mov     [rsp+220h+var_1E0], 1
0x18004bb6c  mov     [rsp+220h+var_1F8], rax
0x18004bb71  mov     r8d, r14d
0x18004bb74  lea     rax, [rsp+220h+var_1D0]
0x18004bb79  mov     edx, esi
0x18004bb7b  mov     rcx, rdi
0x18004bb7e  mov     [rsp+220h+var_200], rax
0x18004bb83  call    HashpParsePEHeader
0x18004bb88  test    eax, eax
0x18004bb8a  js      loc_18004BD19
0x18004bb90  mov     esi, dword ptr [rsp+220h+var_1B0+8]
0x18004bb94  cmp     dword ptr [rsp+220h+var_1C0], esi
0x18004bb98  mov     eax, esi
0x18004bb9a  mov     edi, dword ptr [rsp+220h+var_1C0+4]
0x18004bb9e  cmovb   eax, dword ptr [rsp+220h+var_1C0]
0x18004bba3  or      r13d, 0FFFFFFFFh
0x18004bba7  mov     r15, qword ptr [rsp+220h+var_1D0]
0x18004bbac  mov     [rsp+220h+var_1D8], eax
0x18004bbb0  test    edi, edi
0x18004bbb2  jnz     short loc_18004BBBA
0x18004bbb4  mov     ebx, dword ptr [rsp+220h+var_1B0]
0x18004bbb8  jmp     short loc_18004BBC2
0x18004bbba  mov     rbx, qword ptr [rsp+220h+var_1C0+8]
0x18004bbbf  mov     ebx, [rbx+14h]
0x18004bbc2  xor     edx, edx
0x18004bbc4  lea     rcx, [rbp+120h+var_180]
0x18004bbc8  xor     r14d, r14d
0x18004bbcb  call    HashpInitHash
0x18004bbd0  test    esi, esi
0x18004bbd2  jz      loc_18004BCA3
0x18004bbd8  mov     r12, qword ptr [rsp+220h+var_1C0+8]
0x18004bbdd  cmp     r13d, edi
0x18004bbe0  jge     loc_18004BC9F
0x18004bbe6  cmp     ebx, esi
0x18004bbe8  mov     edi, esi
0x18004bbea  cmovb   edi, ebx
0x18004bbed  lea     eax, [r14+rdi]
0x18004bbf1  cmp     eax, esi
0x18004bbf3  jbe     short loc_18004BBFA
0x18004bbf5  mov     edi, esi
0x18004bbf7  sub     edi, r14d
0x18004bbfa  mov     r8d, [rsp+220h+var_1E0]
0x18004bbff  lea     rdx, [rbp+120h+var_90]
0x18004bc06  mov     r9, r15
0x18004bc09  mov     dword ptr [rsp+220h+var_200], edi
0x18004bc0d  lea     rcx, [rbp+120h+var_180]
0x18004bc11  call    HashpEmitExcludeRange
0x18004bc16  mov     eax, edi
0x18004bc18  add     r14d, edi
0x18004bc1b  add     r15, rax
0x18004bc1e  sub     ebx, edi
0x18004bc20  jnz     short loc_18004BC92
0x18004bc22  mov     edi, [rsp+220h+var_1D8]
0x18004bc26  lea     rcx, [rbp+120h+var_180]
0x18004bc2a  mov     r8d, edi
0x18004bc2d  mov     [rsp+220h+var_1DC], r13d
0x18004bc32  mov     [rsp+220h+var_1D4], r13d
0x18004bc37  inc     r13d
0x18004bc3a  mov     edx, r14d
0x18004bc3d  call    HashpPadHash
0x18004bc42  dec     r14d
0x18004bc45  mov     eax, edi
0x18004bc47  add     r14d, edi
0x18004bc4a  neg     eax
0x18004bc4c  mov     edi, dword ptr [rsp+220h+var_1C0+4]
0x18004bc50  and     r14d, eax
0x18004bc53  lea     eax, [rdi-1]
0x18004bc56  cmp     r13d, eax
0x18004bc59  jge     short loc_18004BC7D
0x18004bc5b  movsxd  rax, [rsp+220h+var_1D4]
0x18004bc60  add     rax, 2
0x18004bc64  lea     rcx, [rax+rax*4]
0x18004bc68  cmp     [r12+rcx*8+10h], ebx
0x18004bc6d  jz      short loc_18004BC96
0x18004bc6f  mov     ebx, [r12+rcx*8+14h]
0x18004bc74  sub     ebx, r15d
0x18004bc77  add     ebx, dword ptr [rsp+220h+var_1D0]
0x18004bc7b  jmp     short loc_18004BC96
0x18004bc7d  cmp     r13d, edi
0x18004bc80  jge     short loc_18004BC96
0x18004bc82  movsxd  rax, [rsp+220h+var_1DC]
0x18004bc87  lea     rcx, [rax+rax*4]
0x18004bc8b  mov     ebx, [r12+rcx*8+38h]
0x18004bc90  jmp     short loc_18004BC96
0x18004bc92  mov     edi, dword ptr [rsp+220h+var_1C0+4]
0x18004bc96  cmp     r14d, esi
0x18004bc99  jnz     loc_18004BBDD
0x18004bc9f  mov     r12, [rbp+120h+var_1A0]
0x18004bca3  mov     r8, rsi
0x18004bca6  mov     edx, r14d
0x18004bca9  lea     rcx, [rbp+120h+var_180]
0x18004bcad  call    HashpPadHash
0x18004bcb2  mov     rdx, [rbp+120h+var_198]
0x18004bcb6  lea     rcx, [rbp+120h+var_180]
0x18004bcba  call    HashpFinalizeHash
0x18004bcbf  mov     rax, [rbp+120h+var_190]
0x18004bcc3  test    rax, rax
0x18004bcc6  jz      short loc_18004BCD0
0x18004bcc8  sub     r15d, dword ptr [rsp+220h+var_1D0]
0x18004bccd  mov     [rax], r15d
0x18004bcd0  test    r12, r12
0x18004bcd3  jz      short loc_18004BD08
0x18004bcd5  movaps  xmm0, [rbp+120h+var_90]
0x18004bcdc  movaps  xmm1, [rbp+120h+var_80]
0x18004bce3  movups  xmmword ptr [r12], xmm0
0x18004bce8  movaps  xmm0, [rbp+120h+var_70]
0x18004bcef  movups  xmmword ptr [r12+10h], xmm1
0x18004bcf5  movaps  xmm1, [rbp+120h+var_60]
0x18004bcfc  movups  xmmword ptr [r12+20h], xmm0
0x18004bd02  movups  xmmword ptr [r12+30h], xmm1
0x18004bd08  mov     rcx, [rbp+120h+var_188]
0x18004bd0c  test    rcx, rcx
0x18004bd0f  jz      short loc_18004BD17
0x18004bd11  mov     eax, [rsp+220h+var_1E0]
0x18004bd15  mov     [rcx], eax
0x18004bd17  xor     eax, eax
0x18004bd19  mov     rcx, [rbp+120h+var_50]
0x18004bd20  xor     rcx, rsp; StackCookie
0x18004bd23  call    __security_check_cookie
0x18004bd28  add     rsp, 1E8h
0x18004bd2f  pop     r15
0x18004bd31  pop     r14
0x18004bd33  pop     r13
0x18004bd35  pop     r12
0x18004bd37  pop     rdi
0x18004bd38  pop     rsi
0x18004bd39  pop     rbx
0x18004bd3a  pop     rbp
0x18004bd3b  retn
```
