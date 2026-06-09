# SmpInitializeSessionManagement

- ea: `0x14000ea00`
- end: `0x14000ea56`
- name: `SmpInitializeSessionManagement`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x14000ea00`
- `0x1400178ac`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x14000ea42`
- `ntdll!NtCreateEvent` at `0x14000ea42`

## pseudocode

```c
NTSTATUS SmpInitializeSessionManagement()
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES v1; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&v1.Length = 48;
  v1.RootDirectory = 0;
  v1.ObjectName = 0;
  *(_QWORD *)&v1.Attributes = 2;
  *(_OWORD *)&v1.SecurityDescriptor = 0;
  result = NtCreateEvent(&SmpSessionCreateBlockEvent, 0x100002u, &v1, NotificationEvent, 1u);
  if ( result >= 0 )
    return SmpInitCoreProcessArray();
  return result;
}

```

## disassembly

```asm
0x14000ea00  mov     r11, rsp
0x14000ea03  sub     rsp, 68h
0x14000ea07  xor     eax, eax
0x14000ea09  mov     qword ptr [r11-38h], 30h ; '0'
0x14000ea11  xorps   xmm0, xmm0
0x14000ea14  mov     [r11-30h], rax
0x14000ea18  mov     [r11-28h], rax
0x14000ea1c  lea     r8, [r11-38h]; ObjectAttributes
0x14000ea20  mov     qword ptr [r11-20h], 2
0x14000ea28  lea     rcx, SmpSessionCreateBlockEvent; EventHandle
0x14000ea2f  xor     r9d, r9d; EventType
0x14000ea32  mov     [rsp+68h+InitialState], 1; InitialState
0x14000ea37  mov     edx, 100002h; DesiredAccess
0x14000ea3c  movdqu  [rsp+68h+var_18], xmm0
0x14000ea42  call    cs:__imp_NtCreateEvent
0x14000ea48  test    eax, eax
0x14000ea4a  js      short loc_14000EA51
0x14000ea4c  call    SmpInitCoreProcessArray
0x14000ea51  add     rsp, 68h
0x14000ea55  retn
```
