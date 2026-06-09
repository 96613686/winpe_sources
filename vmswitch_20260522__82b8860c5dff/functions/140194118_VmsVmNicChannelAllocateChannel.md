# VmsVmNicChannelAllocateChannel

- ea: `0x140194118`
- end: `0x1401944ab`
- name: `VmsVmNicChannelAllocateChannel`
- size: `915`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401944b4`
- `0x140194610`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14006e590`
- `0x140071520`
- `0x14008497c`
- `0x140088840`
- `0x14008e78c`
- `0x1400a7b0c`
- `0x1401872d0`
- `0x140193df0`
- `0x140194118`
- `0x140194c4c`
- `0x140196fe4`
- `0x14019712c`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1401941a6`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401941a6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1401941b5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1401941b5`
- `ntoskrnl!ExRundownCompleted` at `0x1401941c4`
- `ntoskrnl!ExRundownCompleted` at `0x1401941c4`
- `vmbkmclr!VmbChannelInitSetPrimaryChannel` at `0x1401943a6`
- `vmbkmclr!VmbChannelInitSetPrimaryChannel` at `0x1401943a6`
- `vmbkmclr!VmbChannelInitSetPacketPoolTag` at `0x140194332`
- `vmbkmclr!VmbChannelInitSetPacketPoolTag` at `0x140194332`
- `vmbkmclr!VmbServerChannelInitSetTargetVtl` at `0x1401942dd`
- `vmbkmclr!VmbServerChannelInitSetTargetVtl` at `0x1401942dd`
- `vmbkmclr!VmbChannelSetPointer` at `0x1401942c4`
- `vmbkmclr!VmbChannelSetPointer` at `0x1401942c4`
- `vmbkmclr!VmbChannelGetServicingState` at `0x14019438a`
- `vmbkmclr!VmbChannelGetServicingState` at `0x1401943df`
- `vmbkmclr!VmbChannelGetServicingState` at `0x14019438a`
- `vmbkmclr!VmbChannelGetServicingState` at `0x1401943df`

## string_xrefs

