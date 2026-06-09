# RtlpHpLfhSubsegmentCommitBlock

- ea: `0x140010e0c`
- end: `0x140011059`
- name: `RtlpHpLfhSubsegmentCommitBlock`
- size: `589`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f0f0`
- `0x14000ffec`
- `0x140013c44`
- `0x140029bfc`

## callees

- `0x14000e680`
- `0x140010e0c`
- `0x1400326d4`
- `0x140032970`
- `0x1400cea14`
- `0x1400cf4b4`
- `0x1400cffd0`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhSubsegmentCommitBlock(_QWORD *a1, unsigned __int64 a2, unsigned int a3)
{
  unsigned int v3; // r10d
  unsigned __int64 v5; // r13
  char v6; // cl
  char v7; // r9
  unsigned int v8; // r12d
  int v9; // edi
  __int64 v10; // rdx
  signed __int16 *v11; // r14
  int v12; // r11d
  int v13; // ebx
  unsigned int v14; // r15d
  __int64 v15; // rax
  int v16; // r12d
  __int64 v17; // rbp
  int v18; // r15d
  signed __int16 *v19; // rdi
  signed __int16 v20; // ax
  char v21; // al
  signed __int16 v22; // tt
  int v23; // ebx
  char v24; // cl
  __int64 v25; // rbx
  unsigned int v26; // edi
  int v27; // ebp
  char v28; // al
  int v30; // [rsp+40h] [rbp-68h] BYREF
  int v31; // [rsp+44h] [rbp-64h] BYREF
  int v32; // [rsp+48h] [rbp-60h]
  unsigned __int64 v33; // [rsp+50h] [rbp-58h]
  char v35; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+18h]
  int v37; // [rsp+C8h] [rbp+20h]

  v36 = a3;
  v3 = 0;
  v32 = 0;
  v5 = (unsigned __int64)a1;
  v6 = *(_BYTE *)(a2 + 38);
  v7 = -1;
  v30 = 0;
  v8 = a3;
  v31 = 0;
  v9 = 0;
  v35 = -1;
  v10 = a3 >> 12 >> v6;
  v11 = (signed __int16 *)(a2 + 8LL * *(unsigned __int8 *)(a2 + 24) + 2 * v10);
  v33 = a2 + 8LL * *(unsigned __int8 *)(a2 + 24);
  _m_prefetchw(v11);
  v12 = 1;
  v13 = -1;
  v37 = (unsigned __int16)qword_140148348 ^ (unsigned __int16)(a2 >> 12) ^ *(unsigned __int16 *)(a2 + 40);
  v14 = v37;
  v15 = ((v37 + a3 - 1) >> 12 >> v6) - (unsigned int)v10 + 1;
  if ( v11 < &v11[v15] )
  {
    v16 = 0;
    LODWORD(v17) = 0;
    v18 = 0;
    v19 = &v11[v15];
    do
    {
      while ( 1 )
      {
        v20 = *v11;
        while ( v20 > 0 )
        {
          v22 = v20;
          v20 = _InterlockedCompareExchange16(v11, v20 + 1, v20);
          if ( v22 == v20 )
            goto LABEL_14;
        }
        if ( v16 )
          break;
        v16 = 1;
        v21 = RtlpHpAcquireLockExclusive(a2 + 56);
        v3 = 0;
        v7 = v21;
        v12 = 1;
      }
      if ( v20 )
      {
        ++v18;
        v17 = (__int64)((__int64)v11 - v33) >> 1;
        if ( v13 == -1 )
          v13 = (__int64)((__int64)v11 - v33) >> 1;
      }
      else
      {
        --v18;
      }
      *v11 = v20 + 1;
LABEL_14:
      ++v11;
    }
    while ( v11 < v19 );
    v5 = (unsigned __int64)a1;
    if ( v18 )
      RtlpHpLfhContextUpdateFreeCommitCount(a1, a2, (v18 << 12 << *(_BYTE *)(a2 + 38)) / 4096);
    v9 = v32;
    if ( v13 == -1 )
    {
      if ( v16 )
      {
        RtlpHpReleaseLockExclusive(a2 + 56);
        return 0;
      }
    }
    else
    {
      v35 = v7;
      v9 = v12 + v17 - v13;
      v30 = v9;
    }
    v8 = v36;
    v14 = v37;
  }
  if ( v13 == -1 )
    return v3;
  v24 = *(_BYTE *)(a2 + 38);
  v25 = (unsigned int)(v13 << 12 << v24);
  v26 = v9 << 12 << v24;
  v27 = v25;
  v23 = ((__int64 (__fastcall *)(_QWORD, unsigned __int64, _QWORD, int *))(v5 ^ RtlpHpHeapGlobals ^ *(_QWORD *)(v5 + 24)))(
          *(_QWORD *)v5,
          a2 + v25,
          v26,
          &v31);
  if ( v23 < 0 )
  {
    RtlpHpLfhSubsegmentDecBlockCounts(v5, a2, v8, v14);
    RtlpHpReleaseLockExclusive(a2 + 56);
  }
  else
  {
    RtlpHpLfhSubsegmentIncBlockCounts(v5, a2, v27, v26, (__int64)&v30, 1, (__int64)&v35);
    v28 = 3;
    if ( !v31 )
      v28 = 2;
    RtlpHpLfhSubsegmentPrefetchRange(2, a2, v27, v26, v28);
    return 0;
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140010e0c  mov     rax, rsp
0x140010e0f  mov     [rax+18h], r8d
0x140010e13  mov     [rax+8], rcx
0x140010e17  push    rbx
0x140010e18  push    rbp
0x140010e19  push    rsi
0x140010e1a  push    rdi
0x140010e1b  push    r12
0x140010e1d  push    r13
0x140010e1f  push    r14
0x140010e21  push    r15
0x140010e23  sub     rsp, 68h
0x140010e27  xor     r10d, r10d
0x140010e2a  mov     rsi, rdx
0x140010e2d  mov     [rax-60h], r10d
0x140010e31  mov     r13, rcx
0x140010e34  movzx   ecx, byte ptr [rdx+26h]
0x140010e38  mov     r9b, 0FFh
0x140010e3b  mov     edx, r8d
0x140010e3e  mov     [rax-68h], r10d
0x140010e42  shr     edx, 0Ch
0x140010e45  mov     r12d, r8d
0x140010e48  mov     [rax-64h], r10d
0x140010e4c  mov     edi, r10d
0x140010e4f  mov     [rax+10h], r9b
0x140010e53  movzx   eax, byte ptr [rsi+18h]
0x140010e57  shr     edx, cl
0x140010e59  lea     r8, [rsi+rax*8]
0x140010e5d  lea     r14, [r8+rdx*2]
0x140010e61  mov     [rsp+0A8h+var_58], r8
0x140010e66  prefetchw byte ptr [r14]
0x140010e6a  movzx   r15d, word ptr [rsi+28h]
0x140010e6f  lea     r11d, [r10+1]
0x140010e73  mov     rax, rsi
0x140010e76  or      ebx, 0FFFFFFFFh
0x140010e79  shr     rax, 0Ch
0x140010e7d  movzx   eax, ax
0x140010e80  xor     r15d, eax
0x140010e83  movzx   eax, word ptr cs:qword_140148348
0x140010e8a  xor     r15d, eax
0x140010e8d  lea     eax, [r12-1]
0x140010e92  add     eax, r15d
0x140010e95  mov     [rsp+0A8h+arg_18], r15d
0x140010e9d  shr     eax, 0Ch
0x140010ea0  shr     eax, cl
0x140010ea2  sub     eax, edx
0x140010ea4  add     eax, r11d
0x140010ea7  lea     rdx, [r14+rax*2]
0x140010eab  cmp     r14, rdx
0x140010eae  jnb     loc_140010F82
0x140010eb4  mov     r12d, r10d
0x140010eb7  mov     ebp, r10d
0x140010eba  mov     r15d, r10d
0x140010ebd  mov     rdi, rdx
0x140010ec0  movzx   eax, word ptr [r14]
0x140010ec4  test    ax, ax
0x140010ec7  jg      short loc_140010EE6
0x140010ec9  test    r12d, r12d
0x140010ecc  jnz     short loc_140010EF4
0x140010ece  lea     rcx, [rsi+38h]
0x140010ed2  mov     r12d, r11d
0x140010ed5  call    RtlpHpAcquireLockExclusive
0x140010eda  xor     r10d, r10d
0x140010edd  mov     r9b, al
0x140010ee0  lea     r11d, [r10+1]
0x140010ee4  jmp     short loc_140010EC0
0x140010ee6  lea     ecx, [r11+rax]
0x140010eea  lock cmpxchg [r14], cx
0x140010ef0  jnz     short loc_140010EC4
0x140010ef2  jmp     short loc_140010F1D
0x140010ef4  test    ax, ax
0x140010ef7  jnz     short loc_140010EFE
0x140010ef9  sub     r15d, r11d
0x140010efc  jmp     short loc_140010F15
0x140010efe  mov     r8, [rsp+0A8h+var_58]
0x140010f03  mov     rbp, r14
0x140010f06  sub     rbp, r8
0x140010f09  add     r15d, r11d
0x140010f0c  sar     rbp, 1
0x140010f0f  cmp     ebx, 0FFFFFFFFh
0x140010f12  cmovz   ebx, ebp
0x140010f15  add     ax, r11w
0x140010f19  mov     [r14], ax
0x140010f1d  add     r14, 2
0x140010f21  cmp     r14, rdi
0x140010f24  jb      short loc_140010EC0
0x140010f26  mov     r13, [rsp+0A8h+arg_0]
0x140010f2e  test    r15d, r15d
0x140010f31  jz      short loc_140010F56
0x140010f33  mov     cl, [rsi+26h]
0x140010f36  shl     r15d, 0Ch
0x140010f3a  shl     r15d, cl
0x140010f3d  mov     ecx, 1000h
0x140010f42  mov     eax, r15d
0x140010f45  cdq
0x140010f46  idiv    ecx
0x140010f48  mov     rdx, rsi
0x140010f4b  mov     rcx, r13
0x140010f4e  movsxd  r8, eax
0x140010f51  call    RtlpHpLfhContextUpdateFreeCommitCount
0x140010f56  mov     edi, [rsp+0A8h+var_60]
0x140010f5a  cmp     ebx, 0FFFFFFFFh
0x140010f5d  jz      short loc_140010F8F
0x140010f5f  mov     edi, ebp
0x140010f61  mov     [rsp+0A8h+arg_8], r9b
0x140010f69  sub     edi, ebx
0x140010f6b  add     edi, r11d
0x140010f6e  mov     [rsp+0A8h+var_68], edi
0x140010f72  mov     r12d, [rsp+0A8h+arg_10]
0x140010f7a  mov     r15d, [rsp+0A8h+arg_18]
0x140010f82  cmp     ebx, 0FFFFFFFFh
0x140010f85  jnz     short loc_140010FA2
0x140010f87  mov     ebx, r10d
0x140010f8a  jmp     loc_140011045
0x140010f8f  test    r12d, r12d
0x140010f92  jz      short loc_140010F72
0x140010f94  lea     rcx, [rsi+38h]
0x140010f98  call    RtlpHpReleaseLockExclusive
0x140010f9d  xor     r10d, r10d
0x140010fa0  jmp     short loc_140010F87
0x140010fa2  movzx   ecx, byte ptr [rsi+26h]
0x140010fa6  lea     r9, [rsp+0A8h+var_64]
0x140010fab  mov     rax, [r13+18h]
0x140010faf  xor     rax, cs:RtlpHpHeapGlobals
0x140010fb6  shl     ebx, 0Ch
0x140010fb9  xor     rax, r13
0x140010fbc  shl     ebx, cl
0x140010fbe  shl     edi, 0Ch
0x140010fc1  shl     edi, cl
0x140010fc3  mov     rcx, [r13+0]
0x140010fc7  mov     r8d, edi
0x140010fca  lea     rdx, [rsi+rbx]
0x140010fce  mov     ebp, ebx
0x140010fd0  call    rax
0x140010fd2  nop     dword ptr [rax]
0x140010fd5  mov     ebx, eax
0x140010fd7  mov     rdx, rsi
0x140010fda  mov     rcx, r13
0x140010fdd  test    eax, eax
0x140010fdf  js      short loc_140011031
0x140010fe1  lea     rax, [rsp+0A8h+arg_8]
0x140010fe9  mov     r9d, edi
0x140010fec  mov     [rsp+0A8h+var_78], rax
0x140010ff1  mov     r8d, ebp
0x140010ff4  lea     rax, [rsp+0A8h+var_68]
0x140010ff9  mov     [rsp+0A8h+var_80], 1
0x140011001  mov     [rsp+0A8h+var_88], rax
0x140011006  call    RtlpHpLfhSubsegmentIncBlockCounts
0x14001100b  cmp     [rsp+0A8h+var_64], 0
0x140011010  mov     eax, 3
0x140011015  mov     r9d, edi
0x140011018  mov     r8d, ebp
0x14001101b  mov     rdx, rsi
0x14001101e  lea     ecx, [rax-1]
0x140011021  cmovz   eax, ecx
0x140011024  mov     dword ptr [rsp+0A8h+var_88], eax
0x140011028  call    RtlpHpLfhSubsegmentPrefetchRange
0x14001102d  xor     ebx, ebx
0x14001102f  jmp     short loc_140011045
0x140011031  mov     r9d, r15d
0x140011034  mov     r8d, r12d
0x140011037  call    RtlpHpLfhSubsegmentDecBlockCounts
0x14001103c  lea     rcx, [rsi+38h]
0x140011040  call    RtlpHpReleaseLockExclusive
0x140011045  mov     eax, ebx
0x140011047  add     rsp, 68h
0x14001104b  pop     r15
0x14001104d  pop     r14
0x14001104f  pop     r13
0x140011051  pop     r12
0x140011053  pop     rdi
0x140011054  pop     rsi
0x140011055  pop     rbp
0x140011056  pop     rbx
0x140011057  retn
```
