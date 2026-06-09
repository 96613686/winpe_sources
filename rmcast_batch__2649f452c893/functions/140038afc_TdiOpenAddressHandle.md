# TdiOpenAddressHandle

- ea: `0x140038afc`
- end: `0x14003907f`
- name: `TdiOpenAddressHandle`
- size: `1411`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, void **, struct _FILE_OBJECT **, PDEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001a50`

## callees

- `0x140005068`
- `0x140005524`
- `0x14000a580`
- `0x14001bcec`
- `0x14001c4c8`
- `0x14001cdf0`
- `0x14001d000`
- `0x140038afc`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140038d11`
- `ntoskrnl!KeStackAttachProcess` at `0x140038d11`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140039003`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140039003`
- `ntoskrnl!ZwCreateFile` at `0x140038db7`
- `ntoskrnl!ZwCreateFile` at `0x140038db7`
- `ntoskrnl!ZwClose` at `0x140038e78`
- `ntoskrnl!ZwClose` at `0x140038e78`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038ed2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038ed2`
- `ntoskrnl!ObfDereferenceObject` at `0x14003906e`
- `ntoskrnl!ObfDereferenceObject` at `0x14003906e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038e2e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038e2e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140038cf1`
- `ntoskrnl!PsGetCurrentProcess` at `0x140038cf1`
- `ntoskrnl!ExAllocatePool2` at `0x140038bbc`
- `ntoskrnl!ExAllocatePool2` at `0x140038c1e`
- `ntoskrnl!ExAllocatePool2` at `0x140038bbc`
- `ntoskrnl!ExAllocatePool2` at `0x140038c1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ddb`

## pseudocode

```c
__int64 __fastcall TdiOpenAddressHandle(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        struct _FILE_OBJECT **a6,
        PDEVICE_OBJECT *a7)
{
  __int64 v7; // r15
  char v9; // r12
  _DWORD *EaBuffer; // r14
  _QWORD *Pool2; // rdi
  struct _UNICODE_STRING *v13; // r15
  NTSTATUS Status; // ebx
  struct _FILE_OBJECT *v15; // r14
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  PDEVICE_OBJECT v17; // r15
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  void *FileHandle; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE Object[14]; // [rsp+68h] [rbp-D0h] BYREF
  int v22; // [rsp+78h] [rbp-C0h] BYREF
  void **v23; // [rsp+80h] [rbp-B8h]
  struct _FILE_OBJECT **v24; // [rsp+88h] [rbp-B0h]
  PDEVICE_OBJECT *v25; // [rsp+90h] [rbp-A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-70h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-60h] BYREF

  v7 = pgPgmDevice;
  v23 = a5;
  v24 = a6;
  v25 = a7;
  v9 = 1;
  *(_QWORD *)&Object[6] = 0;
  FileHandle = 0;
  v22 = 1;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  EaBuffer = (_DWORD *)ExAllocatePool2(64, 54, 829253456);
  if ( !EaBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, 54);
    return 3221225626LL;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 26, 846030672);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, 26);
    ExFreePoolWithTag(EaBuffer, 0);
    return 3221225626LL;
  }
  *EaBuffer = 0;
  EaBuffer[1] = 1642496;
  memmove(EaBuffer + 2, "TransportAddress", 0x11u);
  *(_DWORD *)&Object[2] = 0;
  *(_WORD *)Object = 28928;
  *(_QWORD *)&Object[6] = 0;
  Pool2[1] = 28928;
  *((_DWORD *)Pool2 + 4) = 0;
  *((_WORD *)Pool2 + 10) = *(_WORD *)&Object[12];
  *((_DWORD *)Pool2 + 1) = 131086;
  *(_DWORD *)Pool2 = 1;
  memmove((char *)EaBuffer + *((unsigned __int8 *)EaBuffer + 5) + 9, Pool2, 0x19u);
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
    v9 = 0;
  else
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = (struct _UNICODE_STRING *)(v7 + 24);
  ObjectAttributes.ObjectName = v13;
  Status = ZwCreateFile(
             &FileHandle,
             0xC0100000,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x80u,
             0,
             3u,
             0,
             EaBuffer,
             *((unsigned __int16 *)EaBuffer + 3) + 12 + *((unsigned __int8 *)EaBuffer + 5));
  ExFreePoolWithTag(Pool2, 0);
  ExFreePoolWithTag(EaBuffer, 0);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v15 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DZ(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        (unsigned int)WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
        Status,
        (__int64)v13);
    if ( Status < 0 )
      goto LABEL_41;
  }
  else
  {
    *(_QWORD *)Object = 0;
    Status = ObReferenceObjectByHandle(FileHandle, 0, 0, 0, (PVOID *)Object, 0);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
          (unsigned int)Status);
      goto LABEL_20;
    }
    v15 = *(struct _FILE_OBJECT **)Object;
  }
  RelatedDeviceObject = IoGetRelatedDeviceObject(v15);
  v17 = RelatedDeviceObject;
  if ( !a2 )
    goto LABEL_38;
  Status = TdiSetEventHandler(RelatedDeviceObject, v15, 2, TdiErrorHandler, a2);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
        (unsigned int)Status);
    goto LABEL_47;
  }
  Status = TdiSetEventHandler(v17, v15, 4, TdiRcvDatagramHandler, a2);
  if ( Status < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_47;
    v19 = 19;
    goto LABEL_36;
  }
  Status = PgmSetTcpInfo(FileHandle, 27, &v22, 4);
  if ( Status >= 0 )
  {
LABEL_38:
    *v23 = FileHandle;
    *v24 = v15;
    *v25 = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids);
    goto LABEL_41;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
    goto LABEL_47;
  v19 = 18;
