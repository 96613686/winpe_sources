# Smb2ProviderCleanupGlobal

- ea: `0x140061bcc`
- end: `0x140061e9e`
- name: `Smb2ProviderCleanupGlobal`
- size: `722`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14005f440`
- `0x14005f538`
- `0x140061f94`

## callees

- `0x14001880c`
- `0x14002019c`
- `0x1400227ac`
- `0x140025504`
- `0x14002952c`
- `0x1400295d0`
- `0x14002bd1c`
- `0x14002d864`
- `0x14002eb60`
- `0x14002fbf0`
- `0x140061bcc`
- `0x1400637e0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140061cfa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e78`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e8b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061cfa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e78`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e8b`
- `ntoskrnl!ZwClose` at `0x140061c34`
- `ntoskrnl!ZwClose` at `0x140061c34`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c21`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c6c`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c21`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061ccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061ccb`
- `srvnet!SrvLibS4U2SelfCleanup` at `0x140061c92`
- `srvnet!SrvLibS4U2SelfCleanup` at `0x140061c92`
- `srvnet!SmbCryptoKeyedHashUninitialize` at `0x140061d18`
- `srvnet!SmbCryptoKeyedHashUninitialize` at `0x140061d18`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140061d9a`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140061d9a`
- `srvnet!SrvLibFreeMemory` at `0x140061e5e`
- `srvnet!SrvLibFreeMemory` at `0x140061e5e`

## pseudocode

```c
NTSTATUS Smb2ProviderCleanupGlobal()
{
  char v0; // al
  char v1; // al
  char v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids);
  }
  v0 = byte_140058001;
  if ( (byte_140058001 & 0x10) != 0 )
  {
    if ( Smb2NamedPipeFileObject )
    {
      ObfDereferenceObject(Smb2NamedPipeFileObject);
      ZwClose(Smb2NamedPipeHandle);
    }
    v0 = byte_140058001 & 0xEF;
    byte_140058001 &= ~0x10u;
  }
  if ( (v0 & 8) != 0 )
  {
    if ( Smb2DfsFileObject )
    {
      Smb2DfsFastIoDeviceControl = 0;
      Smb2DfsDeviceObject = 0;
      ObfDereferenceObject(Smb2DfsFileObject);
      Smb2DfsFileObject = 0;
    }
    byte_140058001 &= ~8u;
  }
  if ( Smb2S4U2SelfContext )
  {
    SrvLibS4U2SelfCleanup();
    Smb2S4U2SelfContext = 0;
  }
  if ( Smb2NetnameTable )
    Smb2CleanupNetnameTable();
  v1 = byte_140058001;
  if ( (byte_140058001 & 4) != 0 )
  {
    if ( P )
    {
      ExFreePoolWithTag(P, 0);
      P = 0;
      qword_14004B2E8 = (__int64)&Smb2VolumeCache;
      Smb2VolumeCache = (__int64)&Smb2VolumeCache;
      ExDeleteResourceLite(&Resource);
    }
    v1 = byte_140058001 & 0xFB;
    byte_140058001 &= ~4u;
  }
  if ( (v1 & 1) != 0 )
  {
    SmbCryptoKeyedHashUninitialize();
    v1 = byte_140058001 & 0xFE;
    byte_140058001 &= ~1u;
  }
  if ( (v1 & 2) != 0 )
  {
    if ( Smb2SigningHashObjectLookasideList )
    {
      PplDestroyLookasideList(Smb2SigningHashObjectLookasideList, 0x2453534Cu);
      Smb2SigningHashObjectLookasideList = 0;
    }
    byte_140058001 &= ~2u;
  }
  if ( Smb2AppInstanceFileTableForCA )
  {
    RfsHashTableCleanup(Smb2AppInstanceFileTableForCA);
    Smb2AppInstanceFileTableForCA = 0;
  }
  if ( Smb2AppInstanceFileTableForNonCA )
  {
    RfsHashTableCleanup(Smb2AppInstanceFileTableForNonCA);
    Smb2AppInstanceFileTableForNonCA = 0;
  }
  if ( (Smb2InitProgress & 0x40) != 0 )
  {
    SrvLibCloseCredentialHandle(Smb2ExtensibleCredentialHandle);
    Smb2InitProgress &= ~0x40u;
    Smb2ExtensibleCredentialHandle = 0;
  }
  if ( Smb2ClientHashTable )
  {
    Smb2CleanupClientHashTable();
    Smb2ClientHashTable = 0;
  }
  v2 = Smb2InitProgress;
  if ( (Smb2InitProgress & 4) != 0 )
  {
    Smb2DeinitializeLowMemLeaseBufferCache();
    v2 = Smb2InitProgress & 0xFB;
    Smb2InitProgress &= ~4u;
  }
  if ( (v2 & 1) != 0 )
  {
    Smb2CleanupScavenger();
    v2 = Smb2InitProgress & 0xFE;
    Smb2InitProgress &= ~1u;
  }
  if ( (v2 & 2) != 0 )
  {
    Smb2CleanupSnapShotScavenger();
    v2 = Smb2InitProgress & 0xFD;
    Smb2InitProgress &= ~2u;
  }
  if ( (v2 & 0x20) != 0 )
  {
    Smb2DurableHandleCleanup();
    v2 = Smb2InitProgress & 0xDF;
    Smb2InitProgress &= ~0x20u;
  }
  if ( (v2 & 0x10) != 0 )
  {
    Smb2CleanupOplockPackage();
    v2 = Smb2InitProgress & 0xEF;
    Smb2InitProgress &= ~0x10u;
  }
  if ( (v2 & 8) != 0 )
  {
    Smb2CleanupSharesGlobal();
    Smb2InitProgress &= ~8u;
  }
  if ( Smb2RequireWindowsHelloForBusinessExceptionList )
  {
    SrvLibFreeMemory();
    Smb2RequireWindowsHelloForBusinessExceptionList = 0;
  }
  ExDeleteResourceLite(&Smb2ExtensibleCredHandleLock);
  return ExDeleteResourceLite(&Smb2NameLock);
}

