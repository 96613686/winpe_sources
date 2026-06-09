# SkmiCommitBasicEnclavePage

- ea: `0x14006a4b8`
- end: `0x14006a997`
- name: `SkmiCommitBasicEnclavePage`
- size: `1247`
- prototype: `__int64 __fastcall(int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14001ce38`
- `0x14006b7a8`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x14001f020`
- `0x140020194`
- `0x14002b534`
- `0x14002eabc`
- `0x14002f3f8`
- `0x140031148`
- `0x140037fe4`
- `0x14006a4b8`
- `0x14006a9a0`
- `0x140081290`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitBasicEnclavePage(int a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 result; // rax
  ULONG v10[2]; // [rsp+48h] [rbp-79h] BYREF
  __int64 v11; // [rsp+50h] [rbp-71h]
  _BYTE v12[2]; // [rsp+60h] [rbp-61h] BYREF

  v11 = a4;
  memset_0(v12, 0, 0x68u);
  *(_QWORD *)v10 = 8194;
  SKMI_SWIZZLE_INVALID_PTE(v10, v6, v7, v8);
  result = SkmiCommitVirtualPageTables(a1, a2, a2, v10[0]);
  if ( (int)result >= 0 )
    return 3221225505LL;
  return result;
}

```

## disassembly

```asm
0x14006a4b8  mov     [rsp-8+arg_10], rbx
0x14006a4bd  push    rbp
0x14006a4be  push    rsi
0x14006a4bf  push    rdi
0x14006a4c0  push    r12
0x14006a4c2  push    r13
0x14006a4c4  push    r14
0x14006a4c6  push    r15
0x14006a4c8  lea     rbp, [rsp-1Fh]
0x14006a4cd  sub     rsp, 0E0h
0x14006a4d4  mov     rax, cs:__security_cookie
0x14006a4db  xor     rax, rsp
0x14006a4de  mov     [rbp+4Fh+var_40], rax
0x14006a4e2  xor     edi, edi
0x14006a4e4  mov     [rsp+110h+BackTraceHash], r8d
0x14006a4e9  mov     r12d, r8d
0x14006a4ec  mov     [rbp+4Fh+var_C0], r9
0x14006a4f0  mov     r14, rdx
0x14006a4f3  mov     [rsp+110h+var_D0], rdi
0x14006a4f8  mov     rbx, rcx
0x14006a4fb  xor     edx, edx; Val
0x14006a4fd  lea     r8d, [rdi+68h]; Size
0x14006a501  mov     r13, r9
0x14006a504  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14006a508  call    memset_0
0x14006a50d  lea     rcx, [rbp+4Fh+var_C8]
0x14006a511  mov     qword ptr [rbp+4Fh+var_C8], 2002h
0x14006a519  call    SKMI_SWIZZLE_INVALID_PTE
0x14006a51e  mov     r9, qword ptr [rbp+4Fh+var_C8]
0x14006a522  lea     rax, [rsp+110h+var_D0]
0x14006a527  mov     r8, r14
0x14006a52a  mov     [rsp+110h+var_E8], rax
0x14006a52f  mov     rdx, r14
0x14006a532  mov     rcx, rbx
0x14006a535  call    SkmiCommitVirtualPageTables
0x14006a53a  test    eax, eax
0x14006a53c  js      loc_14006A5DB
0x14006a542  mov     rsi, [rsp+110h+var_D0]
0x14006a547  test    rsi, rsi
0x14006a54a  jnz     short loc_14006A556
0x14006a54c  mov     eax, 0C0000021h
0x14006a551  jmp     loc_14006A5DB
0x14006a556  mov     rdx, rsi
0x14006a559  mov     rcx, rbx
0x14006a55c  call    SkmiChargeCommitment
0x14006a561  xor     r10d, r10d
0x14006a564  mov     edi, eax
0x14006a566  test    eax, eax
0x14006a568  js      short loc_14006A5C8
0x14006a56a  mov     r15, r14
0x14006a56d  shl     r15, 0Ch
0x14006a571  test    r12d, r12d
0x14006a574  jz      loc_14006A603
0x14006a57a  xor     edx, edx; Val
0x14006a57c  lea     r8d, [r10+68h]; Size
0x14006a580  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14006a584  call    memset_0
0x14006a589  mov     ecx, 1000h
0x14006a58e  mov     [rbp+4Fh+var_98], r15
0x14006a592  mov     eax, 0Ch
0x14006a597  mov     [rbp+4Fh+var_90], rcx
0x14006a59b  mov     [rbp+4Fh+var_AE], ax
0x14006a59f  mov     rax, [rbx+30h]
0x14006a5a3  mov     [rbp+4Fh+var_88], ecx
0x14006a5a6  lea     rcx, [rbp+4Fh+var_B0]
0x14006a5aa  mov     [rbp+4Fh+var_A8], rax
0x14006a5ae  call    SkCallNormalMode
0x14006a5b3  mov     edi, dword ptr [rbp+4Fh+var_A8]
0x14006a5b6  xor     r10d, r10d
0x14006a5b9  test    edi, edi
0x14006a5bb  jns     short loc_14006A603
0x14006a5bd  mov     rdx, rsi
0x14006a5c0  mov     rcx, rbx
0x14006a5c3  call    SkmiReturnCommitment
0x14006a5c8  xor     r9d, r9d
0x14006a5cb  mov     r8, r14
0x14006a5ce  mov     rdx, r14
0x14006a5d1  mov     rcx, rbx
0x14006a5d4  call    SkmiFreeVirtualPageTables
0x14006a5d9  mov     eax, edi
0x14006a5db  mov     rcx, [rbp+4Fh+var_40]
0x14006a5df  xor     rcx, rsp; StackCookie
0x14006a5e2  call    __security_check_cookie
0x14006a5e7  mov     rbx, [rsp+110h+arg_10]
0x14006a5ef  add     rsp, 0E0h
0x14006a5f6  pop     r15
0x14006a5f8  pop     r14
0x14006a5fa  pop     r13
0x14006a5fc  pop     r12
0x14006a5fe  pop     rdi
0x14006a5ff  pop     rsi
0x14006a600  pop     rbp
0x14006a601  retn
0x14006a603  mov     rsi, r15
0x14006a606  mov     rcx, 7FFFFFFFF8h
0x14006a610  shr     rsi, 9
0x14006a614  and     rsi, rcx
0x14006a617  mov     rcx, 0FFFFF68000000000h
0x14006a621  add     rsi, rcx
0x14006a624  mov     [rsp+110h+var_D0], 3002h
0x14006a62d  lea     rcx, [rsp+110h+var_D0]
0x14006a632  call    SKMI_SWIZZLE_INVALID_PTE
0x14006a637  mov     rcx, [rsi]
0x14006a63a  xor     r8d, r8d
0x14006a63d  mov     rdi, [rsp+110h+var_D0]
0x14006a642  mov     rdx, rsi
0x14006a645  mov     [rsp+110h+var_F0], rcx
0x14006a64a  xor     ecx, ecx
0x14006a64c  test    r13, r13
0x14006a64f  jnz     loc_14006A753
0x14006a655  mov     eax, [rbp+4Fh+arg_20]
0x14006a658  shl     rax, 5
0x14006a65c  mov     rbx, rax
0x14006a65f  xor     rbx, rdi
0x14006a662  and     rbx, 0FFFFFFFFFFFFFC1Fh
0x14006a669  xor     rbx, rax
0x14006a66c  mov     r9, rbx
0x14006a66f  call    SkmiGetPteTrace
0x14006a674  mov     r14, rax
0x14006a677  test    rax, rax
0x14006a67a  jz      short loc_14006A6D4
0x14006a67c  lea     rdi, [rax+20h]
0x14006a680  xor     edx, edx; Val
0x14006a682  mov     rcx, rdi; void *
0x14006a685  lea     r8d, [r13+40h]; Size
0x14006a689  call    memset_0
0x14006a68e  xor     r10d, r10d
0x14006a691  test    cs:SkmiFlags, 400000h
0x14006a69b  jz      short loc_14006A6D4
0x14006a69d  mov     rax, gs:8
0x14006a6a6  test    rax, rax
0x14006a6a9  jz      short loc_14006A6D4
0x14006a6ab  lea     r9, [rsp+110h+BackTraceHash]; BackTraceHash
0x14006a6b0  mov     r8, rdi; BackTrace
0x14006a6b3  lea     edx, [r13+8]; FramesToCapture
0x14006a6b7  call    RtlCaptureStackBackTrace
0x14006a6bc  xor     r10d, r10d
0x14006a6bf  test    ax, ax
0x14006a6c2  jnz     short loc_14006A6D4
0x14006a6c4  mov     rax, [rbp+57h]
0x14006a6c8  mov     [r14+28h], rax
0x14006a6cc  call    SkmiGetInstructionPointer
0x14006a6d1  mov     [rdi], rax
0x14006a6d4  mov     r13, 0FFFFF6FB7DBED000h
0x14006a6de  mov     rax, r13
0x14006a6e1  cmp     rsi, rax
0x14006a6e4  jb      short loc_14006A748
0x14006a6e6  mov     r12, 0FFFFF6FB7DBED800h
0x14006a6f0  mov     rax, r12
0x14006a6f3  cmp     rsi, rax
0x14006a6f6  jnb     short loc_14006A748
0x14006a6f8  mov     rax, gs:8
0x14006a701  test    rax, rax
0x14006a704  jz      short loc_14006A70C
0x14006a706  mov     rcx, [rax+50h]
0x14006a70a  jmp     short loc_14006A70F
0x14006a70c  mov     rcx, r10
0x14006a70f  mov     rdx, [rcx+0E8h]
0x14006a716  test    rdx, rdx
0x14006a719  jz      short loc_14006A748
0x14006a71b  mov     ecx, cs:SkiKvaShadowMode
0x14006a721  mov     rax, rsi
0x14006a724  sar     rax, 3
0x14006a728  and     eax, 1FFh
0x14006a72d  mov     [rdx+rax*8], rbx
0x14006a731  cmp     ecx, 2
0x14006a734  jz      short loc_14006A748
0x14006a736  test    bl, 1
0x14006a739  jz      short loc_14006A748
0x14006a73b  mov     rax, 8000000000000000h
0x14006a745  or      rbx, rax
0x14006a748  mov     [rsi], rbx
0x14006a74b  mov     edi, r10d
0x14006a74e  jmp     loc_14006A5D9
0x14006a753  and     rdi, 0FFFFFFFFFFFFFD1Fh
0x14006a75a  bts     rdi, 8
0x14006a75f  mov     r9, rdi
0x14006a762  call    SkmiGetPteTrace
0x14006a767  mov     r13, rax
0x14006a76a  test    rax, rax
0x14006a76d  jz      short loc_14006A7C7
0x14006a76f  xor     edx, edx; Val
0x14006a771  lea     r12, [rax+20h]
0x14006a775  mov     rcx, r12; void *
0x14006a778  lea     r8d, [rdx+40h]; Size
0x14006a77c  call    memset_0
0x14006a781  xor     r10d, r10d
0x14006a784  test    cs:SkmiFlags, 400000h
0x14006a78e  jz      short loc_14006A7C7
0x14006a790  mov     rax, gs:8
0x14006a799  test    rax, rax
0x14006a79c  jz      short loc_14006A7C7
0x14006a79e  lea     r9, [rbp+4Fh+var_C8]; BackTraceHash
0x14006a7a2  mov     r8, r12; BackTrace
0x14006a7a5  lea     edx, [r10+8]; FramesToCapture
0x14006a7a9  call    RtlCaptureStackBackTrace
0x14006a7ae  xor     r10d, r10d
0x14006a7b1  test    ax, ax
0x14006a7b4  jnz     short loc_14006A7C7
0x14006a7b6  mov     rax, [rbp+57h]
0x14006a7ba  mov     [r13+28h], rax
0x14006a7be  call    SkmiGetInstructionPointer
0x14006a7c3  mov     [r12], rax
0x14006a7c7  mov     r13, 0FFFFF6FB7DBED000h
0x14006a7d1  mov     rax, r13
0x14006a7d4  mov     r12, 0FFFFF6FB7DBED800h
0x14006a7de  mov     rdx, 8000000000000000h
0x14006a7e8  cmp     rsi, rax
0x14006a7eb  jb      short loc_14006A83C
0x14006a7ed  mov     rax, r12
0x14006a7f0  cmp     rsi, rax
0x14006a7f3  jnb     short loc_14006A83C
0x14006a7f5  mov     rax, gs:8
0x14006a7fe  test    rax, rax
0x14006a801  jz      short loc_14006A809
0x14006a803  mov     rcx, [rax+50h]
0x14006a807  jmp     short loc_14006A80C
0x14006a809  mov     rcx, r10
0x14006a80c  mov     r8, [rcx+0E8h]
0x14006a813  test    r8, r8
0x14006a816  jz      short loc_14006A83C
0x14006a818  mov     ecx, cs:SkiKvaShadowMode
0x14006a81e  mov     rax, rsi
0x14006a821  sar     rax, 3
0x14006a825  and     eax, 1FFh
0x14006a82a  mov     [r8+rax*8], rdi
0x14006a82e  cmp     ecx, 2
0x14006a831  jz      short loc_14006A83C
0x14006a833  test    dil, 1
0x14006a837  jz      short loc_14006A83C
0x14006a839  or      rdi, rdx
0x14006a83c  mov     r8, [rbp+4Fh+var_C0]
0x14006a840  mov     rdx, r15
0x14006a843  mov     rcx, rbx
0x14006a846  mov     [rsi], rdi
0x14006a849  call    SkmiPrepopulatePage
0x14006a84e  mov     edi, eax
0x14006a850  test    eax, eax
0x14006a852  js      loc_14006A982
0x14006a858  lea     r14, [rbx+8]
0x14006a85c  mov     rcx, r14
0x14006a85f  mov     qword ptr [rsp+110h+BackTraceHash], r14
0x14006a864  call    SkAcquireSpinLockExclusive
0x14006a869  mov     rcx, [rsi]
0x14006a86c  xor     r8d, r8d
0x14006a86f  mov     edx, [rbp+4Fh+arg_20]
0x14006a872  mov     r10b, al
0x14006a875  shl     rdx, 5
0x14006a879  mov     rbx, rdx
0x14006a87c  mov     [rsp+110h+var_E0], al
0x14006a880  xor     rbx, rcx
0x14006a883  mov     rcx, [rsi]
0x14006a886  mov     [rsp+110h+var_F0], rcx
0x14006a88b  and     rbx, 0FFFFFFFFFFFFFC1Fh
0x14006a892  xor     rbx, rdx
0x14006a895  xor     ecx, ecx
0x14006a897  mov     r9, rbx
0x14006a89a  mov     rdx, rsi
0x14006a89d  call    SkmiGetPteTrace
0x14006a8a2  xor     r8d, r8d
0x14006a8a5  mov     r15, rax
0x14006a8a8  test    rax, rax
0x14006a8ab  jz      short loc_14006A90F
0x14006a8ad  xor     edx, edx; Val
0x14006a8af  lea     r14, [rax+20h]
0x14006a8b3  mov     rcx, r14; void *
0x14006a8b6  lea     r8d, [rdx+40h]; Size
0x14006a8ba  call    memset_0
0x14006a8bf  xor     r8d, r8d
0x14006a8c2  test    cs:SkmiFlags, 400000h
0x14006a8cc  jz      short loc_14006A905
0x14006a8ce  mov     rcx, gs:8; FramesToSkip
0x14006a8d7  test    rcx, rcx
0x14006a8da  jz      short loc_14006A905
0x14006a8dc  lea     r9, [rbp+4Fh+var_C8]; BackTraceHash
0x14006a8e0  mov     r8, r14; BackTrace
0x14006a8e3  mov     edx, 8; FramesToCapture
0x14006a8e8  call    RtlCaptureStackBackTrace
0x14006a8ed  xor     r8d, r8d
0x14006a8f0  test    ax, ax
0x14006a8f3  jnz     short loc_14006A905
0x14006a8f5  mov     rax, [rbp+57h]
0x14006a8f9  mov     [r15+28h], rax
0x14006a8fd  call    SkmiGetInstructionPointer
0x14006a902  mov     [r14], rax
0x14006a905  mov     r10b, [rsp+110h+var_E0]
0x14006a90a  mov     r14, qword ptr [rsp+110h+BackTraceHash]
0x14006a90f  mov     rax, r13
0x14006a912  cmp     rsi, rax
0x14006a915  jb      short loc_14006A96F
0x14006a917  mov     rax, r12
0x14006a91a  cmp     rsi, rax
0x14006a91d  jnb     short loc_14006A96F
0x14006a91f  mov     rax, gs:8
0x14006a928  test    rax, rax
0x14006a92b  jz      short loc_14006A933
0x14006a92d  mov     rcx, [rax+50h]
0x14006a931  jmp     short loc_14006A936
0x14006a933  mov     rcx, r8
0x14006a936  mov     rdx, [rcx+0E8h]
  ... truncated ...
```
