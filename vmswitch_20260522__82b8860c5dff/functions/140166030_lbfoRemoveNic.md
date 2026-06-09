# lbfoRemoveNic

- ea: `0x140166030`
- end: `0x14016643e`
- name: `lbfoRemoveNic`
- size: `1038`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140165e50`

## callees

- `0x140027a64`
- `0x14003e9e4`
- `0x140050bd8`
- `0x14008497c`
- `0x140089a04`
- `0x140091154`
- `0x140164c54`
- `0x140166030`
- `0x140166444`
- `0x140166698`
- `0x14016801c`
- `0x1401701d0`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14016620d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14016620d`
- `NDIS!NdisFreeTimerObject` at `0x1401662f7`
- `NDIS!NdisFreeTimerObject` at `0x1401662f7`
- `NDIS!NdisResetEvent` at `0x140166165`
- `NDIS!NdisResetEvent` at `0x140166165`
- `NDIS!NdisReleaseRWLock` at `0x14016613b`
- `NDIS!NdisReleaseRWLock` at `0x140166152`
- `NDIS!NdisReleaseRWLock` at `0x1401661e0`
- `NDIS!NdisReleaseRWLock` at `0x140166411`
- `NDIS!NdisReleaseRWLock` at `0x14016613b`
- `NDIS!NdisReleaseRWLock` at `0x140166152`
- `NDIS!NdisReleaseRWLock` at `0x1401661e0`
- `NDIS!NdisReleaseRWLock` at `0x140166411`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166103`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016611d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016617f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166261`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166103`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016611d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016617f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166261`

## pseudocode

```c
void __fastcall lbfoRemoveNic(__int64 a1, __int64 *a2, _BYTE *a3)
{
  int v6; // eax
  __int16 v7; // bx
  int v8; // ecx
  int v9; // r8d
  int v10; // edx
  void *v11; // rcx
  void (__fastcall *v12)(__int64, __int64 *, struct _LOCK_STATE_EX *); // rax
  void (__fastcall *v13)(__int64, __int64 *); // rax
  __int64 *v14; // rax
  __int64 **v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rdi
  _QWORD *v19; // rcx
  struct _LOCK_STATE_EX v20; // [rsp+70h] [rbp+30h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+38h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v20.OldIrql = 0;
  v20.Flags = 0;
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      23,
      22,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      a1,
      (char)a2,
      *((_BYTE *)a2 + 680));
  if ( *((_WORD *)a2 + 84) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)a2,
      19,
      23,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"Nic->FCRefCount == 0");
    if ( *((_WORD *)a2 + 84) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 1592), &LockState, 0);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20, 0);
  *((_BYTE *)a2 + 768) = 1;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1592), &LockState);
  NdisResetEvent((PNDIS_EVENT)(a1 + 3840));
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20, 0);
  lbfoSetNicFailureReason(a2);
  v6 = *((_DWORD *)a2 + 184);
  *((_DWORD *)a2 + 184) = 0;
  if ( v6 == 1 )
    lbfoTFODisconnectNic(a1, a2);
  lbfoCancelSoftFailTimer(a2);
  v7 = --*((_WORD *)a2 + 85);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20);
  lbfoLBQueueResourceManagementWorkItem(a1);
  if ( v7 )
    KeWaitForSingleObject(a2 + 22, Executive, 0, 0, 0);
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) & 8) != 0 )
    lbfoSetOriginalMacOnNicImmediate(a1, a2);
  if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 0x200000) != 0 )
    McTemplateK0pjd_EtwWriteTransfer(v8, (unsigned int)MemberUnteamedInfo, v9, a1, (__int64)(a2 + 6), 0);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20, 0);
  if ( *((_DWORD *)a2 + 184) == 1 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v10,
      19,
      24,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"!IS_NIC_PHY_CONNECTED(Nic)");
    if ( *((_DWORD *)a2 + 184) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( *((_WORD *)a2 + 85) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v10,
      19,
      25,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"Nic->RefCount == 0");
    if ( *((_WORD *)a2 + 85) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v11 = (void *)a2[98];
  if ( v11 )
    NdisFreeTimerObject(v11);
  v12 = (void (__fastcall *)(__int64, __int64 *, struct _LOCK_STATE_EX *))qword_1401F3A08[9 * *(int *)(a1 + 1520)];
  if ( v12 )
    v12(a1, a2, &v20);
  v13 = (void (__fastcall *)(__int64, __int64 *))*(&off_1401F3AF8 + 14 * *(int *)(a1 + 1516));
  if ( v13 )
    v13(a1, a2);
  v14 = (__int64 *)*a2;
  if ( *(__int64 **)(*a2 + 8) != a2 )
    goto LABEL_35;
  v15 = (__int64 **)a2[1];
  if ( *v15 != a2 )
    goto LABEL_35;
  *v15 = v14;
  v14[1] = (__int64)v15;
  --*(_WORD *)(a2[4] + 40);
  --*(_WORD *)(a1 + 2306);
  *(_QWORD *)(a1 + 8LL * *((unsigned __int8 *)a2 + 680) + 1696) = 0;
  v16 = a2[110];
  if ( v16 )
    VmsOmNicDecrementControlCount(*(_QWORD *)(v16 + 8), *(unsigned __int16 *)(v16 + 16), 34);
  v17 = a2[4];
  a2[110] = 0;
  if ( !*(_WORD *)(v17 + 40) )
  {
    v18 = a2 + 112;
    *a3 = 0;
    v18[1] = v18;
    *v18 = v18;
    v19 = *(_QWORD **)(a1 + 3984);
    if ( *v19 == a1 + 3976 )
    {
      v18[1] = v19;
      *v18 = a1 + 3976;
      *v19 = v18;
      *(_QWORD *)(a1 + 3984) = v18;
      NvIoQueueWorkItem(a1 + 3992, 0);
      goto LABEL_34;
    }
LABEL_35:
    __fastfail(3u);
  }
LABEL_34:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), &v20);
}

```

