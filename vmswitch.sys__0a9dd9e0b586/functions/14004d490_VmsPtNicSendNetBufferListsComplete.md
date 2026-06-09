# VmsPtNicSendNetBufferListsComplete

- ea: `0x14004d490`
- end: `0x14004dcef`
- name: `VmsPtNicSendNetBufferListsComplete`
- size: `2143`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140017a7c`
- `0x140027a64`
- `0x14004d37c`
- `0x14004d490`
- `0x14004dcf8`
- `0x14004f5d8`
- `0x14008497c`
- `0x140097b18`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14004d55c`
- `ntoskrnl!KeBugCheckEx` at `0x14004d7c3`
- `ntoskrnl!KeBugCheckEx` at `0x14004d55c`
- `ntoskrnl!KeBugCheckEx` at `0x14004d7c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d50e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d539`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d747`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d775`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d7a0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d50e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d539`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d747`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d775`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d7a0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004d4f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004d4f8`
- `NDIS!NdisAcquireRWLockRead` at `0x14004d8f0`
- `NDIS!NdisAcquireRWLockRead` at `0x14004d8f0`
- `NDIS!NdisReleaseRWLock` at `0x14004d9f7`
- `NDIS!NdisReleaseRWLock` at `0x14004d9f7`

## string_xrefs

- `0x14004d584`: `VmsPtNicSendNetBufferListsComplete`
- `0x14004d670`: `VmsPtNicSendNetBufferListsComplete`

## pseudocode

