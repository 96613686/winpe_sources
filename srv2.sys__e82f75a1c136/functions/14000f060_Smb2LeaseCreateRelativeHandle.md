# Smb2LeaseCreateRelativeHandle

- ea: `0x14000f060`
- end: `0x14000f417`
- name: `Smb2LeaseCreateRelativeHandle`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000e5f0`

## callees

- `0x140004960`
- `0x140005070`
- `0x14000f060`
- `0x14001bd4c`
- `0x14002f3dc`
- `0x1400593dc`
- `0x140091cc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000f376`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000f376`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f3dc`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f3dc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f391`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f391`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000f2c9`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000f2c9`
- `ntoskrnl!NtClose` at `0x14000f403`
- `ntoskrnl!NtClose` at `0x14000f403`
- `ntoskrnl!IoCreateFileEx` at `0x14000f292`
- `ntoskrnl!IoCreateFileEx` at `0x14000f292`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f0b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f0b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f0fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f0fa`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000f1aa`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000f1aa`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000f136`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000f136`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000f16f`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000f16f`

## string_xrefs

- `0x14000f357`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2LeaseCreateRelativeHandle(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rcx
  NTSTATUS Parameter; // edi
  __int64 v7; // rcx
  int v8; // ecx
  PDEVICE_OBJECT v9; // rcx
  signed __int64 v10; // rax
  __int64 result; // rax
  bool v12; // zf
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rdx
  struct _ECP_LIST *PoolTag; // [rsp+20h] [rbp-E0h]
  int EcpContext; // [rsp+28h] [rbp-D8h]
  ULONG Disposition; // [rsp+38h] [rbp-C8h]
  int EaBuffer; // [rsp+48h] [rbp-B8h]
  ULONG EaLength; // [rsp+50h] [rbp-B0h]
  CREATE_FILE_TYPE CreateFileType; // [rsp+58h] [rbp-A8h]
  int InternalParameters; // [rsp+60h] [rbp-A0h]
  ULONG Options; // [rsp+68h] [rbp-98h]
  _QWORD v25[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+F8h] [rbp-8h] BYREF
  PVOID v31; // [rsp+158h] [rbp+58h] BYREF
  PECP_LIST EcpList; // [rsp+160h] [rbp+60h] BYREF
  void *FileHandle; // [rsp+168h] [rbp+68h] BYREF

  FileHandle = 0;
  v25[0] = 0;
  v25[1] = 0;
  v4 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a2 + 112), &LockHandle);
  if ( (unsigned int)(*(_DWORD *)(a2 + 12) - 219) <= 1 )
  {
    v5 = *(_QWORD *)(a2 + 120);
    if ( v5 )
    {
      if ( !*(_BYTE *)(v5 + 104) )
      {
        v4 = *(_QWORD *)(a2 + 120);
        if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)v5, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          __int2c();
      }
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !v4 )
    return 0;
  EcpList = 0;
  LOWORD(v27) = 0;
  v31 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  Parameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
  if ( Parameter < 0 )
    goto LABEL_14;
  Parameter = FsRtlAllocateExtraCreateParameter(&GUID_ECP_DUAL_OPLOCK_KEY, 0x24u, 0, 0, 0x5324534Cu, &v31);
  if ( Parameter < 0 )
    goto LABEL_14;
  *((_OWORD *)v31 + 1) = *(_OWORD *)(a1 + 80);
  *((_BYTE *)v31 + 33) = 1;
  *((_BYTE *)v31 + 32) = 0;
  Parameter = FsRtlInsertExtraCreateParameter(EcpList, v31);
  if ( Parameter < 0 )
    goto LABEL_14;
  v7 = *(_QWORD *)(a2 + 128);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = *(HANDLE *)(v4 + 88);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v25;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (*(_DWORD *)(v7 + 288) & 0x4000) != 0 || (*(_DWORD *)(v7 + 368) & 0x1000000) != 0 )
  {
    Parameter = Smb2CreateFileWithBypassEcp(
                  &FileHandle,
                  0x80u,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  PoolTag,
                  EcpContext,
                  7u,
                  Disposition,
                  *(_DWORD *)(a2 + 192) & 8 | 0x200000u,
                  EaBuffer,
                  EaLength,
                  CreateFileType,
                  InternalParameters,
                  Options,
                  (__int64)EcpList);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 37;
      goto LABEL_37;
    }
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 192) & 8;
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    *(&DriverContext.Size + 3) = 0;
    v27 = 1;
    DriverContext.Size = 40;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    DriverContext.ExtraCreateParameter = EcpList;
    Parameter = IoCreateFileEx(
                  &FileHandle,
                  0x80u,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0,
                  7u,
                  1u,
                  v8 | 0x200000,
                  0,
                  0,
                  CreateFileTypeNone,
                  EcpList,
                  0,
                  &DriverContext);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 38;
