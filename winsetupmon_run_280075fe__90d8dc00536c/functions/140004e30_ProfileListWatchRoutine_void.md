# ProfileListWatchRoutine(void *)

- ea: `0x140004e30`
- end: `0x14000515b`
- name: `?ProfileListWatchRoutine@@YAXPEAX@Z`
- size: `811`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140003944`
- `0x140004908`
- `0x140004e30`
- `0x140005164`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x140005062`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140005062`
- `ntoskrnl!ZwOpenKey` at `0x140004ec5`
- `ntoskrnl!ZwOpenKey` at `0x140004ec5`
- `ntoskrnl!ZwCreateEvent` at `0x140004f47`
- `ntoskrnl!ZwCreateEvent` at `0x140004f47`
- `ntoskrnl!ExEventObjectType` at `0x140004f69`
- `ntoskrnl!KeResetEvent` at `0x140004fba`
- `ntoskrnl!KeResetEvent` at `0x140004fba`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140004ff8`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140004ff8`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000512a`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000512a`
- `ntoskrnl!ZwClose` at `0x140005106`
- `ntoskrnl!ZwClose` at `0x14000511b`
- `ntoskrnl!ZwClose` at `0x140005106`
- `ntoskrnl!ZwClose` at `0x14000511b`
- `ntoskrnl!KeSetEvent` at `0x140005020`
- `ntoskrnl!KeSetEvent` at `0x140005020`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004f8a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004f8a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400050f1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400050f1`

## string_xrefs

