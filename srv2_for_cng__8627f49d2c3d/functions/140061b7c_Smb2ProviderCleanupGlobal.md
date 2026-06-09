# Smb2ProviderCleanupGlobal

- ea: `0x140061b7c`
- end: `0x140061e4e`
- name: `Smb2ProviderCleanupGlobal`
- size: `722`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14005f440`
- `0x14005f538`
- `0x140061f44`

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
- `0x140061b7c`
- `0x140063790`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140061caa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e28`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e3b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061caa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e28`
- `ntoskrnl!ExDeleteResourceLite` at `0x140061e3b`
- `ntoskrnl!ZwClose` at `0x140061be4`
- `ntoskrnl!ZwClose` at `0x140061be4`
- `ntoskrnl!ObfDereferenceObject` at `0x140061bd1`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c1c`
- `ntoskrnl!ObfDereferenceObject` at `0x140061bd1`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061c7b`
- `srvnet!SrvLibS4U2SelfCleanup` at `0x140061c42`
- `srvnet!SrvLibS4U2SelfCleanup` at `0x140061c42`
- `srvnet!SmbCryptoKeyedHashUninitialize` at `0x140061cc8`
- `srvnet!SmbCryptoKeyedHashUninitialize` at `0x140061cc8`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140061d4a`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140061d4a`
- `srvnet!SrvLibFreeMemory` at `0x140061e0e`
- `srvnet!SrvLibFreeMemory` at `0x140061e0e`

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
0x140061b7c  push    rbx
0x140061b7e  sub     rsp, 20h
0x140061b82  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140061b89  lea     rax, WPP_GLOBAL_Control
0x140061b90  cmp     rcx, rax
0x140061b93  jz      short loc_140061BB9
0x140061b95  test    dword ptr [rcx+2Ch], 4000h
0x140061b9c  jz      short loc_140061BB9
0x140061b9e  cmp     byte ptr [rcx+29h], 2
0x140061ba2  jb      short loc_140061BB9
0x140061ba4  mov     rcx, [rcx+18h]
0x140061ba8  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x140061baf  mov     edx, 1Ah
0x140061bb4  call    WPP_SF_
0x140061bb9  mov     al, cs:byte_140058001
0x140061bbf  xor     ebx, ebx
0x140061bc1  test    al, 10h
0x140061bc3  jz      short loc_140061BFE
0x140061bc5  mov     rcx, cs:Smb2NamedPipeFileObject; Object
0x140061bcc  test    rcx, rcx
0x140061bcf  jz      short loc_140061BF0
0x140061bd1  call    cs:__imp_ObfDereferenceObject
0x140061bd8  nop     dword ptr [rax+rax+00h]
0x140061bdd  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x140061be4  call    cs:__imp_ZwClose
0x140061beb  nop     dword ptr [rax+rax+00h]
0x140061bf0  mov     al, cs:byte_140058001
0x140061bf6  and     al, 0EFh
0x140061bf8  mov     cs:byte_140058001, al
0x140061bfe  test    al, 8
0x140061c00  jz      short loc_140061C36
0x140061c02  mov     rcx, cs:Smb2DfsFileObject; Object
0x140061c09  test    rcx, rcx
0x140061c0c  jz      short loc_140061C2F
0x140061c0e  mov     cs:Smb2DfsFastIoDeviceControl, rbx
0x140061c15  mov     cs:Smb2DfsDeviceObject, rbx
0x140061c1c  call    cs:__imp_ObfDereferenceObject
0x140061c23  nop     dword ptr [rax+rax+00h]
0x140061c28  mov     cs:Smb2DfsFileObject, rbx
0x140061c2f  and     cs:byte_140058001, 0F7h
0x140061c36  mov     rcx, cs:Smb2S4U2SelfContext
0x140061c3d  test    rcx, rcx
0x140061c40  jz      short loc_140061C55
0x140061c42  call    cs:__imp_SrvLibS4U2SelfCleanup
0x140061c49  nop     dword ptr [rax+rax+00h]
0x140061c4e  mov     cs:Smb2S4U2SelfContext, rbx
0x140061c55  cmp     cs:Smb2NetnameTable, rbx
0x140061c5c  jz      short loc_140061C63
0x140061c5e  call    Smb2CleanupNetnameTable
0x140061c63  mov     al, cs:byte_140058001
0x140061c69  test    al, 4
0x140061c6b  jz      short loc_140061CC4
0x140061c6d  mov     rcx, cs:P; P
0x140061c74  test    rcx, rcx
0x140061c77  jz      short loc_140061CB6
0x140061c79  xor     edx, edx; Tag
0x140061c7b  call    cs:__imp_ExFreePoolWithTag
0x140061c82  nop     dword ptr [rax+rax+00h]
0x140061c87  lea     rax, Smb2VolumeCache
0x140061c8e  mov     cs:P, rbx
0x140061c95  lea     rcx, Resource; Resource
0x140061c9c  mov     cs:qword_14004B2E8, rax
0x140061ca3  mov     cs:Smb2VolumeCache, rax
0x140061caa  call    cs:__imp_ExDeleteResourceLite
0x140061cb1  nop     dword ptr [rax+rax+00h]
0x140061cb6  mov     al, cs:byte_140058001
0x140061cbc  and     al, 0FBh
0x140061cbe  mov     cs:byte_140058001, al
0x140061cc4  test    al, 1
0x140061cc6  jz      short loc_140061CE2
0x140061cc8  call    cs:__imp_SmbCryptoKeyedHashUninitialize
0x140061ccf  nop     dword ptr [rax+rax+00h]
0x140061cd4  mov     al, cs:byte_140058001
0x140061cda  and     al, 0FEh
0x140061cdc  mov     cs:byte_140058001, al
0x140061ce2  test    al, 2
0x140061ce4  jz      short loc_140061D0A
0x140061ce6  mov     rcx, cs:Smb2SigningHashObjectLookasideList; P
0x140061ced  test    rcx, rcx
0x140061cf0  jz      short loc_140061D03
0x140061cf2  mov     edx, 2453534Ch; Tag
0x140061cf7  call    PplDestroyLookasideList
0x140061cfc  mov     cs:Smb2SigningHashObjectLookasideList, rbx
0x140061d03  and     cs:byte_140058001, 0FDh
0x140061d0a  mov     rcx, cs:Smb2AppInstanceFileTableForCA; P
0x140061d11  test    rcx, rcx
0x140061d14  jz      short loc_140061D22
0x140061d16  call    RfsHashTableCleanup
0x140061d1b  mov     cs:Smb2AppInstanceFileTableForCA, rbx
0x140061d22  mov     rcx, cs:Smb2AppInstanceFileTableForNonCA; P
0x140061d29  test    rcx, rcx
0x140061d2c  jz      short loc_140061D3A
0x140061d2e  call    RfsHashTableCleanup
0x140061d33  mov     cs:Smb2AppInstanceFileTableForNonCA, rbx
0x140061d3a  test    cs:Smb2InitProgress, 40h
0x140061d41  jz      short loc_140061D64
0x140061d43  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x140061d4a  call    cs:__imp_SrvLibCloseCredentialHandle
0x140061d51  nop     dword ptr [rax+rax+00h]
0x140061d56  and     cs:Smb2InitProgress, 0BFh
0x140061d5d  mov     cs:Smb2ExtensibleCredentialHandle, rbx
0x140061d64  cmp     cs:Smb2ClientHashTable, rbx
0x140061d6b  jz      short loc_140061D79
0x140061d6d  call    Smb2CleanupClientHashTable
0x140061d72  mov     cs:Smb2ClientHashTable, rbx
0x140061d79  mov     al, cs:Smb2InitProgress
0x140061d7f  test    al, 4
0x140061d81  jz      short loc_140061D96
0x140061d83  call    Smb2DeinitializeLowMemLeaseBufferCache
0x140061d88  mov     al, cs:Smb2InitProgress
0x140061d8e  and     al, 0FBh
0x140061d90  mov     cs:Smb2InitProgress, al
0x140061d96  test    al, 1
0x140061d98  jz      short loc_140061DAD
0x140061d9a  call    Smb2CleanupScavenger
0x140061d9f  mov     al, cs:Smb2InitProgress
0x140061da5  and     al, 0FEh
0x140061da7  mov     cs:Smb2InitProgress, al
0x140061dad  test    al, 2
0x140061daf  jz      short loc_140061DC4
0x140061db1  call    Smb2CleanupSnapShotScavenger
0x140061db6  mov     al, cs:Smb2InitProgress
0x140061dbc  and     al, 0FDh
0x140061dbe  mov     cs:Smb2InitProgress, al
0x140061dc4  test    al, 20h
0x140061dc6  jz      short loc_140061DDB
0x140061dc8  call    Smb2DurableHandleCleanup
0x140061dcd  mov     al, cs:Smb2InitProgress
0x140061dd3  and     al, 0DFh
0x140061dd5  mov     cs:Smb2InitProgress, al
0x140061ddb  test    al, 10h
0x140061ddd  jz      short loc_140061DF2
0x140061ddf  call    Smb2CleanupOplockPackage
0x140061de4  mov     al, cs:Smb2InitProgress
0x140061dea  and     al, 0EFh
0x140061dec  mov     cs:Smb2InitProgress, al
0x140061df2  test    al, 8
0x140061df4  jz      short loc_140061E02
0x140061df6  call    Smb2CleanupSharesGlobal
0x140061dfb  and     cs:Smb2InitProgress, 0F7h
0x140061e02  mov     rcx, cs:Smb2RequireWindowsHelloForBusinessExceptionList
0x140061e09  test    rcx, rcx
0x140061e0c  jz      short loc_140061E21
0x140061e0e  call    cs:__imp_SrvLibFreeMemory
0x140061e15  nop     dword ptr [rax+rax+00h]
0x140061e1a  mov     cs:Smb2RequireWindowsHelloForBusinessExceptionList, rbx
0x140061e21  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140061e28  call    cs:__imp_ExDeleteResourceLite
0x140061e2f  nop     dword ptr [rax+rax+00h]
0x140061e34  lea     rcx, Smb2NameLock; Resource
0x140061e3b  call    cs:__imp_ExDeleteResourceLite
0x140061e42  nop     dword ptr [rax+rax+00h]
0x140061e47  add     rsp, 20h
0x140061e4b  pop     rbx
0x140061e4c  retn
```
