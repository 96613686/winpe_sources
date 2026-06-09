# VmsCdpCopyNicInfo

- ea: `0x140054644`
- end: `0x140054a18`
- name: `VmsCdpCopyNicInfo`
- size: `980`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003985c`
- `0x14005407c`

## callees

- `0x140027a64`
- `0x140054644`
- `0x14008497c`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005488a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400548c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140054924`
- `ntoskrnl!KeGetCurrentIrql` at `0x140054954`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005488a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400548c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140054924`
- `ntoskrnl!KeGetCurrentIrql` at `0x140054954`
- `NDIS!NdisAcquireRWLockRead` at `0x14005468f`
- `NDIS!NdisAcquireRWLockRead` at `0x1400548e8`
- `NDIS!NdisAcquireRWLockRead` at `0x140054974`
- `NDIS!NdisAcquireRWLockRead` at `0x14005468f`
- `NDIS!NdisAcquireRWLockRead` at `0x1400548e8`
- `NDIS!NdisAcquireRWLockRead` at `0x140054974`
- `NDIS!NdisReleaseRWLock` at `0x1400549c4`
- `NDIS!NdisReleaseRWLock` at `0x1400549e6`
- `NDIS!NdisReleaseRWLock` at `0x1400549fa`
- `NDIS!NdisReleaseRWLock` at `0x1400549c4`
- `NDIS!NdisReleaseRWLock` at `0x1400549e6`
- `NDIS!NdisReleaseRWLock` at `0x1400549fa`

## pseudocode

```c
void __fastcall VmsCdpCopyNicInfo(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  size_t v11; // r8
  const void *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rsi
  int v15; // edx
  __int64 v16; // rsi
  int v17; // edx
  struct _LOCK_STATE_EX v18; // [rsp+60h] [rbp+30h] BYREF
  struct _LOCK_STATE_EX v19; // [rsp+68h] [rbp+38h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+40h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v19.OldIrql = 0;
  v19.Flags = 0;
  *(_WORD *)&v18.OldIrql = 0;
  v18.Flags = 0;
  memset((void *)a2, 0, 0xA34u);
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, 0);
  memmove((void *)a2, *(const void **)(a1 + 352), *(unsigned __int16 *)(a1 + 344));
  memmove((void *)(a2 + 256), *(const void **)(a1 + 624), *(unsigned __int16 *)(a1 + 616));
  memmove((void *)(a2 + 1300), (const void *)(a1 + 2128), 0x200u);
  memmove((void *)(a2 + 1812), (const void *)(a1 + 2656), 0x200u);
  memmove((void *)(a2 + 2324), (const void *)(a1 + 2104), 6u);
  memmove((void *)(a2 + 2330), (const void *)(a1 + 3336), 6u);
  memmove((void *)(a2 + 2336), (const void *)(a1 + 3342), 6u);
  v5 = *(_DWORD *)(a1 + 68);
  *(_BYTE *)(a2 + 780) = 0;
  *(_DWORD *)(a2 + 776) = v5;
  *(_BYTE *)(a2 + 2608) = 1;
  if ( !*(_DWORD *)(a1 + 68) )
  {
    *(_DWORD *)(a2 + 772) = 0;
    if ( *(_DWORD *)(a1 + 1880) == 1 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v4,
        19,
        334,
        (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids,
        (__int64)"ObjNic->ConnectState != VmsNicConnectStateConnected");
      if ( *(_DWORD *)(a1 + 1880) == 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    goto LABEL_24;
  }
  *(_DWORD *)(a2 + 772) = *(_DWORD *)(a1 + 1872);
  *(_DWORD *)(a2 + 2344) = *(_DWORD *)(a1 + 3360);
  *(_BYTE *)(a2 + 781) = *(_BYTE *)(a1 + 3956);
  *(_DWORD *)(a2 + 2348) = *(_DWORD *)(a1 + 3356) - 14;
  v6 = *(_DWORD *)(a1 + 1872);
  if ( v6 != 1 )
  {
    if ( v6 != 4 )
      goto LABEL_16;
    v13 = *(_QWORD *)(a1 + 3312);
    v11 = 254;
    if ( *(_WORD *)(v13 + 64) < 0xFEu )
      v11 = *(unsigned __int16 *)(v13 + 64);
    v12 = *(const void **)(v13 + 72);
    goto LABEL_15;
  }
  v7 = *(_QWORD *)(a1 + 3312);
  if ( v7 )
  {
    *(_BYTE *)(a2 + 2608) = *(_DWORD *)(v7 + 32) != 2;
    v8 = *(unsigned __int16 *)(v7 + 96);
    if ( (unsigned __int16)v8 > 0x10u )
    {
      v9 = *(_QWORD *)(v7 + 104);
      v10 = v8 - 16;
      v11 = 254;
      if ( v10 < 0xFE )
        v11 = v10;
      v12 = (const void *)(v9 + 16);
LABEL_15:
      memmove((void *)(a2 + 2352), v12, v11);
    }
  }
LABEL_16:
  if ( *(_DWORD *)(a1 + 1880) == 1 )
  {
    *(_BYTE *)(a2 + 780) = 1;
    v14 = *(_QWORD *)(*(_QWORD *)(a1 + 1984) + 1240LL);
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
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v14 + 56), &v19, 1u);
    memmove(
      (void *)(a2 + 782),
      *(const void **)(*(_QWORD *)(*(_QWORD *)(a1 + 1984) + 1240LL) + 352LL),
      *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 1984) + 1240LL) + 344LL));
    v16 = *(_QWORD *)(a1 + 1984);
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
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v16 + 56), &v18, 1u);
    memmove(
      (void *)(a2 + 1038),
      *(const void **)(*(_QWORD *)(a1 + 1984) + 352LL),
      *(unsigned __int16 *)(*(_QWORD *)(a1 + 1984) + 344LL));
    *(_DWORD *)(a2 + 1296) = *(_DWORD *)(*(_QWORD *)(a1 + 1984) + 5920LL);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 1984) + 56LL), &v18);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(*(_QWORD *)(a1 + 1984) + 1240LL) + 56LL), &v19);
  }
