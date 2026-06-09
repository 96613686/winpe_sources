# TdiOpenAddressHandle

- ea: `0x140038b4c`
- end: `0x1400390cf`
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
- `0x140038b4c`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140038d61`
- `ntoskrnl!KeStackAttachProcess` at `0x140038d61`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140039053`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140039053`
- `ntoskrnl!ZwCreateFile` at `0x140038e07`
- `ntoskrnl!ZwCreateFile` at `0x140038e07`
- `ntoskrnl!ZwClose` at `0x140038ec8`
- `ntoskrnl!ZwClose` at `0x140038ec8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038f22`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038f22`
- `ntoskrnl!ObfDereferenceObject` at `0x1400390be`
- `ntoskrnl!ObfDereferenceObject` at `0x1400390be`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038e7e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038e7e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140038d41`
- `ntoskrnl!PsGetCurrentProcess` at `0x140038d41`
- `ntoskrnl!ExAllocatePool2` at `0x140038c0c`
- `ntoskrnl!ExAllocatePool2` at `0x140038c6e`
- `ntoskrnl!ExAllocatePool2` at `0x140038c0c`
- `ntoskrnl!ExAllocatePool2` at `0x140038c6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e2b`

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
  void *v20; // r9
  void *FileHandle; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE Object[14]; // [rsp+68h] [rbp-D0h] BYREF
  int v23; // [rsp+78h] [rbp-C0h] BYREF
  void **v24; // [rsp+80h] [rbp-B8h]
  struct _FILE_OBJECT **v25; // [rsp+88h] [rbp-B0h]
  PDEVICE_OBJECT *v26; // [rsp+90h] [rbp-A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-70h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-60h] BYREF

  v7 = pgPgmDevice;
  v24 = a5;
  v25 = a6;
  v26 = a7;
  v9 = 1;
  *(_QWORD *)&Object[6] = 0;
  FileHandle = 0;
  v23 = 1;
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
  Status = PgmSetTcpInfo(FileHandle, 27, &v23);
  if ( Status >= 0 )
  {
LABEL_38:
    v20 = FileHandle;
    *v24 = FileHandle;
    *v25 = v15;
    *v26 = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, v20, v15, v17);
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
0x140038b4c  mov     r11, rsp
0x140038b4f  mov     [r11+8], rbx
0x140038b53  mov     [r11+18h], rsi
0x140038b57  push    rdi
0x140038b58  push    r12
0x140038b5a  push    r13
0x140038b5c  push    r14
0x140038b5e  push    r15
0x140038b60  sub     rsp, 110h
0x140038b67  mov     rax, cs:__security_cookie
0x140038b6e  xor     rax, rsp
0x140038b71  mov     [rsp+138h+var_30], rax
0x140038b79  mov     rax, [rsp+138h+arg_20]
0x140038b81  xor     esi, esi
0x140038b83  mov     r15, cs:pgPgmDevice
0x140038b8a  xorps   xmm0, xmm0
0x140038b8d  mov     [rsp+138h+var_B8], rax
0x140038b95  xorps   xmm1, xmm1
0x140038b98  mov     rax, [rsp+138h+arg_28]
0x140038ba0  mov     r13, rdx
0x140038ba3  mov     [rsp+138h+var_B0], rax
0x140038bab  lea     ebx, [rsi+36h]
0x140038bae  mov     rax, [rsp+138h+arg_30]
0x140038bb6  lea     edi, [rsi+40h]
0x140038bb9  mov     [rsp+138h+var_A8], rax
0x140038bc1  lea     r12d, [rsi+1]
0x140038bc5  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x140038bcd  xor     eax, eax
0x140038bcf  mov     [rsp+138h+Object+6], rsi
0x140038bd4  mov     r8d, 316D6750h
0x140038bda  mov     [rsp+138h+FileHandle], rsi
0x140038bdf  mov     edx, ebx
0x140038be1  mov     [rsp+138h+var_C0], r12d
0x140038be6  mov     ecx, edi
0x140038be8  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x140038bf0  movups  xmmword ptr [rsp+138h+ObjectAttributes+1Ch], xmm0
0x140038bf8  movups  xmmword ptr [r11-70h], xmm0
0x140038bfd  movups  xmmword ptr [r11-60h], xmm1
0x140038c02  movups  xmmword ptr [r11-50h], xmm1
0x140038c07  movups  xmmword ptr [r11-40h], xmm1
0x140038c0c  call    cs:__imp_ExAllocatePool2
0x140038c13  nop     dword ptr [rax+rax+00h]
0x140038c18  mov     r14, rax
0x140038c1b  test    rax, rax
0x140038c1e  jnz     short loc_140038C5E
0x140038c20  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c27  lea     rdi, WPP_GLOBAL_Control
0x140038c2e  cmp     rcx, rdi
0x140038c31  jz      short loc_140038C54
0x140038c33  mov     eax, [rcx+2Ch]
0x140038c36  lea     esi, [rbx-34h]
0x140038c39  test    sil, al
0x140038c3c  jz      short loc_140038C54
0x140038c3e  mov     rcx, [rcx+18h]
0x140038c42  lea     edx, [rbx-28h]
0x140038c45  mov     r9d, ebx
0x140038c48  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038c4f  call    WPP_SF_d
0x140038c54  mov     eax, 0C000009Ah
0x140038c59  jmp     loc_140039061
0x140038c5e  mov     ebx, 1Ah
0x140038c63  mov     r8d, 326D6750h
0x140038c69  mov     edx, ebx
0x140038c6b  mov     rcx, rdi
0x140038c6e  call    cs:__imp_ExAllocatePool2
0x140038c75  nop     dword ptr [rax+rax+00h]
0x140038c7a  mov     rdi, rax
0x140038c7d  test    rax, rax
0x140038c80  jnz     short loc_140038CC9
0x140038c82  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c89  lea     rdi, WPP_GLOBAL_Control
0x140038c90  cmp     rcx, rdi
0x140038c93  jz      short loc_140038CB6
0x140038c95  mov     eax, [rcx+2Ch]
0x140038c98  lea     esi, [rbx-18h]
0x140038c9b  test    sil, al
0x140038c9e  jz      short loc_140038CB6
0x140038ca0  mov     rcx, [rcx+18h]
0x140038ca4  lea     edx, [rbx-0Bh]
0x140038ca7  mov     r9d, ebx
0x140038caa  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038cb1  call    WPP_SF_d
0x140038cb6  xor     edx, edx; Tag
0x140038cb8  mov     rcx, r14; P
0x140038cbb  call    cs:__imp_ExFreePoolWithTag
0x140038cc2  nop     dword ptr [rax+rax+00h]
0x140038cc7  jmp     short loc_140038C54
0x140038cc9  mov     ebx, 19h
0x140038cce  mov     [r14], esi
0x140038cd1  lea     rcx, [r14+8]; void *
0x140038cd5  mov     dword ptr [r14+4], 191000h
0x140038cdd  lea     rdx, aTransportaddre; "TransportAddress"
0x140038ce4  lea     r8d, [rbx-8]; Size
0x140038ce8  call    memmove
0x140038ced  mov     eax, 7100h
0x140038cf2  mov     dword ptr [rsp+138h+Object+2], esi
0x140038cf6  mov     word ptr [rsp+138h+Object], ax
0x140038cfb  lea     esi, [rbx-17h]
0x140038cfe  xor     eax, eax
0x140038d00  mov     r8d, ebx; Size
0x140038d03  mov     [rsp+138h+Object+6], rax
0x140038d08  mov     rdx, rdi; Src
0x140038d0b  mov     eax, [rsp+138h+var_C8]
0x140038d0f  movsd   xmm0, [rsp+138h+Object]
0x140038d15  movsd   qword ptr [rdi+8], xmm0
0x140038d1a  mov     [rdi+10h], eax
0x140038d1d  movzx   eax, [rsp+138h+var_C4]
0x140038d22  mov     [rdi+14h], ax
0x140038d26  mov     dword ptr [rdi+4], 2000Eh
0x140038d2d  mov     [rdi], r12d
0x140038d30  movzx   ecx, byte ptr [r14+5]
0x140038d35  add     rcx, 9
0x140038d39  add     rcx, r14; void *
0x140038d3c  call    memmove
0x140038d41  call    cs:__imp_PsGetCurrentProcess
0x140038d48  nop     dword ptr [rax+rax+00h]
0x140038d4d  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140038d54  cmp     rax, rcx
0x140038d57  jz      short loc_140038D6F
0x140038d59  lea     rdx, [rsp+138h+ApcState]; ApcState
0x140038d61  call    cs:__imp_KeStackAttachProcess
0x140038d68  nop     dword ptr [rax+rax+00h]
0x140038d6d  jmp     short loc_140038D72
0x140038d6f  xor     r12b, r12b
0x140038d72  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x140038d7d  lea     r9, [rsp+138h+IoStatusBlock]; IoStatusBlock
0x140038d85  mov     [rsp+138h+ObjectAttributes.RootDirectory], 0
0x140038d91  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x140038d99  mov     [rsp+138h+ObjectAttributes.Attributes], 240h
0x140038da4  xorps   xmm0, xmm0
0x140038da7  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x140038db0  add     r15, 18h
0x140038db4  mov     edx, 0C0100000h; DesiredAccess
0x140038db9  mov     [rsp+138h+ObjectAttributes.ObjectName], r15
0x140038dc1  movzx   ecx, byte ptr [r14+5]
0x140038dc6  movzx   eax, word ptr [r14+6]
0x140038dcb  add     eax, 0Ch
0x140038dce  add     ecx, eax
0x140038dd0  mov     [rsp+138h+EaLength], ecx; EaLength
0x140038dd4  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x140038dd9  mov     [rsp+138h+EaBuffer], r14; EaBuffer
0x140038dde  mov     [rsp+138h+CreateOptions], 0; CreateOptions
0x140038de6  mov     [rsp+138h+CreateDisposition], 3; CreateDisposition
0x140038dee  mov     [rsp+138h+ShareAccess], 0; ShareAccess
0x140038df6  mov     [rsp+138h+FileAttributes], 80h; FileAttributes
0x140038dfe  mov     [rsp+138h+AllocationSize], 0; AllocationSize
0x140038e07  call    cs:__imp_ZwCreateFile
0x140038e0e  nop     dword ptr [rax+rax+00h]
0x140038e13  xor     edx, edx; Tag
0x140038e15  mov     rcx, rdi; P
0x140038e18  mov     ebx, eax
0x140038e1a  call    cs:__imp_ExFreePoolWithTag
0x140038e21  nop     dword ptr [rax+rax+00h]
0x140038e26  xor     edx, edx; Tag
0x140038e28  mov     rcx, r14; P
0x140038e2b  call    cs:__imp_ExFreePoolWithTag
0x140038e32  nop     dword ptr [rax+rax+00h]
0x140038e37  lea     rdi, WPP_GLOBAL_Control
0x140038e3e  test    ebx, ebx
0x140038e40  js      loc_140038EE0
0x140038e46  mov     ebx, dword ptr [rsp+138h+IoStatusBlock]
0x140038e4d  test    ebx, ebx
0x140038e4f  js      loc_140038EE0
0x140038e55  mov     rcx, [rsp+138h+FileHandle]; Handle
0x140038e5a  lea     rax, [rsp+138h+Object]
0x140038e5f  mov     qword ptr [rsp+138h+FileAttributes], 0; HandleInformation
0x140038e68  xor     r9d, r9d; AccessMode
0x140038e6b  xor     r8d, r8d; ObjectType
0x140038e6e  mov     [rsp+138h+AllocationSize], rax; Object
0x140038e73  xor     edx, edx; DesiredAccess
0x140038e75  mov     [rsp+138h+Object], 0
0x140038e7e  call    cs:__imp_ObReferenceObjectByHandle
0x140038e85  nop     dword ptr [rax+rax+00h]
0x140038e8a  mov     ebx, eax
0x140038e8c  test    eax, eax
0x140038e8e  jns     short loc_140038ED9
0x140038e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e97  lea     rdi, WPP_GLOBAL_Control
0x140038e9e  cmp     rcx, rdi
0x140038ea1  jz      short loc_140038EC3
0x140038ea3  mov     eax, [rcx+2Ch]
0x140038ea6  test    sil, al
0x140038ea9  jz      short loc_140038EC3
0x140038eab  mov     rcx, [rcx+18h]
0x140038eaf  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038eb6  mov     edx, 10h
0x140038ebb  mov     r9d, ebx
0x140038ebe  call    WPP_SF_d
0x140038ec3  mov     rcx, [rsp+138h+FileHandle]; Handle
0x140038ec8  call    cs:__imp_ZwClose
0x140038ecf  nop     dword ptr [rax+rax+00h]
0x140038ed4  jmp     loc_140039046
0x140038ed9  mov     r14, [rsp+138h+Object]
0x140038ede  jmp     short loc_140038F1F
0x140038ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ee7  cmp     rcx, rdi
0x140038eea  jz      loc_140039046
0x140038ef0  mov     eax, [rcx+2Ch]
0x140038ef3  xor     r14d, r14d
0x140038ef6  test    sil, al
0x140038ef9  jz      short loc_140038F17
0x140038efb  mov     rcx, [rcx+18h]
0x140038eff  lea     edx, [r14+11h]
0x140038f03  mov     r9d, ebx
0x140038f06  mov     [rsp+138h+AllocationSize], r15
0x140038f0b  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038f12  call    WPP_SF_DZ
0x140038f17  test    ebx, ebx
0x140038f19  js      loc_140039046
0x140038f1f  mov     rcx, r14; FileObject
0x140038f22  call    cs:__imp_IoGetRelatedDeviceObject
0x140038f29  nop     dword ptr [rax+rax+00h]
0x140038f2e  mov     r15, rax
0x140038f31  test    r13, r13
0x140038f34  jz      loc_140038FEE
0x140038f3a  lea     r9, TdiErrorHandler
0x140038f41  mov     [rsp+138h+AllocationSize], r13
0x140038f46  mov     r8d, esi
0x140038f49  mov     rdx, r14
0x140038f4c  mov     rcx, rax
0x140038f4f  call    TdiSetEventHandler
0x140038f54  mov     ebx, eax
0x140038f56  test    eax, eax
0x140038f58  js      loc_14003908F
0x140038f5e  mov     [rsp+138h+AllocationSize], r13
0x140038f63  lea     r9, TdiRcvDatagramHandler
0x140038f6a  mov     r13d, 4
0x140038f70  mov     rdx, r14
0x140038f73  mov     r8d, r13d
0x140038f76  mov     rcx, r15
0x140038f79  call    TdiSetEventHandler
0x140038f7e  mov     ebx, eax
0x140038f80  test    eax, eax
0x140038f82  js      short loc_140038FBA
0x140038f84  mov     rcx, [rsp+138h+FileHandle]
0x140038f89  lea     r8, [rsp+138h+var_C0]
0x140038f8e  mov     r9d, r13d
0x140038f91  lea     edx, [r13+17h]
0x140038f95  call    PgmSetTcpInfo
0x140038f9a  mov     ebx, eax
0x140038f9c  test    eax, eax
0x140038f9e  jns     short loc_140038FEE
0x140038fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x140038fa7  cmp     rcx, rdi
0x140038faa  jz      short loc_140038FE6
0x140038fac  mov     eax, [rcx+2Ch]
0x140038faf  test    sil, al
0x140038fb2  jz      short loc_140038FE6
0x140038fb4  lea     edx, [r13+0Eh]
0x140038fb8  jmp     short loc_140038FD3
0x140038fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140038fc1  cmp     rcx, rdi
0x140038fc4  jz      short loc_140038FE6
0x140038fc6  mov     eax, [rcx+2Ch]
0x140038fc9  test    sil, al
0x140038fcc  jz      short loc_140038FE6
0x140038fce  mov     edx, 13h
0x140038fd3  mov     rcx, [rcx+18h]
0x140038fd7  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038fde  mov     r9d, ebx
0x140038fe1  call    WPP_SF_d
0x140038fe6  test    ebx, ebx
0x140038fe8  js      loc_1400390BB
0x140038fee  mov     rax, [rsp+138h+var_B8]
0x140038ff6  mov     r9, [rsp+138h+FileHandle]
0x140038ffb  mov     [rax], r9
0x140038ffe  mov     rax, [rsp+138h+var_B0]
0x140039006  mov     [rax], r14
0x140039009  mov     rax, [rsp+138h+var_A8]
0x140039011  mov     [rax], r15
0x140039014  mov     rcx, cs:WPP_GLOBAL_Control
0x14003901b  cmp     rcx, rdi
0x14003901e  jz      short loc_140039046
0x140039020  mov     eax, [rcx+2Ch]
0x140039023  test    al, 10h
0x140039025  jz      short loc_140039046
0x140039027  mov     rcx, [rcx+18h]
0x14003902b  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140039032  mov     edx, 15h
0x140039037  mov     qword ptr [rsp+138h+FileAttributes], r15
0x14003903c  mov     [rsp+138h+AllocationSize], r14
0x140039041  call    WPP_SF_qqq
0x140039046  test    r12b, r12b
0x140039049  jz      short loc_14003905F
0x14003904b  lea     rcx, [rsp+138h+ApcState]; ApcState
0x140039053  call    cs:__imp_KeUnstackDetachProcess
0x14003905a  nop     dword ptr [rax+rax+00h]
0x14003905f  mov     eax, ebx
0x140039061  mov     rcx, [rsp+138h+var_30]
0x140039069  xor     rcx, rsp; StackCookie
0x14003906c  call    __security_check_cookie
0x140039071  lea     r11, [rsp+138h+var_28]
0x140039079  mov     rbx, [r11+30h]
0x14003907d  mov     rsi, [r11+40h]
0x140039081  mov     rsp, r11
0x140039084  pop     r15
0x140039086  pop     r14
0x140039088  pop     r13
0x14003908a  pop     r12
0x14003908c  pop     rdi
  ... truncated ...
```
