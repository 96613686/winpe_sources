# SkmiCommitHpatPages

- ea: `0x14001ed6c`
- end: `0x14001f01a`
- name: `SkmiCommitHpatPages`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14004a45c`

## callees

- `0x140002410`
- `0x140003780`
- `0x14001ed6c`
- `0x140020194`
- `0x1400202b0`
- `0x14002b534`
- `0x14002eabc`
- `0x14002f3f8`
- `0x140081290`
- `0x1400ee8b0`
- `0x1400f2fc0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitHpatPages(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // rbx
  _QWORD *StackBase; // rax
  __int64 v5; // r15
  _QWORD *v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  int v9; // ebp
  __int64 CurrentIrql; // r12
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r13
  __int64 PteTrace; // rax
  __int64 v20; // r14
  PVOID *v21; // rsi
  PVOID v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C0h]
  unsigned int v32; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B0h]
  unsigned __int64 v34; // [rsp+50h] [rbp-A8h]
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = a2;
  memset_0(&v32, 0, 0x68u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v5 = StackBase[10];
  else
    v5 = 0;
  v6 = KeGetPcr()->NtTib.StackBase;
  if ( v6 )
    v7 = v6[10];
  else
    v7 = 0;
  v8 = v2;
  v9 = SkmiChargeCommitment(v7, v2);
  if ( v9 >= 0 )
  {
    memset_0(&v32, 0, 0x68u);
    v34 = v2;
    HIWORD(v32) = 48;
    v33 = a1 << 12;
    SkCallNormalMode(&v32);
    v9 = v33;
    if ( (int)v33 < 0 )
    {
      if ( (_DWORD)v2 )
      {
        v27 = KeGetPcr()->NtTib.StackBase;
        if ( v27 )
          v28 = v27[10];
        else
          v28 = 0;
        SkmiReturnCommitment(v28, v2);
      }
    }
    else
    {
      CurrentIrql = KeGetCurrentIrql();
      v31 = CurrentIrql;
      __writecr8(2u);
      SkAcquireSpinLockExclusiveAtDpcLevel(v5 + 8);
      *(_QWORD *)BackTraceHash = 12290;
      SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v11, v12, v13);
      v14 = 0xFFFFF68000000000uLL;
      v15 = *(_QWORD *)BackTraceHash & 0xFFFFFFFFFFFFFC1FuLL | 0x60;
      v16 = 8 * (a1 & 0xFFFFFFFFFLL) - 0x98000000000LL;
      v17 = (v8 + a1 - 1) & 0xFFFFFFFFFLL;
      v18 = 8 * v17 - 0x98000000000LL;
      if ( v16 <= v18 )
      {
        do
        {
          PteTrace = SkmiGetPteTrace(0, v16, 0, v15, *(_QWORD *)v16);
          v20 = PteTrace;
          if ( PteTrace )
          {
            v21 = (PVOID *)(PteTrace + 32);
            memset_0((void *)(PteTrace + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v22 = KeGetPcr()->NtTib.StackBase;
              if ( v22 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v22, 8u, v21, BackTraceHash) )
                {
                  *(_QWORD *)(v20 + 40) = retaddr;
                  *v21 = (PVOID)SkmiGetInstructionPointer(v23, v14);
                }
              }
            }
          }
          v24 = v15;
          v17 = 0xFFFFF6FB7DBED000uLL;
          if ( v16 >= 0xFFFFF6FB7DBED000uLL )
          {
            v17 = 0xFFFFF6FB7DBED800uLL;
            if ( v16 < 0xFFFFF6FB7DBED800uLL )
            {
              v17 = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
              if ( v17 )
                v14 = *(_QWORD *)(v17 + 80);
              else
                v14 = 0;
              v25 = *(_QWORD *)(v14 + 232);
              if ( v25 )
              {
                v14 = (unsigned int)SkiKvaShadowMode;
                v17 = ((__int64)v16 >> 3) & 0x1FF;
                *(_QWORD *)(v25 + 8 * v17) = v15;
                if ( (_DWORD)v14 != 2 && (v15 & 1) != 0 )
                {
                  v17 = 0x8000000000000000uLL;
                  v24 = v15 | 0x8000000000000000uLL;
                }
              }
            }
          }
          *(_QWORD *)v16 = v24;
          v15 ^= 0x40u;
          v16 += 8LL;
        }
        while ( v16 <= v18 );
        LOBYTE(CurrentIrql) = v31;
      }
      *(_DWORD *)(v5 + 8) = 0;
      SkTrackSpinLockRelease(v17, v14);
      LOBYTE(v26) = CurrentIrql;
      SkeLowerIrql(v26);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001ed6c  mov     [rsp+arg_10], rbx
0x14001ed71  push    rbp
0x14001ed72  push    rsi
0x14001ed73  push    rdi
0x14001ed74  push    r12
0x14001ed76  push    r13
0x14001ed78  push    r14
0x14001ed7a  push    r15
0x14001ed7c  sub     rsp, 0C0h
0x14001ed83  mov     rax, cs:__security_cookie
0x14001ed8a  xor     rax, rsp
0x14001ed8d  mov     [rsp+0F8h+var_48], rax
0x14001ed95  mov     ebx, edx
0x14001ed97  mov     r14, rcx
0x14001ed9a  mov     r12d, 68h ; 'h'
0x14001eda0  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14001eda5  mov     r8d, r12d; Size
0x14001eda8  xor     edx, edx; Val
0x14001edaa  call    memset_0
0x14001edaf  mov     rax, gs:8
0x14001edb8  xor     edi, edi
0x14001edba  test    rax, rax
0x14001edbd  jz      short loc_14001EDC5
0x14001edbf  mov     r15, [rax+50h]
0x14001edc3  jmp     short loc_14001EDC8
0x14001edc5  mov     r15, rdi
0x14001edc8  mov     rax, gs:8
0x14001edd1  test    rax, rax
0x14001edd4  jz      short loc_14001EDDC
0x14001edd6  mov     rcx, [rax+50h]
0x14001edda  jmp     short loc_14001EDDF
0x14001eddc  mov     rcx, rdi
0x14001eddf  mov     rdx, rbx
0x14001ede2  mov     rsi, rbx
0x14001ede5  call    SkmiChargeCommitment
0x14001edea  mov     ebp, eax
0x14001edec  test    eax, eax
0x14001edee  js      loc_14001EFEC
0x14001edf4  mov     r8, r12; Size
0x14001edf7  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14001edfc  xor     edx, edx; Val
0x14001edfe  call    memset_0
0x14001ee03  mov     eax, 30h ; '0'
0x14001ee08  mov     [rsp+0F8h+var_A8], rbx
0x14001ee0d  mov     [rsp+0F8h+var_B6], ax
0x14001ee12  lea     rcx, [rsp+0F8h+var_B8]
0x14001ee17  mov     rax, r14
0x14001ee1a  shl     rax, 0Ch
0x14001ee1e  mov     [rsp+0F8h+var_B0], rax
0x14001ee23  call    SkCallNormalMode
0x14001ee28  mov     ebp, dword ptr [rsp+0F8h+var_B0]
0x14001ee2c  test    ebp, ebp
0x14001ee2e  js      loc_14001EFC9
0x14001ee34  mov     r12, cr8
0x14001ee38  mov     [rsp+0F8h+var_C0], r12
0x14001ee3d  mov     eax, 2
0x14001ee42  mov     cr8, rax
0x14001ee46  lea     rcx, [r15+8]
0x14001ee4a  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14001ee4f  lea     rcx, [rsp+0F8h+BackTraceHash]
0x14001ee54  mov     qword ptr [rsp+0F8h+BackTraceHash], 3002h
0x14001ee5d  call    SKMI_SWIZZLE_INVALID_PTE
0x14001ee62  mov     rbx, qword ptr [rsp+0F8h+BackTraceHash]
0x14001ee67  mov     rcx, r14
0x14001ee6a  and     rbx, 0FFFFFFFFFFFFFC7Fh
0x14001ee71  mov     rdx, 0FFFFF68000000000h
0x14001ee7b  mov     r8, 0FFFFFFFFFh
0x14001ee85  or      rbx, 60h
0x14001ee89  and     rcx, r8
0x14001ee8c  mov     rax, rdx
0x14001ee8f  lea     rdi, [rax+rcx*8]
0x14001ee93  lea     rcx, [r14-1]
0x14001ee97  add     rcx, rsi
0x14001ee9a  and     rcx, r8
0x14001ee9d  mov     rax, rdx
0x14001eea0  lea     r13, [rax+rcx*8]
0x14001eea4  cmp     rdi, r13
0x14001eea7  ja      loc_14001EFB2
0x14001eead  xor     r12d, r12d
0x14001eeb0  mov     rax, [rdi]
0x14001eeb3  mov     r9, rbx
0x14001eeb6  xor     r8d, r8d
0x14001eeb9  mov     [rsp+0F8h+var_D8], rax
0x14001eebe  mov     rdx, rdi
0x14001eec1  xor     ecx, ecx
0x14001eec3  call    SkmiGetPteTrace
0x14001eec8  mov     r14, rax
0x14001eecb  test    rax, rax
0x14001eece  jz      short loc_14001EF27
0x14001eed0  xor     edx, edx; Val
0x14001eed2  lea     rsi, [rax+20h]
0x14001eed6  mov     rcx, rsi; void *
0x14001eed9  lea     r8d, [rdx+40h]; Size
0x14001eedd  call    memset_0
0x14001eee2  test    cs:SkmiFlags, 400000h
0x14001eeec  jz      short loc_14001EF27
0x14001eeee  mov     rcx, gs:8; FramesToSkip
0x14001eef7  test    rcx, rcx
0x14001eefa  jz      short loc_14001EF27
0x14001eefc  lea     r9, [rsp+0F8h+BackTraceHash]; BackTraceHash
0x14001ef01  mov     r8, rsi; BackTrace
0x14001ef04  mov     edx, 8; FramesToCapture
0x14001ef09  call    RtlCaptureStackBackTrace
0x14001ef0e  test    ax, ax
0x14001ef11  jnz     short loc_14001EF27
0x14001ef13  mov     rax, [rsp+0F8h]
0x14001ef1b  mov     [r14+28h], rax
0x14001ef1f  call    SkmiGetInstructionPointer
0x14001ef24  mov     [rsi], rax
0x14001ef27  mov     rax, rbx
0x14001ef2a  mov     rcx, 0FFFFF6FB7DBED000h
0x14001ef34  cmp     rdi, rcx
0x14001ef37  jb      short loc_14001EF99
0x14001ef39  mov     rcx, 0FFFFF6FB7DBED800h
0x14001ef43  cmp     rdi, rcx
0x14001ef46  jnb     short loc_14001EF99
0x14001ef48  mov     rcx, gs:8
0x14001ef51  test    rcx, rcx
0x14001ef54  jz      short loc_14001EF5C
0x14001ef56  mov     rdx, [rcx+50h]
0x14001ef5a  jmp     short loc_14001EF5F
0x14001ef5c  mov     rdx, r12
0x14001ef5f  mov     r8, [rdx+0E8h]
0x14001ef66  test    r8, r8
0x14001ef69  jz      short loc_14001EF99
0x14001ef6b  mov     edx, cs:SkiKvaShadowMode
0x14001ef71  mov     rcx, rdi
0x14001ef74  sar     rcx, 3
0x14001ef78  and     ecx, 1FFh
0x14001ef7e  mov     [r8+rcx*8], rbx
0x14001ef82  cmp     edx, 2
0x14001ef85  jz      short loc_14001EF99
0x14001ef87  test    bl, 1
0x14001ef8a  jz      short loc_14001EF99
0x14001ef8c  mov     rcx, 8000000000000000h
0x14001ef96  or      rax, rcx
0x14001ef99  mov     [rdi], rax
0x14001ef9c  xor     rbx, 40h
0x14001efa0  add     rdi, 8
0x14001efa4  cmp     rdi, r13
0x14001efa7  jbe     loc_14001EEB0
0x14001efad  mov     r12, [rsp+0F8h+var_C0]
0x14001efb2  mov     dword ptr [r15+8], 0
0x14001efba  call    SkTrackSpinLockRelease
0x14001efbf  mov     cl, r12b
0x14001efc2  call    SkeLowerIrql
0x14001efc7  jmp     short loc_14001EFEC
0x14001efc9  test    ebx, ebx
0x14001efcb  jz      short loc_14001EFEC
0x14001efcd  mov     rcx, gs:8
0x14001efd6  test    rcx, rcx
0x14001efd9  jz      short loc_14001EFE1
0x14001efdb  mov     rcx, [rcx+50h]
0x14001efdf  jmp     short loc_14001EFE4
0x14001efe1  mov     rcx, rdi
0x14001efe4  mov     rdx, rsi
0x14001efe7  call    SkmiReturnCommitment
0x14001efec  mov     eax, ebp
0x14001efee  mov     rcx, [rsp+0F8h+var_48]
0x14001eff6  xor     rcx, rsp; StackCookie
0x14001eff9  call    __security_check_cookie
0x14001effe  mov     rbx, [rsp+0F8h+arg_10]
0x14001f006  add     rsp, 0C0h
0x14001f00d  pop     r15
0x14001f00f  pop     r14
0x14001f011  pop     r13
0x14001f013  pop     r12
0x14001f015  pop     rdi
0x14001f016  pop     rsi
0x14001f017  pop     rbp
0x14001f018  retn
```