- `0x140004e50`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x140004e8b`: `Could not initialize well known SIDs (0x%08X)`
- `0x140004ee3`: `Could not open key %wZ (0x%08X)`
- `0x140004f5d`: `Could not create key change notification event (0x%08X)`
- `0x1400050d5`: `Could not create notification for key change on ProfileList key (0x%08X)`
- `0x14000513d`: `Could not terminate profile list watch thread (0x%08X)`

## pseudocode

```c
void __fastcall ProfileListWatchRoutine(unsigned int *StartContext)
{
  char v2; // cl
  char v3; // di
  unsigned int v4; // ecx
  NTSTATUS v5; // eax
  _QWORD v6[2]; // [rsp+50h] [rbp-29h] BYREF
  PVOID v7[2]; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  void *KeyHandle; // [rsp+E0h] [rbp+67h] BYREF
  PVOID Object; // [rsp+E8h] [rbp+6Fh] BYREF
  void *EventHandle; // [rsp+F0h] [rbp+77h] BYREF

  v6[0] = 9830548;
  v6[1] = L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  v2 = *(_BYTE *)StartContext;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  EventHandle = 0;
  Object = 0;
  StartContext[14] = GetWellKnownSids(v2);
  if ( (StartContext[14] & 0x80000000) == 0 )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    StartContext[14] = ZwOpenKey(&KeyHandle, 0x18u, &ObjectAttributes);
    if ( (StartContext[14] & 0x80000000) == 0 )
    {
      StartContext[14] = RefreshUserNames(KeyHandle);
      if ( (StartContext[14] & 0x80000000) == 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        StartContext[14] = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
        if ( (StartContext[14] & 0x80000000) == 0 )
        {
          StartContext[14] = ObReferenceObjectByHandle(
                               EventHandle,
                               0x1F0003u,
                               (POBJECT_TYPE)ExEventObjectType,
                               0,
                               &Object,
                               0);
          if ( (StartContext[14] & 0x80000000) == 0 )
          {
            v3 = 0;
            while ( 1 )
            {
              IoStatusBlock = 0;
              KeResetEvent((PRKEVENT)Object);
              StartContext[14] = ZwNotifyChangeKey(KeyHandle, EventHandle, 0, 0, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
              if ( (StartContext[14] & 0x80000000) != 0 )
              {
                WriteLogMessage(
                  3,
                  L"Could not create notification for key change on ProfileList key (0x%08X)",
                  StartContext[14]);
                goto LABEL_25;
              }
              if ( !v3 )
              {
                KeSetEvent((PRKEVENT)(StartContext + 2), 0, 0);
                v3 = 1;
              }
              v7[0] = StartContext + 8;
              v7[1] = Object;
              StartContext[14] = KeWaitForMultipleObjects(2u, v7, WaitAny, Executive, 0, 0, 0, 0);
              if ( (StartContext[14] & 0x80000000) != 0 )
              {
                WriteLogMessage(3, L"Could not wait for multiple events notification (0x%08X)", StartContext[14]);
                goto LABEL_25;
              }
              v4 = StartContext[14];
              if ( !v4 )
              {
                StartContext[14] = 0;
                goto LABEL_25;
              }
              if ( v4 != 1 )
                break;
              StartContext[14] = RefreshUserNames(KeyHandle);
              if ( (StartContext[14] & 0x80000000) != 0 )
              {
                WriteLogMessage(3, L"Could not refresh user names (0x%08X)", StartContext[14]);
                goto LABEL_25;
              }
            }
            WriteLogMessage(3, L"Unexpected wait status; exiting (0x%08X)", StartContext[14]);
            if ( (StartContext[14] & 0x80000000) == 0 )
              StartContext[14] = -1073741823;
          }
          else
          {
            WriteLogMessage(3, L"Could not reference notification event object by handle (0x%08X)", StartContext[14]);
          }
        }
        else
        {
          WriteLogMessage(3, L"Could not create key change notification event (0x%08X)", StartContext[14]);
        }
      }
      else
      {
        WriteLogMessage(3, L"Could not initialize user names (0x%08X)", StartContext[14]);
      }
    }
    else
    {
      WriteLogMessage(3, L"Could not open key %wZ (0x%08X)", v6, StartContext[14]);
    }
  }
  else
  {
    WriteLogMessage(3, L"Could not initialize well known SIDs (0x%08X)", StartContext[14]);
  }
LABEL_25:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( EventHandle )
    ZwClose(EventHandle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  v5 = PsTerminateSystemThread(StartContext[14]);
  if ( v5 < 0 )
    WriteLogMessage(3, L"Could not terminate profile list watch thread (0x%08X)", (unsigned int)v5);
}

```

## disassembly

```asm
0x140004e30  push    rbp
0x140004e32  push    rbx
0x140004e33  push    rsi
0x140004e34  push    rdi
0x140004e35  push    r14
0x140004e37  lea     rbp, [rsp-37h]
0x140004e3c  sub     rsp, 0B0h
0x140004e43  xorps   xmm0, xmm0
0x140004e46  mov     [rbp+57h+var_80], 960094h
0x140004e4e  xor     esi, esi
0x140004e50  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x140004e57  mov     rbx, rcx
0x140004e5a  mov     [rbp+57h+var_78], rax
0x140004e5e  mov     cl, [rcx]; unsigned __int8
0x140004e60  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140004e64  mov     [rbp+57h+KeyHandle], rsi
0x140004e68  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140004e6c  mov     [rbp+57h+EventHandle], rsi
0x140004e70  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140004e74  mov     [rbp+57h+Object], rsi
0x140004e78  call    ?GetWellKnownSids@@YAJE@Z; GetWellKnownSids(uchar)
0x140004e7d  mov     [rbx+38h], eax
0x140004e80  lea     r14d, [rsi+3]
0x140004e84  mov     eax, [rbx+38h]
0x140004e87  test    eax, eax
0x140004e89  jns     short loc_140004E97
0x140004e8b  lea     rdx, aCouldNotInitia_0; "Could not initialize well known SIDs (0"...
0x140004e92  jmp     loc_1400050DC
0x140004e97  mov     edi, 30h ; '0'
0x140004e9c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140004ea0  lea     rax, [rbp+57h+var_80]
0x140004ea4  mov     [rbp+57h+ObjectAttributes.Length], edi
0x140004ea7  xorps   xmm0, xmm0
0x140004eaa  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140004eb1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140004eb5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140004eb9  lea     edx, [rdi-18h]; DesiredAccess
0x140004ebc  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140004ec0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140004ec5  call    cs:__imp_ZwOpenKey
0x140004ecc  nop     dword ptr [rax+rax+00h]
0x140004ed1  mov     [rbx+38h], eax
0x140004ed4  mov     eax, [rbx+38h]
0x140004ed7  test    eax, eax
0x140004ed9  jns     short loc_140004EF7
0x140004edb  mov     r9d, [rbx+38h]
0x140004edf  lea     r8, [rbp+57h+var_80]
0x140004ee3  lea     rdx, aCouldNotOpenKe; "Could not open key %wZ (0x%08X)"
0x140004eea  mov     ecx, r14d
0x140004eed  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004ef2  jmp     loc_1400050E8
0x140004ef7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140004efb  call    ?RefreshUserNames@@YAJPEAX@Z; RefreshUserNames(void *)
0x140004f00  mov     [rbx+38h], eax
0x140004f03  mov     eax, [rbx+38h]
0x140004f06  test    eax, eax
0x140004f08  jns     short loc_140004F16
0x140004f0a  lea     rdx, aCouldNotInitia; "Could not initialize user names (0x%08X"...
0x140004f11  jmp     loc_1400050DC
0x140004f16  mov     [rbp+57h+ObjectAttributes.Length], edi
0x140004f19  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140004f1d  xorps   xmm0, xmm0
0x140004f20  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140004f24  mov     edi, 1F0003h
0x140004f29  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140004f30  mov     edx, edi; DesiredAccess
0x140004f32  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x140004f36  xor     r9d, r9d; EventType
0x140004f39  mov     [rsp+0D0h+InitialState], sil; InitialState
0x140004f3e  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140004f42  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140004f47  call    cs:__imp_ZwCreateEvent
0x140004f4e  nop     dword ptr [rax+rax+00h]
0x140004f53  mov     [rbx+38h], eax
0x140004f56  mov     eax, [rbx+38h]
0x140004f59  test    eax, eax
0x140004f5b  jns     short loc_140004F69
0x140004f5d  lea     rdx, aCouldNotCreate_1; "Could not create key change notificatio"...
0x140004f64  jmp     loc_1400050DC
0x140004f69  mov     r8, cs:ExEventObjectType
0x140004f70  lea     rax, [rbp+57h+Object]
0x140004f74  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140004f78  xor     r9d, r9d; AccessMode
0x140004f7b  mov     [rsp+0D0h+HandleInformation], rsi; HandleInformation
0x140004f80  mov     edx, edi; DesiredAccess
0x140004f82  mov     qword ptr [rsp+0D0h+InitialState], rax; Object
0x140004f87  mov     r8, [r8]; ObjectType
0x140004f8a  call    cs:__imp_ObReferenceObjectByHandle
0x140004f91  nop     dword ptr [rax+rax+00h]
0x140004f96  mov     [rbx+38h], eax
0x140004f99  mov     eax, [rbx+38h]
0x140004f9c  test    eax, eax
0x140004f9e  jns     short loc_140004FAC
0x140004fa0  lea     rdx, aCouldNotRefere_0; "Could not reference notification event "...
0x140004fa7  jmp     loc_1400050DC
0x140004fac  mov     dil, sil
0x140004faf  mov     rcx, [rbp+57h+Object]; Event
0x140004fb3  xorps   xmm0, xmm0
0x140004fb6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140004fba  call    cs:__imp_KeResetEvent
0x140004fc1  nop     dword ptr [rax+rax+00h]
0x140004fc6  mov     rdx, [rbp+57h+EventHandle]; Event
0x140004fca  lea     rax, [rbp+57h+IoStatusBlock]
0x140004fce  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140004fd2  xor     r9d, r9d; ApcContext
0x140004fd5  mov     [rsp+0D0h+Asynchronous], 1; Asynchronous
0x140004fda  xor     r8d, r8d; ApcRoutine
0x140004fdd  mov     [rsp+0D0h+BufferSize], esi; BufferSize
0x140004fe1  mov     [rsp+0D0h+Buffer], rsi; Buffer
0x140004fe6  mov     [rsp+0D0h+WatchTree], 1; WatchTree
0x140004feb  mov     dword ptr [rsp+0D0h+HandleInformation], 5; CompletionFilter
0x140004ff3  mov     qword ptr [rsp+0D0h+InitialState], rax; IoStatusBlock
0x140004ff8  call    cs:__imp_ZwNotifyChangeKey
0x140004fff  nop     dword ptr [rax+rax+00h]
0x140005004  mov     [rbx+38h], eax
0x140005007  mov     eax, [rbx+38h]
0x14000500a  test    eax, eax
0x14000500c  js      loc_1400050D5
0x140005012  test    dil, dil
0x140005015  jnz     short loc_14000502F
0x140005017  lea     rcx, [rbx+8]; Event
0x14000501b  xor     r8d, r8d; Wait
0x14000501e  xor     edx, edx; Increment
0x140005020  call    cs:__imp_KeSetEvent
0x140005027  nop     dword ptr [rax+rax+00h]
0x14000502c  mov     dil, 1
0x14000502f  xor     r9d, r9d; WaitReason
0x140005032  mov     [rsp+0D0h+Buffer], rsi; WaitBlockArray
0x140005037  lea     rax, [rbx+20h]
0x14000503b  mov     qword ptr [rsp+0D0h+WatchTree], rsi; Timeout
0x140005040  mov     [rbp+57h+var_70], rax
0x140005044  lea     rdx, [rbp+57h+var_70]; Object
0x140005048  mov     rax, [rbp+57h+Object]
0x14000504c  lea     r8d, [r9+1]; WaitType
0x140005050  mov     byte ptr [rsp+0D0h+HandleInformation], sil; Alertable
0x140005055  lea     ecx, [r9+2]; Count
0x140005059  mov     [rbp+57h+var_68], rax
0x14000505d  mov     [rsp+0D0h+InitialState], sil; WaitMode
0x140005062  call    cs:__imp_KeWaitForMultipleObjects
0x140005069  nop     dword ptr [rax+rax+00h]
0x14000506e  mov     [rbx+38h], eax
0x140005071  mov     eax, [rbx+38h]
0x140005074  test    eax, eax
0x140005076  js      short loc_1400050CC
0x140005078  mov     ecx, [rbx+38h]
0x14000507b  test    ecx, ecx
0x14000507d  jz      short loc_1400050C7
0x14000507f  cmp     ecx, 1
0x140005082  jnz     short loc_1400050A4
0x140005084  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140005088  call    ?RefreshUserNames@@YAJPEAX@Z; RefreshUserNames(void *)
0x14000508d  mov     [rbx+38h], eax
0x140005090  mov     eax, [rbx+38h]
0x140005093  test    eax, eax
0x140005095  jns     loc_140004FAF
0x14000509b  lea     rdx, aCouldNotRefres; "Could not refresh user names (0x%08X)"
0x1400050a2  jmp     short loc_1400050DC
0x1400050a4  mov     r8d, [rbx+38h]
0x1400050a8  lea     rdx, aUnexpectedWait; "Unexpected wait status; exiting (0x%08X"...
0x1400050af  mov     ecx, r14d
0x1400050b2  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400050b7  mov     eax, [rbx+38h]
0x1400050ba  test    eax, eax
0x1400050bc  js      short loc_1400050E8
0x1400050be  mov     dword ptr [rbx+38h], 0C0000001h
0x1400050c5  jmp     short loc_1400050E8
0x1400050c7  mov     [rbx+38h], esi
0x1400050ca  jmp     short loc_1400050E8
0x1400050cc  lea     rdx, aCouldNotWaitFo; "Could not wait for multiple events noti"...
0x1400050d3  jmp     short loc_1400050DC
0x1400050d5  lea     rdx, aCouldNotCreate; "Could not create notification for key c"...
0x1400050dc  mov     r8d, [rbx+38h]
0x1400050e0  mov     ecx, r14d
0x1400050e3  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400050e8  mov     rcx, [rbp+57h+Object]; Object
0x1400050ec  test    rcx, rcx
0x1400050ef  jz      short loc_1400050FD
0x1400050f1  call    cs:__imp_ObfDereferenceObject
0x1400050f8  nop     dword ptr [rax+rax+00h]
0x1400050fd  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140005101  test    rcx, rcx
0x140005104  jz      short loc_140005112
0x140005106  call    cs:__imp_ZwClose
0x14000510d  nop     dword ptr [rax+rax+00h]
0x140005112  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140005116  test    rcx, rcx
0x140005119  jz      short loc_140005127
0x14000511b  call    cs:__imp_ZwClose
0x140005122  nop     dword ptr [rax+rax+00h]
0x140005127  mov     ecx, [rbx+38h]; ExitStatus
0x14000512a  call    cs:__imp_PsTerminateSystemThread
0x140005131  nop     dword ptr [rax+rax+00h]
0x140005136  test    eax, eax
0x140005138  jns     short loc_14000514C
0x14000513a  mov     r8d, eax
0x14000513d  lea     rdx, aCouldNotTermin; "Could not terminate profile list watch "...
0x140005144  mov     ecx, r14d
0x140005147  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000514c  add     rsp, 0B0h
0x140005153  pop     r14
0x140005155  pop     rdi
0x140005156  pop     rsi
0x140005157  pop     rbx
0x140005158  pop     rbp
0x140005159  retn
```
