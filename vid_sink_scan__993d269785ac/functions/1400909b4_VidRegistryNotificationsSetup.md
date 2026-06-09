# VidRegistryNotificationsSetup

- ea: `0x1400909b4`
- end: `0x140090b05`
- name: `VidRegistryNotificationsSetup`
- size: `337`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140082678`

## callees

- `0x1400217a0`
- `0x140021800`
- `0x14002f524`
- `0x1400909b4`
- `0x140090ef4`
- `0x1400f5c00`
- `0x1400faa18`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x140090a14`
- `ntoskrnl!ZwCreateEvent` at `0x140090a4d`
- `ntoskrnl!ZwCreateEvent` at `0x140090a14`
- `ntoskrnl!ZwCreateEvent` at `0x140090a4d`

## string_xrefs

- `0x140090ae1`: `onecore\vm\vid\sys\driver\vidregistry.c`
- `0x140090ae8`: `VidRegistryNotificationsSetup`

## pseudocode

```c
__int64 VidRegistryNotificationsSetup()
{
  NTSTATUS v0; // ebx
  __int64 v1; // r8
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  memset(&gVidRegistryContext, 0, 0xA8u);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 < 0 )
  {
    v1 = 439;
LABEL_9:
    VidTraceErrorStatusInternal0("VidRegistryNotificationsSetup", "onecore\\vm\\vid\\sys\\driver\\vidregistry.c", v1);
    VidRegistrypNotificationsTeardownInternal();
    return (unsigned int)v0;
  }
  v0 = ZwCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( v0 < 0 )
  {
    v1 = 452;
    goto LABEL_9;
  }
  v0 = VidRegistryOpenParametersKey(&qword_1400643B8);
  if ( v0 < 0 )
  {
    v1 = 459;
    goto LABEL_9;
  }
  KeyHandle = (HANDLE)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1856))(
                        WdfDriverGlobals,
                        qword_1400643B8);
  qword_140064330 = 0;
  v0 = VidThreadCreate(VidRegistrypNotificationRoutine, 0, 0, &gVidRegistryContext, 0);
  if ( v0 < 0 )
  {
    v1 = 478;
    goto LABEL_9;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400909b4  push    rbx
0x1400909b6  sub     rsp, 60h
0x1400909ba  xor     edx, edx; Val
0x1400909bc  mov     qword ptr [rsp+68h+ObjectAttributes.Length], 30h ; '0'
0x1400909c5  mov     r8d, 0A8h; Size
0x1400909cb  mov     qword ptr [rsp+68h+ObjectAttributes.Attributes], 200h
0x1400909d4  lea     rcx, gVidRegistryContext; void *
0x1400909db  call    memset
0x1400909e0  xorps   xmm0, xmm0
0x1400909e3  mov     [rsp+68h+ObjectAttributes.RootDirectory], 0
0x1400909ec  xor     r9d, r9d; EventType
0x1400909ef  mov     [rsp+68h+ObjectAttributes.ObjectName], 0
0x1400909f8  lea     r8, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x1400909fd  mov     [rsp+68h+InitialState], 0; InitialState
0x140090a02  mov     edx, 1F0003h; DesiredAccess
0x140090a07  lea     rcx, EventHandle; EventHandle
0x140090a0e  movdqu  xmmword ptr [rsp+68h+ObjectAttributes.SecurityDescriptor], xmm0
0x140090a14  call    cs:__imp_ZwCreateEvent
0x140090a1b  nop     dword ptr [rax+rax+00h]
0x140090a20  mov     ebx, eax
0x140090a22  test    eax, eax
0x140090a24  jns     short loc_140090A31
0x140090a26  mov     r8d, 1B7h
0x140090a2c  jmp     loc_140090AE1
0x140090a31  mov     r9d, 1; EventType
0x140090a37  mov     [rsp+68h+InitialState], 0; InitialState
0x140090a3c  lea     r8, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x140090a41  mov     edx, 1F0003h; DesiredAccess
0x140090a46  lea     rcx, Handle; EventHandle
0x140090a4d  call    cs:__imp_ZwCreateEvent
0x140090a54  nop     dword ptr [rax+rax+00h]
0x140090a59  mov     ebx, eax
0x140090a5b  test    eax, eax
0x140090a5d  jns     short loc_140090A67
0x140090a5f  mov     r8d, 1C4h
0x140090a65  jmp     short loc_140090AE1
0x140090a67  lea     rcx, qword_1400643B8
0x140090a6e  call    VidRegistryOpenParametersKey
0x140090a73  mov     ebx, eax
0x140090a75  test    eax, eax
0x140090a77  jns     short loc_140090A81
0x140090a79  mov     r8d, 1CBh
0x140090a7f  jmp     short loc_140090AE1
0x140090a81  mov     rax, cs:WdfFunctions_01015
0x140090a88  mov     rdx, cs:qword_1400643B8
0x140090a8f  mov     rcx, cs:WdfDriverGlobals
0x140090a96  mov     rax, [rax+740h]
0x140090a9d  call    _guard_dispatch_icall
0x140090aa2  lea     r9, gVidRegistryContext
0x140090aa9  mov     cs:KeyHandle, rax
0x140090ab0  xor     r8d, r8d
0x140090ab3  mov     cs:qword_140064330, 0
0x140090abe  xor     edx, edx
0x140090ac0  mov     qword ptr [rsp+68h+InitialState], 0
0x140090ac9  lea     rcx, VidRegistrypNotificationRoutine
0x140090ad0  call    VidThreadCreate
0x140090ad5  mov     ebx, eax
0x140090ad7  test    eax, eax
0x140090ad9  jns     short loc_140090AFC
0x140090adb  mov     r8d, 1DEh
0x140090ae1  lea     rdx, aOnecoreVmVidSy_74; "onecore\\vm\\vid\\sys\\driver\\vidregis"...
0x140090ae8  lea     rcx, aVidregistrynot; "VidRegistryNotificationsSetup"
0x140090aef  mov     r9d, ebx
0x140090af2  call    VidTraceErrorStatusInternal0
0x140090af7  call    VidRegistrypNotificationsTeardownInternal
0x140090afc  mov     eax, ebx
0x140090afe  add     rsp, 60h
0x140090b02  pop     rbx
0x140090b03  retn
```
