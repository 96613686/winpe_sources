# Tpm20Scheduler::DoUserRequest(void)

- ea: `0x1400171d0`
- end: `0x1400179be`
- name: `?DoUserRequest@Tpm20Scheduler@@AEAAXXZ`
- size: `2030`
- prototype: `void __fastcall(Tpm20Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400179c4`

## callees

- `0x140001148`
- `0x1400078b8`
- `0x1400088ec`
- `0x140009224`
- `0x140009278`
- `0x140009fc8`
- `0x14000b6c8`
- `0x14000e0b0`
- `0x14000e98c`
- `0x140010294`
- `0x140016ac4`
- `0x140016afc`
- `0x1400171d0`
- `0x14001a3a0`
- `0x14001b1ac`
- `0x14001b220`
- `0x14001c1ac`
- `0x14001c234`
- `0x14002215c`
- `0x140039740`
- `0x140039780`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!NtQueryInformationProcess` at `0x1400174db`
- `ntoskrnl!NtQueryInformationProcess` at `0x1400174db`
- `ntoskrnl!KeSetPriorityThread` at `0x14001723a`
- `ntoskrnl!KeSetPriorityThread` at `0x140017991`
- `ntoskrnl!KeSetPriorityThread` at `0x14001723a`
- `ntoskrnl!KeSetPriorityThread` at `0x140017991`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001721a`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001721a`

## string_xrefs

- `0x140017557`: `LastClearCommandBootId`
- `0x1400176d5`: `LastClearCommandBootId`
- `0x14001766a`: `LastClearCommandTimestamp`
- `0x140017795`: `LastClearCommandTimestamp`

## pseudocode

```c
void __fastcall Tpm20Scheduler::DoUserRequest(Tpm20Scheduler *this)
{
  int v2; // r12d
  KPRIORITY v3; // r13d
  KPRIORITY PriorityThread; // eax
  KPRIORITY v5; // edx
  int IsRequestLockedout; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  PDEVICE_OBJECT v9; // rcx
  int v10; // r8d
  unsigned int v11; // r15d
  __int64 v12; // r9
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  const wchar_t *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // r9
  int v21; // r14d
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  unsigned int v27; // esi
  int v28; // eax
  int v29; // eax
  int v30; // eax
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  int v33; // [rsp+40h] [rbp-89h] BYREF
  int v34; // [rsp+48h] [rbp-81h] BYREF
  __int64 v35; // [rsp+50h] [rbp-79h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-71h] BYREF
  const wchar_t *v37; // [rsp+60h] [rbp-69h] BYREF
  _DWORD ProcessInformation[24]; // [rsp+70h] [rbp-59h] BYREF

  v2 = 0;
  v3 = 16;
  if ( !*((_QWORD *)this + 13) )
    *((_QWORD *)this + 13) = KeGetCurrentThread();
  PriorityThread = KeQueryPriorityThread(*((PKTHREAD *)this + 13));
  v5 = *(_DWORD *)(*((_QWORD *)this + 10) + 208LL);
  if ( PriorityThread > v5 )
  {
    v3 = KeSetPriorityThread(*((PKTHREAD *)this + 13), v5);
    v2 = 1;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 280LL) == 2
    || ((*((void (__fastcall **)(PKDPC, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
          *((_QWORD *)this + 19),
          0),
        IsRequestLockedout = TpmSWAntiHammeringMgr::IsRequestLockedout(
                               *((TpmSWAntiHammeringMgr **)this + 20),
                               *(const unsigned __int16 **)(*((_QWORD *)this + 10) + 232LL),
                               *(_QWORD *)(*((_QWORD *)this + 10) + 272LL),
                               *(_DWORD *)(*((_QWORD *)this + 10) + 6LL)),
        (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
          *((_QWORD *)this + 19)),
        !IsRequestLockedout) )
  {
    v11 = Tpm20ResourceMgr::SubmitRequest(*((Tpm20ResourceMgr **)this + 17), *((struct Tpm20Request **)this + 10));
    if ( v11 )
      goto LABEL_80;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        v8,
        *(unsigned int *)(*((_QWORD *)this + 10) + 6LL),
        *(_QWORD *)(*((_QWORD *)this + 10) + 16LL));
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0z_EtwWriteTransfer(v9, v7, v8, *(_QWORD *)(*((_QWORD *)this + 10) + 232LL));
    Tpm20Request::FormatTpm20Error(*((Tpm20Request **)this + 10), 0x921u);
    v11 = 0;
  }
  v12 = *((_QWORD *)this + 10);
  v13 = *(_DWORD *)(v12 + 192);
  if ( !v13 )
  {
    v14 = *(_DWORD *)(v12 + 6);
    if ( v14 == 313 )
    {
      v15 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids);
      if ( (TPMEnableBits & 2) != 0 )
        McTemplateK0dqq_EtwWriteTransfer(v15, (unsigned int)TPM_RESET_LOCKOUT_SUCCESS, v10, 28, 225, 0);
      (*((void (__fastcall **)(PKDPC, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        *((_QWORD *)this + 19),
        0);
      TpmSWAntiHammeringMgr::RemoveAllFromAuthFailureList(*((TpmSWAntiHammeringMgr **)this + 20));
      (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        *((_QWORD *)this + 19));
    }
    else if ( v14 == 294 )
    {
      v16 = L"TPM Driver";
      if ( *(_QWORD *)(v12 + 240) )
        v16 = *(const wchar_t **)(v12 + 240);
      if ( (TPMEnableBits & 2) != 0 )
        McTemplateK0dqz_EtwWriteTransfer(294, (unsigned int)TPM_CLEAR_SUCCESS, v10, 28, 241, (__int64)v16);
      if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v37 = v16;
        v33 = 294;
        v35 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v17,
          (unsigned int)&dword_140041AD4,
          v18,
          v19,
          (__int64)&v35,
          (__int64)&v33,
          (__int64)&v37);
      }
      memset(ProcessInformation, 0, sizeof(ProcessInformation));
      ReturnLength = 0;
      v20 = (unsigned int)NtQueryInformationProcess(
                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                            (PROCESSINFOCLASS)64,
                            ProcessInformation,
                            0x60u,
                            &ReturnLength);
      if ( (int)(v20 + 0x80000000) < 0 || (_DWORD)v20 == -2147483643 )
      {
        v21 = ProcessInformation[15];
      }
      else
      {
        v21 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids, v20);
      }
      v33 = v21;
      v22 = TpmRegistry::AssignValue(25, L"LastClearCommandBootId", 4, &v33, 4);
      if ( v22 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v22);
      }
      v34 = 0;
      v23 = TpmRegistry::QueryValue(25, L"ClearCount", 4, &v34, 4, 0);
      if ( v23 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v23);
      }
      v33 = ++v34;
      v24 = TpmRegistry::AssignValue(25, L"ClearCount", 4, &v33, 4);
      if ( v24 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v24);
      }
      v25 = MEMORY[0xFFFFF78000000014];
      v35 = MEMORY[0xFFFFF78000000014];
      v26 = TpmRegistry::AssignValue(25, L"LastClearCommandTimestamp", 11, &v35, 8);
      if ( v26 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v26);
      }
      v33 = v21;
      v27 = (v34 & 7) + 27;
      v28 = TpmRegistry::AssignValue(v27, L"LastClearCommandBootId", 4, &v33, 4);
      if ( v28 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v28);
      }
      v33 = v34;
      v29 = TpmRegistry::AssignValue(v27, L"ClearCount", 4, &v33, 4);
      if ( v29 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v29);
      }
      v35 = v25;
      v30 = TpmRegistry::AssignValue(v27, L"LastClearCommandTimestamp", 11, &v35, 8);
      if ( v30 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
          (unsigned int)v30);
      }
    }
    goto LABEL_80;
  }
  if ( v13 != 1 && (v13 & 0xBF) != 0x8E && v13 != 341 )
  {
    if ( v13 != 2337 )
      goto LABEL_80;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_80;
    v32 = 39;
LABEL_79:
    WPP_SF_(v31->AttachedDevice, v32, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids);
    goto LABEL_80;
  }
  if ( *(_DWORD *)(v12 + 280) != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
        *(_QWORD *)(v12 + 16),
        v13);
    (*((void (__fastcall **)(PKDPC, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      *((_QWORD *)this + 19),
      0);
    TpmSWAntiHammeringMgr::AddAuthFailure(
      *((TpmSWAntiHammeringMgr **)this + 20),
      *(const unsigned __int16 **)(*((_QWORD *)this + 10) + 232LL),
      *(const unsigned __int16 **)(*((_QWORD *)this + 10) + 240LL),
      *(_QWORD *)(*((_QWORD *)this + 10) + 272LL));
    (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      *((_QWORD *)this + 19));
  }
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v32 = 38;
    goto LABEL_79;
  }
LABEL_80:
  (*((void (__fastcall **)(PKDPC, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    *((_QWORD *)this + 7),
    0);
  Tpm20Context::CompleteTpm20Request(*((struct Tpm20Request **)this + 10), v11);
  *((_QWORD *)this + 10) = 0;
  Tpm20Scheduler::WakeCancelWaitersLocked(this);
  (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    *((_QWORD *)this + 7));
  if ( v11 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids, v11);
  if ( v2 )
    KeSetPriorityThread(*((PKTHREAD *)this + 13), v3);
}

```

## disassembly

```asm
0x1400171d0  push    rbp
0x1400171d2  push    rbx
0x1400171d3  push    rsi
0x1400171d4  push    rdi
0x1400171d5  push    r12
0x1400171d7  push    r13
0x1400171d9  push    r14
0x1400171db  push    r15
0x1400171dd  lea     rbp, [rsp-1Fh]
0x1400171e2  sub     rsp, 0E8h
0x1400171e9  mov     rax, cs:__security_cookie
0x1400171f0  xor     rax, rsp
0x1400171f3  mov     [rbp+57h+var_50], rax
0x1400171f7  xor     esi, esi
0x1400171f9  mov     rdi, rcx
0x1400171fc  mov     r12d, esi
0x1400171ff  lea     r13d, [rsi+10h]
0x140017203  cmp     [rcx+68h], rsi
0x140017207  jnz     short loc_140017216
0x140017209  mov     rax, gs:188h
0x140017212  mov     [rcx+68h], rax
0x140017216  mov     rcx, [rcx+68h]; Thread
0x14001721a  call    cs:__imp_KeQueryPriorityThread
0x140017221  nop     dword ptr [rax+rax+00h]
0x140017226  mov     ecx, eax
0x140017228  mov     rax, [rdi+50h]
0x14001722c  mov     edx, [rax+0D0h]; Priority
0x140017232  cmp     ecx, edx
0x140017234  jle     short loc_14001724F
0x140017236  mov     rcx, [rdi+68h]; Thread
0x14001723a  call    cs:__imp_KeSetPriorityThread
0x140017241  nop     dword ptr [rax+rax+00h]
0x140017246  mov     r13d, eax
0x140017249  mov     r12d, 1
0x14001724f  mov     rcx, [rdi+50h]
0x140017253  lea     r14, WPP_GLOBAL_Control
0x14001725a  cmp     dword ptr [rcx+118h], 2
0x140017261  jz      loc_140017332
0x140017267  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001726e  xor     r8d, r8d
0x140017271  mov     rdx, [rdi+98h]
0x140017278  mov     rax, [rcx+9C8h]
0x14001727f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140017286  call    _guard_dispatch_icall
0x14001728b  mov     rdx, [rdi+50h]
0x14001728f  mov     rcx, [rdi+0A0h]; this
0x140017296  mov     r9d, [rdx+6]; unsigned int
0x14001729a  mov     r8, [rdx+110h]; unsigned __int64
0x1400172a1  mov     rdx, [rdx+0E8h]; unsigned __int16 *
0x1400172a8  call    ?IsRequestLockedout@TpmSWAntiHammeringMgr@@QEAAHPEBG_KI@Z; TpmSWAntiHammeringMgr::IsRequestLockedout(ushort const *,unsigned __int64,uint)
0x1400172ad  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400172b4  mov     ebx, eax
0x1400172b6  mov     rdx, [rdi+98h]
0x1400172bd  mov     rax, [rcx+9D0h]
0x1400172c4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400172cb  call    _guard_dispatch_icall
0x1400172d0  test    ebx, ebx
0x1400172d2  jz      short loc_140017332
0x1400172d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400172db  cmp     rcx, r14
0x1400172de  jz      short loc_140017306
0x1400172e0  mov     eax, [rcx+2Ch]
0x1400172e3  test    al, 4
0x1400172e5  jz      short loc_140017306
0x1400172e7  mov     r9, [rdi+50h]
0x1400172eb  mov     edx, 1Bh
0x1400172f0  mov     rcx, [rcx+18h]
0x1400172f4  mov     rax, [r9+10h]
0x1400172f8  mov     r9d, [r9+6]
0x1400172fc  mov     [rsp+120h+ReturnLength], rax
0x140017301  call    WPP_SF_Dq
0x140017306  test    cs:TPMEnableBits, 1
0x14001730d  jz      short loc_14001731F
0x14001730f  mov     r9, [rdi+50h]
0x140017313  mov     r9, [r9+0E8h]
0x14001731a  call    McTemplateK0z_EtwWriteTransfer
0x14001731f  mov     rcx, [rdi+50h]; this
0x140017323  mov     edx, 921h; unsigned int
0x140017328  call    ?FormatTpm20Error@Tpm20Request@@QEAAXI@Z; Tpm20Request::FormatTpm20Error(uint)
0x14001732d  mov     r15d, esi
0x140017330  jmp     short loc_14001734D
0x140017332  mov     rdx, [rdi+50h]; struct Tpm20Request *
0x140017336  mov     rcx, [rdi+88h]; this
0x14001733d  call    ?SubmitRequest@Tpm20ResourceMgr@@QEAAJPEAVTpm20Request@@@Z; Tpm20ResourceMgr::SubmitRequest(Tpm20Request *)
0x140017342  mov     r15d, eax
0x140017345  test    eax, eax
0x140017347  jnz     loc_1400178FE
0x14001734d  mov     r9, [rdi+50h]
0x140017351  mov     ecx, [r9+0C0h]
0x140017358  test    ecx, ecx
0x14001735a  jnz     loc_1400177E4
0x140017360  mov     ecx, [r9+6]
0x140017364  cmp     ecx, 139h
0x14001736a  jnz     loc_140017415
0x140017370  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017377  cmp     rcx, r14
0x14001737a  jz      short loc_140017398
0x14001737c  mov     eax, [rcx+2Ch]
0x14001737f  test    al, 4
0x140017381  jz      short loc_140017398
0x140017383  mov     rcx, [rcx+18h]
0x140017387  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x14001738e  mov     edx, 1Ch
0x140017393  call    WPP_SF_
0x140017398  test    cs:TPMEnableBits, 2
0x14001739f  jz      short loc_1400173BF
0x1400173a1  mov     dword ptr [rsp+120h+var_F8], esi
0x1400173a5  lea     rdx, TPM_RESET_LOCKOUT_SUCCESS
0x1400173ac  mov     r9d, 1Ch
0x1400173b2  mov     dword ptr [rsp+120h+ReturnLength], 7E1h
0x1400173ba  call    McTemplateK0dqq_EtwWriteTransfer
0x1400173bf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400173c6  xor     r8d, r8d
0x1400173c9  mov     rdx, [rdi+98h]
0x1400173d0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400173d7  mov     rax, [rax+9C8h]
0x1400173de  call    _guard_dispatch_icall
0x1400173e3  mov     rcx, [rdi+0A0h]; this
0x1400173ea  call    ?RemoveAllFromAuthFailureList@TpmSWAntiHammeringMgr@@QEAAJXZ; TpmSWAntiHammeringMgr::RemoveAllFromAuthFailureList(void)
0x1400173ef  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400173f6  mov     rdx, [rdi+98h]
0x1400173fd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140017404  mov     rax, [rax+9D0h]
0x14001740b  call    _guard_dispatch_icall
0x140017410  jmp     loc_1400178FE
0x140017415  cmp     ecx, 126h
0x14001741b  jnz     loc_1400178FE
0x140017421  mov     rax, [r9+0F0h]
0x140017428  lea     rbx, aTpmDriver; "TPM Driver"
0x14001742f  test    rax, rax
0x140017432  cmovnz  rbx, rax
0x140017436  test    cs:TPMEnableBits, 2
0x14001743d  jz      short loc_14001745E
0x14001743f  mov     [rsp+120h+var_F8], rbx
0x140017444  lea     rdx, TPM_CLEAR_SUCCESS
0x14001744b  mov     r9d, 1Ch
0x140017451  mov     dword ptr [rsp+120h+ReturnLength], 7F1h
0x140017459  call    McTemplateK0dqz_EtwWriteTransfer
0x14001745e  mov     eax, cs:dword_1400470A0
0x140017464  cmp     eax, 5
0x140017467  jbe     short loc_1400174AE
0x140017469  call    _tlgKeywordOn
0x14001746e  test    al, al
0x140017470  jz      short loc_1400174AE
0x140017472  lea     rax, [rbp+57h+var_C0]
0x140017476  mov     [rbp+57h+var_C0], rbx
0x14001747a  mov     [rsp+120h+var_F0], rax
0x14001747f  lea     rdx, dword_140041AD4
0x140017486  lea     rax, [rsp+120h+var_E0]
0x14001748b  mov     [rsp+120h+var_E0], 126h
0x140017493  mov     [rsp+120h+var_F8], rax
0x140017498  lea     rax, [rbp+57h+var_D0]
0x14001749c  mov     [rsp+120h+ReturnLength], rax
0x1400174a1  mov     [rbp+57h+var_D0], 1000000h
0x1400174a9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1400174ae  mov     ebx, 60h ; '`'
0x1400174b3  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x1400174b7  mov     r8d, ebx; Size
0x1400174ba  xor     edx, edx; Val
0x1400174bc  call    memset
0x1400174c1  lea     rax, [rbp+57h+var_C8]
0x1400174c5  mov     [rbp+57h+var_C8], esi
0x1400174c8  mov     r9d, ebx; ProcessInformationLength
0x1400174cb  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1400174d0  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1400174d4  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400174d8  lea     edx, [rbx-20h]; ProcessInformationClass
0x1400174db  call    cs:__imp_NtQueryInformationProcess
0x1400174e2  nop     dword ptr [rax+rax+00h]
0x1400174e7  mov     r9d, eax
0x1400174ea  mov     eax, 80000000h
0x1400174ef  lea     ecx, [r9+rax]
0x1400174f3  test    eax, ecx
0x1400174f5  jnz     short loc_140017534
0x1400174f7  cmp     r9d, 80000005h
0x1400174fe  jz      short loc_140017534
0x140017500  mov     r14d, esi
0x140017503  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001750a  lea     rbx, WPP_GLOBAL_Control
0x140017511  cmp     rcx, rbx
0x140017514  jz      short loc_14001753F
0x140017516  mov     eax, [rcx+2Ch]
0x140017519  test    al, 2
0x14001751b  jz      short loc_14001753F
0x14001751d  mov     rcx, [rcx+18h]
0x140017521  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x140017528  mov     edx, 1Dh
0x14001752d  call    WPP_SF_d
0x140017532  jmp     short loc_14001753F
0x140017534  mov     r14d, [rbp+57h+var_74]
0x140017538  lea     rbx, WPP_GLOBAL_Control
0x14001753f  mov     r8d, 4
0x140017545  mov     [rsp+120h+var_E0], r14d
0x14001754a  lea     r9, [rsp+120h+var_E0]
0x14001754f  mov     dword ptr [rsp+120h+ReturnLength], 4
0x140017557  lea     rdx, aLastclearcomma_0; "LastClearCommandBootId"
0x14001755e  lea     ecx, [r8+15h]
0x140017562  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140017567  test    eax, eax
0x140017569  jns     short loc_140017597
0x14001756b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017572  cmp     rcx, rbx
0x140017575  jz      short loc_140017597
0x140017577  mov     edx, [rcx+2Ch]
0x14001757a  test    dl, 2
0x14001757d  jz      short loc_140017597
0x14001757f  mov     rcx, [rcx+18h]
0x140017583  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x14001758a  mov     edx, 1Eh
0x14001758f  mov     r9d, eax
0x140017592  call    WPP_SF_d
0x140017597  mov     eax, 4
0x14001759c  mov     [rsp+120h+var_F8], rsi
0x1400175a1  lea     r9, [rsp+120h+var_D8]
0x1400175a6  mov     [rsp+120h+var_D8], esi
0x1400175aa  mov     r8d, eax
0x1400175ad  mov     dword ptr [rsp+120h+ReturnLength], eax
0x1400175b1  lea     rdx, aClearcount; "ClearCount"
0x1400175b8  lea     ecx, [rax+15h]
0x1400175bb  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x1400175c0  test    eax, eax
0x1400175c2  jns     short loc_1400175F0
0x1400175c4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400175cb  cmp     rcx, rbx
0x1400175ce  jz      short loc_1400175F0
0x1400175d0  mov     edx, [rcx+2Ch]
0x1400175d3  test    dl, 2
0x1400175d6  jz      short loc_1400175F0
0x1400175d8  mov     rcx, [rcx+18h]
0x1400175dc  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x1400175e3  mov     edx, 1Fh
0x1400175e8  mov     r9d, eax
0x1400175eb  call    WPP_SF_d
0x1400175f0  mov     eax, [rsp+120h+var_D8]
0x1400175f4  lea     r9, [rsp+120h+var_E0]
0x1400175f9  inc     eax
0x1400175fb  lea     rdx, aClearcount; "ClearCount"
0x140017602  mov     [rsp+120h+var_D8], eax
0x140017606  mov     [rsp+120h+var_E0], eax
0x14001760a  mov     eax, 4
0x14001760f  mov     r8d, eax
0x140017612  mov     dword ptr [rsp+120h+ReturnLength], eax
0x140017616  lea     ecx, [rax+15h]
0x140017619  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x14001761e  test    eax, eax
0x140017620  jns     short loc_14001764E
0x140017622  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017629  cmp     rcx, rbx
0x14001762c  jz      short loc_14001764E
0x14001762e  mov     edx, [rcx+2Ch]
0x140017631  test    dl, 2
0x140017634  jz      short loc_14001764E
0x140017636  mov     rcx, [rcx+18h]
0x14001763a  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x140017641  mov     edx, 20h ; ' '
0x140017646  mov     r9d, eax
0x140017649  call    WPP_SF_d
0x14001764e  mov     r8d, 0Bh
0x140017654  mov     dword ptr [rsp+120h+ReturnLength], 8
0x14001765c  mov     rbx, 0FFFFF78000000014h
0x140017666  lea     r9, [rbp+57h+var_D0]
0x14001766a  lea     rdx, aLastclearcomma; "LastClearCommandTimestamp"
0x140017671  lea     ecx, [r8+0Eh]
0x140017675  mov     rbx, [rbx]
0x140017678  mov     [rbp+57h+var_D0], rbx
0x14001767c  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140017681  test    eax, eax
0x140017683  jns     short loc_1400176B8
0x140017685  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001768c  lea     rdx, WPP_GLOBAL_Control
0x140017693  cmp     rcx, rdx
0x140017696  jz      short loc_1400176B8
0x140017698  mov     edx, [rcx+2Ch]
0x14001769b  test    dl, 2
0x14001769e  jz      short loc_1400176B8
0x1400176a0  mov     rcx, [rcx+18h]
0x1400176a4  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x1400176ab  mov     edx, 21h ; '!'
0x1400176b0  mov     r9d, eax
0x1400176b3  call    WPP_SF_d
0x1400176b8  mov     esi, [rsp+120h+var_D8]
0x1400176bc  lea     r9, [rsp+120h+var_E0]
0x1400176c1  mov     eax, 4
0x1400176c6  mov     [rsp+120h+var_E0], r14d
0x1400176cb  and     esi, 7
0x1400176ce  mov     dword ptr [rsp+120h+ReturnLength], eax
0x1400176d2  add     esi, 1Bh
0x1400176d5  lea     rdx, aLastclearcomma_0; "LastClearCommandBootId"
0x1400176dc  mov     ecx, esi
0x1400176de  mov     r8d, eax
0x1400176e1  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x1400176e6  test    eax, eax
0x1400176e8  jns     short loc_14001771F
0x1400176ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400176f1  lea     r14, WPP_GLOBAL_Control
0x1400176f8  cmp     rcx, r14
0x1400176fb  jz      short loc_140017726
0x1400176fd  mov     edx, [rcx+2Ch]
0x140017700  test    dl, 2
0x140017703  jz      short loc_140017726
  ... truncated ...
```