- `0x140194351`: `oldState == VmsChannelStateDeleted`

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
  __int64 v25; // rdx
  int v26; // edx
  int v27; // r8d
  int v28; // ecx
  int v30; // [rsp+20h] [rbp-98h]
  char v31; // [rsp+28h] [rbp-90h]
  __int64 v32; // [rsp+28h] [rbp-90h]
  char v33; // [rsp+30h] [rbp-88h]
  char v34; // [rsp+38h] [rbp-80h]
  __int128 v35; // [rsp+50h] [rbp-68h] BYREF
  __int128 v36; // [rsp+60h] [rbp-58h] BYREF
  char v37; // [rsp+C0h] [rbp+8h] BYREF

  v37 = 0;
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
    v31 = *(_BYTE *)(*(_QWORD *)(a1 + 680) + 9464LL);
    v35 = *(_OWORD *)(a1 + 1552);
    v36 = v13;
    v14 = VmsVmNicChannelFindOrAllocate(
            (unsigned int)&v37,
            v12,
            (unsigned int)&v36,
            (unsigned int)&v35,
            v6,
            v31,
            (__int64)a3,
            (__int64)&v37);
    v18 = *(_QWORD *)(a1 + 680);
    inited = v14;
    if ( v14 < 0 )
    {
      v19 = v18 + 72;
      v34 = v14;
      v33 = (char)a3;
      v20 = 26;
      v32 = v19;
LABEL_7:
      WPP_RECORDER_SF_Zqd(
        VmsIfrNicLog,
        v15,
        v17,
        v20,
        (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
        v32,
        v33,
        v34);
      goto LABEL_26;
    }
    if ( *(_BYTE *)(v18 + 9464) == 1 && !v37 )
    {
      if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
        McTemplateK0ztt_EtwWriteTransfer(v16, v15, v17, *(_QWORD *)(v18 + 80), 1, 0);
      WPP_RECORDER_SF_Zq(v16, v15, v17, v18, v30, *(_QWORD *)(a1 + 680) + 72LL, (char)a3);
    }
    VmbChannelSetPointer(*a3, a3);
    if ( *(_BYTE *)(a1 + 1568) && (inited = VmbServerChannelInitSetTargetVtl(*a3), inited < 0) )
    {
      WPP_RECORDER_SF_ZqDd(
        *(_DWORD *)(a1 + 680) + 72,
        v21,
        v22,
        v23,
        v30,
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
            v34 = inited;
            v33 = (char)a3;
            v32 = *(_QWORD *)(a1 + 680) + 72LL;
            goto LABEL_7;
          }
        }
      }
      if ( !(unsigned __int8)VmbChannelGetServicingState(*a3) )
      {
        LOBYTE(v25) = a4;
        VmsVmNicChannelInitializePreEnableParameters(a1, v25, a3);
      }
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
    v28 = VmsIfrLog;
    if ( a1 )
      v28 = VmsIfrNicLog;
    WPP_RECORDER_SF_qHd(v28, v26, v27, 30, (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids, a1, v6, inited);
    if ( v8 )
      VmsVmNicChannelDeleteChannel(a3);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140194118  mov     rax, rsp
0x14019411b  push    rbx
0x14019411c  push    rbp
0x14019411d  push    rsi
0x14019411e  push    rdi
0x14019411f  push    r12
0x140194121  push    r13
0x140194123  push    r14
0x140194125  push    r15
0x140194127  sub     rsp, 78h
0x14019412b  xor     r13d, r13d
0x14019412e  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140194135  mov     [rax+8], r13b
0x140194139  mov     r14b, r9b
0x14019413c  mov     rbx, r8
0x14019413f  movzx   r12d, dx
0x140194143  mov     rsi, rcx
0x140194146  mov     r15b, r13b
0x140194149  test    rcx, rcx
0x14019414c  jz      loc_140194419
0x140194152  cmp     [rcx+2A8h], r13
0x140194159  jz      loc_140194419
0x14019415f  cmp     cs:IsVmsVmInitialized, r13b
0x140194166  jnz     short loc_140194191
0x140194168  mov     edi, 0C000000Dh
0x14019416d  mov     rcx, cs:VmsIfrNicLog
0x140194174  lea     r9d, [r13+19h]
0x140194178  mov     dword ptr [rsp+0B8h+var_90], edi
0x14019417c  lea     r8d, [r13+14h]
0x140194180  mov     dl, 2
0x140194182  mov     [rsp+0B8h+var_98], rbp
0x140194187  call    WPP_RECORDER_SF_d
0x14019418c  jmp     loc_14019444A
0x140194191  xor     edx, edx; Val
0x140194193  mov     rcx, rbx; void *
0x140194196  lea     r8d, [rdx+78h]; Size
0x14019419a  call    memset
0x14019419f  lea     rbp, [rbx+68h]
0x1401941a3  mov     rcx, rbp; RunRef
0x1401941a6  call    cs:__imp_ExInitializeRundownProtection
0x1401941ad  nop     dword ptr [rax+rax+00h]
0x1401941b2  mov     rcx, rbp; RunRef
0x1401941b5  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1401941bc  nop     dword ptr [rax+rax+00h]
0x1401941c1  mov     rcx, rbp; RunRef
0x1401941c4  call    cs:__imp_ExRundownCompleted
0x1401941cb  nop     dword ptr [rax+rax+00h]
0x1401941d0  mov     [rbx+8], rsi
0x1401941d4  lea     rcx, [rsp+0B8h+arg_0]
0x1401941dc  mov     [rbx+10h], r12w
0x1401941e1  lea     r9, [rsp+0B8h+var_68]
0x1401941e6  mov     rax, [rsi+2A8h]
0x1401941ed  lea     r8, [rsp+0B8h+var_58]
0x1401941f2  movups  xmm0, xmmword ptr [rsi+610h]
0x1401941f9  mov     rdx, [rsi+8]
0x1401941fd  movups  xmm1, xmmword ptr [rsi+600h]
0x140194204  mov     al, [rax+24F8h]
0x14019420a  mov     [rsp+0B8h+var_80], rcx
0x14019420f  mov     [rsp+0B8h+var_88], rbx
0x140194214  mov     byte ptr [rsp+0B8h+var_90], al
0x140194218  mov     word ptr [rsp+0B8h+var_98], r12w
0x14019421e  movdqu  [rsp+0B8h+var_68], xmm0
0x140194224  movdqu  [rsp+0B8h+var_58], xmm1
0x14019422a  call    VmsVmNicChannelFindOrAllocate
0x14019422f  mov     r9, [rsi+2A8h]
0x140194236  mov     edi, eax
0x140194238  test    eax, eax
0x14019423a  jns     short loc_140194271
0x14019423c  lea     rcx, [r9+48h]
0x140194240  mov     dword ptr [rsp+0B8h+var_80], eax
0x140194244  mov     [rsp+0B8h+var_88], rbx
0x140194249  mov     r9d, 1Ah
0x14019424f  mov     [rsp+0B8h+var_90], rcx
0x140194254  mov     rcx, cs:VmsIfrNicLog
0x14019425b  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140194262  mov     [rsp+0B8h+var_98], rbp
0x140194267  call    WPP_RECORDER_SF_Zqd
0x14019426c  jmp     loc_14019444A
0x140194271  cmp     byte ptr [r9+24F8h], 1
0x140194279  jnz     short loc_1401942BE
0x14019427b  cmp     [rsp+0B8h+arg_0], r13b
0x140194283  jnz     short loc_1401942BE
0x140194285  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits, 2
0x14019428c  jz      short loc_1401942A4
0x14019428e  mov     r9, [r9+50h]
0x140194292  mov     dword ptr [rsp+0B8h+var_90], r13d
0x140194297  mov     dword ptr [rsp+0B8h+var_98], 1
0x14019429f  call    McTemplateK0ztt_EtwWriteTransfer
0x1401942a4  mov     rax, [rsi+2A8h]
0x1401942ab  add     rax, 48h ; 'H'
0x1401942af  mov     [rsp+0B8h+var_88], rbx
0x1401942b4  mov     [rsp+0B8h+var_90], rax
0x1401942b9  call    WPP_RECORDER_SF_Zq
0x1401942be  mov     rcx, [rbx]
0x1401942c1  mov     rdx, rbx
0x1401942c4  call    cs:__imp_VmbChannelSetPointer
0x1401942cb  nop     dword ptr [rax+rax+00h]
0x1401942d0  mov     dl, [rsi+620h]
0x1401942d6  test    dl, dl
0x1401942d8  jz      short loc_140194324
0x1401942da  mov     rcx, [rbx]
0x1401942dd  call    cs:__imp_VmbServerChannelInitSetTargetVtl
0x1401942e4  nop     dword ptr [rax+rax+00h]
0x1401942e9  mov     edi, eax
0x1401942eb  test    eax, eax
0x1401942ed  jns     short loc_140194324
0x1401942ef  movzx   eax, byte ptr [rsi+620h]
0x1401942f6  mov     rcx, [rsi+2A8h]
0x1401942fd  mov     [rsp+0B8h+var_78], edi
0x140194301  add     rcx, 48h ; 'H'
0x140194305  mov     dword ptr [rsp+0B8h+var_80], eax
0x140194309  mov     [rsp+0B8h+var_88], rbx
0x14019430e  mov     [rsp+0B8h+var_90], rcx
0x140194313  call    WPP_RECORDER_SF_ZqDd
0x140194318  lea     rbp, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x14019431f  jmp     loc_14019444A
0x140194324  mov     rcx, [rbx]
0x140194327  mov     edx, 69427356h
0x14019432c  mov     r8d, 6F427356h
0x140194332  call    cs:__imp_VmbChannelInitSetPacketPoolTag
0x140194339  nop     dword ptr [rax+rax+00h]
0x14019433e  mov     eax, 1
0x140194343  xchg    eax, [rbp+8]
0x140194346  test    eax, eax
0x140194348  jz      short loc_14019437D
0x14019434a  mov     rcx, cs:VmsIfrLog
0x140194351  lea     rax, aOldstateVmscha_0; "oldState == VmsChannelStateDeleted"
0x140194358  mov     [rsp+0B8h+var_90], rax
0x14019435d  mov     r9d, 0Ah
0x140194363  lea     rax, WPP_7f9c2ac2fa983072b55dd04e2689be0b_Traceguids
0x14019436a  mov     [rsp+0B8h+var_98], rax
0x14019436f  lea     r8d, [r9+9]
0x140194373  call    WPP_RECORDER_SF_s
0x140194378  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "oldState == VmsChannelStateDeleted")
0x14019437d  mov     r15b, 1
0x140194380  cmp     [rbx+10h], r13w
0x140194385  jz      short loc_1401943DC
0x140194387  mov     rcx, [rbx]
0x14019438a  call    cs:__imp_VmbChannelGetServicingState
0x140194391  nop     dword ptr [rax+rax+00h]
0x140194396  test    al, al
0x140194398  jnz     short loc_1401943DC
0x14019439a  movzx   r8d, word ptr [rbx+10h]
0x14019439f  mov     rdx, [rsi+10h]
0x1401943a3  mov     rcx, [rbx]
0x1401943a6  call    cs:__imp_VmbChannelInitSetPrimaryChannel
0x1401943ad  nop     dword ptr [rax+rax+00h]
0x1401943b2  mov     edi, eax
0x1401943b4  test    eax, eax
0x1401943b6  jns     short loc_1401943DC
0x1401943b8  mov     rax, [rsi+2A8h]
0x1401943bf  mov     r9d, 1Dh
0x1401943c5  mov     dword ptr [rsp+0B8h+var_80], edi
0x1401943c9  add     rax, 48h ; 'H'
0x1401943cd  mov     [rsp+0B8h+var_88], rbx
0x1401943d2  mov     [rsp+0B8h+var_90], rax
0x1401943d7  jmp     loc_140194254
0x1401943dc  mov     rcx, [rbx]
0x1401943df  call    cs:__imp_VmbChannelGetServicingState
0x1401943e6  nop     dword ptr [rax+rax+00h]
0x1401943eb  test    al, al
0x1401943ed  jnz     short loc_1401943FD
0x1401943ef  mov     r8, rbx
0x1401943f2  mov     dl, r14b
0x1401943f5  mov     rcx, rsi
0x1401943f8  call    VmsVmNicChannelInitializePreEnableParameters
0x1401943fd  mov     rcx, rbx
0x140194400  call    VmsVmNicChannelInitializeCallbacks
0x140194405  lea     rax, [rbx+28h]
0x140194409  mov     [rbx+20h], r13d
0x14019440d  mov     [rax], r13
0x140194410  mov     [rbx+30h], rax
0x140194414  jmp     loc_140194318
0x140194419  mov     edi, 0C000000Dh
0x14019441e  mov     rcx, cs:VmsIfrLog
0x140194425  lea     rax, aVmsvmnicchanne; "!\"VmsVmNicChannelAllocateChannel: VmNi"...
0x14019442c  mov     r9d, 18h
0x140194432  mov     [rsp+0B8h+var_90], rax
0x140194437  mov     [rsp+0B8h+var_98], rbp
0x14019443c  lea     r8d, [r9-5]
0x140194440  call    WPP_RECORDER_SF_s
0x140194445  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"VmsVmNicChannelAllocateChannel: VmNicExt or VmNicExt->Nic is NULL"")
0x14019444a  mov     r8d, edi
0x14019444d  mov     cl, r14b
0x140194450  call    VmsTraceLoggingNicChannelAllocate
0x140194455  test    edi, edi
0x140194457  jns     short loc_140194497
0x140194459  mov     rcx, cs:VmsIfrLog
0x140194460  test    rsi, rsi
0x140194463  mov     dword ptr [rsp+0B8h+var_80], edi
0x140194467  mov     r9d, 1Eh
0x14019446d  cmovnz  rcx, cs:VmsIfrNicLog
0x140194475  mov     word ptr [rsp+0B8h+var_88], r12w
0x14019447b  mov     [rsp+0B8h+var_90], rsi
0x140194480  mov     [rsp+0B8h+var_98], rbp
0x140194485  call    WPP_RECORDER_SF_qHd
0x14019448a  test    r15b, r15b
0x14019448d  jz      short loc_140194497
0x14019448f  mov     rcx, rbx
0x140194492  call    VmsVmNicChannelDeleteChannel
0x140194497  mov     eax, edi
0x140194499  add     rsp, 78h
0x14019449d  pop     r15
0x14019449f  pop     r14
0x1401944a1  pop     r13
0x1401944a3  pop     r12
0x1401944a5  pop     rdi
0x1401944a6  pop     rsi
0x1401944a7  pop     rbp
0x1401944a8  pop     rbx
0x1401944a9  retn
```
