# SkmiCommitVirtualPageRange

- ea: `0x140065d00`
- end: `0x1400660fd`
- name: `SkmiCommitVirtualPageRange`
- size: `1021`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14001ce38`
- `0x140065c04`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x14001f020`
- `0x140020194`
- `0x1400202b0`
- `0x140020360`
- `0x140020424`
- `0x14002b534`
- `0x14002eabc`
- `0x14002f3f8`
- `0x140037fe4`
- `0x14006580c`
- `0x140065d00`
- `0x140081290`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitVirtualPageRange(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v8; // r12
  int v9; // r13d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  unsigned __int64 v14; // rbx
  int v15; // edi
  __int64 v16; // r9
  unsigned __int64 v17; // rdi
  char v18; // al
  char v19; // r12
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r10
  __int64 PteTrace; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // r10
  __int64 v25; // r9
  __int64 v26; // r15
  PVOID *v27; // r14
  PVOID StackBase; // rcx
  USHORT v29; // ax
  __int64 v30; // rcx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // eax
  __int64 v36; // [rsp+20h] [rbp-E0h]
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h]
  __int64 v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  _BYTE v43[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+160h] [rbp+60h]
  char v45; // [rsp+164h] [rbp+64h]
  char v46; // [rsp+165h] [rbp+65h]
  unsigned int v47; // [rsp+170h] [rbp+70h] BYREF
  __int64 v48; // [rsp+178h] [rbp+78h]
  __int64 v49; // [rsp+188h] [rbp+88h]
  __int64 v50; // [rsp+190h] [rbp+90h]
  int v51; // [rsp+198h] [rbp+98h]
  _UNKNOWN *retaddr; // [rsp+228h] [rbp+128h]

  v5 = a3;
  v40 = a3;
  v6 = a2;
  v41 = a2;
  v42 = a4;
  v8 = a4;
  memset_0(v43, 0, 0x108u);
  memset_0(&v47, 0, 0x68u);
  v9 = 0;
  *(_QWORD *)BackTraceHash = 8194;
  v38 = 0;
  v39 = 0;
  SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v10, v11, v12);
  v13 = SkmiCommitVirtualPageTables(a1, v5, v8, *(unsigned __int64 *)BackTraceHash, v36, &v38);
  v14 = v38;
  v15 = v13;
  if ( v13 >= 0 )
  {
    if ( v38 && !_bittest64((const signed __int64 *)(v6 + 48), 0x31u) )
    {
      v15 = SkmiChargeCommitment(a1, v38);
      if ( v15 < 0 )
        goto LABEL_42;
      v39 = 1;
    }
    memset_0(&v47, 0, 0x68u);
    v51 = 4096;
    HIWORD(v47) = 12;
    v49 = v5 << 12;
    v50 = (v8 - v5 + 1) << 12;
    v48 = *(_QWORD *)(a1 + 48);
    SkCallNormalMode(&v47);
    v15 = v48;
    if ( (int)v48 >= 0 )
    {
      v17 = 8 * (v5 & 0xFFFFFFFFFLL) - 0x98000000000LL;
      *(_QWORD *)BackTraceHash = 20482;
      v18 = (*(_QWORD *)(v6 + 48) >> 44) & 7;
      v38 = 8 * (v8 & 0xFFFFFFFFFLL) - 0x98000000000LL;
      if ( v18 != 1 )
        *(_QWORD *)BackTraceHash = 12290;
      SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, 0xFFFFF68000000000uLL, 0xFFFFFFFFFLL, v16);
      v19 = -1;
      v46 = -1;
      v20 = (32LL * a5) ^ (*(_QWORD *)BackTraceHash ^ (32LL * a5)) & 0xFFFFFFFFFFFFFC1FuLL;
      if ( v17 <= v21 )
      {
        do
        {
          if ( (*(_QWORD *)v17 & 0x803LL) == 2 && (*(_QWORD *)v17 & 0x7000LL) == 0x2000 )
          {
            PteTrace = SkmiGetPteTrace(0, v17, 0, v20, *(_QWORD *)v17);
            v25 = 0;
            v26 = PteTrace;
            if ( PteTrace )
            {
              v27 = (PVOID *)(PteTrace + 32);
              memset_0((void *)(PteTrace + 32), 0, 0x40u);
              v25 = 0;
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                StackBase = KeGetPcr()->NtTib.StackBase;
                if ( StackBase )
                {
                  v29 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v27, BackTraceHash);
                  v25 = 0;
                  if ( !v29 )
                  {
                    *(_QWORD *)(v26 + 40) = retaddr;
                    *v27 = (PVOID)SkmiGetInstructionPointer(v30, v23);
                  }
                }
              }
              v24 = v38;
            }
            v31 = v20;
            v32 = 0xFFFFF6FB7DBED000uLL;
            if ( v17 >= 0xFFFFF6FB7DBED000uLL )
            {
              v32 = 0xFFFFF6FB7DBED800uLL;
              if ( v17 < 0xFFFFF6FB7DBED800uLL )
              {
                v32 = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
                v23 = v32 ? *(_QWORD *)(v32 + 80) : v25;
                v33 = *(_QWORD *)(v23 + 232);
                if ( v33 )
                {
                  v23 = (unsigned int)SkiKvaShadowMode;
                  v32 = ((__int64)v17 >> 3) & 0x1FF;
                  *(_QWORD *)(v33 + 8 * v32) = v20;
                  if ( (_DWORD)v23 != 2 && (v20 & 1) != 0 )
                  {
                    v32 = 0x8000000000000000uLL;
                    v31 = v20 | 0x8000000000000000uLL;
                  }
                }
              }
            }
            LODWORD(v6) = v41;
            *(_QWORD *)v17 = v31;
          }
          else
          {
            if ( v19 == -1 )
              v19 = SkAcquireSpinLockExclusive(a1 + 8);
            v34 = SkmiChangePageProtection(a1, v6, v17, a5, v9, (__int64)v43);
            v24 = v38;
            v9 = v34;
          }
          v17 += 8LL;
        }
        while ( v17 <= v24 );
        if ( v45 )
        {
          LOBYTE(v32) = v46;
          SkeFlushEntireTb(v32, a1);
        }
        else if ( v44 )
        {
          LOBYTE(v32) = v46;
          SkeFlushRangeListTb(v32, a1, v44, v43);
        }
        if ( v9 )
        {
          *(_DWORD *)(a1 + 192) = 0;
          SkTrackSpinLockRelease();
        }
        if ( v19 != -1 )
        {
          LOBYTE(v23) = v19;
          SkReleaseSpinLockExclusive(a1 + 8, v23);
        }
        v5 = v40;
      }
      v8 = v42;
      v14 = 0;
      v15 = 0;
    }
  }