```c
__int64 __fastcall VmsPtNicSendNetBufferListsComplete(__int64 a1, __int64 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 *v4; // r15
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v6; // rbx
  ULONG v7; // eax
  const char *v8; // rdx
  __int64 v9; // r13
  __int64 v10; // r12
  __int64 v11; // rbx
  __int64 *v12; // r12
  __int64 **v13; // rbx
  __int64 v14; // rcx
  int v15; // esi
  __int64 *v16; // rdi
  char v17; // r14
  int v18; // r15d
  __int64 *i; // rcx
  __int64 v20; // r14
  __int64 v21; // r13
  __int64 v22; // rbx
  int v23; // r15d
  __int64 v24; // rdx
  __int64 result; // rax
  __int64 v26; // rbx
  __int64 v27; // rdx
  ULONG v28; // eax
  ULONG_PTR v29; // rbx
  ULONG v30; // eax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 *v37; // rbx
  const char *v38; // rdx
  unsigned int v39; // r14d
  __int64 v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  char *v47; // rcx
  char *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 NicHeaderAtIndex; // rax
  int v54; // eax
  char v55; // [rsp+30h] [rbp-69h]
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v57; // [rsp+38h] [rbp-61h] BYREF
  int v58; // [rsp+3Ch] [rbp-5Dh]
  __int64 v59; // [rsp+40h] [rbp-59h]
  __int64 *v60; // [rsp+48h] [rbp-51h]
  int v61; // [rsp+50h] [rbp-49h]
  __int64 *v62; // [rsp+58h] [rbp-41h] BYREF
  __int64 v63; // [rsp+60h] [rbp-39h]
  __int128 v64; // [rsp+68h] [rbp-31h]
  _OWORD v65[2]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v66; // [rsp+98h] [rbp-1h] BYREF
  __int128 v67; // [rsp+A8h] [rbp+Fh]
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+5Fh]

  v59 = a1;
  v61 = a3;
  v3 = a1;
  v60 = a2;
  v57 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v4 = a2;
  LockState.Flags = 0;
  v66 = 0;
  v67 = 0;
  memset(v65, 0, sizeof(v65));
  if ( (a3 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v6 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v47 = (char *)VmsPlanCpuTable + 5440 * v6) == 0 )
    {
      v7 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v6, v7, 0, 0);
    }
    v55 = 1;
    NetDispatchProfilerEnter(v47 + 1152, 1);
  }
  else
  {
    v55 = 0;
  }
  v8 = "VmsPtNicSendNetBufferListsComplete";
  v9 = 0;
  v58 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v4 )
    {
      v31 = v4[36];
      if ( v31 )
      {
        v32 = *(_QWORD *)(v31 + 16);
        if ( v32 )
        {
          *(_QWORD *)(v32 + 176) = "VmsPtNicSendNetBufferListsComplete";
          *(_DWORD *)(v32 + 184) = 12148;
          *(_QWORD *)(v32 + 168) = retaddr;
        }
      }
    }
  }
  v10 = *(_QWORD *)(v3 + 8);
  v57 = 0;
  v63 = v10;
  if ( !v10 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (unsigned int)"VmsPtNicSendNetBufferListsComplete",
      19,
      180,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      "ptNic");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v11 = *(_QWORD *)(v10 + 3312);
  if ( !v11 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)v8,
      19,
      181,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      "ptNicExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !(unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v10, 0) || !*(_BYTE *)(v11 + 304) || !*(_BYTE *)(v11 + 306) )
    goto LABEL_12;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState, 0);
  v37 = v4;
  if ( !v4 )
    goto LABEL_75;
  do
  {
    if ( !*((_WORD *)v37 + 129) )
      goto LABEL_73;
    if ( (unsigned int)VmsPtNicMUXGetAggregateVMQId(
                         *(unsigned __int16 *)(v3 + 16),
                         *((unsigned __int16 *)v37 + 129),
                         &v57)
      || !v57 )
    {
      *((_WORD *)v37 + 129) = 0;
      goto LABEL_73;
    }
    *((_WORD *)v37 + 129) = v57;
    v39 = v57;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      v43 = v37[36];
      if ( v43 )
      {
        v44 = *(_QWORD *)(v43 + 16);
        if ( v44 )
        {
          v38 = "VmsPtNicGetVmqFromNBL";
          *(_DWORD *)(v44 + 184) = 21120;
          *(_QWORD *)(v44 + 176) = "VmsPtNicGetVmqFromNBL";
          *(_QWORD *)(v44 + 168) = retaddr;
        }
      }
    }
    v40 = *(_QWORD *)(v3 + 8);
    if ( !v40 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        (_DWORD)v38,
        19,
        353,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        "ptNic");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v41 = *(_QWORD *)(v40 + 3312);
    if ( !v41 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        (_DWORD)v38,
        19,
        354,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        "ptNicExt");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( v39 && *(_QWORD *)(v41 + 1424) )
    {
      if ( *(_BYTE *)(v41 + 2400) )
      {
        v51 = v37[36];
        if ( v51 )
        {
          v52 = *(_QWORD *)(v51 + 16);
          if ( v52 )
          {
            if ( *(_DWORD *)(v52 + 68) == 1 )
            {
              NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v40, *(unsigned __int16 *)(*(_QWORD *)(v52 + 72) + 4LL));
              if ( NicHeaderAtIndex )
              {
                if ( *(_QWORD *)(NicHeaderAtIndex + 616) )
                {
                  if ( *(_DWORD *)(NicHeaderAtIndex + 624) >= v39 && *(_DWORD *)(NicHeaderAtIndex + 16) == 2 )
                  {
                    _mm_lfence();
                    v54 = *(_DWORD *)(*(_QWORD *)(NicHeaderAtIndex + 616) + 8LL * (v39 - 1));
                    if ( v54 )
                    {
                      v45 = (unsigned int)(v54 - 1);
                      goto LABEL_83;
                    }
                  }
                }
              }
            }
          }
        }
      }
      else if ( *(_DWORD *)(v41 + 1420) >= v39 )
      {
        _mm_lfence();
        v45 = v39 - 1;
LABEL_83:
        v46 = *(_QWORD *)(*(_QWORD *)(v41 + 1424) + 8 * v45);
LABEL_84:
        if ( v46 && *(_DWORD *)(v46 + 48) == 1 )
          v9 = *(_QWORD *)(v46 + 40);
      }
    }
    else
    {
      if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v40, 0) )
      {
        v42 = *(_QWORD *)(v59 + 1928);
      }
      else
      {
        v42 = *(_QWORD *)(v41 + 1480);
        if ( v42 == v41 + 1480 )
          goto LABEL_69;
      }
      if ( v42 )
      {
        v46 = *(_QWORD *)(v42 + 56);
        goto LABEL_84;
      }
    }
LABEL_69:
    if ( !v9 || *((unsigned __int16 *)v37 + 149) != *(_DWORD *)(*(_QWORD *)(v9 + 1984) + 5920LL) )
      *((_WORD *)v37 + 129) = 0;
    v3 = v59;
LABEL_73:
    v37 = (__int64 *)*v37;
  }
  while ( v37 );
  v4 = v60;
  v10 = v63;
LABEL_75:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState);
  LODWORD(v9) = v58;
LABEL_12:
  if ( v4 )
  {
    do
    {
      v12 = (__int64 *)&v62;
      v13 = (__int64 **)v4;
      v66 = 0;
      v60 = 0;
      v64 = 0;
      v62 = 0;
      v14 = 0;
      v67 = 0;
      do
      {
        *((_QWORD *)v65 + v14) = (char *)&v66 + 8 * v14;
        ++v14;
      }
      while ( v14 != 4 );
      if ( v4 )
      {
        do
        {
          v15 = *((unsigned __int16 *)v13 + 149);
          v16 = (__int64 *)v13;
          v17 = *((_WORD *)v13 + 149);
          v18 = 1;
          if ( (VmsRteConfiguration & 0x10) != 0 )
            VmsPtNicCopyCloneTimestampInfo(v13);
          for ( i = *v13; i && *((unsigned __int16 *)i + 149) == v15; i = (__int64 *)*i )
          {
            if ( (VmsRteConfiguration & 0x10) != 0 )
              VmsPtNicCopyCloneTimestampInfo(i);
            v16 = i;
            ++v18;
          }
          if ( (VmsDiagnosticFlags & 1) != 0 )
          {
            if ( *v16 )
            {
              v33 = *(_QWORD *)(*v16 + 288);
              if ( v33 )
              {
                v34 = *(_QWORD *)(v33 + 16);
                if ( v34 )
                {
                  *(_QWORD *)(v34 + 176) = "VmsPtNicSendNetBufferListsComplete";
                  *(_DWORD *)(v34 + 184) = 12299;
                  *(_QWORD *)(v34 + 168) = retaddr;
                }
              }
            }
          }
          v20 = v17 & 3;
          *v16 = 0;
          if ( !*((_QWORD *)&v66 + v20) || *((_DWORD *)&v65[-1] + v20) == v15 )
          {
            *((_DWORD *)&v65[-1] + v20) = v15;
            **((_QWORD **)v65 + v20) = v13;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( *v16 )
              {
                v35 = *(_QWORD *)(*v16 + 288);
                if ( v35 )
                {
                  v36 = *(_QWORD *)(v35 + 16);
                  if ( v36 )
                  {
                    *(_QWORD *)(v36 + 176) = "VmsPtNicSendNetBufferListsComplete";
                    *(_DWORD *)(v36 + 184) = 12312;
                    *(_QWORD *)(v36 + 168) = retaddr;
                  }
                }
              }
            }
            *((_QWORD *)v65 + v20) = v16;
            LODWORD(v9) = v18 + v9;
          }
          else
          {
            *v12 = (__int64)v13;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( *v16 )
              {
                v49 = *(_QWORD *)(*v16 + 288);
                if ( v49 )
                {
                  v50 = *(_QWORD *)(v49 + 16);
                  if ( v50 )
                  {
                    *(_QWORD *)(v50 + 176) = "VmsPtNicSendNetBufferListsComplete";
                    *(_DWORD *)(v50 + 184) = 12324;
                    *(_QWORD *)(v50 + 168) = retaddr;
                  }
                }
              }
            }
            v12 = v16;
          }
          v13 = (__int64 **)i;
        }
        while ( i );
        v60 = v62;
        v58 = v9;
      }
      v21 = v59;
      v22 = 0;
      v23 = v61;
      do
      {
        v24 = *((_QWORD *)&v66 + v22);
        if ( v24 )
          VmsPtNicSendNetBufferListsCompleteWithRss(v21, (__int64 *)v24, *(unsigned __int16 *)(v24 + 258), v23);
        ++v22;
      }
      while ( v22 != 4 );
      v4 = v60;
      LODWORD(v9) = v58;
    }
    while ( v60 );
    v10 = v63;
  }
  result = VmsPtGetNicHeaderAtIndex(v10, *(unsigned __int16 *)(v59 + 16));
  v26 = result;
  if ( result )
  {
    v27 = KeGetCurrentProcessorNumberEx(0);
    result = *(_QWORD *)(v26 + 24);
    _InterlockedAdd64((volatile signed __int64 *)((v27 << 6) + result + 24), -(int)v9);
  }
  if ( v55 )
  {
    v28 = KeGetCurrentProcessorNumberEx(0);
    v29 = v28;
    if ( v28 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v28)
      || (v48 = (char *)VmsPlanCpuTable + 5440 * v29) == 0 )
    {
      v30 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v29, v30, 0, 0);
    }
    return NetDispatchProfilerLeave(v48 + 1152);
  }
  return result;
}

```

