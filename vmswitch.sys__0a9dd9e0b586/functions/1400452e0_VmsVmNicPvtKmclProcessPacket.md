# VmsVmNicPvtKmclProcessPacket

- ea: `0x1400452e0`
- end: `0x140045ba2`
- name: `VmsVmNicPvtKmclProcessPacket`
- size: `2242`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, unsigned int, char)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140027a64`
- `0x14002e0f0`
- `0x14003ded0`
- `0x14003e804`
- `0x14003e9e4`
- `0x140040410`
- `0x140040c40`
- `0x140043a58`
- `0x1400452e0`
- `0x140045ba8`
- `0x14004633c`
- `0x140049500`
- `0x14005d4bc`
- `0x14007a890`
- `0x14008497c`
- `0x1400f2fa8`
- `0x14019792c`
- `0x14019b9e8`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14004537b`
- `ntoskrnl!KeBugCheckEx` at `0x14004548f`
- `ntoskrnl!KeBugCheckEx` at `0x14004537b`
- `ntoskrnl!KeBugCheckEx` at `0x14004548f`
- `ntoskrnl!KeSetEvent` at `0x1400457fd`
- `ntoskrnl!KeSetEvent` at `0x1400457fd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140045331`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004535c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004543e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140045470`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140045331`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004535c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004543e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140045470`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004531c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004531c`
- `vmbkmclr!VmbChannelPacketDeferToPassive` at `0x1400458bc`
- `vmbkmclr!VmbChannelPacketDeferToPassive` at `0x1400458bc`
- `vmbkmclr!VmbChannelPacketDeferUntilPolled` at `0x1400457df`
- `vmbkmclr!VmbChannelPacketDeferUntilPolled` at `0x1400457df`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1400455ac`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045722`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045a7f`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045af9`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045b5a`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1400455ac`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045722`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045a7f`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045af9`
- `vmbkmclr!VmbChannelPacketComplete` at `0x140045b5a`
- `vmbkmclr!VmbChannelPacketGetExternalData` at `0x1400456fd`
- `vmbkmclr!VmbChannelPacketGetExternalData` at `0x140045a5e`
- `vmbkmclr!VmbChannelPacketGetExternalData` at `0x1400456fd`
- `vmbkmclr!VmbChannelPacketGetExternalData` at `0x140045a5e`
- `vmbkmclr!VmbChannelPacketFail` at `0x1400455c8`
- `vmbkmclr!VmbChannelPacketFail` at `0x1400456ad`
- `vmbkmclr!VmbChannelPacketFail` at `0x1400455c8`
- `vmbkmclr!VmbChannelPacketFail` at `0x1400456ad`
- `vmbkmclr!VmbChannelGetPointer` at `0x14004539c`
- `vmbkmclr!VmbChannelGetPointer` at `0x14004539c`

## string_xrefs

- `0x14004594a`: `!"Invalid protocol version."`

## pseudocode

```c
__int64 __fastcall VmsVmNicPvtKmclProcessPacket(__int64 a1, __int64 a2, unsigned int *a3, unsigned int a4, char a5)
{
  KIRQL CurrentIrql; // r13
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v11; // rbx
  ULONG v12; // eax
  int v13; // edx
  __int64 Pointer; // r14
  __int64 v15; // r15
  __int64 v16; // r8
  unsigned int v17; // ebx
  char v18; // r15
  __int64 v19; // rcx
  int v20; // edx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ebx
  char v25; // r14
  ULONG v26; // eax
  ULONG_PTR v27; // rdi
  ULONG v28; // eax
  char v29; // al
  int v30; // edx
  int v31; // r8d
  char *v33; // rcx
  char *v34; // rcx
  int v35; // edx
  int v36; // r8d
  int v37; // eax
  int v38; // edx
  struct _KEVENT *v39; // rcx
  int v40; // edx
  unsigned int v41; // ecx
  int v42; // edx
  int v43; // r9d
  int v44; // eax
  int v45; // eax
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  bool v49; // zf
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  int ExternalData; // eax
  int v55; // edx
  int BugCheckParameter4; // [rsp+28h] [rbp-51h]
  int BugCheckParameter4a; // [rsp+28h] [rbp-51h]
  int v58; // [rsp+30h] [rbp-49h]
  __int64 v59; // [rsp+88h] [rbp+Fh] BYREF
  _QWORD v60[7]; // [rsp+90h] [rbp+17h] BYREF
  char v62; // [rsp+F0h] [rbp+77h]

  v62 = a4;
  v60[0] = 0;
  v59 = 0;
  CurrentIrql = KeGetCurrentIrql();
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v11 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v33 = (char *)VmsPlanCpuTable + 5440 * v11) == 0 )
    {
      v12 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v11, v12, 0, 0);
    }
    NetDispatchProfilerEnter(v33 + 1152, 1);
  }
  Pointer = VmbChannelGetPointer(a1);
  v15 = *(_QWORD *)(Pointer + 8);
  v60[0] = 0;
  LODWORD(v59) = v59 & 0xFFFFFFFC | 2;
  if ( a4 < *(_DWORD *)(v15 + 704) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      v13,
      19,
      89,
      (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
      (__int64)"!\"BufSize too small.\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    VmbChannelPacketFail(a2);
    v24 = -1073741789;
    v25 = v62;
    LOBYTE(v35) = 2;
    WPP_RECORDER_SF_LLd(
      VmsIfrNicLog,
      v35,
      v36,
      90,
      (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
      v62,
      *(_DWORD *)(v15 + 704),
      35);
    goto LABEL_24;
  }
  if ( !(unsigned __int8)NvspFormatsCheckNvspMessage(a3, a4) )
  {
    VmbChannelPacketFail(a2);
    v24 = -1073741823;
    goto LABEL_23;
  }
  v17 = *a3;
  if ( *a3 != 107 || *(int *)(v15 + 580) < 2 )
  {
    LOBYTE(v16) = 1;
    v29 = VmsTraceCategorizeEntryPoint(4, v17, v16);
    HIDWORD(v59) = v17;
    LODWORD(v59) = v59 & 0x2003
                 | ((v29 & 3 | 0x10) << 9)
                 | ((unsigned __int16)(_InterlockedExchangeAdd(&dword_1401FA2BC, 1u) + 1) << 16)
                 | 2;
    LODWORD(v59) = VmsTraceIsCategoryEnabled(((unsigned int)v59 >> 9) & 3) & 1 | v59 & 0xFFFFFFFE;
    VmsWppTraceApi(
      (unsigned int)&v59,
      (unsigned int)"VmsVmNicPvtKmclProcessPacket",
      (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\vm\\vmsvmchannel.c",
      3921,
      4,
      0,
      0,
      1,
      0);
    if ( (v59 & 1) != 0 )
      WPP_RECORDER_SF_sddsqddLddd(
        *(unsigned __int8 *)(Pointer + 28),
        *(unsigned __int16 *)(Pointer + 16),
        ((unsigned int)v59 >> 2) & 0x7F,
        94,
        BugCheckParameter4a,
        v58,
        83,
        ((unsigned int)v59 >> 2) & 0x7F,
        (__int64)"VmsVmNicPvtKmclProcessPacket",
        *(_QWORD *)Pointer,
        *(_WORD *)(Pointer + 16),
        *(_DWORD *)(Pointer + 20),
        *(_DWORD *)(Pointer + 112),
        *(_DWORD *)(Pointer + 24),
        *(_BYTE *)(Pointer + 28),
        *(_DWORD *)(Pointer + 32));
    VmsIfrInfoParamsObjNicSafe(
      (unsigned int)&v59,
      *(_QWORD *)(v15 + 680),
      (unsigned int)"VmsVmNicPvtKmclProcessPacket",
      (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\vm\\vmsvmchannel.c",
      3924,
      1);
    if ( *(_WORD *)(Pointer + 16) )
    {
      v24 = -1073741637;
      WPP_RECORDER_SF_Ld(VmsIfrNicLog, v30, v31, 95, (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids, *a3, 187);
LABEL_22:
      VmbChannelPacketComplete(a2, 0, 0);
LABEL_23:
      v25 = v62;
LABEL_24:
      v18 = a5;
      goto LABEL_14;
    }
    VmsVmNicPvtKmclProcessingCompleteInternal(a1);
    v41 = *a3;
    if ( (*a3 == 1 || *a3 == 101 || *a3 == 103 || *a3 == 104 || *a3 == 106 || *a3 == 129 || *a3 == 131 || *a3 == 133)
      && CurrentIrql )
    {
      VmbChannelPacketDeferToPassive(a2);
LABEL_89:
      v24 = 0;
      goto LABEL_23;
    }
    if ( v41 < 0x64 )
    {
      if ( v41 == 1 )
      {
        VmsVmNicPvtHandleInitMessage(v59, v15, a3, a2);
        goto LABEL_89;
      }
    }
    else if ( v41 <= *(_DWORD *)(v15 + 688) + 100 )
    {
      if ( *(int *)(v15 + 580) < 2 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v40,
          19,
          96,
          (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
          (__int64)"!\"Invalid VscState.\"");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v24 = -1073741436;
        v43 = 97;
        v44 = *(_DWORD *)(v15 + 580);
LABEL_59:
        LOBYTE(v42) = 2;
        WPP_RECORDER_SF_ld(
          VmsIfrNicLog,
          v42,
          20,
          v43,
          (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
          v44,
          132);
        goto LABEL_22;
      }
      v45 = *(_DWORD *)(v15 + 596);
      if ( v45 != 327680 && v45 != 0x40000 && v45 != 196610 && v45 != 2 && (unsigned int)(v45 - 393216) > 1 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v40,
          19,
          98,
          (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
          (__int64)"!\"Invalid protocol version.\"");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v24 = -1073741436;
        v43 = 99;
        v44 = *(_DWORD *)(v15 + 596);
        goto LABEL_59;
      }
      if ( v41 > 0x6D )
      {
        v51 = v41 - 111;
        if ( !v51 )
          goto LABEL_88;
        v52 = v51 - 14;
        if ( !v52 )
          goto LABEL_78;
        v53 = v52 - 4;
        if ( !v53 )
          goto LABEL_78;
        v50 = v53 - 2;
        v49 = v50 == 0;
      }
      else
      {
        if ( v41 == 109 )
          goto LABEL_88;
        v46 = v41 - 100;
        if ( !v46 )
          goto LABEL_78;
        v47 = v46 - 1;
        if ( !v47 )
          goto LABEL_78;
        v48 = v47 - 2;
        if ( !v48 )
          goto LABEL_78;
        v50 = v48 - 1;
        v49 = v50 == 0;
      }
      if ( !v49 && v50 != 2 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v40,
          19,
          101,
          (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
          (__int64)"!\"Unknown message type.\"");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
LABEL_88:
        VmbChannelPacketComplete(a2, 0, 0);
        goto LABEL_89;
      }
LABEL_78:
      if ( (a5 & 1) != 0 )
      {
        ExternalData = VmbChannelPacketGetExternalData(a2, 0, v60);
        v24 = ExternalData;
        if ( ExternalData )
        {
          if ( ExternalData != 259 )
            VmbChannelPacketComplete(a2, 0, 0);
          LOBYTE(v55) = 2;
          WPP_RECORDER_SF_qqd(
            VmsIfrNicLog,
            v55,
            20,
            100,
            (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
            a2,
            (char)v60,
            v24);
          goto LABEL_23;
        }
      }
      BugCheckParameter4 = a2;
      (*(void (__fastcall **)(__int64, __int64, unsigned int *, _QWORD))(*(_QWORD *)(v15 + 696) + 8LL * (*a3 - 100)))(
        v59,
        v15,
        a3,
        v60[0]);
      goto LABEL_89;
    }
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      v40,
      19,
      102,
      (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
      (__int64)"!\"Invalid message type.\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    goto LABEL_88;
  }
  v18 = a5;
  if ( (a5 & 1) != 0 && (v37 = VmbChannelPacketGetExternalData(a2, 0, v60), (v24 = v37) != 0) )
  {
    if ( v37 != 259 )
      VmbChannelPacketComplete(a2, 0, 0);
    LOBYTE(v38) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrNicLog,
      v38,
      20,
      92,
      (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
      a2,
      (char)v60,
      v24);
  }
  else
  {
    v19 = *(_QWORD *)(Pointer + 72);
    if ( v19 && (CurrentIrql || *(struct _KTHREAD **)(v19 + 856) != KeGetCurrentThread()) )
    {
      if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qqq(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          24,
          93,
          (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
          Pointer,
          v19,
          (char)KeGetCurrentThread());
      VmbChannelPacketDeferUntilPolled(a2);
      v39 = (struct _KEVENT *)(*(_QWORD *)(Pointer + 72) + 16LL);
      *(_BYTE *)(Pointer + 80) = 1;
      KeSetEvent(v39, 0, 0);
    }
    else
    {
      VmsVmNicPvtVersion1HandleRndisSendMessage(Pointer, a3, v60[0], a2);
    }
    v24 = 0;
  }
  v25 = v62;
LABEL_14:
  if ( CurrentIrql == 2 )
  {
    v26 = KeGetCurrentProcessorNumberEx(0);
    v27 = v26;
    if ( v26 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v26)
      || (v34 = (char *)VmsPlanCpuTable + 5440 * v27) == 0 )
    {
      v28 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v27, v28, 0, 0);
    }
    NetDispatchProfilerLeave(v34 + 1152);
  }
  if ( v24 < 0 )
    WPP_RECORDER_SF_qqqLDd(v21, v20, v22, v23, BugCheckParameter4, a1, a2, (char)a3, v25, v18, v24);
  return VmsWppTraceApi(
           (unsigned int)&v59,
           (unsigned int)"VmsVmNicPvtKmclProcessPacket",
           (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\vm\\vmsvmchannel.c",
           4173,
           4,
           v24,
           1,
           0,
           0);
}

```

## disassembly

```asm
0x1400452e0  mov     rax, rsp
0x1400452e3  mov     [rax+10h], rbx
0x1400452e7  mov     [rax+20h], r9d
0x1400452eb  mov     [rax+8], rcx
0x1400452ef  push    rbp
0x1400452f0  push    rsi
0x1400452f1  push    rdi
0x1400452f2  push    r12
0x1400452f4  push    r13
0x1400452f6  push    r14
0x1400452f8  push    r15
0x1400452fa  lea     rbp, [rax-57h]
0x1400452fe  sub     rsp, 90h
0x140045305  xor     r15d, r15d
0x140045308  mov     edi, r9d
0x14004530b  mov     [rbp+4Fh+var_38], r15
0x14004530f  mov     r12, r8
0x140045312  mov     [rbp+4Fh+var_40], r15
0x140045316  mov     rsi, rdx
0x140045319  mov     r14, rcx
0x14004531c  call    cs:__imp_KeGetCurrentIrql
0x140045323  nop     dword ptr [rax+rax+00h]
0x140045328  mov     r13b, al
0x14004532b  cmp     al, 2
0x14004532d  jnz     short loc_140045399
0x14004532f  xor     ecx, ecx; ProcNumber
0x140045331  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140045338  nop     dword ptr [rax+rax+00h]
0x14004533d  mov     ebx, eax
0x14004533f  cmp     eax, 0FFFFFFFFh
0x140045342  jz      short loc_14004535A
0x140045344  mov     edx, ebx
0x140045346  lea     rcx, VmsKnownProcessors
0x14004534d  call    VmsCpuSetContainsProcessor
0x140045352  test    al, al
0x140045354  jnz     loc_140045645
0x14004535a  xor     ecx, ecx; ProcNumber
0x14004535c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140045363  nop     dword ptr [rax+rax+00h]
0x140045368  xor     r9d, r9d; BugCheckParameter3
0x14004536b  mov     [rsp+0C0h+BugCheckParameter4], r15; BugCheckParameter4
0x140045370  mov     r8d, eax; BugCheckParameter2
0x140045373  mov     rdx, rbx; BugCheckParameter1
0x140045376  mov     ecx, 121h; BugCheckCode
0x14004537b  call    cs:__imp_KeBugCheckEx
0x140045388  add     rcx, 480h
0x14004538f  mov     edx, 1
0x140045394  call    NetDispatchProfilerEnter
0x140045399  mov     rcx, r14
0x14004539c  call    cs:__imp_VmbChannelGetPointer
0x1400453a3  nop     dword ptr [rax+rax+00h]
0x1400453a8  mov     ecx, dword ptr [rbp+4Fh+var_40]
0x1400453ab  mov     r14, rax
0x1400453ae  and     ecx, 0FFFFFFFEh
0x1400453b1  or      ecx, 2
0x1400453b4  mov     r15, [rax+8]
0x1400453b8  mov     [rbp+4Fh+var_38], 0
0x1400453c0  mov     dword ptr [rbp+4Fh+var_40], ecx
0x1400453c3  cmp     edi, [r15+2C0h]
0x1400453ca  jb      loc_140045677
0x1400453d0  mov     edx, edi
0x1400453d2  mov     rcx, r12
0x1400453d5  call    NvspFormatsCheckNvspMessage
0x1400453da  xor     edi, edi
0x1400453dc  test    al, al
0x1400453de  jz      loc_1400455C5
0x1400453e4  mov     ebx, [r12]
0x1400453e8  cmp     ebx, 6Bh ; 'k'
0x1400453eb  jnz     loc_14004549C
0x1400453f1  cmp     dword ptr [r15+244h], 2
0x1400453f9  jl      loc_14004549C
0x1400453ff  mov     r15d, [rbp+4Fh+arg_20]
0x140045403  test    r15b, 1
0x140045407  jnz     loc_1400456F4
0x14004540d  mov     rcx, [r14+48h]
0x140045411  test    rcx, rcx
0x140045414  jnz     loc_140045769
0x14004541a  mov     r8, [rbp+4Fh+var_38]
0x14004541e  mov     r9, rsi
0x140045421  mov     rdx, r12
0x140045424  mov     rcx, r14
0x140045427  call    VmsVmNicPvtVersion1HandleRndisSendMessage
0x14004542c  mov     ebx, edi
0x14004542e  mov     r14d, [rbp+4Fh+arg_18]
0x140045432  cmp     r13b, 2
0x140045436  jnz     loc_1400455DB
0x14004543c  xor     ecx, ecx; ProcNumber
0x14004543e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140045445  nop     dword ptr [rax+rax+00h]
0x14004544a  mov     edi, eax
0x14004544c  cmp     eax, 0FFFFFFFFh
0x14004544f  jz      loc_140045B6F
0x140045455  mov     edx, edi
0x140045457  lea     rcx, VmsKnownProcessors
0x14004545e  call    VmsCpuSetContainsProcessor
0x140045463  xor     r13d, r13d
0x140045466  test    al, al
0x140045468  jnz     loc_14004565E
0x14004546e  xor     ecx, ecx; ProcNumber
0x140045470  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140045477  nop     dword ptr [rax+rax+00h]
0x14004547c  xor     r9d, r9d; BugCheckParameter3
0x14004547f  mov     [rsp+0C0h+BugCheckParameter4], r13; BugCheckParameter4
0x140045484  mov     r8d, eax; BugCheckParameter2
0x140045487  mov     rdx, rdi; BugCheckParameter1
0x14004548a  mov     ecx, 121h; BugCheckCode
0x14004548f  call    cs:__imp_KeBugCheckEx
0x14004549c  mov     r8b, 1
0x14004549f  mov     edx, ebx
0x1400454a1  mov     ecx, 4
0x1400454a6  call    VmsTraceCategorizeEntryPoint
0x1400454ab  mov     ecx, dword ptr [rbp+4Fh+var_40]
0x1400454ae  and     eax, 3
0x1400454b1  or      eax, 10h
0x1400454b4  mov     dword ptr [rbp+4Fh+var_40+4], ebx
0x1400454b7  shl     eax, 9
0x1400454ba  and     ecx, 0FFFF2003h
0x1400454c0  or      eax, ecx
0x1400454c2  mov     ebx, 1
0x1400454c7  mov     dword ptr [rbp+4Fh+var_40], eax
0x1400454ca  movzx   edx, ax
0x1400454cd  mov     eax, ebx
0x1400454cf  lock xadd cs:dword_1401FA2BC, eax
0x1400454d7  add     eax, ebx
0x1400454d9  movzx   ecx, ax
0x1400454dc  shl     ecx, 10h
0x1400454df  or      ecx, edx
0x1400454e1  or      ecx, 2
0x1400454e4  mov     dword ptr [rbp+4Fh+var_40], ecx
0x1400454e7  shr     ecx, 9
0x1400454ea  and     ecx, 3
0x1400454ed  call    VmsTraceIsCategoryEnabled
0x1400454f2  mov     ecx, dword ptr [rbp+4Fh+var_40]
0x1400454f5  lea     r8, aOnecoreVmDvNet_7; "onecore\\vm\\dv\\net\\nvsp\\driver\\vm"...
0x1400454fc  mov     byte ptr [rsp+0C0h+var_80], dil
0x140045501  lea     rdx, aVmsvmnicpvtkmc_5; "VmsVmNicPvtKmclProcessPacket"
0x140045508  and     ecx, 0FFFFFFFEh
0x14004550b  mov     byte ptr [rsp+0C0h+var_88], bl
0x14004550f  and     eax, ebx
0x140045511  mov     byte ptr [rsp+0C0h+var_90], dil
0x140045516  or      ecx, eax
0x140045518  mov     dword ptr [rsp+0C0h+var_98], edi
0x14004551c  mov     dword ptr [rbp+4Fh+var_40], ecx
0x14004551f  mov     r9d, 0F51h
0x140045525  lea     rcx, [rbp+4Fh+var_40]
0x140045529  mov     byte ptr [rsp+0C0h+BugCheckParameter4], 4
0x14004552e  call    VmsWppTraceApi
0x140045533  mov     r8d, dword ptr [rbp+4Fh+var_40]
0x140045537  test    bl, r8b
0x14004553a  jnz     loc_14004580E
0x140045540  mov     rdx, [r15+2A8h]
0x140045547  lea     r9, aOnecoreVmDvNet_7; "onecore\\vm\\dv\\net\\nvsp\\driver\\vm"...
0x14004554e  mov     byte ptr [rsp+0C0h+var_98], bl
0x140045552  lea     r8, aVmsvmnicpvtkmc_5; "VmsVmNicPvtKmclProcessPacket"
0x140045559  lea     rcx, [rbp+4Fh+var_40]
0x14004555d  mov     dword ptr [rsp+0C0h+BugCheckParameter4], 0F54h
0x140045565  call    VmsIfrInfoParamsObjNicSafe
0x14004556a  cmp     [r14+10h], di
0x14004556f  jz      loc_140045879
0x140045575  mov     ebx, 0C00000BBh
0x14004557a  mov     eax, [r12]
0x14004557e  lea     rdi, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140045585  mov     rcx, cs:VmsIfrNicLog
0x14004558c  mov     r9d, 5Fh ; '_'
0x140045592  mov     dword ptr [rsp+0C0h+var_90], ebx
0x140045596  mov     dword ptr [rsp+0C0h+var_98], eax
0x14004559a  mov     [rsp+0C0h+BugCheckParameter4], rdi
0x14004559f  call    WPP_RECORDER_SF_Ld
0x1400455a4  xor     r8d, r8d
0x1400455a7  xor     edx, edx
0x1400455a9  mov     rcx, rsi
0x1400455ac  call    cs:__imp_VmbChannelPacketComplete
0x1400455b3  nop     dword ptr [rax+rax+00h]
0x1400455b8  mov     r14d, [rbp+4Fh+arg_18]
0x1400455bc  mov     r15d, [rbp+4Fh+arg_20]
0x1400455c0  jmp     loc_140045432
0x1400455c5  mov     rcx, rsi
0x1400455c8  call    cs:__imp_VmbChannelPacketFail
0x1400455cf  nop     dword ptr [rax+rax+00h]
0x1400455d4  mov     ebx, 0C0000001h
0x1400455d9  jmp     short loc_1400455B8
0x1400455db  xor     r13d, r13d
0x1400455de  jmp     short loc_1400455EC
0x1400455e0  add     rcx, 480h
0x1400455e7  call    NetDispatchProfilerLeave
0x1400455ec  test    ebx, ebx
0x1400455ee  js      loc_140045B77
0x1400455f4  mov     byte ptr [rsp+0C0h+var_80], r13b
0x1400455f9  lea     r8, aOnecoreVmDvNet_7; "onecore\\vm\\dv\\net\\nvsp\\driver\\vm"...
0x140045600  mov     byte ptr [rsp+0C0h+var_88], r13b
0x140045605  lea     rdx, aVmsvmnicpvtkmc_5; "VmsVmNicPvtKmclProcessPacket"
0x14004560c  mov     byte ptr [rsp+0C0h+var_90], 1
0x140045611  lea     rcx, [rbp+4Fh+var_40]
0x140045615  mov     dword ptr [rsp+0C0h+var_98], ebx
0x140045619  mov     r9d, 104Dh
0x14004561f  mov     byte ptr [rsp+0C0h+BugCheckParameter4], 4
0x140045624  call    VmsWppTraceApi
0x140045629  mov     rbx, [rsp+0C0h+arg_8]
0x140045631  add     rsp, 90h
0x140045638  pop     r15
0x14004563a  pop     r14
0x14004563c  pop     r13
0x14004563e  pop     r12
0x140045640  pop     rdi
0x140045641  pop     rsi
0x140045642  pop     rbp
0x140045643  retn
0x140045645  imul    rcx, rbx, 1540h
0x14004564c  add     rcx, cs:VmsPlanCpuTable
0x140045653  jz      loc_14004535A
0x140045659  jmp     loc_140045388
0x14004565e  imul    rcx, rdi, 1540h
0x140045665  add     rcx, cs:VmsPlanCpuTable
0x14004566c  jz      loc_14004546E
0x140045672  jmp     loc_1400455E0
0x140045677  mov     rcx, cs:VmsIfrNicLog
0x14004567e  lea     rax, aBufsizeTooSmal; "!\"BufSize too small.\""
0x140045685  mov     r9d, 59h ; 'Y'
0x14004568b  mov     [rsp+0C0h+var_98], rax
0x140045690  lea     rdi, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140045697  mov     [rsp+0C0h+BugCheckParameter4], rdi
0x14004569c  lea     r8d, [r9-46h]
0x1400456a0  call    WPP_RECORDER_SF_s
0x1400456a5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"BufSize too small."")
0x1400456aa  mov     rcx, rsi
0x1400456ad  call    cs:__imp_VmbChannelPacketFail
0x1400456b4  nop     dword ptr [rax+rax+00h]
0x1400456b9  mov     ebx, 0C0000023h
0x1400456be  mov     eax, [r15+2C0h]
0x1400456c5  mov     r9d, 5Ah ; 'Z'
0x1400456cb  mov     r14d, [rbp+4Fh+arg_18]
0x1400456cf  mov     dl, 2
0x1400456d1  mov     rcx, cs:VmsIfrNicLog
0x1400456d8  mov     dword ptr [rsp+0C0h+var_88], ebx
0x1400456dc  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400456e0  mov     dword ptr [rsp+0C0h+var_98], r14d
0x1400456e5  mov     [rsp+0C0h+BugCheckParameter4], rdi
0x1400456ea  call    WPP_RECORDER_SF_LLd
0x1400456ef  jmp     loc_1400455BC
0x1400456f4  lea     r8, [rbp+4Fh+var_38]
0x1400456f8  xor     edx, edx
0x1400456fa  mov     rcx, rsi
0x1400456fd  call    cs:__imp_VmbChannelPacketGetExternalData
0x140045704  nop     dword ptr [rax+rax+00h]
0x140045709  mov     ebx, eax
0x14004570b  test    eax, eax
0x14004570d  jz      loc_14004540D
0x140045713  cmp     eax, 103h
0x140045718  jz      short loc_14004572E
0x14004571a  xor     r8d, r8d
0x14004571d  xor     edx, edx
0x14004571f  mov     rcx, rsi
0x140045722  call    cs:__imp_VmbChannelPacketComplete
0x140045729  nop     dword ptr [rax+rax+00h]
0x14004572e  mov     rcx, cs:VmsIfrNicLog
0x140045735  lea     rax, [rbp+4Fh+var_38]
0x140045739  mov     dword ptr [rsp+0C0h+var_88], ebx
0x14004573d  lea     rdi, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140045744  mov     [rsp+0C0h+var_90], rax
0x140045749  mov     r9d, 5Ch ; '\'
0x14004574f  mov     [rsp+0C0h+var_98], rsi
0x140045754  mov     dl, 2
0x140045756  mov     [rsp+0C0h+BugCheckParameter4], rdi
0x14004575b  lea     r8d, [r9-48h]
0x14004575f  call    WPP_RECORDER_SF_qqd
0x140045764  jmp     loc_14004542E
0x140045769  test    r13b, r13b
0x14004576c  jnz     short loc_140045784
0x14004576e  mov     rax, gs:188h
0x140045777  cmp     [rcx+358h], rax
0x14004577e  jz      loc_14004541A
0x140045784  mov     rdx, cs:WPP_GLOBAL_Control
0x14004578b  mov     al, [rdx+29h]
0x14004578e  dec     al
0x140045790  cmp     al, 2
0x140045792  ja      short loc_14004579A
0x140045794  cmp     [rdx+48h], di
0x140045798  jz      short loc_1400457DC
0x14004579a  mov     rax, gs:188h
0x1400457a3  lea     rdi, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x1400457aa  mov     [rsp+0C0h+var_88], rax
0x1400457af  mov     r9d, 5Dh ; ']'
0x1400457b5  mov     [rsp+0C0h+var_90], rcx
0x1400457ba  xor     edx, edx
0x1400457bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457c3  mov     [rsp+0C0h+var_98], r14
0x1400457c8  lea     r8d, [r9-45h]
0x1400457cc  mov     [rsp+0C0h+BugCheckParameter4], rdi
0x1400457d1  mov     rcx, [rcx+40h]
0x1400457d5  call    WPP_RECORDER_SF_qqq
0x1400457da  xor     edi, edi
0x1400457dc  mov     rcx, rsi
0x1400457df  call    cs:__imp_VmbChannelPacketDeferUntilPolled
0x1400457e6  nop     dword ptr [rax+rax+00h]
0x1400457eb  mov     rcx, [r14+48h]
0x1400457ef  xor     r8d, r8d; Wait
0x1400457f2  add     rcx, 10h; Event
0x1400457f6  mov     byte ptr [r14+50h], 1
0x1400457fb  xor     edx, edx; Increment
0x1400457fd  call    cs:__imp_KeSetEvent
  ... truncated ...
```