LABEL_42:
  if ( v14 )
  {
    if ( v39 )
      SkmiReturnCommitment(a1, v14);
    SkmiFreeVirtualPageTables(a1, v5, v8, 1);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140065d00  mov     [rsp-8+arg_8], rbx
0x140065d05  push    rbp
0x140065d06  push    rsi
0x140065d07  push    rdi
0x140065d08  push    r12
0x140065d0a  push    r13
0x140065d0c  push    r14
0x140065d0e  push    r15
0x140065d10  lea     rbp, [rsp-0F0h]
0x140065d18  sub     rsp, 1F0h
0x140065d1f  mov     rax, cs:__security_cookie
0x140065d26  xor     rax, rsp
0x140065d29  mov     [rbp+120h+var_40], rax
0x140065d30  mov     r14, r8
0x140065d33  mov     [rsp+220h+var_1D8], r8
0x140065d38  mov     r15, rdx
0x140065d3b  mov     [rsp+220h+var_1D0], rdx
0x140065d40  mov     rsi, rcx
0x140065d43  mov     [rsp+220h+var_1C8], r9
0x140065d48  xor     edx, edx; Val
0x140065d4a  lea     rcx, [rsp+220h+var_1C0]; void *
0x140065d4f  mov     r8d, 108h; Size
0x140065d55  mov     r12, r9
0x140065d58  call    memset_0
0x140065d5d  xor     edx, edx; Val
0x140065d5f  lea     rcx, [rbp+120h+var_B0]; void *
0x140065d63  lea     r8d, [rdx+68h]; Size
0x140065d67  call    memset_0
0x140065d6c  xor     r13d, r13d
0x140065d6f  mov     qword ptr [rsp+220h+BackTraceHash], 2002h
0x140065d78  lea     rcx, [rsp+220h+BackTraceHash]
0x140065d7d  mov     [rsp+220h+var_1E8], r13
0x140065d82  mov     [rsp+220h+var_1E0], r13d
0x140065d87  call    SKMI_SWIZZLE_INVALID_PTE
0x140065d8c  mov     r9, qword ptr [rsp+220h+BackTraceHash]
0x140065d91  lea     rax, [rsp+220h+var_1E8]
0x140065d96  mov     r8, r12
0x140065d99  mov     [rsp+220h+var_1F8], rax
0x140065d9e  mov     rdx, r14
0x140065da1  mov     rcx, rsi
0x140065da4  call    SkmiCommitVirtualPageTables
0x140065da9  mov     rbx, [rsp+220h+var_1E8]
0x140065dae  mov     edi, eax
0x140065db0  test    eax, eax
0x140065db2  js      loc_1400660A5
0x140065db8  test    rbx, rbx
0x140065dbb  jz      short loc_140065DE2
0x140065dbd  bt      qword ptr [r15+30h], 31h ; '1'
0x140065dc3  jb      short loc_140065DE2
0x140065dc5  mov     rdx, rbx
0x140065dc8  mov     rcx, rsi
0x140065dcb  call    SkmiChargeCommitment
0x140065dd0  mov     edi, eax
0x140065dd2  test    eax, eax
0x140065dd4  js      loc_1400660A5
0x140065dda  mov     [rsp+220h+var_1E0], 1
0x140065de2  xor     edx, edx; Val
0x140065de4  lea     rcx, [rbp+120h+var_B0]; void *
0x140065de8  lea     r8d, [rdx+68h]; Size
0x140065dec  call    memset_0
0x140065df1  mov     eax, 0Ch
0x140065df6  mov     [rbp+120h+var_88], 1000h
0x140065e00  mov     [rbp+120h+var_AE], ax
0x140065e04  lea     rcx, [rbp+120h+var_B0]
0x140065e08  mov     rax, r14
0x140065e0b  shl     rax, 0Ch
0x140065e0f  mov     [rbp+120h+var_98], rax
0x140065e16  mov     rax, r12
0x140065e19  sub     rax, r14
0x140065e1c  inc     rax
0x140065e1f  shl     rax, 0Ch
0x140065e23  mov     [rbp+120h+var_90], rax
0x140065e2a  mov     rax, [rsi+30h]
0x140065e2e  mov     [rbp+120h+var_A8], rax
0x140065e32  call    SkCallNormalMode
0x140065e37  mov     edi, dword ptr [rbp+120h+var_A8]
0x140065e3a  test    edi, edi
0x140065e3c  js      loc_1400660A5
0x140065e42  mov     rcx, r14
0x140065e45  mov     rdx, 0FFFFF68000000000h
0x140065e4f  mov     r8, 0FFFFFFFFFh
0x140065e59  and     rcx, r8
0x140065e5c  mov     rax, rdx
0x140065e5f  lea     rdi, [rax+rcx*8]
0x140065e63  mov     rcx, r12
0x140065e66  and     rcx, r8
0x140065e69  mov     rax, rdx
0x140065e6c  lea     r10, [rax+rcx*8]
0x140065e70  mov     qword ptr [rsp+220h+BackTraceHash], 5002h
0x140065e79  mov     rax, [r15+30h]
0x140065e7d  lea     rcx, [rsp+220h+BackTraceHash]
0x140065e82  shr     rax, 2Ch
0x140065e86  and     al, 7
0x140065e88  mov     [rsp+220h+var_1E8], r10
0x140065e8d  cmp     al, 1
0x140065e8f  jz      short loc_140065E9A
0x140065e91  mov     qword ptr [rsp+220h+BackTraceHash], 3002h
0x140065e9a  call    SKMI_SWIZZLE_INVALID_PTE
0x140065e9f  mov     eax, [rbp+120h+arg_20]
0x140065ea5  mov     r12b, 0FFh
0x140065ea8  mov     r9, qword ptr [rsp+220h+BackTraceHash]
0x140065ead  shl     rax, 5
0x140065eb1  mov     rbx, rax
0x140065eb4  mov     [rbp+120h+var_BB], 0FFh
0x140065eb8  xor     rbx, r9
0x140065ebb  and     rbx, 0FFFFFFFFFFFFFC1Fh
0x140065ec2  xor     rbx, rax
0x140065ec5  cmp     rdi, r10
0x140065ec8  ja      loc_140066097
0x140065ece  mov     rax, [rdi]
0x140065ed1  mov     rcx, rax
0x140065ed4  and     ecx, 803h
0x140065eda  cmp     rcx, 2
0x140065ede  jnz     loc_140065FF5
0x140065ee4  and     eax, 7000h
0x140065ee9  cmp     rax, 2000h
0x140065eef  jnz     loc_140065FF5
0x140065ef5  mov     rax, [rdi]
0x140065ef8  mov     r9, rbx
0x140065efb  xor     r8d, r8d
0x140065efe  mov     [rsp+220h+var_200], rax
0x140065f03  mov     rdx, rdi
0x140065f06  xor     ecx, ecx
0x140065f08  call    SkmiGetPteTrace
0x140065f0d  xor     r9d, r9d
0x140065f10  mov     r15, rax
0x140065f13  test    rax, rax
0x140065f16  jz      short loc_140065F79
0x140065f18  lea     r14, [rax+20h]
0x140065f1c  xor     edx, edx; Val
0x140065f1e  mov     rcx, r14; void *
0x140065f21  lea     r8d, [r9+40h]; Size
0x140065f25  call    memset_0
0x140065f2a  xor     r9d, r9d
0x140065f2d  test    cs:SkmiFlags, 400000h
0x140065f37  jz      short loc_140065F74
0x140065f39  mov     rcx, gs:8; FramesToSkip
0x140065f42  test    rcx, rcx
0x140065f45  jz      short loc_140065F74
0x140065f47  lea     r9, [rsp+220h+BackTraceHash]; BackTraceHash
0x140065f4c  mov     r8, r14; BackTrace
0x140065f4f  mov     edx, 8; FramesToCapture
0x140065f54  call    RtlCaptureStackBackTrace
0x140065f59  xor     r9d, r9d
0x140065f5c  test    ax, ax
0x140065f5f  jnz     short loc_140065F74
0x140065f61  mov     rax, [rbp+128h]
0x140065f68  mov     [r15+28h], rax
0x140065f6c  call    SkmiGetInstructionPointer
0x140065f71  mov     [r14], rax
0x140065f74  mov     r10, [rsp+220h+var_1E8]
0x140065f79  mov     rax, rbx
0x140065f7c  mov     rcx, 0FFFFF6FB7DBED000h
0x140065f86  cmp     rdi, rcx
0x140065f89  jb      short loc_140065FEB
0x140065f8b  mov     rcx, 0FFFFF6FB7DBED800h
0x140065f95  cmp     rdi, rcx
0x140065f98  jnb     short loc_140065FEB
0x140065f9a  mov     rcx, gs:8
0x140065fa3  test    rcx, rcx
0x140065fa6  jz      short loc_140065FAE
0x140065fa8  mov     rdx, [rcx+50h]
0x140065fac  jmp     short loc_140065FB1
0x140065fae  mov     rdx, r9
0x140065fb1  mov     r8, [rdx+0E8h]
0x140065fb8  test    r8, r8
0x140065fbb  jz      short loc_140065FEB
0x140065fbd  mov     edx, cs:SkiKvaShadowMode
0x140065fc3  mov     rcx, rdi
0x140065fc6  sar     rcx, 3
0x140065fca  and     ecx, 1FFh
0x140065fd0  mov     [r8+rcx*8], rbx
0x140065fd4  cmp     edx, 2
0x140065fd7  jz      short loc_140065FEB
0x140065fd9  test    bl, 1
0x140065fdc  jz      short loc_140065FEB
0x140065fde  mov     rcx, 8000000000000000h
0x140065fe8  or      rax, rcx
0x140065feb  mov     r15, [rsp+220h+var_1D0]
0x140065ff0  mov     [rdi], rax
0x140065ff3  jmp     short loc_140066033
0x140065ff5  cmp     r12b, 0FFh
0x140065ff9  jnz     short loc_140066007
0x140065ffb  lea     rcx, [rsi+8]
0x140065fff  call    SkAcquireSpinLockExclusive
0x140066004  mov     r12b, al
0x140066007  mov     r9d, [rbp+120h+arg_20]
0x14006600e  lea     rax, [rsp+220h+var_1C0]
0x140066013  mov     [rsp+220h+var_1F8], rax
0x140066018  mov     r8, rdi
0x14006601b  mov     rdx, r15
0x14006601e  mov     dword ptr [rsp+220h+var_200], r13d
0x140066023  mov     rcx, rsi
0x140066026  call    SkmiChangePageProtection
0x14006602b  mov     r10, [rsp+220h+var_1E8]
0x140066030  mov     r13d, eax
0x140066033  add     rdi, 8
0x140066037  cmp     rdi, r10
0x14006603a  jbe     loc_140065ECE
0x140066040  cmp     [rbp+120h+var_BC], 0
0x140066044  jz      short loc_140066053
0x140066046  mov     cl, [rbp+120h+var_BB]
0x140066049  mov     rdx, rsi
0x14006604c  call    SkeFlushEntireTb
0x140066051  jmp     short loc_14006606C
0x140066053  mov     r8d, [rbp+120h+var_C0]
0x140066057  test    r8d, r8d
0x14006605a  jz      short loc_14006606C
0x14006605c  mov     cl, [rbp+120h+var_BB]
0x14006605f  lea     r9, [rsp+220h+var_1C0]
0x140066064  mov     rdx, rsi
0x140066067  call    SkeFlushRangeListTb
0x14006606c  test    r13d, r13d
0x14006606f  jz      short loc_140066080
0x140066071  mov     dword ptr [rsi+0C0h], 0
0x14006607b  call    SkTrackSpinLockRelease
0x140066080  cmp     r12b, 0FFh
0x140066084  jz      short loc_140066092
0x140066086  lea     rcx, [rsi+8]
0x14006608a  mov     dl, r12b
0x14006608d  call    SkReleaseSpinLockExclusive
0x140066092  mov     r14, [rsp+220h+var_1D8]
0x140066097  mov     r12, [rsp+220h+var_1C8]
0x14006609c  xor     r13d, r13d
0x14006609f  mov     ebx, r13d
0x1400660a2  mov     edi, r13d
0x1400660a5  test    rbx, rbx
0x1400660a8  jz      short loc_1400660D0
0x1400660aa  cmp     [rsp+220h+var_1E0], r13d
0x1400660af  jz      short loc_1400660BC
0x1400660b1  mov     rdx, rbx
0x1400660b4  mov     rcx, rsi
0x1400660b7  call    SkmiReturnCommitment
0x1400660bc  mov     r9d, 1
0x1400660c2  mov     r8, r12
0x1400660c5  mov     rdx, r14
0x1400660c8  mov     rcx, rsi
0x1400660cb  call    SkmiFreeVirtualPageTables
0x1400660d0  mov     eax, edi
0x1400660d2  mov     rcx, [rbp+120h+var_40]
0x1400660d9  xor     rcx, rsp; StackCookie
0x1400660dc  call    __security_check_cookie
0x1400660e1  mov     rbx, [rsp+220h+arg_8]
0x1400660e9  add     rsp, 1F0h
0x1400660f0  pop     r15
0x1400660f2  pop     r14
0x1400660f4  pop     r13
0x1400660f6  pop     r12
0x1400660f8  pop     rdi
0x1400660f9  pop     rsi
0x1400660fa  pop     rbp
0x1400660fb  retn
```