LABEL_24:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
}

```

## disassembly

```asm
0x140054644  mov     [rsp-28h+arg_18], rbx
0x140054649  push    rbp
0x14005464a  push    rsi
0x14005464b  push    rdi
0x14005464c  push    r12
0x14005464e  push    r15
0x140054650  mov     rbp, rsp
0x140054653  sub     rsp, 30h
0x140054657  xor     eax, eax
0x140054659  mov     rdi, rdx
0x14005465c  mov     rbx, rcx
0x14005465f  mov     word ptr [rbp+LockState.OldIrql], ax
0x140054663  mov     rcx, rdi; void *
0x140054666  mov     [rbp+LockState.Flags], al
0x140054669  xor     edx, edx; Val
0x14005466b  mov     word ptr [rbp+arg_8.OldIrql], ax
0x14005466f  mov     r8d, 0A34h; Size
0x140054675  mov     [rbp+arg_8.Flags], al
0x140054678  mov     word ptr [rbp+arg_0.OldIrql], ax
0x14005467c  mov     [rbp+arg_0.Flags], al
0x14005467f  call    memset
0x140054684  mov     rcx, [rbx+38h]; Lock
0x140054688  lea     rdx, [rbp+LockState]; LockState
0x14005468c  xor     r8d, r8d; Flags
0x14005468f  call    cs:__imp_NdisAcquireRWLockRead
0x140054696  nop     dword ptr [rax+rax+00h]
0x14005469b  movzx   r8d, word ptr [rbx+158h]; Size
0x1400546a3  mov     rcx, rdi; void *
0x1400546a6  mov     rdx, [rbx+160h]; Src
0x1400546ad  call    memmove
0x1400546b2  movzx   r8d, word ptr [rbx+268h]; Size
0x1400546ba  lea     rcx, [rdi+100h]; void *
0x1400546c1  mov     rdx, [rbx+270h]; Src
0x1400546c8  call    memmove
0x1400546cd  mov     esi, 200h
0x1400546d2  lea     rdx, [rbx+850h]; Src
0x1400546d9  mov     r8d, esi; Size
0x1400546dc  lea     rcx, [rdi+514h]; void *
0x1400546e3  call    memmove
0x1400546e8  lea     rdx, [rbx+0A60h]; Src
0x1400546ef  mov     r8d, esi; Size
0x1400546f2  lea     rcx, [rdi+714h]; void *
0x1400546f9  call    memmove
0x1400546fe  mov     esi, 6
0x140054703  lea     rdx, [rbx+838h]; Src
0x14005470a  mov     r8d, esi; Size
0x14005470d  lea     rcx, [rdi+914h]; void *
0x140054714  call    memmove
0x140054719  lea     rdx, [rbx+0D08h]; Src
0x140054720  mov     r8d, esi; Size
0x140054723  lea     rcx, [rdi+91Ah]; void *
0x14005472a  call    memmove
0x14005472f  lea     rdx, [rbx+0D0Eh]; Src
0x140054736  mov     r8d, esi; Size
0x140054739  lea     rcx, [rdi+920h]; void *
0x140054740  call    memmove
0x140054745  mov     eax, [rbx+44h]
0x140054748  xor     ecx, ecx
0x14005474a  mov     [rdi+30Ch], cl
0x140054750  mov     [rdi+308h], eax
0x140054756  mov     byte ptr [rdi+0A30h], 1
0x14005475d  cmp     [rbx+44h], ecx
0x140054760  jnz     short loc_1400547BA
0x140054762  mov     [rdi+304h], ecx
0x140054768  cmp     dword ptr [rbx+758h], 1
0x14005476f  jnz     loc_1400549F2
0x140054775  mov     rcx, cs:VmsIfrLog
0x14005477c  lea     rax, aObjnicConnects_0; "ObjNic->ConnectState != VmsNicConnectSt"...
0x140054783  mov     [rsp+30h+var_8], rax
0x140054788  lea     r8d, [rsi+0Dh]
0x14005478c  lea     rax, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x140054793  mov     r9d, 14Eh
0x140054799  mov     [rsp+30h+var_10], rax
0x14005479e  call    WPP_RECORDER_SF_s
0x1400547a3  cmp     dword ptr [rbx+758h], 1
0x1400547aa  jnz     loc_1400549F2
0x1400547b0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->ConnectState != VmsNicConnectStateConnected")
0x1400547b5  jmp     loc_1400549F2
0x1400547ba  mov     eax, [rbx+750h]
0x1400547c0  mov     [rdi+304h], eax
0x1400547c6  mov     eax, [rbx+0D20h]
0x1400547cc  mov     [rdi+928h], eax
0x1400547d2  mov     al, [rbx+0F74h]
0x1400547d8  mov     [rdi+30Dh], al
0x1400547de  mov     eax, [rbx+0D1Ch]
0x1400547e4  sub     eax, 0Eh
0x1400547e7  mov     [rdi+92Ch], eax
0x1400547ed  mov     eax, [rbx+750h]
0x1400547f3  cmp     eax, 1
0x1400547f6  jnz     short loc_140054839
0x1400547f8  mov     rdx, [rbx+0CF0h]
0x1400547ff  test    rdx, rdx
0x140054802  jz      short loc_140054868
0x140054804  cmp     dword ptr [rdx+20h], 2
0x140054808  mov     ecx, 10h
0x14005480d  setnz   al
0x140054810  mov     [rdi+0A30h], al
0x140054816  movzx   eax, word ptr [rdx+60h]
0x14005481a  cmp     ax, cx
0x14005481d  jbe     short loc_140054868
0x14005481f  mov     rdx, [rdx+68h]
0x140054823  add     rax, 0FFFFFFFFFFFFFFF0h
0x140054827  mov     r8d, 0FEh
0x14005482d  cmp     rax, r8
0x140054830  cmovb   r8, rax
0x140054834  add     rdx, rcx
0x140054837  jmp     short loc_14005485C
0x140054839  cmp     eax, 4
0x14005483c  jnz     short loc_140054868
0x14005483e  mov     rdx, [rbx+0CF0h]
0x140054845  mov     r8d, 0FEh
0x14005484b  movzx   eax, word ptr [rdx+40h]
0x14005484f  cmp     ax, r8w
0x140054853  jnb     short loc_140054858
0x140054855  mov     r8d, eax; Size
0x140054858  mov     rdx, [rdx+48h]; Src
0x14005485c  lea     rcx, [rdi+930h]; void *
0x140054863  call    memmove
0x140054868  cmp     dword ptr [rbx+758h], 1
0x14005486f  jnz     loc_1400549F2
0x140054875  mov     byte ptr [rdi+30Ch], 1
0x14005487c  mov     rax, [rbx+7C0h]
0x140054883  mov     rsi, [rax+4D8h]
0x14005488a  call    cs:__imp_KeGetCurrentIrql
0x140054891  nop     dword ptr [rax+rax+00h]
0x140054896  lea     r15, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14005489d  lea     r12, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x1400548a4  cmp     al, 2
0x1400548a6  jz      short loc_1400548DD
0x1400548a8  mov     rcx, cs:VmsIfrLog
0x1400548af  mov     r9d, 18h
0x1400548b5  mov     [rsp+30h+var_8], r15
0x1400548ba  mov     [rsp+30h+var_10], r12
0x1400548bf  lea     r8d, [r9-5]
0x1400548c3  call    WPP_RECORDER_SF_s
0x1400548c8  call    cs:__imp_KeGetCurrentIrql
0x1400548cf  nop     dword ptr [rax+rax+00h]
0x1400548d4  cmp     al, 2
0x1400548d6  jz      short loc_1400548DD
0x1400548d8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x1400548dd  mov     rcx, [rsi+38h]; Lock
0x1400548e1  lea     rdx, [rbp+arg_8]; LockState
0x1400548e5  mov     r8b, 1; Flags
0x1400548e8  call    cs:__imp_NdisAcquireRWLockRead
0x1400548ef  nop     dword ptr [rax+rax+00h]
0x1400548f4  mov     rax, [rbx+7C0h]
0x1400548fb  lea     rcx, [rdi+30Eh]; void *
0x140054902  mov     rdx, [rax+4D8h]
0x140054909  movzx   r8d, word ptr [rdx+158h]; Size
0x140054911  mov     rdx, [rdx+160h]; Src
0x140054918  call    memmove
0x14005491d  mov     rsi, [rbx+7C0h]
0x140054924  call    cs:__imp_KeGetCurrentIrql
0x14005492b  nop     dword ptr [rax+rax+00h]
0x140054930  cmp     al, 2
0x140054932  jz      short loc_140054969
0x140054934  mov     rcx, cs:VmsIfrLog
0x14005493b  mov     r9d, 18h
0x140054941  mov     [rsp+30h+var_8], r15
0x140054946  mov     [rsp+30h+var_10], r12
0x14005494b  lea     r8d, [r9-5]
0x14005494f  call    WPP_RECORDER_SF_s
0x140054954  call    cs:__imp_KeGetCurrentIrql
0x14005495b  nop     dword ptr [rax+rax+00h]
0x140054960  cmp     al, 2
0x140054962  jz      short loc_140054969
0x140054964  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140054969  mov     rcx, [rsi+38h]; Lock
0x14005496d  lea     rdx, [rbp+arg_0]; LockState
0x140054971  mov     r8b, 1; Flags
0x140054974  call    cs:__imp_NdisAcquireRWLockRead
0x14005497b  nop     dword ptr [rax+rax+00h]
0x140054980  mov     rdx, [rbx+7C0h]
0x140054987  lea     rcx, [rdi+40Eh]; void *
0x14005498e  movzx   r8d, word ptr [rdx+158h]; Size
0x140054996  mov     rdx, [rdx+160h]; Src
0x14005499d  call    memmove
0x1400549a2  mov     rax, [rbx+7C0h]
0x1400549a9  lea     rdx, [rbp+arg_0]; LockState
0x1400549ad  mov     ecx, [rax+1720h]
0x1400549b3  mov     [rdi+510h], ecx
0x1400549b9  mov     rcx, [rbx+7C0h]
0x1400549c0  mov     rcx, [rcx+38h]; Lock
0x1400549c4  call    cs:__imp_NdisReleaseRWLock
0x1400549cb  nop     dword ptr [rax+rax+00h]
0x1400549d0  mov     rax, [rbx+7C0h]
0x1400549d7  lea     rdx, [rbp+arg_8]; LockState
0x1400549db  mov     rcx, [rax+4D8h]
0x1400549e2  mov     rcx, [rcx+38h]; Lock
0x1400549e6  call    cs:__imp_NdisReleaseRWLock
0x1400549ed  nop     dword ptr [rax+rax+00h]
0x1400549f2  mov     rcx, [rbx+38h]; Lock
0x1400549f6  lea     rdx, [rbp+LockState]; LockState
0x1400549fa  call    cs:__imp_NdisReleaseRWLock
0x140054a01  nop     dword ptr [rax+rax+00h]
0x140054a06  mov     rbx, [rsp+30h+arg_18]
0x140054a0b  add     rsp, 30h
0x140054a0f  pop     r15
0x140054a11  pop     r12
0x140054a13  pop     rdi
0x140054a14  pop     rsi
0x140054a15  pop     rbp
0x140054a16  retn
```
