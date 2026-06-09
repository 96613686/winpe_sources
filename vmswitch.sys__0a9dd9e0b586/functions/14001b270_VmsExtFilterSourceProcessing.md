# VmsExtFilterSourceProcessing

- ea: `0x14001b270`
- end: `0x14001b8b3`
- name: `VmsExtFilterSourceProcessing`
- size: `1603`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001acc8`

## callees

- `0x140018330`
- `0x14001b270`
- `0x14001b8bc`
- `0x14001b9fc`
- `0x14001bae4`
- `0x14001bf1c`
- `0x14001c050`
- `0x14001c280`
- `0x14001d520`
- `0x14001e598`
- `0x140027a64`
- `0x1400329f0`
- `0x140032b7c`
- `0x14008497c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001b2f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b30b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b85d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b2f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b30b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b85d`
- `NDIS!NdisAcquireRWLockRead` at `0x14001b32a`
- `NDIS!NdisAcquireRWLockRead` at `0x14001b32a`
- `NDIS!NdisReleaseRWLock` at `0x14001b555`
- `NDIS!NdisReleaseRWLock` at `0x14001b555`

## string_xrefs

- `0x14001b346`: `VmsFltProcessIncomingPacket`
- `0x14001b533`: `VmsFltProcessIncomingPacket`

## pseudocode

```c
__int64 __fastcall VmsExtFilterSourceProcessing(__int64 a1, __int64 a2, __int64 *a3, int a4, __int64 *a5, _QWORD *a6)
{
  int v6; // r13d
  char v7; // bl
  __int64 v8; // r15
  __int64 *v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rdi
  int v12; // edx
  UCHAR v13; // r8
  __int64 v14; // rdx
  __int64 *v15; // rcx
  int v16; // r12d
  __int64 i; // rax
  int v18; // r14d
  int v19; // eax
  char v20; // r15
  _BOOL8 v21; // r9
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // edi
  int BasicHeaderInfo; // eax
  int v27; // eax
  __int64 v28; // rcx
  __int64 result; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // [rsp+50h] [rbp-59h] BYREF
  __int64 v43; // [rsp+58h] [rbp-51h] BYREF
  int v44; // [rsp+60h] [rbp-49h] BYREF
  __int64 v45; // [rsp+68h] [rbp-41h] BYREF
  __int64 *v46; // [rsp+70h] [rbp-39h] BYREF
  __int64 *v47; // [rsp+78h] [rbp-31h]
  __int64 v48; // [rsp+80h] [rbp-29h] BYREF
  __int64 v49; // [rsp+88h] [rbp-21h] BYREF
  __int64 v50; // [rsp+90h] [rbp-19h] BYREF
  __int64 *v51; // [rsp+98h] [rbp-11h]
  char v52; // [rsp+A0h] [rbp-9h] BYREF
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+4Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+110h] [rbp+67h] BYREF
  int v57; // [rsp+118h] [rbp+6Fh]

  v57 = a4;
  v6 = 0;
  v43 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v7 = 0;
  LockState.Flags = 0;
  v8 = a1;
  v47 = &v43;
  v9 = a3;
  v42 = 0;
  v46 = &v45;
  v10 = a2;
  v11 = 0;
  v45 = 0;
  v48 = 0;
  v50 = 0;
  v49 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a3 )
    {
      v38 = a3[36];
      if ( v38 )
      {
        v39 = *(_QWORD *)(v38 + 16);
        if ( v39 )
        {
          *(_QWORD *)(v39 + 176) = "VmsExtFilterSourceProcessing";
          *(_DWORD *)(v39 + 184) = 803;
          *(_QWORD *)(v39 + 168) = retaddr;
        }
      }
    }
  }
  if ( KeGetCurrentIrql() == 2 )
  {
    LOBYTE(v57) = 1;
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        "KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v13 = 1;
  }
  else
  {
    LOBYTE(v57) = 0;
    v13 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState, v13);
  if ( v9 )
  {
    while ( 1 )
    {
      v14 = *v9;
      v51 = (__int64 *)*v9;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v14 )
        {
          v30 = *(_QWORD *)(v14 + 288);
          if ( v30 )
          {
            v31 = *(_QWORD *)(v30 + 16);
            if ( v31 )
            {
              *(_QWORD *)(v31 + 176) = "VmsExtFilterSourceProcessing";
              *(_DWORD *)(v31 + 184) = 825;
              *(_QWORD *)(v31 + 168) = retaddr;
            }
          }
        }
      }
      v15 = v9;
      *v9 = 0;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        v32 = v9[36];
        if ( v32 )
        {
          v33 = *(_QWORD *)(v32 + 16);
          if ( v33 )
          {
            *(_QWORD *)(v33 + 176) = "VmsRouterCountNetBufferListBytesAndPackets";
            *(_DWORD *)(v33 + 184) = 1134;
            *(_QWORD *)(v33 + 168) = retaddr;
          }
        }
      }
      v16 = 0;
      do
      {
        for ( i = v15[1]; i; i = *(_QWORD *)i )
        {
          v6 += *(_DWORD *)(i + 24);
          ++v16;
        }
        v15 = (__int64 *)*v15;
      }
      while ( v15 );
      v18 = *((_DWORD *)v9 + 75) & 0x100;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        v34 = v9[36];
        if ( v34 )
        {
          v35 = *(_QWORD *)(v34 + 16);
          if ( v35 )
          {
            *(_QWORD *)(v35 + 176) = "VmsFltProcessIncomingPacket";
            *(_DWORD *)(v35 + 184) = 455;
            *(_QWORD *)(v35 + 168) = retaddr;
          }
        }
      }
      v19 = *(_DWORD *)(v8 + 1872);
      if ( v19 != 2 && v19 != 5 )
      {
        v20 = v18 != 0;
        v21 = v18 != 0;
        v22 = *(_DWORD *)(a2 + 10448)
            ? VmsFltIsolationProcessIncomingPacket(v9, a1, a2, v21)
            : VmsFltVlanProcessIncomingPacket(v9, a1, a2, v21);
        v25 = v22;
        if ( v22 < 0 )
          goto LABEL_19;
      }
      BasicHeaderInfo = VmsNblGetBasicHeaderInfo((_DWORD)v9, (unsigned int)&v52, 0, 0, (__int64)&v42);
      v7 = v42;
      v25 = BasicHeaderInfo;
      v20 = v18 != 0;
      if ( BasicHeaderInfo < 0 )
