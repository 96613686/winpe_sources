# SkpgCreateSecureModuleExtents

- ea: `0x1400a386c`
- end: `0x1400a3b72`
- name: `SkpgCreateSecureModuleExtents`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400a3798`

## callees

- `0x14001158c`
- `0x140034614`
- `0x1400a386c`
- `0x1400a3ef0`
- `0x1400a4cac`
- `0x1400a4d58`
- `0x1400a5694`

## pseudocode

```c
__int64 __fastcall SkpgCreateSecureModuleExtents(__int64 a1, __int64 *a2, unsigned __int64 *a3, int *a4, __int64 a5)
{
  __int64 v5; // rcx
  int v6; // ebx
  unsigned __int64 v7; // r15
  unsigned int v8; // esi
  ULONG_PTR v9; // r12
  int v10; // r14d
  _DWORD *v12; // rax
  ULONG_PTR v13; // rdi
  BOOL v14; // edx
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // r13d
  __int64 v19; // rbp
  unsigned __int64 v20; // rbp
  unsigned __int64 v21; // rax
  int v22; // edi
  __int64 v23; // rsi
  __int64 v24; // r12
  __int64 v25; // rbp
  __int64 v26; // rdi
  unsigned int v27; // r14d
  __int64 v28; // rdi
  __int16 v29; // ax
  __int64 v30; // [rsp+40h] [rbp-98h]
  unsigned int v31; // [rsp+48h] [rbp-90h]
  __int64 v32; // [rsp+50h] [rbp-88h]
  _BYTE v33[28]; // [rsp+58h] [rbp-80h] BYREF
  int v34; // [rsp+74h] [rbp-64h]
  __int64 v35; // [rsp+78h] [rbp-60h]
  unsigned __int64 v36; // [rsp+80h] [rbp-58h]
  ULONG_PTR v37; // [rsp+88h] [rbp-50h]
  int v42; // [rsp+100h] [rbp+28h]

  v5 = *((_QWORD *)&xmmword_14018A010 + 1);
  v6 = *a4;
  v7 = *a3;
  memset(v33, 0, 24);
  v32 = *((_QWORD *)&xmmword_14018A010 + 1);
  v30 = *a2;
  v8 = (SkmiPatchFlags & 1) != 0 ? SkmiHotPatchAddressReservePages : 0;
  v31 = v8;
  v9 = *(_QWORD *)(a5 + 48);
  v37 = v9;
  if ( v9 < *((_QWORD *)&xmmword_14018A010 + 1)
    || (v10 = qword_14018A020,
        v42 = qword_14018A020,
        v9 >= *((_QWORD *)&xmmword_14018A010 + 1) + (unsigned __int64)(unsigned int)qword_14018A020) )
  {
    RtlpxLookupFunctionTable(v9, v33);
    v5 = *(_QWORD *)&v33[8];
    v10 = *(_DWORD *)&v33[16];
    v32 = *(_QWORD *)&v33[8];
    v42 = *(_DWORD *)&v33[16];
  }
  if ( !v5 )
    return 3221225781LL;
  v34 = 0;
  *(_OWORD *)&v33[12] = 0;
  *(_QWORD *)v33 = v9;
  *(_DWORD *)&v33[8] = v10;
  while ( 1 )
  {
    v12 = (_DWORD *)SkpgEnumerateSections(v33, 2147483653LL);
    v13 = (ULONG_PTR)v12;
    if ( !v12 )
      break;
    v14 = *v12 == 1279410516 && v12[1] == 5198405;
    v15 = (unsigned int)v12[3];
    v16 = v12[2];
    v17 = v9 + v15;
    v18 = *(_DWORD *)(v13 + 16);
    v35 = v17;
    if ( v18 <= v16 )
      v18 = v16;
    if ( v8 )
    {
      v19 = v18 + 4095LL;
      v18 = 4096;
      v20 = ((unsigned __int64)(v17 & 0xFFF) + v19) >> 12;
    }
    else
    {
      LODWORD(v20) = 1;
    }
    v21 = v7 + 48LL * (unsigned int)v20;
    if ( v21 <= v7 )
      return 3221225621LL;
    v7 += 48LL * (unsigned int)v20;
    v36 = v21;
    if ( a1 )
    {
      if ( v14 )
        SkmmProtectKernelImageSubsection(v9, v13);
      v22 = (*(_DWORD *)(v13 + 36) >> 29) & 1;
      if ( (_DWORD)v20 )
      {
        v23 = v30;
        v24 = v35;
        do
        {
          SkpgInitializeSecureMemoryExtent(a1, v23, 4118, v6, v22, v24, v18);
          v23 += 48;
          ++v6;
          v24 += v18;
          LODWORD(v20) = v20 - 1;
        }
        while ( (_DWORD)v20 );
        v10 = v42;
        v7 = v36;
        v9 = v37;
        v30 = v23;
        v8 = v31;
      }
    }
    else
    {
      v6 += v20;
    }
  }
  if ( v8 )
  {
    if ( v7 + 48LL * v8 < v7 )
      return 3221225621LL;
    v7 += 48LL * v8;
    v25 = v30;
    if ( a1 )
    {
      v26 = v10 - (v8 << 12);
      v27 = 0;
      v28 = v32 + v26;
      do
      {
        SkpgInitializeExtent(a1, v25, 4116, v28, 4096);
        v29 = *(_WORD *)(v25 + 2);
        *(_DWORD *)(v25 + 28) |= 2u;
        *(_DWORD *)(v25 + 24) = 4118;
        *(_WORD *)(v25 + 2) = v29 & 0xFFEB | 0x10;
        *(_BYTE *)(v25 + 3) = SkpgExtentCrc(a1, v25);
        ++v6;
        v25 += 48;
        v28 += 4096;
        ++v27;
      }
      while ( v27 < v8 );
    }
    else
    {
      v6 += v8;
    }
  }
  else
  {
    v25 = v30;
  }
  *a2 = v25;
  *a4 = v6;
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x1400a386c  mov     r11, rsp
0x1400a386f  mov     [r11+20h], r9
0x1400a3873  mov     [r11+18h], r8
0x1400a3877  mov     [r11+10h], rdx
0x1400a387b  mov     [r11+8], rcx
0x1400a387f  push    rbx
0x1400a3880  push    rbp
0x1400a3881  push    rsi
0x1400a3882  push    rdi
0x1400a3883  push    r12
0x1400a3885  push    r13
0x1400a3887  push    r14
0x1400a3889  push    r15
0x1400a388b  sub     rsp, 98h
0x1400a3892  mov     rcx, qword ptr cs:xmmword_14018A010+8
0x1400a3899  xor     eax, eax
0x1400a389b  mov     ebx, [r9]
0x1400a389e  xorps   xmm0, xmm0
0x1400a38a1  mov     r15, [r8]
0x1400a38a4  movups  [rsp+0D8h+var_80], xmm0
0x1400a38a9  mov     [r11-70h], rax
0x1400a38ad  mov     al, byte ptr cs:SkmiPatchFlags
0x1400a38b3  and     al, 1
0x1400a38b5  mov     [rsp+0D8h+var_88], rcx
0x1400a38ba  neg     al
0x1400a38bc  mov     rax, [rdx]
0x1400a38bf  sbb     esi, esi
0x1400a38c1  mov     [rsp+0D8h+var_98], rax
0x1400a38c6  and     esi, cs:SkmiHotPatchAddressReservePages
0x1400a38cc  mov     rax, [rsp+0D8h+arg_20]
0x1400a38d4  mov     [rsp+0D8h+var_90], esi
0x1400a38d8  mov     r12, [rax+30h]
0x1400a38dc  mov     [rsp+0D8h+var_50], r12
0x1400a38e4  cmp     r12, rcx
0x1400a38e7  jb      short loc_1400A38FD
0x1400a38e9  mov     r14d, dword ptr cs:qword_14018A020
0x1400a38f0  mov     [r11+28h], r14d
0x1400a38f4  lea     rax, [rcx+r14]
0x1400a38f8  cmp     r12, rax
0x1400a38fb  jb      short loc_1400A3921
0x1400a38fd  lea     rdx, [rsp+0D8h+var_80]
0x1400a3902  mov     rcx, r12
0x1400a3905  call    RtlpxLookupFunctionTable
0x1400a390a  mov     rcx, qword ptr [rsp+0D8h+var_80+8]
0x1400a390f  mov     r14d, [rsp+0D8h+var_70]
0x1400a3914  mov     [rsp+0D8h+var_88], rcx
0x1400a3919  mov     dword ptr [rsp+0D8h+arg_20], r14d
0x1400a3921  test    rcx, rcx
0x1400a3924  jnz     short loc_1400A3930
0x1400a3926  mov     eax, 0C0000135h
0x1400a392b  jmp     loc_1400A3B5D
0x1400a3930  xorps   xmm0, xmm0
0x1400a3933  mov     [rsp+0D8h+var_64], 0
0x1400a393b  movdqu  [rsp+0D8h+var_80+0Ch], xmm0
0x1400a3941  mov     qword ptr [rsp+0D8h+var_80], r12
0x1400a3946  mov     dword ptr [rsp+0D8h+var_80+8], r14d
0x1400a394b  mov     edx, 80000005h
0x1400a3950  lea     rcx, [rsp+0D8h+var_80]
0x1400a3955  call    SkpgEnumerateSections
0x1400a395a  mov     rdi, rax
0x1400a395d  test    rax, rax
0x1400a3960  jz      loc_1400A3A83
0x1400a3966  cmp     dword ptr [rax], 4C424154h
0x1400a396c  jnz     short loc_1400A397E
0x1400a396e  cmp     dword ptr [rax+4], 4F5245h
0x1400a3975  jnz     short loc_1400A397E
0x1400a3977  mov     edx, 1
0x1400a397c  jmp     short loc_1400A3980
0x1400a397e  xor     edx, edx
0x1400a3980  mov     ecx, [rax+0Ch]
0x1400a3983  mov     eax, [rax+8]
0x1400a3986  add     rcx, r12
0x1400a3989  mov     r13d, [rdi+10h]
0x1400a398d  cmp     r13d, eax
0x1400a3990  mov     [rsp+0D8h+var_60], rcx
0x1400a3995  cmovbe  r13d, eax
0x1400a3999  test    esi, esi
0x1400a399b  jz      short loc_1400A39BC
0x1400a399d  mov     ebp, r13d
0x1400a39a0  and     ecx, 0FFFh
0x1400a39a6  add     rbp, 0FFFh
0x1400a39ad  mov     r13d, 1000h
0x1400a39b3  add     rbp, rcx
0x1400a39b6  shr     rbp, 0Ch
0x1400a39ba  jmp     short loc_1400A39C1
0x1400a39bc  mov     ebp, 1
0x1400a39c1  mov     eax, ebp
0x1400a39c3  lea     rax, [rax+rax*2]
0x1400a39c7  shl     rax, 4
0x1400a39cb  add     rax, r15
0x1400a39ce  cmp     rax, r15
0x1400a39d1  jbe     loc_1400A3A9D
0x1400a39d7  cmp     [rsp+0D8h+arg_0], 0
0x1400a39e0  mov     r15, rax
0x1400a39e3  mov     [rsp+0D8h+var_58], rax
0x1400a39eb  jz      loc_1400A3A7C
0x1400a39f1  test    edx, edx
0x1400a39f3  jz      short loc_1400A3A00
0x1400a39f5  mov     rdx, rdi; BugCheckParameter4
0x1400a39f8  mov     rcx, r12; BugCheckParameter3
0x1400a39fb  call    SkmmProtectKernelImageSubsection
0x1400a3a00  mov     edi, [rdi+24h]
0x1400a3a03  shr     edi, 1Dh
0x1400a3a06  and     edi, 1
0x1400a3a09  test    ebp, ebp
0x1400a3a0b  jz      loc_1400A394B
0x1400a3a11  mov     rsi, [rsp+0D8h+var_98]
0x1400a3a16  mov     r12, [rsp+0D8h+var_60]
0x1400a3a1b  mov     r15, [rsp+0D8h+arg_0]
0x1400a3a23  mov     r14d, r13d
0x1400a3a26  mov     [rsp+0D8h+var_A8], r13d
0x1400a3a2b  mov     r9d, ebx
0x1400a3a2e  mov     [rsp+0D8h+var_B0], r12
0x1400a3a33  mov     r8d, 1016h
0x1400a3a39  mov     rdx, rsi
0x1400a3a3c  mov     [rsp+0D8h+var_B8], edi
0x1400a3a40  mov     rcx, r15
0x1400a3a43  call    SkpgInitializeSecureMemoryExtent
0x1400a3a48  add     rsi, 30h ; '0'
0x1400a3a4c  inc     ebx
0x1400a3a4e  add     r12, r14
0x1400a3a51  add     ebp, 0FFFFFFFFh
0x1400a3a54  jnz     short loc_1400A3A26
0x1400a3a56  mov     r14d, dword ptr [rsp+0D8h+arg_20]
0x1400a3a5e  mov     r15, [rsp+0D8h+var_58]
0x1400a3a66  mov     r12, [rsp+0D8h+var_50]
0x1400a3a6e  mov     [rsp+0D8h+var_98], rsi
0x1400a3a73  mov     esi, [rsp+0D8h+var_90]
0x1400a3a77  jmp     loc_1400A394B
0x1400a3a7c  add     ebx, ebp
0x1400a3a7e  jmp     loc_1400A394B
0x1400a3a83  test    esi, esi
0x1400a3a85  jz      loc_1400A3B36
0x1400a3a8b  mov     eax, esi
0x1400a3a8d  lea     rax, [rax+rax*2]
0x1400a3a91  shl     rax, 4
0x1400a3a95  add     rax, r15
0x1400a3a98  cmp     rax, r15
0x1400a3a9b  jnb     short loc_1400A3AA7
0x1400a3a9d  mov     eax, 0C0000095h
0x1400a3aa2  jmp     loc_1400A3B5D
0x1400a3aa7  mov     r13, [rsp+0D8h+arg_0]
0x1400a3aaf  mov     r15, rax
0x1400a3ab2  mov     rbp, [rsp+0D8h+var_98]
0x1400a3ab7  test    r13, r13
0x1400a3aba  jz      short loc_1400A3B32
0x1400a3abc  mov     eax, esi
0x1400a3abe  shl     eax, 0Ch
0x1400a3ac1  sub     r14d, eax
0x1400a3ac4  mov     edi, r14d
0x1400a3ac7  xor     r14d, r14d
0x1400a3aca  add     rdi, [rsp+0D8h+var_88]
0x1400a3acf  test    esi, esi
0x1400a3ad1  jz      short loc_1400A3B3B
0x1400a3ad3  mov     r12d, 1000h
0x1400a3ad9  mov     r9, rdi
0x1400a3adc  mov     [rsp+0D8h+var_B8], r12d
0x1400a3ae1  mov     r8d, 1014h
0x1400a3ae7  mov     rdx, rbp
0x1400a3aea  mov     rcx, r13
0x1400a3aed  call    SkpgInitializeExtent
0x1400a3af2  movzx   eax, word ptr [rbp+2]
0x1400a3af6  mov     ecx, 0FFFBh
0x1400a3afb  or      dword ptr [rbp+1Ch], 2
0x1400a3aff  and     ax, cx
0x1400a3b02  or      ax, 10h
0x1400a3b06  mov     dword ptr [rbp+18h], 1016h
0x1400a3b0d  mov     rdx, rbp
0x1400a3b10  mov     [rbp+2], ax
0x1400a3b14  mov     rcx, r13
0x1400a3b17  call    SkpgExtentCrc
0x1400a3b1c  mov     [rbp+3], al
0x1400a3b1f  inc     ebx
0x1400a3b21  add     rbp, 30h ; '0'
0x1400a3b25  add     rdi, r12
0x1400a3b28  inc     r14d
0x1400a3b2b  cmp     r14d, esi
0x1400a3b2e  jb      short loc_1400A3AD9
0x1400a3b30  jmp     short loc_1400A3B3B
0x1400a3b32  add     ebx, esi
0x1400a3b34  jmp     short loc_1400A3B3B
0x1400a3b36  mov     rbp, [rsp+0D8h+var_98]
0x1400a3b3b  mov     rax, [rsp+0D8h+arg_8]
0x1400a3b43  mov     [rax], rbp
0x1400a3b46  mov     rax, [rsp+0D8h+arg_18]
0x1400a3b4e  mov     [rax], ebx
0x1400a3b50  mov     rax, [rsp+0D8h+arg_10]
0x1400a3b58  mov     [rax], r15
0x1400a3b5b  xor     eax, eax
0x1400a3b5d  add     rsp, 98h
0x1400a3b64  pop     r15
0x1400a3b66  pop     r14
0x1400a3b68  pop     r13
0x1400a3b6a  pop     r12
0x1400a3b6c  pop     rdi
0x1400a3b6d  pop     rsi
0x1400a3b6e  pop     rbp
0x1400a3b6f  pop     rbx
0x1400a3b70  retn
```
