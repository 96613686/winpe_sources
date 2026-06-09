# WcOpenReparsePoint

- ea: `0x14002d7e0`
- end: `0x14002da9e`
- name: `WcOpenReparsePoint`
- size: `702`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, void *, __int64, ACCESS_MASK DesiredAccess, ULONG CreateOptions, ULONG ShareAccess, PVOID **, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001939c`
- `0x14002cb38`
- `0x14002d648`

## callees

- `0x1400020c4`
- `0x14002d7e0`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14002d9bd`
- `ntoskrnl!IoGetSilo` at `0x14002d9bd`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002da7f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002da7f`
- `FLTMGR!FltCreateFileEx2` at `0x14002da61`
- `FLTMGR!FltCreateFileEx2` at `0x14002da61`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002d83f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002d83f`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002d97c`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002d97c`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002d8df`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002d8df`

## pseudocode

```c
__int64 __fastcall WcOpenReparsePoint(
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a2,
        void *a3,
        __int64 a4,
        ACCESS_MASK DesiredAccess,
        ULONG CreateOptions,
        ULONG ShareAccess,
        PVOID **a8,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject)
{
  NTSTATUS v14; // eax
  int v15; // edx
  unsigned int v16; // ebx
  int v17; // r9d
  NTSTATUS v18; // eax
  _QWORD *v19; // rax
  PVOID *v20; // rax
  PVOID *v21; // rdx
  _QWORD *v22; // rdx
  PVOID *v23; // r8
  char EcpContext; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  PVOID v27; // [rsp+80h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-70h] BYREF
  __int64 Silo; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF

  v27 = 0;
  EcpList = 0;
  LOWORD(Silo) = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v14 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  v16 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    AllocationSize = v14;
    v17 = 146;
    EcpContext = -46;
    goto LABEL_4;
  }
  v18 = FltAllocateExtraCreateParameterFromLookasideList(
          Globals,
          &ECP_TYPE_OPEN_REPARSE_GUID,
          0x10u,
          0,
          0,
          qword_14000E300,
          &v27);
  v16 = v18;
  if ( v18 >= 0 )
  {
    v19 = v27;
    *((_QWORD *)v27 + 1) = v27;
    *v19 = v19;
    while ( 1 )
    {
      v20 = *a8;
      if ( *a8 == (PVOID *)a8 )
        break;
      if ( v20[1] != a8
        || (v21 = (PVOID *)*v20, *((PVOID **)*v20 + 1) != v20)
        || (*a8 = v21, v21[1] = a8, v22 = v27, v23 = (PVOID *)*((_QWORD *)v27 + 1), *v23 != v27) )
      {
        __fastfail(3u);
      }
      *v20 = v27;
      v20[1] = v23;
      *v23 = v20;
      v22[1] = v20;
    }
    FltInsertExtraCreateParameter(Globals, EcpList, v27);
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    *(&DriverContext.Size + 3) = 0;
    DriverContext.Size = 40;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    DriverContext.ExtraCreateParameter = EcpList;
    Silo = 1;
    if ( a4 )
      Silo = IoGetSilo(a4);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a3;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = FltCreateFileEx2(
            Globals,
            Instance,
            FileHandle,
            FileObject,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            ShareAccess,
            1u,
            CreateOptions,
            0,
            0,
            0,
            &DriverContext);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    AllocationSize = v18;
    v17 = 147;
    EcpContext = -33;
LABEL_4:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v15,
      5,
      v17,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      EcpContext,
      AllocationSize);
  }
LABEL_18:
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  return v16;
}

```

## disassembly