LABEL_19:
        WPP_RECORDER_SF_qqqLd(
          VmsIfrPortLog,
          v23,
          v24,
          24,
          (__int64)WPP_5917bbece121395a2d7081e042921d7f_Traceguids,
          (char)v9,
          a1,
          a2,
          v20,
          v25);
      if ( (unsigned int)(v25 + 536870909) <= 1 || v25 == -536870899 || v25 >= 0 )
      {
        v27 = 1;
        if ( (v7 & 1) != 0 )
        {
          if ( v7 == -1
            && BYTE5(v42) == 0xFF
            && BYTE3(v42) == 0xFF
            && *(_WORD *)((char *)&v42 + 1) == 0xFFFF
            && BYTE4(v42) == 0xFF )
          {
            v27 = 3;
          }
          else
          {
            v27 = 2;
          }
        }
        if ( v25 >= 0 )
        {
          v28 = v9[36];
          if ( v28 )
            v28 = *(_QWORD *)(v28 + 16);
          if ( v27 == 3 )
          {
            *(_DWORD *)v28 |= 4u;
            goto LABEL_28;
          }
          if ( v27 == 2 )
          {
            *(_DWORD *)v28 |= 8u;
LABEL_28:
            v10 = a2;
            v8 = a1;
            VmsRouterUpdateIncomingStats(a1, *(_QWORD *)(a2 + 1240), v6, v16, v27);
LABEL_30:
            *v47 = (__int64)v9;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( *v9 )
              {
                v36 = *(_QWORD *)(*v9 + 288);
                if ( v36 )
                {
                  v37 = *(_QWORD *)(v36 + 16);
                  if ( v37 )
                  {
                    *(_DWORD *)(v37 + 184) = 888;
                    *(_QWORD *)(v37 + 176) = "VmsExtFilterSourceProcessing";
                    *(_QWORD *)(v37 + 168) = retaddr;
                  }
                }
              }
            }
            v47 = v9;
            goto LABEL_32;
          }
        }
        v10 = a2;
        v8 = a1;
        VmsRouterUpdateIncomingStats(a1, *(_QWORD *)(a2 + 1240), v6, v16, v27);
        if ( v25 >= 0 )
          goto LABEL_30;
      }
      else
      {
        v10 = a2;
        v8 = a1;
      }
      v44 = 0;
      VmsPktGetDropReason((unsigned int)v25, &v44);
      VmsPktReportDroppedNbl(v8, v9, 1, v44, v25, -536862675);
      *v46 = (__int64)v9;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( *v9 )
        {
          v40 = *(_QWORD *)(*v9 + 288);
          if ( v40 )
          {
            v41 = *(_QWORD *)(v40 + 16);
            if ( v41 )
            {
              *(_DWORD *)(v41 + 184) = 883;
              *(_QWORD *)(v41 + 176) = "VmsExtFilterSourceProcessing";
              *(_QWORD *)(v41 + 168) = retaddr;
            }
          }
        }
      }
      v46 = v9;