LABEL_37:
      WPP_SF_Dqq(
        v9->AttachedDevice,
        v15,
        WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
        (unsigned int)Parameter,
        a2,
        a1);
    }
  }
LABEL_14:
  if ( EcpList )
    FsRtlFreeExtraCreateParameterList(EcpList);
  v10 = _InterlockedDecrement64((volatile signed __int64 *)v4);
  if ( v10 == -1 )
  {
    __int2c();
  }
  else if ( !v10 )
  {
    if ( KeGetCurrentIrql() )
    {
      v12 = *(_DWORD *)(v4 + 8) == 5;
      *(_QWORD *)(v4 + 48) = Smb2DereferenceHandleCallback;
      *(_DWORD *)(v4 + 72) = 0;
      if ( v12 )
      {
        LOBYTE(PoolTag) = 1;
        LOBYTE(v16) = 1;
        SRV2_PERF_ENTER_EX(v4 + 584, v16, 391, "Srv2PostToThreadPool", (_DWORD)PoolTag);
      }
      v13 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 136LL);
      v14 = *(_QWORD *)(v13 + 8LL * KeGetCurrentNodeNumber() + 8);
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v14, (PSLIST_ENTRY)(v4 + 32)) && *(_WORD *)(v14 + 66) )
        RfspThreadPoolNodeWakeIdleWorker(v14);
    }
    else
    {
      Smb2DereferenceHandleCleanup((PVOID)v4);
    }
  }
  if ( Parameter < 0 )
    return 0;
  result = Smb2AllocateReferencedHandle(*(_QWORD *)(a1 + 64), FileHandle, 0);
  if ( !result )
  {
    NtClose(FileHandle);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f060  push    rbp
0x14000f062  push    rbx
0x14000f063  push    rsi
0x14000f064  push    r12
0x14000f066  push    r14
0x14000f068  push    r15
0x14000f06a  lea     rbp, [rsp-18h]
0x14000f06f  sub     rsp, 118h
0x14000f076  xorps   xmm0, xmm0
0x14000f079  xor     r12d, r12d
0x14000f07c  mov     r14, rcx
0x14000f07f  mov     [rbp+40h+FileHandle], r12
0x14000f083  lea     rcx, [rdx+70h]; SpinLock
0x14000f087  mov     [rbp+40h+var_C0], r12
0x14000f08b  mov     rbx, rdx
0x14000f08e  mov     [rbp+40h+var_B8], r12
0x14000f092  xor     eax, eax
0x14000f094  lea     rdx, [rbp+40h+LockHandle]; LockHandle
0x14000f098  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x14000f09c  mov     qword ptr [rbp+40h+LockHandle.OldIrql], rax
0x14000f0a0  mov     esi, r12d
0x14000f0a3  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x14000f0a7  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x14000f0ab  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x14000f0af  movups  xmmword ptr [rbp+40h+LockHandle.LockQueue.Next], xmm0
0x14000f0b3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f0ba  nop     dword ptr [rax+rax+00h]
0x14000f0bf  mov     eax, [rbx+0Ch]
0x14000f0c2  sub     eax, 0DBh
0x14000f0c7  cmp     eax, 1
0x14000f0ca  ja      short loc_14000F0F6
0x14000f0cc  mov     rcx, [rbx+78h]
0x14000f0d0  test    rcx, rcx
0x14000f0d3  jz      short loc_14000F0F6
0x14000f0d5  cmp     [rcx+68h], sil
0x14000f0d9  jnz     short loc_14000F0F6
0x14000f0db  mov     rsi, rcx
0x14000f0de  mov     eax, 1
0x14000f0e3  lock xadd [rcx], rax
0x14000f0e8  add     rax, 2
0x14000f0ec  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000f0f2  jnz     short loc_14000F0F6
0x14000f0f4  int     2Ch; Windows NT - assertion failure
0x14000f0f6  lea     rcx, [rbp+40h+LockHandle]; LockHandle
0x14000f0fa  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f101  nop     dword ptr [rax+rax+00h]
0x14000f106  test    rsi, rsi
0x14000f109  jz      loc_14000F331
0x14000f10f  xorps   xmm0, xmm0
0x14000f112  mov     [rsp+140h+var_30], rdi
0x14000f11a  xor     eax, eax
0x14000f11c  mov     [rbp+40h+EcpList], r12
0x14000f120  lea     rdx, [rbp+40h+EcpList]; EcpList
0x14000f124  mov     word ptr [rbp+40h+var_90], ax
0x14000f128  xor     ecx, ecx; Flags
0x14000f12a  mov     [rbp+40h+arg_8], r12
0x14000f12e  movups  xmmword ptr [rbp+40h+var_B0.Size], xmm0
0x14000f132  movups  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x14000f136  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14000f13d  nop     dword ptr [rax+rax+00h]
0x14000f142  mov     edi, eax
0x14000f144  test    eax, eax
0x14000f146  js      loc_14000F2C0
0x14000f14c  lea     rax, [rbp+40h+arg_8]
0x14000f150  xor     r9d, r9d; CleanupCallback
0x14000f153  mov     [rsp+140h+EcpContext], rax; int
0x14000f158  lea     rcx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x14000f15f  xor     r8d, r8d; Flags
0x14000f162  mov     [rsp+140h+PoolTag], 5324534Ch; EcpList
0x14000f16a  mov     edx, 24h ; '$'; SizeOfContext
0x14000f16f  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14000f176  nop     dword ptr [rax+rax+00h]
0x14000f17b  mov     edi, eax
0x14000f17d  test    eax, eax
0x14000f17f  js      loc_14000F2C0
0x14000f185  mov     rax, [rbp+40h+arg_8]
0x14000f189  movups  xmm0, xmmword ptr [r14+50h]
0x14000f18e  movups  xmmword ptr [rax+10h], xmm0
0x14000f192  mov     rax, [rbp+40h+arg_8]
0x14000f196  mov     byte ptr [rax+21h], 1
0x14000f19a  mov     rax, [rbp+40h+arg_8]
0x14000f19e  mov     [rax+20h], r12b
0x14000f1a2  mov     rdx, [rbp+40h+arg_8]; EcpContext
0x14000f1a6  mov     rcx, [rbp+40h+EcpList]; EcpList
0x14000f1aa  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14000f1b1  nop     dword ptr [rax+rax+00h]
0x14000f1b6  mov     edi, eax
0x14000f1b8  test    eax, eax
0x14000f1ba  js      loc_14000F2C0
0x14000f1c0  mov     rcx, [rbx+80h]
0x14000f1c7  xorps   xmm0, xmm0
0x14000f1ca  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x14000f1d1  mov     rax, [rsi+58h]
0x14000f1d5  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x14000f1d9  lea     rax, [rbp+40h+var_C0]
0x14000f1dd  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x14000f1e1  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14000f1e8  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f1ed  test    dword ptr [rcx+120h], 4000h
0x14000f1f7  jnz     loc_14003B95A
0x14000f1fd  test    dword ptr [rcx+170h], 1000000h
0x14000f207  jnz     loc_14003B95A
0x14000f20d  mov     ecx, [rbx+0C0h]
0x14000f213  lea     rdx, [rbp+40h+var_B0]
0x14000f217  mov     [rsp+140h+DriverContext], rdx; DriverContext
0x14000f21c  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x14000f220  mov     [rsp+140h+Options], r12d; Options
0x14000f225  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x14000f229  and     ecx, 8
0x14000f22c  mov     dword ptr [rbp+40h+var_B0+2], r12d
0x14000f230  bts     ecx, 15h
0x14000f234  mov     word ptr [rbp+40h+var_B0+6], r12w
0x14000f239  mov     eax, 28h ; '('
0x14000f23e  mov     [rbp+40h+var_90], 1
0x14000f246  mov     [rbp+40h+var_B0.Size], ax
0x14000f24a  mov     edx, 80h; DesiredAccess
0x14000f24f  mov     rax, [rbp+40h+EcpList]
0x14000f253  mov     [rsp+140h+InternalParameters], rax; InternalParameters
0x14000f258  mov     [rsp+140h+CreateFileType], r12d; CreateFileType
0x14000f25d  mov     [rsp+140h+EaLength], r12d; EaLength
0x14000f262  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14000f267  mov     [rsp+140h+CreateOptions], ecx; CreateOptions
0x14000f26b  lea     rcx, [rbp+40h+FileHandle]; FileHandle
0x14000f26f  mov     [rsp+140h+Disposition], 1; Disposition
0x14000f277  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x14000f27f  mov     dword ptr [rsp+140h+EcpContext], r12d; FileAttributes
0x14000f284  mov     qword ptr [rsp+140h+PoolTag], r12; AllocationSize
0x14000f289  movdqu  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x14000f28e  mov     [rbp+40h+var_B0.ExtraCreateParameter], rax
0x14000f292  call    cs:__imp_IoCreateFileEx
0x14000f299  nop     dword ptr [rax+rax+00h]
0x14000f29e  mov     edi, eax
0x14000f2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2a7  lea     rax, WPP_GLOBAL_Control
0x14000f2ae  cmp     rcx, rax
0x14000f2b1  jz      short loc_14000F2C0
0x14000f2b3  test    dword ptr [rcx+2Ch], 40000000h
0x14000f2ba  jnz     loc_14000F3C1
0x14000f2c0  mov     rcx, [rbp+40h+EcpList]; EcpList
0x14000f2c4  test    rcx, rcx
0x14000f2c7  jz      short loc_14000F2D5
0x14000f2c9  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14000f2d0  nop     dword ptr [rax+rax+00h]
0x14000f2d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000f2dc  lock xadd [rsi], rax
0x14000f2e1  dec     rax
0x14000f2e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f2e8  jnb     loc_14000F3D5
0x14000f2ee  test    rax, rax
0x14000f2f1  jz      loc_14000F3DC
0x14000f2f7  test    edi, edi
0x14000f2f9  mov     rdi, [rsp+140h+var_30]
0x14000f301  js      short loc_14000F331
0x14000f303  mov     rdx, [rbp+40h+FileHandle]
0x14000f307  xor     r8d, r8d
0x14000f30a  mov     rcx, [r14+40h]
0x14000f30e  call    Smb2AllocateReferencedHandle
0x14000f313  mov     rbx, rax
0x14000f316  test    rax, rax
0x14000f319  jz      loc_14000F3FF
0x14000f31f  add     rsp, 118h
0x14000f326  pop     r15
0x14000f328  pop     r14
0x14000f32a  pop     r12
0x14000f32c  pop     rsi
0x14000f32d  pop     rbx
0x14000f32e  pop     rbp
0x14000f32f  retn
0x14000f331  mov     rax, r12
0x14000f334  jmp     short loc_14000F31F
0x14000f336  cmp     dword ptr [rsi+8], 5
0x14000f33a  lea     rax, Smb2DereferenceHandleCallback
0x14000f341  mov     [rsi+30h], rax
0x14000f345  mov     [rsi+48h], r12d
0x14000f349  jnz     short loc_14000F36B
0x14000f34b  lea     rcx, [rsi+248h]
0x14000f352  mov     byte ptr [rsp+140h+PoolTag], 1
0x14000f357  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000f35e  mov     r8d, 187h
0x14000f364  mov     dl, 1
0x14000f366  call    SRV2_PERF_ENTER_EX
0x14000f36b  mov     rax, [rsi+40h]
0x14000f36f  mov     rbx, [rax+88h]
0x14000f376  call    cs:__imp_KeGetCurrentNodeNumber
0x14000f37d  nop     dword ptr [rax+rax+00h]
0x14000f382  movzx   eax, ax
0x14000f385  lea     rdx, [rsi+20h]; ListEntry
0x14000f389  mov     rbx, [rbx+rax*8+8]
0x14000f38e  mov     rcx, rbx; ListHead
0x14000f391  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000f398  nop     dword ptr [rax+rax+00h]
0x14000f39d  test    rax, rax
0x14000f3a0  jnz     loc_14000F2F7
0x14000f3a6  movzx   edx, word ptr [rbx+42h]
0x14000f3aa  cmp     r12w, dx
0x14000f3ae  jz      loc_14000F2F7
0x14000f3b4  mov     rcx, rbx
0x14000f3b7  call    RfspThreadPoolNodeWakeIdleWorker
0x14000f3bc  jmp     loc_14000F2F7
0x14000f3c1  cmp     byte ptr [rcx+29h], 2
0x14000f3c5  jb      loc_14000F2C0
0x14000f3cb  mov     edx, 26h ; '&'
0x14000f3d0  jmp     loc_14003B9C7
0x14000f3d5  int     2Ch; Windows NT - assertion failure
0x14000f3d7  jmp     loc_14000F2F7
0x14000f3dc  call    cs:__imp_KeGetCurrentIrql
0x14000f3e3  nop     dword ptr [rax+rax+00h]
0x14000f3e8  test    al, al
0x14000f3ea  jnz     loc_14000F336
0x14000f3f0  xor     edx, edx
0x14000f3f2  mov     rcx, rsi; P
0x14000f3f5  call    Smb2DereferenceHandleCleanup
0x14000f3fa  jmp     loc_14000F2F7
0x14000f3ff  mov     rcx, [rbp+40h+FileHandle]; Handle
0x14000f403  call    cs:__imp_NtClose
0x14000f40a  nop     dword ptr [rax+rax+00h]
0x14000f40f  mov     rax, rbx
0x14000f412  jmp     loc_14000F31F
0x14003b95a  mov     ecx, [rbx+0C0h]
0x14003b960  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x14003b964  mov     rax, [rbp+40h+EcpList]
0x14003b968  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x14003b96c  and     ecx, 8
0x14003b96f  mov     [rsp+140h+DriverContext], rax; __int64
0x14003b974  bts     ecx, 15h
0x14003b978  mov     edx, 80h; DesiredAccess
0x14003b97d  mov     [rsp+140h+CreateOptions], ecx; ULONG
0x14003b981  lea     rcx, [rbp+40h+FileHandle]; FileHandle
0x14003b985  mov     [rsp+140h+ShareAccess], 7; ULONG
0x14003b98d  call    Smb2CreateFileWithBypassEcp
0x14003b992  mov     edi, eax
0x14003b994  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b99b  lea     rax, WPP_GLOBAL_Control
0x14003b9a2  cmp     rcx, rax
0x14003b9a5  jz      loc_14000F2C0
0x14003b9ab  test    dword ptr [rcx+2Ch], 40000000h
0x14003b9b2  jz      loc_14000F2C0
0x14003b9b8  cmp     byte ptr [rcx+29h], 2
0x14003b9bc  jb      loc_14000F2C0
0x14003b9c2  mov     edx, 25h ; '%'
0x14003b9c7  mov     rcx, [rcx+18h]
0x14003b9cb  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x14003b9d2  mov     [rsp+140h+EcpContext], r14
0x14003b9d7  mov     r9d, edi
0x14003b9da  mov     qword ptr [rsp+140h+PoolTag], rbx
0x14003b9df  call    WPP_SF_Dqq
0x14003b9e4  nop
0x14003b9e5  jmp     loc_14000F2C0
```
