# SpCreateDevice(_GUID,_GUID,uchar,SP_DEVICE * *)

- ea: `0x1400a48e8`
- end: `0x1400a4d6b`
- name: `?SpCreateDevice@@YAJU_GUID@@0EPEAPEAVSP_DEVICE@@@Z`
- size: `1155`
- prototype: `int(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int8, struct SP_DEVICE **)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x14009d930`
- `0x14009f82c`

## callees

- `0x140019500`
- `0x14002b048`
- `0x14002ce90`
- `0x140032bd4`
- `0x140068110`
- `0x1400681e0`
- `0x140068600`
- `0x1400a48e8`
- `0x1400a4fd4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4c98`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a4c98`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a49c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4c6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a49c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a4c6a`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4b57`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4c36`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4b57`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a4c36`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4c7f`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a4c7f`
- `ntoskrnl!ObfReferenceObject` at `0x1400a4bfd`
- `ntoskrnl!ObfReferenceObject` at `0x1400a4bfd`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4acf`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4ae4`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4acf`
- `ntoskrnl!KeInitializeMutex` at `0x1400a4ae4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400a4b33`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400a4b33`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4b7d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a4b7d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4c19`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a4c19`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a498b`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1400a498b`
- `ntoskrnl!IoCreateDevice` at `0x1400a4a00`
- `ntoskrnl!IoCreateDevice` at `0x1400a4a00`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4afa`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400a4afa`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4b12`
- `ntoskrnl!KeInitializeEvent` at `0x1400a4b12`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a4a98`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a4a98`

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
0x1400a48e8  mov     [rsp-8+arg_0], rbx
0x1400a48ed  push    rbp
0x1400a48ee  push    rsi
0x1400a48ef  push    rdi
0x1400a48f0  push    r12
0x1400a48f2  push    r13
0x1400a48f4  push    r14
0x1400a48f6  push    r15
0x1400a48f8  lea     rbp, [rsp-0E0h]
0x1400a4900  sub     rsp, 1E0h
0x1400a4907  mov     rax, cs:__security_cookie
0x1400a490e  xor     rax, rsp
0x1400a4911  mov     [rbp+110h+var_40], rax
0x1400a4918  mov     r12b, r8b
0x1400a491b  mov     [rsp+210h+var_1D0], r8b
0x1400a4920  mov     rsi, rdx
0x1400a4923  mov     [rsp+210h+Buf2], rdx
0x1400a4928  mov     [rsp+210h+var_1A8], rcx
0x1400a492d  xorps   xmm0, xmm0
0x1400a4930  xor     edx, edx; Val
0x1400a4932  mov     [rsp+210h+var_1C8], 0
0x1400a493b  mov     r8d, 100h; Size
0x1400a4941  lea     rcx, [rbp+110h+SourceString]; void *
0x1400a4945  movups  xmmword ptr [rsp+210h+GuidString.Length], xmm0
0x1400a494a  mov     r13, r9
0x1400a494d  xor     edi, edi
0x1400a494f  call    memset
0x1400a4954  xorps   xmm0, xmm0
0x1400a4957  lea     ebx, [rdi+40h]
0x1400a495a  mov     r8d, ebx; Size
0x1400a495d  lea     rcx, [rbp+110h+pszDest]; void *
0x1400a4961  xor     edx, edx; Val
0x1400a4963  movups  xmmword ptr [rbp+110h+SymbolicLinkName.Length], xmm0
0x1400a4967  call    memset
0x1400a496c  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4973  lea     r15d, [rdi+1]
0x1400a4977  xorps   xmm0, xmm0
0x1400a497a  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x1400a497f  lock xadd [rax+148h], r15d
0x1400a4988  inc     r15d
0x1400a498b  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x1400a4992  nop     dword ptr [rax+rax+00h]
0x1400a4997  mov     r9d, r15d
0x1400a499a  lea     r8, aDeviceSpaceD; "\\Device\\Space%d"
0x1400a49a1  mov     edx, ebx; cbDest
0x1400a49a3  lea     rcx, [rbp+110h+pszDest]; pszDest
0x1400a49a7  mov     r14, rax
0x1400a49aa  call    RtlStringCbPrintfW
0x1400a49af  mov     ebx, eax
0x1400a49b1  test    eax, eax
0x1400a49b3  js      loc_1400A4C8B
0x1400a49b9  lea     rdx, [rbp+110h+pszDest]; SourceString
0x1400a49bd  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x1400a49c2  call    cs:__imp_RtlInitUnicodeString
0x1400a49c9  nop     dword ptr [rax+rax+00h]
0x1400a49ce  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a49d5  lea     rax, [rsp+210h+var_1C8]
0x1400a49da  mov     [rsp+210h+DeviceObject], rax; DeviceObject
0x1400a49df  lea     edx, [r14+0CF8h]; DeviceExtensionSize
0x1400a49e6  mov     [rsp+210h+Exclusive], dil; Exclusive
0x1400a49eb  lea     r9d, [rdi+2Dh]; DeviceType
0x1400a49ef  lea     r8, [rsp+210h+DestinationString]; DeviceName
0x1400a49f4  mov     [rsp+210h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1400a49fc  mov     rcx, [rcx+8]; DriverObject
0x1400a4a00  call    cs:__imp_IoCreateDevice
0x1400a4a07  nop     dword ptr [rax+rax+00h]
0x1400a4a0c  mov     ebx, eax
0x1400a4a0e  test    eax, eax
0x1400a4a10  js      loc_1400A4C8B
0x1400a4a16  mov     rax, [rsp+210h+var_1C8]
0x1400a4a1b  mov     rcx, [rax+40h]
0x1400a4a1f  lea     rax, qword_14006D850
0x1400a4a26  mov     [rcx], rax
0x1400a4a29  mov     rcx, [rsp+210h+var_1C8]; unsigned __int64
0x1400a4a2e  mov     rdx, [rcx+40h]
0x1400a4a32  add     rdx, 8; void *
0x1400a4a36  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a4a3b  test    rax, rax
0x1400a4a3e  jz      short loc_1400A4A50
0x1400a4a40  mov     rcx, rax; this
0x1400a4a43  call    ??0SP_DEVICE@@QEAA@XZ; SP_DEVICE::SP_DEVICE(void)
0x1400a4a48  mov     rcx, [rsp+210h+var_1C8]
0x1400a4a4d  mov     rdi, rax
0x1400a4a50  mov     rax, [rsp+210h+var_1A8]
0x1400a4a55  mov     [rdi+0A0h], rcx
0x1400a4a5c  movaps  xmm0, xmmword ptr [rax]
0x1400a4a5f  mov     al, r12b
0x1400a4a62  neg     al
0x1400a4a64  movdqu  xmmword ptr [rdi+18h], xmm0
0x1400a4a69  sbb     cl, cl
0x1400a4a6b  movaps  xmm1, xmmword ptr [rsi]
0x1400a4a6e  and     cl, 5
0x1400a4a71  inc     cl
0x1400a4a73  mov     word ptr [rdi+0A9h], 0
0x1400a4a7c  mov     [rdi+0A8h], cl
0x1400a4a82  movdqu  xmmword ptr [rdi+28h], xmm1
0x1400a4a87  mov     [rdi+0C20h], r15d
0x1400a4a8e  mov     dword ptr [rdi+0C40h], 0FFFFFFFFh
0x1400a4a98  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400a4a9f  nop     dword ptr [rax+rax+00h]
0x1400a4aa4  mov     [rdi+0CD0h], rax
0x1400a4aab  lea     r12, [rdi+8]
0x1400a4aaf  mov     [r12+8], r12
0x1400a4ab4  xor     edx, edx; Level
0x1400a4ab6  lea     rax, [rdi+0CF0h]
0x1400a4abd  mov     [r12], r12
0x1400a4ac1  lea     rcx, [rdi+0B0h]; Mutex
0x1400a4ac8  mov     [rdi+0F0h], rax
0x1400a4acf  call    cs:__imp_KeInitializeMutex
0x1400a4ad6  nop     dword ptr [rax+rax+00h]
0x1400a4adb  lea     rcx, [rdi+0C60h]; Mutex
0x1400a4ae2  xor     edx, edx; Level
0x1400a4ae4  call    cs:__imp_KeInitializeMutex
0x1400a4aeb  nop     dword ptr [rax+rax+00h]
0x1400a4af0  mov     rcx, [rdi+0F0h]; RunRefCacheAware
0x1400a4af7  mov     edx, r14d; RunRefSize
0x1400a4afa  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x1400a4b01  nop     dword ptr [rax+rax+00h]
0x1400a4b06  lea     rcx, [rdi+100h]; Event
0x1400a4b0d  xor     r8d, r8d; State
0x1400a4b10  xor     edx, edx; Type
0x1400a4b12  call    cs:__imp_KeInitializeEvent
0x1400a4b19  nop     dword ptr [rax+rax+00h]
0x1400a4b1e  lea     rax, [rdi+118h]
0x1400a4b25  lea     rcx, [rdi+128h]; SpinLock
0x1400a4b2c  mov     [rax+8], rax
0x1400a4b30  mov     [rax], rax
0x1400a4b33  call    cs:__imp_KeInitializeSpinLock
0x1400a4b3a  nop     dword ptr [rax+rax+00h]
0x1400a4b3f  lea     rax, [rdi+0C10h]
0x1400a4b46  mov     rcx, rsi; Guid
0x1400a4b49  lea     rdx, [rdi+0C30h]; GuidString
0x1400a4b50  mov     [rax+8], rax
0x1400a4b54  mov     [rax], rax
0x1400a4b57  call    cs:__imp_RtlStringFromGUID
0x1400a4b5e  nop     dword ptr [rax+rax+00h]
0x1400a4b63  mov     ebx, eax
0x1400a4b65  test    eax, eax
0x1400a4b67  js      loc_1400A4C8B
0x1400a4b6d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4b74  xor     edx, edx
0x1400a4b76  add     rcx, 140h
0x1400a4b7d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a4b84  nop     dword ptr [rax+rax+00h]
0x1400a4b89  mov     rsi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4b90  add     rsi, 130h
0x1400a4b97  mov     r15, [rsi]
0x1400a4b9a  cmp     r15, rsi
0x1400a4b9d  jz      short loc_1400A4BCD
0x1400a4b9f  lea     r14, [r15-8]
0x1400a4ba3  mov     al, [r14+0A8h]
0x1400a4baa  sub     al, 4
0x1400a4bac  cmp     al, 1
0x1400a4bae  jbe     short loc_1400A4BC8
0x1400a4bb0  mov     rdx, [rsp+210h+Buf2]; Buf2
0x1400a4bb5  lea     rcx, [r14+28h]; Buf1
0x1400a4bb9  mov     r8d, 10h; Size
0x1400a4bbf  call    memcmp
0x1400a4bc4  test    eax, eax
0x1400a4bc6  jz      short loc_1400A4BF2
0x1400a4bc8  mov     r15, [r15]
0x1400a4bcb  jmp     short loc_1400A4B9A
0x1400a4bcd  mov     rax, [rsi+8]
0x1400a4bd1  cmp     [rax], rsi
0x1400a4bd4  jz      short loc_1400A4BDD
0x1400a4bd6  mov     ecx, 3
0x1400a4bdb  int     29h; Win8: RtlFailFast(ecx)
0x1400a4bdd  mov     [r12], rsi
0x1400a4be1  mov     r14, rdi
0x1400a4be4  mov     [r12+8], rax
0x1400a4be9  xor     edi, edi
0x1400a4beb  mov     [rax], r12
0x1400a4bee  mov     [rsi+8], r12
0x1400a4bf2  mov     [r13+0], r14
0x1400a4bf6  mov     rcx, [r14+0A0h]; Object
0x1400a4bfd  call    cs:__imp_ObfReferenceObject
0x1400a4c04  nop     dword ptr [rax+rax+00h]
0x1400a4c09  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a4c10  xor     edx, edx
0x1400a4c12  add     rcx, 140h
0x1400a4c19  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a4c20  nop     dword ptr [rax+rax+00h]
0x1400a4c25  cmp     [rsp+210h+var_1D0], 0
0x1400a4c2a  jz      short loc_1400A4C8B
0x1400a4c2c  mov     rcx, [rsp+210h+Buf2]; Guid
0x1400a4c31  lea     rdx, [rsp+210h+GuidString]; GuidString
0x1400a4c36  call    cs:__imp_RtlStringFromGUID
0x1400a4c3d  nop     dword ptr [rax+rax+00h]
0x1400a4c42  mov     ebx, eax
0x1400a4c44  test    eax, eax
0x1400a4c46  js      short loc_1400A4C8B
0x1400a4c48  lea     r9, [rsp+210h+GuidString]
0x1400a4c4d  mov     edx, 100h; cbDest
0x1400a4c52  lea     r8, aDosdevicesGlob; "\\DosDevices\\Global\\Space#%wZ"
0x1400a4c59  lea     rcx, [rbp+110h+SourceString]; pszDest
0x1400a4c5d  call    RtlStringCbPrintfW
0x1400a4c62  lea     rdx, [rbp+110h+SourceString]; SourceString
0x1400a4c66  lea     rcx, [rbp+110h+SymbolicLinkName]; DestinationString
0x1400a4c6a  call    cs:__imp_RtlInitUnicodeString
0x1400a4c71  nop     dword ptr [rax+rax+00h]
0x1400a4c76  lea     rdx, [rsp+210h+DestinationString]; DeviceName
0x1400a4c7b  lea     rcx, [rbp+110h+SymbolicLinkName]; SymbolicLinkName
0x1400a4c7f  call    cs:__imp_IoCreateSymbolicLink
0x1400a4c86  nop     dword ptr [rax+rax+00h]
0x1400a4c8b  cmp     [rsp+210h+GuidString.Buffer], 0
0x1400a4c91  jz      short loc_1400A4CA4
0x1400a4c93  lea     rcx, [rsp+210h+GuidString]; UnicodeString
0x1400a4c98  call    cs:__imp_RtlFreeUnicodeString
0x1400a4c9f  nop     dword ptr [rax+rax+00h]
0x1400a4ca4  test    rdi, rdi
0x1400a4ca7  jz      short loc_1400A4CB1
0x1400a4ca9  mov     rcx, rdi; struct SP_DEVICE *
0x1400a4cac  call    ?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z; SpDeleteDevice(SP_DEVICE *)
0x1400a4cb1  test    ebx, ebx
0x1400a4cb3  jns     short loc_1400A4CE4
0x1400a4cb5  cmp     ebx, 80000005h
0x1400a4cbb  jz      short loc_1400A4CE4
0x1400a4cbd  cmp     ebx, 0C0000023h
0x1400a4cc3  jz      short loc_1400A4CE4
0x1400a4cc5  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a4ccb  cmp     ecx, 1
0x1400a4cce  jz      short loc_1400A4CDB
0x1400a4cd0  mov     ecx, 1
0x1400a4cd5  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a4cdb  lea     r9, aError; "Error"
0x1400a4ce2  jmp     short loc_1400A4D01
0x1400a4ce4  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a4cea  cmp     ecx, 3
0x1400a4ced  jz      short loc_1400A4CFA
0x1400a4cef  mov     ecx, 3
0x1400a4cf4  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a4cfa  lea     r9, aExit; "Exit "
0x1400a4d01  mov     r10, cs:WPP_GLOBAL_Control
0x1400a4d08  lea     rax, WPP_GLOBAL_Control
0x1400a4d0f  cmp     r10, rax
0x1400a4d12  jz      short loc_1400A4D3E
0x1400a4d14  mov     eax, [r10+2Ch]
0x1400a4d18  test    al, 1
0x1400a4d1a  jz      short loc_1400A4D3E
0x1400a4d1c  movzx   eax, byte ptr [r10+29h]
0x1400a4d21  cmp     eax, ecx
0x1400a4d23  jb      short loc_1400A4D3E
0x1400a4d25  mov     rcx, [r10+18h]
0x1400a4d29  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a4d30  mov     edx, 14h
0x1400a4d35  mov     [rsp+210h+DeviceCharacteristics], ebx
0x1400a4d39  call    WPP_SF_sd
0x1400a4d3e  mov     eax, ebx
0x1400a4d40  mov     rcx, [rbp+110h+var_40]
0x1400a4d47  xor     rcx, rsp; StackCookie
0x1400a4d4a  call    __security_check_cookie
0x1400a4d4f  mov     rbx, [rsp+210h+arg_0]
0x1400a4d57  add     rsp, 1E0h
0x1400a4d5e  pop     r15
0x1400a4d60  pop     r14
0x1400a4d62  pop     r13
0x1400a4d64  pop     r12
0x1400a4d66  pop     rdi
0x1400a4d67  pop     rsi
0x1400a4d68  pop     rbp
0x1400a4d69  retn
```
