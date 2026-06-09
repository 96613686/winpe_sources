# Smb2RkfReadStateAndResume

- ea: `0x14006f438`
- end: `0x14006fba1`
- name: `Smb2RkfReadStateAndResume`
- size: `1897`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14007a89c`

## callees

- `0x140014d60`
- `0x140022958`
- `0x140028dbc`
- `0x140028e58`
- `0x14003420c`
- `0x140034330`
- `0x1400344d0`
- `0x14006cd58`
- `0x14006ead0`
- `0x14006ed5c`
- `0x14006f438`
- `0x14006fba8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14006f947`
- `ntoskrnl!ZwClose` at `0x14006fadf`
- `ntoskrnl!ZwClose` at `0x14006f947`
- `ntoskrnl!ZwClose` at `0x14006fadf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f690`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f690`
- `ntoskrnl!ZwCreateEvent` at `0x14006f8c0`
- `ntoskrnl!ZwCreateEvent` at `0x14006fa5a`
- `ntoskrnl!ZwCreateEvent` at `0x14006f8c0`
- `ntoskrnl!ZwCreateEvent` at `0x14006fa5a`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006f934`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006facc`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006f934`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006facc`
- `ntoskrnl!ZwFsControlFile` at `0x14006f916`
- `ntoskrnl!ZwFsControlFile` at `0x14006faae`
- `ntoskrnl!ZwFsControlFile` at `0x14006f916`
- `ntoskrnl!ZwFsControlFile` at `0x14006faae`

## pseudocode

