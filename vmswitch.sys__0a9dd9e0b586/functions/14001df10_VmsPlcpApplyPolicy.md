# VmsPlcpApplyPolicy

- ea: `0x14001df10`
- end: `0x14001e591`
- name: `VmsPlcpApplyPolicy`
- size: `1665`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001d6d8`

## callees

- `0x14001df10`
- `0x140027a64`
- `0x14008497c`
- `0x140115794`
- `0x14015442c`
- `0x140157828`
- `0x14018b454`
- `0x14018bdf8`
- `0x14018e834`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001e009`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e0f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e394`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e3f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e009`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e0f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e394`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e3f7`
- `NDIS!NdisAcquireRWLockRead` at `0x14001e029`
- `NDIS!NdisAcquireRWLockRead` at `0x14001e110`
- `NDIS!NdisAcquireRWLockRead` at `0x14001e029`
- `NDIS!NdisAcquireRWLockRead` at `0x14001e110`
- `NDIS!NdisReleaseRWLock` at `0x14001dfae`
- `NDIS!NdisReleaseRWLock` at `0x14001dfae`

## pseudocode

```c
__int64 __fastcall VmsPlcpApplyPolicy(
        __int64 a1,
        __int16 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        unsigned __int8 a6,
        _DWORD *a7)
{
  unsigned int v11; // r14d
  char v12; // di
  __int64 result; // rax
  int v14; // edx
  UCHAR v15; // r8
  bool v16; // zf
  int v17; // edx
  UCHAR v18; // r8
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  __int16 v22; // r8
  int v23; // edx
  __int16 v24; // ax
  char v25; // al
  __int64 v26; // r9
  __int16 v27; // ax
  __int16 v28; // ax
  char v29; // al
  _WORD *v30; // rax
  __int64 v31; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-30h] BYREF
  int v33; // [rsp+54h] [rbp-2Ch]
  __int64 v34; // [rsp+60h] [rbp-20h] BYREF
  __int64 v35; // [rsp+68h] [rbp-18h] BYREF
  __int64 v36; // [rsp+70h] [rbp-10h] BYREF
  __int64 v37; // [rsp+78h] [rbp-8h] BYREF

  v34 = 0;
  v11 = 1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( !a6 )
  {
    v12 = 0;
    goto LABEL_3;
  }
  if ( (a2 & 1) != 0 && !*(_BYTE *)(a3 + 3956) )
  {
    v21 = *(_QWORD *)(a1 + 8);
    v22 = *(_WORD *)(a3 + 3336);
    if ( *(_WORD *)(v21 + 6) == v22 )
    {
      v23 = *(_DWORD *)(a3 + 3338);
      if ( *(_DWORD *)(v21 + 8) == v23 )
      {
        v24 = *(_WORD *)(a1 + 18);
        if ( v24 == 2054 )
        {
          v26 = a1 + 58;
          if ( !*(_BYTE *)(a1 + 80) )
            v26 = 0;
        }
        else
        {
          if ( v24 != -31011 || *(_BYTE *)(a1 + 64) != 58 || *(_BYTE *)(a1 + 66) )
            goto LABEL_16;
          v25 = *(_BYTE *)(a1 + 72);
          if ( v25 == -120 )
          {
            v26 = a1 + 105;
            if ( !*(_BYTE *)(a1 + 104) )
              v26 = 0;
          }
          else
          {
            if ( v25 != -121 || !*(_BYTE *)(a1 + 104) )
              goto LABEL_16;
            v26 = a1 + 105;
          }
        }
        if ( !v26 || *(_WORD *)v26 == v22 && *(_DWORD *)(v26 + 2) == v23 )
          goto LABEL_16;
      }
    }
    v11 = 2;
    *a7 = -536870903;
    return v11;
  }
LABEL_16:
  if ( (a2 & 2) != 0 )
  {
    v27 = *(_WORD *)(a1 + 18);
    if ( v27 == 2048 )
    {
      if ( *(_BYTE *)(a1 + 60) == 17 && *(_BYTE *)(a1 + 72) && *(_BYTE *)(a1 + 81) )
      {
        v11 = 2;
        *a7 = -536870902;
        return v11;
      }
    }
    else if ( v27 == -31011 && *(_BYTE *)(a1 + 64) == 17 && *(_BYTE *)(a1 + 72) && *(_BYTE *)(a1 + 81) )
    {
      v11 = 2;
      *a7 = -536870902;
      return v11;
    }
  }
  if ( (a2 & 0x10) == 0 )
    goto LABEL_18;
  v28 = *(_WORD *)(a1 + 18);
  if ( v28 == 2048 )
  {
    if ( *(_BYTE *)(a1 + 60) == 1 && !*(_BYTE *)(a1 + 65) && ((*(_BYTE *)(a1 + 72) - 5) & 0xFB) == 0 )
    {
      v11 = 2;
      *a7 = -536870901;
      return v11;
    }
    goto LABEL_18;
  }
  if ( v28 != -31011
    || *(_BYTE *)(a1 + 64) != 58
    || *(_BYTE *)(a1 + 66)
    || (v29 = *(_BYTE *)(a1 + 72), v29 != -122) && v29 != -119 )
  {
LABEL_18:
    if ( a5 )
    {
      if ( KeGetCurrentIrql() != 2 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v14,
          19,
          24,
          (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
          (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
        if ( KeGetCurrentIrql() != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v15 = 1;
    }
    else
    {
      v15 = 0;
    }
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a4 + 56), &LockState, v15);
    if ( *(_DWORD *)(a4 + 68) == 2 )
      goto LABEL_30;
    v12 = 1;
    if ( (a2 & 4) != 0 )
    {
      v11 = VmsPktCheckForIpSpoofing(a1, *(_QWORD *)(a4 + 5880), *(_QWORD *)(a4 + 5888));
      if ( v11 == 2 )
      {
        v16 = *(_BYTE *)(a4 + 9384) == 0;
        *a7 = -536870906;
        if ( v16 )
        {
          VmsEtwTraceIPSpoofPktDrop(
            *(_QWORD *)(a4 + 1240) + 616,
            *(_QWORD *)(a1 + 32),
            a4 + 72,
            a3 + 2112,
            a3 + 72,
            a3 + 616,
            a4 + 72,
            a4 + 616,
            *(_QWORD *)(a4 + 1240) + 72LL,
            *(_QWORD *)(a4 + 1240) + 616LL);
          *(_BYTE *)(a4 + 9384) = 1;
        }
        goto LABEL_12;
      }
    }
LABEL_3:
    if ( (a2 & 0x80u) != 0 )
    {
      v19 = *(_QWORD *)(a1 + 8);
      v33 = 12746753;
      v20 = *(_DWORD *)v19 - 12746753;
      if ( *(_DWORD *)v19 == 12746753 )
        v20 = *(unsigned __int8 *)(v19 + 4);
      v11 = 1;
      if ( !v20
        && *(_BYTE *)(v19 + 5) < 0x10u
        && (!Vms8021xEnabled || *(_WORD *)(a1 + 18) != 0x888E)
        && (!Vms8021ABEnabled || *(_WORD *)(a1 + 18) != 0x88CC) )
      {
        v11 = 2;
        *a7 = -536870900;
        goto LABEL_11;
      }
    }
    if ( v12 )
      goto LABEL_101;
    if ( a5 )
    {
      if ( KeGetCurrentIrql() != 2 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v17,
          19,
          24,
          (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
          (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
        if ( KeGetCurrentIrql() != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v18 = 1;
    }
    else
    {
      v18 = 0;
    }
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a4 + 56), &LockState, v18);
    v12 = 1;
    if ( *(_DWORD *)(a4 + 68) != 2 )
    {
LABEL_101:
      if ( (a2 & 8) != 0
        && (v11 = VmsScApplyPortAcl(a1, a4, a6, (unsigned int)&v34, (__int64)&v36, (__int64)&v37), v11 == 2) )
      {
        *a7 = -536870906;
        if ( VmsEtwTraceDatapath && v34 != -2 )
        {
          v30 = (_WORD *)(v34 + 2);
          v31 = 64;
          do
          {
            if ( !*v30 )
              break;
            ++v30;
            --v31;
          }
          while ( v31 );
          if ( v31 )
            VmsEtwTracePortAclPktDrop(
              *(_QWORD *)(a4 + 1240) + 616,
              *(_QWORD *)(a1 + 32),
              64 - v31,
              a4 + 72,
              a4 + 616,
              *(_QWORD *)(a4 + 1240) + 72LL,
              *(_QWORD *)(a4 + 1240) + 616LL,
              64 - v31,
              v34 + 2);
        }
      }
      else if ( (a2 & 0x100) != 0 && (v11 = VmsScExtendedPortAclApply(a1, a4, a6, &v35), v11 == 2) )
      {
        *a7 = -536870906;
        if ( VmsEtwTraceDatapath )
          VmsEtwTraceExtendedPortAclPktDrop(
            *(_QWORD *)(a4 + 1240) + 72,
            *(_QWORD *)(a1 + 32),
            *(unsigned __int8 *)(v35 + 164),
            a4 + 72,
            a4 + 616,
            *(_QWORD *)(a4 + 1240) + 72LL,
            *(_QWORD *)(a4 + 1240) + 616LL,
            *(_BYTE *)(v35 + 164),
            *(_WORD *)(v35 + 460));
      }
      else
      {
        if ( v36 )
          _InterlockedAdd64((volatile signed __int64 *)(v36 + 208), *(unsigned int *)(a1 + 20));
        if ( v37 )
          _InterlockedAdd64((volatile signed __int64 *)(v37 + 208), *(unsigned int *)(a1 + 20));
      }
LABEL_11:
      if ( !v12 )
        return v11;
LABEL_12:
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a4 + 56), &LockState);
      return v11;
    }
LABEL_30:
    v11 = 2;
    goto LABEL_12;
  }
  result = 2;
  *a7 = -536870901;
  return result;
}

```

