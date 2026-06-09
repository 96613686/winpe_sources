# SecInitializePackageControl

- ea: `0x18000cce4`
- end: `0x18000cf6f`
- name: `SecInitializePackageControl`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cb04`

## callees

- `0x18000cce4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000cdbf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cdbf`
- `ntdll!RtlReleaseResource` at `0x18000ce40`
- `ntdll!RtlReleaseResource` at `0x18000cee6`
- `ntdll!RtlReleaseResource` at `0x18000cf16`
- `ntdll!RtlReleaseResource` at `0x18000ce40`
- `ntdll!RtlReleaseResource` at `0x18000cee6`
- `ntdll!RtlReleaseResource` at `0x18000cf16`
- `ntdll!RtlDeleteCriticalSection` at `0x18000cf2f`
- `ntdll!RtlDeleteCriticalSection` at `0x18000cf2f`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ce17`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ce17`
- `ntdll!RtlDeleteResource` at `0x18000ce69`
- `ntdll!RtlDeleteResource` at `0x18000cf4a`
- `ntdll!RtlDeleteResource` at `0x18000ce69`
- `ntdll!RtlDeleteResource` at `0x18000cf4a`
- `ntdll!RtlInitializeResource` at `0x18000cd77`
- `ntdll!RtlInitializeResource` at `0x18000cd77`
- `ntdll!RtlGetNtProductType` at `0x18000cd25`
- `ntdll!RtlGetNtProductType` at `0x18000cd25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ceb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ceb2`

## pseudocode

```c
__int64 __fastcall SecInitializePackageControl(__int64 a1)
{
  unsigned int v2; // ebx
  ULONG NumberOfProcessors; // esi
  unsigned int v4; // eax
  unsigned int i; // r14d
  unsigned int j; // r14d
  unsigned int v7; // r14d
  unsigned int k; // r14d
  _NT_PRODUCT_TYPE ProductType; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  ProductType = 0;
  NumberOfProcessors = NtCurrentPeb()->NumberOfProcessors;
  SecPackageListLockCount = 1;
  RtlGetNtProductType(&ProductType);
  if ( (unsigned int)(ProductType - 2) <= 1 )
  {
    v4 = NumberOfProcessors + 1;
    if ( (NumberOfProcessors & 1) == 0 )
      v4 = NumberOfProcessors;
    if ( v4 > 4 )
      v4 = 4;
    if ( v4 )
      SecPackageListLockCount = v4;
  }
  for ( i = 0; i < SecPackageListLockCount; ++i )
    RtlInitializeResource((PRTL_RESOURCE)&SecPackageListLock[12 * i]);
  for ( j = 0; j < SecPackageListLockCount; ++j )
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * j], 1u);
  qword_18003FED0 = (__int64)&SecPackageControlList;
  SecPackageControlList = &SecPackageControlList;
  qword_18003FEC0 = (__int64)&SecSaslProfileList;
  SecSaslProfileList = &SecSaslProfileList;
  qword_180040000 = (__int64)&SaslContextList;
  SaslContextList = (struct _SASL_CONTEXT *)&SaslContextList;
  if ( RtlInitializeCriticalSection(&SaslLock) < 0 )
  {
    v7 = 0;
    if ( SecPackageListLockCount )
    {
      do
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v7++]);
      while ( v7 < SecPackageListLockCount );
      if ( SecPackageListLockCount )
      {
        do
          RtlDeleteResource((PRTL_RESOURCE)&SecPackageListLock[12 * v2++]);
        while ( v2 < SecPackageListLockCount );
      }
    }
    return 0;
  }
  SecPackageLsaLoaded = 0;
  SecPackageSspiLoaded = 0;
  SecPackageLoadInProgress = 0;
  SecpBuiltinBinding = 2;
  dword_18003FE90 = 1;
  qword_18003FE78 = a1;
  SecPackageDllList = LocalAlloc(0, 0x20u);
  if ( !SecPackageDllList )
  {
    for ( k = 0; k < SecPackageListLockCount; ++k )
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * k]);
    RtlDeleteCriticalSection(&SaslLock);
    if ( SecPackageListLockCount )
    {
      do
        RtlDeleteResource((PRTL_RESOURCE)&SecPackageListLock[12 * v2++]);
      while ( v2 < SecPackageListLockCount );
    }
    return 0;
  }
  SecPackageDllCount = 0;
  SecPackageDllTotal = 4;
  if ( SecPackageListLockCount )
  {
    do
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v2++]);
    while ( v2 < SecPackageListLockCount );
  }
  return 1;
}