```c
__int64 __fastcall Smb2RkfReadStateAndResume(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 FileHandle; // rax
  NTSTATUS State; // ebx
  int v8; // r8d
  PDEVICE_OBJECT v9; // rcx
  int v10; // edx
  char v11; // r14
  PVOID v12; // rsi
  unsigned int v13; // r14d
  __int64 v14; // rdx
  PDEVICE_OBJECT v15; // rcx
  int v16; // edx
  PVOID InputBuffer; // r14
  int v18; // r8d
  int v19; // eax
  void *EventHandle; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v21; // [rsp+98h] [rbp-78h] BYREF
  int v22; // [rsp+9Ch] [rbp-74h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp-70h] BYREF
  int v24; // [rsp+A4h] [rbp-6Ch] BYREF
  int v25; // [rsp+A8h] [rbp-68h] BYREF
  PVOID P; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-50h] BYREF
  PVOID v29; // [rsp+C8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-10h] BYREF
  PDEVICE_OBJECT v32; // [rsp+110h] [rbp+0h]
  __int128 v33; // [rsp+118h] [rbp+8h] BYREF
  __int64 v34; // [rsp+128h] [rbp+18h]
  char v35; // [rsp+180h] [rbp+70h] BYREF
  ULONG InputBufferLength; // [rsp+188h] [rbp+78h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  EventHandle = 0;
  P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v22 = 0;
  v28 = 0;
  v21 = 0;
  v27 = 0;
  v29 = 0;
  InputBufferLength = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v35 = 0;
  if ( !*(_QWORD *)(v2 + 80) )
  {
    FileHandle = Smb2GetFileHandle(a2);
    *(_QWORD *)(v2 + 80) = FileHandle;
    if ( !FileHandle )
      return 3221225768LL;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZiDDDDDDDDDDD(
      v32->AttachedDevice,
      *(unsigned __int8 *)(a2 + 685),
      *(unsigned __int8 *)(a2 + 684),
      a1,
      v2 + 192,
      *(_QWORD *)(a2 + 80),
      *(_DWORD *)(a2 + 672),
      *(_WORD *)(a2 + 676),
      *(_WORD *)(a2 + 678),
      *(_BYTE *)(a2 + 680),
      *(_BYTE *)(a2 + 681),
      *(_BYTE *)(a2 + 682),
      *(_BYTE *)(a2 + 683),
      *(_BYTE *)(a2 + 684),
      *(_BYTE *)(a2 + 685),
      *(_BYTE *)(a2 + 686),
      *(_BYTE *)(a2 + 687));
  }
  State = Smb2RkfReadState(
            *(_QWORD *)(a1 + 64),
            *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL),
            (unsigned int)&v23,
            (unsigned int)&P,
            (__int64)&v22,
            (__int64)&v25,
            (__int64)&v28,
            (__int64)&v21,
            (__int64)&v27,
            (__int64)&v29,
            (__int64)&InputBufferLength,
            (__int64)&v24,
            (__int64)&v35);
  if ( State < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 20;
    goto LABEL_13;
  }
  v12 = P;
  if ( *(_DWORD *)P != 3 )
  {
    State = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
        a1,
        v2 + 192);
    }
    goto LABEL_14;
  }
  v13 = v21;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZiDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v2 + 192,
      v8,
      a1,
      v2 + 192,
      *(_QWORD *)(a2 + 80),
      v22,
      *((_DWORD *)P + 22),
      v21,
      InputBufferLength);
  }
  v14 = v23;
  *(_BYTE *)(v2 + 380) = 1;
  if ( (unsigned __int8)Smb2RkfResumeAppInstance(a1, v14, v12) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 23;
LABEL_39:
      WPP_SF_qZ(v15->AttachedDevice, v16, (unsigned int)WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1, v2 + 192);
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 24;
      goto LABEL_39;
    }
  }
  if ( v27 && (State = Smb2RestoreFileLockState(a2, v28, v13), State < 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 25;
  }
  else
  {
    InputBuffer = v29;
    if ( v29 )
    {
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      State = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
      if ( State < 0 )
        goto LABEL_14;
      State = ZwFsControlFile(
                *(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL),
                EventHandle,
                0,
                0,
                &IoStatusBlock,
                0x90308u,
                InputBuffer,
                InputBufferLength,
                0,
                0);
      if ( State == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        State = IoStatusBlock.Status;
      }
      ZwClose(EventHandle);
      v11 = 0;
      if ( State < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            (unsigned int)WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
            a1,
            v2 + 192,
            State);
        }
        goto LABEL_15;
      }
      *(_WORD *)(a2 + 196) = 512;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdZ(WPP_GLOBAL_Control->AttachedDevice, 512, v18, a1, 0, v2 + 192);
      }
    }
    if ( !v35 )
      goto LABEL_69;
    ObjectAttributes.Attributes = 512;
    v33 = 0;
    LODWORD(v33) = v24;
    v34 = 128;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    State = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( State < 0 )
      goto LABEL_14;
    State = ZwFsControlFile(
              *(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL),
              EventHandle,
              0,
              0,
              &IoStatusBlock,
              0x900FCu,
              &v33,
              0x18u,
              0,
              0);
    if ( State == 259 )
    {
      ZwWaitForSingleObject(EventHandle, 0, 0);
      State = IoStatusBlock.Status;
    }
    ZwClose(EventHandle);
    if ( State >= 0 )
    {
LABEL_69:
      if ( !*(_BYTE *)(v2 + 306) && !*(_BYTE *)(v2 + 302) )
      {
        v19 = Smb2RkfNotifyComplete(*(_QWORD *)(a1 + 64), *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL));
        *(_BYTE *)(v2 + 381) = 0;
        v11 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1, v19);
        }
        goto LABEL_15;
      }
      *(_BYTE *)(v2 + 381) = 1;
      goto LABEL_14;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 28;
  }
LABEL_13:
  WPP_SF_qZd(
    v9->AttachedDevice,
    v10,
    (unsigned int)WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
    a1,
    v2 + 192,
    State);
LABEL_14:
  v11 = 0;
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( State < 0 && !v11 )
  {
    Smb2RkfNotifyComplete(*(_QWORD *)(a1 + 64), *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL));
    *(_BYTE *)(v2 + 381) = 0;
  }
  return (unsigned int)State;
}

```

## disassembly

