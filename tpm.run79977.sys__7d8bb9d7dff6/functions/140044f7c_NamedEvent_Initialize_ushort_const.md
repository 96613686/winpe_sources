# NamedEvent::Initialize(ushort const *)

- ea: `0x140044f7c`
- end: `0x140045068`
- name: `?Initialize@NamedEvent@@QEAAJPEBG@Z`
- size: `236`
- prototype: `__int64 __fastcall(NamedEvent *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140005370`

## callees

- `0x140044f7c`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x140044fef`
- `ntoskrnl!ZwOpenEvent` at `0x140044fef`
- `ntoskrnl!ZwClose` at `0x140045047`
- `ntoskrnl!ZwClose` at `0x140045047`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140045029`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140045029`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044fb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044fb0`

## pseudocode

```c
__int64 __fastcall NamedEvent::Initialize(NamedEvent *this, const unsigned __int16 *a2)
{
  NTSTATUS v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+20h] BYREF
  PVOID Object; // [rsp+98h] [rbp+28h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenEvent(&EventHandle, 1u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    Object = 0;
    v3 = ObReferenceObjectByHandle(EventHandle, 1u, 0, 0, &Object, 0);
    *(_QWORD *)this = Object;
  }
  if ( EventHandle )
    ZwClose(EventHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140044f7c  mov     [rsp-8+arg_0], rbx
0x140044f81  mov     [rsp-8+arg_8], rdi
0x140044f86  push    rbp
0x140044f87  mov     rbp, rsp
0x140044f8a  sub     rsp, 70h
0x140044f8e  xorps   xmm0, xmm0
0x140044f91  mov     [rbp+EventHandle], 0
0x140044f99  mov     rdi, rcx
0x140044f9c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044fa0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140044fa4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140044fa8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140044fac  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140044fb0  call    cs:__imp_RtlInitUnicodeString
0x140044fb7  nop     dword ptr [rax+rax+00h]
0x140044fbc  lea     rax, [rbp+DestinationString]
0x140044fc0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140044fc7  xorps   xmm0, xmm0
0x140044fca  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140044fce  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140044fd2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140044fda  mov     edx, 1; DesiredAccess
0x140044fdf  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140044fe6  lea     rcx, [rbp+EventHandle]; EventHandle
0x140044fea  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140044fef  call    cs:__imp_ZwOpenEvent
0x140044ff6  nop     dword ptr [rax+rax+00h]
0x140044ffb  mov     ebx, eax
0x140044ffd  test    eax, eax
0x140044fff  js      short loc_14004503E
0x140045001  mov     rcx, [rbp+EventHandle]; Handle
0x140045005  lea     rax, [rbp+arg_18]
0x140045009  xor     r9d, r9d; AccessMode
0x14004500c  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x140045015  xor     r8d, r8d; ObjectType
0x140045018  mov     [rbp+arg_18], 0
0x140045020  mov     [rsp+70h+Object], rax; Object
0x140045025  lea     edx, [r9+1]; DesiredAccess
0x140045029  call    cs:__imp_ObReferenceObjectByHandle
0x140045030  nop     dword ptr [rax+rax+00h]
0x140045035  mov     ebx, eax
0x140045037  mov     rax, [rbp+arg_18]
0x14004503b  mov     [rdi], rax
0x14004503e  mov     rcx, [rbp+EventHandle]; Handle
0x140045042  test    rcx, rcx
0x140045045  jz      short loc_140045053
0x140045047  call    cs:__imp_ZwClose
0x14004504e  nop     dword ptr [rax+rax+00h]
0x140045053  lea     r11, [rsp+70h+var_s0]
0x140045058  mov     eax, ebx
0x14004505a  mov     rbx, [r11+10h]
0x14004505e  mov     rdi, [r11+18h]
0x140045062  mov     rsp, r11
0x140045065  pop     rbp
0x140045066  retn
```
