# SkmiConfigureEnclavePartition

- ea: `0x140070cd8`
- end: `0x140071099`
- name: `SkmiConfigureEnclavePartition`
- size: `961`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006b310`

## callees

- `0x140002900`
- `0x140003780`
- `0x14000b084`
- `0x14000d020`
- `0x140027ac0`
- `0x14002b534`
- `0x14002bd78`
- `0x140050ba4`
- `0x140070cd8`
- `0x140081290`
- `0x140095cd8`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiConfigureEnclavePartition(__int64 *a1)
{
  __int64 *v2; // r14
  unsigned __int64 v3; // rdi
  __int64 SystemPtes; // rbx
  _QWORD *StackBase; // rax
  __int64 v6; // rax
  unsigned int v7; // esi
  __int64 v8; // r15
  __int64 v9; // rsi
  unsigned __int64 v10; // rsi
  __int64 PteTrace; // rax
  __int64 v12; // r8
  PVOID *v13; // r15
  PVOID v14; // rcx
  USHORT v15; // ax
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v26; // rbx
  __int64 v27; // r9
  volatile signed __int32 *v28; // r8
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h]
  _BYTE v32[44]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+6Ch] [rbp-94h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int64 v38[11]; // [rsp+98h] [rbp-68h] BYREF
  _UNKNOWN *retaddr; // [rsp+148h] [rbp+48h]

  memset_0(v32, 0, 0x40u);
  memset_0(&v35, 0, 0x68u);
  v2 = SkmiSystemPartition;
  if ( a1 )
    v2 = a1;
  LOBYTE(v3) = 1;
  SystemPtes = SkmiAllocateSystemPtes((__int64)&SkmiSystemPtes, 1u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v6 = StackBase[18];
    if ( v6 )
      --*(_WORD *)(v6 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(v2 + 29);
  if ( v2[30] )
    goto LABEL_26;
  if ( SystemPtes )
  {
    BYTE1(v35) = 0;
    HIWORD(v35) = 38;
    v37 = v2[3];
    v36 = 1;
    v38[0] = (unsigned int)(12 * SkeNumberProcessors);
    SkCallNormalMode(&v35);
    v7 = v36;
    if ( (int)v36 < 0 )
      goto LABEL_27;
    SkmmInitializeShortMdl(v32, v37, 88, v38);
    v8 = v33;
    if ( (unsigned __int64)v33 + 88 > 0x1000 )
    {
      SKMI_SECURITY(44545);
      BYTE1(v35) = 0;
      v36 = 0;
      HIWORD(v35) = 38;
      SkCallNormalMode(&v35);
      goto LABEL_27;
    }
    v9 = v34;
    *(_QWORD *)BackTraceHash = v34;
    SkmiClaimPhysicalPages((ULONG_PTR)BackTraceHash, 1, 1u);
    v10 = ((word_140156D90 & 1 | (16 * (v9 & 0xFFFFFFFFFFLL))) << 8) | 0x8000000000000063uLL;
    PteTrace = SkmiGetPteTrace(0, SystemPtes, 0, v10, *(_QWORD *)SystemPtes);
    v12 = 0;
    v31 = PteTrace;
    if ( PteTrace )
    {
      v13 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      v12 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v14 = KeGetPcr()->NtTib.StackBase;
        if ( v14 )
        {
          v15 = RtlCaptureStackBackTrace((ULONG)v14, 8u, v13, BackTraceHash);
          v12 = 0;
          if ( !v15 )
          {
            v17 = v31;
            *(_QWORD *)(v31 + 40) = retaddr;
            *v13 = (PVOID)SkmiGetInstructionPointer(v17, v16);
          }
        }
      }
      v8 = v33;
    }
    if ( (unsigned __int64)SystemPtes >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)SystemPtes < 0xFFFFF6FB7DBED800uLL )
    {
      v18 = KeGetPcr()->NtTib.StackBase;
      v19 = v18 ? v18[10] : v12;
      v20 = *(_QWORD *)(v19 + 232);
      if ( v20 )
        *(_QWORD *)(v20 + 8 * ((SystemPtes >> 3) & 0x1FF)) = v10;
    }
    *(_QWORD *)SystemPtes = v10;
    v2[31] = v37;
    v2[30] = v8 + (SystemPtes << 25 >> 16);
    SystemPtes = 0;
LABEL_26:
    v7 = 0;
    goto LABEL_27;
  }
  v7 = -1073741670;
LABEL_27:
  RtlReleaseSRWLockExclusive(v2 + 29);
  v23 = KeGetPcr()->NtTib.StackBase;
  if ( v23 )
  {
    v24 = v23[18];
    if ( v24 )
    {
      if ( (*(_WORD *)(v24 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v24 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v23[17]
        && !*(_WORD *)(v24 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery(xmmword_140167160, v24, v21, v22);
      }
    }
  }
  if ( SystemPtes )
  {
    v26 = (SystemPtes - SkmiSystemPtes) >> 3;
    v27 = v26 & 0x1F;
    v28 = (volatile signed __int32 *)(qword_140156F78 + 4 * ((unsigned __int64)(unsigned int)v26 >> 5));
    if ( (unsigned __int64)(v27 + 1) > 0x20 )
    {
      if ( (v26 & 0x1F) == 0 )
        goto LABEL_41;
      _InterlockedAnd(v28, ~(((1 << (32 - (v26 & 0x1F))) - 1) << v27));
      v3 = 1LL - (32 - (unsigned int)(v26 & 0x1F));
      ++v28;
      while ( v3 >= 0x20 )
      {
        *v28++ = 0;
        v3 -= 32LL;
      }
      if ( v3 )
LABEL_41:
        _InterlockedAnd(v28, -1 << v3);
    }
    else
    {
      _InterlockedAnd(v28, ~(1 << v27));
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140070cd8  push    rbp
0x140070cda  push    rbx
0x140070cdb  push    rsi
0x140070cdc  push    rdi
0x140070cdd  push    r12
0x140070cdf  push    r13
0x140070ce1  push    r14
0x140070ce3  push    r15
0x140070ce5  lea     rbp, [rsp-8]
0x140070cea  sub     rsp, 108h
0x140070cf1  mov     rax, cs:__security_cookie
0x140070cf8  xor     rax, rsp
0x140070cfb  mov     [rbp+40h+var_50], rax
0x140070cff  xor     edx, edx; Val
0x140070d01  mov     rbx, rcx
0x140070d04  lea     rcx, [rsp+140h+var_100]; void *
0x140070d09  lea     r8d, [rdx+40h]; Size
0x140070d0d  call    memset_0
0x140070d12  xor     edx, edx; Val
0x140070d14  lea     rcx, [rbp+40h+var_C0]; void *
0x140070d18  lea     r8d, [rdx+68h]; Size
0x140070d1c  call    memset_0
0x140070d21  xor     r15d, r15d
0x140070d24  lea     r14, SkmiSystemPartition
0x140070d2b  test    rbx, rbx
0x140070d2e  lea     rcx, SkmiSystemPtes
0x140070d35  cmovnz  r14, rbx
0x140070d39  lea     edi, [r15+1]
0x140070d3d  mov     edx, edi
0x140070d3f  call    SkmiAllocateSystemPtes
0x140070d44  mov     rbx, rax
0x140070d47  or      r12d, 0FFFFFFFFh
0x140070d4b  mov     rax, gs:8
0x140070d54  test    rax, rax
0x140070d57  jz      short loc_140070D72
0x140070d59  mov     rax, [rax+90h]
0x140070d60  test    rax, rax
0x140070d63  jz      short loc_140070D72
0x140070d65  mov     rcx, qword ptr cs:xmmword_140167150
0x140070d6c  add     [rax+rcx], r12w
0x140070d71  nop
0x140070d72  lea     r13, [r14+0E8h]
0x140070d79  mov     rcx, r13
0x140070d7c  call    SkAcquirePushLockExclusive
0x140070d81  cmp     [r14+0F0h], r15
0x140070d88  jnz     loc_140070F86
0x140070d8e  test    rbx, rbx
0x140070d91  jnz     short loc_140070D9D
0x140070d93  mov     esi, 0C000009Ah
0x140070d98  jmp     loc_140070F89
0x140070d9d  mov     eax, 26h ; '&'
0x140070da2  mov     [rbp+40h+var_BF], r15b
0x140070da6  mov     [rbp+40h+var_BE], ax
0x140070daa  lea     rcx, [rbp+40h+var_C0]
0x140070dae  mov     rax, [r14+18h]
0x140070db2  mov     [rbp+40h+var_B0], rax
0x140070db6  mov     eax, cs:SkeNumberProcessors
0x140070dbc  mov     [rbp+40h+var_B8], rdi
0x140070dc0  lea     eax, [rax+rax*2]
0x140070dc3  shl     eax, 2
0x140070dc6  mov     [rbp+40h+var_A8], rax
0x140070dca  call    SkCallNormalMode
0x140070dcf  mov     esi, dword ptr [rbp+40h+var_B8]
0x140070dd2  test    esi, esi
0x140070dd4  js      loc_140070F89
0x140070dda  mov     rdx, [rbp+40h+var_B0]
0x140070dde  lea     r9, [rbp+40h+var_A8]
0x140070de2  mov     r8d, 58h ; 'X'
0x140070de8  lea     rcx, [rsp+140h+var_100]
0x140070ded  call    SkmmInitializeShortMdl
0x140070df2  mov     r15d, [rsp+140h+var_D4]
0x140070df7  lea     rax, [r15+58h]
0x140070dfb  cmp     rax, 1000h
0x140070e01  jbe     short loc_140070E2E
0x140070e03  mov     ecx, 0AE01h
0x140070e08  call    SKMI_SECURITY
0x140070e0d  xor     r15d, r15d
0x140070e10  lea     rcx, [rbp+40h+var_C0]
0x140070e14  mov     [rbp+40h+var_BF], r15b
0x140070e18  mov     [rbp+40h+var_B8], r15
0x140070e1c  lea     eax, [r15+26h]
0x140070e20  mov     [rbp+40h+var_BE], ax
0x140070e24  call    SkCallNormalMode
0x140070e29  jmp     loc_140070F89
0x140070e2e  mov     rsi, [rsp+140h+var_D0]
0x140070e33  lea     rcx, [rsp+140h+BackTraceHash]
0x140070e38  mov     r8d, edi
0x140070e3b  mov     qword ptr [rsp+140h+BackTraceHash], rsi
0x140070e40  mov     edx, edi
0x140070e42  call    SkmiClaimPhysicalPages
0x140070e47  mov     rax, 0FFFFFFFFFFh
0x140070e51  xor     r8d, r8d
0x140070e54  and     rsi, rax
0x140070e57  mov     rdx, rbx
0x140070e5a  movzx   eax, byte ptr cs:word_140156D90
0x140070e61  xor     ecx, ecx
0x140070e63  and     rax, rdi
0x140070e66  shl     rsi, 4
0x140070e6a  or      rsi, rax
0x140070e6d  mov     rax, 8000000000000063h
0x140070e77  shl     rsi, 8
0x140070e7b  or      rsi, rax
0x140070e7e  mov     rax, [rbx]
0x140070e81  mov     r9, rsi
0x140070e84  mov     [rsp+140h+var_120], rax
0x140070e89  call    SkmiGetPteTrace
0x140070e8e  xor     r8d, r8d
0x140070e91  mov     [rsp+140h+var_108], rax
0x140070e96  test    rax, rax
0x140070e99  jz      short loc_140070EFE
0x140070e9b  xor     edx, edx; Val
0x140070e9d  lea     r15, [rax+20h]
0x140070ea1  mov     rcx, r15; void *
0x140070ea4  lea     r8d, [rdx+40h]; Size
0x140070ea8  call    memset_0
0x140070ead  xor     r8d, r8d
0x140070eb0  test    cs:SkmiFlags, 400000h
0x140070eba  jz      short loc_140070EF9
0x140070ebc  mov     rcx, gs:8; FramesToSkip
0x140070ec5  test    rcx, rcx
0x140070ec8  jz      short loc_140070EF9
0x140070eca  lea     r9, [rsp+140h+BackTraceHash]; BackTraceHash
0x140070ecf  mov     r8, r15; BackTrace
0x140070ed2  mov     edx, 8; FramesToCapture
0x140070ed7  call    RtlCaptureStackBackTrace
0x140070edc  xor     r8d, r8d
0x140070edf  test    ax, ax
0x140070ee2  jnz     short loc_140070EF9
0x140070ee4  mov     rax, [rbp+48h]
0x140070ee8  mov     rcx, [rsp+140h+var_108]
0x140070eed  mov     [rcx+28h], rax
0x140070ef1  call    SkmiGetInstructionPointer
0x140070ef6  mov     [r15], rax
0x140070ef9  mov     r15d, [rsp+140h+var_D4]
0x140070efe  mov     rax, 0FFFFF6FB7DBED000h
0x140070f08  cmp     rbx, rax
0x140070f0b  jb      short loc_140070F4F
0x140070f0d  mov     rax, 0FFFFF6FB7DBED800h
0x140070f17  cmp     rbx, rax
0x140070f1a  jnb     short loc_140070F4F
0x140070f1c  mov     rax, gs:8
0x140070f25  test    rax, rax
0x140070f28  jz      short loc_140070F30
0x140070f2a  mov     rcx, [rax+50h]
0x140070f2e  jmp     short loc_140070F33
0x140070f30  mov     rcx, r8
0x140070f33  mov     rdx, [rcx+0E8h]
0x140070f3a  test    rdx, rdx
0x140070f3d  jz      short loc_140070F4F
0x140070f3f  mov     rax, rbx
0x140070f42  sar     rax, 3
0x140070f46  and     eax, 1FFh
0x140070f4b  mov     [rdx+rax*8], rsi
0x140070f4f  mov     [rbx], rsi
0x140070f52  mov     rax, [rbp+40h+var_B0]
0x140070f56  mov     [r14+0F8h], rax
0x140070f5d  shl     rbx, 19h
0x140070f61  mov     rax, 0FFFFF68000000000h
0x140070f6b  shl     rax, 19h
0x140070f6f  sub     rbx, rax
0x140070f72  sar     rbx, 10h
0x140070f76  add     rbx, r15
0x140070f79  xor     r15d, r15d
0x140070f7c  mov     [r14+0F0h], rbx
0x140070f83  mov     ebx, r15d
0x140070f86  mov     esi, r15d
0x140070f89  mov     rcx, r13
0x140070f8c  call    RtlReleaseSRWLockExclusive
0x140070f91  mov     rcx, gs:8
0x140070f9a  test    rcx, rcx
0x140070f9d  jz      short loc_140070FE4
0x140070f9f  mov     rdx, [rcx+90h]
0x140070fa6  test    rdx, rdx
0x140070fa9  jz      short loc_140070FE4
0x140070fab  nop
0x140070fac  mov     rax, qword ptr cs:xmmword_140167150
0x140070fb3  add     [rdx+rax], di
0x140070fb7  jnz     short loc_140070FE4
0x140070fb9  mov     rax, [rcx+88h]
0x140070fc0  nop
0x140070fc1  mov     rcx, qword ptr cs:xmmword_140167160
0x140070fc8  add     rax, rcx
0x140070fcb  cmp     [rdx+rcx], rax
0x140070fcf  jz      short loc_140070FE4
0x140070fd1  mov     rax, qword ptr cs:xmmword_140167150+8
0x140070fd8  cmp     [rdx+rax], r15w
0x140070fdd  jnz     short loc_140070FE4
0x140070fdf  call    SkiCheckForKernelApcDelivery
0x140070fe4  test    rbx, rbx
0x140070fe7  jz      loc_140071076
0x140070fed  sub     rbx, cs:SkmiSystemPtes
0x140070ff4  mov     rax, cs:qword_140156F78
0x140070ffb  sar     rbx, 3
0x140070fff  mov     r9d, ebx
0x140071002  and     r9d, 1Fh
0x140071006  mov     ecx, ebx
0x140071008  shr     rcx, 5
0x14007100c  mov     edx, ebx
0x14007100e  lea     r8, [rax+rcx*4]
0x140071012  lea     rax, [r9+1]
0x140071016  cmp     rax, 20h ; ' '
0x14007101a  ja      short loc_140071029
0x14007101c  mov     ecx, r9d
0x14007101f  shl     edi, cl
0x140071021  not     edi
0x140071023  lock and [r8], edi
0x140071027  jmp     short loc_140071076
0x140071029  test    r9, r9
0x14007102c  jz      short loc_14007106C
0x14007102e  and     edx, 1Fh
0x140071031  mov     eax, 20h ; ' '
0x140071036  sub     eax, edx
0x140071038  mov     ecx, eax
0x14007103a  mov     edx, eax
0x14007103c  mov     eax, edi
0x14007103e  shl     eax, cl
0x140071040  mov     rcx, r9
0x140071043  sub     eax, edi
0x140071045  shl     eax, cl
0x140071047  not     eax
0x140071049  lock and [r8], eax
0x14007104d  sub     rdi, rdx
0x140071050  add     r8, 4
0x140071054  jmp     short loc_140071061
0x140071056  mov     [r8], r15d
0x140071059  add     r8, 4
0x14007105d  sub     rdi, 20h ; ' '
0x140071061  cmp     rdi, 20h ; ' '
0x140071065  jnb     short loc_140071056
0x140071067  test    rdi, rdi
0x14007106a  jz      short loc_140071076
0x14007106c  mov     rcx, rdi
0x14007106f  shl     r12d, cl
0x140071072  lock and [r8], r12d
0x140071076  mov     eax, esi
0x140071078  mov     rcx, [rbp+40h+var_50]
0x14007107c  xor     rcx, rsp; StackCookie
0x14007107f  call    __security_check_cookie
0x140071084  add     rsp, 108h
0x14007108b  pop     r15
0x14007108d  pop     r14
0x14007108f  pop     r13
0x140071091  pop     r12
0x140071093  pop     rdi
0x140071094  pop     rsi
0x140071095  pop     rbx
0x140071096  pop     rbp
0x140071097  retn
```
