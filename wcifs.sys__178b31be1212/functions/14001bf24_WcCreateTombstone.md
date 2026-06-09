# WcCreateTombstone

- ea: `0x14001bf24`
- end: `0x14001c23d`
- name: `WcCreateTombstone`
- size: `793`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001c688`
- `0x140031940`
- `0x140032550`
- `0x140032928`
- `0x140033fe0`

## callees

- `0x1400020c4`
- `0x1400080c0`
- `0x14001bf24`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x14001c0fd`
- `ntoskrnl!PsGetHostSilo` at `0x14001c0fd`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c21e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c21e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001c1f4`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001c1f4`
- `FLTMGR!FltCreateFileEx2` at `0x14001c1a6`
- `FLTMGR!FltCreateFileEx2` at `0x14001c1a6`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001bf9a`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001bf9a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001c0d7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001c0d7`
- `FLTMGR!FltClose` at `0x14001c209`
- `FLTMGR!FltClose` at `0x14001c209`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001c1ce`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001c1ce`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001c03e`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001c03e`

## pseudocode

```c
__int64 __fastcall WcCreateTombstone(PFLT_INSTANCE Instance, struct _UNICODE_STRING *a2, char a3)
{
  ULONG CreateOptions; // esi
  NTSTATUS v6; // ebx
  PECP_LIST EcpList; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-68h] BYREF
  __int64 HostSilo; // [rsp+B8h] [rbp-48h]
  __int128 v13; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v14; // [rsp+D0h] [rbp-30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+178h] [rbp+78h] BYREF

  EcpList = 0;
  EcpContext = 0;
  v14 = 0;
  LOWORD(HostSilo) = 0;
  FileHandle = 0;
  FileObject = 0;
  CreateOptions = (a3 != 0) + 2162728;
  v13 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v6 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  if ( v6 >= 0 )
  {
    v6 = FltAllocateExtraCreateParameterFromLookasideList(
           Globals,
           &GUID_ECP_ATOMIC_CREATE,
           0x58u,
           0,
           0,
           qword_14000E280,
           &EcpContext);
    if ( v6 >= 0 )
    {
      WORD2(v13) = 0;
      LODWORD(v13) = -1610612705;
      memset(EcpContext, 0, 0x58u);
      *(_WORD *)EcpContext = 88;
      *((_WORD *)EcpContext + 1) = 2;
      *((_WORD *)EcpContext + 2) = 0;
      *((_WORD *)EcpContext + 3) = 8;
      *((_QWORD *)EcpContext + 1) = &v13;
      FltInsertExtraCreateParameter(Globals, EcpList, EcpContext);
      HostSilo = 1;
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      HostSilo = PsGetHostSilo();
      DriverContext.ExtraCreateParameter = EcpList;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = a2;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = FltCreateFileEx2(
             Globals,
             Instance,
             &FileHandle,
             &FileObject,
             0x40000000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             6u,
             0,
             2u,
             CreateOptions,
             0,
             0,
             0,
             &DriverContext);
      if ( v6 == -1073741771 )
      {
        v6 = 0;
      }
      else if ( v6 >= 0 && !FltIsEcpAcknowledged(Globals, EcpContext) )
      {
        v6 = -1073741823;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        2,
        19,
        15,
        (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
        3,
        v6);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      2,
      19,
      14,
      (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
      246,
      v6);
  }
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001bf24  push    rbp
0x14001bf26  push    rbx
0x14001bf27  push    rsi
0x14001bf28  push    rdi
0x14001bf29  push    r14
0x14001bf2b  push    r15
0x14001bf2d  lea     rbp, [rsp-28h]
0x14001bf32  sub     rsp, 128h
0x14001bf39  xorps   xmm0, xmm0
0x14001bf3c  mov     [rbp+50h+EcpList], 0
0x14001bf44  xor     eax, eax
0x14001bf46  mov     [rbp+50h+arg_18], 0
0x14001bf4e  neg     r8b
0x14001bf51  mov     [rbp+50h+var_80], rax
0x14001bf55  mov     r14, rdx
0x14001bf58  mov     word ptr [rbp+50h+var_98], ax
0x14001bf5c  sbb     esi, esi
0x14001bf5e  mov     [rbp+50h+FileHandle], rax
0x14001bf62  mov     r15, rcx
0x14001bf65  mov     [rbp+50h+FileObject], rax
0x14001bf69  mov     rcx, cs:Globals; Filter
0x14001bf70  lea     r8, [rbp+50h+EcpList]; EcpList
0x14001bf74  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14001bf78  neg     esi
0x14001bf7a  xor     edx, edx; Flags
0x14001bf7c  add     esi, 210028h
0x14001bf82  movups  [rbp+50h+var_90], xmm0
0x14001bf86  movups  xmmword ptr [rbp+50h+var_B8.Size], xmm0
0x14001bf8a  movups  xmmword ptr [rbp+50h+var_B8.DeviceObjectHint], xmm0
0x14001bf8e  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14001bf92  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14001bf96  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14001bf9a  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14001bfa1  nop     dword ptr [rax+rax+00h]
0x14001bfa6  mov     ebx, eax
0x14001bfa8  test    eax, eax
0x14001bfaa  jns     short loc_14001C008
0x14001bfac  lea     rax, WPP_RECORDER_INITIALIZED
0x14001bfb3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001bfba  jz      loc_14001C1E4
0x14001bfc0  mov     dword ptr [rsp+150h+AllocationSize], ebx
0x14001bfc4  mov     r9d, 0Eh
0x14001bfca  mov     dword ptr [rsp+150h+EcpContext], 1F6h
0x14001bfd2  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001bfd9  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x14001bfe0  mov     [rsp+150h+LookasideList], rax
0x14001bfe5  mov     edx, 2
0x14001bfea  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x14001bff1  mov     [rsp+150h+CleanupCallback], rax
0x14001bff6  mov     rcx, [rcx+40h]
0x14001bffa  lea     r8d, [rdx+11h]
0x14001bffe  call    WPP_RECORDER_SF_sDd
0x14001c003  jmp     loc_14001C1E4
0x14001c008  mov     rcx, cs:Globals; Filter
0x14001c00f  lea     rax, [rbp+50h+arg_18]
0x14001c013  mov     [rsp+150h+EcpContext], rax; EcpContext
0x14001c018  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x14001c01f  xor     r9d, r9d; Flags
0x14001c022  lea     rax, qword_14000E280
0x14001c029  mov     [rsp+150h+LookasideList], rax; LookasideList
0x14001c02e  mov     [rsp+150h+CleanupCallback], 0; CleanupCallback
0x14001c037  lea     edi, [r9+58h]
0x14001c03b  mov     r8d, edi; SizeOfContext
0x14001c03e  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14001c045  nop     dword ptr [rax+rax+00h]
0x14001c04a  mov     ebx, eax
0x14001c04c  test    eax, eax
0x14001c04e  jns     short loc_14001C079
0x14001c050  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c057  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c05e  jz      loc_14001C1E4
0x14001c064  mov     dword ptr [rsp+150h+AllocationSize], ebx
0x14001c068  lea     r9d, [rdi-49h]
0x14001c06c  mov     dword ptr [rsp+150h+EcpContext], 203h
0x14001c074  jmp     loc_14001BFD2
0x14001c079  mov     rcx, [rbp+50h+arg_18]; void *
0x14001c07d  xor     eax, eax
0x14001c07f  mov     r8, rdi; Size
0x14001c082  mov     word ptr [rbp+50h+var_90+4], ax
0x14001c086  xor     edx, edx; Val
0x14001c088  mov     dword ptr [rbp+50h+var_90], 0A000001Fh
0x14001c08f  call    memset
0x14001c094  mov     rax, [rbp+50h+arg_18]
0x14001c098  xor     ecx, ecx
0x14001c09a  mov     [rax], di
0x14001c09d  mov     edi, 2
0x14001c0a2  mov     rax, [rbp+50h+arg_18]
0x14001c0a6  mov     [rax+2], di
0x14001c0aa  mov     rax, [rbp+50h+arg_18]
0x14001c0ae  mov     [rax+4], cx
0x14001c0b2  lea     rcx, [rbp+50h+var_90]
0x14001c0b6  mov     rax, [rbp+50h+arg_18]
0x14001c0ba  mov     word ptr [rax+6], 8
0x14001c0c0  mov     rax, [rbp+50h+arg_18]
0x14001c0c4  mov     [rax+8], rcx
0x14001c0c8  mov     r8, [rbp+50h+arg_18]; EcpContext
0x14001c0cc  mov     rdx, [rbp+50h+EcpList]; EcpList
0x14001c0d0  mov     rcx, cs:Globals; Filter
0x14001c0d7  call    cs:__imp_FltInsertExtraCreateParameter
0x14001c0de  nop     dword ptr [rax+rax+00h]
0x14001c0e3  xorps   xmm0, xmm0
0x14001c0e6  mov     [rbp+50h+var_98], 1
0x14001c0ee  lea     eax, [rdi+26h]
0x14001c0f1  movups  xmmword ptr [rbp+50h+var_B8.Size], xmm0
0x14001c0f5  mov     [rbp+50h+var_B8.Size], ax
0x14001c0f9  movups  xmmword ptr [rbp+50h+var_B8.DeviceObjectHint], xmm0
0x14001c0fd  call    cs:__imp_PsGetHostSilo
0x14001c104  nop     dword ptr [rax+rax+00h]
0x14001c109  mov     rcx, cs:Globals; Filter
0x14001c110  lea     r9, [rbp+50h+FileObject]; FileObject
0x14001c114  mov     [rbp+50h+var_98], rax
0x14001c118  lea     r8, [rbp+50h+FileHandle]; FileHandle
0x14001c11c  mov     rax, [rbp+50h+EcpList]
0x14001c120  xorps   xmm0, xmm0
0x14001c123  mov     [rbp+50h+var_B8.ExtraCreateParameter], rax
0x14001c127  mov     rdx, r15; Instance
0x14001c12a  lea     rax, [rbp+50h+var_B8]
0x14001c12e  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14001c135  mov     [rsp+150h+DriverContext], rax; DriverContext
0x14001c13a  lea     rax, [rbp+50h+IoStatusBlock]
0x14001c13e  mov     [rsp+150h+Flags], 0; Flags
0x14001c146  mov     [rsp+150h+EaLength], 0; EaLength
0x14001c14e  mov     [rsp+150h+EaBuffer], 0; EaBuffer
0x14001c157  mov     [rsp+150h+CreateOptions], esi; CreateOptions
0x14001c15b  mov     [rsp+150h+CreateDisposition], edi; CreateDisposition
0x14001c15f  mov     [rsp+150h+ShareAccess], 0; ShareAccess
0x14001c167  mov     [rsp+150h+FileAttributes], 6; FileAttributes
0x14001c16f  mov     [rsp+150h+AllocationSize], 0; AllocationSize
0x14001c178  mov     [rsp+150h+EcpContext], rax; IoStatusBlock
0x14001c17d  lea     rax, [rbp+50h+ObjectAttributes]
0x14001c181  mov     [rsp+150h+LookasideList], rax; ObjectAttributes
0x14001c186  mov     dword ptr [rsp+150h+CleanupCallback], 40000000h; DesiredAccess
0x14001c18e  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x14001c196  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14001c19d  mov     [rbp+50h+ObjectAttributes.ObjectName], r14
0x14001c1a1  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001c1a6  call    cs:__imp_FltCreateFileEx2
0x14001c1ad  nop     dword ptr [rax+rax+00h]
0x14001c1b2  mov     ebx, eax
0x14001c1b4  cmp     eax, 0C0000035h
0x14001c1b9  jnz     short loc_14001C1BF
0x14001c1bb  xor     ebx, ebx
0x14001c1bd  jmp     short loc_14001C1E4
0x14001c1bf  test    ebx, ebx
0x14001c1c1  js      short loc_14001C1E4
0x14001c1c3  mov     rdx, [rbp+50h+arg_18]; EcpContext
0x14001c1c7  mov     rcx, cs:Globals; Filter
0x14001c1ce  call    cs:__imp_FltIsEcpAcknowledged
0x14001c1d5  nop     dword ptr [rax+rax+00h]
0x14001c1da  test    al, al
0x14001c1dc  mov     ecx, 0C0000001h
0x14001c1e1  cmovz   ebx, ecx
0x14001c1e4  mov     rdx, [rbp+50h+EcpList]; EcpList
0x14001c1e8  test    rdx, rdx
0x14001c1eb  jz      short loc_14001C200
0x14001c1ed  mov     rcx, cs:Globals; Filter
0x14001c1f4  call    cs:__imp_FltFreeExtraCreateParameterList
0x14001c1fb  nop     dword ptr [rax+rax+00h]
0x14001c200  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x14001c204  test    rcx, rcx
0x14001c207  jz      short loc_14001C215
0x14001c209  call    cs:__imp_FltClose
0x14001c210  nop     dword ptr [rax+rax+00h]
0x14001c215  mov     rcx, [rbp+50h+FileObject]; Object
0x14001c219  test    rcx, rcx
0x14001c21c  jz      short loc_14001C22A
0x14001c21e  call    cs:__imp_ObfDereferenceObject
0x14001c225  nop     dword ptr [rax+rax+00h]
0x14001c22a  mov     eax, ebx
0x14001c22c  add     rsp, 128h
0x14001c233  pop     r15
0x14001c235  pop     r14
0x14001c237  pop     rdi
0x14001c238  pop     rsi
0x14001c239  pop     rbx
0x14001c23a  pop     rbp
0x14001c23b  retn
```
