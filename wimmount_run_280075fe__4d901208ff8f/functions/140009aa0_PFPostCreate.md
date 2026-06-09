# PFPostCreate

- ea: `0x140009aa0`
- end: `0x140009f54`
- name: `PFPostCreate`
- size: `1204`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001558`
- `0x140002a94`
- `0x140002c90`
- `0x140009378`
- `0x1400095c8`
- `0x1400098a8`
- `0x140009aa0`
- `0x14000a0d0`
- `0x14000aa98`
- `0x14000b938`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009df1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009df1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140009bc2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140009bc2`
- `ntoskrnl!KeSetEvent` at `0x140009cfb`
- `ntoskrnl!KeSetEvent` at `0x140009cfb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140009d8e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140009d8e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140009ee0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140009ee0`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cbf`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cbf`
- `FLTMGR!FltClose` at `0x140009e4a`
- `FLTMGR!FltClose` at `0x140009f14`
- `FLTMGR!FltClose` at `0x140009e4a`
- `FLTMGR!FltClose` at `0x140009f14`
- `FLTMGR!FltDeleteStreamContext` at `0x140009d11`
- `FLTMGR!FltDeleteStreamContext` at `0x140009d11`
- `FLTMGR!FltReissueSynchronousIo` at `0x140009b8f`
- `FLTMGR!FltReissueSynchronousIo` at `0x140009e64`
- `FLTMGR!FltReissueSynchronousIo` at `0x140009b8f`
- `FLTMGR!FltReissueSynchronousIo` at `0x140009e64`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009b34`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009eca`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009b34`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009eca`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140009cda`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140009cda`
- `FLTMGR!FltReleaseContext` at `0x140009e86`
- `FLTMGR!FltReleaseContext` at `0x140009e86`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140009b7c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140009b7c`

## pseudocode

```c
__int64 __fastcall PFPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _DWORD *a3, __int64 a4)
{
  NTSTATUS Lock; // ebx
  HANDLE v5; // r14
  struct _KEVENT *v6; // rsi
  char v7; // r13
  NTSTATUS Status; // eax
  _DWORD *v12; // rdx
  _QWORD *v13; // r8
  _QWORD *v14; // rax
  struct _FLT_TAG_DATA_BUFFER *TagData; // rax
  NTSTATUS v16; // eax
  struct _FILE_OBJECT *v17; // r13
  PVOID v18; // r8
  NTSTATUS v19; // eax
  struct _FLT_TAG_DATA_BUFFER *v20; // rax
  unsigned int TagDataLength; // r13d
  int v22; // eax
  __int64 v23; // rdx
  LONG v24; // eax
  NTSTATUS v25; // eax
  int v26; // eax
  int v28; // [rsp+28h] [rbp-48h]
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _KEVENT *v31; // [rsp+40h] [rbp-30h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-28h] BYREF
  PVOID P; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__usercall *v34)@<rax>(PFLT_CALLBACK_DATA@<rcx>, __int64); // [rsp+58h] [rbp-18h]
  _DWORD *v35; // [rsp+60h] [rbp-10h]
  char v36; // [rsp+B0h] [rbp+40h]
  PVOID Object; // [rsp+C0h] [rbp+50h] BYREF

  Lock = 0;
  v5 = 0;
  v6 = 0;
  FileHandle = 0;
  v7 = 0;
  v34 = 0;
  v35 = 0;
  P = 0;
  if ( !a3 )
    goto LABEL_17;
  Status = CallbackData->IoStatus.Status;
  if ( Status != -1073741194 && Status != -1073741192 )
  {
    v12 = a3 + 14;
    goto LABEL_6;
  }
  v12 = a3 + 14;
  if ( !a3[14] )
  {
LABEL_6:
    if ( Status != 260 )
      goto LABEL_17;
    if ( CallbackData->IoStatus.Information == 2147483656 )
    {
      if ( *(_QWORD *)(a2 + 40) )
        goto LABEL_17;
      if ( CallbackData->TagData->UnparsedNameLength )
      {
        v35 = a3;
        v34 = PFOnlyConsiderDirectories;
        goto LABEL_17;
      }
    }
    else if ( !*v12 )
    {
      goto LABEL_17;
    }
  }
  v13 = *(_QWORD **)a3;
  if ( v13 )
  {
    if ( (_QWORD *)*v13 != v13 )
    {
      FltRemoveOpenReparseEntry(*(_QWORD *)(a2 + 8), CallbackData);
      v14 = *(_QWORD **)a3;
      v14[1] = v14;
      *v14 = v14;
    }
  }
  else
  {
    CallbackData->Iopb->Parameters.Create.Options |= *v12;
    FltSetCallbackDataDirty(CallbackData);
  }
  FltReissueSynchronousIo(*(PFLT_INSTANCE *)(a2 + 24), CallbackData);