## disassembly

```asm
0x140166030  mov     [rsp-28h+arg_10], rbx
0x140166035  mov     [rsp-28h+arg_18], rsi
0x14016603a  push    rbp
0x14016603b  push    rdi
0x14016603c  push    r12
0x14016603e  push    r14
0x140166040  push    r15
0x140166042  mov     rbp, rsp
0x140166045  sub     rsp, 40h
0x140166049  xor     eax, eax
0x14016604b  mov     r14, r8
0x14016604e  mov     word ptr [rbp+LockState.OldIrql], ax
0x140166052  mov     rdi, rdx
0x140166055  mov     [rbp+LockState.Flags], al
0x140166058  mov     rsi, rcx
0x14016605b  mov     word ptr [rbp+arg_0.OldIrql], ax
0x14016605f  mov     [rbp+arg_0.Flags], al
0x140166062  mov     rcx, cs:WPP_GLOBAL_Control
0x140166069  lea     r12, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166070  xor     r15d, r15d
0x140166073  mov     ebx, 17h
0x140166078  mov     al, [rcx+29h]
0x14016607b  dec     al
0x14016607d  cmp     al, 2
0x14016607f  ja      short loc_140166088
0x140166081  cmp     [rcx+48h], r15w
0x140166086  jz      short loc_1401660B6
0x140166088  movzx   eax, byte ptr [rdx+2A8h]
0x14016608f  mov     r9d, 16h
0x140166095  mov     rcx, [rcx+40h]
0x140166099  mov     r8d, ebx
0x14016609c  mov     [rsp+40h+var_8], eax
0x1401660a0  xor     edx, edx
0x1401660a2  mov     [rsp+40h+var_10], rdi
0x1401660a7  mov     [rsp+40h+var_18], rsi
0x1401660ac  mov     [rsp+40h+Timeout], r12
0x1401660b1  call    WPP_RECORDER_SF_qqd
0x1401660b6  cmp     [rdi+0A8h], r15w
0x1401660be  jz      short loc_1401660F5
0x1401660c0  mov     rcx, cs:VmsIfrLog
0x1401660c7  lea     rax, aNicFcrefcount0; "Nic->FCRefCount == 0"
0x1401660ce  mov     [rsp+40h+var_18], rax
0x1401660d3  mov     r9d, ebx
0x1401660d6  mov     r8d, 13h
0x1401660dc  mov     [rsp+40h+Timeout], r12
0x1401660e1  call    WPP_RECORDER_SF_s
0x1401660e6  cmp     [rdi+0A8h], r15w
0x1401660ee  jz      short loc_1401660F5
0x1401660f0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->FCRefCount == 0")
0x1401660f5  mov     rcx, [rsi+638h]; Lock
0x1401660fc  lea     rdx, [rbp+LockState]; LockState
0x140166100  xor     r8d, r8d; Flags
0x140166103  call    cs:__imp_NdisAcquireRWLockWrite
0x14016610a  nop     dword ptr [rax+rax+00h]
0x14016610f  mov     rcx, [rsi+630h]; Lock
0x140166116  lea     rdx, [rbp+arg_0]; LockState
0x14016611a  xor     r8d, r8d; Flags
0x14016611d  call    cs:__imp_NdisAcquireRWLockWrite
0x140166124  nop     dword ptr [rax+rax+00h]
0x140166129  mov     byte ptr [rdi+300h], 1
0x140166130  lea     rdx, [rbp+arg_0]; LockState
0x140166134  mov     rcx, [rsi+630h]; Lock
0x14016613b  call    cs:__imp_NdisReleaseRWLock
0x140166142  nop     dword ptr [rax+rax+00h]
0x140166147  mov     rcx, [rsi+638h]; Lock
0x14016614e  lea     rdx, [rbp+LockState]; LockState
0x140166152  call    cs:__imp_NdisReleaseRWLock
0x140166159  nop     dword ptr [rax+rax+00h]
0x14016615e  lea     rcx, [rsi+0F00h]; Event
0x140166165  call    cs:__imp_NdisResetEvent
0x14016616c  nop     dword ptr [rax+rax+00h]
0x140166171  mov     rcx, [rsi+630h]; Lock
0x140166178  lea     rdx, [rbp+arg_0]; LockState
0x14016617c  xor     r8d, r8d; Flags
0x14016617f  call    cs:__imp_NdisAcquireRWLockWrite
0x140166186  nop     dword ptr [rax+rax+00h]
0x14016618b  xor     r9d, r9d
0x14016618e  mov     r8b, 1
0x140166191  mov     rcx, rdi; FunctionContext
0x140166194  lea     edx, [r9+6]
0x140166198  call    lbfoSetNicFailureReason
0x14016619d  mov     eax, [rdi+2E0h]
0x1401661a3  mov     [rdi+2E0h], r15d
0x1401661aa  cmp     eax, 1
0x1401661ad  jnz     short loc_1401661BA
0x1401661af  mov     rdx, rdi
0x1401661b2  mov     rcx, rsi
0x1401661b5  call    lbfoTFODisconnectNic
0x1401661ba  mov     rcx, rdi
0x1401661bd  call    lbfoCancelSoftFailTimer
0x1401661c2  mov     eax, 0FFFFh
0x1401661c7  lea     rdx, [rbp+arg_0]; LockState
0x1401661cb  add     [rdi+0AAh], ax
0x1401661d2  mov     rcx, [rsi+630h]; Lock
0x1401661d9  movzx   ebx, word ptr [rdi+0AAh]
0x1401661e0  call    cs:__imp_NdisReleaseRWLock
0x1401661e7  nop     dword ptr [rax+rax+00h]
0x1401661ec  mov     rcx, rsi
0x1401661ef  call    lbfoLBQueueResourceManagementWorkItem
0x1401661f4  test    bx, bx
0x1401661f7  jz      short loc_140166219
0x1401661f9  lea     rcx, [rdi+0B0h]; Object
0x140166200  mov     [rsp+40h+Timeout], r15; Timeout
0x140166205  xor     r9d, r9d; Alertable
0x140166208  xor     r8d, r8d; WaitMode
0x14016620b  xor     edx, edx; WaitReason
0x14016620d  call    cs:__imp_KeWaitForSingleObject
0x140166214  nop     dword ptr [rax+rax+00h]
0x140166219  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166220  jz      short loc_14016622D
0x140166222  mov     rdx, rdi
0x140166225  mov     rcx, rsi
0x140166228  call    lbfoSetOriginalMacOnNicImmediate
0x14016622d  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x140166234  jz      short loc_140166253
0x140166236  lea     rax, [rdi+30h]
0x14016623a  mov     dword ptr [rsp+40h+var_18], r15d
0x14016623f  mov     r9, rsi
0x140166242  mov     [rsp+40h+Timeout], rax
0x140166247  lea     rdx, MemberUnteamedInfo
0x14016624e  call    McTemplateK0pjd_EtwWriteTransfer
0x140166253  mov     rcx, [rsi+630h]; Lock
0x14016625a  lea     rdx, [rbp+arg_0]; LockState
0x14016625e  xor     r8d, r8d; Flags
0x140166261  call    cs:__imp_NdisAcquireRWLockWrite
0x140166268  nop     dword ptr [rax+rax+00h]
0x14016626d  cmp     dword ptr [rdi+2E0h], 1
0x140166274  jnz     short loc_1401662AB
0x140166276  mov     rcx, cs:VmsIfrLog
0x14016627d  lea     rax, aIsNicPhyConnec_0; "!IS_NIC_PHY_CONNECTED(Nic)"
0x140166284  mov     r9d, 18h
0x14016628a  mov     [rsp+40h+var_18], rax
0x14016628f  mov     [rsp+40h+Timeout], r12
0x140166294  lea     r8d, [r9-5]
0x140166298  call    WPP_RECORDER_SF_s
0x14016629d  cmp     dword ptr [rdi+2E0h], 1
0x1401662a4  jnz     short loc_1401662AB
0x1401662a6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!((Nic)->PHY.State == PHY_Connected)")
0x1401662ab  cmp     [rdi+0AAh], r15w
0x1401662b3  jz      short loc_1401662EB
0x1401662b5  mov     rcx, cs:VmsIfrLog
0x1401662bc  lea     rax, aNicRefcount0; "Nic->RefCount == 0"
0x1401662c3  mov     r9d, 19h
0x1401662c9  mov     [rsp+40h+var_18], rax
0x1401662ce  mov     [rsp+40h+Timeout], r12
0x1401662d3  lea     r8d, [r9-6]
0x1401662d7  call    WPP_RECORDER_SF_s
0x1401662dc  cmp     [rdi+0AAh], r15w
0x1401662e4  jz      short loc_1401662EB
0x1401662e6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->RefCount == 0")
0x1401662eb  mov     rcx, [rdi+310h]; TimerObject
0x1401662f2  test    rcx, rcx
0x1401662f5  jz      short loc_140166303
0x1401662f7  call    cs:__imp_NdisFreeTimerObject
0x1401662fe  nop     dword ptr [rax+rax+00h]
0x140166303  movsxd  rax, dword ptr [rsi+5F0h]
0x14016630a  lea     rbx, cs:140000000h
0x140166311  lea     rcx, [rax+rax*8]
0x140166315  mov     rax, rva qword_1401F3A08[rbx+rcx*8]
0x14016631d  test    rax, rax
0x140166320  jz      short loc_140166331
0x140166322  lea     r8, [rbp+arg_0]
0x140166326  mov     rdx, rdi
0x140166329  mov     rcx, rsi
0x14016632c  call    _guard_dispatch_icall
0x140166331  movsxd  rax, dword ptr [rsi+5ECh]
0x140166338  imul    rcx, rax, 70h ; 'p'
0x14016633c  mov     rax, [rcx+rbx+1F3AF8h]
0x140166344  test    rax, rax
0x140166347  jz      short loc_140166354
0x140166349  mov     rdx, rdi
0x14016634c  mov     rcx, rsi
0x14016634f  call    _guard_dispatch_icall
0x140166354  mov     rax, [rdi]
0x140166357  cmp     [rax+8], rdi
0x14016635b  jnz     loc_140166437
0x140166361  mov     rcx, [rdi+8]
0x140166365  cmp     [rcx], rdi
0x140166368  jnz     loc_140166437
0x14016636e  mov     [rcx], rax
0x140166371  mov     [rax+8], rcx
0x140166375  mov     ecx, 0FFFFh
0x14016637a  mov     rax, [rdi+20h]
0x14016637e  add     [rax+28h], cx
0x140166382  add     [rsi+902h], cx
0x140166389  movzx   eax, byte ptr [rdi+2A8h]
0x140166390  mov     [rsi+rax*8+6A0h], r15
0x140166398  mov     rcx, [rdi+370h]
0x14016639f  test    rcx, rcx
0x1401663a2  jz      short loc_1401663B7
0x1401663a4  movzx   edx, word ptr [rcx+10h]
0x1401663a8  mov     r8d, 22h ; '"'
0x1401663ae  mov     rcx, [rcx+8]
0x1401663b2  call    VmsOmNicDecrementControlCount
0x1401663b7  mov     rax, [rdi+20h]
0x1401663bb  mov     [rdi+370h], r15
0x1401663c2  cmp     [rax+28h], r15w
0x1401663c7  jnz     short loc_140166406
0x1401663c9  add     rdi, 380h
0x1401663d0  mov     [r14], r15b
0x1401663d3  lea     rax, [rsi+0F88h]
0x1401663da  mov     [rdi+8], rdi
0x1401663de  mov     [rdi], rdi
0x1401663e1  mov     rcx, [rax+8]
0x1401663e5  cmp     [rcx], rax
0x1401663e8  jnz     short loc_140166437
0x1401663ea  mov     [rdi+8], rcx
0x1401663ee  xor     edx, edx
0x1401663f0  mov     [rdi], rax
0x1401663f3  mov     [rcx], rdi
0x1401663f6  lea     rcx, [rsi+0F98h]
0x1401663fd  mov     [rax+8], rdi
0x140166401  call    NvIoQueueWorkItem
0x140166406  mov     rcx, [rsi+630h]; Lock
0x14016640d  lea     rdx, [rbp+arg_0]; LockState
0x140166411  call    cs:__imp_NdisReleaseRWLock
0x140166418  nop     dword ptr [rax+rax+00h]
0x14016641d  lea     r11, [rsp+40h+var_s0]
0x140166422  mov     rbx, [r11+40h]
0x140166426  mov     rsi, [r11+48h]
0x14016642a  mov     rsp, r11
0x14016642d  pop     r15
0x14016642f  pop     r14
0x140166431  pop     r12
0x140166433  pop     rdi
0x140166434  pop     rbp
0x140166435  retn
0x140166437  mov     ecx, 3
0x14016643c  int     29h; Win8: RtlFailFast(ecx)
```
