# VMX_IO_DISK_EXTENT::DeleteLegacyNameLinks(void)

- ea: `0x14000cce0`
- end: `0x14000cdd8`
- name: `?DeleteLegacyNameLinks@VMX_IO_DISK_EXTENT@@UEAAXXZ`
- size: `248`
- prototype: `void __fastcall(VMX_IO_DISK_EXTENT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000982c`
- `0x14000cce0`
- `0x14001b960`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd50`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd99`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd50`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd99`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000cd61`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000cdaa`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000cd61`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000cdaa`

## pseudocode

```c
void __fastcall VMX_IO_DISK_EXTENT::DeleteLegacyNameLinks(VMX_IO_DISK_EXTENT *this)
{
  signed __int32 v1; // edi
  signed __int32 v3; // [rsp+20h] [rbp-D8h]
  __int64 v4; // [rsp+20h] [rbp-D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-C8h] BYREF
  wchar_t pszDest[80]; // [rsp+40h] [rbp-B8h] BYREF

  v1 = *((_DWORD *)this + 16);
  DestinationString = 0;
  if ( v1 )
  {
    if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)this + 16, 0, v1) )
    {
      v3 = v1;
      RtlStringCbPrintfW(
        pszDest,
        0xA0u,
        L"\\DosDevices\\Harddisk%dPartition%d",
        *(unsigned int *)(*((_QWORD *)this + 6) + 32LL),
        v3);
      RtlInitUnicodeString(&DestinationString, pszDest);
      IoDeleteSymbolicLink(&DestinationString);
      LODWORD(v4) = v1;
      RtlStringCbPrintfW(
        pszDest,
        0xA0u,
        L"\\Device\\Harddisk%d\\Partition%d",
        *(unsigned int *)(*((_QWORD *)this + 6) + 32LL),
        v4);
      RtlInitUnicodeString(&DestinationString, pszDest);
      IoDeleteSymbolicLink(&DestinationString);
    }
  }
}

```

## disassembly

```asm
0x14000cce0  mov     [rsp+arg_8], rbx
0x14000cce5  push    rdi
0x14000cce6  sub     rsp, 0F0h
0x14000cced  mov     rax, cs:__security_cookie
0x14000ccf4  xor     rax, rsp
0x14000ccf7  mov     [rsp+0F8h+var_18], rax
0x14000ccff  mov     edi, [rcx+40h]
0x14000cd02  xorps   xmm0, xmm0
0x14000cd05  mov     rbx, rcx
0x14000cd08  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x14000cd0d  test    edi, edi
0x14000cd0f  jz      loc_14000CDB6
0x14000cd15  xor     edx, edx
0x14000cd17  mov     eax, edi
0x14000cd19  lock cmpxchg [rcx+40h], edx
0x14000cd1e  jnz     loc_14000CDB6
0x14000cd24  mov     r9, [rcx+30h]
0x14000cd28  lea     r8, aDosdevicesHard; "\\DosDevices\\Harddisk%dPartition%d"
0x14000cd2f  mov     edx, 0A0h; cbDest
0x14000cd34  mov     [rsp+0F8h+var_D8], edi
0x14000cd38  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x14000cd3d  mov     r9d, [r9+20h]
0x14000cd41  call    RtlStringCbPrintfW
0x14000cd46  lea     rdx, [rsp+0F8h+pszDest]; SourceString
0x14000cd4b  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x14000cd50  call    cs:__imp_RtlInitUnicodeString
0x14000cd57  nop     dword ptr [rax+rax+00h]
0x14000cd5c  lea     rcx, [rsp+0F8h+DestinationString]; SymbolicLinkName
0x14000cd61  call    cs:__imp_IoDeleteSymbolicLink
0x14000cd68  nop     dword ptr [rax+rax+00h]
0x14000cd6d  mov     r9, [rbx+30h]
0x14000cd71  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%d\\Partition%d"
0x14000cd78  mov     edx, 0A0h; cbDest
0x14000cd7d  mov     [rsp+0F8h+var_D8], edi
0x14000cd81  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x14000cd86  mov     r9d, [r9+20h]
0x14000cd8a  call    RtlStringCbPrintfW
0x14000cd8f  lea     rdx, [rsp+0F8h+pszDest]; SourceString
0x14000cd94  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x14000cd99  call    cs:__imp_RtlInitUnicodeString
0x14000cda0  nop     dword ptr [rax+rax+00h]
0x14000cda5  lea     rcx, [rsp+0F8h+DestinationString]; SymbolicLinkName
0x14000cdaa  call    cs:__imp_IoDeleteSymbolicLink
0x14000cdb1  nop     dword ptr [rax+rax+00h]
0x14000cdb6  mov     rcx, [rsp+0F8h+var_18]
0x14000cdbe  xor     rcx, rsp; StackCookie
0x14000cdc1  call    __security_check_cookie
0x14000cdc6  mov     rbx, [rsp+0F8h+arg_8]
0x14000cdce  add     rsp, 0F0h
0x14000cdd5  pop     rdi
0x14000cdd6  retn
```
