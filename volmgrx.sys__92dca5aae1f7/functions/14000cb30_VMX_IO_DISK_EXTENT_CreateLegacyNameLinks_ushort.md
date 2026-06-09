# VMX_IO_DISK_EXTENT::CreateLegacyNameLinks(ushort *)

- ea: `0x14000cb30`
- end: `0x14000cc6c`
- name: `?CreateLegacyNameLinks@VMX_IO_DISK_EXTENT@@UEAAXPEAG@Z`
- size: `316`
- prototype: `void __fastcall(VMX_IO_DISK_EXTENT *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000982c`
- `0x14000cb30`
- `0x140010214`
- `0x14001b960`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb70`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cbdb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc2c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb70`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cbdb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc2c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000cbf1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000cc42`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000cbf1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000cc42`

## pseudocode

```c
void __fastcall VMX_IO_DISK_EXTENT::CreateLegacyNameLinks(VMX_IO_DISK_EXTENT *this, unsigned __int16 *a2)
{
  int v3; // [rsp+20h] [rbp-E0h]
  __int64 v4; // [rsp+20h] [rbp-E0h]
  unsigned int v5; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[80]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( !*((_DWORD *)this + 16)
    && (int)VMX_IO_DISK_EXTENT::QueryPartitionNumber(this, &v5) >= 0
    && !_InterlockedCompareExchange((volatile signed __int32 *)this + 16, v5, 0) )
  {
    v3 = *((_DWORD *)this + 16);
    RtlStringCbPrintfW(
      pszDest,
      0xA0u,
      L"\\Device\\Harddisk%d\\Partition%d",
      *(unsigned int *)(*((_QWORD *)this + 6) + 32LL),
      v3);
    RtlInitUnicodeString(&SymbolicLinkName, pszDest);
    IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
    LODWORD(v4) = *((_DWORD *)this + 16);
    RtlStringCbPrintfW(
      pszDest,
      0xA0u,
      L"\\DosDevices\\Harddisk%dPartition%d",
      *(unsigned int *)(*((_QWORD *)this + 6) + 32LL),
      v4);
    RtlInitUnicodeString(&SymbolicLinkName, pszDest);
    IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
  }
}

```

## disassembly

```asm
0x14000cb30  mov     [rsp-8+arg_10], rbx
0x14000cb35  push    rbp
0x14000cb36  lea     rbp, [rsp-10h]
0x14000cb3b  sub     rsp, 110h
0x14000cb42  mov     rax, cs:__security_cookie
0x14000cb49  xor     rax, rsp
0x14000cb4c  mov     [rbp+10h+var_10], rax
0x14000cb50  mov     rbx, rcx
0x14000cb53  mov     [rsp+110h+var_E0], 0
0x14000cb5b  xorps   xmm0, xmm0
0x14000cb5e  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x14000cb63  xorps   xmm1, xmm1
0x14000cb66  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x14000cb6b  movups  xmmword ptr [rsp+110h+SymbolicLinkName.Length], xmm1
0x14000cb70  call    cs:__imp_RtlInitUnicodeString
0x14000cb77  nop     dword ptr [rax+rax+00h]
0x14000cb7c  cmp     dword ptr [rbx+40h], 0
0x14000cb80  jnz     loc_14000CC4E
0x14000cb86  lea     rdx, [rsp+110h+var_E0]; unsigned int *
0x14000cb8b  mov     rcx, rbx; this
0x14000cb8e  call    ?QueryPartitionNumber@VMX_IO_DISK_EXTENT@@AEAAJPEAK@Z; VMX_IO_DISK_EXTENT::QueryPartitionNumber(ulong *)
0x14000cb93  test    eax, eax
0x14000cb95  js      loc_14000CC4E
0x14000cb9b  mov     ecx, [rsp+110h+var_E0]
0x14000cb9f  xor     eax, eax
0x14000cba1  lock cmpxchg [rbx+40h], ecx
0x14000cba6  jnz     loc_14000CC4E
0x14000cbac  mov     r9, [rbx+30h]
0x14000cbb0  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%d\\Partition%d"
0x14000cbb7  mov     eax, [rbx+40h]
0x14000cbba  lea     rcx, [rsp+110h+pszDest]; pszDest
0x14000cbbf  mov     edx, 0A0h; cbDest
0x14000cbc4  mov     [rsp+110h+var_F0], eax
0x14000cbc8  mov     r9d, [r9+20h]
0x14000cbcc  call    RtlStringCbPrintfW
0x14000cbd1  lea     rdx, [rsp+110h+pszDest]; SourceString
0x14000cbd6  lea     rcx, [rsp+110h+SymbolicLinkName]; DestinationString
0x14000cbdb  call    cs:__imp_RtlInitUnicodeString
0x14000cbe2  nop     dword ptr [rax+rax+00h]
0x14000cbe7  lea     rdx, [rsp+110h+DestinationString]; DeviceName
0x14000cbec  lea     rcx, [rsp+110h+SymbolicLinkName]; SymbolicLinkName
0x14000cbf1  call    cs:__imp_IoCreateSymbolicLink
0x14000cbf8  nop     dword ptr [rax+rax+00h]
0x14000cbfd  mov     r9, [rbx+30h]
0x14000cc01  lea     r8, aDosdevicesHard; "\\DosDevices\\Harddisk%dPartition%d"
0x14000cc08  mov     eax, [rbx+40h]
0x14000cc0b  lea     rcx, [rsp+110h+pszDest]; pszDest
0x14000cc10  mov     edx, 0A0h; cbDest
0x14000cc15  mov     [rsp+110h+var_F0], eax
0x14000cc19  mov     r9d, [r9+20h]
0x14000cc1d  call    RtlStringCbPrintfW
0x14000cc22  lea     rdx, [rsp+110h+pszDest]; SourceString
0x14000cc27  lea     rcx, [rsp+110h+SymbolicLinkName]; DestinationString
0x14000cc2c  call    cs:__imp_RtlInitUnicodeString
0x14000cc33  nop     dword ptr [rax+rax+00h]
0x14000cc38  lea     rdx, [rsp+110h+DestinationString]; DeviceName
0x14000cc3d  lea     rcx, [rsp+110h+SymbolicLinkName]; SymbolicLinkName
0x14000cc42  call    cs:__imp_IoCreateSymbolicLink
0x14000cc49  nop     dword ptr [rax+rax+00h]
0x14000cc4e  mov     rcx, [rbp+10h+var_10]
0x14000cc52  xor     rcx, rsp; StackCookie
0x14000cc55  call    __security_check_cookie
0x14000cc5a  mov     rbx, [rsp+110h+arg_10]
0x14000cc62  add     rsp, 110h
0x14000cc69  pop     rbp
0x14000cc6a  retn
```
