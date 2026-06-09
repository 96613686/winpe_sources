# PgmTdiOpenControl

- ea: `0x140038884`
- end: `0x140038af4`
- name: `PgmTdiOpenControl`
- size: `624`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140037ac4`

## callees

- `0x140005068`
- `0x14000bcfc`
- `0x14001cdf0`
- `0x140038884`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400388fa`
- `ntoskrnl!KeStackAttachProcess` at `0x1400388fa`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140038a70`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140038a70`
- `ntoskrnl!ZwCreateFile` at `0x140038992`
- `ntoskrnl!ZwCreateFile` at `0x140038992`
- `ntoskrnl!ZwClose` at `0x140038a2a`
- `ntoskrnl!ZwClose` at `0x140038a2a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038a84`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140038a84`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400389e1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400389e1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400388da`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400388da`

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
0x140038884  mov     r11, rsp
0x140038887  push    rbx
0x140038888  push    rsi
0x140038889  push    rdi
0x14003888a  push    r13
0x14003888c  push    r14
0x14003888e  push    r15
0x140038890  sub     rsp, 0E8h
0x140038897  mov     rax, cs:__security_cookie
0x14003889e  xor     rax, rsp
0x1400388a1  mov     [rsp+118h+var_40], rax
0x1400388a9  xorps   xmm0, xmm0
0x1400388ac  xorps   xmm1, xmm1
0x1400388af  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x1400388b4  xor     eax, eax
0x1400388b6  mov     rdi, rcx
0x1400388b9  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x1400388c1  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x1400388c6  movups  xmmword ptr [r11-80h], xmm0
0x1400388cb  movups  xmmword ptr [r11-70h], xmm1
0x1400388d0  movups  xmmword ptr [r11-60h], xmm1
0x1400388d5  movups  xmmword ptr [r11-50h], xmm1
0x1400388da  call    cs:__imp_PsGetCurrentProcess
0x1400388e1  nop     dword ptr [rax+rax+00h]
0x1400388e6  mov     rcx, cs:PgmStaticConfig; PROCESS
0x1400388ed  cmp     rax, rcx
0x1400388f0  jz      short loc_14003890B
0x1400388f2  lea     rdx, [rsp+118h+ApcState]; ApcState
0x1400388fa  call    cs:__imp_KeStackAttachProcess
0x140038901  nop     dword ptr [rax+rax+00h]
0x140038906  mov     sil, 1
0x140038909  jmp     short loc_14003890E
0x14003890b  xor     sil, sil
0x14003890e  mov     [rsp+118h+EaLength], 0; EaLength
0x140038916  lea     r14, [rdi+28h]
0x14003891a  mov     [rsp+118h+EaBuffer], 0; EaBuffer
0x140038923  lea     r15, [rdi+18h]
0x140038927  mov     [rsp+118h+CreateOptions], 0; CreateOptions
0x14003892f  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x140038937  mov     [rsp+118h+CreateDisposition], 2; CreateDisposition
0x14003893f  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140038944  mov     [rsp+118h+ShareAccess], 0; ShareAccess
0x14003894c  xorps   xmm0, xmm0
0x14003894f  mov     [rsp+118h+FileAttributes], 80h; FileAttributes
0x140038957  mov     edx, 0C0000000h; DesiredAccess
0x14003895c  mov     rcx, r14; FileHandle
0x14003895f  mov     [rsp+118h+AllocationSize], 0; AllocationSize
0x140038968  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x140038970  mov     [rsp+118h+ObjectAttributes.RootDirectory], 0
0x140038979  mov     [rsp+118h+ObjectAttributes.Attributes], 200h
0x140038984  mov     [rsp+118h+ObjectAttributes.ObjectName], r15
0x140038989  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x140038992  call    cs:__imp_ZwCreateFile
0x140038999  nop     dword ptr [rax+rax+00h]
0x14003899e  lea     r13, WPP_GLOBAL_Control
0x1400389a5  mov     ebx, eax
0x1400389a7  test    eax, eax
0x1400389a9  js      loc_140038A38
0x1400389af  mov     ebx, dword ptr [rsp+118h+IoStatusBlock]
0x1400389b6  test    ebx, ebx
0x1400389b8  js      short loc_140038A38
0x1400389ba  mov     rcx, [r14]; Handle
0x1400389bd  lea     rax, [rsp+118h+Object]
0x1400389c2  mov     qword ptr [rsp+118h+FileAttributes], 0; HandleInformation
0x1400389cb  xor     r9d, r9d; AccessMode
0x1400389ce  xor     r8d, r8d; ObjectType
0x1400389d1  mov     [rsp+118h+AllocationSize], rax; Object
0x1400389d6  xor     edx, edx; DesiredAccess
0x1400389d8  mov     [rsp+118h+Object], 0
0x1400389e1  call    cs:__imp_ObReferenceObjectByHandle
0x1400389e8  nop     dword ptr [rax+rax+00h]
0x1400389ed  mov     ebx, eax
0x1400389ef  mov     rax, [rsp+118h+Object]
0x1400389f4  mov     [rdi+38h], rax
0x1400389f8  test    ebx, ebx
0x1400389fa  jns     short loc_140038A63
0x1400389fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a03  cmp     rcx, r13
0x140038a06  jz      short loc_140038A27
0x140038a08  mov     eax, [rcx+2Ch]
0x140038a0b  test    al, 2
0x140038a0d  jz      short loc_140038A27
0x140038a0f  mov     rcx, [rcx+18h]
0x140038a13  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038a1a  mov     edx, 17h
0x140038a1f  mov     r9d, ebx
0x140038a22  call    WPP_SF_d
0x140038a27  mov     rcx, [r14]; Handle
0x140038a2a  call    cs:__imp_ZwClose
0x140038a31  nop     dword ptr [rax+rax+00h]
0x140038a36  jmp     short loc_140038A63
0x140038a38  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a3f  cmp     rcx, r13
0x140038a42  jz      short loc_140038A63
0x140038a44  mov     eax, [rcx+2Ch]
0x140038a47  test    al, 2
0x140038a49  jz      short loc_140038A63
0x140038a4b  mov     rcx, [rcx+18h]
0x140038a4f  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038a56  mov     edx, 18h
0x140038a5b  mov     r9d, ebx
0x140038a5e  call    WPP_SF_d
0x140038a63  test    sil, sil
0x140038a66  jz      short loc_140038A7C
0x140038a68  lea     rcx, [rsp+118h+ApcState]; ApcState
0x140038a70  call    cs:__imp_KeUnstackDetachProcess
0x140038a77  nop     dword ptr [rax+rax+00h]
0x140038a7c  test    ebx, ebx
0x140038a7e  js      short loc_140038AC1
0x140038a80  mov     rcx, [rdi+38h]; FileObject
0x140038a84  call    cs:__imp_IoGetRelatedDeviceObject
0x140038a8b  nop     dword ptr [rax+rax+00h]
0x140038a90  mov     [rdi+30h], rax
0x140038a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a9b  cmp     rcx, r13
0x140038a9e  jz      short loc_140038AD0
0x140038aa0  mov     eax, [rcx+2Ch]
0x140038aa3  test    al, 10h
0x140038aa5  jz      short loc_140038AD0
0x140038aa7  mov     rcx, [rcx+18h]
0x140038aab  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x140038ab2  mov     edx, 19h
0x140038ab7  mov     r9, r15
0x140038aba  call    WPP_SF_Z
0x140038abf  jmp     short loc_140038AD0
0x140038ac1  mov     qword ptr [r14], 0
0x140038ac8  mov     qword ptr [rdi+38h], 0
0x140038ad0  mov     eax, ebx
0x140038ad2  mov     rcx, [rsp+118h+var_40]
0x140038ada  xor     rcx, rsp; StackCookie
0x140038add  call    __security_check_cookie
0x140038ae2  add     rsp, 0E8h
0x140038ae9  pop     r15
0x140038aeb  pop     r14
0x140038aed  pop     r13
0x140038aef  pop     rdi
0x140038af0  pop     rsi
0x140038af1  pop     rbx
0x140038af2  retn
```
