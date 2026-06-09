# PgmTdiOpenControl

- ea: `0x1400388d4`
- end: `0x140038b44`
- name: `PgmTdiOpenControl`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140037b14`

## callees

- `0x140005068`
- `0x14000bcfc`
- `0x14001cdf0`
- `0x1400388d4`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14003894a`
- `ntoskrnl!KeStackAttachProcess` at `0x14003894a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140038ac0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140038ac0`
- `ntoskrnl!ZwCreateFile` at `0x1400389e2`
- `ntoskrnl!ZwCreateFile` at `0x1400389e2`
- `ntoskrnl!ZwClose` at `0x140038a7a`
- `ntoskrnl!ZwClose` at `0x140038a7a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038ad4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038ad4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038a31`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140038a31`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003892a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003892a`

## pseudocode

```c
__int64 __fastcall PgmTdiOpenControl(__int64 a1)
{
  char v2; // si
  HANDLE *v3; // r14
  NTSTATUS Status; // ebx
  HANDLE v5; // rcx
  PVOID Object; // [rsp+60h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-80h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+A8h] [rbp-70h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
  {
    v2 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v2 = 1;
  }
  v3 = (HANDLE *)(a1 + 40);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 24);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateFile((PHANDLE)(a1 + 40), 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 2u, 0, 0, 0);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
        (unsigned int)Status);
  }
  else
  {
    v5 = *v3;
    Object = 0;
    Status = ObReferenceObjectByHandle(v5, 0, 0, 0, &Object, 0);
    *(_QWORD *)(a1 + 56) = Object;
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
          (unsigned int)Status);
      ZwClose(*v3);
    }
  }
  if ( v2 )
    KeUnstackDetachProcess(&ApcState);
  if ( Status < 0 )
  {
    *v3 = 0;
    *(_QWORD *)(a1 + 56) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 48) = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(a1 + 56));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, a1 + 24);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400388d4  mov     r11, rsp
0x1400388d7  push    rbx
0x1400388d8  push    rsi
0x1400388d9  push    rdi
0x1400388da  push    r13
0x1400388dc  push    r14
0x1400388de  push    r15
0x1400388e0  sub     rsp, 0E8h
0x1400388e7  mov     rax, cs:__security_cookie
0x1400388ee  xor     rax, rsp
0x1400388f1  mov     [rsp+118h+var_40], rax
0x1400388f9  xorps   xmm0, xmm0
0x1400388fc  xorps   xmm1, xmm1
0x1400388ff  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x140038904  xor     eax, eax
0x140038906  mov     rdi, rcx
0x140038909  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x140038911  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x140038916  movups  xmmword ptr [r11-80h], xmm0
0x14003891b  movups  xmmword ptr [r11-70h], xmm1
0x140038920  movups  xmmword ptr [r11-60h], xmm1
0x140038925  movups  xmmword ptr [r11-50h], xmm1
0x14003892a  call    cs:__imp_PsGetCurrentProcess
0x140038931  nop     dword ptr [rax+rax+00h]
0x140038936  mov     rcx, cs:PgmStaticConfig; PROCESS
0x14003893d  cmp     rax, rcx
0x140038940  jz      short loc_14003895B
0x140038942  lea     rdx, [rsp+118h+ApcState]; ApcState
0x14003894a  call    cs:__imp_KeStackAttachProcess
0x140038951  nop     dword ptr [rax+rax+00h]
0x140038956  mov     sil, 1
0x140038959  jmp     short loc_14003895E
0x14003895b  xor     sil, sil
0x14003895e  mov     [rsp+118h+EaLength], 0; EaLength
0x140038966  lea     r14, [rdi+28h]
0x14003896a  mov     [rsp+118h+EaBuffer], 0; EaBuffer
0x140038973  lea     r15, [rdi+18h]
0x140038977  mov     [rsp+118h+CreateOptions], 0; CreateOptions
0x14003897f  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x140038987  mov     [rsp+118h+CreateDisposition], 2; CreateDisposition
0x14003898f  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140038994  mov     [rsp+118h+ShareAccess], 0; ShareAccess
0x14003899c  xorps   xmm0, xmm0
0x14003899f  mov     [rsp+118h+FileAttributes], 80h; FileAttributes
0x1400389a7  mov     edx, 0C0000000h; DesiredAccess
0x1400389ac  mov     rcx, r14; FileHandle
0x1400389af  mov     [rsp+118h+AllocationSize], 0; AllocationSize
0x1400389b8  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x1400389c0  mov     [rsp+118h+ObjectAttributes.RootDirectory], 0
0x1400389c9  mov     [rsp+118h+ObjectAttributes.Attributes], 200h
0x1400389d4  mov     [rsp+118h+ObjectAttributes.ObjectName], r15
0x1400389d9  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400389e2  call    cs:__imp_ZwCreateFile
0x1400389e9  nop     dword ptr [rax+rax+00h]
0x1400389ee  lea     r13, WPP_GLOBAL_Control
0x1400389f5  mov     ebx, eax
0x1400389f7  test    eax, eax
0x1400389f9  js      loc_140038A88
0x1400389ff  mov     ebx, dword ptr [rsp+118h+IoStatusBlock]
0x140038a06  test    ebx, ebx
0x140038a08  js      short loc_140038A88
0x140038a0a  mov     rcx, [r14]; Handle
0x140038a0d  lea     rax, [rsp+118h+Object]
0x140038a12  mov     qword ptr [rsp+118h+FileAttributes], 0; HandleInformation
0x140038a1b  xor     r9d, r9d; AccessMode
0x140038a1e  xor     r8d, r8d; ObjectType
0x140038a21  mov     [rsp+118h+AllocationSize], rax; Object
0x140038a26  xor     edx, edx; DesiredAccess
0x140038a28  mov     [rsp+118h+Object], 0
0x140038a31  call    cs:__imp_ObReferenceObjectByHandle
0x140038a38  nop     dword ptr [rax+rax+00h]
0x140038a3d  mov     ebx, eax
0x140038a3f  mov     rax, [rsp+118h+Object]
0x140038a44  mov     [rdi+38h], rax
0x140038a48  test    ebx, ebx
0x140038a4a  jns     short loc_140038AB3
0x140038a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a53  cmp     rcx, r13
0x140038a56  jz      short loc_140038A77
0x140038a58  mov     eax, [rcx+2Ch]
0x140038a5b  test    al, 2
0x140038a5d  jz      short loc_140038A77
0x140038a5f  mov     rcx, [rcx+18h]
0x140038a63  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038a6a  mov     edx, 17h
0x140038a6f  mov     r9d, ebx
0x140038a72  call    WPP_SF_d
0x140038a77  mov     rcx, [r14]; Handle
0x140038a7a  call    cs:__imp_ZwClose
0x140038a81  nop     dword ptr [rax+rax+00h]
0x140038a86  jmp     short loc_140038AB3
0x140038a88  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a8f  cmp     rcx, r13
0x140038a92  jz      short loc_140038AB3
0x140038a94  mov     eax, [rcx+2Ch]
0x140038a97  test    al, 2
0x140038a99  jz      short loc_140038AB3
0x140038a9b  mov     rcx, [rcx+18h]
0x140038a9f  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038aa6  mov     edx, 18h
0x140038aab  mov     r9d, ebx
0x140038aae  call    WPP_SF_d
0x140038ab3  test    sil, sil
0x140038ab6  jz      short loc_140038ACC
0x140038ab8  lea     rcx, [rsp+118h+ApcState]; ApcState
0x140038ac0  call    cs:__imp_KeUnstackDetachProcess
0x140038ac7  nop     dword ptr [rax+rax+00h]
0x140038acc  test    ebx, ebx
0x140038ace  js      short loc_140038B11
0x140038ad0  mov     rcx, [rdi+38h]; FileObject
0x140038ad4  call    cs:__imp_IoGetRelatedDeviceObject
0x140038adb  nop     dword ptr [rax+rax+00h]
0x140038ae0  mov     [rdi+30h], rax
0x140038ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x140038aeb  cmp     rcx, r13
0x140038aee  jz      short loc_140038B20
0x140038af0  mov     eax, [rcx+2Ch]
0x140038af3  test    al, 10h
0x140038af5  jz      short loc_140038B20
0x140038af7  mov     rcx, [rcx+18h]
0x140038afb  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038b02  mov     edx, 19h
0x140038b07  mov     r9, r15
0x140038b0a  call    WPP_SF_Z
0x140038b0f  jmp     short loc_140038B20
0x140038b11  mov     qword ptr [r14], 0
0x140038b18  mov     qword ptr [rdi+38h], 0
0x140038b20  mov     eax, ebx
0x140038b22  mov     rcx, [rsp+118h+var_40]
0x140038b2a  xor     rcx, rsp; StackCookie
0x140038b2d  call    __security_check_cookie
0x140038b32  add     rsp, 0E8h
0x140038b39  pop     r15
0x140038b3b  pop     r14
0x140038b3d  pop     r13
0x140038b3f  pop     rdi
0x140038b40  pop     rsi
0x140038b41  pop     rbx
0x140038b42  retn
```
