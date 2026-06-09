# Tpm20Scheduler::SubmitRequest(Tpm20Request *)

- ea: `0x14000463c`
- end: `0x1400049ac`
- name: `?SubmitRequest@Tpm20Scheduler@@QEAAJPEAVTpm20Request@@@Z`
- size: `880`
- prototype: `__int64 __fastcall(Tpm20Scheduler *__hidden this, struct Tpm20Request *)`
- caller_count: `4`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140003380`
- `0x140003c30`
- `0x14001c7cc`
- `0x14001c944`

## callees

- `0x14000463c`
- `0x140004f80`
- `0x140005080`
- `0x14000521c`
- `0x140005698`
- `0x1400088ec`
- `0x14000e0b0`
- `0x14000e98c`
- `0x140010fdc`
- `0x1400110c0`
- `0x140013064`
- `0x14001c1ac`
- `0x14001c234`
- `0x1400293bc`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140004992`
- `ntoskrnl!KeSetEvent` at `0x140004992`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000494f`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000494f`

## pseudocode

```c
__int64 __fastcall Tpm20Scheduler::SubmitRequest(TpmSWAntiHammeringMgr **this, struct Tpm20Request *a2)
{
  __int64 v2; // rax
  int PermFlags; // ebp
  const char *v6; // rdx
  unsigned int v7; // edi
  __int64 v8; // r8
  struct TpmTransport *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // r8
  unsigned int v16; // [rsp+68h] [rbp+10h] BYREF

  v2 = *((_QWORD *)a2 + 2);
  if ( v2 && *(_BYTE *)(v2 + 44) )
    return (unsigned int)-1073741536;
  if ( Tpm20Scheduler::IsCommandBlocked((Tpm20Scheduler *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v6 = "non-admin user";
      if ( *((_DWORD *)a2 + 70) == 2 )
        v6 = "admin user";
      WPP_SF_Dqs(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v6,
        (unsigned int)"admin user",
        *(_DWORD *)((char *)a2 + 6),
        *((_QWORD *)a2 + 2),
        (__int64)v6);
    }
LABEL_10:
    v7 = -2144861184;
    goto LABEL_41;
  }
  if ( Tpm20Scheduler::IsHarmfulCommand((Tpm20Scheduler *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 11, v8, *(unsigned int *)((char *)a2 + 6), *((_QWORD *)a2 + 2));
    goto LABEL_10;
  }
  if ( *((_DWORD *)a2 + 70) == 2 )
    goto LABEL_35;
  if ( *(_DWORD *)((char *)a2 + 6) != 371 || !Tpm20Request::IsPrimaryHandleOfType(a2, 0x81010001) )
    goto LABEL_24;
  v9 = this[18];
  v16 = 0;
  PermFlags = Tpm20CmdGetPermFlags(v9, &v16);
  if ( PermFlags < 0 )
    return (unsigned int)PermFlags;
  if ( (v16 & 2) == 0 )
  {
LABEL_24:
    v7 = 2431;
    (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      this[19],
      0);
    PermFlags = TpmSWAntiHammeringMgr::LoadUserAuthFailures(this[20]);
    if ( PermFlags < 0 )
      goto LABEL_32;
    if ( TpmSWAntiHammeringMgr::IsRequestLockedout(
           this[20],
           *((const unsigned __int16 **)a2 + 29),
           *((_QWORD *)a2 + 34),
           *(_DWORD *)((char *)a2 + 6)) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 13, v12, *(unsigned int *)((char *)a2 + 6), *((_QWORD *)a2 + 2));
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0z_EtwWriteTransfer(v13, v11, v12, *((_QWORD *)a2 + 29));
      v7 = 2337;
LABEL_32:
      (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        this[19]);
      if ( v7 == 2431 )
        return (unsigned int)PermFlags;
      goto LABEL_41;
    }
    (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      this[19]);
LABEL_35:
    (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      this[7],
      0);
    if ( *((_DWORD *)a2 + 70) == 2
      || Tpm20Scheduler::VerifyNonAdminUserRequestForQueueLocked((Tpm20Scheduler *)this, a2) )
    {
      *((_DWORD *)a2 + 52) = KeQueryPriorityThread(KeGetCurrentThread());
      Tpm20Scheduler::QueueRequestLocked((Tpm20Scheduler *)this, a2);
      (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        this[7]);
      KeSetEvent((PRKEVENT)this, 0, 0);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 14, v14, *(unsigned int *)((char *)a2 + 6), *((_QWORD *)a2 + 2));
    v7 = 2313;
    (*((void (__fastcall **)(PKDPC, TpmSWAntiHammeringMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      this[7]);
LABEL_41:
    Tpm20Request::FormatTpm20Error(a2, v7);
    Tpm20Context::CompleteTpm20Request(a2, 0);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 12, v10, *(unsigned int *)((char *)a2 + 6), *((_QWORD *)a2 + 2));
  return (unsigned int)-1073741790;
}

```