```asm
0x14006f438  mov     [rsp-8+arg_8], rbx
0x14006f43d  push    rbp
0x14006f43e  push    rsi
0x14006f43f  push    rdi
0x14006f440  push    r12
0x14006f442  push    r13
0x14006f444  push    r14
0x14006f446  push    r15
0x14006f448  lea     rbp, [rsp-20h]
0x14006f44d  sub     rsp, 130h
0x14006f454  mov     r15, [rcx+230h]
0x14006f45b  xor     r14d, r14d
0x14006f45e  xorps   xmm0, xmm0
0x14006f461  mov     [rbp+50h+EventHandle], r14
0x14006f465  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14006f469  xor     eax, eax
0x14006f46b  mov     [rbp+50h+P], r14
0x14006f46f  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14006f473  mov     r12, rdx
0x14006f476  mov     r13, rcx
0x14006f479  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14006f47d  mov     [rbp+50h+var_C4], r14d
0x14006f481  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14006f485  mov     [rbp+50h+var_A0], r14
0x14006f489  mov     [rbp+50h+var_C8], r14d
0x14006f48d  mov     [rbp+50h+var_A8], r14
0x14006f491  mov     [rbp+50h+var_98], r14
0x14006f495  mov     [rbp+50h+arg_18], r14d
0x14006f499  mov     [rbp+50h+var_C0], r14d
0x14006f49d  mov     [rbp+50h+var_B8], r14d
0x14006f4a1  mov     [rbp+50h+var_BC], r14d
0x14006f4a5  mov     [rbp+50h+arg_10], r14b
0x14006f4a9  cmp     [r15+50h], r14
0x14006f4ad  jnz     short loc_14006F4CA
0x14006f4af  mov     rcx, rdx
0x14006f4b2  call    Smb2GetFileHandle
0x14006f4b7  mov     [r15+50h], rax
0x14006f4bb  test    rax, rax
0x14006f4be  jnz     short loc_14006F4CA
0x14006f4c0  mov     eax, 0C0000128h
0x14006f4c5  jmp     loc_14006F6BF
0x14006f4ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f4d1  lea     rsi, WPP_GLOBAL_Control
0x14006f4d8  mov     [rbp+50h+arg_0], r14b
0x14006f4dc  mov     edi, 100000h
0x14006f4e1  mov     [rbp+50h+var_50], rcx
0x14006f4e5  cmp     rcx, rsi
0x14006f4e8  jz      loc_14006F5CB
0x14006f4ee  test    [rcx+2Ch], edi
0x14006f4f1  jz      loc_14006F5CB
0x14006f4f7  cmp     byte ptr [rcx+29h], 2
0x14006f4fb  jb      loc_14006F5CB
0x14006f501  movzx   eax, byte ptr [r12+2AFh]
0x14006f50a  lea     r14, [r15+0C0h]
0x14006f511  movzx   ecx, byte ptr [r12+2AEh]
0x14006f51a  movzx   r9d, byte ptr [r12+2ABh]
0x14006f523  movzx   edx, byte ptr [r12+2ADh]
0x14006f52c  movzx   r8d, byte ptr [r12+2ACh]
0x14006f535  movzx   r10d, byte ptr [r12+2AAh]
0x14006f53e  movzx   r11d, byte ptr [r12+2A9h]
0x14006f547  movzx   ebx, byte ptr [r12+2A8h]
0x14006f550  movzx   edi, word ptr [r12+2A6h]
0x14006f559  movzx   esi, word ptr [r12+2A4h]
0x14006f562  mov     [rsp+160h+var_E0], eax
0x14006f569  mov     eax, [r12+2A0h]
0x14006f571  mov     [rsp+160h+var_E8], ecx
0x14006f575  mov     rcx, [rbp+50h+var_50]
0x14006f579  mov     [rsp+160h+var_F0], edx
0x14006f57d  mov     [rsp+160h+var_F8], r8d
0x14006f582  mov     dword ptr [rsp+160h+var_100], r9d
0x14006f587  mov     r9, r13
0x14006f58a  mov     rcx, [rcx+18h]
0x14006f58e  mov     dword ptr [rsp+160h+var_108], r10d
0x14006f593  mov     dword ptr [rsp+160h+var_110], r11d
0x14006f598  mov     [rsp+160h+OutputBufferLength], ebx
0x14006f59c  mov     dword ptr [rsp+160h+OutputBuffer], edi
0x14006f5a0  mov     [rsp+160h+InputBufferLength], esi
0x14006f5a4  mov     dword ptr [rsp+160h+InputBuffer], eax
0x14006f5a8  mov     rax, [r12+50h]
0x14006f5ad  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f5b2  mov     qword ptr [rsp+160h+InitialState], r14
0x14006f5b7  call    WPP_SF_qZiDDDDDDDDDDD
0x14006f5bc  xor     r14d, r14d
0x14006f5bf  lea     rsi, WPP_GLOBAL_Control
0x14006f5c6  mov     edi, 100000h
0x14006f5cb  mov     rdx, [r15+50h]
0x14006f5cf  lea     rax, [rbp+50h+arg_10]
0x14006f5d3  mov     rcx, [r13+40h]
0x14006f5d7  lea     r9, [rbp+50h+P]
0x14006f5db  mov     [rsp+160h+var_100], rax
0x14006f5e0  lea     r8, [rbp+50h+var_C0]
0x14006f5e4  lea     rax, [rbp+50h+var_BC]
0x14006f5e8  mov     rdx, [rdx+60h]
0x14006f5ec  mov     [rsp+160h+var_108], rax
0x14006f5f1  lea     rax, [rbp+50h+arg_18]
0x14006f5f5  mov     [rsp+160h+var_110], rax
0x14006f5fa  lea     rax, [rbp+50h+var_98]
0x14006f5fe  mov     qword ptr [rsp+160h+OutputBufferLength], rax
0x14006f603  lea     rax, [rbp+50h+var_A8]
0x14006f607  mov     [rsp+160h+OutputBuffer], rax
0x14006f60c  lea     rax, [rbp+50h+var_C8]
0x14006f610  mov     qword ptr [rsp+160h+InputBufferLength], rax
0x14006f615  lea     rax, [rbp+50h+var_A0]
0x14006f619  mov     [rsp+160h+InputBuffer], rax
0x14006f61e  lea     rax, [rbp+50h+var_B8]
0x14006f622  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f627  lea     rax, [rbp+50h+var_C4]
0x14006f62b  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f630  call    Smb2RkfReadState
0x14006f635  mov     ebx, eax
0x14006f637  test    eax, eax
0x14006f639  jns     loc_14006F6DB
0x14006f63f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f646  cmp     rcx, rsi
0x14006f649  jz      short loc_14006F681
0x14006f64b  test    [rcx+2Ch], edi
0x14006f64e  jz      short loc_14006F681
0x14006f650  mov     dil, 1
0x14006f653  cmp     [rcx+29h], dil
0x14006f657  jb      short loc_14006F681
0x14006f659  mov     edx, 14h
0x14006f65e  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f665  mov     rcx, [rcx+18h]
0x14006f669  lea     rax, [r15+0C0h]
0x14006f670  mov     [rsp+160h+FsControlCode], ebx
0x14006f674  mov     r9, r13
0x14006f677  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f67c  call    WPP_SF_qZd
0x14006f681  mov     r14b, [rbp+50h+arg_0]
0x14006f685  mov     rcx, [rbp+50h+P]; P
0x14006f689  test    rcx, rcx
0x14006f68c  jz      short loc_14006F69C
0x14006f68e  xor     edx, edx; Tag
0x14006f690  call    cs:__imp_ExFreePoolWithTag
0x14006f697  nop     dword ptr [rax+rax+00h]
0x14006f69c  test    ebx, ebx
0x14006f69e  jns     short loc_14006F6BD
0x14006f6a0  test    r14b, r14b
0x14006f6a3  jnz     short loc_14006F6BD
0x14006f6a5  mov     rdx, [r15+50h]
0x14006f6a9  mov     rcx, [r13+40h]
0x14006f6ad  mov     rdx, [rdx+60h]
0x14006f6b1  call    Smb2RkfNotifyComplete
0x14006f6b6  mov     [r15+17Dh], r14b
0x14006f6bd  mov     eax, ebx
0x14006f6bf  mov     rbx, [rsp+160h+arg_8]
0x14006f6c7  add     rsp, 130h
0x14006f6ce  pop     r15
0x14006f6d0  pop     r14
0x14006f6d2  pop     r13
0x14006f6d4  pop     r12
0x14006f6d6  pop     rdi
0x14006f6d7  pop     rsi
0x14006f6d8  pop     rbp
0x14006f6d9  retn
0x14006f6db  mov     rsi, [rbp+50h+P]
0x14006f6df  cmp     dword ptr [rsi], 3
0x14006f6e2  jz      short loc_14006F732
0x14006f6e4  mov     ebx, r14d
0x14006f6e7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f6ee  lea     rax, WPP_GLOBAL_Control
0x14006f6f5  cmp     rcx, rax
0x14006f6f8  jz      short loc_14006F681
0x14006f6fa  test    [rcx+2Ch], edi
0x14006f6fd  jz      short loc_14006F681
0x14006f6ff  cmp     byte ptr [rcx+29h], 2
0x14006f703  jb      loc_14006F681
0x14006f709  mov     rcx, [rcx+18h]
0x14006f70d  lea     rax, [r15+0C0h]
0x14006f714  mov     edx, 15h
0x14006f719  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f71e  mov     r9, r13
0x14006f721  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f728  call    WPP_SF_qZ
0x14006f72d  jmp     loc_14006F681
0x14006f732  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f739  lea     rax, WPP_GLOBAL_Control
0x14006f740  mov     r14d, [rbp+50h+var_C8]
0x14006f744  cmp     rcx, rax
0x14006f747  jz      short loc_14006F790
0x14006f749  test    [rcx+2Ch], edi
0x14006f74c  jz      short loc_14006F790
0x14006f74e  cmp     byte ptr [rcx+29h], 2
0x14006f752  jb      short loc_14006F790
0x14006f754  mov     eax, [rbp+50h+arg_18]
0x14006f757  lea     rdx, [r15+0C0h]
0x14006f75e  mov     rcx, [rcx+18h]
0x14006f762  mov     r9, r13
0x14006f765  mov     [rsp+160h+OutputBufferLength], eax
0x14006f769  mov     eax, [rsi+58h]
0x14006f76c  mov     dword ptr [rsp+160h+OutputBuffer], r14d
0x14006f771  mov     [rsp+160h+InputBufferLength], eax
0x14006f775  mov     eax, [rbp+50h+var_C4]
0x14006f778  mov     dword ptr [rsp+160h+InputBuffer], eax
0x14006f77c  mov     rax, [r12+50h]
0x14006f781  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f786  mov     qword ptr [rsp+160h+InitialState], rdx
0x14006f78b  call    WPP_SF_qZiDDDD
0x14006f790  mov     edx, [rbp+50h+var_C0]
0x14006f793  mov     dil, 1
0x14006f796  mov     r8, rsi
0x14006f799  mov     [r15+17Ch], dil
0x14006f7a0  mov     rcx, r13
0x14006f7a3  call    Smb2RkfResumeAppInstance
0x14006f7a8  lea     rsi, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f7af  test    al, al
0x14006f7b1  jz      short loc_14006F7DC
0x14006f7b3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f7ba  lea     rax, WPP_GLOBAL_Control
0x14006f7c1  cmp     rcx, rax
0x14006f7c4  jz      short loc_14006F81E
0x14006f7c6  test    dword ptr [rcx+2Ch], 100000h
0x14006f7cd  jz      short loc_14006F81E
0x14006f7cf  cmp     byte ptr [rcx+29h], 2
0x14006f7d3  jb      short loc_14006F81E
0x14006f7d5  mov     edx, 17h
0x14006f7da  jmp     short loc_14006F803
0x14006f7dc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f7e3  lea     rax, WPP_GLOBAL_Control
0x14006f7ea  cmp     rcx, rax
0x14006f7ed  jz      short loc_14006F81E
0x14006f7ef  test    dword ptr [rcx+2Ch], 100000h
0x14006f7f6  jz      short loc_14006F81E
0x14006f7f8  cmp     byte ptr [rcx+29h], 2
0x14006f7fc  jb      short loc_14006F81E
0x14006f7fe  mov     edx, 18h
0x14006f803  mov     rcx, [rcx+18h]
0x14006f807  lea     rax, [r15+0C0h]
0x14006f80e  mov     r9, r13
0x14006f811  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f816  mov     r8, rsi
0x14006f819  call    WPP_SF_qZ
0x14006f81e  mov     r9, [rbp+50h+var_A8]
0x14006f822  test    r9, r9
0x14006f825  jz      short loc_14006F877
0x14006f827  mov     rdx, [rbp+50h+var_A0]
0x14006f82b  mov     r8d, r14d
0x14006f82e  mov     rcx, r12
0x14006f831  call    Smb2RestoreFileLockState
0x14006f836  mov     ebx, eax
0x14006f838  test    eax, eax
0x14006f83a  jns     short loc_14006F877
0x14006f83c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f843  lea     rax, WPP_GLOBAL_Control
0x14006f84a  cmp     rcx, rax
0x14006f84d  jz      loc_14006F681
0x14006f853  test    dword ptr [rcx+2Ch], 100000h
0x14006f85a  jz      loc_14006F681
0x14006f860  cmp     [rcx+29h], dil
0x14006f864  jb      loc_14006F681
0x14006f86a  mov     edx, 19h
0x14006f86f  mov     r8, rsi
0x14006f872  jmp     loc_14006F665
0x14006f877  mov     r14, [rbp+50h+var_98]
0x14006f87b  mov     edx, 200h
0x14006f880  test    r14, r14
0x14006f883  jz      loc_14006FA03
0x14006f889  mov     [rbp+50h+ObjectAttributes.Attributes], edx
0x14006f88c  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x14006f890  xorps   xmm0, xmm0
0x14006f893  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14006f89a  mov     edx, 1F0003h; DesiredAccess
0x14006f89f  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x14006f8a7  xor     r9d, r9d; EventType
0x14006f8aa  mov     [rbp+50h+ObjectAttributes.ObjectName], 0
0x14006f8b2  lea     rcx, [rbp+50h+EventHandle]; EventHandle
0x14006f8b6  mov     [rsp+160h+InitialState], 0; InitialState
0x14006f8bb  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006f8c0  call    cs:__imp_ZwCreateEvent
0x14006f8c7  nop     dword ptr [rax+rax+00h]
0x14006f8cc  mov     ebx, eax
0x14006f8ce  test    eax, eax
0x14006f8d0  js      loc_14006F681
0x14006f8d6  mov     rcx, [r15+50h]
0x14006f8da  xor     r9d, r9d; ApcContext
0x14006f8dd  mov     eax, [rbp+50h+arg_18]
0x14006f8e0  xor     r8d, r8d; ApcRoutine
0x14006f8e3  mov     rdx, [rbp+50h+EventHandle]; Event
0x14006f8e7  mov     [rsp+160h+OutputBufferLength], 0; OutputBufferLength
0x14006f8ef  mov     rcx, [rcx+58h]; FileHandle
0x14006f8f3  mov     [rsp+160h+OutputBuffer], 0; OutputBuffer
0x14006f8fc  mov     [rsp+160h+InputBufferLength], eax; InputBufferLength
0x14006f900  lea     rax, [rbp+50h+IoStatusBlock]
0x14006f904  mov     [rsp+160h+InputBuffer], r14; InputBuffer
0x14006f909  mov     [rsp+160h+FsControlCode], 90308h; FsControlCode
0x14006f911  mov     qword ptr [rsp+160h+InitialState], rax; IoStatusBlock
0x14006f916  call    cs:__imp_ZwFsControlFile
0x14006f91d  nop     dword ptr [rax+rax+00h]
0x14006f922  mov     ebx, eax
0x14006f924  cmp     eax, 103h
0x14006f929  jnz     short loc_14006F943
0x14006f92b  mov     rcx, [rbp+50h+EventHandle]; Handle
0x14006f92f  xor     r8d, r8d; Timeout
0x14006f932  xor     edx, edx; Alertable
0x14006f934  call    cs:__imp_ZwWaitForSingleObject
0x14006f93b  nop     dword ptr [rax+rax+00h]
0x14006f940  mov     ebx, dword ptr [rbp+50h+IoStatusBlock]
0x14006f943  mov     rcx, [rbp+50h+EventHandle]; Handle
0x14006f947  call    cs:__imp_ZwClose
0x14006f94e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
