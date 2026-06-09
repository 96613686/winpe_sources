# SpCreatePoolDevice(_GUID,SP_POOL_DEVICE * *)

- ea: `0x1400a4c44`
- end: `0x1400a4e9b`
- name: `?SpCreatePoolDevice@@YAJU_GUID@@PEAPEAVSP_POOL_DEVICE@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct SP_POOL_DEVICE **)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x14008cbf8`
- `0x140092fbc`

## callees

- `0x140019500`
- `0x14002b048`
- `0x140032c24`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400a4c44`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4e66`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4e66`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4d21`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4e2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4d21`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4e2d`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4ce0`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4ce0`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4e43`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4e43`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4dcc`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4dcc`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a4cc8`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a4cc8`
- `ntoskrnl!IoCreateDevice` at `0x1400a4d5d`
- `ntoskrnl!IoCreateDevice` at `0x1400a4d5d`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4de5`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4de5`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4dfa`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4dfa`

## pseudocode

```c
__int64 __fastcall SpCreatePoolDevice(struct _GUID *a1, struct SP_POOL_DEVICE **a2)
{
  unsigned int v3; // esi
  NTSTATUS v4; // ebx
  unsigned __int64 v5; // r8
  _QWORD *DeviceExtension; // rcx
  SP_POOL_DEVICE *v7; // rax
  SP_POOL_DEVICE *v8; // rax
  SP_POOL_DEVICE *v9; // rdi
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+68h] [rbp-98h] BYREF
  GUID Guid; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[128]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t SourceString[128]; // [rsp+190h] [rbp+90h] BYREF

  Guid = *a1;
  DeviceObject = 0;
  GuidString = 0;
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  *a2 = 0;
  SymbolicLinkName = 0;
  v3 = ExSizeOfRundownProtectionCacheAware();
  v4 = RtlStringFromGUID(&Guid, &GuidString);
  if ( v4 >= 0 )
  {
    v4 = RtlStringCbPrintfW(pszDest, 0x100u, L"\\Device\\Pool#%wZ", &GuidString);
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pszDest);
      v4 = IoCreateDevice(
             *((PDRIVER_OBJECT *)WPP_MAIN_CB.DeviceExtension + 1),
             v3 + 352,
             &DestinationString,
             0x22u,
             0x100u,
             0,
             &DeviceObject);
      if ( v4 >= 0 )
      {
        DeviceExtension = DeviceObject->DeviceExtension;
        *DeviceExtension = qword_14006D770;
        v7 = (SP_POOL_DEVICE *)SP_DEVICE::operator new(
                                 (unsigned __int64)DeviceExtension,
                                 (char *)DeviceObject->DeviceExtension + 8,
                                 v5);
        if ( v7 && (v8 = SP_POOL_DEVICE::SP_POOL_DEVICE(v7), (v9 = v8) != 0) )
        {
          *(_QWORD *)v8 = DeviceObject;
          *(GUID *)((char *)v8 + 8) = Guid;
          KeInitializeMutex((PRKMUTEX)((char *)v8 + 24), 0);
          *((_QWORD *)v9 + 10) = (char *)v9 + 344;
          ExInitializeRundownProtectionCacheAware((SP_POOL_DEVICE *)((char *)v9 + 344), v3);
          KeInitializeEvent((PRKEVENT)((char *)v9 + 88), NotificationEvent, 0);
          RtlStringCbPrintfW(SourceString, 0x100u, L"\\DosDevices\\Global\\Pool#%wZ", &GuidString);
          RtlInitUnicodeString(&SymbolicLinkName, SourceString);
          IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
          *a2 = v9;
        }
        else
        {
          v4 = -1073741670;
        }
      }
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400a4c44  mov     [rsp-8+arg_10], rbx
0x1400a4c49  push    rbp
0x1400a4c4a  push    rsi
0x1400a4c4b  push    rdi
0x1400a4c4c  push    r12
0x1400a4c4e  push    r14
0x1400a4c50  lea     rbp, [rsp-1A0h]
0x1400a4c58  sub     rsp, 2A0h
0x1400a4c5f  mov     rax, cs:__security_cookie
0x1400a4c66  xor     rax, rsp
0x1400a4c69  mov     [rbp+1C0h+var_30], rax
0x1400a4c70  movaps  xmm0, xmmword ptr [rcx]
0x1400a4c73  mov     r14, rdx
0x1400a4c76  movdqu  xmmword ptr [rbp+1C0h+Guid.Data1], xmm0
0x1400a4c7b  mov     [rsp+2C0h+var_280], 0
0x1400a4c84  mov     r12d, 100h
0x1400a4c8a  xorps   xmm0, xmm0
0x1400a4c8d  lea     rcx, [rbp+1C0h+pszDest]; void *
0x1400a4c91  mov     r8d, r12d; Size
0x1400a4c94  xor     edx, edx; Val
0x1400a4c96  movups  xmmword ptr [rsp+2C0h+GuidString.Length], xmm0
0x1400a4c9b  call    memset
0x1400a4ca0  xorps   xmm0, xmm0
0x1400a4ca3  lea     rcx, [rbp+1C0h+SourceString]; void *
0x1400a4caa  mov     r8d, r12d; Size
0x1400a4cad  xor     edx, edx; Val
0x1400a4caf  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x1400a4cb4  call    memset
0x1400a4cb9  xorps   xmm0, xmm0
0x1400a4cbc  mov     qword ptr [r14], 0
0x1400a4cc3  movups  xmmword ptr [rsp+2C0h+SymbolicLinkName.Length], xmm0
0x1400a4cc8  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x1400a4ccf  nop     dword ptr [rax+rax+00h]
0x1400a4cd4  lea     rdx, [rsp+2C0h+GuidString]; GuidString
0x1400a4cd9  mov     rsi, rax
0x1400a4cdc  lea     rcx, [rbp+1C0h+Guid]; Guid
0x1400a4ce0  call    cs:__imp_RtlStringFromGUID
0x1400a4ce7  nop     dword ptr [rax+rax+00h]
0x1400a4cec  mov     ebx, eax
0x1400a4cee  test    eax, eax
0x1400a4cf0  js      loc_1400A4E59
0x1400a4cf6  lea     r9, [rsp+2C0h+GuidString]
0x1400a4cfb  mov     edx, r12d; cbDest
0x1400a4cfe  lea     r8, aDevicePoolWz; "\\Device\\Pool#%wZ"
0x1400a4d05  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x1400a4d09  call    RtlStringCbPrintfW
0x1400a4d0e  mov     ebx, eax
0x1400a4d10  test    eax, eax
0x1400a4d12  js      loc_1400A4E59
0x1400a4d18  lea     rdx, [rbp+1C0h+pszDest]; SourceString
0x1400a4d1c  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1400a4d21  call    cs:__imp_RtlInitUnicodeString
0x1400a4d28  nop     dword ptr [rax+rax+00h]
0x1400a4d2d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4d34  lea     rax, [rsp+2C0h+var_280]
0x1400a4d39  mov     [rsp+2C0h+DeviceObject], rax; DeviceObject
0x1400a4d3e  lea     edx, [rsi+160h]; DeviceExtensionSize
0x1400a4d44  mov     [rsp+2C0h+Exclusive], 0; Exclusive
0x1400a4d49  lea     r8, [rsp+2C0h+DestinationString]; DeviceName
0x1400a4d4e  mov     r9d, 22h ; '"'; DeviceType
0x1400a4d54  mov     [rsp+2C0h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x1400a4d59  mov     rcx, [rcx+8]; DriverObject
0x1400a4d5d  call    cs:__imp_IoCreateDevice
0x1400a4d64  nop     dword ptr [rax+rax+00h]
0x1400a4d69  mov     ebx, eax
0x1400a4d6b  test    eax, eax
0x1400a4d6d  js      loc_1400A4E59
0x1400a4d73  mov     rax, [rsp+2C0h+var_280]
0x1400a4d78  mov     rcx, [rax+40h]; unsigned __int64
0x1400a4d7c  lea     rax, qword_14006D770
0x1400a4d83  mov     [rcx], rax
0x1400a4d86  mov     rax, [rsp+2C0h+var_280]
0x1400a4d8b  mov     rdx, [rax+40h]
0x1400a4d8f  add     rdx, 8; void *
0x1400a4d93  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a4d98  test    rax, rax
0x1400a4d9b  jz      loc_1400A4E54
0x1400a4da1  mov     rcx, rax; this
0x1400a4da4  call    ??0SP_POOL_DEVICE@@QEAA@XZ; SP_POOL_DEVICE::SP_POOL_DEVICE(void)
0x1400a4da9  mov     rdi, rax
0x1400a4dac  test    rax, rax
0x1400a4daf  jz      loc_1400A4E54
0x1400a4db5  mov     rcx, [rsp+2C0h+var_280]
0x1400a4dba  xor     edx, edx; Level
0x1400a4dbc  mov     [rax], rcx
0x1400a4dbf  lea     rcx, [rax+18h]; Mutex
0x1400a4dc3  movaps  xmm0, xmmword ptr [rbp+1C0h+Guid.Data1]
0x1400a4dc7  movdqu  xmmword ptr [rax+8], xmm0
0x1400a4dcc  call    cs:__imp_KeInitializeMutex
0x1400a4dd3  nop     dword ptr [rax+rax+00h]
0x1400a4dd8  lea     rcx, [rdi+158h]; RunRefCacheAware
0x1400a4ddf  mov     edx, esi; RunRefSize
0x1400a4de1  mov     [rdi+50h], rcx
0x1400a4de5  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x1400a4dec  nop     dword ptr [rax+rax+00h]
0x1400a4df1  lea     rcx, [rdi+58h]; Event
0x1400a4df5  xor     r8d, r8d; State
0x1400a4df8  xor     edx, edx; Type
0x1400a4dfa  call    cs:__imp_KeInitializeEvent
0x1400a4e01  nop     dword ptr [rax+rax+00h]
0x1400a4e06  lea     r9, [rsp+2C0h+GuidString]
0x1400a4e0b  mov     edx, r12d; cbDest
0x1400a4e0e  lea     r8, aDosdevicesGlob_0; "\\DosDevices\\Global\\Pool#%wZ"
0x1400a4e15  lea     rcx, [rbp+1C0h+SourceString]; pszDest
0x1400a4e1c  call    RtlStringCbPrintfW
0x1400a4e21  lea     rdx, [rbp+1C0h+SourceString]; SourceString
0x1400a4e28  lea     rcx, [rsp+2C0h+SymbolicLinkName]; DestinationString
0x1400a4e2d  call    cs:__imp_RtlInitUnicodeString
0x1400a4e34  nop     dword ptr [rax+rax+00h]
0x1400a4e39  lea     rdx, [rsp+2C0h+DestinationString]; DeviceName
0x1400a4e3e  lea     rcx, [rsp+2C0h+SymbolicLinkName]; SymbolicLinkName
0x1400a4e43  call    cs:__imp_IoCreateSymbolicLink
0x1400a4e4a  nop     dword ptr [rax+rax+00h]
0x1400a4e4f  mov     [r14], rdi
0x1400a4e52  jmp     short loc_1400A4E59
0x1400a4e54  mov     ebx, 0C000009Ah
0x1400a4e59  cmp     [rsp+2C0h+GuidString.Buffer], 0
0x1400a4e5f  jz      short loc_1400A4E72
0x1400a4e61  lea     rcx, [rsp+2C0h+GuidString]; UnicodeString
0x1400a4e66  call    cs:__imp_RtlFreeUnicodeString
0x1400a4e6d  nop     dword ptr [rax+rax+00h]
0x1400a4e72  mov     eax, ebx
0x1400a4e74  mov     rcx, [rbp+1C0h+var_30]
0x1400a4e7b  xor     rcx, rsp; StackCookie
0x1400a4e7e  call    __security_check_cookie
0x1400a4e83  mov     rbx, [rsp+2C0h+arg_10]
0x1400a4e8b  add     rsp, 2A0h
0x1400a4e92  pop     r14
0x1400a4e94  pop     r12
0x1400a4e96  pop     rdi
0x1400a4e97  pop     rsi
0x1400a4e98  pop     rbp
0x1400a4e99  retn
```