```

## disassembly

```asm
0x140061bcc  push    rbx
0x140061bce  sub     rsp, 20h
0x140061bd2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140061bd9  lea     rax, WPP_GLOBAL_Control
0x140061be0  cmp     rcx, rax
0x140061be3  jz      short loc_140061C09
0x140061be5  test    dword ptr [rcx+2Ch], 4000h
0x140061bec  jz      short loc_140061C09
0x140061bee  cmp     byte ptr [rcx+29h], 2
0x140061bf2  jb      short loc_140061C09
0x140061bf4  mov     rcx, [rcx+18h]
0x140061bf8  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x140061bff  mov     edx, 1Ah
0x140061c04  call    WPP_SF_
0x140061c09  mov     al, cs:byte_140058001
0x140061c0f  xor     ebx, ebx
0x140061c11  test    al, 10h
0x140061c13  jz      short loc_140061C4E
0x140061c15  mov     rcx, cs:Smb2NamedPipeFileObject; Object
0x140061c1c  test    rcx, rcx
0x140061c1f  jz      short loc_140061C40
0x140061c21  call    cs:__imp_ObfDereferenceObject
0x140061c28  nop     dword ptr [rax+rax+00h]
0x140061c2d  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x140061c34  call    cs:__imp_ZwClose
0x140061c3b  nop     dword ptr [rax+rax+00h]
0x140061c40  mov     al, cs:byte_140058001
0x140061c46  and     al, 0EFh
0x140061c48  mov     cs:byte_140058001, al
0x140061c4e  test    al, 8
0x140061c50  jz      short loc_140061C86
0x140061c52  mov     rcx, cs:Smb2DfsFileObject; Object
0x140061c59  test    rcx, rcx
0x140061c5c  jz      short loc_140061C7F
0x140061c5e  mov     cs:Smb2DfsFastIoDeviceControl, rbx
0x140061c65  mov     cs:Smb2DfsDeviceObject, rbx
0x140061c6c  call    cs:__imp_ObfDereferenceObject
0x140061c73  nop     dword ptr [rax+rax+00h]
0x140061c78  mov     cs:Smb2DfsFileObject, rbx
0x140061c7f  and     cs:byte_140058001, 0F7h
0x140061c86  mov     rcx, cs:Smb2S4U2SelfContext
0x140061c8d  test    rcx, rcx
0x140061c90  jz      short loc_140061CA5
0x140061c92  call    cs:__imp_SrvLibS4U2SelfCleanup
0x140061c99  nop     dword ptr [rax+rax+00h]
0x140061c9e  mov     cs:Smb2S4U2SelfContext, rbx
0x140061ca5  cmp     cs:Smb2NetnameTable, rbx
0x140061cac  jz      short loc_140061CB3
0x140061cae  call    Smb2CleanupNetnameTable
0x140061cb3  mov     al, cs:byte_140058001
0x140061cb9  test    al, 4
0x140061cbb  jz      short loc_140061D14
0x140061cbd  mov     rcx, cs:P; P
0x140061cc4  test    rcx, rcx
0x140061cc7  jz      short loc_140061D06
0x140061cc9  xor     edx, edx; Tag
0x140061ccb  call    cs:__imp_ExFreePoolWithTag
0x140061cd2  nop     dword ptr [rax+rax+00h]
0x140061cd7  lea     rax, Smb2VolumeCache
0x140061cde  mov     cs:P, rbx
0x140061ce5  lea     rcx, Resource; Resource
0x140061cec  mov     cs:qword_14004B2E8, rax
0x140061cf3  mov     cs:Smb2VolumeCache, rax
0x140061cfa  call    cs:__imp_ExDeleteResourceLite
0x140061d01  nop     dword ptr [rax+rax+00h]
0x140061d06  mov     al, cs:byte_140058001
0x140061d0c  and     al, 0FBh
0x140061d0e  mov     cs:byte_140058001, al
0x140061d14  test    al, 1
0x140061d16  jz      short loc_140061D32
0x140061d18  call    cs:__imp_SmbCryptoKeyedHashUninitialize
0x140061d1f  nop     dword ptr [rax+rax+00h]
0x140061d24  mov     al, cs:byte_140058001
0x140061d2a  and     al, 0FEh
0x140061d2c  mov     cs:byte_140058001, al
0x140061d32  test    al, 2
0x140061d34  jz      short loc_140061D5A
0x140061d36  mov     rcx, cs:Smb2SigningHashObjectLookasideList; P
0x140061d3d  test    rcx, rcx
0x140061d40  jz      short loc_140061D53
0x140061d42  mov     edx, 2453534Ch; Tag
0x140061d47  call    PplDestroyLookasideList
0x140061d4c  mov     cs:Smb2SigningHashObjectLookasideList, rbx
0x140061d53  and     cs:byte_140058001, 0FDh
0x140061d5a  mov     rcx, cs:Smb2AppInstanceFileTableForCA; P
0x140061d61  test    rcx, rcx
0x140061d64  jz      short loc_140061D72
0x140061d66  call    RfsHashTableCleanup
0x140061d6b  mov     cs:Smb2AppInstanceFileTableForCA, rbx
0x140061d72  mov     rcx, cs:Smb2AppInstanceFileTableForNonCA; P
0x140061d79  test    rcx, rcx
0x140061d7c  jz      short loc_140061D8A
0x140061d7e  call    RfsHashTableCleanup
0x140061d83  mov     cs:Smb2AppInstanceFileTableForNonCA, rbx
0x140061d8a  test    cs:Smb2InitProgress, 40h
0x140061d91  jz      short loc_140061DB4
0x140061d93  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x140061d9a  call    cs:__imp_SrvLibCloseCredentialHandle
0x140061da1  nop     dword ptr [rax+rax+00h]
0x140061da6  and     cs:Smb2InitProgress, 0BFh
0x140061dad  mov     cs:Smb2ExtensibleCredentialHandle, rbx
0x140061db4  cmp     cs:Smb2ClientHashTable, rbx
0x140061dbb  jz      short loc_140061DC9
0x140061dbd  call    Smb2CleanupClientHashTable
0x140061dc2  mov     cs:Smb2ClientHashTable, rbx
0x140061dc9  mov     al, cs:Smb2InitProgress
0x140061dcf  test    al, 4
0x140061dd1  jz      short loc_140061DE6
0x140061dd3  call    Smb2DeinitializeLowMemLeaseBufferCache
0x140061dd8  mov     al, cs:Smb2InitProgress
0x140061dde  and     al, 0FBh
0x140061de0  mov     cs:Smb2InitProgress, al
0x140061de6  test    al, 1
0x140061de8  jz      short loc_140061DFD
0x140061dea  call    Smb2CleanupScavenger
0x140061def  mov     al, cs:Smb2InitProgress
0x140061df5  and     al, 0FEh
0x140061df7  mov     cs:Smb2InitProgress, al
0x140061dfd  test    al, 2
0x140061dff  jz      short loc_140061E14
0x140061e01  call    Smb2CleanupSnapShotScavenger
0x140061e06  mov     al, cs:Smb2InitProgress
0x140061e0c  and     al, 0FDh
0x140061e0e  mov     cs:Smb2InitProgress, al
0x140061e14  test    al, 20h
0x140061e16  jz      short loc_140061E2B
0x140061e18  call    Smb2DurableHandleCleanup
0x140061e1d  mov     al, cs:Smb2InitProgress
0x140061e23  and     al, 0DFh
0x140061e25  mov     cs:Smb2InitProgress, al
0x140061e2b  test    al, 10h
0x140061e2d  jz      short loc_140061E42
0x140061e2f  call    Smb2CleanupOplockPackage
0x140061e34  mov     al, cs:Smb2InitProgress
0x140061e3a  and     al, 0EFh
0x140061e3c  mov     cs:Smb2InitProgress, al
0x140061e42  test    al, 8
0x140061e44  jz      short loc_140061E52
0x140061e46  call    Smb2CleanupSharesGlobal
0x140061e4b  and     cs:Smb2InitProgress, 0F7h
0x140061e52  mov     rcx, cs:Smb2RequireWindowsHelloForBusinessExceptionList
0x140061e59  test    rcx, rcx
0x140061e5c  jz      short loc_140061E71
0x140061e5e  call    cs:__imp_SrvLibFreeMemory
0x140061e65  nop     dword ptr [rax+rax+00h]
0x140061e6a  mov     cs:Smb2RequireWindowsHelloForBusinessExceptionList, rbx
0x140061e71  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140061e78  call    cs:__imp_ExDeleteResourceLite
0x140061e7f  nop     dword ptr [rax+rax+00h]
0x140061e84  lea     rcx, Smb2NameLock; Resource
0x140061e8b  call    cs:__imp_ExDeleteResourceLite
0x140061e92  nop     dword ptr [rax+rax+00h]
0x140061e97  add     rsp, 20h
0x140061e9b  pop     rbx
0x140061e9c  retn
```
