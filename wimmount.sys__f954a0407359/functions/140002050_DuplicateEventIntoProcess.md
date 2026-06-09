# DuplicateEventIntoProcess

- ea: `0x140002050`
- end: `0x14000215d`
- name: `DuplicateEventIntoProcess`
- size: `269`
- prototype: `__int64 __fastcall(HANDLE TargetProcessHandle, PHANDLE TargetHandle, PVOID *Object)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ab38`

## callees

- `0x140002050`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140002141`
- `ntoskrnl!ZwClose` at `0x140002141`
- `ntoskrnl!ExEventObjectType` at `0x1400020bd`
- `ntoskrnl!ZwCreateEvent` at `0x1400020ab`
- `ntoskrnl!ZwCreateEvent` at `0x1400020ab`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400020dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400020dd`
- `ntoskrnl!ObfDereferenceObject` at `0x140002129`
- `ntoskrnl!ObfDereferenceObject` at `0x140002129`
- `ntoskrnl!ZwDuplicateObject` at `0x14000210f`
- `ntoskrnl!ZwDuplicateObject` at `0x14000210f`

## pseudocode

```c
__int64 __fastcall DuplicateEventIntoProcess(HANDLE TargetProcessHandle, PHANDLE TargetHandle, PVOID *Object)
{
  NTSTATUS v6; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *EventHandle; // [rsp+B8h] [rbp+40h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *TargetHandle = 0;
  *Object = 0;
  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v6 < 0
    || (v6 = ObReferenceObjectByHandle(EventHandle, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 0, Object, 0), v6 < 0)
    || (v6 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, EventHandle, TargetProcessHandle, TargetHandle, 0, 0, 6u),
        v6 < 0) )
  {
    if ( *Object )
    {
      ObfDereferenceObject(*Object);
      *Object = 0;
    }
  }
  if ( EventHandle )
    ZwClose(EventHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140002050  push    rbp
0x140002052  push    rbx
0x140002053  push    rsi
0x140002054  push    rdi
0x140002055  push    r14
0x140002057  push    r15
0x140002059  mov     rbp, rsp
0x14000205c  sub     rsp, 78h
0x140002060  xor     r15d, r15d
0x140002063  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000206b  mov     [rdx], r15
0x14000206e  mov     rdi, r8
0x140002071  mov     [r8], r15
0x140002074  mov     rsi, rdx
0x140002077  mov     r14, rcx
0x14000207a  mov     [rbp+EventHandle], r15
0x14000207e  xorps   xmm0, xmm0
0x140002081  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x140002089  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000208d  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x140002091  xor     r9d, r9d; EventType
0x140002094  mov     [rbp+ObjectAttributes.ObjectName], r15
0x140002098  mov     edx, 1F0003h; DesiredAccess
0x14000209d  mov     [rsp+78h+InitialState], r15b; InitialState
0x1400020a2  lea     rcx, [rbp+EventHandle]; EventHandle
0x1400020a6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400020ab  call    cs:__imp_ZwCreateEvent
0x1400020b2  nop     dword ptr [rax+rax+00h]
0x1400020b7  mov     ebx, eax
0x1400020b9  test    eax, eax
0x1400020bb  js      short loc_140002121
0x1400020bd  mov     r8, cs:ExEventObjectType
0x1400020c4  xor     r9d, r9d; AccessMode
0x1400020c7  mov     rcx, [rbp+EventHandle]; Handle
0x1400020cb  mov     edx, 1F0003h; DesiredAccess
0x1400020d0  mov     [rsp+78h+HandleInformation], r15; HandleInformation
0x1400020d5  mov     qword ptr [rsp+78h+InitialState], rdi; Object
0x1400020da  mov     r8, [r8]; ObjectType
0x1400020dd  call    cs:__imp_ObReferenceObjectByHandle
0x1400020e4  nop     dword ptr [rax+rax+00h]
0x1400020e9  mov     ebx, eax
0x1400020eb  test    eax, eax
0x1400020ed  js      short loc_140002121
0x1400020ef  mov     rdx, [rbp+EventHandle]; SourceHandle
0x1400020f3  mov     r9, rsi; TargetHandle
0x1400020f6  mov     [rsp+78h+Options], 6; Options
0x1400020fe  mov     r8, r14; TargetProcessHandle
0x140002101  mov     dword ptr [rsp+78h+HandleInformation], r15d; HandleAttributes
0x140002106  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000210a  mov     dword ptr [rsp+78h+InitialState], r15d; DesiredAccess
0x14000210f  call    cs:__imp_ZwDuplicateObject
0x140002116  nop     dword ptr [rax+rax+00h]
0x14000211b  mov     ebx, eax
0x14000211d  test    eax, eax
0x14000211f  jns     short loc_140002138
0x140002121  mov     rcx, [rdi]; Object
0x140002124  test    rcx, rcx
0x140002127  jz      short loc_140002138
0x140002129  call    cs:__imp_ObfDereferenceObject
0x140002130  nop     dword ptr [rax+rax+00h]
0x140002135  mov     [rdi], r15
0x140002138  mov     rcx, [rbp+EventHandle]; Handle
0x14000213c  test    rcx, rcx
0x14000213f  jz      short loc_14000214D
0x140002141  call    cs:__imp_ZwClose
0x140002148  nop     dword ptr [rax+rax+00h]
0x14000214d  mov     eax, ebx
0x14000214f  add     rsp, 78h
0x140002153  pop     r15
0x140002155  pop     r14
0x140002157  pop     rdi
0x140002158  pop     rsi
0x140002159  pop     rbx
0x14000215a  pop     rbp
0x14000215b  retn
```
