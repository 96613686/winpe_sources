# SpCreatePoolDevice(_GUID,SP_POOL_DEVICE * *)

- ea: `0x1400a4d74`
- end: `0x1400a4fcb`
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
- `0x140032cd8`
- `0x140068110`
- `0x140068600`
- `0x1400a4d74`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4f96`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4f96`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4e51`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4f5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4e51`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4f5d`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4e10`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4e10`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4f73`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4f73`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4efc`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4efc`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a4df8`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a4df8`
- `ntoskrnl!IoCreateDevice` at `0x1400a4e8d`
- `ntoskrnl!IoCreateDevice` at `0x1400a4e8d`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4f15`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4f15`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4f2a`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4f2a`

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
0x1400a4d74  mov     [rsp-8+arg_10], rbx
0x1400a4d79  push    rbp
0x1400a4d7a  push    rsi
0x1400a4d7b  push    rdi
0x1400a4d7c  push    r12
0x1400a4d7e  push    r14
0x1400a4d80  lea     rbp, [rsp-1A0h]
0x1400a4d88  sub     rsp, 2A0h
0x1400a4d8f  mov     rax, cs:__security_cookie
0x1400a4d96  xor     rax, rsp
0x1400a4d99  mov     [rbp+1C0h+var_30], rax
0x1400a4da0  movaps  xmm0, xmmword ptr [rcx]
0x1400a4da3  mov     r14, rdx
0x1400a4da6  movdqu  xmmword ptr [rbp+1C0h+Guid.Data1], xmm0
0x1400a4dab  mov     [rsp+2C0h+var_280], 0
0x1400a4db4  mov     r12d, 100h
0x1400a4dba  xorps   xmm0, xmm0
0x1400a4dbd  lea     rcx, [rbp+1C0h+pszDest]; void *
0x1400a4dc1  mov     r8d, r12d; Size
0x1400a4dc4  xor     edx, edx; Val
0x1400a4dc6  movups  xmmword ptr [rsp+2C0h+GuidString.Length], xmm0
0x1400a4dcb  call    memset
0x1400a4dd0  xorps   xmm0, xmm0
0x1400a4dd3  lea     rcx, [rbp+1C0h+SourceString]; void *
0x1400a4dda  mov     r8d, r12d; Size
0x1400a4ddd  xor     edx, edx; Val
0x1400a4ddf  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x1400a4de4  call    memset
0x1400a4de9  xorps   xmm0, xmm0
0x1400a4dec  mov     qword ptr [r14], 0
0x1400a4df3  movups  xmmword ptr [rsp+2C0h+SymbolicLinkName.Length], xmm0
0x1400a4df8  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x1400a4dff  nop     dword ptr [rax+rax+00h]
0x1400a4e04  lea     rdx, [rsp+2C0h+GuidString]; GuidString
0x1400a4e09  mov     rsi, rax
0x1400a4e0c  lea     rcx, [rbp+1C0h+Guid]; Guid
0x1400a4e10  call    cs:__imp_RtlStringFromGUID
0x1400a4e17  nop     dword ptr [rax+rax+00h]
0x1400a4e1c  mov     ebx, eax
0x1400a4e1e  test    eax, eax
0x1400a4e20  js      loc_1400A4F89
0x1400a4e26  lea     r9, [rsp+2C0h+GuidString]
0x1400a4e2b  mov     edx, r12d; cbDest
0x1400a4e2e  lea     r8, aDevicePoolWz; "\\Device\\Pool#%wZ"
0x1400a4e35  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x1400a4e39  call    RtlStringCbPrintfW
0x1400a4e3e  mov     ebx, eax
0x1400a4e40  test    eax, eax
0x1400a4e42  js      loc_1400A4F89
0x1400a4e48  lea     rdx, [rbp+1C0h+pszDest]; SourceString
0x1400a4e4c  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1400a4e51  call    cs:__imp_RtlInitUnicodeString
0x1400a4e58  nop     dword ptr [rax+rax+00h]
0x1400a4e5d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4e64  lea     rax, [rsp+2C0h+var_280]
0x1400a4e69  mov     [rsp+2C0h+DeviceObject], rax; DeviceObject
0x1400a4e6e  lea     edx, [rsi+160h]; DeviceExtensionSize
0x1400a4e74  mov     [rsp+2C0h+Exclusive], 0; Exclusive
0x1400a4e79  lea     r8, [rsp+2C0h+DestinationString]; DeviceName
0x1400a4e7e  mov     r9d, 22h ; '"'; DeviceType
0x1400a4e84  mov     [rsp+2C0h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x1400a4e89  mov     rcx, [rcx+8]; DriverObject
0x1400a4e8d  call    cs:__imp_IoCreateDevice
0x1400a4e94  nop     dword ptr [rax+rax+00h]
0x1400a4e99  mov     ebx, eax
0x1400a4e9b  test    eax, eax
0x1400a4e9d  js      loc_1400A4F89
0x1400a4ea3  mov     rax, [rsp+2C0h+var_280]
0x1400a4ea8  mov     rcx, [rax+40h]; unsigned __int64
0x1400a4eac  lea     rax, qword_14006D770
0x1400a4eb3  mov     [rcx], rax
0x1400a4eb6  mov     rax, [rsp+2C0h+var_280]
0x1400a4ebb  mov     rdx, [rax+40h]
0x1400a4ebf  add     rdx, 8; void *
0x1400a4ec3  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a4ec8  test    rax, rax
0x1400a4ecb  jz      loc_1400A4F84
0x1400a4ed1  mov     rcx, rax; this
0x1400a4ed4  call    ??0SP_POOL_DEVICE@@QEAA@XZ; SP_POOL_DEVICE::SP_POOL_DEVICE(void)
0x1400a4ed9  mov     rdi, rax
0x1400a4edc  test    rax, rax
0x1400a4edf  jz      loc_1400A4F84
0x1400a4ee5  mov     rcx, [rsp+2C0h+var_280]
0x1400a4eea  xor     edx, edx; Level
0x1400a4eec  mov     [rax], rcx
0x1400a4eef  lea     rcx, [rax+18h]; Mutex
0x1400a4ef3  movaps  xmm0, xmmword ptr [rbp+1C0h+Guid.Data1]
0x1400a4ef7  movdqu  xmmword ptr [rax+8], xmm0
0x1400a4efc  call    cs:__imp_KeInitializeMutex
0x1400a4f03  nop     dword ptr [rax+rax+00h]
0x1400a4f08  lea     rcx, [rdi+158h]; RunRefCacheAware
0x1400a4f0f  mov     edx, esi; RunRefSize
0x1400a4f11  mov     [rdi+50h], rcx
0x1400a4f15  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x1400a4f1c  nop     dword ptr [rax+rax+00h]
0x1400a4f21  lea     rcx, [rdi+58h]; Event
0x1400a4f25  xor     r8d, r8d; State
0x1400a4f28  xor     edx, edx; Type
0x1400a4f2a  call    cs:__imp_KeInitializeEvent
0x1400a4f31  nop     dword ptr [rax+rax+00h]
0x1400a4f36  lea     r9, [rsp+2C0h+GuidString]
0x1400a4f3b  mov     edx, r12d; cbDest
0x1400a4f3e  lea     r8, aDosdevicesGlob_0; "\\DosDevices\\Global\\Pool#%wZ"
0x1400a4f45  lea     rcx, [rbp+1C0h+SourceString]; pszDest
0x1400a4f4c  call    RtlStringCbPrintfW
0x1400a4f51  lea     rdx, [rbp+1C0h+SourceString]; SourceString
0x1400a4f58  lea     rcx, [rsp+2C0h+SymbolicLinkName]; DestinationString
0x1400a4f5d  call    cs:__imp_RtlInitUnicodeString
0x1400a4f64  nop     dword ptr [rax+rax+00h]
0x1400a4f69  lea     rdx, [rsp+2C0h+DestinationString]; DeviceName
0x1400a4f6e  lea     rcx, [rsp+2C0h+SymbolicLinkName]; SymbolicLinkName
0x1400a4f73  call    cs:__imp_IoCreateSymbolicLink
0x1400a4f7a  nop     dword ptr [rax+rax+00h]
0x1400a4f7f  mov     [r14], rdi
0x1400a4f82  jmp     short loc_1400A4F89
0x1400a4f84  mov     ebx, 0C000009Ah
0x1400a4f89  cmp     [rsp+2C0h+GuidString.Buffer], 0
0x1400a4f8f  jz      short loc_1400A4FA2
0x1400a4f91  lea     rcx, [rsp+2C0h+GuidString]; UnicodeString
0x1400a4f96  call    cs:__imp_RtlFreeUnicodeString
0x1400a4f9d  nop     dword ptr [rax+rax+00h]
0x1400a4fa2  mov     eax, ebx
0x1400a4fa4  mov     rcx, [rbp+1C0h+var_30]
0x1400a4fab  xor     rcx, rsp; StackCookie
0x1400a4fae  call    __security_check_cookie
0x1400a4fb3  mov     rbx, [rsp+2C0h+arg_10]
0x1400a4fbb  add     rsp, 2A0h
0x1400a4fc2  pop     r14
0x1400a4fc4  pop     r12
0x1400a4fc6  pop     rdi
0x1400a4fc7  pop     rsi
0x1400a4fc8  pop     rbp
0x1400a4fc9  retn
```
