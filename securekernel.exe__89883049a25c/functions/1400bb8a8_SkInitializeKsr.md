# SkInitializeKsr

- ea: `0x1400bb8a8`
- end: `0x1400bbc39`
- name: `SkInitializeKsr`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x1400b86ec`

## callees

- `0x140059dcc`
- `0x14008938c`
- `0x1400bb8a8`
- `0x1400f9a80`

## import_xrefs

- `skci!SkciValidateImageData` at `0x1400bbad0`
- `skci!SkciCreateSecureImage` at `0x1400bbac5`
- `skci!SkciFreeImageContext` at `0x1400bbaf7`
- `skci!SkciFinishImageValidation` at `0x1400bbae9`
- `skci!SkciFinalizeSecureImageHash` at `0x1400bbadb`
- `ext-ms-win-ntos-ksr-l1-1-0!KsrSkInitSystem` at `0x1400bbbf3`
- `ext-ms-win-ntos-ksr-l1-1-0!KsrSkInitSystem` at `0x1400bbbf3`

## pseudocode

```c
__int64 SkInitializeKsr()
{
  __int64 v0; // rcx
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  char v4; // al
  __int64 (__fastcall *v5)(char, char, __int64, __int64, unsigned int, unsigned int, unsigned int, int, void *); // rcx
  __int64 result; // rax
  __int64 v7; // rcx
  _QWORD v8[24]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall *v9)(char, char, __int64, __int64, unsigned int, unsigned int, unsigned int, int, void *); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v10)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v11)(); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v12)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v13)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v14)(_QWORD); // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v15)(_QWORD); // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v16)(_QWORD); // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v17)(); // [rsp+140h] [rbp+40h]
  __int64 (__fastcall *v18)(__int64, unsigned __int64); // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v19)(_QWORD, _QWORD); // [rsp+150h] [rbp+50h]
  __int64 (__fastcall *v20)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v21)(); // [rsp+160h] [rbp+60h]
  KIRQL (*v22)(void); // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v23)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v24)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v25)(_QWORD, _QWORD); // [rsp+180h] [rbp+80h]
  __int64 v26; // [rsp+188h] [rbp+88h]
  __int64 (*v27)(void); // [rsp+190h] [rbp+90h]
  NTSTATUS (__stdcall *v28)(HANDLE); // [rsp+198h] [rbp+98h]
  __int64 (__fastcall *v29)(); // [rsp+1A0h] [rbp+A0h]
  NTSTATUS (__stdcall *v30)(HANDLE, HANDLE, PIO_APC_ROUTINE, PVOID, PIO_STATUS_BLOCK, ULONG, PVOID, ULONG, PVOID, ULONG); // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v31)(); // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v32)(); // [rsp+1B8h] [rbp+B8h]
  __int64 (__fastcall *v33)(); // [rsp+1C0h] [rbp+C0h]
  NTSTATUS (__stdcall *v34)(HANDLE, HANDLE, PIO_APC_ROUTINE, PVOID, PIO_STATUS_BLOCK, PVOID, ULONG, FILE_INFORMATION_CLASS, BOOLEAN, PUNICODE_STRING, BOOLEAN); // [rsp+1C8h] [rbp+C8h]
  NTSTATUS (__stdcall *v35)(HANDLE, PIO_STATUS_BLOCK, PVOID, ULONG, FILE_INFORMATION_CLASS); // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v36)(); // [rsp+1D8h] [rbp+D8h]
  void *v37; // [rsp+1E0h] [rbp+E0h]
  __int64 (__fastcall *v38)(int, int, int, int, int, __int64); // [rsp+1E8h] [rbp+E8h]
  NTSTATUS (__stdcall *v39)(HANDLE, PIO_STATUS_BLOCK, PVOID, ULONG, FS_INFORMATION_CLASS); // [rsp+1F0h] [rbp+F0h]
  __int64 (__fastcall *v40)(); // [rsp+1F8h] [rbp+F8h]
  __int64 (__fastcall *v41)(); // [rsp+200h] [rbp+100h]
  __int64 (__fastcall *v42)(); // [rsp+208h] [rbp+108h]
  __int64 (__fastcall *v43)(); // [rsp+210h] [rbp+110h]
  __int64 (__fastcall *v44)(); // [rsp+218h] [rbp+118h]
  __int64 (__fastcall *v45)(); // [rsp+220h] [rbp+120h]
  __int64 (__fastcall *v46)(); // [rsp+228h] [rbp+128h]
  unsigned __int64 v47; // [rsp+230h] [rbp+130h]
  __int64 (__fastcall *v48)(_QWORD); // [rsp+238h] [rbp+138h]

  memset_0(v8, 0, 0x220u);
  v8[0] = 0x100000220LL;
  v0 = *(_QWORD *)(SkeLoaderBlock + 1912);
  v47 = 0xFFFFF78000000000uLL;
  v8[5] = SkpKsrRebootNotify;
  v8[3] = SkpKsrRegisterForSecrets;
  v8[4] = SkpKsrUnregisterForSecrets;
  v8[6] = SkGetIdkSignatureForData;
  v8[23] = SkhalGetAcpiTable;
  v4 = SkhalPciEnabled(v0, v1, v2, v3, 0x100000220LL, v0, SkpKsrCallNormalMode);
  v5 = v9;
  v8[7] = SkmmInitializeRebootAddressRange;
  v8[17] = SkmmReserveMappingAddress;
  if ( v4 )
    v5 = SkhalAccessPciDevice;
  v9 = v5;
  v8[18] = SkmmFreeReservedMapping;
  v8[19] = SkmmGetPhysicalAddress;
  v8[8] = SkmmProtectRestartMdl;
  v8[9] = SkmmUnprotectRestartMdl;
  v8[10] = SkmmProtectIoSpace;
  v8[11] = SkmmUnprotectIoSpace;
  v8[12] = SkmmMapMdl;
  v8[13] = SkmmMapMdlWithReservedMapping;
  v8[14] = SkmmUnmapMdl;
  v8[15] = SkmmMapPhysicalMemory;
  v8[16] = SkmmUnmapPhysicalMemory;
  v8[20] = SkmmRegisterSharedPageRun;
  v8[21] = SkmmIsAddressRangeValidMemory;
  v8[22] = SkmmReserveSpecificAddress;
  v46 = SkmmKsrApplyFunctionOverrideFixupsToImage;
  v10 = SkLogImageLoadEvent;
  v11 = SkLogImageLoadEvent;
  v12 = SkInsertLoadedModule;
  v13 = SkRemoveLoadedModule;
  v14 = SkAcquirePushLockExclusive;
  v15 = RtlAcquireSRWLockShared;
  v16 = SkReleasePushLockExclusive;
  v17 = SkReleasePushLockShared;
  v18 = SkAllocatePool;
  v19 = SkFreePool;
  v20 = SkeGenericIpiCall;
  v21 = ShvlQueryConnection;
  v22 = KeGetCurrentIrql;
  v45 = SkeWalkFrameChain;
  v23 = SkciCreateSecureImage;
  v24 = SkciValidateImageData;
  v25 = SkciFinalizeSecureImageHash;
  v26 = SkciFinishImageValidation;
  v27 = SkciFreeImageContext;
  v28 = NtClose;
  v29 = NkCreateFile;
  v30 = NtDeviceIoControlFile;
  v31 = NkOpenFile;
  v32 = NkOpenKey;
  v33 = NkOpenSymbolicLinkObject;
  v34 = NtQueryDirectoryFile;
  v35 = NtQueryInformationFile;
  v36 = NkQuerySymbolicLinkObject;
  v37 = &NtQuerySystemInformation;
  v38 = NtQueryValueKey;
  v39 = NtQueryVolumeInformationFile;
  v40 = NkReadFile;
  v41 = NkSaveKeyEx;
  v44 = NkQueryDirectoryObject;
  v43 = NkOpenDirectoryObject;
  v42 = NkWriteFile;
  if ( !(unsigned int)KsrSkInitSystem(v8) )
    qword_1401483C0 = v48;
  result = SkeLoaderBlock;
  v7 = *(_QWORD *)(SkeLoaderBlock + 1912);
  if ( v7 )
    return SkmmFreeBootLoadedPages(v7, *(unsigned int *)(SkeLoaderBlock + 1920));
  return result;
}

