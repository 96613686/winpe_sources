# VsmmCxlpOpenScmbusCxlDevice

- ea: `0x1400e4474`
- end: `0x1400e46a8`
- name: `VsmmCxlpOpenScmbusCxlDevice`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400e46b0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400e4474`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e4521`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e4521`
- `ntoskrnl!ZwClose` at `0x1400e4669`
- `ntoskrnl!ZwClose` at `0x1400e4669`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4681`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4681`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400e44d0`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400e44d0`
- `ntoskrnl!ZwOpenFile` at `0x1400e4574`
- `ntoskrnl!ZwOpenFile` at `0x1400e4574`

## string_xrefs

- `0x1400e44f2`: `VsmmCxlpOpenScmbusCxlDevice`
- `0x1400e45b2`: `VsmmCxlpOpenScmbusCxlDevice`

## pseudocode

```c
__int64 __fastcall VsmmCxlpOpenScmbusCxlDevice(void **a1)
{
  NTSTATUS DeviceInterfaces; // ebx
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+38h] [rbp-C8h] BYREF
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  NTSTATUS v7; // [rsp+44h] [rbp-BCh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  char v11[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v12[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v13[16]; // [rsp+D0h] [rbp-30h] BYREF
  int *v14; // [rsp+E0h] [rbp-20h]
  __int64 v15; // [rsp+E8h] [rbp-18h]
  NTSTATUS *v16; // [rsp+F0h] [rbp-10h]
  __int64 v17; // [rsp+F8h] [rbp-8h]
  _DWORD *v18; // [rsp+100h] [rbp+0h]
  __int64 v19; // [rsp+108h] [rbp+8h]
  wchar_t *Buffer; // [rsp+110h] [rbp+10h]
  _DWORD v21[2]; // [rsp+118h] [rbp+18h] BYREF

  SymbolicLinkList = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DeviceInterfaces = IoGetDeviceInterfaces(&GUID_DEVINTERFACE_MTM_BUS, 0, 0, &SymbolicLinkList);
  if ( DeviceInterfaces >= 0 )
  {
    if ( *SymbolicLinkList )
    {
      RtlInitUnicodeString(&DestinationString, SymbolicLinkList);
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      DeviceInterfaces = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0);
      if ( DeviceInterfaces >= 0 )
      {
        DeviceInterfaces = 0;
        *a1 = FileHandle;
        FileHandle = 0;
      }
      else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v12, "VsmmCxlpOpenScmbusCxlDevice");
        tlgCreate1Sz_char(v13, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v6 = 459;
        v14 = &v6;
        v15 = 4;
        v16 = &v7;
        v7 = DeviceInterfaces;
        v18 = v21;
        Buffer = DestinationString.Buffer;
        v21[0] = DestinationString.Length;
        v17 = 4;
        v19 = 2;
        v21[1] = 0;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14005B44F, 0, 0, 8, v11);
      }
    }
    else
    {
      DeviceInterfaces = -1073741275;
    }
  }
  else
  {
    VidTraceErrorStatusInternal0("VsmmCxlpOpenScmbusCxlDevice", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c", 429);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( SymbolicLinkList )
    ExFreePoolWithTag(SymbolicLinkList, 0);
  return (unsigned int)DeviceInterfaces;
}

```

## disassembly

```asm
0x1400e4474  push    rbp
0x1400e4476  push    rbx
0x1400e4477  push    rsi
0x1400e4478  push    rdi
0x1400e4479  lea     rbp, [rsp-38h]
0x1400e447e  sub     rsp, 138h
0x1400e4485  mov     rax, cs:__security_cookie
0x1400e448c  xor     rax, rsp
0x1400e448f  mov     [rbp+50h+var_30], rax
0x1400e4493  xorps   xmm0, xmm0
0x1400e4496  lea     r9, [rsp+150h+SymbolicLinkList]; SymbolicLinkList
0x1400e449b  mov     rdi, rcx
0x1400e449e  xor     esi, esi
0x1400e44a0  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x1400e44a5  xor     eax, eax
0x1400e44a7  mov     [rsp+150h+SymbolicLinkList], rsi
0x1400e44ac  xor     r8d, r8d; Flags
0x1400e44af  mov     [rsp+150h+FileHandle], rsi
0x1400e44b4  xor     edx, edx; PhysicalDeviceObject
0x1400e44b6  lea     rcx, GUID_DEVINTERFACE_MTM_BUS; InterfaceClassGuid
0x1400e44bd  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1400e44c2  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1400e44c7  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400e44cc  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400e44d0  call    cs:__imp_IoGetDeviceInterfaces
0x1400e44d7  nop     dword ptr [rax+rax+00h]
0x1400e44dc  mov     ebx, eax
0x1400e44de  test    eax, eax
0x1400e44e0  jns     short loc_1400E4503
0x1400e44e2  mov     r9d, eax
0x1400e44e5  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e44ec  mov     r8d, 1ADh
0x1400e44f2  lea     rcx, aVsmmcxlpopensc; "VsmmCxlpOpenScmbusCxlDevice"
0x1400e44f9  call    VidTraceErrorStatusInternal0
0x1400e44fe  jmp     loc_1400E465F
0x1400e4503  mov     rax, [rsp+150h+SymbolicLinkList]
0x1400e4508  cmp     [rax], si
0x1400e450b  jnz     short loc_1400E4517
0x1400e450d  mov     ebx, 0C0000225h
0x1400e4512  jmp     loc_1400E465F
0x1400e4517  mov     rdx, [rsp+150h+SymbolicLinkList]; SourceString
0x1400e451c  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400e4521  call    cs:__imp_RtlInitUnicodeString
0x1400e4528  nop     dword ptr [rax+rax+00h]
0x1400e452d  lea     rax, [rsp+150h+DestinationString]
0x1400e4532  mov     [rsp+150h+OpenOptions], esi; OpenOptions
0x1400e4536  xorps   xmm0, xmm0
0x1400e4539  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1400e453e  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400e4542  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400e454a  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400e454f  mov     [rsp+150h+ObjectAttributes.RootDirectory], rsi
0x1400e4554  mov     edx, 80100000h; DesiredAccess
0x1400e4559  mov     [rsp+150h+ObjectAttributes.Attributes], 240h
0x1400e4561  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400e4566  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x1400e456e  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e4574  call    cs:__imp_ZwOpenFile
0x1400e457b  nop     dword ptr [rax+rax+00h]
0x1400e4580  mov     ebx, eax
0x1400e4582  test    eax, eax
0x1400e4584  jns     loc_1400E4650
0x1400e458a  mov     eax, cs:dword_140064110
0x1400e4590  cmp     eax, 2
0x1400e4593  jbe     loc_1400E465F
0x1400e4599  mov     edx, 100h
0x1400e459e  lea     rcx, dword_140064110
0x1400e45a5  call    _tlgKeywordOn
0x1400e45aa  test    al, al
0x1400e45ac  jz      loc_1400E465F
0x1400e45b2  lea     rdx, aVsmmcxlpopensc; "VsmmCxlpOpenScmbusCxlDevice"
0x1400e45b9  lea     rcx, [rbp+50h+var_90]
0x1400e45bd  call    _tlgCreate1Sz_char
0x1400e45c2  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e45c9  lea     rcx, [rbp+50h+var_80]
0x1400e45cd  call    _tlgCreate1Sz_char
0x1400e45d2  lea     rax, [rsp+150h+var_110]
0x1400e45d7  mov     [rsp+150h+var_110], 1CBh
0x1400e45df  mov     [rbp+50h+var_70], rax
0x1400e45e3  lea     rdx, byte_14005B44F
0x1400e45ea  lea     rax, [rsp+150h+var_10C]
0x1400e45ef  mov     [rbp+50h+var_68], 4
0x1400e45f7  mov     [rbp+50h+var_60], rax
0x1400e45fb  lea     rcx, dword_140064110
0x1400e4602  lea     rax, [rbp+50h+var_38]
0x1400e4606  mov     [rsp+150h+var_10C], ebx
0x1400e460a  mov     [rbp+50h+var_50], rax
0x1400e460e  xor     r9d, r9d
0x1400e4611  mov     rax, [rsp+150h+DestinationString.Buffer]
0x1400e4616  xor     r8d, r8d
0x1400e4619  mov     [rbp+50h+var_40], rax
0x1400e461d  movzx   eax, [rsp+150h+DestinationString.Length]
0x1400e4622  mov     [rbp+50h+var_38], eax
0x1400e4625  lea     rax, [rbp+50h+var_B0]
0x1400e4629  mov     qword ptr [rsp+150h+OpenOptions], rax
0x1400e462e  mov     [rsp+150h+ShareAccess], 8
0x1400e4636  mov     [rbp+50h+var_58], 4
0x1400e463e  mov     [rbp+50h+var_48], 2
0x1400e4646  mov     [rbp+50h+var_34], esi
0x1400e4649  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e464e  jmp     short loc_1400E465F
0x1400e4650  mov     rax, [rsp+150h+FileHandle]
0x1400e4655  mov     ebx, esi
0x1400e4657  mov     [rdi], rax
0x1400e465a  mov     [rsp+150h+FileHandle], rsi
0x1400e465f  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1400e4664  test    rcx, rcx
0x1400e4667  jz      short loc_1400E4675
0x1400e4669  call    cs:__imp_ZwClose
0x1400e4670  nop     dword ptr [rax+rax+00h]
0x1400e4675  mov     rcx, [rsp+150h+SymbolicLinkList]; P
0x1400e467a  test    rcx, rcx
0x1400e467d  jz      short loc_1400E468D
0x1400e467f  xor     edx, edx; Tag
0x1400e4681  call    cs:__imp_ExFreePoolWithTag
0x1400e4688  nop     dword ptr [rax+rax+00h]
0x1400e468d  mov     eax, ebx
0x1400e468f  mov     rcx, [rbp+50h+var_30]
0x1400e4693  xor     rcx, rsp; StackCookie
0x1400e4696  call    __security_check_cookie
0x1400e469b  add     rsp, 138h
0x1400e46a2  pop     rdi
0x1400e46a3  pop     rsi
0x1400e46a4  pop     rbx
0x1400e46a5  pop     rbp
0x1400e46a6  retn
```
