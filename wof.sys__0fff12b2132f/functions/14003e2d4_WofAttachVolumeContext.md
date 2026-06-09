# WofAttachVolumeContext

- ea: `0x14003e2d4`
- end: `0x14003e817`
- name: `WofAttachVolumeContext`
- size: `1347`
- prototype: `__int64 __fastcall(__int64, int, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14003bc70`

## callees

- `0x14000ba78`
- `0x14000dbd8`
- `0x14000dc88`
- `0x14000de64`
- `0x14000e000`
- `0x140011640`
- `0x1400119c0`
- `0x14003e2d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003e5e9`
- `ntoskrnl!KeInitializeEvent` at `0x14003e5e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e44d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e498`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e6ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e7e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e44d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e498`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e6ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e7e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e391`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e62c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e69b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e391`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e62c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e69b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003e682`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003e682`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003e4c6`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003e4c6`
- `FLTMGR!FltSetInstanceContext` at `0x14003e776`
- `FLTMGR!FltSetInstanceContext` at `0x14003e776`
- `FLTMGR!FltReleaseContext` at `0x14003e4b4`
- `FLTMGR!FltReleaseContext` at `0x14003e7fa`
- `FLTMGR!FltReleaseContext` at `0x14003e4b4`
- `FLTMGR!FltReleaseContext` at `0x14003e7fa`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003e6d0`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003e6d0`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e317`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e3dc`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e317`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e3dc`
- `FLTMGR!FltAllocateContext` at `0x14003e533`
- `FLTMGR!FltAllocateContext` at `0x14003e533`

## pseudocode

```c
__int64 __fastcall WofAttachVolumeContext(__int64 a1, int a2, PFLT_CONTEXT *a3)
{
  NTSTATUS VolumeProperties; // eax
  int v7; // edx
  NTSTATUS v8; // ebx
  int v9; // r9d
  struct _FLT_VOLUME_PROPERTIES *PoolWithTag; // rax
  struct _FLT_VOLUME_PROPERTIES *v11; // r14
  int v12; // edx
  _QWORD *v13; // rax
  void *v14; // rcx
  _QWORD *v15; // rax
  void *v16; // rcx
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // r8d
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // r9d
  _OWORD *v24; // rax
  _QWORD *v25; // rax
  struct _KEVENT *v26; // rcx
  PVOID v27; // rax
  USHORT Length; // cx
  _WORD *v29; // rdx
  void *v30; // rcx
  PVOID v31; // rax
  _WORD *v32; // rcx
  unsigned int i; // r15d
  __int64 v34; // rax
  int v35; // r8d
  int v36; // r9d
  int ReturnedContext; // [rsp+20h] [rbp-40h]
  __int64 v38; // [rsp+28h] [rbp-38h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-10h] BYREF
  ULONG LengthReturned; // [rsp+A0h] [rbp+40h] BYREF
  ULONG v41; // [rsp+B8h] [rbp+58h] BYREF

  v41 = 0;
  LengthReturned = 0;
  Context = 0;
  VolumeProperties = FltGetVolumeProperties(*(PFLT_VOLUME *)(a1 + 16), 0, 0, &LengthReturned);
  v8 = VolumeProperties;
  if ( VolumeProperties != -2147483643 && VolumeProperties != -1073741789 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_15:
      v13 = Context;
      if ( Context )
      {
        v14 = (void *)*((_QWORD *)Context + 9);
        if ( v14 )
        {
          ExFreePoolWithTag(v14, 0);
          v13 = Context;
        }
        v13[9] = 0;
        v15 = Context;
        v16 = (void *)*((_QWORD *)Context + 11);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0);
          v15 = Context;
        }
        v15[11] = 0;
        FltReleaseContext(Context);
        v17 = FltDeleteInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), 0);
        if ( v17 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(WPP_GLOBAL_Control->DeviceExtension, v18, v19, 16, ReturnedContext, v17);
      }
      return (unsigned int)v8;
    }
    v9 = 11;
    v38 = *(_QWORD *)(a1 + 16);
