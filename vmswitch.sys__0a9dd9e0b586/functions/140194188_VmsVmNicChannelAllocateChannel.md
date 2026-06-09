# VmsVmNicChannelAllocateChannel

- ea: `0x140194188`
- end: `0x14019451b`
- name: `VmsVmNicChannelAllocateChannel`
- size: `915`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140194524`
- `0x140194680`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14006e590`
- `0x140071520`
- `0x14008497c`
- `0x140088840`
- `0x14008e78c`
- `0x1400a7b7c`
- `0x140187340`
- `0x140193e60`
- `0x140194188`
- `0x140194cbc`
- `0x140197054`
- `0x14019719c`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140194216`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140194216`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194225`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194225`
- `ntoskrnl!ExRundownCompleted` at `0x140194234`
- `ntoskrnl!ExRundownCompleted` at `0x140194234`
- `vmbkmclr!VmbChannelInitSetPrimaryChannel` at `0x140194416`
- `vmbkmclr!VmbChannelInitSetPrimaryChannel` at `0x140194416`
- `vmbkmclr!VmbChannelInitSetPacketPoolTag` at `0x1401943a2`
- `vmbkmclr!VmbChannelInitSetPacketPoolTag` at `0x1401943a2`
- `vmbkmclr!VmbServerChannelInitSetTargetVtl` at `0x14019434d`
- `vmbkmclr!VmbServerChannelInitSetTargetVtl` at `0x14019434d`
- `vmbkmclr!VmbChannelSetPointer` at `0x140194334`
- `vmbkmclr!VmbChannelSetPointer` at `0x140194334`
- `vmbkmclr!VmbChannelGetServicingState` at `0x1401943fa`
- `vmbkmclr!VmbChannelGetServicingState` at `0x14019444f`
- `vmbkmclr!VmbChannelGetServicingState` at `0x1401943fa`
- `vmbkmclr!VmbChannelGetServicingState` at `0x14019444f`

## string_xrefs

- `0x1401943c1`: `oldState == VmsChannelStateDeleted`

## pseudocode

