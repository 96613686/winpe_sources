# IsSPMgrReady

- ea: `0x18000860c`
- end: `0x18000872a`
- name: `IsSPMgrReady`
- size: `286`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800084f0`

## callees

- `0x18000860c`
- `0x18001fc24`

## import_xrefs

- `ntdll!NtClose` at `0x1800086e4`
- `ntdll!NtClose` at `0x1800086e4`
- `ntdll!RtlInitUnicodeString` at `0x180008647`
- `ntdll!RtlInitUnicodeString` at `0x180008647`
- `ntdll!NtQueryEvent` at `0x1800086d8`
- `ntdll!NtQueryEvent` at `0x1800086d8`
- `ntdll!NtOpenEvent` at `0x180008680`
- `ntdll!NtOpenEvent` at `0x180008680`

## string_xrefs

- `0x180008624`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
__int64 IsSPMgrReady()
{
  NTSTATUS v0; // ebx
  int v1; // r8d
  _QWORD *v2; // rcx
  int v3; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  HANDLE EventHandle; // [rsp+80h] [rbp+10h] BYREF
  __int64 EventInformation; // [rsp+88h] [rbp+18h] BYREF

  EventInformation = 0;
  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, szLsaEvent);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 1u, &ObjectAttributes);
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v0;
    v3 = 10;
LABEL_5:
    WPP_SF_SD(v2[2], v3, v1, DestinationString.Buffer, v0);
    return (unsigned int)v0;
  }
  v0 = NtQueryEvent(EventHandle, EventBasicInformation, &EventInformation, 8u, 0);
  NtClose(EventHandle);
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v0;
    v3 = 11;
    goto LABEL_5;
  }
  return HIDWORD(EventInformation) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x18000860c  mov     [rsp-8+arg_10], rbx
0x180008611  push    rbp
0x180008612  mov     rbp, rsp
0x180008615  sub     rsp, 70h
0x180008619  xorps   xmm0, xmm0
0x18000861c  mov     [rbp+EventInformation], 0
0x180008624  lea     rdx, ?szLsaEvent@@3PAGA; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x18000862b  mov     [rbp+EventHandle], 0
0x180008633  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008637  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000863b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000863f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008643  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180008647  call    cs:__imp_RtlInitUnicodeString
0x18000864d  lea     rax, [rbp+DestinationString]
0x180008651  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180008658  xorps   xmm0, xmm0
0x18000865b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000865f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008663  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000866b  mov     edx, 1; DesiredAccess
0x180008670  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180008677  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000867b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008680  call    cs:__imp_NtOpenEvent
0x180008686  mov     ebx, eax
0x180008688  test    eax, eax
0x18000868a  jns     short loc_1800086BF
0x18000868c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008693  lea     rdx, WPP_GLOBAL_Control
0x18000869a  cmp     rcx, rdx
0x18000869d  jz      short loc_1800086BB
0x18000869f  test    byte ptr [rcx+1Ch], 1
0x1800086a3  jz      short loc_1800086BB
0x1800086a5  mov     edx, 0Ah
0x1800086aa  mov     r9, [rbp+DestinationString.Buffer]
0x1800086ae  mov     rcx, [rcx+10h]
0x1800086b2  mov     dword ptr [rsp+70h+ReturnLength], ebx
0x1800086b6  call    WPP_SF_SD
0x1800086bb  mov     eax, ebx
0x1800086bd  jmp     short loc_18000871C
0x1800086bf  mov     rcx, [rbp+EventHandle]; EventHandle
0x1800086c3  lea     r8, [rbp+EventInformation]; EventInformation
0x1800086c7  mov     r9d, 8; EventInformationLength
0x1800086cd  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1800086d6  xor     edx, edx; EventInformationClass
0x1800086d8  call    cs:__imp_NtQueryEvent
0x1800086de  mov     rcx, [rbp+EventHandle]; Handle
0x1800086e2  mov     ebx, eax
0x1800086e4  call    cs:__imp_NtClose
0x1800086ea  test    ebx, ebx
0x1800086ec  jns     short loc_18000870E
0x1800086ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086f5  lea     rdx, WPP_GLOBAL_Control
0x1800086fc  cmp     rcx, rdx
0x1800086ff  jz      short loc_1800086BB
0x180008701  test    byte ptr [rcx+1Ch], 1
0x180008705  jz      short loc_1800086BB
0x180008707  mov     edx, 0Bh
0x18000870c  jmp     short loc_1800086AA
0x18000870e  mov     eax, dword ptr [rbp+EventInformation+4]
0x180008711  neg     eax
0x180008713  sbb     eax, eax
0x180008715  not     eax
0x180008717  and     eax, 0C0000001h
0x18000871c  mov     rbx, [rsp+70h+arg_10]
0x180008724  add     rsp, 70h
0x180008728  pop     rbp
0x180008729  retn
```