LABEL_5:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      4,
      v9,
      (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
      v38);
    goto LABEL_15;
  }
  PoolWithTag = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePoolWithTag((POOL_TYPE)512, LengthReturned, 0x56666F57u);
  v11 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v8 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v9 = 10;
    v38 = *(_QWORD *)(a1 + 16);
    goto LABEL_5;
  }
  v8 = FltGetVolumeProperties(*(PFLT_VOLUME *)(a1 + 16), PoolWithTag, LengthReturned, &v41);
  if ( v8 < 0 )
    goto LABEL_14;
  if ( v11->DeviceType == 20 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qZ(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        4,
        12,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        *(_QWORD *)(a1 + 16),
        (__int64)&v11->FileSystemDeviceName);
    }
    v8 = -1073741637;
    goto LABEL_14;
  }
  v21 = FltAllocateContext(WofGlobal, 2u, (unsigned int)Size, (POOL_TYPE)512, &Context);
  v8 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 13;
LABEL_27:
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        4,
        v23,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        v21);
    }
LABEL_14:
    ExFreePoolWithTag(v11, 0);
    goto LABEL_15;
  }
  memset(Context, 0, (unsigned int)Size);
  v24 = Context;
  *((_OWORD *)Context + 6) = *(_OWORD *)a1;
  v24[7] = *(_OWORD *)(a1 + 16);
  v24[8] = *(_OWORD *)(a1 + 32);
  v25 = (char *)Context + 152;
  *((_QWORD *)Context + 20) = (char *)Context + 152;
  *v25 = v25;
  v26 = (struct _KEVENT *)Context;
  *(_DWORD *)Context = 1;
  v26->Header.WaitListHead.Flink = 0;
  LODWORD(v26->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(v26 + 1, SynchronizationEvent, 0);
  *((_DWORD *)Context + 36) = a2;
  *((_DWORD *)Context + 14) |= 1u;
  _InterlockedAdd(&dword_14001845C, 1u);
  v27 = ExAllocatePoolWithTag((POOL_TYPE)512, v11->RealDeviceName.Length + 2LL, 0x56666F57u);
  Length = v11->RealDeviceName.Length;
  v29 = Context;
  *((_OWORD *)Context + 4) = 0;
  v29[33] = Length;
  *((_QWORD *)v29 + 9) = v27;
  v30 = (void *)*((_QWORD *)Context + 9);
  if ( !v30
    || (memset(v30, 0, v11->RealDeviceName.Length + 2LL),
        RtlCopyUnicodeString((PUNICODE_STRING)Context + 4, &v11->RealDeviceName),
        v31 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x62u, 0x56666F57u),
        v32 = Context,
        *((_OWORD *)Context + 5) = 0,
        v32[41] = 98,
        *((_QWORD *)v32 + 11) = v31,
        !*((_QWORD *)Context + 11)) )
  {
    v8 = -1073741670;
    goto LABEL_14;
  }
  if ( FltGetVolumeGuidName(*(PFLT_VOLUME *)(a1 + 16), (PUNICODE_STRING)Context + 5, 0) >= 0 )
  {
    *((_DWORD *)Context + 14) |= 2u;
  }
  else
  {
    ExFreePoolWithTag(*((PVOID *)Context + 11), 0);
    *((_OWORD *)Context + 5) = 0;
    *((_DWORD *)Context + 14) &= ~2u;
  }
  for ( i = 0; i < 4; ++i )
  {
    v34 = 424LL * i;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34) )
    {
      v8 = (*(__int64 (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 160))((char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 20));
      if ( v8 < 0 )
        goto LABEL_14;
      *((_DWORD *)Context + 42) = i;
    }
  }
  v21 = FltSetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), FLT_SET_CONTEXT_REPLACE_IF_EXISTS, Context, 0);
  v8 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v23 = 14;
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqZ(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      v35,
      v36,
      ReturnedContext,
      (char)Context,
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(a1 + 16),
      (__int64)&v11->RealDeviceName);
  ExFreePoolWithTag(v11, 0);
  if ( a3 )
    *a3 = Context;
  else
    FltReleaseContext(Context);
  return 0;
}

