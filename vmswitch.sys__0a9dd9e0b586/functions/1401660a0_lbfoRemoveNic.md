# lbfoRemoveNic

- ea: `0x1401660a0`
- end: `0x1401664ae`
- name: `lbfoRemoveNic`
- size: `1038`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140165ec0`

## callees

- `0x140027a64`
- `0x14003e9e4`
- `0x140050bd8`
- `0x14008497c`
- `0x140089a04`
- `0x140091154`
- `0x140164cc4`
- `0x1401660a0`
- `0x1401664b4`
- `0x140166708`
- `0x14016808c`
- `0x140170240`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14016627d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14016627d`
- `NDIS!NdisFreeTimerObject` at `0x140166367`
- `NDIS!NdisFreeTimerObject` at `0x140166367`
- `NDIS!NdisResetEvent` at `0x1401661d5`
- `NDIS!NdisResetEvent` at `0x1401661d5`
- `NDIS!NdisReleaseRWLock` at `0x1401661ab`
- `NDIS!NdisReleaseRWLock` at `0x1401661c2`
- `NDIS!NdisReleaseRWLock` at `0x140166250`
- `NDIS!NdisReleaseRWLock` at `0x140166481`
- `NDIS!NdisReleaseRWLock` at `0x1401661ab`
- `NDIS!NdisReleaseRWLock` at `0x1401661c2`
- `NDIS!NdisReleaseRWLock` at `0x140166250`
- `NDIS!NdisReleaseRWLock` at `0x140166481`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166173`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016618d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401661ef`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401662d1`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166173`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016618d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401661ef`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401662d1`

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
0x1401660a0  mov     [rsp-28h+arg_10], rbx
0x1401660a5  mov     [rsp-28h+arg_18], rsi
0x1401660aa  push    rbp
0x1401660ab  push    rdi
0x1401660ac  push    r12
0x1401660ae  push    r14
0x1401660b0  push    r15
0x1401660b2  mov     rbp, rsp
0x1401660b5  sub     rsp, 40h
0x1401660b9  xor     eax, eax
0x1401660bb  mov     r14, r8
0x1401660be  mov     word ptr [rbp+LockState.OldIrql], ax
0x1401660c2  mov     rdi, rdx
0x1401660c5  mov     [rbp+LockState.Flags], al
0x1401660c8  mov     rsi, rcx
0x1401660cb  mov     word ptr [rbp+arg_0.OldIrql], ax
0x1401660cf  mov     [rbp+arg_0.Flags], al
0x1401660d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401660d9  lea     r12, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x1401660e0  xor     r15d, r15d
0x1401660e3  mov     ebx, 17h
0x1401660e8  mov     al, [rcx+29h]
0x1401660eb  dec     al
0x1401660ed  cmp     al, 2
0x1401660ef  ja      short loc_1401660F8
0x1401660f1  cmp     [rcx+48h], r15w
0x1401660f6  jz      short loc_140166126
0x1401660f8  movzx   eax, byte ptr [rdx+2A8h]
0x1401660ff  mov     r9d, 16h
0x140166105  mov     rcx, [rcx+40h]
0x140166109  mov     r8d, ebx
0x14016610c  mov     [rsp+40h+var_8], eax
0x140166110  xor     edx, edx
0x140166112  mov     [rsp+40h+var_10], rdi
0x140166117  mov     [rsp+40h+var_18], rsi
0x14016611c  mov     [rsp+40h+Timeout], r12
0x140166121  call    WPP_RECORDER_SF_qqd
0x140166126  cmp     [rdi+0A8h], r15w
0x14016612e  jz      short loc_140166165
0x140166130  mov     rcx, cs:VmsIfrLog
0x140166137  lea     rax, aNicFcrefcount0; "Nic->FCRefCount == 0"
0x14016613e  mov     [rsp+40h+var_18], rax
0x140166143  mov     r9d, ebx
0x140166146  mov     r8d, 13h
0x14016614c  mov     [rsp+40h+Timeout], r12
0x140166151  call    WPP_RECORDER_SF_s
0x140166156  cmp     [rdi+0A8h], r15w
0x14016615e  jz      short loc_140166165
0x140166160  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->FCRefCount == 0")
0x140166165  mov     rcx, [rsi+638h]; Lock
0x14016616c  lea     rdx, [rbp+LockState]; LockState
0x140166170  xor     r8d, r8d; Flags
0x140166173  call    cs:__imp_NdisAcquireRWLockWrite
0x14016617a  nop     dword ptr [rax+rax+00h]
0x14016617f  mov     rcx, [rsi+630h]; Lock
0x140166186  lea     rdx, [rbp+arg_0]; LockState
0x14016618a  xor     r8d, r8d; Flags
0x14016618d  call    cs:__imp_NdisAcquireRWLockWrite
0x140166194  nop     dword ptr [rax+rax+00h]
0x140166199  mov     byte ptr [rdi+300h], 1
0x1401661a0  lea     rdx, [rbp+arg_0]; LockState
0x1401661a4  mov     rcx, [rsi+630h]; Lock
0x1401661ab  call    cs:__imp_NdisReleaseRWLock
0x1401661b2  nop     dword ptr [rax+rax+00h]
0x1401661b7  mov     rcx, [rsi+638h]; Lock
0x1401661be  lea     rdx, [rbp+LockState]; LockState
0x1401661c2  call    cs:__imp_NdisReleaseRWLock
0x1401661c9  nop     dword ptr [rax+rax+00h]
0x1401661ce  lea     rcx, [rsi+0F00h]; Event
0x1401661d5  call    cs:__imp_NdisResetEvent
0x1401661dc  nop     dword ptr [rax+rax+00h]
0x1401661e1  mov     rcx, [rsi+630h]; Lock
0x1401661e8  lea     rdx, [rbp+arg_0]; LockState
0x1401661ec  xor     r8d, r8d; Flags
0x1401661ef  call    cs:__imp_NdisAcquireRWLockWrite
0x1401661f6  nop     dword ptr [rax+rax+00h]
0x1401661fb  xor     r9d, r9d
0x1401661fe  mov     r8b, 1
0x140166201  mov     rcx, rdi; FunctionContext
0x140166204  lea     edx, [r9+6]
0x140166208  call    lbfoSetNicFailureReason
0x14016620d  mov     eax, [rdi+2E0h]
0x140166213  mov     [rdi+2E0h], r15d
0x14016621a  cmp     eax, 1
0x14016621d  jnz     short loc_14016622A
0x14016621f  mov     rdx, rdi
0x140166222  mov     rcx, rsi
0x140166225  call    lbfoTFODisconnectNic
0x14016622a  mov     rcx, rdi
0x14016622d  call    lbfoCancelSoftFailTimer
0x140166232  mov     eax, 0FFFFh
0x140166237  lea     rdx, [rbp+arg_0]; LockState
0x14016623b  add     [rdi+0AAh], ax
0x140166242  mov     rcx, [rsi+630h]; Lock
0x140166249  movzx   ebx, word ptr [rdi+0AAh]
0x140166250  call    cs:__imp_NdisReleaseRWLock
0x140166257  nop     dword ptr [rax+rax+00h]
0x14016625c  mov     rcx, rsi
0x14016625f  call    lbfoLBQueueResourceManagementWorkItem
0x140166264  test    bx, bx
0x140166267  jz      short loc_140166289
0x140166269  lea     rcx, [rdi+0B0h]; Object
0x140166270  mov     [rsp+40h+Timeout], r15; Timeout
0x140166275  xor     r9d, r9d; Alertable
0x140166278  xor     r8d, r8d; WaitMode
0x14016627b  xor     edx, edx; WaitReason
0x14016627d  call    cs:__imp_KeWaitForSingleObject
0x140166284  nop     dword ptr [rax+rax+00h]
0x140166289  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166290  jz      short loc_14016629D
0x140166292  mov     rdx, rdi
0x140166295  mov     rcx, rsi
0x140166298  call    lbfoSetOriginalMacOnNicImmediate
0x14016629d  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x1401662a4  jz      short loc_1401662C3
0x1401662a6  lea     rax, [rdi+30h]
0x1401662aa  mov     dword ptr [rsp+40h+var_18], r15d
0x1401662af  mov     r9, rsi
0x1401662b2  mov     [rsp+40h+Timeout], rax
0x1401662b7  lea     rdx, MemberUnteamedInfo
0x1401662be  call    McTemplateK0pjd_EtwWriteTransfer
0x1401662c3  mov     rcx, [rsi+630h]; Lock
0x1401662ca  lea     rdx, [rbp+arg_0]; LockState
0x1401662ce  xor     r8d, r8d; Flags
0x1401662d1  call    cs:__imp_NdisAcquireRWLockWrite
0x1401662d8  nop     dword ptr [rax+rax+00h]
0x1401662dd  cmp     dword ptr [rdi+2E0h], 1
0x1401662e4  jnz     short loc_14016631B
0x1401662e6  mov     rcx, cs:VmsIfrLog
0x1401662ed  lea     rax, aIsNicPhyConnec_0; "!IS_NIC_PHY_CONNECTED(Nic)"
0x1401662f4  mov     r9d, 18h
0x1401662fa  mov     [rsp+40h+var_18], rax
0x1401662ff  mov     [rsp+40h+Timeout], r12
0x140166304  lea     r8d, [r9-5]
0x140166308  call    WPP_RECORDER_SF_s
0x14016630d  cmp     dword ptr [rdi+2E0h], 1
0x140166314  jnz     short loc_14016631B
0x140166316  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!((Nic)->PHY.State == PHY_Connected)")
0x14016631b  cmp     [rdi+0AAh], r15w
0x140166323  jz      short loc_14016635B
0x140166325  mov     rcx, cs:VmsIfrLog
0x14016632c  lea     rax, aNicRefcount0; "Nic->RefCount == 0"
0x140166333  mov     r9d, 19h
0x140166339  mov     [rsp+40h+var_18], rax
0x14016633e  mov     [rsp+40h+Timeout], r12
0x140166343  lea     r8d, [r9-6]
0x140166347  call    WPP_RECORDER_SF_s
0x14016634c  cmp     [rdi+0AAh], r15w
0x140166354  jz      short loc_14016635B
0x140166356  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->RefCount == 0")
0x14016635b  mov     rcx, [rdi+310h]; TimerObject
0x140166362  test    rcx, rcx
0x140166365  jz      short loc_140166373
0x140166367  call    cs:__imp_NdisFreeTimerObject
0x14016636e  nop     dword ptr [rax+rax+00h]
0x140166373  movsxd  rax, dword ptr [rsi+5F0h]
0x14016637a  lea     rbx, cs:140000000h
0x140166381  lea     rcx, [rax+rax*8]
0x140166385  mov     rax, rva qword_1401F3A08[rbx+rcx*8]
0x14016638d  test    rax, rax
0x140166390  jz      short loc_1401663A1
0x140166392  lea     r8, [rbp+arg_0]
0x140166396  mov     rdx, rdi
0x140166399  mov     rcx, rsi
0x14016639c  call    _guard_dispatch_icall
0x1401663a1  movsxd  rax, dword ptr [rsi+5ECh]
0x1401663a8  imul    rcx, rax, 70h ; 'p'
0x1401663ac  mov     rax, [rcx+rbx+1F3AF8h]
0x1401663b4  test    rax, rax
0x1401663b7  jz      short loc_1401663C4
0x1401663b9  mov     rdx, rdi
0x1401663bc  mov     rcx, rsi
0x1401663bf  call    _guard_dispatch_icall
0x1401663c4  mov     rax, [rdi]
0x1401663c7  cmp     [rax+8], rdi
0x1401663cb  jnz     loc_1401664A7
0x1401663d1  mov     rcx, [rdi+8]
0x1401663d5  cmp     [rcx], rdi
0x1401663d8  jnz     loc_1401664A7
0x1401663de  mov     [rcx], rax
0x1401663e1  mov     [rax+8], rcx
0x1401663e5  mov     ecx, 0FFFFh
0x1401663ea  mov     rax, [rdi+20h]
0x1401663ee  add     [rax+28h], cx
0x1401663f2  add     [rsi+902h], cx
0x1401663f9  movzx   eax, byte ptr [rdi+2A8h]
0x140166400  mov     [rsi+rax*8+6A0h], r15
0x140166408  mov     rcx, [rdi+370h]
0x14016640f  test    rcx, rcx
0x140166412  jz      short loc_140166427
0x140166414  movzx   edx, word ptr [rcx+10h]
0x140166418  mov     r8d, 22h ; '"'
0x14016641e  mov     rcx, [rcx+8]
0x140166422  call    VmsOmNicDecrementControlCount
0x140166427  mov     rax, [rdi+20h]
0x14016642b  mov     [rdi+370h], r15
0x140166432  cmp     [rax+28h], r15w
0x140166437  jnz     short loc_140166476
0x140166439  add     rdi, 380h
0x140166440  mov     [r14], r15b
0x140166443  lea     rax, [rsi+0F88h]
0x14016644a  mov     [rdi+8], rdi
0x14016644e  mov     [rdi], rdi
0x140166451  mov     rcx, [rax+8]
0x140166455  cmp     [rcx], rax
0x140166458  jnz     short loc_1401664A7
0x14016645a  mov     [rdi+8], rcx
0x14016645e  xor     edx, edx
0x140166460  mov     [rdi], rax
0x140166463  mov     [rcx], rdi
0x140166466  lea     rcx, [rsi+0F98h]
0x14016646d  mov     [rax+8], rdi
0x140166471  call    NvIoQueueWorkItem
0x140166476  mov     rcx, [rsi+630h]; Lock
0x14016647d  lea     rdx, [rbp+arg_0]; LockState
0x140166481  call    cs:__imp_NdisReleaseRWLock
0x140166488  nop     dword ptr [rax+rax+00h]
0x14016648d  lea     r11, [rsp+40h+var_s0]
0x140166492  mov     rbx, [r11+40h]
0x140166496  mov     rsi, [r11+48h]
0x14016649a  mov     rsp, r11
0x14016649d  pop     r15
0x14016649f  pop     r14
0x1401664a1  pop     r12
0x1401664a3  pop     rdi
0x1401664a4  pop     rbp
0x1401664a5  retn
0x1401664a7  mov     ecx, 3
0x1401664ac  int     29h; Win8: RtlFailFast(ecx)
```