```

## disassembly

```asm
0x18000cce4  mov     [rsp+arg_10], rbx
0x18000cce9  mov     [rsp+arg_0], rcx
0x18000ccee  push    rsi
0x18000ccef  push    r12
0x18000ccf1  push    r13
0x18000ccf3  push    r14
0x18000ccf5  push    r15
0x18000ccf7  sub     rsp, 20h
0x18000ccfb  mov     r13, rcx
0x18000ccfe  xor     ebx, ebx
0x18000cd00  mov     r12d, ebx
0x18000cd03  mov     [rsp+48h+ProductType], ebx
0x18000cd07  mov     rax, gs:60h
0x18000cd10  mov     esi, [rax+0B8h]
0x18000cd16  mov     cs:SecPackageListLockCount, 1
0x18000cd20  lea     rcx, [rsp+48h+ProductType]; ProductType
0x18000cd25  call    cs:__imp_RtlGetNtProductType
0x18000cd2b  mov     eax, [rsp+48h+ProductType]
0x18000cd2f  add     eax, 0FFFFFFFEh
0x18000cd32  lea     r15d, [rbx+4]
0x18000cd36  cmp     eax, 1
0x18000cd39  ja      short loc_18000CD56
0x18000cd3b  test    sil, 1
0x18000cd3f  lea     eax, [rsi+1]
0x18000cd42  cmovz   eax, esi
0x18000cd45  cmp     eax, r15d
0x18000cd48  cmova   eax, r15d
0x18000cd4c  test    eax, eax
0x18000cd4e  jz      short loc_18000CD56
0x18000cd50  mov     cs:SecPackageListLockCount, eax
0x18000cd56  mov     r14d, ebx
0x18000cd59  lea     rsi, SecPackageListLock
0x18000cd60  cmp     r14d, cs:SecPackageListLockCount
0x18000cd67  jnb     short loc_18000CD9B
0x18000cd69  mov     eax, r14d
0x18000cd6c  lea     rcx, [rax+rax*2]
0x18000cd70  shl     rcx, 5
0x18000cd74  add     rcx, rsi; Resource
0x18000cd77  call    cs:__imp_RtlInitializeResource
0x18000cd7d  nop
0x18000cd7e  inc     r14d
0x18000cd81  jmp     short loc_18000CD60
0x18000cd83  xor     ebx, ebx
0x18000cd85  mov     r12d, 0C000009Ah
0x18000cd8b  lea     r15d, [rbx+4]
0x18000cd8f  lea     rsi, SecPackageListLock
0x18000cd96  mov     r13, [rsp+48h+arg_0]
0x18000cd9b  test    r12d, r12d
0x18000cd9e  js      loc_18000CF5A
0x18000cda4  mov     r14d, ebx
0x18000cda7  cmp     cs:SecPackageListLockCount, ebx
0x18000cdad  jbe     short loc_18000CDD1
0x18000cdaf  mov     eax, r14d
0x18000cdb2  lea     rcx, [rax+rax*2]
0x18000cdb6  shl     rcx, 5
0x18000cdba  add     rcx, rsi; Resource
0x18000cdbd  mov     dl, 1; Wait
0x18000cdbf  call    cs:__imp_RtlAcquireResourceExclusive
0x18000cdc5  inc     r14d
0x18000cdc8  cmp     r14d, cs:SecPackageListLockCount
0x18000cdcf  jb      short loc_18000CDAF
0x18000cdd1  lea     rax, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000cdd8  mov     cs:qword_18003FED0, rax
0x18000cddf  mov     cs:?SecPackageControlList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY SecPackageControlList
0x18000cde6  lea     rax, ?SecSaslProfileList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecSaslProfileList
0x18000cded  mov     cs:qword_18003FEC0, rax
0x18000cdf4  mov     cs:?SecSaslProfileList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY SecSaslProfileList
0x18000cdfb  lea     rax, SaslContextList
0x18000ce02  mov     cs:qword_180040000, rax
0x18000ce09  mov     cs:SaslContextList, rax
0x18000ce10  lea     rcx, SaslLock; CriticalSection
0x18000ce17  call    cs:__imp_RtlInitializeCriticalSection
0x18000ce1d  test    eax, eax
0x18000ce1f  jns     short loc_18000CE7E
0x18000ce21  mov     r14d, ebx
0x18000ce24  mov     eax, cs:SecPackageListLockCount
0x18000ce2a  test    eax, eax
0x18000ce2c  jz      loc_18000CF5A
0x18000ce32  mov     eax, r14d
0x18000ce35  lea     rcx, [rax+rax*2]
0x18000ce39  shl     rcx, 5
0x18000ce3d  add     rcx, rsi; Resource
0x18000ce40  call    cs:__imp_RtlReleaseResource
0x18000ce46  inc     r14d
0x18000ce49  mov     eax, cs:SecPackageListLockCount
0x18000ce4f  cmp     r14d, eax
0x18000ce52  jb      short loc_18000CE32
0x18000ce54  test    eax, eax
0x18000ce56  jz      loc_18000CF5A
0x18000ce5c  mov     eax, ebx
0x18000ce5e  lea     rcx, [rax+rax*2]
0x18000ce62  shl     rcx, 5
0x18000ce66  add     rcx, rsi; Resource
0x18000ce69  call    cs:__imp_RtlDeleteResource
0x18000ce6f  inc     ebx
0x18000ce71  cmp     ebx, cs:SecPackageListLockCount
0x18000ce77  jb      short loc_18000CE5C
0x18000ce79  jmp     loc_18000CF5A
0x18000ce7e  mov     cs:?SecPackageLsaLoaded@@3HA, ebx; int SecPackageLsaLoaded
0x18000ce84  mov     cs:?SecPackageSspiLoaded@@3HA, ebx; int SecPackageSspiLoaded
0x18000ce8a  mov     cs:?SecPackageLoadInProgress@@3HA, ebx; int SecPackageLoadInProgress
0x18000ce90  mov     cs:?SecpBuiltinBinding@@3U_SECP_DLL_BINDING@@A, 2; _SECP_DLL_BINDING SecpBuiltinBinding
0x18000ce9a  mov     cs:dword_18003FE90, 1
0x18000cea4  mov     cs:qword_18003FE78, r13
0x18000ceab  mov     edx, 20h ; ' '; uBytes
0x18000ceb0  xor     ecx, ecx; uFlags
0x18000ceb2  call    cs:__imp_LocalAlloc
0x18000ceb8  mov     cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA, rax; _SECP_DLL_BINDING * * SecPackageDllList
0x18000cebf  test    rax, rax
0x18000cec2  jz      short loc_18000CEFD
0x18000cec4  mov     cs:?SecPackageDllCount@@3KA, ebx; ulong SecPackageDllCount
0x18000ceca  mov     cs:?SecPackageDllTotal@@3KA, r15d; ulong SecPackageDllTotal
0x18000ced1  cmp     cs:SecPackageListLockCount, ebx
0x18000ced7  jbe     short loc_18000CEF6
0x18000ced9  mov     ecx, ebx
0x18000cedb  lea     rcx, [rcx+rcx*2]
0x18000cedf  shl     rcx, 5
0x18000cee3  add     rcx, rsi; Resource
0x18000cee6  call    cs:__imp_RtlReleaseResource
0x18000ceec  inc     ebx
0x18000ceee  cmp     ebx, cs:SecPackageListLockCount
0x18000cef4  jb      short loc_18000CED9
0x18000cef6  mov     eax, 1
0x18000cefb  jmp     short loc_18000CF5C
0x18000cefd  mov     r14d, ebx
0x18000cf00  cmp     cs:SecPackageListLockCount, ebx
0x18000cf06  jbe     short loc_18000CF28
0x18000cf08  mov     eax, r14d
0x18000cf0b  lea     rcx, [rax+rax*2]
0x18000cf0f  shl     rcx, 5
0x18000cf13  add     rcx, rsi; Resource
0x18000cf16  call    cs:__imp_RtlReleaseResource
0x18000cf1c  inc     r14d
0x18000cf1f  cmp     r14d, cs:SecPackageListLockCount
0x18000cf26  jb      short loc_18000CF08
0x18000cf28  lea     rcx, SaslLock; CriticalSection
0x18000cf2f  call    cs:__imp_RtlDeleteCriticalSection
0x18000cf35  cmp     cs:SecPackageListLockCount, ebx
0x18000cf3b  jbe     short loc_18000CF5A
0x18000cf3d  mov     eax, ebx
0x18000cf3f  lea     rcx, [rax+rax*2]
0x18000cf43  shl     rcx, 5
0x18000cf47  add     rcx, rsi; Resource
0x18000cf4a  call    cs:__imp_RtlDeleteResource
0x18000cf50  inc     ebx
0x18000cf52  cmp     ebx, cs:SecPackageListLockCount
0x18000cf58  jb      short loc_18000CF3D
0x18000cf5a  xor     eax, eax
0x18000cf5c  mov     rbx, [rsp+48h+arg_10]
0x18000cf61  add     rsp, 20h
0x18000cf65  pop     r15
0x18000cf67  pop     r14
0x18000cf69  pop     r13
0x18000cf6b  pop     r12
0x18000cf6d  pop     rsi
0x18000cf6e  retn
```