LABEL_32:
      v9 = v51;
      v6 = 0;
      if ( !v51 )
      {
        v11 = v43;
        break;
      }
    }
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState);
  if ( v11 )
  {
    v43 = 0;
    VmsRouterSourceProcessing(v8, v10, v11, v57, &v43, &v48);
    if ( v48 )
    {
      VmsNblHelperExtractDuplicateInspectionNbls(v48, &v50, &v49);
      VmsNblHelperAppendNblsMoveLast(&v46, v49);
      if ( v50 )
        VmsNblHelperRefCountDecrementMany(v50, 0);
    }
    *a5 = v43;
  }
  else
  {
    *a5 = 0;
  }
  result = v45;
  *a6 = v45;
  return result;
}

```

## disassembly

```asm
0x14001b270  mov     [rsp-8+arg_18], r9d
0x14001b275  mov     [rsp-8+arg_8], rdx
0x14001b27a  mov     [rsp-8+arg_0], rcx
0x14001b27f  push    rbp
0x14001b280  push    rbx
0x14001b281  push    rsi
0x14001b282  push    rdi
0x14001b283  push    r12
0x14001b285  push    r13
0x14001b287  push    r14
0x14001b289  push    r15
0x14001b28b  lea     rbp, [rsp-0Fh]
0x14001b290  sub     rsp, 0B8h
0x14001b297  xor     r13d, r13d
0x14001b29a  lea     r12, aVmsextfilterso; "VmsExtFilterSourceProcessing"
0x14001b2a1  xor     eax, eax
0x14001b2a3  mov     [rbp+47h+var_98], r13
0x14001b2a7  mov     word ptr [rbp+47h+LockState.OldIrql], ax
0x14001b2ab  mov     ebx, r13d
0x14001b2ae  mov     [rbp+47h+LockState.Flags], al
0x14001b2b1  mov     r15, rcx
0x14001b2b4  mov     rcx, [rbp+4Fh]
0x14001b2b8  lea     rax, [rbp+47h+var_98]
0x14001b2bc  mov     [rbp+47h+var_78], rax
0x14001b2c0  mov     rsi, r8
0x14001b2c3  lea     rax, [rbp+47h+var_88]
0x14001b2c7  mov     [rbp+47h+var_A0], rbx
0x14001b2cb  mov     [rbp+47h+var_80], rax
0x14001b2cf  mov     r14, rdx
0x14001b2d2  mov     eax, cs:VmsDiagnosticFlags
0x14001b2d8  mov     edi, r13d
0x14001b2db  mov     [rbp+47h+var_88], r13
0x14001b2df  mov     [rbp+47h+var_70], r13
0x14001b2e3  mov     [rbp+47h+var_60], r13
0x14001b2e7  mov     [rbp+47h+var_68], r13
0x14001b2eb  test    al, 1
0x14001b2ed  jnz     loc_14001B73D
0x14001b2f3  call    cs:__imp_KeGetCurrentIrql
0x14001b2fa  nop     dword ptr [rax+rax+00h]
0x14001b2ff  cmp     al, 2
0x14001b301  jnz     loc_14001B780
0x14001b307  mov     byte ptr [rbp+47h+arg_18], 1
0x14001b30b  call    cs:__imp_KeGetCurrentIrql
0x14001b312  nop     dword ptr [rax+rax+00h]
0x14001b317  cmp     al, 2
0x14001b319  jnz     loc_14001B82D
0x14001b31f  mov     r8b, 1; Flags
0x14001b322  mov     rcx, [r14+38h]; Lock
0x14001b326  lea     rdx, [rbp+47h+LockState]; LockState
0x14001b32a  call    cs:__imp_NdisAcquireRWLockRead
0x14001b331  nop     dword ptr [rax+rax+00h]
0x14001b336  test    rsi, rsi
0x14001b339  jz      loc_14001B54D
0x14001b33f  lea     r8, aVmsroutercount; "VmsRouterCountNetBufferListBytesAndPack"...
0x14001b346  lea     r9, aVmsfltprocessi; "VmsFltProcessIncomingPacket"
0x14001b34d  mov     rdx, [rsi]
0x14001b350  mov     eax, cs:VmsDiagnosticFlags
0x14001b356  mov     rcx, [rbp+4Fh]
0x14001b35a  mov     [rbp+47h+var_58], rdx
0x14001b35e  test    al, 1
0x14001b360  jnz     loc_14001B5CB
0x14001b366  mov     rdx, [rbp+4Fh]
0x14001b36a  mov     rcx, rsi
0x14001b36d  mov     [rsi], r13
0x14001b370  mov     eax, cs:VmsDiagnosticFlags
0x14001b376  test    al, 1
0x14001b378  jnz     loc_14001B60E
0x14001b37e  mov     r12d, r13d
0x14001b381  mov     rax, [rcx+8]
0x14001b385  test    rax, rax
0x14001b388  jz      short loc_14001B399
0x14001b38a  add     r13d, [rax+18h]
0x14001b38e  inc     r12d
0x14001b391  mov     rax, [rax]
0x14001b394  test    rax, rax
0x14001b397  jnz     short loc_14001B38A
0x14001b399  mov     rcx, [rcx]
0x14001b39c  test    rcx, rcx
0x14001b39f  jnz     short loc_14001B381
0x14001b3a1  mov     r14d, [rsi+12Ch]
0x14001b3a8  mov     eax, cs:VmsDiagnosticFlags
0x14001b3ae  and     r14d, 100h
0x14001b3b5  mov     rcx, [rbp+4Fh]
0x14001b3b9  test    al, 1
0x14001b3bb  jnz     loc_14001B648
0x14001b3c1  mov     eax, [r15+750h]
0x14001b3c8  cmp     eax, 2
0x14001b3cb  jz      short loc_14001B403
0x14001b3cd  cmp     eax, 5
0x14001b3d0  jz      short loc_14001B403
0x14001b3d2  mov     rax, [rbp+47h+arg_8]
0x14001b3d6  test    r14d, r14d
0x14001b3d9  mov     rdx, [rbp+47h+arg_0]
0x14001b3dd  mov     r8, rax
0x14001b3e0  setnz   r15b
0x14001b3e4  mov     rcx, rsi
0x14001b3e7  movzx   r9d, r15b
0x14001b3eb  cmp     dword ptr [rax+28D0h], 0
0x14001b3f2  jnz     loc_14001B78B
0x14001b3f8  call    VmsFltVlanProcessIncomingPacket
0x14001b3fd  mov     edi, eax
0x14001b3ff  test    eax, eax
0x14001b401  js      short loc_14001B42F
0x14001b403  lea     rax, [rbp+47h+var_A0]
0x14001b407  xor     r9d, r9d
0x14001b40a  xor     r8d, r8d
0x14001b40d  mov     [rsp+0F0h+var_D0], rax
0x14001b412  lea     rdx, [rbp+47h+var_50]
0x14001b416  mov     rcx, rsi
0x14001b419  call    VmsNblGetBasicHeaderInfo
0x14001b41e  mov     rbx, [rbp+47h+var_A0]
0x14001b422  test    r14d, r14d
0x14001b425  mov     edi, eax
0x14001b427  setnz   r15b
0x14001b42b  test    eax, eax
0x14001b42d  jns     short loc_14001B470
0x14001b42f  mov     rcx, cs:VmsIfrPortLog
0x14001b436  mov     r9d, 18h
0x14001b43c  mov     [rsp+0F0h+var_A8], edi
0x14001b440  movzx   eax, r15b
0x14001b444  mov     [rsp+0F0h+var_B0], eax
0x14001b448  mov     rax, [rbp+47h+arg_8]
0x14001b44c  mov     [rsp+0F0h+var_B8], rax
0x14001b451  mov     rax, [rbp+47h+arg_0]
0x14001b455  mov     [rsp+0F0h+var_C0], rax
0x14001b45a  lea     rax, WPP_5917bbece121395a2d7081e042921d7f_Traceguids
0x14001b461  mov     [rsp+0F0h+var_C8], rsi
0x14001b466  mov     [rsp+0F0h+var_D0], rax
0x14001b46b  call    WPP_RECORDER_SF_qqqLd
0x14001b470  lea     eax, [rdi+1FFFFFFDh]
0x14001b476  cmp     eax, 1
0x14001b479  ja      loc_14001B6CF
0x14001b47f  mov     eax, 1
0x14001b484  test    al, bl
0x14001b486  jnz     loc_14001B7A1
0x14001b48c  test    edi, edi
0x14001b48e  js      short loc_14001B4D8
0x14001b490  mov     rcx, [rsi+120h]
0x14001b497  test    rcx, rcx
0x14001b49a  jz      loc_14001B87B
0x14001b4a0  mov     rcx, [rcx+10h]
0x14001b4a4  cmp     eax, 3
0x14001b4a7  jz      loc_14001B7B0
0x14001b4ad  cmp     eax, 2
0x14001b4b0  jnz     short loc_14001B4D8
0x14001b4b2  or      dword ptr [rcx], 8
0x14001b4b5  mov     r14, [rbp+47h+arg_8]
0x14001b4b9  mov     r9d, r12d
0x14001b4bc  mov     r15, [rbp+47h+arg_0]
0x14001b4c0  mov     r8d, r13d
0x14001b4c3  mov     rcx, r15
0x14001b4c6  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14001b4ca  mov     rdx, [r14+4D8h]
0x14001b4d1  call    VmsRouterUpdateIncomingStats
0x14001b4d6  jmp     short loc_14001B501
0x14001b4d8  mov     r14, [rbp+47h+arg_8]
0x14001b4dc  mov     r9d, r12d
0x14001b4df  mov     r15, [rbp+47h+arg_0]
0x14001b4e3  mov     r8d, r13d
0x14001b4e6  mov     rcx, r15
0x14001b4e9  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14001b4ed  mov     rdx, [r14+4D8h]
0x14001b4f4  call    VmsRouterUpdateIncomingStats
0x14001b4f9  test    edi, edi
0x14001b4fb  js      loc_14001B6EB
0x14001b501  mov     rax, [rbp+47h+var_78]
0x14001b505  mov     rcx, [rbp+4Fh]
0x14001b509  mov     [rax], rsi
0x14001b50c  mov     eax, cs:VmsDiagnosticFlags
0x14001b512  test    al, 1
0x14001b514  jnz     loc_14001B682
0x14001b51a  mov     [rbp+47h+var_78], rsi
0x14001b51e  mov     rax, [rbp+47h+var_58]
0x14001b522  lea     r12, aVmsextfilterso; "VmsExtFilterSourceProcessing"
0x14001b529  lea     r8, aVmsroutercount; "VmsRouterCountNetBufferListBytesAndPack"...
0x14001b530  mov     rsi, rax
0x14001b533  lea     r9, aVmsfltprocessi; "VmsFltProcessIncomingPacket"
0x14001b53a  mov     r13d, 0
0x14001b540  test    rax, rax
0x14001b543  jnz     loc_14001B34D
0x14001b549  mov     rdi, [rbp+47h+var_98]
0x14001b54d  mov     rcx, [r14+38h]; Lock
0x14001b551  lea     rdx, [rbp+47h+LockState]; LockState
0x14001b555  call    cs:__imp_NdisReleaseRWLock
0x14001b55c  nop     dword ptr [rax+rax+00h]
0x14001b561  test    rdi, rdi
0x14001b564  jz      loc_14001B795
0x14001b56a  movzx   r9d, byte ptr [rbp+47h+arg_18]
0x14001b56f  lea     rax, [rbp+47h+var_70]
0x14001b573  mov     [rsp+0F0h+var_C8], rax
0x14001b578  mov     r8, rdi
0x14001b57b  lea     rax, [rbp+47h+var_98]
0x14001b57f  mov     [rbp+47h+var_98], r13
0x14001b583  mov     rdx, r14
0x14001b586  mov     [rsp+0F0h+var_D0], rax
0x14001b58b  mov     rcx, r15
0x14001b58e  call    VmsRouterSourceProcessing
0x14001b593  mov     rcx, [rbp+47h+var_70]
0x14001b597  test    rcx, rcx
0x14001b59a  jnz     loc_14001B880
0x14001b5a0  mov     rcx, [rbp+47h+arg_20]
0x14001b5a4  mov     rax, [rbp+47h+var_98]
0x14001b5a8  mov     [rcx], rax
0x14001b5ab  mov     rcx, [rbp+47h+arg_28]
0x14001b5af  mov     rax, [rbp+47h+var_88]
0x14001b5b3  mov     [rcx], rax
0x14001b5b6  add     rsp, 0B8h
0x14001b5bd  pop     r15
0x14001b5bf  pop     r14
0x14001b5c1  pop     r13
0x14001b5c3  pop     r12
0x14001b5c5  pop     rdi
0x14001b5c6  pop     rsi
0x14001b5c7  pop     rbx
0x14001b5c8  pop     rbp
0x14001b5c9  retn
0x14001b5cb  test    rdx, rdx
0x14001b5ce  jz      loc_14001B366
0x14001b5d4  mov     rax, [rdx+120h]
0x14001b5db  test    rax, rax
0x14001b5de  jz      loc_14001B366
0x14001b5e4  mov     rax, [rax+10h]
0x14001b5e8  test    rax, rax
0x14001b5eb  jz      loc_14001B366
0x14001b5f1  mov     [rax+0B0h], r12
0x14001b5f8  mov     dword ptr [rax+0B8h], 339h
0x14001b602  mov     [rax+0A8h], rcx
0x14001b609  jmp     loc_14001B366
0x14001b60e  mov     rax, [rsi+120h]
0x14001b615  test    rax, rax
0x14001b618  jz      loc_14001B37E
0x14001b61e  mov     rax, [rax+10h]
0x14001b622  test    rax, rax
0x14001b625  jz      loc_14001B37E
0x14001b62b  mov     [rax+0B0h], r8
0x14001b632  mov     dword ptr [rax+0B8h], 46Eh
0x14001b63c  mov     [rax+0A8h], rdx
0x14001b643  jmp     loc_14001B37E
0x14001b648  mov     rax, [rsi+120h]
0x14001b64f  test    rax, rax
0x14001b652  jz      loc_14001B3C1
0x14001b658  mov     rax, [rax+10h]
0x14001b65c  test    rax, rax
0x14001b65f  jz      loc_14001B3C1
0x14001b665  mov     [rax+0B0h], r9
0x14001b66c  mov     dword ptr [rax+0B8h], 1C7h
0x14001b676  mov     [rax+0A8h], rcx
0x14001b67d  jmp     loc_14001B3C1
0x14001b682  mov     rax, [rsi]
0x14001b685  test    rax, rax
0x14001b688  jz      loc_14001B51A
0x14001b68e  mov     rax, [rax+120h]
0x14001b695  test    rax, rax
0x14001b698  jz      loc_14001B51A
0x14001b69e  mov     rax, [rax+10h]
0x14001b6a2  test    rax, rax
0x14001b6a5  jz      loc_14001B51A
0x14001b6ab  lea     rdx, aVmsextfilterso; "VmsExtFilterSourceProcessing"
0x14001b6b2  mov     dword ptr [rax+0B8h], 378h
0x14001b6bc  mov     [rax+0B0h], rdx
0x14001b6c3  mov     [rax+0A8h], rcx
0x14001b6ca  jmp     loc_14001B51A
0x14001b6cf  cmp     edi, 0E000000Dh
0x14001b6d5  jz      loc_14001B47F
0x14001b6db  test    edi, edi
0x14001b6dd  jns     loc_14001B47F
0x14001b6e3  mov     r14, [rbp+47h+arg_8]
0x14001b6e7  mov     r15, [rbp+47h+arg_0]
0x14001b6eb  lea     rdx, [rbp+47h+var_90]
0x14001b6ef  mov     [rbp+47h+var_90], 0
0x14001b6f6  mov     ecx, edi
0x14001b6f8  call    VmsPktGetDropReason
0x14001b6fd  mov     r9d, [rbp+47h+var_90]
0x14001b701  mov     r8b, 1
0x14001b704  mov     rcx, r15
0x14001b707  mov     dword ptr [rsp+0F0h+var_C8], 0E000202Dh
0x14001b70f  mov     rdx, rsi
0x14001b712  mov     dword ptr [rsp+0F0h+var_D0], edi
0x14001b716  call    VmsPktReportDroppedNbl
0x14001b71b  mov     rax, [rbp+47h+var_80]
0x14001b71f  mov     rcx, [rbp+4Fh]
0x14001b723  mov     [rax], rsi
0x14001b726  mov     eax, cs:VmsDiagnosticFlags
0x14001b72c  test    al, 1
0x14001b72e  jnz     loc_14001B7E0
0x14001b734  mov     [rbp+47h+var_80], rsi
0x14001b738  jmp     loc_14001B51E
0x14001b73d  test    rsi, rsi
0x14001b740  jz      loc_14001B2F3
0x14001b746  mov     rax, [r8+120h]
0x14001b74d  test    rax, rax
0x14001b750  jz      loc_14001B2F3
0x14001b756  mov     rax, [rax+10h]
0x14001b75a  test    rax, rax
0x14001b75d  jz      loc_14001B2F3
0x14001b763  mov     [rax+0B0h], r12
0x14001b76a  mov     dword ptr [rax+0B8h], 323h
0x14001b774  mov     [rax+0A8h], rcx
0x14001b77b  jmp     loc_14001B2F3
0x14001b780  mov     byte ptr [rbp+47h+arg_18], bl
  ... truncated ...
```