## disassembly

```asm
0x14004d490  mov     [rsp-8+arg_10], rbx
0x14004d495  push    rbp
0x14004d496  push    rsi
0x14004d497  push    rdi
0x14004d498  push    r12
0x14004d49a  push    r13
0x14004d49c  push    r14
0x14004d49e  push    r15
0x14004d4a0  lea     rbp, [rsp-27h]
0x14004d4a5  sub     rsp, 0C0h
0x14004d4ac  mov     rax, cs:__security_cookie
0x14004d4b3  xor     rax, rsp
0x14004d4b6  mov     [rbp+57h+var_38], rax
0x14004d4ba  xorps   xmm0, xmm0
0x14004d4bd  mov     [rbp+57h+var_B0], rcx
0x14004d4c1  xorps   xmm1, xmm1
0x14004d4c4  mov     [rbp+57h+var_A0], r8d
0x14004d4c8  mov     rdi, rcx
0x14004d4cb  mov     [rbp+57h+var_A8], rdx
0x14004d4cf  xor     ecx, ecx
0x14004d4d1  mov     [rbp+57h+var_B8], 0
0x14004d4d8  mov     word ptr [rbp+57h+LockState.OldIrql], cx
0x14004d4dc  mov     r15, rdx
0x14004d4df  mov     [rbp+57h+LockState.Flags], cl
0x14004d4e2  movups  [rbp+57h+var_58], xmm0
0x14004d4e6  movups  [rbp+57h+var_48], xmm0
0x14004d4ea  movups  [rbp+57h+var_78], xmm1
0x14004d4ee  movups  [rbp+57h+var_68], xmm1
0x14004d4f2  test    r8b, 1
0x14004d4f6  jnz     short loc_14004D50C
0x14004d4f8  call    cs:__imp_KeGetCurrentIrql
0x14004d4ff  nop     dword ptr [rax+rax+00h]
0x14004d504  cmp     al, 2
0x14004d506  jnz     loc_14004DB55
0x14004d50c  xor     ecx, ecx; ProcNumber
0x14004d50e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004d515  nop     dword ptr [rax+rax+00h]
0x14004d51a  mov     ebx, eax
0x14004d51c  cmp     eax, 0FFFFFFFFh
0x14004d51f  jz      short loc_14004D537
0x14004d521  mov     edx, ebx
0x14004d523  lea     rcx, VmsKnownProcessors
0x14004d52a  call    VmsCpuSetContainsProcessor
0x14004d52f  test    al, al
0x14004d531  jnz     loc_14004DAD7
0x14004d537  xor     ecx, ecx; ProcNumber
0x14004d539  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004d540  nop     dword ptr [rax+rax+00h]
0x14004d545  xor     r9d, r9d; BugCheckParameter3
0x14004d548  mov     [rsp+0F0h+BugCheckParameter4], 0; BugCheckParameter4
0x14004d551  mov     r8d, eax; BugCheckParameter2
0x14004d554  mov     rdx, rbx; BugCheckParameter1
0x14004d557  mov     ecx, 121h; BugCheckCode
0x14004d55c  call    cs:__imp_KeBugCheckEx
0x14004d569  add     rcx, 480h
0x14004d570  mov     [rbp+57h+var_C0], 1
0x14004d574  mov     edx, 1
0x14004d579  call    NetDispatchProfilerEnter
0x14004d57e  mov     eax, cs:VmsDiagnosticFlags
0x14004d584  lea     rdx, aVmsptnicsendne_0; "VmsPtNicSendNetBufferListsComplete"
0x14004d58b  mov     rcx, [rbp+5Fh]
0x14004d58f  xor     r13d, r13d
0x14004d592  mov     [rbp+57h+var_B4], r13d
0x14004d596  test    al, 1
0x14004d598  jnz     loc_14004D7FB
0x14004d59e  mov     r12, [rdi+8]
0x14004d5a2  lea     rcx, aPtnic; "ptNic"
0x14004d5a9  mov     [rbp+57h+var_B8], r13d
0x14004d5ad  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14004d5b4  mov     [rbp+57h+var_90], r12
0x14004d5b8  test    r12, r12
0x14004d5bb  jz      loc_14004DB5E
0x14004d5c1  mov     rbx, [r12+0CF0h]
0x14004d5c9  lea     rcx, aPtnicext; "ptNicExt"
0x14004d5d0  test    rbx, rbx
0x14004d5d3  jz      loc_14004DB91
0x14004d5d9  xor     edx, edx
0x14004d5db  mov     rcx, r12
0x14004d5de  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14004d5e3  test    al, al
0x14004d5e5  jnz     loc_14004D8CA
0x14004d5eb  test    r15, r15
0x14004d5ee  jz      loc_14004D72D
0x14004d5f4  lea     rax, [rbp+57h+var_58]
0x14004d5f8  lea     rcx, [rbp+57h+var_88]
0x14004d5fc  xorps   xmm0, xmm0
0x14004d5ff  lea     r12, [rbp+57h+var_98]
0x14004d603  mov     rbx, r15
0x14004d606  xor     r15d, r15d
0x14004d609  movups  xmmword ptr [rax], xmm0
0x14004d60c  mov     [rbp+57h+var_A8], r15
0x14004d610  movups  xmmword ptr [rcx], xmm0
0x14004d613  mov     [rbp+57h+var_98], r15
0x14004d617  xor     ecx, ecx
0x14004d619  movups  xmmword ptr [rax+10h], xmm0
0x14004d61d  lea     rax, [rbp+57h+var_58]
0x14004d621  lea     rax, [rax+rcx*8]
0x14004d625  mov     qword ptr [rbp+rcx*8+57h+var_78], rax
0x14004d62a  inc     rcx
0x14004d62d  cmp     rcx, 4
0x14004d631  jnz     short loc_14004D61D
0x14004d633  test    rbx, rbx
0x14004d636  jz      loc_14004D6E0
0x14004d63c  movzx   esi, word ptr [rbx+12Ah]
0x14004d643  mov     rdi, rbx
0x14004d646  mov     eax, cs:VmsRteConfiguration
0x14004d64c  movzx   r14d, si
0x14004d650  mov     r15d, 1
0x14004d656  test    al, 10h
0x14004d658  jnz     loc_14004DCC9
0x14004d65e  mov     rcx, [rbx]
0x14004d661  test    rcx, rcx
0x14004d664  jnz     loc_14004D7D0
0x14004d66a  mov     eax, cs:VmsDiagnosticFlags
0x14004d670  lea     r8, aVmsptnicsendne_0; "VmsPtNicSendNetBufferListsComplete"
0x14004d677  mov     rdx, [rbp+5Fh]
0x14004d67b  test    al, 1
0x14004d67d  jnz     loc_14004D83E
0x14004d683  and     r14d, 3
0x14004d687  mov     qword ptr [rdi], 0
0x14004d68e  cmp     qword ptr [rbp+r14*8+57h+var_58], 0
0x14004d694  lea     rax, ds:0[r14*4]
0x14004d69c  jnz     loc_14004DCE0
0x14004d6a2  mov     rdx, [rbp+5Fh]
0x14004d6a6  mov     dword ptr [rbp+rax+57h+var_88], esi
0x14004d6aa  mov     rax, qword ptr [rbp+r14*8+57h+var_78]
0x14004d6af  mov     [rax], rbx
0x14004d6b2  mov     eax, cs:VmsDiagnosticFlags
0x14004d6b8  test    al, 1
0x14004d6ba  jnz     loc_14004D884
0x14004d6c0  mov     qword ptr [rbp+r14*8+57h+var_78], rdi
0x14004d6c5  add     r13d, r15d
0x14004d6c8  mov     rbx, rcx
0x14004d6cb  test    rcx, rcx
0x14004d6ce  jnz     loc_14004D63C
0x14004d6d4  mov     r15, [rbp+57h+var_98]
0x14004d6d8  mov     [rbp+57h+var_A8], r15
0x14004d6dc  mov     [rbp+57h+var_B4], r13d
0x14004d6e0  mov     r13, [rbp+57h+var_B0]
0x14004d6e4  xor     ebx, ebx
0x14004d6e6  mov     r15d, [rbp+57h+var_A0]
0x14004d6ea  mov     rdx, qword ptr [rbp+rbx*8+57h+var_58]
0x14004d6ef  test    rdx, rdx
0x14004d6f2  jz      short loc_14004D707
0x14004d6f4  movzx   r8d, word ptr [rdx+102h]
0x14004d6fc  mov     r9d, r15d
0x14004d6ff  mov     rcx, r13
0x14004d702  call    VmsPtNicSendNetBufferListsCompleteWithRss
0x14004d707  inc     rbx
0x14004d70a  cmp     rbx, 4
0x14004d70e  jnz     short loc_14004D6EA
0x14004d710  mov     r15, [rbp+57h+var_A8]
0x14004d714  lea     rax, [rbp+57h+var_58]
0x14004d718  mov     r13d, [rbp+57h+var_B4]
0x14004d71c  lea     rcx, [rbp+57h+var_88]
0x14004d720  test    r15, r15
0x14004d723  jnz     loc_14004D5FC
0x14004d729  mov     r12, [rbp+57h+var_90]
0x14004d72d  mov     rdx, [rbp+57h+var_B0]
0x14004d731  mov     rcx, r12
0x14004d734  movzx   edx, word ptr [rdx+10h]
0x14004d738  call    VmsPtGetNicHeaderAtIndex
0x14004d73d  mov     rbx, rax
0x14004d740  test    rax, rax
0x14004d743  jz      short loc_14004D769
0x14004d745  xor     ecx, ecx; ProcNumber
0x14004d747  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004d74e  nop     dword ptr [rax+rax+00h]
0x14004d753  mov     edx, eax
0x14004d755  neg     r13d
0x14004d758  mov     rax, [rbx+18h]
0x14004d75c  shl     rdx, 6
0x14004d760  movsxd  r8, r13d
0x14004d763  lock add [rdx+rax+18h], r8
0x14004d769  cmp     [rbp+57h+var_C0], 0
0x14004d76d  jz      loc_14004DAAF
0x14004d773  xor     ecx, ecx; ProcNumber
0x14004d775  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004d77c  nop     dword ptr [rax+rax+00h]
0x14004d781  mov     ebx, eax
0x14004d783  cmp     eax, 0FFFFFFFFh
0x14004d786  jz      short loc_14004D79E
0x14004d788  mov     edx, ebx
0x14004d78a  lea     rcx, VmsKnownProcessors
0x14004d791  call    VmsCpuSetContainsProcessor
0x14004d796  test    al, al
0x14004d798  jnz     loc_14004DAF0
0x14004d79e  xor     ecx, ecx; ProcNumber
0x14004d7a0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004d7a7  nop     dword ptr [rax+rax+00h]
0x14004d7ac  xor     r9d, r9d; BugCheckParameter3
0x14004d7af  mov     [rsp+0F0h+BugCheckParameter4], 0; BugCheckParameter4
0x14004d7b8  mov     r8d, eax; BugCheckParameter2
0x14004d7bb  mov     rdx, rbx; BugCheckParameter1
0x14004d7be  mov     ecx, 121h; BugCheckCode
0x14004d7c3  call    cs:__imp_KeBugCheckEx
0x14004d7d0  movzx   eax, word ptr [rcx+12Ah]
0x14004d7d7  cmp     eax, esi
0x14004d7d9  jnz     loc_14004D66A
0x14004d7df  mov     eax, cs:VmsRteConfiguration
0x14004d7e5  test    al, 10h
0x14004d7e7  jnz     loc_14004DCD6
0x14004d7ed  mov     rdi, rcx
0x14004d7f0  inc     r15d
0x14004d7f3  mov     rcx, [rcx]
0x14004d7f6  jmp     loc_14004D661
0x14004d7fb  test    r15, r15
0x14004d7fe  jz      loc_14004D59E
0x14004d804  mov     rax, [r15+120h]
0x14004d80b  test    rax, rax
0x14004d80e  jz      loc_14004D59E
0x14004d814  mov     rax, [rax+10h]
0x14004d818  test    rax, rax
0x14004d81b  jz      loc_14004D59E
0x14004d821  mov     [rax+0B0h], rdx
0x14004d828  mov     dword ptr [rax+0B8h], 2F74h
0x14004d832  mov     [rax+0A8h], rcx
0x14004d839  jmp     loc_14004D59E
0x14004d83e  mov     rax, [rdi]
0x14004d841  test    rax, rax
0x14004d844  jz      loc_14004D683
0x14004d84a  mov     rax, [rax+120h]
0x14004d851  test    rax, rax
0x14004d854  jz      loc_14004D683
0x14004d85a  mov     rax, [rax+10h]
0x14004d85e  test    rax, rax
0x14004d861  jz      loc_14004D683
0x14004d867  mov     [rax+0B0h], r8
0x14004d86e  mov     dword ptr [rax+0B8h], 300Bh
0x14004d878  mov     [rax+0A8h], rdx
0x14004d87f  jmp     loc_14004D683
0x14004d884  mov     rax, [rdi]
0x14004d887  test    rax, rax
0x14004d88a  jz      loc_14004D6C0
0x14004d890  mov     rax, [rax+120h]
0x14004d897  test    rax, rax
0x14004d89a  jz      loc_14004D6C0
0x14004d8a0  mov     rax, [rax+10h]
0x14004d8a4  test    rax, rax
0x14004d8a7  jz      loc_14004D6C0
0x14004d8ad  mov     [rax+0B0h], r8
0x14004d8b4  mov     dword ptr [rax+0B8h], 3018h
0x14004d8be  mov     [rax+0A8h], rdx
0x14004d8c5  jmp     loc_14004D6C0
0x14004d8ca  cmp     [rbx+130h], r13b
0x14004d8d1  jz      loc_14004D5EB
0x14004d8d7  cmp     [rbx+132h], r13b
0x14004d8de  jz      loc_14004D5EB
0x14004d8e4  mov     rcx, [r12+38h]; Lock
0x14004d8e9  lea     rdx, [rbp+57h+LockState]; LockState
0x14004d8ed  xor     r8d, r8d; Flags
0x14004d8f0  call    cs:__imp_NdisAcquireRWLockRead
0x14004d8f7  nop     dword ptr [rax+rax+00h]
0x14004d8fc  mov     rbx, r15
0x14004d8ff  test    r15, r15
0x14004d902  jz      loc_14004D9EE
0x14004d908  lea     r12, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14004d90f  lea     r15, aPtnicext; "ptNicExt"
0x14004d916  movzx   edx, word ptr [rbx+102h]
0x14004d91d  test    edx, edx
0x14004d91f  jz      loc_14004D9DA
0x14004d925  movzx   ecx, word ptr [rdi+10h]
0x14004d929  lea     r8, [rbp+57h+var_B8]
0x14004d92d  call    VmsPtNicMUXGetAggregateVMQId
0x14004d932  test    eax, eax
0x14004d934  jnz     loc_14004DCBB
0x14004d93a  mov     eax, [rbp+57h+var_B8]
0x14004d93d  test    eax, eax
0x14004d93f  jz      loc_14004DCBB
0x14004d945  mov     rcx, [rbp+5Fh]
0x14004d949  mov     [rbx+102h], ax
0x14004d950  mov     eax, cs:VmsDiagnosticFlags
0x14004d956  mov     r14d, [rbp+57h+var_B8]
0x14004d95a  test    al, 1
0x14004d95c  jnz     loc_14004DA0C
0x14004d962  mov     rsi, [rdi+8]
0x14004d966  test    rsi, rsi
0x14004d969  jz      loc_14004DBBD
0x14004d96f  mov     rdi, [rsi+0CF0h]
0x14004d976  test    rdi, rdi
0x14004d979  jz      loc_14004DBF0
0x14004d97f  test    r14d, r14d
0x14004d982  jnz     loc_14004DA4D
0x14004d988  xor     edx, edx
0x14004d98a  mov     rcx, rsi
0x14004d98d  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14004d992  test    al, al
0x14004d994  jnz     loc_14004DCA2
0x14004d99a  lea     rax, [rdi+5C8h]
0x14004d9a1  mov     rdx, [rax]
0x14004d9a4  cmp     rdx, rax
0x14004d9a7  jz      short loc_14004D9B2
0x14004d9a9  test    rdx, rdx
0x14004d9ac  jnz     loc_14004DCB2
0x14004d9b2  test    r13, r13
0x14004d9b5  jz      short loc_14004D9CD
0x14004d9b7  mov     rcx, [r13+7C0h]
0x14004d9be  movzx   eax, word ptr [rbx+12Ah]
0x14004d9c5  cmp     eax, [rcx+1720h]
0x14004d9cb  jz      short loc_14004D9D6
  ... truncated ...
```
