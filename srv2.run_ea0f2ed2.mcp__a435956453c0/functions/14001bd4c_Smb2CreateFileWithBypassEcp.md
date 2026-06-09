# Smb2CreateFileWithBypassEcp

- ea: `0x14001bd4c`
- end: `0x14001bea6`
- name: `Smb2CreateFileWithBypassEcp`
- size: `346`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, PECP_LIST EcpList, int, ULONG, int, ULONG, int, int, int, int, int, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000f060`
- `0x140077678`
- `0x140081de0`

## callees

- `0x14001bd4c`
- `0x1400224b8`
- `0x140094e44`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001be83`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001be83`
- `ntoskrnl!IoCreateFileEx` at `0x14001be6d`
- `ntoskrnl!IoCreateFileEx` at `0x14001be6d`

## pseudocode

```c
__int64 __fastcall Smb2CreateFileWithBypassEcp(
        PHANDLE FileHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        PECP_LIST EcpList,
        int a6,
        ULONG ShareAccess,
        int a8,
        ULONG CreateOptions,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        struct _ECP_LIST *a15)
{
  char v19; // si
  int v20; // eax
  unsigned int v21; // ebx
  struct _ECP_LIST *v22; // rdi
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+80h] [rbp-31h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-11h]

  LOWORD(v25) = 0;
  EcpList = 0;
  v19 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( a15 )
  {
    EcpList = a15;
    v19 = 0;
  }
  v20 = Smb2CreateRkfBypassEcp(&EcpList);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v22 = EcpList;
    DriverContext.Size = 40;
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    *(&DriverContext.Size + 3) = 0;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    v25 = 1;
    DriverContext.ExtraCreateParameter = EcpList;
    v21 = IoCreateFileEx(
            FileHandle,
            DesiredAccess,
            ObjectAttributes,
            IoStatusBlock,
            0,
            0,
            ShareAccess,
            1u,
            CreateOptions,
            0,
            0,
            CreateFileTypeNone,
            0,
            0,
            &DriverContext);
    if ( v19 )
      FsRtlFreeExtraCreateParameterList(v22);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      85,
      &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
      (unsigned int)v20);
  }
  return v21;
}

```

## disassembly

```asm
0x14001bd4c  push    rbp
0x14001bd4e  push    rbx
0x14001bd4f  push    rsi
0x14001bd50  push    rdi
0x14001bd51  push    r12
0x14001bd53  push    r13
0x14001bd55  push    r14
0x14001bd57  push    r15
0x14001bd59  lea     rbp, [rsp-7]
0x14001bd5e  sub     rsp, 0B8h
0x14001bd65  xor     eax, eax
0x14001bd67  xorps   xmm0, xmm0
0x14001bd6a  mov     word ptr [rbp+3Fh+var_50], ax
0x14001bd6e  mov     r14, r9
0x14001bd71  mov     [rbp+3Fh+EcpList], rax
0x14001bd75  mov     r15, r8
0x14001bd78  mov     rax, [rbp+3Fh+arg_70]
0x14001bd7f  mov     r12d, edx
0x14001bd82  mov     r13, rcx
0x14001bd85  mov     sil, 1
0x14001bd88  movups  xmmword ptr [rbp+3Fh+var_70.Size], xmm0
0x14001bd8c  movups  xmmword ptr [rbp+3Fh+var_70.DeviceObjectHint], xmm0
0x14001bd90  test    rax, rax
0x14001bd93  jz      short loc_14001BD9C
0x14001bd95  mov     [rbp+3Fh+EcpList], rax
0x14001bd99  xor     sil, sil
0x14001bd9c  lea     rcx, [rbp+3Fh+EcpList]
0x14001bda0  call    Smb2CreateRkfBypassEcp
0x14001bda5  xor     ecx, ecx
0x14001bda7  mov     ebx, eax
0x14001bda9  test    eax, eax
0x14001bdab  jns     short loc_14001BDF8
0x14001bdad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001bdb4  lea     rax, WPP_GLOBAL_Control
0x14001bdbb  cmp     rcx, rax
0x14001bdbe  jz      loc_14001BE8F
0x14001bdc4  test    dword ptr [rcx+2Ch], 100000h
0x14001bdcb  jz      loc_14001BE8F
0x14001bdd1  cmp     byte ptr [rcx+29h], 1
0x14001bdd5  jb      loc_14001BE8F
0x14001bddb  mov     rcx, [rcx+18h]
0x14001bddf  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14001bde6  mov     edx, 55h ; 'U'
0x14001bdeb  mov     r9d, ebx
0x14001bdee  call    WPP_SF_d
0x14001bdf3  jmp     loc_14001BE8F
0x14001bdf8  mov     rdi, [rbp+3Fh+EcpList]
0x14001bdfc  mov     eax, 28h ; '('
0x14001be01  mov     [rbp+3Fh+var_70.Size], ax
0x14001be05  xorps   xmm0, xmm0
0x14001be08  lea     rax, [rbp+3Fh+var_70]
0x14001be0c  mov     dword ptr [rbp+3Fh+var_70+2], ecx
0x14001be0f  mov     [rsp+0F0h+DriverContext], rax; DriverContext
0x14001be14  mov     r9, r14; IoStatusBlock
0x14001be17  mov     eax, [rbp+3Fh+arg_40]
0x14001be1d  mov     r8, r15; ObjectAttributes
0x14001be20  mov     [rsp+0F0h+Options], ecx; Options
0x14001be24  mov     edx, r12d; DesiredAccess
0x14001be27  mov     [rsp+0F0h+InternalParameters], rcx; InternalParameters
0x14001be2c  mov     [rsp+0F0h+CreateFileType], ecx; CreateFileType
0x14001be30  mov     [rsp+0F0h+EaLength], ecx; EaLength
0x14001be34  mov     [rsp+0F0h+EaBuffer], rcx; EaBuffer
0x14001be39  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x14001be3d  mov     eax, [rbp+3Fh+arg_30]
0x14001be40  mov     [rsp+0F0h+Disposition], 1; Disposition
0x14001be48  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x14001be4c  mov     [rsp+0F0h+FileAttributes], ecx; FileAttributes
0x14001be50  mov     [rsp+0F0h+AllocationSize], rcx; AllocationSize
0x14001be55  mov     word ptr [rbp+3Fh+var_70+6], cx
0x14001be59  mov     rcx, r13; FileHandle
0x14001be5c  movdqu  xmmword ptr [rbp+3Fh+var_70.DeviceObjectHint], xmm0
0x14001be61  mov     [rbp+3Fh+var_50], 1
0x14001be69  mov     [rbp+3Fh+var_70.ExtraCreateParameter], rdi
0x14001be6d  call    cs:__imp_IoCreateFileEx
0x14001be74  nop     dword ptr [rax+rax+00h]
0x14001be79  mov     ebx, eax
0x14001be7b  test    sil, sil
0x14001be7e  jz      short loc_14001BE8F
0x14001be80  mov     rcx, rdi; EcpList
0x14001be83  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14001be8a  nop     dword ptr [rax+rax+00h]
0x14001be8f  mov     eax, ebx
0x14001be91  add     rsp, 0B8h
0x14001be98  pop     r15
0x14001be9a  pop     r14
0x14001be9c  pop     r13
0x14001be9e  pop     r12
0x14001bea0  pop     rdi
0x14001bea1  pop     rsi
0x14001bea2  pop     rbx
0x14001bea3  pop     rbp
0x14001bea4  retn
```
