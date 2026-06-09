# WimFSFReadWim

- ea: `0x14003ccf0`
- end: `0x14003d215`
- name: `WimFSFReadWim`
- size: `1317`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID, __int64, int, PVOID Context)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14002e1f4`
- `0x14003da08`

## callees

- `0x14000afc0`
- `0x14000bf54`
- `0x14000c074`
- `0x14000cfe0`
- `0x14000d2fc`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010774`
- `0x14003ccf0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003cfc2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003cfc2`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003ceb8`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003d112`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003ceb8`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003d112`
- `ntoskrnl!KeInitializeEvent` at `0x14003ce5f`
- `ntoskrnl!KeInitializeEvent` at `0x14003cf5a`
- `ntoskrnl!KeInitializeEvent` at `0x14003d1e8`
- `ntoskrnl!KeInitializeEvent` at `0x14003ce5f`
- `ntoskrnl!KeInitializeEvent` at `0x14003cf5a`
- `ntoskrnl!KeInitializeEvent` at `0x14003d1e8`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003d130`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003d130`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x14003d103`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x14003d103`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14003d186`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14003d186`
- `FLTMGR!FltReadFile` at `0x14003cf2f`
- `FLTMGR!FltReadFile` at `0x14003cf2f`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003ce1b`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003ce1b`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003d1f8`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003d1f8`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003d03b`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003d03b`
- `FLTMGR!FltPropagateIrpExtension` at `0x14003d05f`
- `FLTMGR!FltPropagateIrpExtension` at `0x14003d05f`
- `FLTMGR!FltFreeCallbackData` at `0x14003d075`
- `FLTMGR!FltFreeCallbackData` at `0x14003d075`

## pseudocode