```asm
0x14002d7e0  push    rbp
0x14002d7e2  push    rbx
0x14002d7e3  push    rsi
0x14002d7e4  push    rdi
0x14002d7e5  push    r14
0x14002d7e7  push    r15
0x14002d7e9  lea     rbp, [rsp-8]
0x14002d7ee  sub     rsp, 108h
0x14002d7f5  xorps   xmm0, xmm0
0x14002d7f8  mov     [rbp+30h+var_B0], 0
0x14002d800  mov     rsi, r8
0x14002d803  mov     [rbp+30h+EcpList], 0
0x14002d80b  mov     r14, rdx
0x14002d80e  lea     r8, [rbp+30h+EcpList]; EcpList
0x14002d812  mov     r15, rcx
0x14002d815  xor     eax, eax
0x14002d817  mov     rcx, cs:Globals; Filter
0x14002d81e  xor     edx, edx; Flags
0x14002d820  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14002d824  mov     rdi, r9
0x14002d827  mov     word ptr [rbp+30h+var_80], ax
0x14002d82b  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14002d82f  movups  xmmword ptr [rbp+30h+var_A0.Size], xmm0
0x14002d833  movups  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm0
0x14002d837  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14002d83b  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x14002d83f  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14002d846  nop     dword ptr [rax+rax+00h]
0x14002d84b  mov     ebx, eax
0x14002d84d  test    eax, eax
0x14002d84f  jns     short loc_14002D8AC
0x14002d851  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d858  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d85f  jz      loc_14002DA6F
0x14002d865  mov     dword ptr [rsp+130h+AllocationSize], eax
0x14002d869  mov     r9d, 92h
0x14002d86f  mov     dword ptr [rsp+130h+EcpContext], 14D2h
0x14002d877  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002d87e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002d885  mov     [rsp+130h+LookasideList], rax
0x14002d88a  mov     r8d, 5
0x14002d890  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002d897  mov     dl, 2
0x14002d899  mov     [rsp+130h+CleanupCallback], rax
0x14002d89e  mov     rcx, [rcx+40h]
0x14002d8a2  call    WPP_RECORDER_SF_sDd
0x14002d8a7  jmp     loc_14002DA6F
0x14002d8ac  mov     rcx, cs:Globals; Filter
0x14002d8b3  lea     rax, [rbp+30h+var_B0]
0x14002d8b7  mov     [rsp+130h+EcpContext], rax; EcpContext
0x14002d8bc  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14002d8c3  xor     r9d, r9d; Flags
0x14002d8c6  lea     rax, qword_14000E300
0x14002d8cd  mov     [rsp+130h+LookasideList], rax; LookasideList
0x14002d8d2  mov     [rsp+130h+CleanupCallback], 0; CleanupCallback
0x14002d8db  lea     r8d, [r9+10h]; SizeOfContext
0x14002d8df  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14002d8e6  nop     dword ptr [rax+rax+00h]
0x14002d8eb  mov     ebx, eax
0x14002d8ed  test    eax, eax
0x14002d8ef  jns     short loc_14002D91C
0x14002d8f1  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d8f8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d8ff  jz      loc_14002DA6F
0x14002d905  mov     dword ptr [rsp+130h+AllocationSize], eax
0x14002d909  mov     r9d, 93h
0x14002d90f  mov     dword ptr [rsp+130h+EcpContext], 14DFh
0x14002d917  jmp     loc_14002D877
0x14002d91c  mov     rax, [rbp+30h+var_B0]
0x14002d920  mov     rcx, [rbp+30h+arg_38]
0x14002d924  mov     [rax+8], rax
0x14002d928  mov     [rax], rax
0x14002d92b  mov     rax, [rcx]
0x14002d92e  cmp     rax, rcx
0x14002d931  jz      short loc_14002D96D
0x14002d933  cmp     [rax+8], rcx
0x14002d937  jnz     short loc_14002D966
0x14002d939  mov     rdx, [rax]
0x14002d93c  cmp     [rdx+8], rax
0x14002d940  jnz     short loc_14002D966
0x14002d942  mov     [rcx], rdx
0x14002d945  mov     [rdx+8], rcx
0x14002d949  mov     rdx, [rbp+30h+var_B0]
0x14002d94d  mov     r8, [rdx+8]
0x14002d951  cmp     [r8], rdx
0x14002d954  jnz     short loc_14002D966
0x14002d956  mov     [rax], rdx
0x14002d959  mov     [rax+8], r8
0x14002d95d  mov     [r8], rax
0x14002d960  mov     [rdx+8], rax
0x14002d964  jmp     short loc_14002D92B
0x14002d966  mov     ecx, 3
0x14002d96b  int     29h; Win8: RtlFailFast(ecx)
0x14002d96d  mov     r8, [rbp+30h+var_B0]; EcpContext
0x14002d971  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14002d975  mov     rcx, cs:Globals; Filter
0x14002d97c  call    cs:__imp_FltInsertExtraCreateParameter
0x14002d983  nop     dword ptr [rax+rax+00h]
0x14002d988  xor     eax, eax
0x14002d98a  mov     dword ptr [rbp+30h+var_A0+2], 0
0x14002d991  mov     word ptr [rbp+30h+var_A0+6], ax
0x14002d995  mov     eax, 28h ; '('
0x14002d99a  mov     [rbp+30h+var_A0.Size], ax
0x14002d99e  xorps   xmm0, xmm0
0x14002d9a1  movdqu  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm0
0x14002d9a6  lea     ebx, [rax-27h]
0x14002d9a9  mov     rax, [rbp+30h+EcpList]
0x14002d9ad  mov     [rbp+30h+var_A0.ExtraCreateParameter], rax
0x14002d9b1  mov     [rbp+30h+var_80], rbx
0x14002d9b5  test    rdi, rdi
0x14002d9b8  jz      short loc_14002D9CD
0x14002d9ba  mov     rcx, rdi
0x14002d9bd  call    cs:__imp_IoGetSilo
0x14002d9c4  nop     dword ptr [rax+rax+00h]
0x14002d9c9  mov     [rbp+30h+var_80], rax
0x14002d9cd  mov     r9, [rbp+30h+FileObject]; FileObject
0x14002d9d4  lea     rax, [rbp+30h+var_A0]
0x14002d9d8  mov     r8, [rbp+30h+FileHandle]; FileHandle
0x14002d9df  xorps   xmm0, xmm0
0x14002d9e2  mov     rcx, cs:Globals; Filter
0x14002d9e9  mov     rdx, r15; Instance
0x14002d9ec  mov     [rsp+130h+DriverContext], rax; DriverContext
0x14002d9f1  mov     eax, [rbp+30h+arg_28]
0x14002d9f4  mov     [rsp+130h+Flags], 0; Flags
0x14002d9fc  mov     [rsp+130h+EaLength], 0; EaLength
0x14002da04  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x14002da0d  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14002da11  mov     eax, [rbp+30h+arg_30]
0x14002da14  mov     [rsp+130h+CreateDisposition], ebx; CreateDisposition
0x14002da18  mov     [rsp+130h+ShareAccess], eax; ShareAccess
0x14002da1c  lea     rax, [rbp+30h+IoStatusBlock]
0x14002da20  mov     [rsp+130h+FileAttributes], 0; FileAttributes
0x14002da28  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x14002da31  mov     [rsp+130h+EcpContext], rax; IoStatusBlock
0x14002da36  lea     rax, [rbp+30h+ObjectAttributes]
0x14002da3a  mov     [rsp+130h+LookasideList], rax; ObjectAttributes
0x14002da3f  mov     eax, [rbp+30h+DesiredAccess]
0x14002da42  mov     dword ptr [rsp+130h+CleanupCallback], eax; DesiredAccess
0x14002da46  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14002da4d  mov     [rbp+30h+ObjectAttributes.RootDirectory], rsi
0x14002da51  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x14002da58  mov     [rbp+30h+ObjectAttributes.ObjectName], r14
0x14002da5c  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002da61  call    cs:__imp_FltCreateFileEx2
0x14002da68  nop     dword ptr [rax+rax+00h]
0x14002da6d  mov     ebx, eax
0x14002da6f  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14002da73  test    rdx, rdx
0x14002da76  jz      short loc_14002DA8B
0x14002da78  mov     rcx, cs:Globals; Filter
0x14002da7f  call    cs:__imp_FltFreeExtraCreateParameterList
0x14002da86  nop     dword ptr [rax+rax+00h]
0x14002da8b  mov     eax, ebx
0x14002da8d  add     rsp, 108h
0x14002da94  pop     r15
0x14002da96  pop     r14
0x14002da98  pop     rdi
0x14002da99  pop     rsi
0x14002da9a  pop     rbx
0x14002da9b  pop     rbp
0x14002da9c  retn
```
