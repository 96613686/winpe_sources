# WinHvpInitializeRmSupport

- ea: `0x140009024`
- end: `0x140009144`
- name: `WinHvpInitializeRmSupport`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002a804`

## callees

- `0x140009024`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140009078`
- `ntoskrnl!KeInitializeDpc` at `0x140009078`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000908b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000908b`
- `ntoskrnl!ZwOpenEvent` at `0x1400090e0`
- `ntoskrnl!ZwOpenEvent` at `0x1400090e0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009115`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009115`
- `ntoskrnl!ZwClose` at `0x140009127`
- `ntoskrnl!ZwClose` at `0x140009127`

## pseudocode

```c
__int64 WinHvpInitializeRmSupport()
{
  NTSTATUS v1; // ebx
  _QWORD v2[2]; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF

  v2[0] = 4456514;
  EventHandle = 0;
  WinHvpMmFlags = 50;
  v2[1] = L"\\KernelObjects\\HvlWithdrawAllowed";
  memset(&ObjectAttributes, 0, 44);
  KeInitializeDpc(&stru_140016130, WinHvpOnInsufficientMemoryDpcRoutine, 0);
  qword_140016170 = IoAllocateWorkItem(WinHvpHypervisorDriver);
  if ( !qword_140016170 )
    return 3221225626LL;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v2;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenEvent(&EventHandle, 1u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    v1 = ObReferenceObjectByHandle(EventHandle, 1u, 0, 0, &WinHvpWithdrawAllowedEvent, 0);
    ZwClose(EventHandle);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140009024  mov     [rsp-8+arg_8], rbx
0x140009029  push    rbp
0x14000902a  mov     rbp, rsp
0x14000902d  sub     rsp, 70h
0x140009031  xorps   xmm0, xmm0
0x140009034  mov     [rbp+var_40], 440042h
0x14000903c  xor     eax, eax
0x14000903e  mov     [rbp+EventHandle], 0
0x140009046  lea     rax, aKernelobjectsH; "\\KernelObjects\\HvlWithdrawAllowed"
0x14000904d  mov     cs:WinHvpMmFlags, 32h ; '2'
0x140009057  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000905b  xor     r8d, r8d; DeferredContext
0x14000905e  mov     [rbp+var_38], rax
0x140009062  lea     rdx, WinHvpOnInsufficientMemoryDpcRoutine; DeferredRoutine
0x140009069  lea     rcx, stru_140016130; Dpc
0x140009070  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140009074  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140009078  call    cs:__imp_KeInitializeDpc
0x14000907f  nop     dword ptr [rax+rax+00h]
0x140009084  mov     rcx, cs:WinHvpHypervisorDriver; DeviceObject
0x14000908b  call    cs:__imp_IoAllocateWorkItem
0x140009092  nop     dword ptr [rax+rax+00h]
0x140009097  mov     cs:qword_140016170, rax
0x14000909e  test    rax, rax
0x1400090a1  jnz     short loc_1400090AD
0x1400090a3  mov     eax, 0C000009Ah
0x1400090a8  jmp     loc_140009135
0x1400090ad  lea     rax, [rbp+var_40]
0x1400090b1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400090b8  xorps   xmm0, xmm0
0x1400090bb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400090bf  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400090c3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400090cb  mov     edx, 1; DesiredAccess
0x1400090d0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400090d7  lea     rcx, [rbp+EventHandle]; EventHandle
0x1400090db  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400090e0  call    cs:__imp_ZwOpenEvent
0x1400090e7  nop     dword ptr [rax+rax+00h]
0x1400090ec  mov     ebx, eax
0x1400090ee  test    eax, eax
0x1400090f0  js      short loc_140009133
0x1400090f2  mov     rcx, [rbp+EventHandle]; Handle
0x1400090f6  lea     rax, WinHvpWithdrawAllowedEvent
0x1400090fd  xor     r9d, r9d; AccessMode
0x140009100  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x140009109  xor     r8d, r8d; ObjectType
0x14000910c  mov     [rsp+70h+Object], rax; Object
0x140009111  lea     edx, [r9+1]; DesiredAccess
0x140009115  call    cs:__imp_ObReferenceObjectByHandle
0x14000911c  nop     dword ptr [rax+rax+00h]
0x140009121  mov     rcx, [rbp+EventHandle]; Handle
0x140009125  mov     ebx, eax
0x140009127  call    cs:__imp_ZwClose
0x14000912e  nop     dword ptr [rax+rax+00h]
0x140009133  mov     eax, ebx
0x140009135  mov     rbx, [rsp+70h+arg_8]
0x14000913d  add     rsp, 70h
0x140009141  pop     rbp
0x140009142  retn
```