```c
__int64 __fastcall WimFSFReadWim(
        unsigned __int8 a1,
        __int64 a2,
        __int64 a3,
        struct _FLT_CALLBACK_DATA *a4,
        PVOID a5,
        void *a6,
        int a7,
        char *Context)
{
  char *v8; // rdi
  int v10; // r15d
  char v11; // r12
  struct _FLT_INSTANCE *v12; // r13
  __int64 v13; // r14
  int v14; // esi
  int v15; // r9d
  char v16; // al
  ULONG v17; // r12d
  PVOID v18; // rbx
  PVOID Buffer; // r15
  NTSTATUS v20; // ebx
  char v21; // si
  __int64 v23; // rcx
  struct _FILE_OBJECT *v24; // rdx
  PFLT_CALLBACK_DATA v25; // rax
  void *v26; // rdx
  int v27; // [rsp+50h] [rbp-18h] BYREF
  ULONG BytesRead; // [rsp+54h] [rbp-14h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-10h] BYREF
  SIZE_T NumberOfBytes; // [rsp+B8h] [rbp+50h] BYREF
  char v32; // [rsp+C0h] [rbp+58h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+C8h] [rbp+60h] BYREF

  RetNewCallbackData = a4;
  v32 = a3;
  v8 = Context;
  v10 = a1;
  v11 = a2;
  BytesRead = 0;
  ByteOffset.QuadPart = 0;
  v12 = (struct _FLT_INSTANCE *)*((_QWORD *)Context + 5);
  v13 = *((_QWORD *)Context + 6);
  LODWORD(NumberOfBytes) = 0;
  v27 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  v14 = a7;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_iqDl(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a4, a5, a7, v10);
  *((_DWORD *)v8 + 29) = 0;
  if ( v11 )
  {
    ByteOffset.QuadPart = (LONGLONG)a4;
    v17 = v14;
  }
  else
  {
    if ( (_BYTE)v10 )
      v15 = *(_DWORD *)(v13 + 92);
    else
      v15 = 1;
    v16 = WimFSFGetAlignedSizesForIntegrity(
            v13,
            (unsigned int)&RetNewCallbackData,
            v14,
            v15,
            (__int64)&ByteOffset,
            (__int64)&NumberOfBytes,
            (__int64)&v27);
    v17 = NumberOfBytes;
    v32 = v16;
  }
  if ( (struct _FLT_CALLBACK_DATA *)ByteOffset.QuadPart == a4 && v17 == v14 )
  {
    v18 = a5;
    Buffer = a5;
  }
  else
  {
    a6 = 0;
    Buffer = FltAllocatePoolAlignedWithTag(v12, (POOL_TYPE)512, v17, 0x44527077u);
    if ( !Buffer )
    {
      v20 = -1073741670;
      goto LABEL_38;
    }
    v18 = a5;
  }
  if ( (*((_DWORD *)v8 + 36) & 1) != 0 )
  {
    v8[201] = 1;
    KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
  }
  else
  {
    v8[201] = 0;
  }
  v8[152] = v32;
  *((union _LARGE_INTEGER *)v8 + 20) = ByteOffset;
  *((_DWORD *)v8 + 46) = v27;
  *((_DWORD *)v8 + 39) = v14;
  *((_QWORD *)v8 + 21) = Buffer;
  *((_QWORD *)v8 + 22) = v18;
  WimFSFReferenceReadCompletionContext(v8);
  if ( !a1 && !KeAreAllApcsDisabled() )
  {
    v8[200] = 0;
    v21 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    v20 = FltReadFile(
            *(PFLT_INSTANCE *)(*(_QWORD *)(v13 + 40) + 120LL),
            *(PFILE_OBJECT *)(v13 + 72),
            &ByteOffset,
            v17,
            Buffer,
            4u,
            &BytesRead,
            0,
            0);
    if ( !v8[201] )
    {
      v8[201] = 1;
      KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
    }
    *((_DWORD *)v8 + 58) = BytesRead;
    *((_DWORD *)v8 + 2) = v20;
    WimFSFReadWimCompletion(0, v8);
LABEL_30:
    if ( v20 < 0 )
      goto LABEL_36;
    goto LABEL_31;
  }
  v23 = *(_QWORD *)(v13 + 40);
  v24 = *(struct _FILE_OBJECT **)(v13 + 72);
  RetNewCallbackData = 0;
  v21 = 1;
  v20 = FltAllocateCallbackDataEx(*(PFLT_INSTANCE *)(v23 + 120), v24, 1u, &RetNewCallbackData);
  if ( v20 < 0 )
    goto LABEL_30;
  v20 = FltPropagateIrpExtension(*((_QWORD *)v8 + 3), RetNewCallbackData, 0);
  if ( v20 < 0 )
  {
    FltFreeCallbackData(RetNewCallbackData);
    goto LABEL_37;
  }
  v25 = RetNewCallbackData;
  v26 = a6;
  *((_QWORD *)v8 + 24) = a6;
  v8[200] = 1;
  v25->Iopb->MajorFunction = 3;
  RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = ByteOffset;
  RetNewCallbackData->Iopb->Parameters.Read.Length = v17;
  RetNewCallbackData->Iopb->Parameters.Create.Options = 0;
  RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = v26;
  RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = Buffer;
  WofTraceRedirectedFileIo(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 3) + 16LL) + 8LL), RetNewCallbackData);
  FltSetIoPriorityHintIntoCallbackData(RetNewCallbackData, *((IO_PRIORITY_HINT *)v8 + 32));
  v21 = 0;
  if ( KeAreAllApcsDisabled()
    || (*((_DWORD *)v8 + 36) & 1) != 0
    || FltIsOperationSynchronous(*((PFLT_CALLBACK_DATA *)v8 + 3)) )
  {
    RetNewCallbackData->Iopb->IrpFlags |= 0x143u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    if ( !v8[201] )
    {
      v8[201] = 1;
      KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
    }
    FltPerformSynchronousIo(RetNewCallbackData);
    WimFSFReadWimCompletion(RetNewCallbackData, v8);
  }
  else
  {
    v20 = 259;
    RetNewCallbackData->Iopb->IrpFlags |= 0x103u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    FltPerformAsynchronousIo(RetNewCallbackData, WimFSFReadWimCompletion, v8);
  }
LABEL_31:
  if ( v8[201] )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    KeWaitForSingleObject(v8 + 208, Executive, 0, 0, 0);
    v20 = *((_DWORD *)v8 + 2);
  }
LABEL_36:
  if ( v21 )
LABEL_37:
    WimFSFReleaseReadCompletionContext(v8);
LABEL_38:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14003ccf0  mov     [rsp-40h+RetNewCallbackData], r9
0x14003ccf5  mov     [rsp-40h+arg_10], r8b
0x14003ccfa  mov     [rsp-40h+arg_0], cl
0x14003ccfe  push    rbp
0x14003ccff  push    rbx
0x14003cd00  push    rsi
0x14003cd01  push    rdi
0x14003cd02  push    r12
0x14003cd04  push    r13
0x14003cd06  push    r14
0x14003cd08  push    r15
0x14003cd0a  mov     rbp, rsp
0x14003cd0d  sub     rsp, 68h
0x14003cd11  mov     rdi, [rbp+Context]
0x14003cd18  xor     eax, eax
0x14003cd1a  mov     rbx, r9
0x14003cd1d  movzx   r15d, cl
0x14003cd21  mov     r12b, dl
0x14003cd24  mov     [rbp+var_14], eax
0x14003cd27  mov     qword ptr [rbp+ByteOffset], rax
0x14003cd2b  mov     r13, [rdi+28h]
0x14003cd2f  mov     r14, [rdi+30h]
0x14003cd33  mov     dword ptr [rbp+NumberOfBytes], eax
0x14003cd36  mov     [rbp+var_18], eax
0x14003cd39  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd40  mov     eax, [rcx+2Ch]
0x14003cd43  test    al, 20h
0x14003cd45  jz      short loc_14003CD62
0x14003cd47  cmp     byte ptr [rcx+29h], 4
0x14003cd4b  jb      short loc_14003CD62
0x14003cd4d  mov     rcx, [rcx+18h]
0x14003cd51  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cd58  mov     edx, 31h ; '1'
0x14003cd5d  call    WPP_SF_
0x14003cd62  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd69  mov     esi, [rbp+arg_30]
0x14003cd6c  mov     eax, [rcx+2Ch]
0x14003cd6f  test    al, 20h
0x14003cd71  jz      short loc_14003CD97
0x14003cd73  cmp     byte ptr [rcx+29h], 5
0x14003cd77  jb      short loc_14003CD97
0x14003cd79  mov     rax, [rbp+arg_20]
0x14003cd7d  mov     r9, rbx
0x14003cd80  mov     rcx, [rcx+18h]
0x14003cd84  mov     dword ptr [rsp+68h+BytesRead], r15d
0x14003cd89  mov     [rsp+68h+Flags], esi
0x14003cd8d  mov     [rsp+68h+Buffer], rax
0x14003cd92  call    WPP_SF_iqDl
0x14003cd97  mov     dword ptr [rdi+74h], 0
0x14003cd9e  test    r12b, r12b
0x14003cda1  jnz     short loc_14003CDE7
0x14003cda3  test    r15b, r15b
0x14003cda6  jz      short loc_14003CDAE
0x14003cda8  mov     r9d, [r14+5Ch]
0x14003cdac  jmp     short loc_14003CDB4
0x14003cdae  mov     r9d, 1
0x14003cdb4  lea     rax, [rbp+var_18]
0x14003cdb8  mov     r8d, esi
0x14003cdbb  mov     [rsp+68h+BytesRead], rax
0x14003cdc0  lea     rdx, [rbp+RetNewCallbackData]
0x14003cdc4  lea     rax, [rbp+NumberOfBytes]
0x14003cdc8  mov     rcx, r14
0x14003cdcb  mov     qword ptr [rsp+68h+Flags], rax
0x14003cdd0  lea     rax, [rbp+ByteOffset]
0x14003cdd4  mov     [rsp+68h+Buffer], rax
0x14003cdd9  call    WimFSFGetAlignedSizesForIntegrity
0x14003cdde  mov     r12d, dword ptr [rbp+NumberOfBytes]
0x14003cde2  mov     [rbp+arg_10], al
0x14003cde5  jmp     short loc_14003CDEE
0x14003cde7  mov     qword ptr [rbp+ByteOffset], rbx
0x14003cdeb  mov     r12d, esi
0x14003cdee  cmp     qword ptr [rbp+ByteOffset], rbx
0x14003cdf2  jnz     short loc_14003CE02
0x14003cdf4  cmp     r12d, esi
0x14003cdf7  jnz     short loc_14003CE02
0x14003cdf9  mov     rbx, [rbp+arg_20]
0x14003cdfd  mov     r15, rbx
0x14003ce00  jmp     short loc_14003CE3D
0x14003ce02  mov     r8d, r12d; NumberOfBytes
0x14003ce05  mov     edx, 200h; PoolType
0x14003ce0a  mov     r9d, 44527077h; Tag
0x14003ce10  mov     [rbp+arg_28], 0
0x14003ce18  mov     rcx, r13; Instance
0x14003ce1b  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14003ce22  nop     dword ptr [rax+rax+00h]
0x14003ce27  mov     r15, rax
0x14003ce2a  test    rax, rax
0x14003ce2d  jnz     short loc_14003CE39
0x14003ce2f  mov     ebx, 0C000009Ah
0x14003ce34  jmp     loc_14003CFDE
0x14003ce39  mov     rbx, [rbp+arg_20]
0x14003ce3d  mov     eax, [rdi+90h]
0x14003ce43  lea     r13, [rdi+0D0h]
0x14003ce4a  test    al, 1
0x14003ce4c  jz      short loc_14003CE6D
0x14003ce4e  xor     r8d, r8d; State
0x14003ce51  mov     byte ptr [rdi+0C9h], 1
0x14003ce58  mov     rcx, r13; Event
0x14003ce5b  lea     edx, [r8+1]; Type
0x14003ce5f  call    cs:__imp_KeInitializeEvent
0x14003ce66  nop     dword ptr [rax+rax+00h]
0x14003ce6b  jmp     short loc_14003CE74
0x14003ce6d  mov     byte ptr [rdi+0C9h], 0
0x14003ce74  mov     al, [rbp+arg_10]
0x14003ce77  mov     rcx, rdi
0x14003ce7a  mov     [rdi+98h], al
0x14003ce80  mov     rax, qword ptr [rbp+ByteOffset]
0x14003ce84  mov     [rdi+0A0h], rax
0x14003ce8b  mov     eax, [rbp+var_18]
0x14003ce8e  mov     [rdi+0B8h], eax
0x14003ce94  mov     [rdi+9Ch], esi
0x14003ce9a  mov     [rdi+0A8h], r15
0x14003cea1  mov     [rdi+0B0h], rbx
0x14003cea8  call    WimFSFReferenceReadCompletionContext
0x14003cead  xor     ebx, ebx
0x14003ceaf  cmp     [rbp+arg_0], bl
0x14003ceb2  jnz     loc_14003D01E
0x14003ceb8  call    cs:__imp_KeAreAllApcsDisabled
0x14003cebf  nop     dword ptr [rax+rax+00h]
0x14003cec4  test    al, al
0x14003cec6  jnz     loc_14003D01E
0x14003cecc  mov     [rdi+0C8h], bl
0x14003ced2  mov     sil, bl
0x14003ced5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cedc  mov     eax, [rcx+2Ch]
0x14003cedf  test    al, 20h
0x14003cee1  jz      short loc_14003CEFC
0x14003cee3  cmp     byte ptr [rcx+29h], 5
0x14003cee7  jb      short loc_14003CEFC
0x14003cee9  mov     rcx, [rcx+18h]
0x14003ceed  lea     edx, [rbx+35h]
0x14003cef0  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cef7  call    WPP_SF_
0x14003cefc  mov     rcx, [r14+28h]
0x14003cf00  lea     rax, [rbp+var_14]
0x14003cf04  mov     rdx, [r14+48h]; FileObject
0x14003cf08  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14003cf0c  mov     [rsp+68h+CallbackContext], rbx; CallbackContext
0x14003cf11  mov     r9d, r12d; Length
0x14003cf14  mov     [rsp+68h+CallbackRoutine], rbx; CallbackRoutine
0x14003cf19  mov     rcx, [rcx+78h]; InitiatingInstance
0x14003cf1d  mov     [rsp+68h+BytesRead], rax; BytesRead
0x14003cf22  mov     [rsp+68h+Flags], 4; Flags
0x14003cf2a  mov     [rsp+68h+Buffer], r15; Buffer
0x14003cf2f  call    cs:__imp_FltReadFile
0x14003cf36  nop     dword ptr [rax+rax+00h]
0x14003cf3b  xor     r14d, r14d
0x14003cf3e  mov     ebx, eax
0x14003cf40  cmp     [rdi+0C9h], r14b
0x14003cf47  jnz     short loc_14003CF66
0x14003cf49  xor     r8d, r8d; State
0x14003cf4c  mov     byte ptr [rdi+0C9h], 1
0x14003cf53  lea     edx, [r14+1]; Type
0x14003cf57  mov     rcx, r13; Event
0x14003cf5a  call    cs:__imp_KeInitializeEvent
0x14003cf61  nop     dword ptr [rax+rax+00h]
0x14003cf66  mov     ecx, [rbp+var_14]
0x14003cf69  mov     rdx, rdi; Context
0x14003cf6c  mov     [rdi+0E8h], ecx
0x14003cf72  xor     ecx, ecx; CallbackData
0x14003cf74  mov     [rdi+8], ebx
0x14003cf77  call    WimFSFReadWimCompletion
0x14003cf7c  test    ebx, ebx
0x14003cf7e  js      short loc_14003CFD1
0x14003cf80  cmp     [rdi+0C9h], r14b
0x14003cf87  jz      short loc_14003CFD1
0x14003cf89  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf90  mov     eax, [rcx+2Ch]
0x14003cf93  test    al, 20h
0x14003cf95  jz      short loc_14003CFB2
0x14003cf97  cmp     byte ptr [rcx+29h], 5
0x14003cf9b  jb      short loc_14003CFB2
0x14003cf9d  mov     rcx, [rcx+18h]
0x14003cfa1  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cfa8  mov     edx, 36h ; '6'
0x14003cfad  call    WPP_SF_
0x14003cfb2  xor     r9d, r9d; Alertable
0x14003cfb5  mov     [rsp+68h+Buffer], r14; Timeout
0x14003cfba  xor     r8d, r8d; WaitMode
0x14003cfbd  xor     edx, edx; WaitReason
0x14003cfbf  mov     rcx, r13; Object
0x14003cfc2  call    cs:__imp_KeWaitForSingleObject
0x14003cfc9  nop     dword ptr [rax+rax+00h]
0x14003cfce  mov     ebx, [rdi+8]
0x14003cfd1  test    sil, sil
0x14003cfd4  jz      short loc_14003CFDE
0x14003cfd6  mov     rcx, rdi; Entry
0x14003cfd9  call    WimFSFReleaseReadCompletionContext
0x14003cfde  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfe5  mov     eax, [rcx+2Ch]
0x14003cfe8  test    al, 20h
0x14003cfea  jz      short loc_14003D00A
0x14003cfec  cmp     byte ptr [rcx+29h], 4
0x14003cff0  jb      short loc_14003D00A
0x14003cff2  mov     rcx, [rcx+18h]
0x14003cff6  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cffd  mov     edx, 37h ; '7'
0x14003d002  mov     r9d, ebx
0x14003d005  call    WPP_SF_d
0x14003d00a  mov     eax, ebx
0x14003d00c  add     rsp, 68h
0x14003d010  pop     r15
0x14003d012  pop     r14
0x14003d014  pop     r13
0x14003d016  pop     r12
0x14003d018  pop     rdi
0x14003d019  pop     rsi
0x14003d01a  pop     rbx
0x14003d01b  pop     rbp
0x14003d01c  retn
0x14003d01e  mov     rcx, [r14+28h]
0x14003d022  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14003d026  mov     rdx, [r14+48h]; FileObject
0x14003d02a  mov     r8d, 1; Flags
0x14003d030  mov     [rbp+RetNewCallbackData], rbx
0x14003d034  mov     sil, 1
0x14003d037  mov     rcx, [rcx+78h]; Instance
0x14003d03b  call    cs:__imp_FltAllocateCallbackDataEx
0x14003d042  nop     dword ptr [rax+rax+00h]
0x14003d047  xor     r14d, r14d
0x14003d04a  mov     ebx, eax
0x14003d04c  test    eax, eax
0x14003d04e  js      loc_14003CF7C
0x14003d054  mov     rdx, [rbp+RetNewCallbackData]
0x14003d058  xor     r8d, r8d
0x14003d05b  mov     rcx, [rdi+18h]
0x14003d05f  call    cs:__imp_FltPropagateIrpExtension
0x14003d066  nop     dword ptr [rax+rax+00h]
0x14003d06b  mov     ebx, eax
0x14003d06d  test    eax, eax
0x14003d06f  jns     short loc_14003D086
0x14003d071  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003d075  call    cs:__imp_FltFreeCallbackData
0x14003d07c  nop     dword ptr [rax+rax+00h]
0x14003d081  jmp     loc_14003CFD6
0x14003d086  mov     rax, [rbp+RetNewCallbackData]
0x14003d08a  mov     rdx, [rbp+arg_28]
0x14003d08e  mov     [rdi+0C0h], rdx
0x14003d095  mov     [rdi+0C8h], sil
0x14003d09c  mov     rcx, [rax+10h]
0x14003d0a0  mov     byte ptr [rcx+4], 3
0x14003d0a4  mov     rax, [rbp+RetNewCallbackData]
0x14003d0a8  mov     rcx, [rax+10h]
0x14003d0ac  mov     rax, qword ptr [rbp+ByteOffset]
0x14003d0b0  mov     [rcx+28h], rax
0x14003d0b4  mov     rax, [rbp+RetNewCallbackData]
0x14003d0b8  mov     rcx, [rax+10h]
0x14003d0bc  mov     [rcx+18h], r12d
0x14003d0c0  mov     rax, [rbp+RetNewCallbackData]
0x14003d0c4  mov     rcx, [rax+10h]
0x14003d0c8  mov     [rcx+20h], r14d
0x14003d0cc  mov     rax, [rbp+RetNewCallbackData]
0x14003d0d0  mov     rcx, [rax+10h]
0x14003d0d4  mov     [rcx+38h], rdx
0x14003d0d8  mov     rax, [rbp+RetNewCallbackData]
0x14003d0dc  mov     rcx, [rax+10h]
0x14003d0e0  mov     [rcx+30h], r15
0x14003d0e4  mov     rax, [rdi+18h]
0x14003d0e8  mov     rdx, [rbp+RetNewCallbackData]
0x14003d0ec  mov     rcx, [rax+10h]
0x14003d0f0  mov     rcx, [rcx+8]
0x14003d0f4  call    WofTraceRedirectedFileIo
0x14003d0f9  mov     edx, [rdi+80h]; PriorityHint
0x14003d0ff  mov     rcx, [rbp+RetNewCallbackData]; Data
0x14003d103  call    cs:__imp_FltSetIoPriorityHintIntoCallbackData
0x14003d10a  nop     dword ptr [rax+rax+00h]
0x14003d10f  mov     sil, r14b
0x14003d112  call    cs:__imp_KeAreAllApcsDisabled
0x14003d119  nop     dword ptr [rax+rax+00h]
0x14003d11e  test    al, al
0x14003d120  jnz     short loc_14003D197
0x14003d122  mov     eax, [rdi+90h]
0x14003d128  test    al, 1
0x14003d12a  jnz     short loc_14003D197
0x14003d12c  mov     rcx, [rdi+18h]; CallbackData
0x14003d130  call    cs:__imp_FltIsOperationSynchronous
0x14003d137  nop     dword ptr [rax+rax+00h]
0x14003d13c  test    al, al
0x14003d13e  jnz     short loc_14003D197
0x14003d140  mov     rax, [rbp+RetNewCallbackData]
0x14003d144  mov     ebx, 103h
0x14003d149  mov     rcx, [rax+10h]
0x14003d14d  or      [rcx], ebx
0x14003d14f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d156  mov     eax, [rcx+2Ch]
0x14003d159  test    al, 20h
0x14003d15b  jz      short loc_14003D178
0x14003d15d  cmp     byte ptr [rcx+29h], 5
0x14003d161  jb      short loc_14003D178
0x14003d163  mov     rcx, [rcx+18h]
0x14003d167  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003d16e  mov     edx, 34h ; '4'
0x14003d173  call    WPP_SF_
0x14003d178  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003d17c  lea     rdx, WimFSFReadWimCompletion; CallbackRoutine
0x14003d183  mov     r8, rdi; CallbackContext
0x14003d186  call    cs:__imp_FltPerformAsynchronousIo
0x14003d18d  nop     dword ptr [rax+rax+00h]
0x14003d192  jmp     loc_14003CF80
0x14003d197  mov     rax, [rbp+RetNewCallbackData]
  ... truncated ...
```
