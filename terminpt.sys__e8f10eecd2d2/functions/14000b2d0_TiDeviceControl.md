# TiDeviceControl

- ea: `0x14000b2d0`
- end: `0x14000b783`
- name: `TiDeviceControl`
- size: `1203`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x1400023c4`
- `0x1400024e8`
- `0x1400026a0`
- `0x140002c7c`
- `0x140002e58`
- `0x140009b60`
- `0x14000b2d0`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b3af`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b3af`
- `ntoskrnl!IofCompleteRequest` at `0x14000b477`
- `ntoskrnl!IofCompleteRequest` at `0x14000b477`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b415`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b415`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14000b539`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14000b539`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x14000b583`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x14000b583`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000b574`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000b574`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b5da`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b5da`
- `ntoskrnl!ZwOpenFile` at `0x14000b643`
- `ntoskrnl!ZwOpenFile` at `0x14000b643`
- `ntoskrnl!ZwClose` at `0x14000b655`
- `ntoskrnl!ZwClose` at `0x14000b655`

## pseudocode

```c
__int64 __fastcall TiDeviceControl(__int64 a1, IRP *a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  DWORD LowPart; // ebx
  unsigned __int64 Options; // r12
  ULONG Length; // r14d
  _QWORD *FsContext2; // rsi
  int v11; // edx
  int v12; // r8d
  NTSTATUS RequestorSessionId; // ebx
  unsigned __int64 MasterIrp; // rdx
  int v15; // r8d
  DWORD v16; // ebx
  DWORD v17; // ebx
  DWORD v18; // ebx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 CurrentServerSilo; // rax
  int ServerSiloServiceSessionId; // eax
  __int64 v24; // rcx
  int v25; // edx
  int v26; // r8d
  KPROCESSOR_MODE AccessMode[4]; // [rsp+28h] [rbp-41h]
  _QWORD v28[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  ULONG pSessionId; // [rsp+D0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+D8h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+77h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      22,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  a2->IoStatus.Information = 0;
  if ( *(_DWORD *)(a1 + 72) != 56 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        23,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    return PtDeviceControl(a1, a2);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(FsContext2 + 3), &TiDeviceControl, File, 1u, 0x20u) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        24,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    RequestorSessionId = -1073741667;
    goto LABEL_17;
  }
  TiLockSession(FsContext2[24]);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(FsContext2 + 3), &TiDeviceControl, 0x20u);
  v16 = LowPart - 3704836;
  if ( !v16 )
  {
    if ( !a2->AssociatedIrp.MasterIrp || (MasterIrp = Options / 0xC, Options != 12 * (Options / 0xC)) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v21 = 25;
      goto LABEL_26;
    }
    PtSendCurrentKeyboardInput(*FsContext2, a2->AssociatedIrp.MasterIrp, (unsigned int)MasterIrp);
    goto LABEL_43;
  }
  v17 = v16 - 4;
  if ( !v17 )
  {
    if ( !a2->AssociatedIrp.MasterIrp || (MasterIrp = Options / 0x18, Options != 24 * (Options / 0x18)) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v21 = 27;
      goto LABEL_26;
    }
    PtSendCurrentMouseInput(*FsContext2, a2->AssociatedIrp.MasterIrp, (unsigned int)MasterIrp);
LABEL_43:
    RequestorSessionId = 0;
    goto LABEL_16;
  }
  v18 = v17 - 4;
  if ( v18 )
  {
    if ( v18 != 4 )
    {
      RequestorSessionId = -1073741808;
      goto LABEL_16;
    }
    MasterIrp = (unsigned __int64)a2->AssociatedIrp.MasterIrp;
    if ( MasterIrp && Length == 12 )
    {
      RequestorSessionId = PtSendCurrentKeyboardIndicators(*FsContext2, MasterIrp, a2);
      goto LABEL_16;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v21 = 26;
    goto LABEL_26;
  }
  pSessionId = 0;
  RequestorSessionId = IoGetRequestorSessionId(a2, &pSessionId);
  if ( RequestorSessionId >= 0 )
  {
    if ( Length != 8 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v21 = 28;
LABEL_26:
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        MasterIrp,
        v15,
        v21,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
LABEL_27:
      RequestorSessionId = -1073741811;
      goto LABEL_16;
    }
    CurrentServerSilo = PsGetCurrentServerSilo();
    ServerSiloServiceSessionId = PsGetServerSiloServiceSessionId(CurrentServerSilo);
    if ( ServerSiloServiceSessionId == pSessionId )
    {
      v24 = FsContext2[24];
      Handle = 0;
      FileHandle = 0;
      TiUnlockSession(v24);
      RequestorSessionId = ObOpenObjectByPointer((PVOID)FsContext2[2], 0x200u, 0, 0x80000000, 0, 0, &Handle);
      if ( RequestorSessionId >= 0 )
      {
        v28[0] = 0x20000;
        v28[1] = &word_1400052E8;
        ObjectAttributes.RootDirectory = Handle;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v28;
        IoStatusBlock = 0;
        memset(&ObjectAttributes.Attributes, 0, 24);
        RequestorSessionId = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x40001u);
        ZwClose(Handle);
      }
      TiLockSession(FsContext2[24]);
      if ( RequestorSessionId < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_s(
            WPP_GLOBAL_Control->DeviceExtension,
            v25,
            v26,
            29,
            (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
      }
      else
      {
        *(_QWORD *)a2->AssociatedIrp.MasterIrp = FileHandle;
        a2->IoStatus.Information = 8;
      }
    }
    else
    {
      RequestorSessionId = -1073741790;
    }
  }
LABEL_16:
  TiUnlockSession(FsContext2[24]);
  if ( RequestorSessionId != 259 )
  {
LABEL_17:
    a2->IoStatus.Status = RequestorSessionId;
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      v20,
      30,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids,
      *(_DWORD *)AccessMode,
      a1,
      RequestorSessionId);
  return (unsigned int)RequestorSessionId;
}

```

## disassembly

```asm
0x14000b2d0  mov     [rsp-8+arg_18], rbx
0x14000b2d5  push    rbp
0x14000b2d6  push    rsi
0x14000b2d7  push    rdi
0x14000b2d8  push    r12
0x14000b2da  push    r13
0x14000b2dc  push    r14
0x14000b2de  push    r15
0x14000b2e0  lea     rbp, [rsp-27h]
0x14000b2e5  sub     rsp, 90h
0x14000b2ec  mov     rdi, rdx
0x14000b2ef  mov     r15, rcx
0x14000b2f2  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b2f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b300  lea     rcx, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b307  jz      short loc_14000B332
0x14000b309  mov     qword ptr [rsp+0C0h+RemlockSize], rcx
0x14000b30e  mov     r9d, 16h
0x14000b314  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b31b  mov     rcx, [rcx+40h]
0x14000b31f  call    WPP_RECORDER_SF_s
0x14000b324  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b32b  lea     rcx, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b332  mov     qword ptr [rdi+38h], 0
0x14000b33a  cmp     dword ptr [r15+48h], 38h ; '8'
0x14000b33f  jz      short loc_14000B375
0x14000b341  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b348  jz      short loc_14000B365
0x14000b34a  mov     qword ptr [rsp+0C0h+RemlockSize], rcx
0x14000b34f  mov     r9d, 17h
0x14000b355  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b35c  mov     rcx, [rcx+40h]
0x14000b360  call    WPP_RECORDER_SF_s
0x14000b365  mov     rdx, rdi
0x14000b368  mov     rcx, r15
0x14000b36b  call    PtDeviceControl
0x14000b370  jmp     loc_14000B4B2
0x14000b375  mov     rcx, [rdi+0B8h]
0x14000b37c  lea     r8, File; File
0x14000b383  mov     r9d, 1; Line
0x14000b389  mov     [rsp+0C0h+RemlockSize], 20h ; ' '; RemlockSize
0x14000b391  lea     rdx, TiDeviceControl; Tag
0x14000b398  mov     rax, [rcx+30h]
0x14000b39c  mov     ebx, [rcx+18h]
0x14000b39f  mov     r12d, [rcx+10h]
0x14000b3a3  mov     r14d, [rcx+8]
0x14000b3a7  mov     rsi, [rax+20h]
0x14000b3ab  lea     rcx, [rsi+18h]; RemoveLock
0x14000b3af  call    cs:__imp_IoAcquireRemoveLockEx
0x14000b3b6  nop     dword ptr [rax+rax+00h]
0x14000b3bb  test    eax, eax
0x14000b3bd  jns     short loc_14000B3F8
0x14000b3bf  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b3c6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b3cd  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b3d4  jz      short loc_14000B3F1
0x14000b3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b3dd  mov     r9d, 18h
0x14000b3e3  mov     qword ptr [rsp+0C0h+RemlockSize], r12
0x14000b3e8  mov     rcx, [rcx+40h]
0x14000b3ec  call    WPP_RECORDER_SF_s
0x14000b3f1  mov     ebx, 0C000009Dh
0x14000b3f6  jmp     short loc_14000B46F
0x14000b3f8  mov     rcx, [rsi+0C0h]
0x14000b3ff  call    TiLockSession
0x14000b404  mov     r8d, 20h ; ' '; RemlockSize
0x14000b40a  lea     rdx, TiDeviceControl; Tag
0x14000b411  lea     rcx, [rsi+18h]; RemoveLock
0x14000b415  call    cs:__imp_IoReleaseRemoveLockEx
0x14000b41c  nop     dword ptr [rax+rax+00h]
0x14000b421  sub     ebx, 388804h
0x14000b427  jz      loc_14000B726
0x14000b42d  sub     ebx, 4
0x14000b430  jz      loc_14000B6C4
0x14000b436  sub     ebx, 4
0x14000b439  jz      loc_14000B52B
0x14000b43f  cmp     ebx, 4
0x14000b442  jz      loc_14000B4CE
0x14000b448  mov     ebx, 0C0000010h
0x14000b44d  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b454  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b45b  mov     rcx, [rsi+0C0h]
0x14000b462  call    TiUnlockSession
0x14000b467  cmp     ebx, 103h
0x14000b46d  jz      short loc_14000B483
0x14000b46f  xor     edx, edx; PriorityBoost
0x14000b471  mov     [rdi+30h], ebx
0x14000b474  mov     rcx, rdi; Irp
0x14000b477  call    cs:__imp_IofCompleteRequest
0x14000b47e  nop     dword ptr [rax+rax+00h]
0x14000b483  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b48a  jz      short loc_14000B4B0
0x14000b48c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b493  mov     r9d, 1Eh
0x14000b499  mov     [rsp+0C0h+var_88], ebx
0x14000b49d  mov     [rsp+0C0h+Handle], r15
0x14000b4a2  mov     qword ptr [rsp+0C0h+RemlockSize], r12
0x14000b4a7  mov     rcx, [rcx+40h]
0x14000b4ab  call    WPP_RECORDER_SF_sqd
0x14000b4b0  mov     eax, ebx
0x14000b4b2  mov     rbx, [rsp+0C0h+arg_18]
0x14000b4ba  add     rsp, 90h
0x14000b4c1  pop     r15
0x14000b4c3  pop     r14
0x14000b4c5  pop     r13
0x14000b4c7  pop     r12
0x14000b4c9  pop     rdi
0x14000b4ca  pop     rsi
0x14000b4cb  pop     rbp
0x14000b4cc  retn
0x14000b4ce  mov     rdx, [rdi+18h]
0x14000b4d2  test    rdx, rdx
0x14000b4d5  jz      short loc_14000B4EF
0x14000b4d7  cmp     r14d, 0Ch
0x14000b4db  jnz     short loc_14000B4EF
0x14000b4dd  mov     rcx, [rsi]
0x14000b4e0  mov     r8, rdi
0x14000b4e3  call    PtSendCurrentKeyboardIndicators
0x14000b4e8  mov     ebx, eax
0x14000b4ea  jmp     loc_14000B44D
0x14000b4ef  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b4f6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b4fd  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b504  jz      short loc_14000B521
0x14000b506  mov     r9d, 1Ah
0x14000b50c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b513  mov     qword ptr [rsp+0C0h+RemlockSize], r12
0x14000b518  mov     rcx, [rcx+40h]
0x14000b51c  call    WPP_RECORDER_SF_s
0x14000b521  mov     ebx, 0C000000Dh
0x14000b526  jmp     loc_14000B45B
0x14000b52b  xor     r12d, r12d
0x14000b52e  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x14000b532  mov     rcx, rdi; Irp
0x14000b535  mov     [rbp+57h+pSessionId], r12d
0x14000b539  call    cs:__imp_IoGetRequestorSessionId
0x14000b540  nop     dword ptr [rax+rax+00h]
0x14000b545  mov     ebx, eax
0x14000b547  test    eax, eax
0x14000b549  js      loc_14000B44D
0x14000b54f  cmp     r14d, 8
0x14000b553  jz      short loc_14000B574
0x14000b555  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b55c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b563  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b56a  jz      short loc_14000B521
0x14000b56c  mov     r9d, 1Ch
0x14000b572  jmp     short loc_14000B50C
0x14000b574  call    cs:__imp_PsGetCurrentServerSilo
0x14000b57b  nop     dword ptr [rax+rax+00h]
0x14000b580  mov     rcx, rax
0x14000b583  call    cs:__imp_PsGetServerSiloServiceSessionId
0x14000b58a  nop     dword ptr [rax+rax+00h]
0x14000b58f  cmp     eax, [rbp+57h+pSessionId]
0x14000b592  jz      short loc_14000B59E
0x14000b594  mov     ebx, 0C0000022h
0x14000b599  jmp     loc_14000B44D
0x14000b59e  mov     rcx, [rsi+0C0h]
0x14000b5a5  mov     [rbp+57h+arg_8], r12
0x14000b5a9  mov     [rbp+57h+FileHandle], r12
0x14000b5ad  call    TiUnlockSession
0x14000b5b2  mov     rcx, [rsi+10h]; Object
0x14000b5b6  lea     rax, [rbp+57h+arg_8]
0x14000b5ba  mov     [rsp+0C0h+Handle], rax; Handle
0x14000b5bf  mov     r14d, 80000000h
0x14000b5c5  mov     [rsp+0C0h+AccessMode], r12b; AccessMode
0x14000b5ca  mov     r9d, r14d; DesiredAccess
0x14000b5cd  xor     r8d, r8d; PassedAccessState
0x14000b5d0  mov     qword ptr [rsp+0C0h+RemlockSize], r12; ObjectType
0x14000b5d5  mov     edx, 200h; HandleAttributes
0x14000b5da  call    cs:__imp_ObOpenObjectByPointer
0x14000b5e1  nop     dword ptr [rax+rax+00h]
0x14000b5e6  mov     ebx, eax
0x14000b5e8  test    eax, eax
0x14000b5ea  js      short loc_14000B661
0x14000b5ec  xorps   xmm0, xmm0
0x14000b5ef  mov     dword ptr [rsp+0C0h+AccessMode], 40001h; OpenOptions
0x14000b5f7  lea     rax, word_1400052E8
0x14000b5fe  mov     [rbp+57h+var_80], 20000h
0x14000b606  mov     [rbp+57h+var_78], rax
0x14000b60a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000b60e  mov     rax, [rbp+57h+arg_8]
0x14000b612  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000b616  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000b61a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000b61e  lea     rax, [rbp+57h+var_80]
0x14000b622  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000b62a  mov     edx, r14d; DesiredAccess
0x14000b62d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000b631  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000b635  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r12
0x14000b639  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b63e  mov     [rsp+0C0h+RemlockSize], r12d; ShareAccess
0x14000b643  call    cs:__imp_ZwOpenFile
0x14000b64a  nop     dword ptr [rax+rax+00h]
0x14000b64f  mov     rcx, [rbp+57h+arg_8]; Handle
0x14000b653  mov     ebx, eax
0x14000b655  call    cs:__imp_ZwClose
0x14000b65c  nop     dword ptr [rax+rax+00h]
0x14000b661  mov     rcx, [rsi+0C0h]
0x14000b668  call    TiLockSession
0x14000b66d  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b674  test    ebx, ebx
0x14000b676  js      short loc_14000B690
0x14000b678  mov     rcx, [rdi+18h]
0x14000b67c  mov     rax, [rbp+57h+FileHandle]
0x14000b680  mov     [rcx], rax
0x14000b683  mov     qword ptr [rdi+38h], 8
0x14000b68b  jmp     loc_14000B454
0x14000b690  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b697  jz      loc_14000B454
0x14000b69d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6a4  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b6ab  mov     r9d, 1Dh
0x14000b6b1  mov     qword ptr [rsp+0C0h+RemlockSize], r12
0x14000b6b6  mov     rcx, [rcx+40h]
0x14000b6ba  call    WPP_RECORDER_SF_s
0x14000b6bf  jmp     loc_14000B45B
0x14000b6c4  mov     r9, [rdi+18h]
0x14000b6c8  test    r9, r9
0x14000b6cb  jz      short loc_14000B700
0x14000b6cd  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000b6d7  mul     r12
0x14000b6da  shr     rdx, 4
0x14000b6de  lea     rax, [rdx+rdx*2]
0x14000b6e2  shl     rax, 3
0x14000b6e6  cmp     r12, rax
0x14000b6e9  jnz     short loc_14000B700
0x14000b6eb  mov     rcx, [rsi]
0x14000b6ee  mov     r8d, edx
0x14000b6f1  mov     rdx, r9
0x14000b6f4  call    PtSendCurrentMouseInput
0x14000b6f9  xor     ebx, ebx
0x14000b6fb  jmp     loc_14000B44D
0x14000b700  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b707  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b70e  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b715  jz      loc_14000B521
0x14000b71b  mov     r9d, 1Bh
0x14000b721  jmp     loc_14000B50C
0x14000b726  mov     r9, [rdi+18h]
0x14000b72a  test    r9, r9
0x14000b72d  jz      short loc_14000B75D
0x14000b72f  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000b739  mul     r12
0x14000b73c  shr     rdx, 3
0x14000b740  lea     rax, [rdx+rdx*2]
0x14000b744  shl     rax, 2
0x14000b748  cmp     r12, rax
0x14000b74b  jnz     short loc_14000B75D
0x14000b74d  mov     rcx, [rsi]
0x14000b750  mov     r8d, edx
0x14000b753  mov     rdx, r9
0x14000b756  call    PtSendCurrentKeyboardInput
0x14000b75b  jmp     short loc_14000B6F9
0x14000b75d  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b764  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b76b  lea     r12, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b772  jz      loc_14000B521
0x14000b778  mov     r9d, 19h
0x14000b77e  jmp     loc_14000B50C
```