LABEL_36:
  WPP_SF_d(v18->AttachedDevice, v19, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, (unsigned int)Status);
LABEL_47:
  ObfDereferenceObject(v15);
LABEL_20:
  ZwClose(FileHandle);
LABEL_41:
  if ( v9 )
    KeUnstackDetachProcess(&ApcState);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140038afc  mov     r11, rsp
0x140038aff  mov     [r11+8], rbx
0x140038b03  mov     [r11+18h], rsi
0x140038b07  push    rdi
0x140038b08  push    r12
0x140038b0a  push    r13
0x140038b0c  push    r14
0x140038b0e  push    r15
0x140038b10  sub     rsp, 110h
0x140038b17  mov     rax, cs:__security_cookie
0x140038b1e  xor     rax, rsp
0x140038b21  mov     [rsp+138h+var_30], rax
0x140038b29  mov     rax, [rsp+138h+arg_20]
0x140038b31  xor     esi, esi
0x140038b33  mov     r15, cs:pgPgmDevice
0x140038b3a  xorps   xmm0, xmm0
0x140038b3d  mov     [rsp+138h+var_B8], rax
0x140038b45  xorps   xmm1, xmm1
0x140038b48  mov     rax, [rsp+138h+arg_28]
0x140038b50  mov     r13, rdx
0x140038b53  mov     [rsp+138h+var_B0], rax
0x140038b5b  lea     ebx, [rsi+36h]
0x140038b5e  mov     rax, [rsp+138h+arg_30]
0x140038b66  lea     edi, [rsi+40h]
0x140038b69  mov     [rsp+138h+var_A8], rax
0x140038b71  lea     r12d, [rsi+1]
0x140038b75  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x140038b7d  xor     eax, eax
0x140038b7f  mov     [rsp+138h+Object+6], rsi
0x140038b84  mov     r8d, 316D6750h
0x140038b8a  mov     [rsp+138h+FileHandle], rsi
0x140038b8f  mov     edx, ebx
0x140038b91  mov     [rsp+138h+var_C0], r12d
0x140038b96  mov     ecx, edi
0x140038b98  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x140038ba0  movups  xmmword ptr [rsp+138h+ObjectAttributes+1Ch], xmm0
0x140038ba8  movups  xmmword ptr [r11-70h], xmm0
0x140038bad  movups  xmmword ptr [r11-60h], xmm1
0x140038bb2  movups  xmmword ptr [r11-50h], xmm1
0x140038bb7  movups  xmmword ptr [r11-40h], xmm1
0x140038bbc  call    cs:__imp_ExAllocatePool2
0x140038bc3  nop     dword ptr [rax+rax+00h]
0x140038bc8  mov     r14, rax
0x140038bcb  test    rax, rax
0x140038bce  jnz     short loc_140038C0E
0x140038bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140038bd7  lea     rdi, WPP_GLOBAL_Control
0x140038bde  cmp     rcx, rdi
0x140038be1  jz      short loc_140038C04
0x140038be3  mov     eax, [rcx+2Ch]
0x140038be6  lea     esi, [rbx-34h]
0x140038be9  test    sil, al
0x140038bec  jz      short loc_140038C04
0x140038bee  mov     rcx, [rcx+18h]
0x140038bf2  lea     edx, [rbx-28h]
0x140038bf5  mov     r9d, ebx
0x140038bf8  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038bff  call    WPP_SF_d
0x140038c04  mov     eax, 0C000009Ah
0x140038c09  jmp     loc_140039011
0x140038c0e  mov     ebx, 1Ah
0x140038c13  mov     r8d, 326D6750h
0x140038c19  mov     edx, ebx
0x140038c1b  mov     rcx, rdi
0x140038c1e  call    cs:__imp_ExAllocatePool2
0x140038c25  nop     dword ptr [rax+rax+00h]
0x140038c2a  mov     rdi, rax
0x140038c2d  test    rax, rax
0x140038c30  jnz     short loc_140038C79
0x140038c32  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c39  lea     rdi, WPP_GLOBAL_Control
0x140038c40  cmp     rcx, rdi
0x140038c43  jz      short loc_140038C66
0x140038c45  mov     eax, [rcx+2Ch]
0x140038c48  lea     esi, [rbx-18h]
0x140038c4b  test    sil, al
0x140038c4e  jz      short loc_140038C66
0x140038c50  mov     rcx, [rcx+18h]
0x140038c54  lea     edx, [rbx-0Bh]
0x140038c57  mov     r9d, ebx
0x140038c5a  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038c61  call    WPP_SF_d
0x140038c66  xor     edx, edx; Tag
0x140038c68  mov     rcx, r14; P
0x140038c6b  call    cs:__imp_ExFreePoolWithTag
0x140038c72  nop     dword ptr [rax+rax+00h]
0x140038c77  jmp     short loc_140038C04
0x140038c79  mov     ebx, 19h
0x140038c7e  mov     [r14], esi
0x140038c81  lea     rcx, [r14+8]; void *
0x140038c85  mov     dword ptr [r14+4], 191000h
0x140038c8d  lea     rdx, aTransportaddre; "TransportAddress"
0x140038c94  lea     r8d, [rbx-8]; Size
0x140038c98  call    memmove
0x140038c9d  mov     eax, 7100h
0x140038ca2  mov     dword ptr [rsp+138h+Object+2], esi
0x140038ca6  mov     word ptr [rsp+138h+Object], ax
0x140038cab  lea     esi, [rbx-17h]
0x140038cae  xor     eax, eax
0x140038cb0  mov     r8d, ebx; Size
0x140038cb3  mov     [rsp+138h+Object+6], rax
0x140038cb8  mov     rdx, rdi; Src
0x140038cbb  mov     eax, [rsp+138h+var_C8]
0x140038cbf  movsd   xmm0, [rsp+138h+Object]
0x140038cc5  movsd   qword ptr [rdi+8], xmm0
0x140038cca  mov     [rdi+10h], eax
0x140038ccd  movzx   eax, [rsp+138h+var_C4]
0x140038cd2  mov     [rdi+14h], ax
0x140038cd6  mov     dword ptr [rdi+4], 2000Eh
0x140038cdd  mov     [rdi], r12d
0x140038ce0  movzx   ecx, byte ptr [r14+5]
0x140038ce5  add     rcx, 9
0x140038ce9  add     rcx, r14; void *
0x140038cec  call    memmove
0x140038cf1  call    cs:__imp_PsGetCurrentProcess
0x140038cf8  nop     dword ptr [rax+rax+00h]
0x140038cfd  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140038d04  cmp     rax, rcx
0x140038d07  jz      short loc_140038D1F
0x140038d09  lea     rdx, [rsp+138h+ApcState]; ApcState
0x140038d11  call    cs:__imp_KeStackAttachProcess
0x140038d18  nop     dword ptr [rax+rax+00h]
0x140038d1d  jmp     short loc_140038D22
0x140038d1f  xor     r12b, r12b
0x140038d22  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x140038d2d  lea     r9, [rsp+138h+IoStatusBlock]; IoStatusBlock
0x140038d35  mov     [rsp+138h+ObjectAttributes.RootDirectory], 0
0x140038d41  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x140038d49  mov     [rsp+138h+ObjectAttributes.Attributes], 240h
0x140038d54  xorps   xmm0, xmm0
0x140038d57  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x140038d60  add     r15, 18h
0x140038d64  mov     edx, 0C0100000h; DesiredAccess
0x140038d69  mov     [rsp+138h+ObjectAttributes.ObjectName], r15
0x140038d71  movzx   ecx, byte ptr [r14+5]
0x140038d76  movzx   eax, word ptr [r14+6]
0x140038d7b  add     eax, 0Ch
0x140038d7e  add     ecx, eax
0x140038d80  mov     [rsp+138h+EaLength], ecx; EaLength
0x140038d84  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x140038d89  mov     [rsp+138h+EaBuffer], r14; EaBuffer
0x140038d8e  mov     [rsp+138h+CreateOptions], 0; CreateOptions
0x140038d96  mov     [rsp+138h+CreateDisposition], 3; CreateDisposition
0x140038d9e  mov     [rsp+138h+ShareAccess], 0; ShareAccess
0x140038da6  mov     [rsp+138h+FileAttributes], 80h; FileAttributes
0x140038dae  mov     [rsp+138h+AllocationSize], 0; AllocationSize
0x140038db7  call    cs:__imp_ZwCreateFile
0x140038dbe  nop     dword ptr [rax+rax+00h]
0x140038dc3  xor     edx, edx; Tag
0x140038dc5  mov     rcx, rdi; P
0x140038dc8  mov     ebx, eax
0x140038dca  call    cs:__imp_ExFreePoolWithTag
0x140038dd1  nop     dword ptr [rax+rax+00h]
0x140038dd6  xor     edx, edx; Tag
0x140038dd8  mov     rcx, r14; P
0x140038ddb  call    cs:__imp_ExFreePoolWithTag
0x140038de2  nop     dword ptr [rax+rax+00h]
0x140038de7  lea     rdi, WPP_GLOBAL_Control
0x140038dee  test    ebx, ebx
0x140038df0  js      loc_140038E90
0x140038df6  mov     ebx, dword ptr [rsp+138h+IoStatusBlock]
0x140038dfd  test    ebx, ebx
0x140038dff  js      loc_140038E90
0x140038e05  mov     rcx, [rsp+138h+FileHandle]; Handle
0x140038e0a  lea     rax, [rsp+138h+Object]
0x140038e0f  mov     qword ptr [rsp+138h+FileAttributes], 0; HandleInformation
0x140038e18  xor     r9d, r9d; AccessMode
0x140038e1b  xor     r8d, r8d; ObjectType
0x140038e1e  mov     [rsp+138h+AllocationSize], rax; Object
0x140038e23  xor     edx, edx; DesiredAccess
0x140038e25  mov     [rsp+138h+Object], 0
0x140038e2e  call    cs:__imp_ObReferenceObjectByHandle
0x140038e35  nop     dword ptr [rax+rax+00h]
0x140038e3a  mov     ebx, eax
0x140038e3c  test    eax, eax
0x140038e3e  jns     short loc_140038E89
0x140038e40  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e47  lea     rdi, WPP_GLOBAL_Control
0x140038e4e  cmp     rcx, rdi
0x140038e51  jz      short loc_140038E73
0x140038e53  mov     eax, [rcx+2Ch]
0x140038e56  test    sil, al
0x140038e59  jz      short loc_140038E73
0x140038e5b  mov     rcx, [rcx+18h]
0x140038e5f  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038e66  mov     edx, 10h
0x140038e6b  mov     r9d, ebx
0x140038e6e  call    WPP_SF_d
0x140038e73  mov     rcx, [rsp+138h+FileHandle]; Handle
0x140038e78  call    cs:__imp_ZwClose
0x140038e7f  nop     dword ptr [rax+rax+00h]
0x140038e84  jmp     loc_140038FF6
0x140038e89  mov     r14, [rsp+138h+Object]
0x140038e8e  jmp     short loc_140038ECF
0x140038e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e97  cmp     rcx, rdi
0x140038e9a  jz      loc_140038FF6
0x140038ea0  mov     eax, [rcx+2Ch]
0x140038ea3  xor     r14d, r14d
0x140038ea6  test    sil, al
0x140038ea9  jz      short loc_140038EC7
0x140038eab  mov     rcx, [rcx+18h]
0x140038eaf  lea     edx, [r14+11h]
0x140038eb3  mov     r9d, ebx
0x140038eb6  mov     [rsp+138h+AllocationSize], r15
0x140038ebb  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038ec2  call    WPP_SF_DZ
0x140038ec7  test    ebx, ebx
0x140038ec9  js      loc_140038FF6
0x140038ecf  mov     rcx, r14; FileObject
0x140038ed2  call    cs:__imp_IoGetRelatedDeviceObject
0x140038ed9  nop     dword ptr [rax+rax+00h]
0x140038ede  mov     r15, rax
0x140038ee1  test    r13, r13
0x140038ee4  jz      loc_140038F9E
0x140038eea  lea     r9, TdiErrorHandler
0x140038ef1  mov     [rsp+138h+AllocationSize], r13
0x140038ef6  mov     r8d, esi
0x140038ef9  mov     rdx, r14
0x140038efc  mov     rcx, rax
0x140038eff  call    TdiSetEventHandler
0x140038f04  mov     ebx, eax
0x140038f06  test    eax, eax
0x140038f08  js      loc_14003903F
0x140038f0e  mov     [rsp+138h+AllocationSize], r13
0x140038f13  lea     r9, TdiRcvDatagramHandler
0x140038f1a  mov     r13d, 4
0x140038f20  mov     rdx, r14
0x140038f23  mov     r8d, r13d
0x140038f26  mov     rcx, r15
0x140038f29  call    TdiSetEventHandler
0x140038f2e  mov     ebx, eax
0x140038f30  test    eax, eax
0x140038f32  js      short loc_140038F6A
0x140038f34  mov     rcx, [rsp+138h+FileHandle]
0x140038f39  lea     r8, [rsp+138h+var_C0]
0x140038f3e  mov     r9d, r13d
0x140038f41  lea     edx, [r13+17h]
0x140038f45  call    PgmSetTcpInfo
0x140038f4a  mov     ebx, eax
0x140038f4c  test    eax, eax
0x140038f4e  jns     short loc_140038F9E
0x140038f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f57  cmp     rcx, rdi
0x140038f5a  jz      short loc_140038F96
0x140038f5c  mov     eax, [rcx+2Ch]
0x140038f5f  test    sil, al
0x140038f62  jz      short loc_140038F96
0x140038f64  lea     edx, [r13+0Eh]
0x140038f68  jmp     short loc_140038F83
0x140038f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f71  cmp     rcx, rdi
0x140038f74  jz      short loc_140038F96
0x140038f76  mov     eax, [rcx+2Ch]
0x140038f79  test    sil, al
0x140038f7c  jz      short loc_140038F96
0x140038f7e  mov     edx, 13h
0x140038f83  mov     rcx, [rcx+18h]
0x140038f87  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038f8e  mov     r9d, ebx
0x140038f91  call    WPP_SF_d
0x140038f96  test    ebx, ebx
0x140038f98  js      loc_14003906B
0x140038f9e  mov     rax, [rsp+138h+var_B8]
0x140038fa6  mov     r9, [rsp+138h+FileHandle]
0x140038fab  mov     [rax], r9
0x140038fae  mov     rax, [rsp+138h+var_B0]
0x140038fb6  mov     [rax], r14
0x140038fb9  mov     rax, [rsp+138h+var_A8]
0x140038fc1  mov     [rax], r15
0x140038fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140038fcb  cmp     rcx, rdi
0x140038fce  jz      short loc_140038FF6
0x140038fd0  mov     eax, [rcx+2Ch]
0x140038fd3  test    al, 10h
0x140038fd5  jz      short loc_140038FF6
0x140038fd7  mov     rcx, [rcx+18h]
0x140038fdb  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038fe2  mov     edx, 15h
0x140038fe7  mov     qword ptr [rsp+138h+FileAttributes], r15
0x140038fec  mov     [rsp+138h+AllocationSize], r14
0x140038ff1  call    WPP_SF_qqq
0x140038ff6  test    r12b, r12b
0x140038ff9  jz      short loc_14003900F
0x140038ffb  lea     rcx, [rsp+138h+ApcState]; ApcState
0x140039003  call    cs:__imp_KeUnstackDetachProcess
0x14003900a  nop     dword ptr [rax+rax+00h]
0x14003900f  mov     eax, ebx
0x140039011  mov     rcx, [rsp+138h+var_30]
0x140039019  xor     rcx, rsp; StackCookie
0x14003901c  call    __security_check_cookie
0x140039021  lea     r11, [rsp+138h+var_28]
0x140039029  mov     rbx, [r11+30h]
0x14003902d  mov     rsi, [r11+40h]
0x140039031  mov     rsp, r11
0x140039034  pop     r15
0x140039036  pop     r14
0x140039038  pop     r13
0x14003903a  pop     r12
0x14003903c  pop     rdi
  ... truncated ...
```
