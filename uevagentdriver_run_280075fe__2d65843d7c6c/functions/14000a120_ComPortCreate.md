# ComPortCreate

- ea: `0x14000a120`
- end: `0x14000a27b`
- name: `ComPortCreate`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c614`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a120`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a196`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a196`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000a24f`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000bb1e`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000a24f`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000bb1e`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000a21d`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000a21d`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x14000a168`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x14000a168`

## string_xrefs

- `0x14000a14b`: `UevFilter.ComPortCreate: Entry\n`
- `0x14000a17e`: `UevFilter.ComPortCreate: Failed building security descriptor, error = 0x%X\n`
- `0x14000a18a`: `\UevConnectCreateNotifyPort`
- `0x14000a233`: `UevFilter.ComPortCreate: Failed creating communication port, error = 0x%X\n`
- `0x14000a25e`: `UevFilter.ComPortCreate: Exit, retStatus = 0x%X\n`

## pseudocode

```c
__int64 ComPortCreate()
{
  NTSTATUS v0; // ebx
  char *v1; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+8h] BYREF

  DestinationString = 0;
  SecurityDescriptor = 0;
  memset(&ObjectAttributes, 0, 44);
  DbgTrace(2, "UevFilter.ComPortCreate: Entry\n");
  v0 = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\UevConnectCreateNotifyPort");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.SecurityQualityOfService = 0;
    v0 = FltCreateCommunicationPort(
           g_pFilter,
           &pServerPort,
           &ObjectAttributes,
           0,
           PortConnectHandler,
           PortDisconnectHandler,
           0,
           10);
    if ( v0 >= 0 )
      goto LABEL_6;
    v1 = "UevFilter.ComPortCreate: Failed creating communication port, error = 0x%X\n";
  }
  else
  {
    v1 = "UevFilter.ComPortCreate: Failed building security descriptor, error = 0x%X\n";
  }
  DbgTraceFrmtErr(v1);
LABEL_6:
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  DbgTraceFrmt(2, "UevFilter.ComPortCreate: Exit, retStatus = 0x%X\n", v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000a120  mov     rax, rsp
0x14000a123  push    rbx
0x14000a124  sub     rsp, 90h
0x14000a12b  xorps   xmm0, xmm0
0x14000a12e  movups  xmmword ptr [rax-50h], xmm0
0x14000a132  mov     qword ptr [rax+8], 0
0x14000a13a  xor     eax, eax
0x14000a13c  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x14000a141  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x14000a146  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x14000a14b  lea     rdx, aUevfilterCompo; "UevFilter.ComPortCreate: Entry\n"
0x14000a152  lea     ecx, [rax+2]
0x14000a155  call    DbgTrace
0x14000a15a  nop
0x14000a15b  mov     edx, 1F0001h; DesiredAccess
0x14000a160  lea     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x14000a168  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x14000a16f  nop     dword ptr [rax+rax+00h]
0x14000a174  mov     ebx, eax
0x14000a176  mov     [rsp+98h+var_58], eax
0x14000a17a  test    eax, eax
0x14000a17c  jns     short loc_14000A18A
0x14000a17e  lea     rcx, aUevfilterCompo_1; "UevFilter.ComPortCreate: Failed buildin"...
0x14000a185  jmp     loc_14000A23A
0x14000a18a  lea     rdx, SourceString; "\\UevConnectCreateNotifyPort"
0x14000a191  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14000a196  call    cs:__imp_RtlInitUnicodeString
0x14000a19d  nop     dword ptr [rax+rax+00h]
0x14000a1a2  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x14000a1aa  mov     [rsp+98h+ObjectAttributes.RootDirectory], 0
0x14000a1b3  mov     [rsp+98h+ObjectAttributes.Attributes], 240h
0x14000a1bb  lea     rax, [rsp+98h+DestinationString]
0x14000a1c0  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x14000a1c5  mov     rax, [rsp+98h+SecurityDescriptor]
0x14000a1cd  mov     [rsp+98h+ObjectAttributes.SecurityDescriptor], rax
0x14000a1d2  mov     [rsp+98h+ObjectAttributes.SecurityQualityOfService], 0
0x14000a1de  mov     [rsp+98h+MaxConnections], 0Ah; MaxConnections
0x14000a1e6  mov     [rsp+98h+MessageNotifyCallback], 0; MessageNotifyCallback
0x14000a1ef  lea     rax, PortDisconnectHandler
0x14000a1f6  mov     [rsp+98h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x14000a1fb  lea     rax, PortConnectHandler
0x14000a202  mov     [rsp+98h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x14000a207  xor     r9d, r9d; ServerPortCookie
0x14000a20a  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x14000a20f  lea     rdx, pServerPort; ServerPort
0x14000a216  mov     rcx, cs:g_pFilter; Filter
0x14000a21d  call    cs:__imp_FltCreateCommunicationPort
0x14000a224  nop     dword ptr [rax+rax+00h]
0x14000a229  mov     ebx, eax
0x14000a22b  mov     [rsp+98h+var_58], eax
0x14000a22f  test    eax, eax
0x14000a231  jns     short loc_14000A242
0x14000a233  lea     rcx, aUevfilterCompo_14; "UevFilter.ComPortCreate: Failed creatin"...
0x14000a23a  mov     edx, eax
0x14000a23c  call    DbgTraceFrmtErr
0x14000a241  nop
0x14000a242  mov     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x14000a24a  test    rcx, rcx
0x14000a24d  jz      short loc_14000A25B
0x14000a24f  call    cs:__imp_FltFreeSecurityDescriptor
0x14000a256  nop     dword ptr [rax+rax+00h]
0x14000a25b  mov     r8d, ebx
0x14000a25e  lea     rdx, aUevfilterCompo_7; "UevFilter.ComPortCreate: Exit, retStatu"...
0x14000a265  mov     ecx, 2
0x14000a26a  call    DbgTraceFrmt
0x14000a26f  mov     eax, ebx
0x14000a271  add     rsp, 90h
0x14000a278  pop     rbx
0x14000a279  retn
0x14000bb09  push    rbp
0x14000bb0b  sub     rsp, 40h
0x14000bb0f  mov     rbp, rdx
0x14000bb12  mov     rcx, [rbp+0A0h]; SecurityDescriptor
0x14000bb19  test    rcx, rcx
0x14000bb1c  jz      short loc_14000BB2B
0x14000bb1e  call    cs:__imp_FltFreeSecurityDescriptor
0x14000bb25  nop     dword ptr [rax+rax+00h]
0x14000bb2a  nop
0x14000bb2b  add     rsp, 40h
0x14000bb2f  pop     rbp
0x14000bb30  retn
```
