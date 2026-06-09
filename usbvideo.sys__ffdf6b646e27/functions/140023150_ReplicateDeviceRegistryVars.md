# ReplicateDeviceRegistryVars

- ea: `0x140023150`
- end: `0x140023339`
- name: `ReplicateDeviceRegistryVars`
- size: `489`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PKSFILTERFACTORY FilterFactory)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x14001bdfc`

## callees

- `0x140004bac`
- `0x140022fa0`
- `0x140023150`
- `0x140023660`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002326d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002326d`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140023208`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140023208`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x1400231e7`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x1400231e7`
- `ntoskrnl!ZwClose` at `0x140023237`
- `ntoskrnl!ZwClose` at `0x1400232cb`
- `ntoskrnl!ZwClose` at `0x140023237`
- `ntoskrnl!ZwClose` at `0x1400232cb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400231a1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400231a1`
- `ks!KsFilterFactoryGetSymbolicLink` at `0x140023174`
- `ks!KsFilterFactoryGetSymbolicLink` at `0x140023174`

## pseudocode

```c
int __fastcall ReplicateDeviceRegistryVars(PDEVICE_OBJECT DeviceObject, PKSFILTERFACTORY FilterFactory)
{
  PUNICODE_STRING SymbolicLink; // rax
  struct _UNICODE_STRING *v5; // r15
  const KSFILTER_DESCRIPTOR *FilterDescriptor; // rsi
  ULONG v7; // edi
  __int64 v8; // r8
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  struct _UNICODE_STRING AliasSymbolicLinkName; // [rsp+20h] [rbp-10h] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp+38h] BYREF
  void *DeviceInterfaceRegKey; // [rsp+70h] [rbp+40h] BYREF

  DeviceRegKey = 0;
  SymbolicLink = KsFilterFactoryGetSymbolicLink(FilterFactory);
  v5 = SymbolicLink;
  if ( !SymbolicLink )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      return (int)SymbolicLink;
    v10 = 29;
LABEL_22:
    LODWORD(SymbolicLink) = WPP_SF_(v9->AttachedDevice, v10, WPP_687d416b691536ceda7edcd6a9251505_Traceguids);
    return (int)SymbolicLink;
  }
  FilterDescriptor = FilterFactory->FilterDescriptor;
  LODWORD(SymbolicLink) = IoOpenDeviceRegistryKey(DeviceObject, 1u, 0x20000u, &DeviceRegKey);
  if ( (int)SymbolicLink < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      return (int)SymbolicLink;
    v10 = 28;
    goto LABEL_22;
  }
  v7 = 0;
  DeviceInterfaceRegKey = 0;
  for ( AliasSymbolicLinkName = 0; v7 < FilterDescriptor->CategoriesCount; ++v7 )
  {
    if ( IoGetDeviceInterfaceAlias(v5, &FilterDescriptor->Categories[v7], &AliasSymbolicLinkName) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_687d416b691536ceda7edcd6a9251505_Traceguids);
    }
    else
    {
      if ( IoOpenDeviceInterfaceRegistryKey(&AliasSymbolicLinkName, 0x1F0000u, &DeviceInterfaceRegKey) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, struct _UNICODE_STRING *))WPP_SF_Z)(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            v8,
            &AliasSymbolicLinkName);
      }
      else
      {
        ForeachRegistryVar(
          DeviceRegKey,
          SaveInterfaceVar,
          DeviceInterfaceRegKey,
          L"UVC-",
          *(_QWORD *)&AliasSymbolicLinkName.Length,
          AliasSymbolicLinkName.Buffer);
        ZwClose(DeviceInterfaceRegKey);
      }
      RtlFreeUnicodeString(&AliasSymbolicLinkName);
    }
  }
  ForeachRegistryVar(
    DeviceRegKey,
    SaveDevPropKey,
    DeviceObject,
    L"DKEY-",
    *(_QWORD *)&AliasSymbolicLinkName.Length,
    AliasSymbolicLinkName.Buffer);
  LODWORD(SymbolicLink) = ZwClose(DeviceRegKey);
  return (int)SymbolicLink;
}

```

## disassembly

