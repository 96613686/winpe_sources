# CreateBaseVhd(ushort const *,unsigned __int64,ulong,ushort const *)

- ea: `0x18005ca68`
- end: `0x18005cf1f`
- name: `?CreateBaseVhd@@YA?AUMountedVolume@@PEBG_KK0@Z`
- size: `1207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180034e10`
- `0x180034f50`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006660`
- `0x180018bd4`
- `0x180022d10`
- `0x18002ee18`
- `0x18005c608`
- `0x18005c7a4`
- `0x18005c868`
- `0x18005ca68`
- `0x18005d254`
- `0x18005d664`
- `0x18005dab8`
- `0x18005dd3c`
- `0x18005deac`
- `0x18005e01c`
- `0x18005e18c`
- `0x18005fe7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cd68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cdb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cd68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cdb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cda6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cda6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce9b`
- `VirtDisk!CreateVirtualDisk` at `0x18005cbc4`
- `VirtDisk!CreateVirtualDisk` at `0x18005cbc4`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005cc5b`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005cc5b`

## string_xrefs

- `0x18005cb5c`: `GraphDriver_CreateVirtualDisk`
- `0x18005cc10`: `GraphDriver_GetVirtualDiskPhysicalPath`
- `0x18005cad0`: `GraphDriver_CreateBaseVhd`
- `0x18005cef8`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005cf0d`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CreateBaseVhd(__int64 a1, const WCHAR *a2, __int64 a3, int a4, __int64 *a5)
{
  void **Handle; // rax
  DWORD v10; // eax
  DWORD VirtualDiskPhysicalPath; // eax
  HANDLE *v12; // rsi
  HANDLE v13; // r12
  void *v14; // r15
  DWORD LastError; // ebx
  HANDLE v16; // r12
  HANDLE v17; // r15
  DWORD v18; // ebx
  CREATE_VIRTUAL_DISK_FLAG Flags; // [rsp+20h] [rbp-E0h]
  _OWORD v21[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v22; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE hObject; // [rsp+B0h] [rbp-50h] BYREF
  int v25; // [rsp+B8h] [rbp-48h] BYREF
  ULONG DiskPathSizeInBytes[4]; // [rsp+C0h] [rbp-40h] BYREF
  UUID v27; // [rsp+D0h] [rbp-30h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+E0h] [rbp-20h] BYREF
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v30[42]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v31[42]; // [rsp+310h] [rbp+210h] BYREF
  _QWORD v32[42]; // [rsp+460h] [rbp+360h] BYREF
  _QWORD v33[42]; // [rsp+5B0h] [rbp+4B0h] BYREF
  WCHAR DiskPath[264]; // [rsp+700h] [rbp+600h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+968h] [rbp+868h]

  *(_QWORD *)&v27.Data1 = a3;
  v25 = a4;
  v22 = a5;
  memset_0(v30, 0, sizeof(v30));
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "GraphDriver_CreateBaseVhd");
  v30[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::`vftable';
  ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::StartActivity<unsigned __int64 &,unsigned long &,unsigned short const * &>(
    (__int64)v30,
    (int *)&v27,
    &v25,
    &v22);
  *(_QWORD *)&Parameters.Version = 2;
  memset_0(&Parameters.Version1, 0, 0xB0u);
  Parameters.Version1.MaximumSize = a3 << 30;
  Parameters.Version1.BlockSizeInBytes = a4 << 20;
  memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
  VirtualDiskHandle = (HANDLE)-1LL;
  memset_0(v33, 0, sizeof(v33));
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "GraphDriver_CreateVirtualDisk");
  v33[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable';
  ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StartActivity(
    (ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *)v33,
    (const struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *)v30);
  Handle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&VirtualDiskHandle);
  v10 = CreateVirtualDisk(
          &VirtualStorageType,
          a2,
          VIRTUAL_DISK_ACCESS_NONE,
          0,
          CREATE_VIRTUAL_DISK_FLAG_NONE,
          0,
          &Parameters,
          0,
          Handle);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)v10,
      Flags);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
  MountVhd(
    VirtualDiskHandle,
    ATTACH_VIRTUAL_DISK_FLAG_BYPASS_DEFAULT_ENCRYPTION_POLICY|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER,
    4u);
  memset_0(v32, 0, sizeof(v32));
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "GraphDriver_GetVirtualDiskPhysicalPath");
  v32[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::`vftable';
  ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::StartActivity(
    (ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath *)v32,
    (const struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *)v30);
  DiskPathSizeInBytes[0] = 520;
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, DiskPathSizeInBytes, DiskPath);
  if ( VirtualDiskPhysicalPath )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskPhysicalPath,
      Flags);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
  hObject = 0;
  OpenDisk(&hObject, DiskPath);
  memset_0(v31, 0, sizeof(v31));
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "GraphDriver_FormatDisk");
  v31[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::`vftable';
  ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::StartActivity(
    (ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk *)v31,
    (const struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *)v30);
  v27 = GUID_00000000_0000_0000_0000_000000000000;
  FormatDisk(v21, hObject, (__int64)a5, &v27);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
  *(_QWORD *)a1 = -1;
  v12 = (HANDLE *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = -1;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 7;
  *(_WORD *)(a1 + 16) = 0;
  if ( (HANDLE *)a1 != &VirtualDiskHandle )
  {
    v13 = VirtualDiskHandle;
    v14 = *(void **)a1;
    if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v14);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v13;
    VirtualDiskHandle = (HANDLE)-1LL;
  }
  if ( v12 != &hObject )
  {
    v16 = hObject;
    v17 = *v12;
    if ( (char *)*v12 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v18 = GetLastError();
      CloseHandle(v17);
      SetLastError(v18);
    }
    *v12 = v16;
    hObject = (HANDLE)-1LL;
  }
  std::wstring::operator=(a1 + 16, v21);
  *(_OWORD *)(a1 + 48) = v21[2];
  *(_OWORD *)(a1 + 64) = v21[3];
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v30);
  std::wstring::~wstring(v21);
  v31[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v31);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v31);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v32[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v32);
  v33[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v33);
  if ( (char *)VirtualDiskHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(VirtualDiskHandle);
  v30[0] = &ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v30);
  return a1;
}

```

## disassembly

```asm
0x18005ca68  push    rbp
0x18005ca6a  push    rbx
0x18005ca6b  push    rsi
0x18005ca6c  push    rdi
0x18005ca6d  push    r12
0x18005ca6f  push    r13
0x18005ca71  push    r14
0x18005ca73  push    r15
0x18005ca75  lea     rbp, [rsp-828h]
0x18005ca7d  sub     rsp, 928h
0x18005ca84  mov     rax, cs:__security_cookie
0x18005ca8b  xor     rax, rsp
0x18005ca8e  mov     [rbp+860h+var_50], rax
0x18005ca95  mov     edi, r9d
0x18005ca98  mov     rbx, r8
0x18005ca9b  mov     rsi, rdx
0x18005ca9e  mov     r14, rcx
0x18005caa1  mov     qword ptr [rbp+860h+var_890], rcx
0x18005caa5  mov     qword ptr [rbp+860h+var_890], rbx
0x18005caa9  mov     [rbp+860h+var_8A8], r9d
0x18005caad  mov     r15, [rbp+860h+arg_20]
0x18005cab4  mov     [rbp+860h+var_8C0], r15
0x18005cab8  xor     r12d, r12d
0x18005cabb  xor     edx, edx; Val
0x18005cabd  mov     r8d, 150h; Size
0x18005cac3  lea     rcx, [rbp+860h+var_7A0]; void *
0x18005caca  call    memset_0
0x18005cacf  nop
0x18005cad0  lea     rdx, aGraphdriverCre_3; "GraphDriver_CreateBaseVhd"
0x18005cad7  lea     rcx, [rbp+860h+var_7A0]
0x18005cade  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005cae3  lea     rax, ??_7GraphDriver_CreateBaseVhd@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::`vftable'
0x18005caea  mov     [rbp+860h+var_7A0], rax
0x18005caf1  lea     r9, [rbp+860h+var_8C0]
0x18005caf5  lea     r8, [rbp+860h+var_8A8]
0x18005caf9  lea     rdx, [rbp+860h+var_890]
0x18005cafd  lea     rcx, [rbp+860h+var_7A0]
0x18005cb04  call    ??$StartActivity@AEA_KAEAKAEAPEBG@GraphDriver_CreateBaseVhd@TraceProvider@Diagnostics@ComputeService@@QEAAXAEA_KAEAKAEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::StartActivity<unsigned __int64 &,ulong &,ushort const * &>(unsigned __int64 &,ulong &,ushort const * &)
0x18005cb09  nop
0x18005cb0a  mov     qword ptr [rbp+860h+var_860.Version], 2
0x18005cb12  xor     edx, edx; Val
0x18005cb14  mov     r8d, 0B0h; Size
0x18005cb1a  lea     rcx, [rbp+860h+var_860.8]; void *
0x18005cb1e  call    memset_0
0x18005cb23  shl     rbx, 1Eh
0x18005cb27  mov     qword ptr [rbp+860h+var_860.8+10h], rbx
0x18005cb2b  shl     edi, 14h
0x18005cb2e  mov     dword ptr [rbp+860h+var_860.8+18h], edi
0x18005cb31  xorps   xmm0, xmm0
0x18005cb34  xor     eax, eax
0x18005cb36  movups  xmmword ptr [rbp+860h+VirtualStorageType.DeviceId], xmm0
0x18005cb3a  mov     dword ptr [rbp+860h+VirtualStorageType.VendorId.Data4+4], eax
0x18005cb3d  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005cb41  mov     [rbp+860h+VirtualDiskHandle], r13
0x18005cb45  mov     ebx, 150h
0x18005cb4a  mov     r8d, ebx; Size
0x18005cb4d  xor     edx, edx; Val
0x18005cb4f  lea     rcx, [rbp+860h+var_3B0]; void *
0x18005cb56  call    memset_0
0x18005cb5b  nop
0x18005cb5c  lea     rdx, aGraphdriverCre_0; "GraphDriver_CreateVirtualDisk"
0x18005cb63  lea     rcx, [rbp+860h+var_3B0]
0x18005cb6a  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005cb6f  lea     rax, ??_7GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable'
0x18005cb76  mov     [rbp+860h+var_3B0], rax
0x18005cb7d  lea     rdx, [rbp+860h+var_7A0]; struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *
0x18005cb84  lea     rcx, [rbp+860h+var_3B0]; this
0x18005cb8b  call    ?StartActivity@GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeService@@QEAAXAEBVGraphDriver_CreateBaseVhd@234@@Z; ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StartActivity(ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd const &)
0x18005cb90  nop
0x18005cb91  lea     rcx, [rbp+860h+VirtualDiskHandle]
0x18005cb95  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18005cb9a  mov     [rsp+960h+Handle], rax; Handle
0x18005cb9f  mov     [rsp+960h+Overlapped], r12; Overlapped
0x18005cba4  lea     rax, [rbp+860h+var_860]
0x18005cba8  mov     [rsp+960h+Parameters], rax; Parameters
0x18005cbad  mov     [rsp+960h+ProviderSpecificFlags], r12d; ProviderSpecificFlags
0x18005cbb2  mov     [rsp+960h+Flags], r12d; unsigned int
0x18005cbb7  xor     r9d, r9d; SecurityDescriptor
0x18005cbba  xor     r8d, r8d; VirtualDiskAccessMask
0x18005cbbd  mov     rdx, rsi; Path
0x18005cbc0  lea     rcx, [rbp+860h+VirtualStorageType]; VirtualStorageType
0x18005cbc4  call    cs:__imp_CreateVirtualDisk
0x18005cbcb  nop     dword ptr [rax+rax+00h]
0x18005cbd0  mov     rcx, [rbp+868h]; this
0x18005cbd7  test    eax, eax
0x18005cbd9  jnz     loc_18005CF0A
0x18005cbdf  lea     rcx, [rbp+860h+var_3B0]
0x18005cbe6  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005cbeb  lea     edx, [r12+22h]; enum _ATTACH_VIRTUAL_DISK_FLAG
0x18005cbf0  lea     r8d, [r12+4]; unsigned __int16
0x18005cbf5  mov     rcx, [rbp+860h+VirtualDiskHandle]; void *
0x18005cbf9  call    ?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z; MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)
0x18005cbfe  mov     r8d, ebx; Size
0x18005cc01  xor     edx, edx; Val
0x18005cc03  lea     rcx, [rbp+860h+var_500]; void *
0x18005cc0a  call    memset_0
0x18005cc0f  nop
0x18005cc10  lea     rdx, aGraphdriverGet; "GraphDriver_GetVirtualDiskPhysicalPath"
0x18005cc17  lea     rcx, [rbp+860h+var_500]
0x18005cc1e  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005cc23  lea     rax, ??_7GraphDriver_GetVirtualDiskPhysicalPath@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::`vftable'
0x18005cc2a  mov     [rbp+860h+var_500], rax
0x18005cc31  lea     rdx, [rbp+860h+var_7A0]; struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *
0x18005cc38  lea     rcx, [rbp+860h+var_500]; this
0x18005cc3f  call    ?StartActivity@GraphDriver_GetVirtualDiskPhysicalPath@TraceProvider@Diagnostics@ComputeService@@QEAAXAEBVGraphDriver_CreateBaseVhd@234@@Z; ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::StartActivity(ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd const &)
0x18005cc44  nop
0x18005cc45  mov     [rbp+860h+DiskPathSizeInBytes], 208h
0x18005cc4c  lea     r8, [rbp+860h+DiskPath]; DiskPath
0x18005cc53  lea     rdx, [rbp+860h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18005cc57  mov     rcx, [rbp+860h+VirtualDiskHandle]; VirtualDiskHandle
0x18005cc5b  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18005cc62  nop     dword ptr [rax+rax+00h]
0x18005cc67  mov     rcx, [rbp+868h]; this
0x18005cc6e  test    eax, eax
0x18005cc70  jnz     loc_18005CEF5
0x18005cc76  lea     rcx, [rbp+860h+var_500]
0x18005cc7d  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005cc82  mov     [rbp+860h+hObject], r12
0x18005cc86  lea     rdx, [rbp+860h+DiskPath]
0x18005cc8d  lea     rcx, [rbp+860h+hObject]
0x18005cc91  call    ?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z; OpenDisk(ushort const *,ulong)
0x18005cc96  nop
0x18005cc97  mov     r8d, ebx; Size
0x18005cc9a  xor     edx, edx; Val
0x18005cc9c  lea     rcx, [rbp+860h+var_650]; void *
0x18005cca3  call    memset_0
0x18005cca8  nop
0x18005cca9  lea     rdx, aGraphdriverFor; "GraphDriver_FormatDisk"
0x18005ccb0  lea     rcx, [rbp+860h+var_650]
0x18005ccb7  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005ccbc  lea     rax, ??_7GraphDriver_FormatDisk@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::`vftable'
0x18005ccc3  mov     [rbp+860h+var_650], rax
0x18005ccca  lea     rdx, [rbp+860h+var_7A0]; struct ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *
0x18005ccd1  lea     rcx, [rbp+860h+var_650]; this
0x18005ccd8  call    ?StartActivity@GraphDriver_FormatDisk@TraceProvider@Diagnostics@ComputeService@@QEAAXAEBVGraphDriver_CreateBaseVhd@234@@Z; ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::StartActivity(ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd const &)
0x18005ccdd  nop
0x18005ccde  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005cce5  movdqu  [rbp+860h+var_890], xmm0
0x18005ccea  lea     r9, [rbp+860h+var_890]
0x18005ccee  mov     r8, r15
0x18005ccf1  mov     rdx, [rbp+860h+hObject]
0x18005ccf5  lea     rcx, [rsp+960h+var_900]
0x18005ccfa  call    ?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z; FormatDisk(void *,ushort const *,_GUID)
0x18005ccff  lea     rcx, [rbp+860h+var_650]
0x18005cd06  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005cd0b  mov     [r14], r13
0x18005cd0e  lea     rsi, [r14+8]
0x18005cd12  mov     [rsi], r13
0x18005cd15  lea     rdi, [r14+10h]
0x18005cd19  xorps   xmm0, xmm0
0x18005cd1c  movups  xmmword ptr [rdi], xmm0
0x18005cd1f  mov     [rdi+10h], r12
0x18005cd23  mov     qword ptr [rdi+18h], 7
0x18005cd2b  mov     [rdi], r12w
0x18005cd2f  lea     rax, [rbp+860h+VirtualDiskHandle]
0x18005cd33  cmp     r14, rax
0x18005cd36  jz      short loc_18005CD7B
0x18005cd38  mov     r12, [rbp+860h+VirtualDiskHandle]
0x18005cd3c  mov     r15, [r14]
0x18005cd3f  lea     rax, [r15-1]
0x18005cd43  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd47  ja      short loc_18005CD74
0x18005cd49  call    cs:__imp_GetLastError
0x18005cd50  nop     dword ptr [rax+rax+00h]
0x18005cd55  mov     ebx, eax
0x18005cd57  mov     rcx, r15; hObject
0x18005cd5a  call    cs:__imp_CloseHandle
0x18005cd61  nop     dword ptr [rax+rax+00h]
0x18005cd66  mov     ecx, ebx; dwErrCode
0x18005cd68  call    cs:__imp_SetLastError
0x18005cd6f  nop     dword ptr [rax+rax+00h]
0x18005cd74  mov     [r14], r12
0x18005cd77  mov     [rbp+860h+VirtualDiskHandle], r13
0x18005cd7b  lea     rax, [rbp+860h+hObject]
0x18005cd7f  cmp     rsi, rax
0x18005cd82  jz      short loc_18005CDC7
0x18005cd84  mov     r12, [rbp+860h+hObject]
0x18005cd88  mov     r15, [rsi]
0x18005cd8b  lea     rax, [r15-1]
0x18005cd8f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd93  ja      short loc_18005CDC0
0x18005cd95  call    cs:__imp_GetLastError
0x18005cd9c  nop     dword ptr [rax+rax+00h]
0x18005cda1  mov     ebx, eax
0x18005cda3  mov     rcx, r15; hObject
0x18005cda6  call    cs:__imp_CloseHandle
0x18005cdad  nop     dword ptr [rax+rax+00h]
0x18005cdb2  mov     ecx, ebx; dwErrCode
0x18005cdb4  call    cs:__imp_SetLastError
0x18005cdbb  nop     dword ptr [rax+rax+00h]
0x18005cdc0  mov     [rsi], r12
0x18005cdc3  mov     [rbp+860h+hObject], r13
0x18005cdc7  lea     rdx, [rsp+960h+var_900]
0x18005cdcc  mov     rcx, rdi
0x18005cdcf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005cdd4  movaps  xmm0, [rbp+860h+var_8E0]
0x18005cdd8  movdqu  xmmword ptr [rdi+20h], xmm0
0x18005cddd  movaps  xmm1, [rbp+860h+var_8D0]
0x18005cde1  movdqu  xmmword ptr [rdi+30h], xmm1
0x18005cde6  lea     rcx, [rbp+860h+var_7A0]
0x18005cded  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005cdf2  lea     rcx, [rsp+960h+var_900]
0x18005cdf7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cdfc  nop
0x18005cdfd  lea     rax, ??_7GraphDriver_FormatDisk@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::`vftable'
0x18005ce04  mov     [rbp+860h+var_650], rax
0x18005ce0b  lea     rcx, [rbp+860h+var_650]
0x18005ce12  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005ce17  lea     rcx, [rbp+860h+var_650]
0x18005ce1e  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005ce23  nop
0x18005ce24  mov     rcx, [rbp+860h+hObject]; hObject
0x18005ce28  lea     rax, [rcx-1]
0x18005ce2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ce30  ja      short loc_18005CE3F
0x18005ce32  call    cs:__imp_CloseHandle
0x18005ce39  nop     dword ptr [rax+rax+00h]
0x18005ce3e  nop
0x18005ce3f  lea     rax, ??_7GraphDriver_GetVirtualDiskPhysicalPath@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_GetVirtualDiskPhysicalPath::`vftable'
0x18005ce46  mov     [rbp+860h+var_500], rax
0x18005ce4d  lea     rcx, [rbp+860h+var_500]
0x18005ce54  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005ce59  lea     rcx, [rbp+860h+var_500]
0x18005ce60  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005ce65  nop
0x18005ce66  lea     rax, ??_7GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable'
0x18005ce6d  mov     [rbp+860h+var_3B0], rax
0x18005ce74  lea     rcx, [rbp+860h+var_3B0]
0x18005ce7b  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005ce80  lea     rcx, [rbp+860h+var_3B0]
0x18005ce87  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005ce8c  nop
0x18005ce8d  mov     rcx, [rbp+860h+VirtualDiskHandle]; hObject
0x18005ce91  lea     rdx, [rcx-1]
0x18005ce95  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005ce99  ja      short loc_18005CEA8
0x18005ce9b  call    cs:__imp_CloseHandle
0x18005cea2  nop     dword ptr [rax+rax+00h]
0x18005cea7  nop
0x18005cea8  lea     rax, ??_7GraphDriver_CreateBaseVhd@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::`vftable'
0x18005ceaf  mov     [rbp+860h+var_7A0], rax
0x18005ceb6  lea     rcx, [rbp+860h+var_7A0]
0x18005cebd  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005cec2  lea     rcx, [rbp+860h+var_7A0]
0x18005cec9  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005cece  mov     rax, r14
0x18005ced1  mov     rcx, [rbp+860h+var_50]
0x18005ced8  xor     rcx, rsp; StackCookie
0x18005cedb  call    __security_check_cookie
0x18005cee0  add     rsp, 928h
0x18005cee7  pop     r15
0x18005cee9  pop     r14
0x18005ceeb  pop     r13
0x18005ceed  pop     r12
0x18005ceef  pop     rdi
0x18005cef0  pop     rsi
0x18005cef1  pop     rbx
0x18005cef2  pop     rbp
0x18005cef3  retn
0x18005cef5  mov     r9d, eax; char *
0x18005cef8  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005ceff  mov     edx, 87h; void *
0x18005cf04  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005cf0a  mov     r9d, eax; char *
0x18005cf0d  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005cf14  mov     edx, 7Eh ; '~'; void *
0x18005cf19  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
