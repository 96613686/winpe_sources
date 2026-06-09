# VmsRouterDestinationProcessing

- ea: `0x14001c480`
- end: `0x14001c84a`
- name: `VmsRouterDestinationProcessing`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140030b98`

## callees

- `0x14001c480`
- `0x14001c850`
- `0x14001d100`
- `0x14001d1b8`
- `0x14001d520`
- `0x140027a64`
- `0x14008497c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001c4f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c82c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c4f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c82c`
- `NDIS!NdisAcquireRWLockRead` at `0x14001c511`
- `NDIS!NdisAcquireRWLockRead` at `0x14001c662`
- `NDIS!NdisAcquireRWLockRead` at `0x14001c511`
- `NDIS!NdisAcquireRWLockRead` at `0x14001c662`
- `NDIS!NdisReleaseRWLock` at `0x14001c5d8`
- `NDIS!NdisReleaseRWLock` at `0x14001c688`
- `NDIS!NdisReleaseRWLock` at `0x14001c5d8`
- `NDIS!NdisReleaseRWLock` at `0x14001c688`

## pseudocode

```c
_QWORD *__fastcall VmsRouterDestinationProcessing(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6,
        char a7,
        _QWORD *a8,
        _QWORD *a9)
{
  __int64 v9; // r13
  __int64 v12; // rdi
  __int64 v13; // r14
  char v14; // r12
  int v15; // edx
  UCHAR v16; // r8
  int v17; // eax
  __int64 v18; // rsi
  _QWORD *result; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  char IsFiltered; // di
  int v24; // edx
  unsigned int v25; // r9d
  char v26; // r9
  char v27; // r9
  struct _LOCK_STATE_EX v28; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+64h] [rbp-1Ch] BYREF
  __int64 v30; // [rsp+68h] [rbp-18h] BYREF
  __int64 v31; // [rsp+70h] [rbp-10h] BYREF
  __int64 *v32; // [rsp+78h] [rbp-8h] BYREF
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+38h]
  struct _LOCK_STATE_EX LockState; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v36; // [rsp+D0h] [rbp+50h]

  v36 = a3;
  LODWORD(v9) = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v12 = a3;
  *(_WORD *)&v28.OldIrql = 0;
  v13 = 0;
  v28.Flags = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a4 )
    {
      v20 = *(_QWORD *)(a4 + 288);
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 16);
        if ( v21 )
        {
          *(_DWORD *)(v21 + 184) = 2845;
          *(_QWORD *)(v21 + 176) = "VmsRouterDestinationProcessing";
          *(_QWORD *)(v21 + 168) = retaddr;
        }
      }
    }
  }
  v14 = a6;
  v32 = &v30;
  if ( (_BYTE)a6 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v15,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v16 = 1;
  }
  else
  {
    v16 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a2 + 56), &LockState, v16);
  v17 = *(_DWORD *)(a2 + 1880);
  if ( v17 == 2 )
  {
    VmsPktReportDroppedNblChain(a2, (__int16 *)a4, 0, 5, 31, -536862691);
    goto LABEL_37;
  }
  if ( *(_BYTE *)(a2 + 1884) )
  {
    VmsPktReportDroppedNblChain(a2, (__int16 *)a4, 0, 21, 15, -536862690);
LABEL_37:
    v30 = a4;
    goto LABEL_14;
  }
  if ( v17 == 1 )
  {
    v18 = *(_QWORD *)(a2 + 1984);
    v9 = *(_QWORD *)(v18 + 1240);
  }
  else
  {
    v18 = 0;
  }
  if ( (*(_DWORD *)(a4 + 300) & 0x100) == 0 )
    goto LABEL_12;
  if ( v18 )
  {
    if ( *(_DWORD *)(a2 + 1872) == 2 )
      goto LABEL_12;
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v18 + 56), &v28, 0);
    IsFiltered = VmsFltIsFiltered(v18, a4, v22, &v29);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v18 + 56), &v28);
    if ( IsFiltered == 1 )
    {
      a6 = 0;
      VmsPktGetDropReason(v29, &a6);
      VmsPktReportDroppedNblChain(a2, (__int16 *)a4, 0, a6, v27, -536862689);
      goto LABEL_35;
    }
    v12 = v36;
  }
  if ( *(_DWORD *)(a2 + 1872) != 2 )
  {
    v24 = *(_DWORD *)(a2 + 3360);
    if ( v24 )
    {
      if ( (v24 & 0x20) != 0
        || (v24 & 1) != 0 && (_WORD)a5 == *(_WORD *)(a2 + 3336) && (unsigned int)(a5 >> 16) == *(_DWORD *)(a2 + 3338)
        || (v24 & 6) != 0 && (a5 & 1) != 0
        || (v24 & 8) != 0
        && BYTE5(a5) == 0xFF
        && (_BYTE)a5 == 0xFF
        && *(_WORD *)((char *)&a5 + 1) == 0xFFFF
        && BYTE3(a5) == (_BYTE)a5
        && BYTE4(a5) == (_BYTE)a5 )
      {
        goto LABEL_12;
      }
      v25 = -536870884;
    }
    else
    {
      v25 = -536870885;
    }
    a6 = 0;
    VmsPktGetDropReason(v25, &a6);
    VmsPktReportDroppedNblChain(a2, (__int16 *)a4, 0, a6, v26, -536862688);
LABEL_35:
    v30 = a4;
    goto LABEL_14;
  }
