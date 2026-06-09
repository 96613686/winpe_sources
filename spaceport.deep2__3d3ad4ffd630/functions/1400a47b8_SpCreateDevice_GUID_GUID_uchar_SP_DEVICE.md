# SpCreateDevice(_GUID,_GUID,uchar,SP_DEVICE * *)

- ea: `0x1400a47b8`
- end: `0x1400a4c3b`
- name: `?SpCreateDevice@@YAJU_GUID@@0EPEAPEAVSP_DEVICE@@@Z`
- size: `1155`
- prototype: `int(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int8, struct SP_DEVICE **)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x14009d910`
- `0x14009f818`

## callees

- `0x140019500`
- `0x14002b048`
- `0x14002ce90`
- `0x140032b20`
- `0x140067fc0`
- `0x1400680a0`
- `0x1400684c0`
- `0x1400a47b8`
- `0x1400a4ea4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4b68`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4b68`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4892`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4b3a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4892`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4b3a`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4a27`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4b06`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4a27`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4b06`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4b4f`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4b4f`
- `ntoskrnl!ObfReferenceObject` at `0x1400a4acd`
- `ntoskrnl!ObfReferenceObject` at `0x1400a4acd`
- `ntoskrnl!KeInitializeMutex` at `0x1400a499f`
- `ntoskrnl!KeInitializeMutex` at `0x1400a49b4`
- `ntoskrnl!KeInitializeMutex` at `0x1400a499f`
- `ntoskrnl!KeInitializeMutex` at `0x1400a49b4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400a4a03`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400a4a03`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4a4d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4a4d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4ae9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4ae9`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a485b`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a485b`
- `ntoskrnl!IoCreateDevice` at `0x1400a48d0`
- `ntoskrnl!IoCreateDevice` at `0x1400a48d0`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a49ca`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a49ca`
- `ntoskrnl!KeInitializeEvent` at `0x1400a49e2`
- `ntoskrnl!KeInitializeEvent` at `0x1400a49e2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a4968`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a4968`

## pseudocode

```c
__int64 __fastcall SpCreateDevice(struct _GUID *a1, struct _GUID *a2, char a3, PVOID **a4)
{
  SP_DEVICE *v7; // rdi
  unsigned __int32 v8; // r15d
  unsigned int v9; // r14d
  NTSTATUS v10; // ebx
  unsigned __int64 v11; // r8
  SP_DEVICE *v12; // rax
  PDEVICE_OBJECT v13; // rcx
  SP_DEVICE *v14; // rax
  struct _GUID *v15; // rax
  __int128 v16; // xmm1
  char *v17; // r12
  char *v18; // rsi
  char *i; // r15
  PVOID *v20; // r14
  char **v21; // rax
  ULONG DeviceType; // ecx
  const char *v23; // r9
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-B8h] BYREF
  void *Buf2; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING GuidString; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v29; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[32]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t SourceString[128]; // [rsp+D0h] [rbp-30h] BYREF

  Buf2 = a2;
  v29 = a1;
  DeviceObject = 0;
  GuidString = 0;
  v7 = 0;
  memset(SourceString, 0, sizeof(SourceString));
  SymbolicLinkName = 0;
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  v8 = _InterlockedIncrement((volatile signed __int32 *)WPP_MAIN_CB.DeviceExtension + 82);
  v9 = ExSizeOfRundownProtectionCacheAware();
  v10 = RtlStringCbPrintfW(pszDest, 0x40u, L"\\Device\\Space%d", v8);
  if ( v10 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    v10 = IoCreateDevice(
            *((PDRIVER_OBJECT *)WPP_MAIN_CB.DeviceExtension + 1),
            v9 + 3320,
            &DestinationString,
            0x2Du,
            0x100u,
            0,
            &DeviceObject);
    if ( v10 >= 0 )
    {
      *(_QWORD *)DeviceObject->DeviceExtension = qword_14006D850;
      v12 = (SP_DEVICE *)SP_DEVICE::operator new(
                           (unsigned __int64)DeviceObject,
                           (char *)DeviceObject->DeviceExtension + 8,
                           v11);
      if ( v12 )
      {
        v14 = SP_DEVICE::SP_DEVICE(v12);
        v13 = DeviceObject;
        v7 = v14;
      }
      v15 = v29;
      *((_QWORD *)v7 + 20) = v13;
      *(struct _GUID *)((char *)v7 + 24) = *v15;
      v16 = (__int128)*a2;
      *(_WORD *)((char *)v7 + 169) = 0;
      *((_BYTE *)v7 + 168) = a3 != 0 ? 6 : 1;
      *(_OWORD *)((char *)v7 + 40) = v16;
      *((_DWORD *)v7 + 776) = v8;
      *((_DWORD *)v7 + 784) = -1;
      *((_QWORD *)v7 + 410) = KeQueryUnbiasedInterruptTime();
      v17 = (char *)v7 + 8;
      *((_QWORD *)v7 + 2) = (char *)v7 + 8;
      *((_QWORD *)v7 + 1) = (char *)v7 + 8;
      *((_QWORD *)v7 + 30) = (char *)v7 + 3312;
      KeInitializeMutex((PRKMUTEX)((char *)v7 + 176), 0);
      KeInitializeMutex((PRKMUTEX)((char *)v7 + 3168), 0);
      ExInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v7 + 30), v9);
      KeInitializeEvent((PRKEVENT)((char *)v7 + 256), NotificationEvent, 0);
      *((_QWORD *)v7 + 36) = (char *)v7 + 280;
      *((_QWORD *)v7 + 35) = (char *)v7 + 280;
      KeInitializeSpinLock((PKSPIN_LOCK)v7 + 37);
      *((_QWORD *)v7 + 387) = (char *)v7 + 3088;
      *((_QWORD *)v7 + 386) = (char *)v7 + 3088;
      v10 = RtlStringFromGUID(a2, (PUNICODE_STRING)v7 + 195);
      if ( v10 >= 0 )
      {
        ExAcquirePushLockExclusiveEx((char *)WPP_MAIN_CB.DeviceExtension + 320, 0);
        v18 = (char *)WPP_MAIN_CB.DeviceExtension + 304;
        for ( i = (char *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 38); i != v18; i = *(char **)i )
        {
          v20 = (PVOID *)(i - 8);
          if ( (unsigned __int8)(i[160] - 4) > 1u && !memcmp(v20 + 5, Buf2, 0x10u) )
            goto LABEL_14;
        }
        v21 = (char **)*((_QWORD *)v18 + 1);
        if ( *v21 != v18 )
          __fastfail(3u);
        *(_QWORD *)v17 = v18;
        v20 = (PVOID *)v7;
        *((_QWORD *)v7 + 2) = v21;
        v7 = 0;
        *v21 = v17;
        *((_QWORD *)v18 + 1) = v17;
LABEL_14:
        *a4 = v20;
        ObfReferenceObject(v20[20]);
        ExReleasePushLockExclusiveEx((char *)WPP_MAIN_CB.DeviceExtension + 320, 0);
        if ( a3 )
        {
          v10 = RtlStringFromGUID((const GUID *const)Buf2, &GuidString);
          if ( v10 >= 0 )
          {
            RtlStringCbPrintfW(SourceString, 0x100u, L"\\DosDevices\\Global\\Space#%wZ", &GuidString);
            RtlInitUnicodeString(&SymbolicLinkName, SourceString);
            IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
          }
        }
      }
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( v7 )
    SpDeleteDevice(v7);
  if ( v10 >= 0 || v10 == -2147483643 || v10 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v23 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v23 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v23,
      v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a47b8  mov     [rsp-8+arg_0], rbx
0x1400a47bd  push    rbp
0x1400a47be  push    rsi
0x1400a47bf  push    rdi
0x1400a47c0  push    r12
0x1400a47c2  push    r13
0x1400a47c4  push    r14
0x1400a47c6  push    r15
0x1400a47c8  lea     rbp, [rsp-0E0h]
0x1400a47d0  sub     rsp, 1E0h
0x1400a47d7  mov     rax, cs:__security_cookie
0x1400a47de  xor     rax, rsp
0x1400a47e1  mov     [rbp+110h+var_40], rax
0x1400a47e8  mov     r12b, r8b
0x1400a47eb  mov     [rsp+210h+var_1D0], r8b
0x1400a47f0  mov     rsi, rdx
0x1400a47f3  mov     [rsp+210h+Buf2], rdx
0x1400a47f8  mov     [rsp+210h+var_1A8], rcx
0x1400a47fd  xorps   xmm0, xmm0
0x1400a4800  xor     edx, edx; Val
0x1400a4802  mov     [rsp+210h+var_1C8], 0
0x1400a480b  mov     r8d, 100h; Size
0x1400a4811  lea     rcx, [rbp+110h+SourceString]; void *
0x1400a4815  movups  xmmword ptr [rsp+210h+GuidString.Length], xmm0
0x1400a481a  mov     r13, r9
0x1400a481d  xor     edi, edi
0x1400a481f  call    memset
0x1400a4824  xorps   xmm0, xmm0
0x1400a4827  lea     ebx, [rdi+40h]
0x1400a482a  mov     r8d, ebx; Size
0x1400a482d  lea     rcx, [rbp+110h+pszDest]; void *
0x1400a4831  xor     edx, edx; Val
0x1400a4833  movups  xmmword ptr [rbp+110h+SymbolicLinkName.Length], xmm0
0x1400a4837  call    memset
0x1400a483c  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4843  lea     r15d, [rdi+1]
0x1400a4847  xorps   xmm0, xmm0
0x1400a484a  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x1400a484f  lock xadd [rax+148h], r15d
0x1400a4858  inc     r15d
0x1400a485b  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x1400a4862  nop     dword ptr [rax+rax+00h]
0x1400a4867  mov     r9d, r15d
0x1400a486a  lea     r8, aDeviceSpaceD; "\\Device\\Space%d"
0x1400a4871  mov     edx, ebx; cbDest
0x1400a4873  lea     rcx, [rbp+110h+pszDest]; pszDest
0x1400a4877  mov     r14, rax
0x1400a487a  call    RtlStringCbPrintfW
0x1400a487f  mov     ebx, eax
0x1400a4881  test    eax, eax
0x1400a4883  js      loc_1400A4B5B
0x1400a4889  lea     rdx, [rbp+110h+pszDest]; SourceString
0x1400a488d  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x1400a4892  call    cs:__imp_RtlInitUnicodeString
0x1400a4899  nop     dword ptr [rax+rax+00h]
0x1400a489e  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a48a5  lea     rax, [rsp+210h+var_1C8]
0x1400a48aa  mov     [rsp+210h+DeviceObject], rax; DeviceObject
0x1400a48af  lea     edx, [r14+0CF8h]; DeviceExtensionSize
0x1400a48b6  mov     [rsp+210h+Exclusive], dil; Exclusive
0x1400a48bb  lea     r9d, [rdi+2Dh]; DeviceType
0x1400a48bf  lea     r8, [rsp+210h+DestinationString]; DeviceName
0x1400a48c4  mov     [rsp+210h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1400a48cc  mov     rcx, [rcx+8]; DriverObject
0x1400a48d0  call    cs:__imp_IoCreateDevice
0x1400a48d7  nop     dword ptr [rax+rax+00h]
0x1400a48dc  mov     ebx, eax
0x1400a48de  test    eax, eax
0x1400a48e0  js      loc_1400A4B5B
0x1400a48e6  mov     rax, [rsp+210h+var_1C8]
0x1400a48eb  mov     rcx, [rax+40h]
0x1400a48ef  lea     rax, qword_14006D850
0x1400a48f6  mov     [rcx], rax
0x1400a48f9  mov     rcx, [rsp+210h+var_1C8]; unsigned __int64
0x1400a48fe  mov     rdx, [rcx+40h]
0x1400a4902  add     rdx, 8; void *
0x1400a4906  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a490b  test    rax, rax
0x1400a490e  jz      short loc_1400A4920
0x1400a4910  mov     rcx, rax; this
0x1400a4913  call    ??0SP_DEVICE@@QEAA@XZ; SP_DEVICE::SP_DEVICE(void)
0x1400a4918  mov     rcx, [rsp+210h+var_1C8]
0x1400a491d  mov     rdi, rax
0x1400a4920  mov     rax, [rsp+210h+var_1A8]
0x1400a4925  mov     [rdi+0A0h], rcx
0x1400a492c  movaps  xmm0, xmmword ptr [rax]
0x1400a492f  mov     al, r12b
0x1400a4932  neg     al
0x1400a4934  movdqu  xmmword ptr [rdi+18h], xmm0
0x1400a4939  sbb     cl, cl
0x1400a493b  movaps  xmm1, xmmword ptr [rsi]
0x1400a493e  and     cl, 5
0x1400a4941  inc     cl
0x1400a4943  mov     word ptr [rdi+0A9h], 0
0x1400a494c  mov     [rdi+0A8h], cl
0x1400a4952  movdqu  xmmword ptr [rdi+28h], xmm1
0x1400a4957  mov     [rdi+0C20h], r15d
0x1400a495e  mov     dword ptr [rdi+0C40h], 0FFFFFFFFh
0x1400a4968  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400a496f  nop     dword ptr [rax+rax+00h]
0x1400a4974  mov     [rdi+0CD0h], rax
0x1400a497b  lea     r12, [rdi+8]
0x1400a497f  mov     [r12+8], r12
0x1400a4984  xor     edx, edx; Level
0x1400a4986  lea     rax, [rdi+0CF0h]
0x1400a498d  mov     [r12], r12
0x1400a4991  lea     rcx, [rdi+0B0h]; Mutex
0x1400a4998  mov     [rdi+0F0h], rax
0x1400a499f  call    cs:__imp_KeInitializeMutex
0x1400a49a6  nop     dword ptr [rax+rax+00h]
0x1400a49ab  lea     rcx, [rdi+0C60h]; Mutex
0x1400a49b2  xor     edx, edx; Level
0x1400a49b4  call    cs:__imp_KeInitializeMutex
0x1400a49bb  nop     dword ptr [rax+rax+00h]
0x1400a49c0  mov     rcx, [rdi+0F0h]; RunRefCacheAware
0x1400a49c7  mov     edx, r14d; RunRefSize
0x1400a49ca  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x1400a49d1  nop     dword ptr [rax+rax+00h]
0x1400a49d6  lea     rcx, [rdi+100h]; Event
0x1400a49dd  xor     r8d, r8d; State
0x1400a49e0  xor     edx, edx; Type
0x1400a49e2  call    cs:__imp_KeInitializeEvent
0x1400a49e9  nop     dword ptr [rax+rax+00h]
0x1400a49ee  lea     rax, [rdi+118h]
0x1400a49f5  lea     rcx, [rdi+128h]; SpinLock
0x1400a49fc  mov     [rax+8], rax
0x1400a4a00  mov     [rax], rax
0x1400a4a03  call    cs:__imp_KeInitializeSpinLock
0x1400a4a0a  nop     dword ptr [rax+rax+00h]
0x1400a4a0f  lea     rax, [rdi+0C10h]
0x1400a4a16  mov     rcx, rsi; Guid
0x1400a4a19  lea     rdx, [rdi+0C30h]; GuidString
0x1400a4a20  mov     [rax+8], rax
0x1400a4a24  mov     [rax], rax
0x1400a4a27  call    cs:__imp_RtlStringFromGUID
0x1400a4a2e  nop     dword ptr [rax+rax+00h]
0x1400a4a33  mov     ebx, eax
0x1400a4a35  test    eax, eax
0x1400a4a37  js      loc_1400A4B5B
0x1400a4a3d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4a44  xor     edx, edx
0x1400a4a46  add     rcx, 140h
0x1400a4a4d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a4a54  nop     dword ptr [rax+rax+00h]
0x1400a4a59  mov     rsi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4a60  add     rsi, 130h
0x1400a4a67  mov     r15, [rsi]
0x1400a4a6a  cmp     r15, rsi
0x1400a4a6d  jz      short loc_1400A4A9D
0x1400a4a6f  lea     r14, [r15-8]
0x1400a4a73  mov     al, [r14+0A8h]
0x1400a4a7a  sub     al, 4
0x1400a4a7c  cmp     al, 1
0x1400a4a7e  jbe     short loc_1400A4A98
0x1400a4a80  mov     rdx, [rsp+210h+Buf2]; Buf2
0x1400a4a85  lea     rcx, [r14+28h]; Buf1
0x1400a4a89  mov     r8d, 10h; Size
0x1400a4a8f  call    memcmp
0x1400a4a94  test    eax, eax
0x1400a4a96  jz      short loc_1400A4AC2
0x1400a4a98  mov     r15, [r15]
0x1400a4a9b  jmp     short loc_1400A4A6A
0x1400a4a9d  mov     rax, [rsi+8]
0x1400a4aa1  cmp     [rax], rsi
0x1400a4aa4  jz      short loc_1400A4AAD
0x1400a4aa6  mov     ecx, 3
0x1400a4aab  int     29h; Win8: RtlFailFast(ecx)
0x1400a4aad  mov     [r12], rsi
0x1400a4ab1  mov     r14, rdi
0x1400a4ab4  mov     [r12+8], rax
0x1400a4ab9  xor     edi, edi
0x1400a4abb  mov     [rax], r12
0x1400a4abe  mov     [rsi+8], r12
0x1400a4ac2  mov     [r13+0], r14
0x1400a4ac6  mov     rcx, [r14+0A0h]; Object
0x1400a4acd  call    cs:__imp_ObfReferenceObject
0x1400a4ad4  nop     dword ptr [rax+rax+00h]
0x1400a4ad9  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4ae0  xor     edx, edx
0x1400a4ae2  add     rcx, 140h
0x1400a4ae9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a4af0  nop     dword ptr [rax+rax+00h]
0x1400a4af5  cmp     [rsp+210h+var_1D0], 0
0x1400a4afa  jz      short loc_1400A4B5B
0x1400a4afc  mov     rcx, [rsp+210h+Buf2]; Guid
0x1400a4b01  lea     rdx, [rsp+210h+GuidString]; GuidString
0x1400a4b06  call    cs:__imp_RtlStringFromGUID
0x1400a4b0d  nop     dword ptr [rax+rax+00h]
0x1400a4b12  mov     ebx, eax
0x1400a4b14  test    eax, eax
0x1400a4b16  js      short loc_1400A4B5B
0x1400a4b18  lea     r9, [rsp+210h+GuidString]
0x1400a4b1d  mov     edx, 100h; cbDest
0x1400a4b22  lea     r8, aDosdevicesGlob; "\\DosDevices\\Global\\Space#%wZ"
0x1400a4b29  lea     rcx, [rbp+110h+SourceString]; pszDest
0x1400a4b2d  call    RtlStringCbPrintfW
0x1400a4b32  lea     rdx, [rbp+110h+SourceString]; SourceString
0x1400a4b36  lea     rcx, [rbp+110h+SymbolicLinkName]; DestinationString
0x1400a4b3a  call    cs:__imp_RtlInitUnicodeString
0x1400a4b41  nop     dword ptr [rax+rax+00h]
0x1400a4b46  lea     rdx, [rsp+210h+DestinationString]; DeviceName
0x1400a4b4b  lea     rcx, [rbp+110h+SymbolicLinkName]; SymbolicLinkName
0x1400a4b4f  call    cs:__imp_IoCreateSymbolicLink
0x1400a4b56  nop     dword ptr [rax+rax+00h]
0x1400a4b5b  cmp     [rsp+210h+GuidString.Buffer], 0
0x1400a4b61  jz      short loc_1400A4B74
0x1400a4b63  lea     rcx, [rsp+210h+GuidString]; UnicodeString
0x1400a4b68  call    cs:__imp_RtlFreeUnicodeString
0x1400a4b6f  nop     dword ptr [rax+rax+00h]
0x1400a4b74  test    rdi, rdi
0x1400a4b77  jz      short loc_1400A4B81
0x1400a4b79  mov     rcx, rdi; struct SP_DEVICE *
0x1400a4b7c  call    ?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z; SpDeleteDevice(SP_DEVICE *)
0x1400a4b81  test    ebx, ebx
0x1400a4b83  jns     short loc_1400A4BB4
0x1400a4b85  cmp     ebx, 80000005h
0x1400a4b8b  jz      short loc_1400A4BB4
0x1400a4b8d  cmp     ebx, 0C0000023h
0x1400a4b93  jz      short loc_1400A4BB4
0x1400a4b95  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a4b9b  cmp     ecx, 1
0x1400a4b9e  jz      short loc_1400A4BAB
0x1400a4ba0  mov     ecx, 1
0x1400a4ba5  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a4bab  lea     r9, aError; "Error"
0x1400a4bb2  jmp     short loc_1400A4BD1
0x1400a4bb4  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a4bba  cmp     ecx, 3
0x1400a4bbd  jz      short loc_1400A4BCA
0x1400a4bbf  mov     ecx, 3
0x1400a4bc4  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a4bca  lea     r9, aExit; "Exit "
0x1400a4bd1  mov     r10, cs:WPP_GLOBAL_Control
0x1400a4bd8  lea     rax, WPP_GLOBAL_Control
0x1400a4bdf  cmp     r10, rax
0x1400a4be2  jz      short loc_1400A4C0E
0x1400a4be4  mov     eax, [r10+2Ch]
0x1400a4be8  test    al, 1
0x1400a4bea  jz      short loc_1400A4C0E
0x1400a4bec  movzx   eax, byte ptr [r10+29h]
0x1400a4bf1  cmp     eax, ecx
0x1400a4bf3  jb      short loc_1400A4C0E
0x1400a4bf5  mov     rcx, [r10+18h]
0x1400a4bf9  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a4c00  mov     edx, 14h
0x1400a4c05  mov     [rsp+210h+DeviceCharacteristics], ebx
0x1400a4c09  call    WPP_SF_sd
0x1400a4c0e  mov     eax, ebx
0x1400a4c10  mov     rcx, [rbp+110h+var_40]
0x1400a4c17  xor     rcx, rsp; StackCookie
0x1400a4c1a  call    __security_check_cookie
0x1400a4c1f  mov     rbx, [rsp+210h+arg_0]
0x1400a4c27  add     rsp, 1E0h
0x1400a4c2e  pop     r15
0x1400a4c30  pop     r14
0x1400a4c32  pop     r13
0x1400a4c34  pop     r12
0x1400a4c36  pop     rdi
0x1400a4c37  pop     rsi
0x1400a4c38  pop     rbp
0x1400a4c39  retn
```
