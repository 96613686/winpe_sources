# DriverEntry

- ea: `0x14003a078`
- end: `0x14003a233`
- name: `DriverEntry`
- size: `443`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003a010`

## callees

- `0x140005038`
- `0x140005068`
- `0x14000702c`
- `0x14003627c`
- `0x140036310`
- `0x1400366fc`
- `0x14003770c`
- `0x140038350`
- `0x140038494`
- `0x14003a078`
- `0x14003a23c`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int inited; // eax
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx

  wil_InitializeFeatureStaging();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  inited = InitPgm(DriverObject, RegistryPath);
  v5 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_a24bb4c2db3a31577af78786167edc49_Traceguids,
        (unsigned int)inited);
    wil_UninitializeFeatureStaging();
    return v5;
  }
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)PgmDispatchCreate;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)PgmDispatchDeviceControl;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)PgmDispatchInternalDeviceControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&PgmDispatchCleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&PgmDispatchClose;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)PgmUnload;
  v5 = SetTdiHandlers();
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_11;
    v7 = 11;
LABEL_10:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids, (unsigned int)v5);
LABEL_11:
    CleanupInit(5u);
    return v5;
  }
  v5 = PgmBuildAdminSecurityDescriptor((struct _ACL **)&PgmSecurityDescriptor);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_11;
    v7 = 12;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x14003a078  mov     [rsp+arg_0], rbx
0x14003a07d  push    rdi
0x14003a07e  sub     rsp, 20h
0x14003a082  mov     rbx, rdx
0x14003a085  mov     rdi, rcx
0x14003a088  call    wil_InitializeFeatureStaging
0x14003a08d  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14003a094  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14003a09f  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14003a0a6  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14003a0b1  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14003a0bc  mov     cs:WPP_MAIN_CB.Timer, 1
0x14003a0c7  call    WppLoadTracingSupport
0x14003a0cc  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14003a0d7  call    WppInitKm
0x14003a0dc  mov     rdx, rbx
0x14003a0df  mov     rcx, rdi
0x14003a0e2  call    InitPgm
0x14003a0e7  mov     ebx, eax
0x14003a0e9  test    eax, eax
0x14003a0eb  jns     short loc_14003A12A
0x14003a0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a0f4  lea     rdx, WPP_GLOBAL_Control
0x14003a0fb  cmp     rcx, rdx
0x14003a0fe  jz      short loc_14003A120
0x14003a100  mov     edx, [rcx+2Ch]
0x14003a103  test    dl, 2
0x14003a106  jz      short loc_14003A120
0x14003a108  mov     rcx, [rcx+18h]
0x14003a10c  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x14003a113  mov     edx, 0Ah
0x14003a118  mov     r9d, eax
0x14003a11b  call    WPP_SF_d
0x14003a120  call    wil_UninitializeFeatureStaging
0x14003a125  jmp     loc_14003A225
0x14003a12a  lea     rax, PgmDispatchCreate
0x14003a131  mov     [rdi+70h], rax
0x14003a135  lea     rax, PgmDispatchDeviceControl
0x14003a13c  mov     [rdi+0E0h], rax
0x14003a143  lea     rax, PgmDispatchInternalDeviceControl
0x14003a14a  mov     [rdi+0E8h], rax
0x14003a151  lea     rax, PgmDispatchCleanup
0x14003a158  mov     [rdi+100h], rax
0x14003a15f  lea     rax, PgmDispatchClose
0x14003a166  mov     [rdi+80h], rax
0x14003a16d  lea     rax, PgmUnload
0x14003a174  mov     [rdi+68h], rax
0x14003a178  call    SetTdiHandlers
0x14003a17d  mov     ebx, eax
0x14003a17f  test    eax, eax
0x14003a181  jns     short loc_14003A1C2
0x14003a183  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a18a  lea     rdx, WPP_GLOBAL_Control
0x14003a191  cmp     rcx, rdx
0x14003a194  jz      short loc_14003A1B6
0x14003a196  mov     edx, [rcx+2Ch]
0x14003a199  test    dl, 2
0x14003a19c  jz      short loc_14003A1B6
0x14003a19e  mov     edx, 0Bh
0x14003a1a3  mov     rcx, [rcx+18h]
0x14003a1a7  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x14003a1ae  mov     r9d, ebx
0x14003a1b1  call    WPP_SF_d
0x14003a1b6  mov     ecx, 5
0x14003a1bb  call    CleanupInit
0x14003a1c0  jmp     short loc_14003A225
0x14003a1c2  lea     rcx, PgmSecurityDescriptor
0x14003a1c9  call    PgmBuildAdminSecurityDescriptor
0x14003a1ce  mov     ebx, eax
0x14003a1d0  test    eax, eax
0x14003a1d2  jns     short loc_14003A1F6
0x14003a1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1db  lea     rdx, WPP_GLOBAL_Control
0x14003a1e2  cmp     rcx, rdx
0x14003a1e5  jz      short loc_14003A1B6
0x14003a1e7  mov     edx, [rcx+2Ch]
0x14003a1ea  test    dl, 2
0x14003a1ed  jz      short loc_14003A1B6
0x14003a1ef  mov     edx, 0Ch
0x14003a1f4  jmp     short loc_14003A1A3
0x14003a1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1fd  lea     rdx, WPP_GLOBAL_Control
0x14003a204  cmp     rcx, rdx
0x14003a207  jz      short loc_14003A225
0x14003a209  mov     eax, [rcx+2Ch]
0x14003a20c  test    al, 10h
0x14003a20e  jz      short loc_14003A225
0x14003a210  mov     rcx, [rcx+18h]
0x14003a214  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x14003a21b  mov     edx, 0Dh
0x14003a220  call    WPP_SF_
0x14003a225  mov     eax, ebx
0x14003a227  mov     rbx, [rsp+28h+arg_0]
0x14003a22c  add     rsp, 20h
0x14003a230  pop     rdi
0x14003a231  retn
```
