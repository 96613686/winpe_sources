# CreateProcessEventCompletionPort

- ea: `0x14000c078`
- end: `0x14000c1b3`
- name: `CreateProcessEventCompletionPort`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c55c`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000164c`
- `0x14000c078`
- `0x14000c1bc`
- `0x14000c4a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000c0e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c0e5`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000c15a`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000c15a`

## string_xrefs

- `0x14000c08d`: `UevFilter.CreateProcessEventCompletionPort: Entry\n`
- `0x14000c0b9`: `UevFilter.CreateProcessEventCompletionPort: Failed building security descriptor. Error = 0x%0X.\n`
- `0x14000c16c`: `UevFilter.CreateProcessEventCompletionPort: Failed creating communication port. Error = 0x%0X.\n`
- `0x14000c18a`: `UevFilter.CreateProcessEventCompletionPort: Exit. Error = 0x%0X.\n`

## pseudocode

```c
__int64 CreateProcessEventCompletionPort()
{
  int CompletionPortSecurityDescriptor; // eax
  PVOID v1; // rdi
  NTSTATUS v2; // ebx
  char *v3; // rcx
  LONG MaxConnections; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID P; // [rsp+90h] [rbp+10h] BYREF

  P = 0;
  DbgTrace(2, "UevFilter.CreateProcessEventCompletionPort: Entry\n");
  CompletionPortSecurityDescriptor = GetCompletionPortSecurityDescriptor(&P);
  v1 = P;
  v2 = CompletionPortSecurityDescriptor;
  if ( CompletionPortSecurityDescriptor >= 0 )
  {
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\UevProcessEventPort");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityDescriptor = v1;
    ObjectAttributes.SecurityQualityOfService = 0;
    MaxConnections = GetMaxConnections();
    v2 = FltCreateCommunicationPort(
           g_pFilter,
           &ServerPort,
           &ObjectAttributes,
           0,
           PortConnectHandler_0,
           PortDisconnectHandler_0,
           0,
           MaxConnections);
    if ( v2 >= 0 )
      goto LABEL_6;
    v3 = "UevFilter.CreateProcessEventCompletionPort: Failed creating communication port. Error = 0x%0X.\n";
  }
  else
  {
    v3 = "UevFilter.CreateProcessEventCompletionPort: Failed building security descriptor. Error = 0x%0X.\n";
  }
  DbgTraceFrmtErr(v3);
LABEL_6:
  if ( v1 )
    FreeGenericBuffer(v1);
  DbgTraceFrmt(2, "UevFilter.CreateProcessEventCompletionPort: Exit. Error = 0x%0X.\n", v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000c078  mov     [rsp-8+arg_8], rbx
0x14000c07d  mov     [rsp-8+arg_10], rdi
0x14000c082  push    rbp
0x14000c083  mov     rbp, rsp
0x14000c086  sub     rsp, 80h
0x14000c08d  lea     rdx, aUevfilterCreat_2; "UevFilter.CreateProcessEventCompletionP"...
0x14000c094  mov     [rbp+P], 0
0x14000c09c  mov     ecx, 2
0x14000c0a1  call    DbgTrace
0x14000c0a6  lea     rcx, [rbp+P]
0x14000c0aa  call    GetCompletionPortSecurityDescriptor
0x14000c0af  mov     rdi, [rbp+P]
0x14000c0b3  mov     ebx, eax
0x14000c0b5  test    eax, eax
0x14000c0b7  jns     short loc_14000C0C5
0x14000c0b9  lea     rcx, aUevfilterCreat_0; "UevFilter.CreateProcessEventCompletionP"...
0x14000c0c0  jmp     loc_14000C173
0x14000c0c5  xorps   xmm0, xmm0
0x14000c0c8  lea     rdx, aUevprocesseven; "\\UevProcessEventPort"
0x14000c0cf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000c0d3  xor     eax, eax
0x14000c0d5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c0d9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000c0dd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000c0e1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000c0e5  call    cs:__imp_RtlInitUnicodeString
0x14000c0ec  nop     dword ptr [rax+rax+00h]
0x14000c0f1  lea     rax, [rbp+DestinationString]
0x14000c0f5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000c0fc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000c100  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000c108  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000c10f  mov     [rbp+ObjectAttributes.SecurityDescriptor], rdi
0x14000c113  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x14000c11b  call    GetMaxConnections
0x14000c120  mov     rcx, cs:g_pFilter; Filter
0x14000c127  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000c12b  mov     [rsp+80h+MaxConnections], eax; MaxConnections
0x14000c12f  lea     rdx, ServerPort; ServerPort
0x14000c136  lea     rax, PortDisconnectHandler_0
0x14000c13d  mov     [rsp+80h+MessageNotifyCallback], 0; MessageNotifyCallback
0x14000c146  mov     [rsp+80h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x14000c14b  xor     r9d, r9d; ServerPortCookie
0x14000c14e  lea     rax, PortConnectHandler_0
0x14000c155  mov     [rsp+80h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x14000c15a  call    cs:__imp_FltCreateCommunicationPort
0x14000c161  nop     dword ptr [rax+rax+00h]
0x14000c166  mov     ebx, eax
0x14000c168  test    eax, eax
0x14000c16a  jns     short loc_14000C17A
0x14000c16c  lea     rcx, aUevfilterCreat_1; "UevFilter.CreateProcessEventCompletionP"...
0x14000c173  mov     edx, eax
0x14000c175  call    DbgTraceFrmtErr
0x14000c17a  test    rdi, rdi
0x14000c17d  jz      short loc_14000C187
0x14000c17f  mov     rcx, rdi; P
0x14000c182  call    FreeGenericBuffer
0x14000c187  mov     r8d, ebx
0x14000c18a  lea     rdx, aUevfilterCreat; "UevFilter.CreateProcessEventCompletionP"...
0x14000c191  mov     ecx, 2
0x14000c196  call    DbgTraceFrmt
0x14000c19b  lea     r11, [rsp+80h+var_s0]
0x14000c1a3  mov     eax, ebx
0x14000c1a5  mov     rbx, [r11+18h]
0x14000c1a9  mov     rdi, [r11+20h]
0x14000c1ad  mov     rsp, r11
0x14000c1b0  pop     rbp
0x14000c1b1  retn
```
