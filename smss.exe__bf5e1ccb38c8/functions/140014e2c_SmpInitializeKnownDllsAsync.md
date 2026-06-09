# SmpInitializeKnownDllsAsync

- ea: `0x140014e2c`
- end: `0x140014f22`
- name: `SmpInitializeKnownDllsAsync`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x14000d4c0`
- `0x140014e2c`

## import_xrefs

- `ntdll!NtClose` at `0x140014ef0`
- `ntdll!NtClose` at `0x140014ef0`
- `ntdll!NtSetEvent` at `0x140014ee6`
- `ntdll!NtSetEvent` at `0x140014ee6`
- `ntdll!TpAllocWork` at `0x140014ebb`
- `ntdll!TpAllocWork` at `0x140014ebb`
- `ntdll!TpPostWork` at `0x140014f0a`
- `ntdll!TpPostWork` at `0x140014f0a`
- `ntdll!TpReleaseWork` at `0x140014f14`
- `ntdll!TpReleaseWork` at `0x140014f14`
- `ntdll!NtCreateEvent` at `0x140014e99`
- `ntdll!NtCreateEvent` at `0x140014e99`

## string_xrefs

- `0x140014e39`: `\KnownDlls\SmKnownDllsInitialized`
- `0x140014eca`: `SmpInitializeKnownDllsAsync`

## pseudocode

```c
__int64 SmpInitializeKnownDllsAsync()
{
  NTSTATUS v0; // ebx
  int v1; // eax
  void *v2; // rcx
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF
  __int64 v7; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  v4[1] = L"\\KnownDlls\\SmKnownDllsInitialized";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  *(_QWORD *)&ObjectAttributes.Attributes = 80;
  v4[0] = 4456514;
  v7 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 < 0 )
    goto LABEL_4;
  v1 = TpAllocWork(&v7, &SmpInitializeKnownDllsWorker, EventHandle, &SmpCallbackEnviron);
  v0 = v1;
  if ( v1 < 0 )
  {
    SmpLogFailure("SmpInitializeKnownDllsAsync", 4174, (unsigned int)v1);
LABEL_4:
    v2 = EventHandle;
    goto LABEL_5;
  }
  TpPostWork(v7);
  TpReleaseWork(v7);
  v2 = 0;
  EventHandle = 0;
LABEL_5:
  if ( v2 )
  {
    NtSetEvent(v2, 0);
    NtClose(EventHandle);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140014e2c  mov     [rsp-8+arg_10], rbx
0x140014e31  push    rbp
0x140014e32  mov     rbp, rsp
0x140014e35  sub     rsp, 70h
0x140014e39  lea     rax, aKnowndllsSmkno; "\\KnownDlls\\SmKnownDllsInitialized"
0x140014e40  mov     [rbp+EventHandle], 0
0x140014e48  mov     [rbp+var_38], rax
0x140014e4c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140014e50  lea     rax, [rbp+var_40]
0x140014e54  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140014e5c  xorps   xmm0, xmm0
0x140014e5f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140014e63  xor     r9d, r9d; EventType
0x140014e66  mov     qword ptr [rbp+ObjectAttributes.Attributes], 50h ; 'P'
0x140014e6e  mov     edx, 1F0003h; DesiredAccess
0x140014e73  mov     [rbp+var_40], 440042h
0x140014e7b  lea     rcx, [rbp+EventHandle]; EventHandle
0x140014e7f  mov     [rbp+arg_8], 0
0x140014e87  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140014e8f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140014e94  mov     [rsp+70h+InitialState], 0; InitialState
0x140014e99  call    cs:__imp_NtCreateEvent
0x140014e9f  mov     ebx, eax
0x140014ea1  test    eax, eax
0x140014ea3  js      short loc_140014EDB
0x140014ea5  mov     r8, [rbp+EventHandle]
0x140014ea9  lea     r9, SmpCallbackEnviron
0x140014eb0  lea     rdx, SmpInitializeKnownDllsWorker
0x140014eb7  lea     rcx, [rbp+arg_8]
0x140014ebb  call    cs:__imp_TpAllocWork
0x140014ec1  mov     ebx, eax
0x140014ec3  test    eax, eax
0x140014ec5  jns     short loc_140014F06
0x140014ec7  mov     r8d, eax
0x140014eca  lea     rcx, aSmpinitializek_1; "SmpInitializeKnownDllsAsync"
0x140014ed1  mov     edx, 104Eh
0x140014ed6  call    SmpLogFailure
0x140014edb  mov     rcx, [rbp+EventHandle]; EventHandle
0x140014edf  test    rcx, rcx
0x140014ee2  jz      short loc_140014EF6
0x140014ee4  xor     edx, edx; PreviousState
0x140014ee6  call    cs:__imp_NtSetEvent
0x140014eec  mov     rcx, [rbp+EventHandle]; Handle
0x140014ef0  call    cs:__imp_NtClose
0x140014ef6  mov     eax, ebx
0x140014ef8  mov     rbx, [rsp+70h+arg_10]
0x140014f00  add     rsp, 70h
0x140014f04  pop     rbp
0x140014f05  retn
0x140014f06  mov     rcx, [rbp+arg_8]
0x140014f0a  call    cs:__imp_TpPostWork
0x140014f10  mov     rcx, [rbp+arg_8]
0x140014f14  call    cs:__imp_TpReleaseWork
0x140014f1a  xor     ecx, ecx
0x140014f1c  mov     [rbp+EventHandle], rcx
0x140014f20  jmp     short loc_140014EDF
```