```c
__int64 __fastcall VmsVmNicChannelAllocateChannel(__int64 a1, __int16 a2, _QWORD *a3, char a4)
{
  __int16 v6; // r12
  char v8; // r15
  int inited; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int128 v13; // xmm1
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // r9d
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  __int16 v24; // dx
  int v25; // edx
  int v26; // r8d
  int v27; // ecx
  int v29; // [rsp+20h] [rbp-98h]
  char v30; // [rsp+28h] [rbp-90h]
  __int64 v31; // [rsp+28h] [rbp-90h]
  char v32; // [rsp+30h] [rbp-88h]
  char v33; // [rsp+38h] [rbp-80h]
  __int128 v34; // [rsp+50h] [rbp-68h] BYREF
  __int128 v35; // [rsp+60h] [rbp-58h] BYREF
  char v36; // [rsp+C0h] [rbp+8h] BYREF

  v36 = 0;
  v6 = a2;
  v8 = 0;
  if ( a1 && *(_QWORD *)(a1 + 680) )
  {
    if ( !IsVmsVmInitialized )
    {
      inited = -1073741811;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, a2, 20, 25, (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids, 13);
      goto LABEL_26;
    }
    memset(a3, 0, 0x78u);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)a3 + 13);
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a3 + 13);
    ExRundownCompleted((PEX_RUNDOWN_REF)a3 + 13);
    a3[1] = a1;
    *((_WORD *)a3 + 8) = v6;
    v12 = *(_QWORD *)(a1 + 8);
    v13 = *(_OWORD *)(a1 + 1536);
    v30 = *(_BYTE *)(*(_QWORD *)(a1 + 680) + 9464LL);
    v34 = *(_OWORD *)(a1 + 1552);
    v35 = v13;
    v14 = VmsVmNicChannelFindOrAllocate(
            (unsigned int)&v36,
            v12,
            (unsigned int)&v35,
            (unsigned int)&v34,
            v6,
            v30,
            (__int64)a3,
            (__int64)&v36);
    v18 = *(_QWORD *)(a1 + 680);
    inited = v14;
    if ( v14 < 0 )
    {
      v19 = v18 + 72;
      v33 = v14;
      v32 = (char)a3;
      v20 = 26;
      v31 = v19;
LABEL_7:
      WPP_RECORDER_SF_Zqd(
        VmsIfrNicLog,
        v15,
        v17,
        v20,
        (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
        v31,
        v32,
        v33);
      goto LABEL_26;
    }
    if ( *(_BYTE *)(v18 + 9464) == 1 && !v36 )
    {
      if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
        McTemplateK0ztt_EtwWriteTransfer(v16, v15, v17, *(_QWORD *)(v18 + 80), 1, 0);
      WPP_RECORDER_SF_Zq(v16, v15, v17, v18, v29, *(_QWORD *)(a1 + 680) + 72LL, (char)a3);
    }
    VmbChannelSetPointer(*a3, a3);
    if ( *(_BYTE *)(a1 + 1568) && (inited = VmbServerChannelInitSetTargetVtl(*a3), inited < 0) )
    {
      WPP_RECORDER_SF_ZqDd(
        *(_DWORD *)(a1 + 680) + 72,
        v21,
        v22,
        v23,
        v29,
        *(_QWORD *)(a1 + 680) + 72LL,
        (char)a3,
        *(_BYTE *)(a1 + 1568),
        inited);
    }
    else
    {
      VmbChannelInitSetPacketPoolTag(*a3, 1765962582, 1866625878);
      if ( _InterlockedExchange((volatile __int32 *)a3 + 28, 1) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v24,
          19,
          10,
          (__int64)WPP_7f9c2ac2fa983072b55dd04e2689be0b_Traceguids,
          "oldState == VmsChannelStateDeleted");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v8 = 1;
      if ( *((_WORD *)a3 + 8) )
      {
        if ( !(unsigned __int8)VmbChannelGetServicingState(*a3) )
        {
          inited = VmbChannelInitSetPrimaryChannel(*a3, *(_QWORD *)(a1 + 16), *((unsigned __int16 *)a3 + 8));
          if ( inited < 0 )
          {
            v20 = 29;
            v33 = inited;
            v32 = (char)a3;
            v31 = *(_QWORD *)(a1 + 680) + 72LL;
            goto LABEL_7;
          }
        }
      }
      if ( !(unsigned __int8)VmbChannelGetServicingState(*a3) )
        VmsVmNicChannelInitializePreEnableParameters(a1, a4, a3);
      VmsVmNicChannelInitializeCallbacks(a3);
      *((_DWORD *)a3 + 8) = 0;
      a3[5] = 0;
      a3[6] = a3 + 5;
    }
  }
  else
  {
    inited = -1073741811;
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      24,
      (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
      "!\"VmsVmNicChannelAllocateChannel: VmNicExt or VmNicExt->Nic is NULL\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
LABEL_26:
  LOBYTE(v11) = a4;
  VmsTraceLoggingNicChannelAllocate(v11, v10, (unsigned int)inited);
  if ( inited < 0 )
  {
    v27 = VmsIfrLog;
    if ( a1 )
      v27 = VmsIfrNicLog;
    WPP_RECORDER_SF_qHd(v27, v25, v26, 30, (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids, a1, v6, inited);
    if ( v8 )
      VmsVmNicChannelDeleteChannel(a3);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140194188  mov     rax, rsp
0x14019418b  push    rbx
0x14019418c  push    rbp
0x14019418d  push    rsi
0x14019418e  push    rdi
0x14019418f  push    r12
0x140194191  push    r13
0x140194193  push    r14
0x140194195  push    r15
0x140194197  sub     rsp, 78h
0x14019419b  xor     r13d, r13d
0x14019419e  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x1401941a5  mov     [rax+8], r13b
0x1401941a9  mov     r14b, r9b
0x1401941ac  mov     rbx, r8
0x1401941af  movzx   r12d, dx
0x1401941b3  mov     rsi, rcx
0x1401941b6  mov     r15b, r13b
0x1401941b9  test    rcx, rcx
0x1401941bc  jz      loc_140194489
0x1401941c2  cmp     [rcx+2A8h], r13
0x1401941c9  jz      loc_140194489
0x1401941cf  cmp     cs:IsVmsVmInitialized, r13b
0x1401941d6  jnz     short loc_140194201
0x1401941d8  mov     edi, 0C000000Dh
0x1401941dd  mov     rcx, cs:VmsIfrNicLog
0x1401941e4  lea     r9d, [r13+19h]
0x1401941e8  mov     dword ptr [rsp+0B8h+var_90], edi
0x1401941ec  lea     r8d, [r13+14h]
0x1401941f0  mov     dl, 2
0x1401941f2  mov     [rsp+0B8h+var_98], rbp
0x1401941f7  call    WPP_RECORDER_SF_d
0x1401941fc  jmp     loc_1401944BA
0x140194201  xor     edx, edx; Val
0x140194203  mov     rcx, rbx; void *
0x140194206  lea     r8d, [rdx+78h]; Size
0x14019420a  call    memset
0x14019420f  lea     rbp, [rbx+68h]
0x140194213  mov     rcx, rbp; RunRef
0x140194216  call    cs:__imp_ExInitializeRundownProtection
0x14019421d  nop     dword ptr [rax+rax+00h]
0x140194222  mov     rcx, rbp; RunRef
0x140194225  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14019422c  nop     dword ptr [rax+rax+00h]
0x140194231  mov     rcx, rbp; RunRef
0x140194234  call    cs:__imp_ExRundownCompleted
0x14019423b  nop     dword ptr [rax+rax+00h]
0x140194240  mov     [rbx+8], rsi
0x140194244  lea     rcx, [rsp+0B8h+arg_0]
0x14019424c  mov     [rbx+10h], r12w
0x140194251  lea     r9, [rsp+0B8h+var_68]
0x140194256  mov     rax, [rsi+2A8h]
0x14019425d  lea     r8, [rsp+0B8h+var_58]
0x140194262  movups  xmm0, xmmword ptr [rsi+610h]
0x140194269  mov     rdx, [rsi+8]
0x14019426d  movups  xmm1, xmmword ptr [rsi+600h]
0x140194274  mov     al, [rax+24F8h]
0x14019427a  mov     [rsp+0B8h+var_80], rcx
0x14019427f  mov     [rsp+0B8h+var_88], rbx
0x140194284  mov     byte ptr [rsp+0B8h+var_90], al
0x140194288  mov     word ptr [rsp+0B8h+var_98], r12w
0x14019428e  movdqu  [rsp+0B8h+var_68], xmm0
0x140194294  movdqu  [rsp+0B8h+var_58], xmm1
0x14019429a  call    VmsVmNicChannelFindOrAllocate
0x14019429f  mov     r9, [rsi+2A8h]
0x1401942a6  mov     edi, eax
0x1401942a8  test    eax, eax
0x1401942aa  jns     short loc_1401942E1
0x1401942ac  lea     rcx, [r9+48h]
0x1401942b0  mov     dword ptr [rsp+0B8h+var_80], eax
0x1401942b4  mov     [rsp+0B8h+var_88], rbx
0x1401942b9  mov     r9d, 1Ah
0x1401942bf  mov     [rsp+0B8h+var_90], rcx
0x1401942c4  mov     rcx, cs:VmsIfrNicLog
0x1401942cb  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x1401942d2  mov     [rsp+0B8h+var_98], rbp
0x1401942d7  call    WPP_RECORDER_SF_Zqd
0x1401942dc  jmp     loc_1401944BA
0x1401942e1  cmp     byte ptr [r9+24F8h], 1
0x1401942e9  jnz     short loc_14019432E
0x1401942eb  cmp     [rsp+0B8h+arg_0], r13b
0x1401942f3  jnz     short loc_14019432E
0x1401942f5  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits, 2
0x1401942fc  jz      short loc_140194314
0x1401942fe  mov     r9, [r9+50h]
0x140194302  mov     dword ptr [rsp+0B8h+var_90], r13d
0x140194307  mov     dword ptr [rsp+0B8h+var_98], 1
0x14019430f  call    McTemplateK0ztt_EtwWriteTransfer
0x140194314  mov     rax, [rsi+2A8h]
0x14019431b  add     rax, 48h ; 'H'
0x14019431f  mov     [rsp+0B8h+var_88], rbx
0x140194324  mov     [rsp+0B8h+var_90], rax
0x140194329  call    WPP_RECORDER_SF_Zq
0x14019432e  mov     rcx, [rbx]
0x140194331  mov     rdx, rbx
0x140194334  call    cs:__imp_VmbChannelSetPointer
0x14019433b  nop     dword ptr [rax+rax+00h]
0x140194340  mov     dl, [rsi+620h]
0x140194346  test    dl, dl
0x140194348  jz      short loc_140194394
0x14019434a  mov     rcx, [rbx]
0x14019434d  call    cs:__imp_VmbServerChannelInitSetTargetVtl
0x140194354  nop     dword ptr [rax+rax+00h]
0x140194359  mov     edi, eax
0x14019435b  test    eax, eax
0x14019435d  jns     short loc_140194394
0x14019435f  movzx   eax, byte ptr [rsi+620h]
0x140194366  mov     rcx, [rsi+2A8h]
0x14019436d  mov     [rsp+0B8h+var_78], edi
0x140194371  add     rcx, 48h ; 'H'
0x140194375  mov     dword ptr [rsp+0B8h+var_80], eax
0x140194379  mov     [rsp+0B8h+var_88], rbx
0x14019437e  mov     [rsp+0B8h+var_90], rcx
0x140194383  call    WPP_RECORDER_SF_ZqDd
0x140194388  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x14019438f  jmp     loc_1401944BA
0x140194394  mov     rcx, [rbx]
0x140194397  mov     edx, 69427356h
0x14019439c  mov     r8d, 6F427356h
0x1401943a2  call    cs:__imp_VmbChannelInitSetPacketPoolTag
0x1401943a9  nop     dword ptr [rax+rax+00h]
0x1401943ae  mov     eax, 1
0x1401943b3  xchg    eax, [rbp+8]
0x1401943b6  test    eax, eax
0x1401943b8  jz      short loc_1401943ED
0x1401943ba  mov     rcx, cs:VmsIfrLog
0x1401943c1  lea     rax, aOldstateVmscha_0; "oldState == VmsChannelStateDeleted"
0x1401943c8  mov     [rsp+0B8h+var_90], rax
0x1401943cd  mov     r9d, 0Ah
0x1401943d3  lea     rax, WPP_7f9c2ac2fa983072b55dd04e2689be0b_Traceguids
0x1401943da  mov     [rsp+0B8h+var_98], rax
0x1401943df  lea     r8d, [r9+9]
0x1401943e3  call    WPP_RECORDER_SF_s
0x1401943e8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "oldState == VmsChannelStateDeleted")
0x1401943ed  mov     r15b, 1
0x1401943f0  cmp     [rbx+10h], r13w
0x1401943f5  jz      short loc_14019444C
0x1401943f7  mov     rcx, [rbx]
0x1401943fa  call    cs:__imp_VmbChannelGetServicingState
0x140194401  nop     dword ptr [rax+rax+00h]
0x140194406  test    al, al
0x140194408  jnz     short loc_14019444C
0x14019440a  movzx   r8d, word ptr [rbx+10h]
0x14019440f  mov     rdx, [rsi+10h]
0x140194413  mov     rcx, [rbx]
0x140194416  call    cs:__imp_VmbChannelInitSetPrimaryChannel
0x14019441d  nop     dword ptr [rax+rax+00h]
0x140194422  mov     edi, eax
0x140194424  test    eax, eax
0x140194426  jns     short loc_14019444C
0x140194428  mov     rax, [rsi+2A8h]
0x14019442f  mov     r9d, 1Dh
0x140194435  mov     dword ptr [rsp+0B8h+var_80], edi
0x140194439  add     rax, 48h ; 'H'
0x14019443d  mov     [rsp+0B8h+var_88], rbx
0x140194442  mov     [rsp+0B8h+var_90], rax
0x140194447  jmp     loc_1401942C4
0x14019444c  mov     rcx, [rbx]
0x14019444f  call    cs:__imp_VmbChannelGetServicingState
0x140194456  nop     dword ptr [rax+rax+00h]
0x14019445b  test    al, al
0x14019445d  jnz     short loc_14019446D
0x14019445f  mov     r8, rbx
0x140194462  mov     dl, r14b
0x140194465  mov     rcx, rsi
0x140194468  call    VmsVmNicChannelInitializePreEnableParameters
0x14019446d  mov     rcx, rbx
0x140194470  call    VmsVmNicChannelInitializeCallbacks
0x140194475  lea     rax, [rbx+28h]
0x140194479  mov     [rbx+20h], r13d
0x14019447d  mov     [rax], r13
0x140194480  mov     [rbx+30h], rax
0x140194484  jmp     loc_140194388
0x140194489  mov     edi, 0C000000Dh
0x14019448e  mov     rcx, cs:VmsIfrLog
0x140194495  lea     rax, aVmsvmnicchanne; "!\"VmsVmNicChannelAllocateChannel: VmNi"...
0x14019449c  mov     r9d, 18h
0x1401944a2  mov     [rsp+0B8h+var_90], rax
0x1401944a7  mov     [rsp+0B8h+var_98], rbp
0x1401944ac  lea     r8d, [r9-5]
0x1401944b0  call    WPP_RECORDER_SF_s
0x1401944b5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"VmsVmNicChannelAllocateChannel: VmNicExt or VmNicExt->Nic is NULL"")
0x1401944ba  mov     r8d, edi
0x1401944bd  mov     cl, r14b
0x1401944c0  call    VmsTraceLoggingNicChannelAllocate
0x1401944c5  test    edi, edi
0x1401944c7  jns     short loc_140194507
0x1401944c9  mov     rcx, cs:VmsIfrLog
0x1401944d0  test    rsi, rsi
0x1401944d3  mov     dword ptr [rsp+0B8h+var_80], edi
0x1401944d7  mov     r9d, 1Eh
0x1401944dd  cmovnz  rcx, cs:VmsIfrNicLog
0x1401944e5  mov     word ptr [rsp+0B8h+var_88], r12w
0x1401944eb  mov     [rsp+0B8h+var_90], rsi
0x1401944f0  mov     [rsp+0B8h+var_98], rbp
0x1401944f5  call    WPP_RECORDER_SF_qHd
0x1401944fa  test    r15b, r15b
0x1401944fd  jz      short loc_140194507
0x1401944ff  mov     rcx, rbx
0x140194502  call    VmsVmNicChannelDeleteChannel
0x140194507  mov     eax, edi
0x140194509  add     rsp, 78h
0x14019450d  pop     r15
0x14019450f  pop     r14
0x140194511  pop     r13
0x140194513  pop     r12
0x140194515  pop     rdi
0x140194516  pop     rsi
0x140194517  pop     rbp
0x140194518  pop     rbx
0x140194519  retn
```