```

## disassembly

```asm
0x14003e2d4  mov     [rsp-38h+arg_8], rbx
0x14003e2d9  push    rbp
0x14003e2da  push    rsi
0x14003e2db  push    rdi
0x14003e2dc  push    r12
0x14003e2de  push    r13
0x14003e2e0  push    r14
0x14003e2e2  push    r15
0x14003e2e4  mov     rbp, rsp
0x14003e2e7  sub     rsp, 60h
0x14003e2eb  mov     r12, r8
0x14003e2ee  mov     [rbp+arg_18], 0
0x14003e2f5  mov     r15d, edx
0x14003e2f8  mov     [rbp+LengthReturned], 0
0x14003e2ff  mov     rsi, rcx
0x14003e302  mov     [rbp+Context], 0
0x14003e30a  mov     rcx, [rcx+10h]; Volume
0x14003e30e  lea     r9, [rbp+LengthReturned]; LengthReturned
0x14003e312  xor     r8d, r8d; VolumePropertiesLength
0x14003e315  xor     edx, edx; VolumeProperties
0x14003e317  call    cs:__imp_FltGetVolumeProperties
0x14003e31e  nop     dword ptr [rax+rax+00h]
0x14003e323  mov     ebx, eax
0x14003e325  cmp     eax, 80000005h
0x14003e32a  jz      short loc_14003E37F
0x14003e32c  cmp     eax, 0C0000023h
0x14003e331  jz      short loc_14003E37F
0x14003e333  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e33a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e341  jz      loc_14003E459
0x14003e347  mov     rcx, [rsi+10h]
0x14003e34b  mov     r9d, 0Bh
0x14003e351  mov     [rsp+60h+var_38], rcx
0x14003e356  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e35d  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e364  mov     r8d, 4
0x14003e36a  mov     [rsp+60h+ReturnedContext], rax
0x14003e36f  mov     dl, 2
0x14003e371  mov     rcx, [rcx+40h]
0x14003e375  call    WPP_RECORDER_SF_q
0x14003e37a  jmp     loc_14003E459
0x14003e37f  mov     edx, [rbp+LengthReturned]; NumberOfBytes
0x14003e382  mov     r13d, 200h
0x14003e388  mov     ecx, r13d; PoolType
0x14003e38b  mov     r8d, 56666F57h; Tag
0x14003e391  call    cs:__imp_ExAllocatePoolWithTag
0x14003e398  nop     dword ptr [rax+rax+00h]
0x14003e39d  mov     r14, rax
0x14003e3a0  test    rax, rax
0x14003e3a3  jnz     short loc_14003E3CD
0x14003e3a5  mov     ebx, 0C000009Ah
0x14003e3aa  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e3b1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e3b8  jz      loc_14003E459
0x14003e3be  lea     r9d, [rax+0Ah]
0x14003e3c2  mov     rax, [rsi+10h]
0x14003e3c6  mov     [rsp+60h+var_38], rax
0x14003e3cb  jmp     short loc_14003E356
0x14003e3cd  mov     r8d, [rbp+LengthReturned]; VolumePropertiesLength
0x14003e3d1  lea     r9, [rbp+arg_18]; LengthReturned
0x14003e3d5  mov     rcx, [rsi+10h]; Volume
0x14003e3d9  mov     rdx, r14; VolumeProperties
0x14003e3dc  call    cs:__imp_FltGetVolumeProperties
0x14003e3e3  nop     dword ptr [rax+rax+00h]
0x14003e3e8  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e3ef  mov     ebx, eax
0x14003e3f1  test    eax, eax
0x14003e3f3  js      short loc_14003E448
0x14003e3f5  cmp     dword ptr [r14], 14h
0x14003e3f9  jnz     loc_14003E514
0x14003e3ff  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e406  jz      short loc_14003E443
0x14003e408  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e40f  lea     rax, [r14+28h]
0x14003e413  mov     [rsp+60h+var_30], rax
0x14003e418  mov     r9d, 0Ch
0x14003e41e  mov     rax, [rsi+10h]
0x14003e422  mov     [rsp+60h+var_38], rax
0x14003e427  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e42e  mov     rcx, [rcx+40h]
0x14003e432  lea     r8d, [r9-8]
0x14003e436  mov     [rsp+60h+ReturnedContext], rax
0x14003e43b  mov     dl, r8b
0x14003e43e  call    WPP_RECORDER_SF_qZ
0x14003e443  mov     ebx, 0C00000BBh
0x14003e448  xor     edx, edx; Tag
0x14003e44a  mov     rcx, r14; P
0x14003e44d  call    cs:__imp_ExFreePoolWithTag
0x14003e454  nop     dword ptr [rax+rax+00h]
0x14003e459  mov     rax, [rbp+Context]
0x14003e45d  test    rax, rax
0x14003e460  jz      loc_14003E4F9
0x14003e466  mov     rcx, [rax+48h]; P
0x14003e46a  test    rcx, rcx
0x14003e46d  jz      short loc_14003E481
0x14003e46f  xor     edx, edx; Tag
0x14003e471  call    cs:__imp_ExFreePoolWithTag
0x14003e478  nop     dword ptr [rax+rax+00h]
0x14003e47d  mov     rax, [rbp+Context]
0x14003e481  mov     qword ptr [rax+48h], 0
0x14003e489  mov     rax, [rbp+Context]
0x14003e48d  mov     rcx, [rax+58h]; P
0x14003e491  test    rcx, rcx
0x14003e494  jz      short loc_14003E4A8
0x14003e496  xor     edx, edx; Tag
0x14003e498  call    cs:__imp_ExFreePoolWithTag
0x14003e49f  nop     dword ptr [rax+rax+00h]
0x14003e4a4  mov     rax, [rbp+Context]
0x14003e4a8  mov     qword ptr [rax+58h], 0
0x14003e4b0  mov     rcx, [rbp+Context]; Context
0x14003e4b4  call    cs:__imp_FltReleaseContext
0x14003e4bb  nop     dword ptr [rax+rax+00h]
0x14003e4c0  mov     rcx, [rsi+18h]; Instance
0x14003e4c4  xor     edx, edx; OldContext
0x14003e4c6  call    cs:__imp_FltDeleteInstanceContext
0x14003e4cd  nop     dword ptr [rax+rax+00h]
0x14003e4d2  test    eax, eax
0x14003e4d4  jns     short loc_14003E4F9
0x14003e4d6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e4dd  jz      short loc_14003E4F9
0x14003e4df  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e4e6  mov     r9d, 10h
0x14003e4ec  mov     dword ptr [rsp+60h+var_38], eax
0x14003e4f0  mov     rcx, [rcx+40h]
0x14003e4f4  call    WPP_RECORDER_SF_D
0x14003e4f9  mov     eax, ebx
0x14003e4fb  mov     rbx, [rsp+60h+arg_8]
0x14003e503  add     rsp, 60h
0x14003e507  pop     r15
0x14003e509  pop     r14
0x14003e50b  pop     r13
0x14003e50d  pop     r12
0x14003e50f  pop     rdi
0x14003e510  pop     rsi
0x14003e511  pop     rbp
0x14003e512  retn
0x14003e514  mov     r8d, cs:Size; ContextSize
0x14003e51b  lea     rax, [rbp+Context]
0x14003e51f  mov     rcx, cs:WofGlobal; Filter
0x14003e526  mov     edx, 2; ContextType
0x14003e52b  mov     r9d, r13d; PoolType
0x14003e52e  mov     [rsp+60h+ReturnedContext], rax; ReturnedContext
0x14003e533  call    cs:__imp_FltAllocateContext
0x14003e53a  nop     dword ptr [rax+rax+00h]
0x14003e53f  mov     ebx, eax
0x14003e541  test    eax, eax
0x14003e543  jns     short loc_14003E585
0x14003e545  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e54c  jz      loc_14003E448
0x14003e552  mov     r9d, 0Dh
0x14003e558  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e55f  mov     r8d, 4
0x14003e565  mov     dword ptr [rsp+60h+var_38], eax
0x14003e569  mov     dl, 2
0x14003e56b  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e572  mov     [rsp+60h+ReturnedContext], rax
0x14003e577  mov     rcx, [rcx+40h]
0x14003e57b  call    WPP_RECORDER_SF_d
0x14003e580  jmp     loc_14003E448
0x14003e585  mov     r8d, cs:Size; Size
0x14003e58c  xor     edx, edx; Val
0x14003e58e  mov     rcx, [rbp+Context]; void *
0x14003e592  call    memset
0x14003e597  mov     rax, [rbp+Context]
0x14003e59b  mov     ebx, 1
0x14003e5a0  movups  xmm0, xmmword ptr [rsi]
0x14003e5a3  xor     r8d, r8d; State
0x14003e5a6  mov     edx, ebx; Type
0x14003e5a8  movups  xmmword ptr [rax+60h], xmm0
0x14003e5ac  movups  xmm1, xmmword ptr [rsi+10h]
0x14003e5b0  movups  xmmword ptr [rax+70h], xmm1
0x14003e5b4  movups  xmm0, xmmword ptr [rsi+20h]
0x14003e5b8  movups  xmmword ptr [rax+80h], xmm0
0x14003e5bf  mov     rax, [rbp+Context]
0x14003e5c3  add     rax, 98h
0x14003e5c9  mov     [rax+8], rax
0x14003e5cd  mov     [rax], rax
0x14003e5d0  mov     rcx, [rbp+Context]
0x14003e5d4  mov     [rcx], ebx
0x14003e5d6  mov     qword ptr [rcx+8], 0
0x14003e5de  mov     dword ptr [rcx+10h], 0
0x14003e5e5  add     rcx, 18h; Event
0x14003e5e9  call    cs:__imp_KeInitializeEvent
0x14003e5f0  nop     dword ptr [rax+rax+00h]
0x14003e5f5  mov     rax, [rbp+Context]
0x14003e5f9  mov     [rax+90h], r15d
0x14003e600  mov     rax, [rbp+Context]
0x14003e604  or      [rax+38h], ebx
0x14003e607  lock add cs:dword_14001845C, ebx
0x14003e60e  lea     r13, [r14+38h]
0x14003e612  mov     ebx, 56666F57h
0x14003e617  movzx   edx, word ptr [r13+0]
0x14003e61c  mov     r15d, 200h
0x14003e622  add     rdx, 2; NumberOfBytes
0x14003e626  mov     r8d, ebx; Tag
0x14003e629  mov     ecx, r15d; PoolType
0x14003e62c  call    cs:__imp_ExAllocatePoolWithTag
0x14003e633  nop     dword ptr [rax+rax+00h]
0x14003e638  movzx   ecx, word ptr [r13+0]
0x14003e63d  xorps   xmm0, xmm0
0x14003e640  mov     rdx, [rbp+Context]
0x14003e644  movups  xmmword ptr [rdx+40h], xmm0
0x14003e648  mov     [rdx+42h], cx
0x14003e64c  mov     [rdx+48h], rax
0x14003e650  mov     rax, [rbp+Context]
0x14003e654  mov     rcx, [rax+48h]; void *
0x14003e658  test    rcx, rcx
0x14003e65b  jnz     short loc_14003E667
0x14003e65d  mov     ebx, 0C000009Ah
0x14003e662  jmp     loc_14003E448
0x14003e667  movzx   r8d, word ptr [r13+0]
0x14003e66c  xor     edx, edx; Val
0x14003e66e  add     r8, 2; Size
0x14003e672  call    memset
0x14003e677  mov     rcx, [rbp+Context]
0x14003e67b  mov     rdx, r13; SourceString
0x14003e67e  add     rcx, 40h ; '@'; DestinationString
0x14003e682  call    cs:__imp_RtlCopyUnicodeString
0x14003e689  nop     dword ptr [rax+rax+00h]
0x14003e68e  mov     r8d, ebx; Tag
0x14003e691  mov     ecx, r15d; PoolType
0x14003e694  mov     ebx, 62h ; 'b'
0x14003e699  mov     edx, ebx; NumberOfBytes
0x14003e69b  call    cs:__imp_ExAllocatePoolWithTag
0x14003e6a2  nop     dword ptr [rax+rax+00h]
0x14003e6a7  mov     rcx, [rbp+Context]
0x14003e6ab  xorps   xmm0, xmm0
0x14003e6ae  movups  xmmword ptr [rcx+50h], xmm0
0x14003e6b2  mov     [rcx+52h], bx
0x14003e6b6  mov     [rcx+58h], rax
0x14003e6ba  mov     rdx, [rbp+Context]
0x14003e6be  cmp     qword ptr [rdx+58h], 0
0x14003e6c3  jz      short loc_14003E65D
0x14003e6c5  mov     rcx, [rsi+10h]; Volume
0x14003e6c9  add     rdx, 50h ; 'P'; VolumeGuidName
0x14003e6cd  xor     r8d, r8d; BufferSizeNeeded
0x14003e6d0  call    cs:__imp_FltGetVolumeGuidName
0x14003e6d7  nop     dword ptr [rax+rax+00h]
0x14003e6dc  test    eax, eax
0x14003e6de  jns     short loc_14003E70B
0x14003e6e0  mov     rcx, [rbp+Context]
0x14003e6e4  xor     edx, edx; Tag
0x14003e6e6  mov     rcx, [rcx+58h]; P
0x14003e6ea  call    cs:__imp_ExFreePoolWithTag
0x14003e6f1  nop     dword ptr [rax+rax+00h]
0x14003e6f6  mov     rax, [rbp+Context]
0x14003e6fa  xorps   xmm0, xmm0
0x14003e6fd  movups  xmmword ptr [rax+50h], xmm0
0x14003e701  mov     rax, [rbp+Context]
0x14003e705  and     dword ptr [rax+38h], 0FFFFFFFDh
0x14003e709  jmp     short loc_14003E713
0x14003e70b  mov     rax, [rbp+Context]
0x14003e70f  or      dword ptr [rax+38h], 2
0x14003e713  xor     r15d, r15d
0x14003e716  lea     rdx, WPP_MAIN_CB.Queue+10h
0x14003e71d  cmp     r15d, 4
0x14003e721  jnb     short loc_14003E769
0x14003e723  mov     eax, r15d
0x14003e726  imul    rax, 1A8h
0x14003e72d  cmp     byte ptr [rax+rdx], 0
0x14003e731  jz      short loc_14003E764
0x14003e733  mov     ecx, [rax+rdx+14h]
0x14003e737  add     rcx, [rbp+Context]
0x14003e73b  mov     rax, [rax+rdx+0A0h]
0x14003e743  call    _guard_dispatch_icall
0x14003e748  mov     ebx, eax
0x14003e74a  test    eax, eax
0x14003e74c  js      loc_14003E448
0x14003e752  mov     rax, [rbp+Context]
0x14003e756  lea     rdx, WPP_MAIN_CB.Queue+10h
0x14003e75d  mov     [rax+0A8h], r15d
0x14003e764  inc     r15d
0x14003e767  jmp     short loc_14003E71D
0x14003e769  mov     r8, [rbp+Context]; NewContext
0x14003e76d  xor     r9d, r9d; OldContext
0x14003e770  mov     rcx, [rsi+18h]; Instance
0x14003e774  xor     edx, edx; Operation
0x14003e776  call    cs:__imp_FltSetInstanceContext
0x14003e77d  nop     dword ptr [rax+rax+00h]
0x14003e782  mov     ebx, eax
0x14003e784  test    eax, eax
0x14003e786  jns     short loc_14003E7A0
0x14003e788  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e78f  jz      loc_14003E448
0x14003e795  mov     r9d, 0Eh
0x14003e79b  jmp     loc_14003E558
0x14003e7a0  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e7a7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e7ae  jz      short loc_14003E7E0
0x14003e7b0  mov     rax, [rsi+10h]
0x14003e7b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7bb  mov     [rsp+60h+var_20], r13
0x14003e7c0  mov     [rsp+60h+var_28], rax
0x14003e7c5  mov     rax, [rsi+18h]
0x14003e7c9  mov     rcx, [rcx+40h]
0x14003e7cd  mov     [rsp+60h+var_30], rax
0x14003e7d2  mov     rax, [rbp+Context]
0x14003e7d6  mov     [rsp+60h+var_38], rax
0x14003e7db  call    WPP_RECORDER_SF_qqqZ
0x14003e7e0  xor     edx, edx; Tag
  ... truncated ...
```