```

## disassembly

```asm
0x1400bb8a8  push    rbp
0x1400bb8aa  lea     rbp, [rsp-140h]
0x1400bb8b2  sub     rsp, 240h
0x1400bb8b9  xor     edx, edx; Val
0x1400bb8bb  lea     rcx, [rsp+240h+var_220]; void *
0x1400bb8c0  mov     r8d, 220h; Size
0x1400bb8c6  call    memset_0
0x1400bb8cb  mov     rax, cs:SkeLoaderBlock
0x1400bb8d2  mov     dword ptr [rsp+240h+var_220], 220h
0x1400bb8da  mov     dword ptr [rsp+240h+var_220+4], 1
0x1400bb8e2  mov     rcx, [rax+778h]
0x1400bb8e9  mov     [rsp+240h+var_218], rcx
0x1400bb8ee  mov     rax, 0FFFFF78000000000h
0x1400bb8f8  mov     [rbp+140h+var_10], rax
0x1400bb8ff  lea     rax, SkpKsrCallNormalMode
0x1400bb906  mov     [rsp+240h+var_210], rax
0x1400bb90b  lea     rax, SkpKsrRebootNotify
0x1400bb912  mov     [rsp+240h+var_1F8], rax
0x1400bb917  lea     rax, SkpKsrRegisterForSecrets
0x1400bb91e  mov     [rsp+240h+var_208], rax
0x1400bb923  lea     rax, SkpKsrUnregisterForSecrets
0x1400bb92a  mov     [rsp+240h+var_200], rax
0x1400bb92f  lea     rax, SkGetIdkSignatureForData
0x1400bb936  mov     [rsp+240h+var_1F0], rax
0x1400bb93b  lea     rax, SkhalGetAcpiTable
0x1400bb942  mov     [rbp+140h+var_168], rax
0x1400bb946  call    SkhalPciEnabled
0x1400bb94b  mov     rcx, [rbp+140h+var_160]
0x1400bb94f  lea     rdx, SkhalAccessPciDevice
0x1400bb956  test    al, al
0x1400bb958  lea     rax, SkmmInitializeRebootAddressRange
0x1400bb95f  mov     [rsp+240h+var_1E8], rax
0x1400bb964  lea     rax, SkmmReserveMappingAddress
0x1400bb96b  mov     [rbp+140h+var_198], rax
0x1400bb96f  cmovnz  rcx, rdx
0x1400bb973  lea     rax, SkmmFreeReservedMapping
0x1400bb97a  mov     [rbp+140h+var_160], rcx
0x1400bb97e  mov     [rbp+140h+var_190], rax
0x1400bb982  lea     rax, SkmmGetPhysicalAddress
0x1400bb989  mov     [rbp+140h+var_188], rax
0x1400bb98d  lea     rax, SkmmProtectRestartMdl
0x1400bb994  mov     [rsp+240h+var_1E0], rax
0x1400bb999  lea     rax, SkmmUnprotectRestartMdl
0x1400bb9a0  mov     [rsp+240h+var_1D8], rax
0x1400bb9a5  lea     rax, SkmmProtectIoSpace
0x1400bb9ac  mov     [rsp+240h+var_1D0], rax
0x1400bb9b1  lea     rax, SkmmUnprotectIoSpace
0x1400bb9b8  mov     [rsp+240h+var_1C8], rax
0x1400bb9bd  lea     rax, SkmmMapMdl
0x1400bb9c4  mov     [rbp+140h+var_1C0], rax
0x1400bb9c8  lea     rax, SkmmMapMdlWithReservedMapping
0x1400bb9cf  mov     [rbp+140h+var_1B8], rax
0x1400bb9d3  lea     rax, SkmmUnmapMdl
0x1400bb9da  mov     [rbp+140h+var_1B0], rax
0x1400bb9de  lea     rax, SkmmMapPhysicalMemory
0x1400bb9e5  mov     [rbp+140h+var_1A8], rax
0x1400bb9e9  lea     rax, SkmmUnmapPhysicalMemory
0x1400bb9f0  mov     [rbp+140h+var_1A0], rax
0x1400bb9f4  lea     rax, SkmmRegisterSharedPageRun
0x1400bb9fb  mov     [rbp+140h+var_180], rax
0x1400bb9ff  lea     rax, SkmmIsAddressRangeValidMemory
0x1400bba06  mov     [rbp+140h+var_178], rax
0x1400bba0a  lea     rax, SkmmReserveSpecificAddress
0x1400bba11  mov     [rbp+140h+var_170], rax
0x1400bba15  lea     rax, SkmmKsrApplyFunctionOverrideFixupsToImage
0x1400bba1c  mov     [rbp+140h+var_18], rax
0x1400bba23  lea     rax, SkLogImageLoadEvent
0x1400bba2a  mov     [rbp+140h+var_158], rax
0x1400bba2e  lea     rax, SkLogImageLoadEvent
0x1400bba35  mov     [rbp+140h+var_150], rax
0x1400bba39  lea     rax, SkInsertLoadedModule
0x1400bba40  mov     [rbp+140h+var_148], rax
0x1400bba44  lea     rax, SkRemoveLoadedModule
0x1400bba4b  mov     [rbp+140h+var_140], rax
0x1400bba4f  lea     rax, SkAcquirePushLockExclusive
0x1400bba56  mov     [rbp+140h+var_118], rax
0x1400bba5a  lea     rax, RtlAcquireSRWLockShared
0x1400bba61  mov     [rbp+140h+var_110], rax
0x1400bba65  lea     rax, SkReleasePushLockExclusive
0x1400bba6c  mov     [rbp+140h+var_108], rax
0x1400bba70  lea     rax, SkReleasePushLockShared
0x1400bba77  mov     [rbp+140h+var_100], rax
0x1400bba7b  lea     rax, SkAllocatePool
0x1400bba82  mov     [rbp+140h+var_F8], rax
0x1400bba86  lea     rax, SkFreePool
0x1400bba8d  mov     [rbp+140h+var_F0], rax
0x1400bba91  lea     rcx, [rsp+240h+var_220]
0x1400bba96  lea     rax, SkeGenericIpiCall
0x1400bba9d  mov     [rbp+140h+var_E8], rax
0x1400bbaa1  lea     rax, ShvlQueryConnection
0x1400bbaa8  mov     [rbp+140h+var_E0], rax
0x1400bbaac  lea     rax, KeGetCurrentIrql
0x1400bbab3  mov     [rbp+140h+var_D8], rax
0x1400bbab7  lea     rax, SkeWalkFrameChain
0x1400bbabe  mov     [rbp+140h+var_20], rax
0x1400bbac5  mov     rax, cs:__imp_SkciCreateSecureImage
0x1400bbacc  mov     [rbp+140h+var_D0], rax
0x1400bbad0  mov     rax, cs:__imp_SkciValidateImageData
0x1400bbad7  mov     [rbp+140h+var_C8], rax
0x1400bbadb  mov     rax, cs:__imp_SkciFinalizeSecureImageHash
0x1400bbae2  mov     [rbp+140h+var_C0], rax
0x1400bbae9  mov     rax, cs:__imp_SkciFinishImageValidation
0x1400bbaf0  mov     [rbp+140h+var_B8], rax
0x1400bbaf7  mov     rax, cs:__imp_SkciFreeImageContext
0x1400bbafe  mov     [rbp+140h+var_B0], rax
0x1400bbb05  lea     rax, NtClose
0x1400bbb0c  mov     [rbp+140h+var_A8], rax
0x1400bbb13  lea     rax, NkCreateFile
0x1400bbb1a  mov     [rbp+140h+var_A0], rax
0x1400bbb21  lea     rax, NtDeviceIoControlFile
0x1400bbb28  mov     [rbp+140h+var_98], rax
0x1400bbb2f  lea     rax, NkOpenFile
0x1400bbb36  mov     [rbp+140h+var_90], rax
0x1400bbb3d  lea     rax, NkOpenKey
0x1400bbb44  mov     [rbp+140h+var_88], rax
0x1400bbb4b  lea     rax, NkOpenSymbolicLinkObject
0x1400bbb52  mov     [rbp+140h+var_80], rax
0x1400bbb59  lea     rax, NtQueryDirectoryFile
0x1400bbb60  mov     [rbp+140h+var_78], rax
0x1400bbb67  lea     rax, NtQueryInformationFile
0x1400bbb6e  mov     [rbp+140h+var_70], rax
0x1400bbb75  lea     rax, NkQuerySymbolicLinkObject
0x1400bbb7c  mov     [rbp+140h+var_68], rax
0x1400bbb83  lea     rax, NtQuerySystemInformation
0x1400bbb8a  mov     [rbp+140h+var_60], rax
0x1400bbb91  lea     rax, NtQueryValueKey
0x1400bbb98  mov     [rbp+140h+var_58], rax
0x1400bbb9f  lea     rax, NtQueryVolumeInformationFile
0x1400bbba6  mov     [rbp+140h+var_50], rax
0x1400bbbad  lea     rax, NkReadFile
0x1400bbbb4  mov     [rbp+140h+var_48], rax
0x1400bbbbb  lea     rax, NkSaveKeyEx
0x1400bbbc2  mov     [rbp+140h+var_40], rax
0x1400bbbc9  lea     rax, NkQueryDirectoryObject
0x1400bbbd0  mov     [rbp+140h+var_28], rax
0x1400bbbd7  lea     rax, NkOpenDirectoryObject
0x1400bbbde  mov     [rbp+140h+var_30], rax
0x1400bbbe5  lea     rax, NkWriteFile
0x1400bbbec  mov     [rbp+140h+var_38], rax
0x1400bbbf3  call    cs:__imp_KsrSkInitSystem
0x1400bbbfa  nop     dword ptr [rax+rax+00h]
0x1400bbbff  test    eax, eax
0x1400bbc01  jnz     short loc_1400BBC11
0x1400bbc03  mov     rax, [rbp+140h+var_8]
0x1400bbc0a  mov     cs:qword_1401483C0, rax
0x1400bbc11  mov     rax, cs:SkeLoaderBlock
0x1400bbc18  mov     rcx, [rax+778h]
0x1400bbc1f  test    rcx, rcx
0x1400bbc22  jz      short loc_1400BBC2F
0x1400bbc24  mov     edx, [rax+780h]
0x1400bbc2a  call    SkmmFreeBootLoadedPages
0x1400bbc2f  add     rsp, 240h
0x1400bbc36  pop     rbp
0x1400bbc37  retn
```