```asm
0x140023150  mov     [rsp-28h+arg_0], rbx
0x140023155  push    rbp
0x140023156  push    rsi
0x140023157  push    rdi
0x140023158  push    r14
0x14002315a  push    r15
0x14002315c  mov     rbp, rsp
0x14002315f  sub     rsp, 30h
0x140023163  mov     r14, rcx
0x140023166  mov     [rbp+DeviceRegKey], 0
0x14002316e  mov     rcx, rdx; FilterFactory
0x140023171  mov     rbx, rdx
0x140023174  call    cs:__imp_KsFilterFactoryGetSymbolicLink
0x14002317b  nop     dword ptr [rax+rax+00h]
0x140023180  mov     r15, rax
0x140023183  test    rax, rax
0x140023186  jz      loc_1400232F9
0x14002318c  mov     rsi, [rbx]
0x14002318f  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140023193  mov     edx, 1; DevInstKeyType
0x140023198  mov     r8d, 20000h; DesiredAccess
0x14002319e  mov     rcx, r14; DeviceObject
0x1400231a1  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400231a8  nop     dword ptr [rax+rax+00h]
0x1400231ad  test    eax, eax
0x1400231af  js      loc_1400232D9
0x1400231b5  xor     edi, edi
0x1400231b7  mov     [rbp+DeviceInterfaceRegKey], 0
0x1400231bf  xorps   xmm0, xmm0
0x1400231c2  movups  xmmword ptr [rbp+AliasSymbolicLinkName.Length], xmm0
0x1400231c6  cmp     [rsi+30h], edi
0x1400231c9  jbe     loc_1400232AD
0x1400231cf  lea     rbx, WPP_GLOBAL_Control
0x1400231d6  mov     edx, edi
0x1400231d8  lea     r8, [rbp+AliasSymbolicLinkName]; AliasSymbolicLinkName
0x1400231dc  shl     rdx, 4
0x1400231e0  mov     rcx, r15; SymbolicLinkName
0x1400231e3  add     rdx, [rsi+38h]; AliasInterfaceClassGuid
0x1400231e7  call    cs:__imp_IoGetDeviceInterfaceAlias
0x1400231ee  nop     dword ptr [rax+rax+00h]
0x1400231f3  test    eax, eax
0x1400231f5  js      loc_14002327B
0x1400231fb  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x1400231ff  mov     edx, 1F0000h; DesiredAccess
0x140023204  lea     rcx, [rbp+AliasSymbolicLinkName]; SymbolicLinkName
0x140023208  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x14002320f  nop     dword ptr [rax+rax+00h]
0x140023214  test    eax, eax
0x140023216  js      short loc_140023245
0x140023218  mov     r8, [rbp+DeviceInterfaceRegKey]
0x14002321c  lea     r9, aUvc; "UVC-"
0x140023223  mov     rcx, [rbp+DeviceRegKey]
0x140023227  lea     rdx, SaveInterfaceVar
0x14002322e  call    ForeachRegistryVar
0x140023233  mov     rcx, [rbp+DeviceInterfaceRegKey]; Handle
0x140023237  call    cs:__imp_ZwClose
0x14002323e  nop     dword ptr [rax+rax+00h]
0x140023243  jmp     short loc_140023269
0x140023245  mov     rcx, cs:WPP_GLOBAL_Control
0x14002324c  cmp     rcx, rbx
0x14002324f  jz      short loc_140023269
0x140023251  cmp     byte ptr [rcx+29h], 2
0x140023255  jb      short loc_140023269
0x140023257  mov     rcx, [rcx+18h]
0x14002325b  lea     r9, [rbp+AliasSymbolicLinkName]
0x14002325f  mov     edx, 1Ah
0x140023264  call    WPP_SF_Z
0x140023269  lea     rcx, [rbp+AliasSymbolicLinkName]; UnicodeString
0x14002326d  call    cs:__imp_RtlFreeUnicodeString
0x140023274  nop     dword ptr [rax+rax+00h]
0x140023279  jmp     short loc_1400232A2
0x14002327b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023282  cmp     rcx, rbx
0x140023285  jz      short loc_1400232A2
0x140023287  cmp     byte ptr [rcx+29h], 2
0x14002328b  jb      short loc_1400232A2
0x14002328d  mov     rcx, [rcx+18h]
0x140023291  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x140023298  mov     edx, 1Bh
0x14002329d  call    WPP_SF_
0x1400232a2  inc     edi
0x1400232a4  cmp     edi, [rsi+30h]
0x1400232a7  jb      loc_1400231D6
0x1400232ad  mov     rcx, [rbp+DeviceRegKey]
0x1400232b1  lea     r9, aDkey; "DKEY-"
0x1400232b8  mov     r8, r14
0x1400232bb  lea     rdx, SaveDevPropKey
0x1400232c2  call    ForeachRegistryVar
0x1400232c7  mov     rcx, [rbp+DeviceRegKey]; Handle
0x1400232cb  call    cs:__imp_ZwClose
0x1400232d2  nop     dword ptr [rax+rax+00h]
0x1400232d7  jmp     short loc_140023327
0x1400232d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232e0  lea     rbx, WPP_GLOBAL_Control
0x1400232e7  cmp     rcx, rbx
0x1400232ea  jz      short loc_140023327
0x1400232ec  cmp     byte ptr [rcx+29h], 4
0x1400232f0  jb      short loc_140023327
0x1400232f2  mov     edx, 1Ch
0x1400232f7  jmp     short loc_140023317
0x1400232f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140023300  lea     rbx, WPP_GLOBAL_Control
0x140023307  cmp     rcx, rbx
0x14002330a  jz      short loc_140023327
0x14002330c  cmp     byte ptr [rcx+29h], 4
0x140023310  jb      short loc_140023327
0x140023312  mov     edx, 1Dh
0x140023317  mov     rcx, [rcx+18h]
0x14002331b  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x140023322  call    WPP_SF_
0x140023327  mov     rbx, [rsp+30h+arg_0]
0x14002332c  add     rsp, 30h
0x140023330  pop     r15
0x140023332  pop     r14
0x140023334  pop     rdi
0x140023335  pop     rsi
0x140023336  pop     rbp
0x140023337  retn
```