## disassembly

```asm
0x14001df10  push    rbp
0x14001df12  push    rbx
0x14001df13  push    rsi
0x14001df14  push    rdi
0x14001df15  push    r13
0x14001df17  push    r14
0x14001df19  push    r15
0x14001df1b  mov     rbp, rsp
0x14001df1e  sub     rsp, 80h
0x14001df25  xor     r10d, r10d
0x14001df28  lea     rdi, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001df2f  xor     eax, eax
0x14001df31  mov     [rbp+var_20], r10
0x14001df35  mov     rsi, r9
0x14001df38  mov     r15, r8
0x14001df3b  mov     rbx, rdx
0x14001df3e  mov     r13, rcx
0x14001df41  mov     r14d, 1
0x14001df47  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001df4b  mov     [rbp+LockState.Flags], al
0x14001df4e  mov     [rbp+var_18], r10
0x14001df52  mov     [rbp+var_10], r10
0x14001df56  mov     [rbp+var_8], r10
0x14001df5a  cmp     [rbp+arg_28], al
0x14001df5d  jnz     short loc_14001DFD0
0x14001df5f  xor     dil, dil
0x14001df62  test    bl, bl
0x14001df64  js      loc_14001E13C
0x14001df6a  test    dil, dil
0x14001df6d  jz      loc_14001E0E7
0x14001df73  test    bl, 8
0x14001df76  jnz     loc_14001E415
0x14001df7c  bt      rbx, 8
0x14001df81  jb      loc_14001E4E0
0x14001df87  mov     rcx, [rbp+var_10]
0x14001df8b  test    rcx, rcx
0x14001df8e  jnz     loc_14001E56F
0x14001df94  mov     rcx, [rbp+var_8]
0x14001df98  test    rcx, rcx
0x14001df9b  jnz     loc_14001E580
0x14001dfa1  test    dil, dil
0x14001dfa4  jz      short loc_14001DFBA
0x14001dfa6  mov     rcx, [rsi+38h]; Lock
0x14001dfaa  lea     rdx, [rbp+LockState]; LockState
0x14001dfae  call    cs:__imp_NdisReleaseRWLock
0x14001dfb5  nop     dword ptr [rax+rax+00h]
0x14001dfba  mov     eax, r14d
0x14001dfbd  add     rsp, 80h
0x14001dfc4  pop     r15
0x14001dfc6  pop     r14
0x14001dfc8  pop     r13
0x14001dfca  pop     rdi
0x14001dfcb  pop     rsi
0x14001dfcc  pop     rbx
0x14001dfcd  pop     rbp
0x14001dfce  retn
0x14001dfd0  mov     r11d, 86DDh
0x14001dfd6  test    r14b, bl
0x14001dfd9  jz      short loc_14001DFE8
0x14001dfdb  cmp     [r8+0F74h], al
0x14001dfe2  jz      loc_14001E1B3
0x14001dfe8  mov     ecx, 800h
0x14001dfed  test    bl, 2
0x14001dff0  jnz     loc_14001E269
0x14001dff6  test    bl, 10h
0x14001dff9  jnz     loc_14001E2E5
0x14001dfff  cmp     [rbp+arg_20], r10b
0x14001e003  jz      loc_14001E134
0x14001e009  call    cs:__imp_KeGetCurrentIrql
0x14001e010  nop     dword ptr [rax+rax+00h]
0x14001e015  cmp     al, 2
0x14001e017  jnz     loc_14001E36B
0x14001e01d  movzx   r8d, r14b; Flags
0x14001e021  mov     rcx, [rsi+38h]; Lock
0x14001e025  lea     rdx, [rbp+LockState]; LockState
0x14001e029  call    cs:__imp_NdisAcquireRWLockRead
0x14001e030  nop     dword ptr [rax+rax+00h]
0x14001e035  cmp     dword ptr [rsi+44h], 2
0x14001e039  jz      loc_14001E129
0x14001e03f  movzx   edi, r14b
0x14001e043  test    bl, 4
0x14001e046  jz      loc_14001DF62
0x14001e04c  mov     r8, [rsi+1700h]
0x14001e053  mov     rcx, r13
0x14001e056  mov     rdx, [rsi+16F8h]
0x14001e05d  call    VmsPktCheckForIpSpoofing
0x14001e062  mov     r14d, eax
0x14001e065  cmp     eax, 2
0x14001e068  jnz     loc_14001DF62
0x14001e06e  cmp     byte ptr [rsi+24A8h], 0
0x14001e075  mov     rax, [rbp+arg_30]
0x14001e079  mov     dword ptr [rax], 0E0000006h
0x14001e07f  jnz     loc_14001DFA6
0x14001e085  mov     rax, [rsi+4D8h]
0x14001e08c  lea     rdx, [rsi+268h]
0x14001e093  lea     r8, [rsi+48h]
0x14001e097  lea     r10, [r15+268h]
0x14001e09e  lea     r11, [r15+48h]
0x14001e0a2  lea     rcx, [rax+268h]
0x14001e0a9  add     rax, 48h ; 'H'
0x14001e0ad  mov     [rsp+80h+var_38], rcx
0x14001e0b2  lea     r9, [r15+840h]
0x14001e0b9  mov     [rsp+80h+var_40], rax
0x14001e0be  mov     [rsp+80h+var_48], rdx
0x14001e0c3  mov     rdx, [r13+20h]
0x14001e0c7  mov     [rsp+80h+var_50], r8
0x14001e0cc  mov     [rsp+80h+var_58], r10
0x14001e0d1  mov     [rsp+80h+var_60], r11
0x14001e0d6  call    VmsEtwTraceIPSpoofPktDrop
0x14001e0db  mov     [rsi+24A8h], dil
0x14001e0e2  jmp     loc_14001DFA6
0x14001e0e7  cmp     [rbp+arg_20], 0
0x14001e0eb  jz      loc_14001E1AB
0x14001e0f1  call    cs:__imp_KeGetCurrentIrql
0x14001e0f8  nop     dword ptr [rax+rax+00h]
0x14001e0fd  cmp     al, 2
0x14001e0ff  jnz     loc_14001E3C7
0x14001e105  mov     r8b, 1; Flags
0x14001e108  mov     rcx, [rsi+38h]; Lock
0x14001e10c  lea     rdx, [rbp+LockState]; LockState
0x14001e110  call    cs:__imp_NdisAcquireRWLockRead
0x14001e117  nop     dword ptr [rax+rax+00h]
0x14001e11c  cmp     dword ptr [rsi+44h], 2
0x14001e120  mov     dil, 1
0x14001e123  jnz     loc_14001DF73
0x14001e129  mov     r14d, 2
0x14001e12f  jmp     loc_14001DFA6
0x14001e134  xor     r8d, r8d
0x14001e137  jmp     loc_14001E021
0x14001e13c  mov     rdx, [r13+8]
0x14001e140  xor     al, al
0x14001e142  mov     [rbp+var_2C], 0C28001h
0x14001e149  mov     ecx, [rdx]
0x14001e14b  sub     ecx, [rbp+var_2C]
0x14001e14e  jnz     short loc_14001E159
0x14001e150  movzx   ecx, byte ptr [rdx+4]
0x14001e154  movzx   eax, al
0x14001e157  sub     ecx, eax
0x14001e159  mov     r14d, 1
0x14001e15f  test    ecx, ecx
0x14001e161  jnz     loc_14001DF6A
0x14001e167  cmp     byte ptr [rdx+5], 10h
0x14001e16b  jnb     loc_14001DF6A
0x14001e171  cmp     cs:Vms8021xEnabled, cl
0x14001e177  jz      short loc_14001E189
0x14001e179  mov     eax, 888Eh
0x14001e17e  cmp     [r13+12h], ax
0x14001e183  jz      loc_14001DF6A
0x14001e189  cmp     cs:Vms8021ABEnabled, 0
0x14001e190  jnz     loc_14001E3B2
0x14001e196  mov     rax, [rbp+arg_30]
0x14001e19a  mov     r14d, 2
0x14001e1a0  mov     dword ptr [rax], 0E000000Ch
0x14001e1a6  jmp     loc_14001DFA1
0x14001e1ab  xor     r8d, r8d
0x14001e1ae  jmp     loc_14001E108
0x14001e1b3  mov     rax, [rcx+8]
0x14001e1b7  movzx   r8d, word ptr [r8+0D08h]
0x14001e1bf  cmp     [rax+6], r8w
0x14001e1c4  jnz     short loc_14001E1D2
0x14001e1c6  mov     edx, [r15+0D0Ah]
0x14001e1cd  cmp     [rax+8], edx
0x14001e1d0  jz      short loc_14001E1E7
0x14001e1d2  mov     rax, [rbp+arg_30]
0x14001e1d6  mov     r14d, 2
0x14001e1dc  mov     dword ptr [rax], 0E0000009h
0x14001e1e2  jmp     loc_14001DFBA
0x14001e1e7  movzx   eax, word ptr [rcx+12h]
0x14001e1eb  mov     ecx, 806h
0x14001e1f0  cmp     ax, cx
0x14001e1f3  jz      short loc_14001E22B
0x14001e1f5  cmp     ax, r11w
0x14001e1f9  jnz     loc_14001DFE8
0x14001e1ff  cmp     byte ptr [r13+40h], 3Ah ; ':'
0x14001e204  jnz     loc_14001DFE8
0x14001e20a  cmp     [r13+42h], r10b
0x14001e20e  jnz     loc_14001DFE8
0x14001e214  movzx   eax, byte ptr [r13+48h]
0x14001e219  cmp     al, 88h
0x14001e21b  jnz     short loc_14001E251
0x14001e21d  cmp     [r13+68h], r10b
0x14001e221  lea     r9, [r13+69h]
0x14001e225  cmovz   r9, r10
0x14001e229  jmp     short loc_14001E237
0x14001e22b  cmp     [r13+50h], r10b
0x14001e22f  lea     r9, [r13+3Ah]
0x14001e233  cmovz   r9, r10
0x14001e237  test    r9, r9
0x14001e23a  jz      loc_14001DFE8
0x14001e240  cmp     [r9], r8w
0x14001e244  jnz     short loc_14001E1D2
0x14001e246  cmp     [r9+2], edx
0x14001e24a  jnz     short loc_14001E1D2
0x14001e24c  jmp     loc_14001DFE8
0x14001e251  cmp     al, 87h
0x14001e253  jnz     loc_14001DFE8
0x14001e259  cmp     [r13+68h], r10b
0x14001e25d  jz      loc_14001DFE8
0x14001e263  lea     r9, [r13+69h]
0x14001e267  jmp     short loc_14001E237
0x14001e269  movzx   eax, word ptr [r13+12h]
0x14001e26e  cmp     ax, cx
0x14001e271  jnz     short loc_14001E2A7
0x14001e273  cmp     byte ptr [r13+3Ch], 11h
0x14001e278  jnz     loc_14001DFF6
0x14001e27e  cmp     [r13+48h], r10b
0x14001e282  jz      loc_14001DFF6
0x14001e288  cmp     [r13+51h], r10b
0x14001e28c  jz      loc_14001DFF6
0x14001e292  mov     rax, [rbp+arg_30]
0x14001e296  mov     r14d, 2
0x14001e29c  mov     dword ptr [rax], 0E000000Ah
0x14001e2a2  jmp     loc_14001DFBA
0x14001e2a7  cmp     ax, r11w
0x14001e2ab  jnz     loc_14001DFF6
0x14001e2b1  cmp     byte ptr [r13+40h], 11h
0x14001e2b6  jnz     loc_14001DFF6
0x14001e2bc  cmp     [r13+48h], r10b
0x14001e2c0  jz      loc_14001DFF6
0x14001e2c6  cmp     [r13+51h], r10b
0x14001e2ca  jz      loc_14001DFF6
0x14001e2d0  mov     rax, [rbp+arg_30]
0x14001e2d4  mov     r14d, 2
0x14001e2da  mov     dword ptr [rax], 0E000000Ah
0x14001e2e0  jmp     loc_14001DFBA
0x14001e2e5  movzx   eax, word ptr [r13+12h]
0x14001e2ea  cmp     ax, cx
0x14001e2ed  jnz     short loc_14001E327
0x14001e2ef  cmp     [r13+3Ch], r14b
0x14001e2f3  jnz     loc_14001DFFF
0x14001e2f9  cmp     [r13+41h], r10b
0x14001e2fd  jnz     loc_14001DFFF
0x14001e303  movzx   eax, byte ptr [r13+48h]
0x14001e308  sub     al, 5
0x14001e30a  test    al, 0FBh
0x14001e30c  jnz     loc_14001DFFF
0x14001e312  mov     rax, [rbp+arg_30]
0x14001e316  mov     r14d, 2
0x14001e31c  mov     dword ptr [rax], 0E000000Bh
0x14001e322  jmp     loc_14001DFBA
0x14001e327  cmp     ax, r11w
0x14001e32b  jnz     loc_14001DFFF
0x14001e331  cmp     byte ptr [r13+40h], 3Ah ; ':'
0x14001e336  jnz     loc_14001DFFF
0x14001e33c  cmp     [r13+42h], r10b
0x14001e340  jnz     loc_14001DFFF
0x14001e346  movzx   eax, byte ptr [r13+48h]
0x14001e34b  cmp     al, 86h
0x14001e34d  jz      short loc_14001E357
0x14001e34f  cmp     al, 89h
0x14001e351  jnz     loc_14001DFFF
0x14001e357  mov     rcx, [rbp+arg_30]
0x14001e35b  mov     eax, 2
0x14001e360  mov     dword ptr [rcx], 0E000000Bh
0x14001e366  jmp     loc_14001DFBD
0x14001e36b  mov     rcx, cs:VmsIfrLog
0x14001e372  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001e379  mov     r9d, 18h
0x14001e37f  mov     [rsp+80h+var_58], rdi
0x14001e384  mov     r8d, 13h
0x14001e38a  mov     [rsp+80h+var_60], rax
0x14001e38f  call    WPP_RECORDER_SF_s
0x14001e394  call    cs:__imp_KeGetCurrentIrql
0x14001e39b  nop     dword ptr [rax+rax+00h]
0x14001e3a0  cmp     al, 2
0x14001e3a2  jz      loc_14001E01D
0x14001e3a8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001e3ad  jmp     loc_14001E01D
0x14001e3b2  mov     eax, 88CCh
0x14001e3b7  cmp     [r13+12h], ax
0x14001e3bc  jz      loc_14001DF6A
0x14001e3c2  jmp     loc_14001E196
0x14001e3c7  mov     rcx, cs:VmsIfrLog
0x14001e3ce  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001e3d5  mov     [rsp+80h+var_58], rax
0x14001e3da  mov     r9d, 18h
0x14001e3e0  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001e3e7  mov     r8d, 13h
0x14001e3ed  mov     [rsp+80h+var_60], rax
0x14001e3f2  call    WPP_RECORDER_SF_s
0x14001e3f7  call    cs:__imp_KeGetCurrentIrql
0x14001e3fe  nop     dword ptr [rax+rax+00h]
0x14001e403  cmp     al, 2
0x14001e405  jz      loc_14001E105
0x14001e40b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001e410  jmp     loc_14001E105
0x14001e415  movzx   r8d, [rbp+arg_28]
0x14001e41a  lea     rax, [rbp+var_8]
0x14001e41e  mov     [rsp+80h+var_58], rax
0x14001e423  lea     r9, [rbp+var_20]
0x14001e427  lea     rax, [rbp+var_10]
0x14001e42b  mov     rdx, rsi
0x14001e42e  mov     rcx, r13
0x14001e431  mov     [rsp+80h+var_60], rax
0x14001e436  call    VmsScApplyPortAcl
0x14001e43b  mov     r14d, eax
0x14001e43e  cmp     eax, 2
0x14001e441  jnz     loc_14001DF7C
0x14001e447  mov     rax, [rbp+arg_30]
0x14001e44b  mov     dword ptr [rax], 0E0000006h
  ... truncated ...
```