LABEL_17:
  if ( CallbackData->IoStatus.Status != 260 )
    goto LABEL_63;
  while ( 1 )
  {
    TagData = CallbackData->TagData;
    if ( !TagData || TagData->FileTag != -2147483640 || IoGetTopLevelIrp() )
      goto LABEL_61;
    v6 = 0;
    Object = 0;
    v31 = 0;
    FileNameInformation = 0;
    v36 = 0;
    LOWORD(v29) = 0;
    v16 = PFOpenReparseTarget(CallbackData, a2, &FileNameInformation, &Object);
    v17 = (struct _FILE_OBJECT *)Object;
    Lock = v16;
    if ( (int)(v16 + 0x80000000) < 0 || v16 == -1073741195 )
    {
      if ( v16 == -1073741195 )
      {
        Lock = 0;
        goto LABEL_32;
      }
      if ( !v34 )
        goto LABEL_29;
      v18 = Object;
      LOBYTE(Object) = 0;
      Lock = ((__int64 (__fastcall *)(PFLT_CALLBACK_DATA, __int64, PVOID, _DWORD *, PVOID *))v34)(
               CallbackData,
               a2,
               v18,
               v35,
               &Object);
      if ( Lock < 0 )
        goto LABEL_32;
      if ( (_BYTE)Object )
      {
        Lock = 0;
        BYTE1(v29) = 1;
      }
      else
      {
LABEL_29:
        Lock = PFGetContextByFileObject(*(PFLT_FILTER *)(a2 + 8), *(PFLT_INSTANCE *)(a2 + 24), v17, (__int64)&v29);
        v36 = v29;
        if ( (_BYTE)v29 )
        {
          v19 = PFGetWritableHandle(CallbackData, a2, FileNameInformation, v17, &FileHandle);
          v5 = FileHandle;
          Lock = v19;
        }
        v6 = v31;
      }
    }
LABEL_32:
    if ( v17 )
    {
      ObfDereferenceObject(v17);
      v17 = 0;
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( Lock < 0 )
    {
      if ( v36 )
      {
        v6[1].Header.LockNV = Lock;
        KeSetEvent(v6, 0, 0);
        FltDeleteStreamContext(*(PFLT_INSTANCE *)(a2 + 24), v17, 0);
        v7 = 0;
        v36 = 0;
      }
      else
      {
        v7 = 0;
      }
      if ( v6 )
      {
        FltReleaseContext(v6);
        v6 = 0;
        goto LABEL_61;
      }
      goto LABEL_60;
    }
    v7 = v36;
    if ( BYTE1(v29) )
      goto LABEL_61;
    if ( !v36 )
      break;
    v20 = CallbackData->TagData;
    TagDataLength = v20->TagDataLength;
    if ( TagDataLength < 0x10 )
    {
      Lock = -1073741811;
      goto LABEL_60;
    }
    Object = &v20->SymbolicLinkReparseBuffer;
    v22 = WMCommListGet(&v20->SymbolicLinkReparseBuffer, &P);
    Lock = v22;
    if ( v22 == -1073741275 )
    {
      Lock = 260;
LABEL_60:
      v7 = v36;
      goto LABEL_61;
    }
    if ( v22 < 0 )
      goto LABEL_60;
    PsGetCurrentProcessId();
    v24 = PFSendExtractMessage(&FileHandle, v23, P, Object, TagDataLength);
    v6[1].Header.LockNV = v24;
    Lock = v24;
    PFSetSubsumedStatus(*(PFLT_INSTANCE *)(a2 + 24));
    v5 = FileHandle;
    v7 = v36;
    if ( Lock < 0 )
      goto LABEL_61;
LABEL_53:
    LOBYTE(v28) = 1;
    LOBYTE(a4) = v7;
    v26 = PFReleaseContextAndUntagFile(CallbackData, a2, v6, a4, v5, v28);
    v6 = 0;
    Lock = v26;
    if ( v26 >= 0 )
    {
      v7 = 0;
      if ( v5 )
      {
        FltClose(v5);
        v5 = 0;
        FileHandle = 0;
      }
      FltReissueSynchronousIo(*(PFLT_INSTANCE *)(a2 + 24), CallbackData);
      if ( CallbackData->IoStatus.Status == 260 )
        continue;
    }
    goto LABEL_61;
  }
  if ( !v6 )
    goto LABEL_53;
  v25 = KeWaitForSingleObject(v6, UserRequest, 0, 1u, 0);
  Lock = v25;
  if ( v25 != 257 )
  {
    if ( v25 < 0 )
      goto LABEL_61;
    if ( v6[1].Header.LockNV >= 0 )
      goto LABEL_53;
  }
  Lock = v6[1].Header.Lock;
LABEL_61:
  if ( P )
    WMCommListEntryRelease(P);
LABEL_63:
  if ( a3 )
  {
    if ( *(_QWORD *)a3 && **(_QWORD **)a3 != *(_QWORD *)a3 )
      FltRemoveOpenReparseEntry(*(_QWORD *)(a2 + 8), CallbackData);
    ExFreeToPagedLookasideList(&Lookaside, a3);
  }
  if ( v6 )
  {
    LOBYTE(v28) = 0;
    LOBYTE(a4) = v7;
    PFReleaseContextAndUntagFile(CallbackData, a2, v6, a4, v5, v28);
  }
  if ( v5 )
    FltClose(v5);
  if ( Lock < 0 )
    CallbackData->IoStatus.Status = Lock;
  return 0;
}