## disassembly

```asm
0x14000463c  push    rbx
0x14000463e  push    rbp
0x14000463f  push    rsi
0x140004640  push    rdi
0x140004641  sub     rsp, 38h
0x140004645  mov     rax, [rdx+10h]
0x140004649  mov     rbx, rdx
0x14000464c  mov     rsi, rcx
0x14000464f  test    rax, rax
0x140004652  jz      short loc_140004664
0x140004654  cmp     byte ptr [rax+2Ch], 0
0x140004658  jz      short loc_140004664
0x14000465a  mov     ebp, 0C0000120h
0x14000465f  jmp     loc_1400049A0
0x140004664  call    ?IsCommandBlocked@Tpm20Scheduler@@AEAA_NPEBVTpm20Request@@@Z; Tpm20Scheduler::IsCommandBlocked(Tpm20Request const *)
0x140004669  test    al, al
0x14000466b  jz      short loc_1400046C5
0x14000466d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004674  lea     rax, WPP_GLOBAL_Control
0x14000467b  cmp     rcx, rax
0x14000467e  jz      short loc_1400046BB
0x140004680  mov     eax, [rcx+2Ch]
0x140004683  test    al, 4
0x140004685  jz      short loc_1400046BB
0x140004687  cmp     dword ptr [rbx+118h], 2
0x14000468e  lea     r8, aAdminUser; "admin user"
0x140004695  mov     rax, [rbx+10h]
0x140004699  lea     rdx, aNonAdminUser; "non-admin user"
0x1400046a0  mov     r9d, [rbx+6]
0x1400046a4  cmovz   rdx, r8
0x1400046a8  mov     rcx, [rcx+18h]
0x1400046ac  mov     [rsp+58h+var_30], rdx
0x1400046b1  mov     [rsp+58h+var_38], rax
0x1400046b6  call    WPP_SF_Dqs
0x1400046bb  mov     edi, 80280400h
0x1400046c0  jmp     loc_140004930
0x1400046c5  mov     rdx, rbx; struct Tpm20Request *
0x1400046c8  mov     rcx, rsi; this
0x1400046cb  call    ?IsHarmfulCommand@Tpm20Scheduler@@AEAA_NPEAVTpm20Request@@@Z; Tpm20Scheduler::IsHarmfulCommand(Tpm20Request *)
0x1400046d0  test    al, al
0x1400046d2  jz      short loc_14000470B
0x1400046d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400046db  lea     rax, WPP_GLOBAL_Control
0x1400046e2  cmp     rcx, rax
0x1400046e5  jz      short loc_1400046BB
0x1400046e7  mov     eax, [rcx+2Ch]
0x1400046ea  test    al, 4
0x1400046ec  jz      short loc_1400046BB
0x1400046ee  mov     rax, [rbx+10h]
0x1400046f2  mov     edx, 0Bh
0x1400046f7  mov     r9d, [rbx+6]
0x1400046fb  mov     rcx, [rcx+18h]
0x1400046ff  mov     [rsp+58h+var_38], rax
0x140004704  call    WPP_SF_Dq
0x140004709  jmp     short loc_1400046BB
0x14000470b  cmp     dword ptr [rbx+118h], 2
0x140004712  jz      loc_14000489F
0x140004718  cmp     dword ptr [rbx+6], 173h
0x14000471f  jnz     short loc_14000479C
0x140004721  mov     edx, 81010001h; unsigned int
0x140004726  mov     rcx, rbx; this
0x140004729  call    ?IsPrimaryHandleOfType@Tpm20Request@@QEAA_NI@Z; Tpm20Request::IsPrimaryHandleOfType(uint)
0x14000472e  test    al, al
0x140004730  jz      short loc_14000479C
0x140004732  mov     rcx, [rsi+90h]; this
0x140004739  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x14000473e  mov     [rsp+58h+arg_8], 0
0x140004746  call    ?Tpm20CmdGetPermFlags@@YAJPEAVTpmTransport@@PEAI@Z; Tpm20CmdGetPermFlags(TpmTransport *,uint *)
0x14000474b  mov     ebp, eax
0x14000474d  test    eax, eax
0x14000474f  js      loc_1400049A0
0x140004755  mov     eax, [rsp+58h+arg_8]
0x140004759  test    al, 2
0x14000475b  jz      short loc_14000479C
0x14000475d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004764  lea     rax, WPP_GLOBAL_Control
0x14000476b  cmp     rcx, rax
0x14000476e  jz      short loc_140004792
0x140004770  mov     eax, [rcx+2Ch]
0x140004773  test    al, 4
0x140004775  jz      short loc_140004792
0x140004777  mov     rax, [rbx+10h]
0x14000477b  mov     edx, 0Ch
0x140004780  mov     r9d, [rbx+6]
0x140004784  mov     rcx, [rcx+18h]
0x140004788  mov     [rsp+58h+var_38], rax
0x14000478d  call    WPP_SF_Dq
0x140004792  mov     ebp, 0C0000022h
0x140004797  jmp     loc_1400049A0
0x14000479c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400047a3  xor     r8d, r8d
0x1400047a6  mov     rdx, [rsi+98h]
0x1400047ad  mov     edi, 97Fh
0x1400047b2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400047b9  mov     rax, [rax+9C8h]
0x1400047c0  call    _guard_dispatch_icall
0x1400047c5  mov     rcx, [rsi+0A0h]; this
0x1400047cc  call    ?LoadUserAuthFailures@TpmSWAntiHammeringMgr@@QEAAJXZ; TpmSWAntiHammeringMgr::LoadUserAuthFailures(void)
0x1400047d1  mov     ebp, eax
0x1400047d3  test    eax, eax
0x1400047d5  js      short loc_14000484C
0x1400047d7  mov     r9d, [rbx+6]; unsigned int
0x1400047db  mov     r8, [rbx+110h]; unsigned __int64
0x1400047e2  mov     rdx, [rbx+0E8h]; unsigned __int16 *
0x1400047e9  mov     rcx, [rsi+0A0h]; this
0x1400047f0  call    ?IsRequestLockedout@TpmSWAntiHammeringMgr@@QEAAHPEBG_KI@Z; TpmSWAntiHammeringMgr::IsRequestLockedout(ushort const *,unsigned __int64,uint)
0x1400047f5  test    eax, eax
0x1400047f7  jz      loc_14000487E
0x1400047fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004804  lea     rax, WPP_GLOBAL_Control
0x14000480b  cmp     rcx, rax
0x14000480e  jz      short loc_140004832
0x140004810  mov     eax, [rcx+2Ch]
0x140004813  test    al, 4
0x140004815  jz      short loc_140004832
0x140004817  mov     rax, [rbx+10h]
0x14000481b  mov     edx, 0Dh
0x140004820  mov     r9d, [rbx+6]
0x140004824  mov     rcx, [rcx+18h]
0x140004828  mov     [rsp+58h+var_38], rax
0x14000482d  call    WPP_SF_Dq
0x140004832  test    cs:TPMEnableBits, 1
0x140004839  jz      short loc_140004847
0x14000483b  mov     r9, [rbx+0E8h]
0x140004842  call    McTemplateK0z_EtwWriteTransfer
0x140004847  mov     edi, 921h
0x14000484c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140004853  mov     rdx, [rsi+98h]
0x14000485a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140004861  mov     rax, [rax+9D0h]
0x140004868  call    _guard_dispatch_icall
0x14000486d  cmp     edi, 97Fh
0x140004873  jnz     loc_140004930
0x140004879  jmp     loc_1400049A0
0x14000487e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140004885  mov     rdx, [rsi+98h]
0x14000488c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140004893  mov     rax, [rax+9D0h]
0x14000489a  call    _guard_dispatch_icall
0x14000489f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400048a6  xor     r8d, r8d
0x1400048a9  mov     rdx, [rsi+38h]
0x1400048ad  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400048b4  mov     rax, [rax+9C8h]
0x1400048bb  call    _guard_dispatch_icall
0x1400048c0  cmp     dword ptr [rbx+118h], 2
0x1400048c7  jz      short loc_140004946
0x1400048c9  mov     rdx, rbx; struct Tpm20Request *
0x1400048cc  mov     rcx, rsi; this
0x1400048cf  call    ?VerifyNonAdminUserRequestForQueueLocked@Tpm20Scheduler@@AEAA_NPEBVTpm20Request@@@Z; Tpm20Scheduler::VerifyNonAdminUserRequestForQueueLocked(Tpm20Request const *)
0x1400048d4  test    al, al
0x1400048d6  jnz     short loc_140004946
0x1400048d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400048df  lea     rax, WPP_GLOBAL_Control
0x1400048e6  cmp     rcx, rax
0x1400048e9  jz      short loc_14000490D
0x1400048eb  mov     eax, [rcx+2Ch]
0x1400048ee  test    al, 4
0x1400048f0  jz      short loc_14000490D
0x1400048f2  mov     rax, [rbx+10h]
0x1400048f6  mov     edx, 0Eh
0x1400048fb  mov     r9d, [rbx+6]
0x1400048ff  mov     rcx, [rcx+18h]
0x140004903  mov     [rsp+58h+var_38], rax
0x140004908  call    WPP_SF_Dq
0x14000490d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140004914  mov     edi, 909h
0x140004919  mov     rdx, [rsi+38h]
0x14000491d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140004924  mov     rax, [rax+9D0h]
0x14000492b  call    _guard_dispatch_icall
0x140004930  mov     edx, edi; unsigned int
0x140004932  mov     rcx, rbx; this
0x140004935  call    ?FormatTpm20Error@Tpm20Request@@QEAAXI@Z; Tpm20Request::FormatTpm20Error(uint)
0x14000493a  xor     edx, edx; int
0x14000493c  mov     rcx, rbx; this
0x14000493f  call    ?CompleteTpm20Request@Tpm20Context@@SAXPEAVTpm20Request@@J@Z; Tpm20Context::CompleteTpm20Request(Tpm20Request *,long)
0x140004944  jmp     short loc_14000499E
0x140004946  mov     rcx, gs:188h; Thread
0x14000494f  call    cs:__imp_KeQueryPriorityThread
0x140004956  nop     dword ptr [rax+rax+00h]
0x14000495b  mov     rdx, rbx; struct Tpm20Request *
0x14000495e  mov     rcx, rsi; this
0x140004961  mov     [rbx+0D0h], eax
0x140004967  call    ?QueueRequestLocked@Tpm20Scheduler@@AEAAXPEAVTpm20Request@@@Z; Tpm20Scheduler::QueueRequestLocked(Tpm20Request *)
0x14000496c  mov     r9, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140004973  mov     rdx, [rsi+38h]
0x140004977  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000497e  mov     rax, [r9+9D0h]
0x140004985  call    _guard_dispatch_icall
0x14000498a  xor     r8d, r8d; Wait
0x14000498d  xor     edx, edx; Increment
0x14000498f  mov     rcx, rsi; Event
0x140004992  call    cs:__imp_KeSetEvent
0x140004999  nop     dword ptr [rax+rax+00h]
0x14000499e  xor     ebp, ebp
0x1400049a0  mov     eax, ebp
0x1400049a2  add     rsp, 38h
0x1400049a6  pop     rdi
0x1400049a7  pop     rsi
0x1400049a8  pop     rbp
0x1400049a9  pop     rbx
0x1400049aa  retn
```