LABEL_12:
  if ( v18 )
  {
    VmsPlcApplyPolicy(v9, a4, a1, a2, v12, v18, v14, 0, a7, (__int64)&v31, (__int64)&v32);
    v13 = v31;
  }
  else
  {
    v13 = a4;
  }
LABEL_14:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 56), &LockState);
  *a9 = v30;
  result = a8;
  *a8 = v13;
  return result;
}

```

## disassembly

```asm
0x14001c480  mov     [rsp-38h+arg_10], r8
0x14001c485  mov     [rsp-38h+arg_0], rcx
0x14001c48a  push    rbp
0x14001c48b  push    rbx
0x14001c48c  push    rdi
0x14001c48d  push    r12
0x14001c48f  push    r13
0x14001c491  push    r14
0x14001c493  push    r15
0x14001c495  mov     rbp, rsp
0x14001c498  sub     rsp, 80h
0x14001c49f  xor     eax, eax
0x14001c4a1  xor     r13d, r13d
0x14001c4a4  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001c4a8  mov     rbx, rdx
0x14001c4ab  mov     rdx, [rbp+38h]
0x14001c4af  mov     r15, r9
0x14001c4b2  mov     [rbp+LockState.Flags], al
0x14001c4b5  mov     rdi, r8
0x14001c4b8  mov     word ptr [rbp+var_20.OldIrql], ax
0x14001c4bc  mov     r14d, r13d
0x14001c4bf  mov     [rbp+var_20.Flags], al
0x14001c4c2  mov     eax, cs:VmsDiagnosticFlags
0x14001c4c8  mov     [rbp+var_10], r13
0x14001c4cc  mov     [rbp+var_18], r13
0x14001c4d0  mov     [rbp+var_1C], r13d
0x14001c4d4  test    al, 1
0x14001c4d6  jnz     loc_14001C60D
0x14001c4dc  movzx   r12d, byte ptr [rbp+arg_28]
0x14001c4e1  lea     rax, [rbp+var_18]
0x14001c4e5  mov     [rbp+var_8], rax
0x14001c4e9  test    r12b, r12b
0x14001c4ec  jz      loc_14001C727
0x14001c4f2  call    cs:__imp_KeGetCurrentIrql
0x14001c4f9  nop     dword ptr [rax+rax+00h]
0x14001c4fe  cmp     al, 2
0x14001c500  jnz     loc_14001C7FC
0x14001c506  mov     r8b, 1; Flags
0x14001c509  mov     rcx, [rbx+38h]; Lock
0x14001c50d  lea     rdx, [rbp+LockState]; LockState
0x14001c511  call    cs:__imp_NdisAcquireRWLockRead
0x14001c518  nop     dword ptr [rax+rax+00h]
0x14001c51d  mov     eax, [rbx+758h]
0x14001c523  cmp     eax, 2
0x14001c526  jz      loc_14001C798
0x14001c52c  cmp     [rbx+75Ch], r13b
0x14001c533  jnz     loc_14001C76B
0x14001c539  mov     [rsp+80h+arg_18], rsi
0x14001c541  cmp     eax, 1
0x14001c544  jnz     loc_14001C7F4
0x14001c54a  mov     rsi, [rbx+7C0h]
0x14001c551  mov     r13, [rsi+4D8h]
0x14001c558  test    dword ptr [r15+12Ch], 100h
0x14001c563  jz      short loc_14001C57B
0x14001c565  test    rsi, rsi
0x14001c568  jz      loc_14001C6A2
0x14001c56e  cmp     dword ptr [rbx+750h], 2
0x14001c575  jnz     loc_14001C657
0x14001c57b  test    rsi, rsi
0x14001c57e  jz      loc_14001C7EC
0x14001c584  mov     r8, [rbp+arg_0]
0x14001c588  lea     rax, [rbp+var_8]
0x14001c58c  mov     [rsp+80h+var_30], rax
0x14001c591  mov     r9, rbx
0x14001c594  lea     rax, [rbp+var_10]
0x14001c598  mov     rdx, r15
0x14001c59b  mov     [rsp+80h+var_38], rax
0x14001c5a0  mov     rcx, r13
0x14001c5a3  movzx   eax, [rbp+arg_30]
0x14001c5a7  mov     [rsp+80h+var_40], al
0x14001c5ab  mov     [rsp+80h+var_48], r14b
0x14001c5b0  mov     [rsp+80h+var_50], r12b
0x14001c5b5  mov     [rsp+80h+var_58], rsi
0x14001c5ba  mov     [rsp+80h+var_60], rdi
0x14001c5bf  call    VmsPlcApplyPolicy
0x14001c5c4  mov     r14, [rbp+var_10]
0x14001c5c8  mov     rsi, [rsp+80h+arg_18]
0x14001c5d0  mov     rcx, [rbx+38h]; Lock
0x14001c5d4  lea     rdx, [rbp+LockState]; LockState
0x14001c5d8  call    cs:__imp_NdisReleaseRWLock
0x14001c5df  nop     dword ptr [rax+rax+00h]
0x14001c5e4  mov     rax, [rbp+var_18]
0x14001c5e8  mov     rcx, [rbp+arg_40]
0x14001c5ef  mov     [rcx], rax
0x14001c5f2  mov     rax, [rbp+arg_38]
0x14001c5f6  mov     [rax], r14
0x14001c5f9  add     rsp, 80h
0x14001c600  pop     r15
0x14001c602  pop     r14
0x14001c604  pop     r13
0x14001c606  pop     r12
0x14001c608  pop     rdi
0x14001c609  pop     rbx
0x14001c60a  pop     rbp
0x14001c60b  retn
0x14001c60d  test    r15, r15
0x14001c610  jz      loc_14001C4DC
0x14001c616  mov     rax, [r9+120h]
0x14001c61d  test    rax, rax
0x14001c620  jz      loc_14001C4DC
0x14001c626  mov     rax, [rax+10h]
0x14001c62a  test    rax, rax
0x14001c62d  jz      loc_14001C4DC
0x14001c633  lea     rcx, aVmsrouterdesti; "VmsRouterDestinationProcessing"
0x14001c63a  mov     dword ptr [rax+0B8h], 0B1Dh
0x14001c644  mov     [rax+0B0h], rcx
0x14001c64b  mov     [rax+0A8h], rdx
0x14001c652  jmp     loc_14001C4DC
0x14001c657  mov     rcx, [rsi+38h]; Lock
0x14001c65b  lea     rdx, [rbp+var_20]; LockState
0x14001c65f  xor     r8d, r8d; Flags
0x14001c662  call    cs:__imp_NdisAcquireRWLockRead
0x14001c669  nop     dword ptr [rax+rax+00h]
0x14001c66e  lea     r9, [rbp+var_1C]
0x14001c672  mov     rdx, r15
0x14001c675  mov     rcx, rsi
0x14001c678  call    VmsFltIsFiltered
0x14001c67d  mov     rcx, [rsi+38h]; Lock
0x14001c681  lea     rdx, [rbp+var_20]; LockState
0x14001c685  movzx   edi, al
0x14001c688  call    cs:__imp_NdisReleaseRWLock
0x14001c68f  nop     dword ptr [rax+rax+00h]
0x14001c694  cmp     dil, 1
0x14001c698  jz      loc_14001C72F
0x14001c69e  mov     rdi, [rbp+arg_10]
0x14001c6a2  cmp     dword ptr [rbx+750h], 2
0x14001c6a9  jz      loc_14001C57B
0x14001c6af  mov     edx, [rbx+0D20h]
0x14001c6b5  test    edx, edx
0x14001c6b7  jz      loc_14001C7B0
0x14001c6bd  test    dl, 20h
0x14001c6c0  jnz     loc_14001C57B
0x14001c6c6  mov     rax, [rbp+arg_20]
0x14001c6ca  test    dl, 1
0x14001c6cd  jz      short loc_14001C6EB
0x14001c6cf  cmp     ax, [rbx+0D08h]
0x14001c6d6  jnz     short loc_14001C6EB
0x14001c6d8  mov     rcx, rax
0x14001c6db  shr     rcx, 10h
0x14001c6df  cmp     ecx, [rbx+0D0Ah]
0x14001c6e5  jz      loc_14001C57B
0x14001c6eb  test    dl, 6
0x14001c6ee  jz      short loc_14001C6F8
0x14001c6f0  test    al, 1
0x14001c6f2  jnz     loc_14001C57B
0x14001c6f8  test    dl, 8
0x14001c6fb  jz      short loc_14001C707
0x14001c6fd  cmp     byte ptr [rbp+arg_20+5], 0FFh
0x14001c701  jz      loc_14001C7BB
0x14001c707  mov     r9d, 0E000001Ch
0x14001c70d  lea     rdx, [rbp+arg_28]
0x14001c711  mov     [rbp+arg_28], r14d
0x14001c715  mov     ecx, r9d
0x14001c718  call    VmsPktGetDropReason
0x14001c71d  mov     dword ptr [rsp+80h+var_58], 0E0002020h
0x14001c725  jmp     short loc_14001C74B
0x14001c727  xor     r8d, r8d
0x14001c72a  jmp     loc_14001C509
0x14001c72f  mov     r9d, [rbp+var_1C]
0x14001c733  lea     rdx, [rbp+arg_28]
0x14001c737  mov     ecx, r9d
0x14001c73a  mov     [rbp+arg_28], r14d
0x14001c73e  call    VmsPktGetDropReason
0x14001c743  mov     dword ptr [rsp+80h+var_58], 0E000201Fh
0x14001c74b  mov     dword ptr [rsp+80h+var_60], r9d
0x14001c750  xor     r8d, r8d
0x14001c753  mov     r9d, [rbp+arg_28]
0x14001c757  mov     rdx, r15
0x14001c75a  mov     rcx, rbx
0x14001c75d  call    VmsPktReportDroppedNblChain
0x14001c762  mov     [rbp+var_18], r15
0x14001c766  jmp     loc_14001C5C8
0x14001c76b  mov     dword ptr [rsp+80h+var_58], 0E000201Eh
0x14001c773  mov     r9d, 15h
0x14001c779  mov     dword ptr [rsp+80h+var_60], 0E000000Fh
0x14001c781  xor     r8d, r8d
0x14001c784  mov     rdx, r15
0x14001c787  mov     rcx, rbx
0x14001c78a  call    VmsPktReportDroppedNblChain
0x14001c78f  mov     [rbp+var_18], r15
0x14001c793  jmp     loc_14001C5D0
0x14001c798  mov     dword ptr [rsp+80h+var_58], 0E000201Dh
0x14001c7a0  mov     r9d, 5
0x14001c7a6  mov     dword ptr [rsp+80h+var_60], 0C023001Fh
0x14001c7ae  jmp     short loc_14001C781
0x14001c7b0  mov     r9d, 0E000001Bh
0x14001c7b6  jmp     loc_14001C70D
0x14001c7bb  cmp     al, 0FFh
0x14001c7bd  jnz     loc_14001C707
0x14001c7c3  cmp     byte ptr [rbp+arg_20+1], al
0x14001c7c6  jnz     loc_14001C707
0x14001c7cc  cmp     byte ptr [rbp+arg_20+2], al
0x14001c7cf  jnz     loc_14001C707
0x14001c7d5  cmp     byte ptr [rbp+arg_20+3], al
0x14001c7d8  jnz     loc_14001C707
0x14001c7de  cmp     byte ptr [rbp+arg_20+4], al
0x14001c7e1  jnz     loc_14001C707
0x14001c7e7  jmp     loc_14001C57B
0x14001c7ec  mov     r14, r15
0x14001c7ef  jmp     loc_14001C5C8
0x14001c7f4  mov     rsi, r13
0x14001c7f7  jmp     loc_14001C558
0x14001c7fc  mov     rcx, cs:VmsIfrLog
0x14001c803  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001c80a  mov     [rsp+80h+var_58], rax
0x14001c80f  mov     r9d, 18h
0x14001c815  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001c81c  mov     r8d, 13h
0x14001c822  mov     [rsp+80h+var_60], rax
0x14001c827  call    WPP_RECORDER_SF_s
0x14001c82c  call    cs:__imp_KeGetCurrentIrql
0x14001c833  nop     dword ptr [rax+rax+00h]
0x14001c838  cmp     al, 2
0x14001c83a  jz      loc_14001C506
0x14001c840  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001c845  jmp     loc_14001C506
```
