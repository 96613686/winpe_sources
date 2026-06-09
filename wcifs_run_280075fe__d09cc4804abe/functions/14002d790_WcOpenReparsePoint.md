# WcOpenReparsePoint

- ea: `0x14002d790`
- end: `0x14002da4e`
- name: `WcOpenReparsePoint`
- size: `702`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, ACCESS_MASK DesiredAccess, ULONG, ULONG, __int64, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001939c`
- `0x14002cae8`
- `0x14002d5f8`

## callees

- `0x1400020c4`
- `0x14002d790`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14002d96d`
- `ntoskrnl!IoGetSilo` at `0x14002d96d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002da2f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002da2f`
- `FLTMGR!FltCreateFileEx2` at `0x14002da11`
- `FLTMGR!FltCreateFileEx2` at `0x14002da11`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002d7ef`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002d7ef`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002d92c`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002d92c`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002d88f`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002d88f`

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
      WPP_GLOBAL_Control->DeviceExtension,
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
0x14002d790  push    rbp
0x14002d792  push    rbx
0x14002d793  push    rsi
0x14002d794  push    rdi
0x14002d795  push    r14
0x14002d797  push    r15
0x14002d799  lea     rbp, [rsp-8]
0x14002d79e  sub     rsp, 108h
0x14002d7a5  xorps   xmm0, xmm0
0x14002d7a8  mov     [rbp+30h+var_B0], 0
0x14002d7b0  mov     rsi, r8
0x14002d7b3  mov     [rbp+30h+EcpList], 0
0x14002d7bb  mov     r14, rdx
0x14002d7be  lea     r8, [rbp+30h+EcpList]; EcpList
0x14002d7c2  mov     r15, rcx
0x14002d7c5  xor     eax, eax
0x14002d7c7  mov     rcx, cs:Globals; Filter
0x14002d7ce  xor     edx, edx; Flags
0x14002d7d0  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14002d7d4  mov     rdi, r9
0x14002d7d7  mov     word ptr [rbp+30h+var_80], ax
0x14002d7db  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14002d7df  movups  xmmword ptr [rbp+30h+var_A0.Size], xmm0
0x14002d7e3  movups  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm0
0x14002d7e7  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14002d7eb  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x14002d7ef  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14002d7f6  nop     dword ptr [rax+rax+00h]
0x14002d7fb  mov     ebx, eax
0x14002d7fd  test    eax, eax
0x14002d7ff  jns     short loc_14002D85C
0x14002d801  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d808  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d80f  jz      loc_14002DA1F
0x14002d815  mov     dword ptr [rsp+130h+AllocationSize], eax
0x14002d819  mov     r9d, 92h
0x14002d81f  mov     dword ptr [rsp+130h+EcpContext], 14D2h
0x14002d827  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d82e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002d835  mov     [rsp+130h+LookasideList], rax
0x14002d83a  mov     r8d, 5
0x14002d840  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002d847  mov     dl, 2
0x14002d849  mov     [rsp+130h+CleanupCallback], rax
0x14002d84e  mov     rcx, [rcx+40h]
0x14002d852  call    WPP_RECORDER_SF_sDd
0x14002d857  jmp     loc_14002DA1F
0x14002d85c  mov     rcx, cs:Globals; Filter
0x14002d863  lea     rax, [rbp+30h+var_B0]
0x14002d867  mov     [rsp+130h+EcpContext], rax; EcpContext
0x14002d86c  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14002d873  xor     r9d, r9d; Flags
0x14002d876  lea     rax, qword_14000E300
0x14002d87d  mov     [rsp+130h+LookasideList], rax; LookasideList
0x14002d882  mov     [rsp+130h+CleanupCallback], 0; CleanupCallback
0x14002d88b  lea     r8d, [r9+10h]; SizeOfContext
0x14002d88f  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14002d896  nop     dword ptr [rax+rax+00h]
0x14002d89b  mov     ebx, eax
0x14002d89d  test    eax, eax
0x14002d89f  jns     short loc_14002D8CC
0x14002d8a1  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d8a8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d8af  jz      loc_14002DA1F
0x14002d8b5  mov     dword ptr [rsp+130h+AllocationSize], eax
0x14002d8b9  mov     r9d, 93h
0x14002d8bf  mov     dword ptr [rsp+130h+EcpContext], 14DFh
0x14002d8c7  jmp     loc_14002D827
0x14002d8cc  mov     rax, [rbp+30h+var_B0]
0x14002d8d0  mov     rcx, [rbp+30h+arg_38]
0x14002d8d4  mov     [rax+8], rax
0x14002d8d8  mov     [rax], rax
0x14002d8db  mov     rax, [rcx]
0x14002d8de  cmp     rax, rcx
0x14002d8e1  jz      short loc_14002D91D
0x14002d8e3  cmp     [rax+8], rcx
0x14002d8e7  jnz     short loc_14002D916
0x14002d8e9  mov     rdx, [rax]
0x14002d8ec  cmp     [rdx+8], rax
0x14002d8f0  jnz     short loc_14002D916
0x14002d8f2  mov     [rcx], rdx
0x14002d8f5  mov     [rdx+8], rcx
0x14002d8f9  mov     rdx, [rbp+30h+var_B0]
0x14002d8fd  mov     r8, [rdx+8]
0x14002d901  cmp     [r8], rdx
0x14002d904  jnz     short loc_14002D916
0x14002d906  mov     [rax], rdx
0x14002d909  mov     [rax+8], r8
0x14002d90d  mov     [r8], rax
0x14002d910  mov     [rdx+8], rax
0x14002d914  jmp     short loc_14002D8DB
0x14002d916  mov     ecx, 3
0x14002d91b  int     29h; Win8: RtlFailFast(ecx)
0x14002d91d  mov     r8, [rbp+30h+var_B0]; EcpContext
0x14002d921  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14002d925  mov     rcx, cs:Globals; Filter
0x14002d92c  call    cs:__imp_FltInsertExtraCreateParameter
0x14002d933  nop     dword ptr [rax+rax+00h]
0x14002d938  xor     eax, eax
0x14002d93a  mov     dword ptr [rbp+30h+var_A0+2], 0
0x14002d941  mov     word ptr [rbp+30h+var_A0+6], ax
0x14002d945  mov     eax, 28h ; '('
0x14002d94a  mov     [rbp+30h+var_A0.Size], ax
0x14002d94e  xorps   xmm0, xmm0
0x14002d951  movdqu  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm0
0x14002d956  lea     ebx, [rax-27h]
0x14002d959  mov     rax, [rbp+30h+EcpList]
0x14002d95d  mov     [rbp+30h+var_A0.ExtraCreateParameter], rax
0x14002d961  mov     [rbp+30h+var_80], rbx
0x14002d965  test    rdi, rdi
0x14002d968  jz      short loc_14002D97D
0x14002d96a  mov     rcx, rdi
0x14002d96d  call    cs:__imp_IoGetSilo
0x14002d974  nop     dword ptr [rax+rax+00h]
0x14002d979  mov     [rbp+30h+var_80], rax
0x14002d97d  mov     r9, [rbp+30h+FileObject]; FileObject
0x14002d984  lea     rax, [rbp+30h+var_A0]
0x14002d988  mov     r8, [rbp+30h+FileHandle]; FileHandle
0x14002d98f  xorps   xmm0, xmm0
0x14002d992  mov     rcx, cs:Globals; Filter
0x14002d999  mov     rdx, r15; Instance
0x14002d99c  mov     [rsp+130h+DriverContext], rax; DriverContext
0x14002d9a1  mov     eax, [rbp+30h+arg_28]
0x14002d9a4  mov     [rsp+130h+Flags], 0; Flags
0x14002d9ac  mov     [rsp+130h+EaLength], 0; EaLength
0x14002d9b4  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x14002d9bd  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14002d9c1  mov     eax, [rbp+30h+arg_30]
0x14002d9c4  mov     [rsp+130h+CreateDisposition], ebx; CreateDisposition
0x14002d9c8  mov     [rsp+130h+ShareAccess], eax; ShareAccess
0x14002d9cc  lea     rax, [rbp+30h+IoStatusBlock]
0x14002d9d0  mov     [rsp+130h+FileAttributes], 0; FileAttributes
0x14002d9d8  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x14002d9e1  mov     [rsp+130h+EcpContext], rax; IoStatusBlock
0x14002d9e6  lea     rax, [rbp+30h+ObjectAttributes]
0x14002d9ea  mov     [rsp+130h+LookasideList], rax; ObjectAttributes
0x14002d9ef  mov     eax, [rbp+30h+DesiredAccess]
0x14002d9f2  mov     dword ptr [rsp+130h+CleanupCallback], eax; DesiredAccess
0x14002d9f6  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14002d9fd  mov     [rbp+30h+ObjectAttributes.RootDirectory], rsi
0x14002da01  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x14002da08  mov     [rbp+30h+ObjectAttributes.ObjectName], r14
0x14002da0c  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002da11  call    cs:__imp_FltCreateFileEx2
0x14002da18  nop     dword ptr [rax+rax+00h]
0x14002da1d  mov     ebx, eax
0x14002da1f  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14002da23  test    rdx, rdx
0x14002da26  jz      short loc_14002DA3B
0x14002da28  mov     rcx, cs:Globals; Filter
0x14002da2f  call    cs:__imp_FltFreeExtraCreateParameterList
0x14002da36  nop     dword ptr [rax+rax+00h]
0x14002da3b  mov     eax, ebx
0x14002da3d  add     rsp, 108h
0x14002da44  pop     r15
0x14002da46  pop     r14
0x14002da48  pop     rdi
0x14002da49  pop     rsi
0x14002da4a  pop     rbx
0x14002da4b  pop     rbp
0x14002da4c  retn
```