```

## disassembly

```asm
0x140009aa0  mov     [rsp-38h+arg_8], rbx
0x140009aa5  push    rbp
0x140009aa6  push    rsi
0x140009aa7  push    rdi
0x140009aa8  push    r12
0x140009aaa  push    r13
0x140009aac  push    r14
0x140009aae  push    r15
0x140009ab0  mov     rbp, rsp
0x140009ab3  sub     rsp, 70h
0x140009ab7  xor     ebx, ebx
0x140009ab9  xor     r14d, r14d
0x140009abc  xor     esi, esi
0x140009abe  mov     [rbp+FileHandle], r14
0x140009ac2  xor     r13b, r13b
0x140009ac5  mov     [rbp+var_18], rbx
0x140009ac9  mov     [rbp+var_10], rbx
0x140009acd  mov     rdi, rcx
0x140009ad0  mov     [rbp+P], rbx
0x140009ad4  mov     r12, r8
0x140009ad7  mov     r15, rdx
0x140009ada  mov     ecx, 80000008h
0x140009adf  test    r8, r8
0x140009ae2  jz      loc_140009BA0
0x140009ae8  mov     eax, [rdi+18h]
0x140009aeb  cmp     eax, 0C0000276h
0x140009af0  jz      short loc_140009AFF
0x140009af2  cmp     eax, 0C0000278h
0x140009af7  jz      short loc_140009AFF
0x140009af9  lea     rdx, [r8+38h]
0x140009afd  jmp     short loc_140009B07
0x140009aff  lea     rdx, [r8+38h]
0x140009b03  cmp     [rdx], ebx
0x140009b05  jnz     short loc_140009B20
0x140009b07  cmp     eax, 104h
0x140009b0c  jnz     loc_140009BA0
0x140009b12  cmp     [rdi+20h], rcx
0x140009b16  jz      short loc_140009B4D
0x140009b18  cmp     [rdx], ebx
0x140009b1a  jz      loc_140009BA0
0x140009b20  mov     r8, [r8]
0x140009b23  test    r8, r8
0x140009b26  jz      short loc_140009B70
0x140009b28  cmp     [r8], r8
0x140009b2b  jz      short loc_140009B88
0x140009b2d  mov     rcx, [r15+8]
0x140009b31  mov     rdx, rdi
0x140009b34  call    cs:__imp_FltRemoveOpenReparseEntry
0x140009b3b  nop     dword ptr [rax+rax+00h]
0x140009b40  mov     rax, [r12]
0x140009b44  mov     [rax+8], rax
0x140009b48  mov     [rax], rax
0x140009b4b  jmp     short loc_140009B88
0x140009b4d  cmp     [r15+28h], rbx
0x140009b51  jnz     short loc_140009BA0
0x140009b53  mov     rcx, [rdi+28h]
0x140009b57  xor     eax, eax
0x140009b59  cmp     ax, [rcx+6]
0x140009b5d  jz      short loc_140009B20
0x140009b5f  lea     rax, PFOnlyConsiderDirectories
0x140009b66  mov     [rbp+var_10], r12
0x140009b6a  mov     [rbp+var_18], rax
0x140009b6e  jmp     short loc_140009B9B
0x140009b70  mov     rcx, [rdi+10h]
0x140009b74  mov     eax, [rdx]
0x140009b76  or      [rcx+20h], eax
0x140009b79  mov     rcx, rdi; Data
0x140009b7c  call    cs:__imp_FltSetCallbackDataDirty
0x140009b83  nop     dword ptr [rax+rax+00h]
0x140009b88  mov     rcx, [r15+18h]; InitiatingInstance
0x140009b8c  mov     rdx, rdi; CallbackData
0x140009b8f  call    cs:__imp_FltReissueSynchronousIo
0x140009b96  nop     dword ptr [rax+rax+00h]
0x140009b9b  mov     ecx, 80000008h
0x140009ba0  cmp     dword ptr [rdi+18h], 104h
0x140009ba7  jnz     loc_140009EB0
0x140009bad  mov     rax, [rdi+28h]
0x140009bb1  test    rax, rax
0x140009bb4  jz      loc_140009E9F
0x140009bba  cmp     [rax], ecx
0x140009bbc  jnz     loc_140009E9F
0x140009bc2  call    cs:__imp_IoGetTopLevelIrp
0x140009bc9  nop     dword ptr [rax+rax+00h]
0x140009bce  test    rax, rax
0x140009bd1  jnz     loc_140009E9F
0x140009bd7  xor     esi, esi
0x140009bd9  mov     [rbp+Object], rax
0x140009bdd  lea     r9, [rbp+Object]
0x140009be1  mov     [rbp+var_30], rsi
0x140009be5  lea     r8, [rbp+FileNameInformation]
0x140009be9  mov     [rbp+FileNameInformation], rax
0x140009bed  mov     rdx, r15
0x140009bf0  mov     byte ptr [rbp+var_40+1], al
0x140009bf3  mov     rcx, rdi
0x140009bf6  mov     [rbp+arg_0], al
0x140009bf9  mov     byte ptr [rbp+var_40], al
0x140009bfc  call    PFOpenReparseTarget
0x140009c01  mov     r13, [rbp+Object]
0x140009c05  mov     ecx, 80000000h
0x140009c0a  mov     ebx, eax
0x140009c0c  add     eax, ecx
0x140009c0e  test    ecx, eax
0x140009c10  jnz     short loc_140009C1E
0x140009c12  cmp     ebx, 0C0000275h
0x140009c18  jnz     loc_140009CB7
0x140009c1e  cmp     ebx, 0C0000275h
0x140009c24  jnz     short loc_140009C2D
0x140009c26  xor     ebx, ebx
0x140009c28  jmp     loc_140009CB7
0x140009c2d  mov     rax, [rbp+var_18]
0x140009c31  test    rax, rax
0x140009c34  jz      short loc_140009C69
0x140009c36  mov     r9, [rbp+var_10]
0x140009c3a  lea     rcx, [rbp+Object]
0x140009c3e  mov     [rsp+70h+Timeout], rcx
0x140009c43  mov     r8, r13
0x140009c46  mov     rcx, rdi
0x140009c49  mov     byte ptr [rbp+Object], sil
0x140009c4d  mov     rdx, r15
0x140009c50  call    _guard_dispatch_icall
0x140009c55  mov     ebx, eax
0x140009c57  test    eax, eax
0x140009c59  js      short loc_140009CB7
0x140009c5b  cmp     byte ptr [rbp+Object], sil
0x140009c5f  jz      short loc_140009C69
0x140009c61  xor     ebx, ebx
0x140009c63  mov     byte ptr [rbp+var_40+1], 1
0x140009c67  jmp     short loc_140009CB7
0x140009c69  mov     rdx, [r15+18h]; Instance
0x140009c6d  lea     rax, [rbp+var_40]
0x140009c71  mov     rcx, [r15+8]; Filter
0x140009c75  lea     r9, [rbp+var_30]
0x140009c79  mov     r8, r13; FileObject
0x140009c7c  mov     [rsp+70h+Timeout], rax; __int64
0x140009c81  call    PFGetContextByFileObject
0x140009c86  mov     ebx, eax
0x140009c88  mov     al, byte ptr [rbp+var_40]
0x140009c8b  mov     [rbp+arg_0], al
0x140009c8e  test    al, al
0x140009c90  jz      short loc_140009CB3
0x140009c92  mov     r8, [rbp+FileNameInformation]
0x140009c96  lea     rax, [rbp+FileHandle]
0x140009c9a  mov     r9, r13
0x140009c9d  mov     [rsp+70h+Timeout], rax
0x140009ca2  mov     rdx, r15
0x140009ca5  mov     rcx, rdi
0x140009ca8  call    PFGetWritableHandle
0x140009cad  mov     r14, [rbp+FileHandle]
0x140009cb1  mov     ebx, eax
0x140009cb3  mov     rsi, [rbp+var_30]
0x140009cb7  test    r13, r13
0x140009cba  jz      short loc_140009CCE
0x140009cbc  mov     rcx, r13; Object
0x140009cbf  call    cs:__imp_ObfDereferenceObject
0x140009cc6  nop     dword ptr [rax+rax+00h]
0x140009ccb  xor     r13d, r13d
0x140009cce  mov     rax, [rbp+FileNameInformation]
0x140009cd2  test    rax, rax
0x140009cd5  jz      short loc_140009CE6
0x140009cd7  mov     rcx, rax; FileNameInformation
0x140009cda  call    cs:__imp_FltReleaseFileNameInformation
0x140009ce1  nop     dword ptr [rax+rax+00h]
0x140009ce6  test    ebx, ebx
0x140009ce8  jns     short loc_140009D3B
0x140009cea  cmp     [rbp+arg_0], 0
0x140009cee  jz      short loc_140009D26
0x140009cf0  xor     r8d, r8d; Wait
0x140009cf3  mov     [rsi+18h], ebx
0x140009cf6  xor     edx, edx; Increment
0x140009cf8  mov     rcx, rsi; Event
0x140009cfb  call    cs:__imp_KeSetEvent
0x140009d02  nop     dword ptr [rax+rax+00h]
0x140009d07  mov     rcx, [r15+18h]; Instance
0x140009d0b  xor     r8d, r8d; OldContext
0x140009d0e  mov     rdx, r13; FileObject
0x140009d11  call    cs:__imp_FltDeleteStreamContext
0x140009d18  nop     dword ptr [rax+rax+00h]
0x140009d1d  xor     r13b, r13b
0x140009d20  mov     [rbp+arg_0], r13b
0x140009d24  jmp     short loc_140009D2A
0x140009d26  mov     r13b, [rbp+arg_0]
0x140009d2a  test    rsi, rsi
0x140009d2d  jnz     loc_140009E83
0x140009d33  test    ebx, ebx
0x140009d35  js      loc_140009E9B
0x140009d3b  cmp     byte ptr [rbp+var_40+1], 0
0x140009d3f  mov     r13b, [rbp+arg_0]
0x140009d43  jnz     loc_140009E9F
0x140009d49  test    r13b, r13b
0x140009d4c  jz      loc_140009DD6
0x140009d52  mov     rax, [rdi+28h]
0x140009d56  movzx   r13d, word ptr [rax+4]
0x140009d5b  cmp     r13d, 10h
0x140009d5f  jb      loc_140009F42
0x140009d65  add     rax, 8
0x140009d69  lea     rdx, [rbp+P]
0x140009d6d  mov     rcx, rax
0x140009d70  mov     [rbp+Object], rax
0x140009d74  call    WMCommListGet
0x140009d79  mov     ebx, eax
0x140009d7b  cmp     eax, 0C0000225h
0x140009d80  jz      loc_140009E96
0x140009d86  test    eax, eax
0x140009d88  js      loc_140009E9B
0x140009d8e  call    cs:__imp_PsGetCurrentProcessId
0x140009d95  nop     dword ptr [rax+rax+00h]
0x140009d9a  mov     r9, [rbp+Object]
0x140009d9e  lea     rcx, [rbp+FileHandle]
0x140009da2  mov     r8, [rbp+P]
0x140009da6  mov     dword ptr [rsp+70h+Timeout], r13d
0x140009dab  call    PFSendExtractMessage
0x140009db0  mov     [rsi+18h], eax
0x140009db3  mov     r8d, eax
0x140009db6  mov     rcx, [r15+18h]; InitiatingInstance
0x140009dba  mov     rdx, rsi
0x140009dbd  mov     ebx, eax
0x140009dbf  call    PFSetSubsumedStatus
0x140009dc4  mov     r14, [rbp+FileHandle]
0x140009dc8  mov     r13b, [rbp+arg_0]
0x140009dcc  test    ebx, ebx
0x140009dce  js      loc_140009E9F
0x140009dd4  jmp     short loc_140009E1C
0x140009dd6  test    rsi, rsi
0x140009dd9  jz      short loc_140009E1C
0x140009ddb  xor     r8d, r8d; WaitMode
0x140009dde  mov     [rsp+70h+Timeout], 0; Timeout
0x140009de7  mov     r9b, 1; Alertable
0x140009dea  mov     rcx, rsi; Object
0x140009ded  lea     edx, [r8+6]; WaitReason
0x140009df1  call    cs:__imp_KeWaitForSingleObject
0x140009df8  nop     dword ptr [rax+rax+00h]
0x140009dfd  mov     ebx, eax
0x140009dff  cmp     eax, 101h
0x140009e04  jz      loc_140009F4C
0x140009e0a  test    eax, eax
0x140009e0c  js      loc_140009E9F
0x140009e12  cmp     dword ptr [rsi+18h], 0
0x140009e16  jl      loc_140009F4C
0x140009e1c  mov     [rsp+70h+var_48], 1
0x140009e21  mov     r9b, r13b
0x140009e24  mov     r8, rsi
0x140009e27  mov     [rsp+70h+Timeout], r14
0x140009e2c  mov     rdx, r15
0x140009e2f  mov     rcx, rdi
0x140009e32  call    PFReleaseContextAndUntagFile
0x140009e37  xor     esi, esi
0x140009e39  mov     ebx, eax
0x140009e3b  test    eax, eax
0x140009e3d  js      short loc_140009E9F
0x140009e3f  xor     r13b, r13b
0x140009e42  test    r14, r14
0x140009e45  jz      short loc_140009E5D
0x140009e47  mov     rcx, r14; FileHandle
0x140009e4a  call    cs:__imp_FltClose
0x140009e51  nop     dword ptr [rax+rax+00h]
0x140009e56  xor     r14d, r14d
0x140009e59  mov     [rbp+FileHandle], r14
0x140009e5d  mov     rcx, [r15+18h]; InitiatingInstance
0x140009e61  mov     rdx, rdi; CallbackData
0x140009e64  call    cs:__imp_FltReissueSynchronousIo
0x140009e6b  nop     dword ptr [rax+rax+00h]
0x140009e70  cmp     dword ptr [rdi+18h], 104h
0x140009e77  jnz     short loc_140009E9F
0x140009e79  mov     ecx, 80000008h
0x140009e7e  jmp     loc_140009BAD
0x140009e83  mov     rcx, rsi; Context
0x140009e86  call    cs:__imp_FltReleaseContext
0x140009e8d  nop     dword ptr [rax+rax+00h]
0x140009e92  xor     esi, esi
0x140009e94  jmp     short loc_140009E9F
0x140009e96  mov     ebx, 104h
0x140009e9b  mov     r13b, [rbp+arg_0]
0x140009e9f  mov     rax, [rbp+P]
0x140009ea3  test    rax, rax
0x140009ea6  jz      short loc_140009EB0
0x140009ea8  mov     rcx, rax; P
0x140009eab  call    WMCommListEntryRelease
0x140009eb0  test    r12, r12
0x140009eb3  jz      short loc_140009EEC
0x140009eb5  mov     r8, [r12]
0x140009eb9  test    r8, r8
0x140009ebc  jz      short loc_140009ED6
0x140009ebe  cmp     [r8], r8
0x140009ec1  jz      short loc_140009ED6
0x140009ec3  mov     rcx, [r15+8]
0x140009ec7  mov     rdx, rdi
0x140009eca  call    cs:__imp_FltRemoveOpenReparseEntry
0x140009ed1  nop     dword ptr [rax+rax+00h]
0x140009ed6  mov     rdx, r12; Entry
0x140009ed9  lea     rcx, Lookaside; Lookaside
0x140009ee0  call    cs:__imp_ExFreeToPagedLookasideList
0x140009ee7  nop     dword ptr [rax+rax+00h]
0x140009eec  test    rsi, rsi
0x140009eef  jz      short loc_140009F0C
0x140009ef1  mov     [rsp+70h+var_48], 0
0x140009ef6  mov     r9b, r13b
0x140009ef9  mov     r8, rsi
0x140009efc  mov     [rsp+70h+Timeout], r14
0x140009f01  mov     rdx, r15
0x140009f04  mov     rcx, rdi
  ... truncated ...
```
