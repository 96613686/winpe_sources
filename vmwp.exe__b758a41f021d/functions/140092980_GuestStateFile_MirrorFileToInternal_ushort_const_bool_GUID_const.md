# GuestStateFile::MirrorFileToInternal(ushort const *,bool,_GUID const *)

- ea: `0x140092980`
- end: `0x140093055`
- name: `?MirrorFileToInternal@GuestStateFile@@AEAAXPEBG_NPEBU_GUID@@@Z`
- size: `1749`
- prototype: `void(GuestStateFile *__hidden this, const unsigned __int16 *, bool, const struct _GUID *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140022888`
- `0x140027fdc`
- `0x14003b750`
- `0x14003c680`
- `0x14003d828`
- `0x14003e2b8`
- `0x14004f6dc`
- `0x140078628`
- `0x140085634`
- `0x140085bf4`
- `0x140090cbc`
- `0x140092980`
- `0x140093060`
- `0x14009310c`
- `0x140094fec`
- `0x1400969e8`
- `0x1400ba144`
- `0x1400c015c`
- `0x1400d9ef0`
- `0x140101f84`
- `0x14011ea40`
- `0x14011f6fc`
- `0x14019e254`
- `0x14019e280`
- `0x14019e304`
- `0x14019f740`
- `0x14019f854`
- `0x14019fb9c`
- `0x1401a23e0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140092a82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140092a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140092b10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140092b10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140092fcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140092fcf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140092e95`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140092e95`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140092f72`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140092f72`
- `VirtDisk!OpenVirtualDisk` at `0x140092c6e`
- `VirtDisk!OpenVirtualDisk` at `0x140092cbc`
- `VirtDisk!OpenVirtualDisk` at `0x140092c6e`
- `VirtDisk!OpenVirtualDisk` at `0x140092cbc`
- `VirtDisk!MirrorVirtualDisk` at `0x140092e28`
- `VirtDisk!MirrorVirtualDisk` at `0x140092e28`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140092e5e`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140092e5e`

## string_xrefs

- `0x140092b33`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140093043`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140092bdb`: `GuestStateFileOpenVirtualDisk`
- `0x140092ce5`: `Failed to open "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall GuestStateFile::MirrorFileToInternal(
        GuestStateFile *this,
        const unsigned __int16 *a2,
        bool a3,
        const struct _GUID *a4)
{
  __int64 FilePath; // rax
  const unsigned __int16 *v9; // rdi
  bool v10; // zf
  char v11; // al
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // al
  const unsigned __int16 *v15; // rcx
  __int64 v16; // r14
  _QWORD *v17; // rax
  _QWORD *v18; // rsi
  __int64 v19; // rax
  const WCHAR *v20; // rdx
  DWORD v21; // eax
  const char *v22; // r9
  const WCHAR *v23; // rdx
  PCWSTR *v24; // rax
  unsigned __int64 v25; // r8
  unsigned __int16 **v26; // rax
  unsigned __int16 *v27; // rdx
  unsigned int v28; // esi
  unsigned __int16 **v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // r14
  __int64 v32; // rax
  unsigned int v33; // eax
  const char *v34; // r9
  DWORD VirtualDiskOperationProgress; // eax
  unsigned __int16 **v36; // rdx
  PCWSTR *v37; // rax
  unsigned int Parameters; // [rsp+20h] [rbp-E0h]
  const char *Handle; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  __int128 v44; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v47[2]; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR Path[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v51[3]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v52; // [rsp+100h] [rbp+0h]
  _VIRTUAL_DISK_PROGRESS Progress; // [rsp+108h] [rbp+8h] BYREF
  PCWSTR v54[2]; // [rsp+128h] [rbp+28h] BYREF
  __m128i v55; // [rsp+138h] [rbp+38h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+148h] [rbp+48h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS v57; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v58[34]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v59; // [rsp+2A0h] [rbp+1A0h]
  _QWORD v60[42]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v61[42]; // [rsp+430h] [rbp+330h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  memset_0(v58, 0, 0x150u);
  FilePath = GuestStateFile::GetFilePath(this, &Progress);
  v9 = (const unsigned __int16 *)FilePath;
  if ( *(_QWORD *)(FilePath + 24) > 7u )
    v9 = *(const unsigned __int16 **)FilePath;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v58);
  v58[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable';
  v42 = (struct _GUID)*((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)v58,
    &v42,
    v9,
    a2,
    a3,
    a4);
  std::wstring::_Tidy_deallocate(&Progress);
  std::wstring::wstring(v51, a2);
  *(_OWORD *)Path = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Path[0]) = 0;
  *(_OWORD *)v54 = 0;
  v55 = si128;
  LOWORD(v54[0]) = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 5);
  *(_QWORD *)&v42.Data1 = (char *)this + 40;
  v42.Data4[0] = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7))
    || (v10 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7)) == 0,
        v11 = 0,
        !v10) )
  {
    v11 = 1;
  }
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D4,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8007139FLL,
      Parameters);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
  std::wstring::assign(Path, v12);
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 88LL))(*((_QWORD *)this + 7));
  std::wstring::assign(v54, v13);
  ReleaseSRWLockShared((PSRWLOCK)this + 5);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((GuestStateFile *)((char *)this + 120));
  *(_QWORD *)&v42.Data1 = (char *)this + 120;
  v14 = 1;
  v42.Data4[0] = 1;
  while ( v14 )
  {
    if ( *((_QWORD *)this + 18) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E6,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)0x800700AALL,
        Parameters);
    v15 = (const unsigned __int16 *)v51;
    if ( v52 > 7 )
      v15 = v51[0];
    GuestStateFile::EnsureDirectoryExists(v15);
    VirtualDiskHandle = (HANDLE)-1LL;
    VirtualStorageType.DeviceId = 2;
    VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
    memset(&v57, 0, sizeof(v57));
    v57.Version = OPEN_VIRTUAL_DISK_VERSION_2;
    v57.Version3.ResiliencyGuid = (GUID)*((_OWORD *)this + 6);
    memset_0(v61, 0, sizeof(v61));
    v16 = v59;
    v17 = (_QWORD *)GuestStateFile::GetFilePath(this, &Progress);
    v18 = v17;
    if ( v17[3] > 7u )
      v18 = (_QWORD *)*v17;
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
    v61[0] = &GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable';
    v19 = std::wstring::wstring(v46, v18);
    v44 = *((_OWORD *)this + 6);
    GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(v61, &v44, v19, v16 + 8);
    std::wstring::_Tidy_deallocate(&Progress);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&VirtualDiskHandle);
    v20 = (const WCHAR *)Path;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = Path[0];
    v21 = OpenVirtualDisk(
            &VirtualStorageType,
            v20,
            VIRTUAL_DISK_ACCESS_NONE,
            OPEN_VIRTUAL_DISK_FLAG_NONE,
            &v57,
            &VirtualDiskHandle);
    v22 = (const char *)v21;
    if ( v21 )
    {
      if ( v21 == 3 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&VirtualDiskHandle);
        v23 = (const WCHAR *)v54;
        if ( v55.m128i_i64[1] > 7uLL )
          v23 = v54[0];
        v22 = (const char *)OpenVirtualDisk(
                              &VirtualStorageType,
                              v23,
                              VIRTUAL_DISK_ACCESS_NONE,
                              OPEN_VIRTUAL_DISK_FLAG_NONE,
                              &v57,
                              &VirtualDiskHandle);
      }
      v24 = Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v24 = (PCWSTR *)Path[0];
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x411,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        v22,
        (unsigned int)"Failed to open \"%ws\"",
        (const char *)v24);
    }
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v61);
    v41 = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v41,
      1);
    v47[0] = 1;
    v25 = v52;
    v26 = v51;
    v27 = v51[0];
    if ( v52 > 7 )
      v26 = (unsigned __int16 **)v51[0];
    v47[1] = v26;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = v41;
    v28 = 2 * a3;
    v29 = v51;
    if ( v25 > 7 )
      v29 = (unsigned __int16 **)v27;
    if ( (unsigned __int8)anonymous_namespace_::FileExists(v29) )
      v28 |= 1u;
    memset_0(v60, 0, sizeof(v60));
    v43 = v59 + 8;
    v30 = (_QWORD *)GuestStateFile::GetFilePath(this, v46);
    v31 = v30;
    if ( v30[3] > 7u )
      v31 = (_QWORD *)*v30;
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v60);
    v60[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable';
    v32 = std::wstring::wstring(&Progress, v31);
    v45 = *((_OWORD *)this + 6);
    GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(v60, &v45, v32, v43);
    std::wstring::_Tidy_deallocate(v46);
    v33 = MirrorVirtualDisk(VirtualDiskHandle, v28, v47, (char *)this + 152);
    v34 = (const char *)v33;
    if ( v33 && v33 != 997 )
    {
      v36 = v51;
      if ( v52 > 7 )
        v36 = (unsigned __int16 **)v51[0];
      v37 = Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v37 = (PCWSTR *)Path[0];
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x441,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        v34,
        (unsigned int)"Mirror operation of \"%ws\" to \"%ws\" failed.",
        (const char *)v37,
        v36);
    }
    while ( 1 )
    {
      memset(&Progress, 0, sizeof(Progress));
      VirtualDiskOperationProgress = GetVirtualDiskOperationProgress(
                                       VirtualDiskHandle,
                                       (LPOVERLAPPED)((char *)this + 152),
                                       &Progress);
      if ( VirtualDiskOperationProgress )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x44A,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
          (const char *)VirtualDiskOperationProgress,
          Parameters);
      if ( Progress.OperationStatus != 997 )
      {
        CancelIoEx(*((HANDLE *)this + 17), (LPOVERLAPPED)((char *)this + 152));
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x451,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
          (const char *)Progress.OperationStatus,
          (unsigned int)"Mirror operation of failed.",
          Handle);
      }
      if ( Progress.CurrentValue == Progress.CompletionValue )
        break;
      Sleep(0x12Cu);
    }
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v60);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 136,
      &VirtualDiskHandle);
    __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
      (char *)this + 144,
      &v41);
    if ( !a3 )
      std::wstring::operator=((char *)this + 184, v51);
    GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::~GuestStateFileMirrorVirtualDisk((GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk *)v60);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::~GuestStateFileOpenVirtualDisk((GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk *)v61);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&VirtualDiskHandle);
    v14 = 0;
    v42.Data4[0] = 0;
  }
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
  std::wstring::_Tidy_deallocate(v54);
  std::wstring::_Tidy_deallocate(Path);
  std::wstring::_Tidy_deallocate(v51);
  GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::~GuestStateFileMirrorFileToInternal((GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)v58);
}

```

## disassembly

```asm
0x140092980  mov     [rsp-8+arg_10], rbx
0x140092985  push    rbp
0x140092986  push    rsi
0x140092987  push    rdi
0x140092988  push    r12
0x14009298a  push    r13
0x14009298c  push    r14
0x14009298e  push    r15
0x140092990  lea     rbp, [rsp-490h]
0x140092998  sub     rsp, 590h
0x14009299f  mov     rax, cs:__security_cookie
0x1400929a6  xor     rax, rsp
0x1400929a9  mov     [rbp+4C0h+var_40], rax
0x1400929b0  mov     r14, r9
0x1400929b3  mov     r15b, r8b
0x1400929b6  mov     [rsp+5C0h+var_580], r8b
0x1400929bb  mov     rsi, rdx
0x1400929be  mov     rbx, rcx
0x1400929c1  xor     edx, edx; Val
0x1400929c3  mov     r8d, 150h; Size
0x1400929c9  lea     rcx, [rbp+4C0h+var_430]; void *
0x1400929d0  call    memset_0
0x1400929d5  lea     rdx, [rbp+4C0h+Progress]
0x1400929d9  mov     rcx, rbx
0x1400929dc  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x1400929e1  mov     rdi, rax
0x1400929e4  cmp     qword ptr [rax+18h], 7
0x1400929e9  jbe     short loc_1400929EE
0x1400929eb  mov     rdi, [rax]
0x1400929ee  lea     rdx, aGueststatefile_3; "GuestStateFileMirrorFileToInternal"
0x1400929f5  lea     rcx, [rbp+4C0h+var_430]; struct wil::details::IFailureCallback *
0x1400929fc  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140092a01  lea     rax, ??_7GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable'
0x140092a08  mov     [rbp+4C0h+var_430], rax
0x140092a0f  movups  xmm0, xmmword ptr [rbx+60h]
0x140092a13  movdqu  xmmword ptr [rsp+5C0h+var_570.Data1], xmm0
0x140092a19  mov     [rsp+5C0h+Handle], r14; struct _GUID *
0x140092a1e  mov     byte ptr [rsp+5C0h+Parameters], r15b; int
0x140092a23  mov     r9, rsi; unsigned __int16 *
0x140092a26  mov     r8, rdi; unsigned __int16 *
0x140092a29  lea     rdx, [rsp+5C0h+var_570]; struct _GUID *
0x140092a2e  lea     rcx, [rbp+4C0h+var_430]; this
0x140092a35  call    ?StartActivity@GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1_NPEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(_GUID,ushort const *,ushort const *,bool,_GUID const *)
0x140092a3a  nop
0x140092a3b  lea     rcx, [rbp+4C0h+Progress]
0x140092a3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140092a44  mov     rdx, rsi
0x140092a47  lea     rcx, [rbp+4C0h+var_4D8]
0x140092a4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092a50  nop
0x140092a51  xorps   xmm0, xmm0
0x140092a54  movups  xmmword ptr [rbp+4C0h+Path], xmm0
0x140092a58  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140092a60  movdqu  [rbp+4C0h+var_4E8], xmm1
0x140092a65  xor     r15d, r15d
0x140092a68  mov     word ptr [rbp+4C0h+Path], r15w
0x140092a6d  movups  xmmword ptr [rbp+4C0h+var_498], xmm0
0x140092a71  movdqu  [rbp+4C0h+var_488], xmm1
0x140092a76  mov     word ptr [rbp+4C0h+var_498], r15w
0x140092a7b  lea     rdi, [rbx+28h]
0x140092a7f  mov     rcx, rdi; SRWLock
0x140092a82  call    cs:__imp_AcquireSRWLockShared
0x140092a89  nop     dword ptr [rax+rax+00h]
0x140092a8e  mov     qword ptr [rsp+5C0h+var_570.Data1], rdi
0x140092a93  mov     [rsp+5C0h+var_570.Data4], 1
0x140092a98  mov     rcx, [rbx+38h]
0x140092a9c  mov     rax, [rcx]
0x140092a9f  mov     rax, [rax+28h]
0x140092aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092aa8  test    al, al
0x140092aaa  jz      short loc_140092AC3
0x140092aac  mov     rcx, [rbx+38h]
0x140092ab0  mov     rax, [rcx]
0x140092ab3  mov     rax, [rax+38h]
0x140092ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092abc  test    al, al
0x140092abe  mov     al, r15b
0x140092ac1  jz      short loc_140092AC5
0x140092ac3  mov     al, 1
0x140092ac5  mov     rcx, [rbp+4C8h]; this
0x140092acc  test    al, al
0x140092ace  jnz     loc_14009303D
0x140092ad4  mov     rcx, [rbx+38h]
0x140092ad8  mov     rax, [rcx]
0x140092adb  mov     rax, [rax+48h]
0x140092adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092ae4  mov     rdx, rax
0x140092ae7  lea     rcx, [rbp+4C0h+Path]
0x140092aeb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140092af0  mov     rcx, [rbx+38h]
0x140092af4  mov     rax, [rcx]
0x140092af7  mov     rax, [rax+58h]
0x140092afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092b00  mov     rdx, rax
0x140092b03  lea     rcx, [rbp+4C0h+var_498]
0x140092b07  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140092b0c  nop
0x140092b0d  mov     rcx, rdi; SRWLock
0x140092b10  call    cs:__imp_ReleaseSRWLockShared
0x140092b17  nop     dword ptr [rax+rax+00h]
0x140092b1c  lea     r13, [rbx+78h]
0x140092b20  mov     rcx, r13; this
0x140092b23  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140092b28  mov     qword ptr [rsp+5C0h+var_570.Data1], r13
0x140092b2d  mov     al, 1
0x140092b2f  mov     [rsp+5C0h+var_570.Data4], al
0x140092b33  lea     rdi, aOnecoreVmCommo_12; "onecore\\vm\\common\\gueststate\\guests"...
0x140092b3a  test    al, al
0x140092b3c  jz      loc_140092FC8
0x140092b42  lea     r12, [rbx+90h]
0x140092b49  mov     rcx, [rbp+4C8h]; this
0x140092b50  cmp     [r12], r15
0x140092b54  jnz     loc_140092FB4
0x140092b5a  lea     rcx, [rbp+4C0h+var_4D8]
0x140092b5e  cmp     [rbp+4C0h+var_4C0], 7
0x140092b63  cmova   rcx, [rbp+4C0h+var_4D8]; unsigned __int16 *
0x140092b68  call    ?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z; GuestStateFile::EnsureDirectoryExists(ushort const *)
0x140092b6d  mov     [rbp+4C0h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x140092b75  mov     [rbp+4C0h+VirtualStorageType.DeviceId], 2
0x140092b7c  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140092b83  movdqu  xmmword ptr [rbp+4C0h+VirtualStorageType.VendorId.Data1], xmm0
0x140092b88  xorps   xmm1, xmm1
0x140092b8b  movups  xmmword ptr [rbp+4C0h+var_460.Version], xmm1
0x140092b8f  movups  xmmword ptr [rbp+4C0h+var_460.4+0Ch], xmm1
0x140092b93  movups  xmmword ptr [rbp+4C0h+var_460.4+18h], xmm1
0x140092b97  mov     [rbp+4C0h+var_460.Version], 2
0x140092b9e  movups  xmm0, xmmword ptr [rbx+60h]
0x140092ba2  movdqu  xmmword ptr [rbp+4C0h+var_460.4+8], xmm0
0x140092ba7  xor     edx, edx; Val
0x140092ba9  mov     r8d, 150h; Size
0x140092baf  lea     rcx, [rbp+4C0h+var_190]; void *
0x140092bb6  call    memset_0
0x140092bbb  mov     r14, [rbp+4C0h+var_320]
0x140092bc2  lea     rdx, [rbp+4C0h+Progress]
0x140092bc6  mov     rcx, rbx
0x140092bc9  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140092bce  mov     rsi, rax
0x140092bd1  cmp     qword ptr [rax+18h], 7
0x140092bd6  jbe     short loc_140092BDB
0x140092bd8  mov     rsi, [rax]
0x140092bdb  lea     rdx, aGueststatefile; "GuestStateFileOpenVirtualDisk"
0x140092be2  lea     rcx, [rbp+4C0h+var_190]; struct wil::details::IFailureCallback *
0x140092be9  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140092bee  lea     rax, ??_7GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable'
0x140092bf5  mov     [rbp+4C0h+var_190], rax
0x140092bfc  mov     rdx, rsi
0x140092bff  lea     rcx, [rbp+4C0h+var_530]
0x140092c03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092c08  movups  xmm0, xmmword ptr [rbx+60h]
0x140092c0c  movdqu  [rsp+5C0h+var_550], xmm0
0x140092c12  lea     r9, [r14+8]
0x140092c16  mov     r8, rax
0x140092c19  lea     rdx, [rsp+5C0h+var_550]
0x140092c1e  lea     rcx, [rbp+4C0h+var_190]
0x140092c25  call    ?StartActivity@GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140092c2a  nop
0x140092c2b  lea     rcx, [rbp+4C0h+Progress]
0x140092c2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140092c34  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140092c38  mov     rdx, rsi
0x140092c3b  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140092c3f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140092c44  lea     rdx, [rbp+4C0h+Path]
0x140092c48  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140092c4d  cmova   rdx, [rbp+4C0h+Path]; Path
0x140092c52  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140092c56  mov     [rsp+5C0h+Handle], rax; Handle
0x140092c5b  lea     rax, [rbp+4C0h+var_460]
0x140092c5f  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140092c64  xor     r9d, r9d; Flags
0x140092c67  xor     r8d, r8d; VirtualDiskAccessMask
0x140092c6a  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140092c6e  call    cs:__imp_OpenVirtualDisk
0x140092c75  nop     dword ptr [rax+rax+00h]
0x140092c7a  mov     r9d, eax
0x140092c7d  test    eax, eax
0x140092c7f  jz      short loc_140092CFE
0x140092c81  cmp     eax, 3
0x140092c84  jnz     short loc_140092CCB
0x140092c86  mov     rdx, rsi
0x140092c89  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140092c8d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140092c92  lea     rdx, [rbp+4C0h+var_498]
0x140092c96  cmp     qword ptr [rbp+4C0h+var_488+8], 7
0x140092c9b  cmova   rdx, [rbp+4C0h+var_498]; Path
0x140092ca0  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140092ca4  mov     [rsp+5C0h+Handle], rax; Handle
0x140092ca9  lea     rax, [rbp+4C0h+var_460]
0x140092cad  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140092cb2  xor     r9d, r9d; Flags
0x140092cb5  xor     r8d, r8d; VirtualDiskAccessMask
0x140092cb8  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140092cbc  call    cs:__imp_OpenVirtualDisk
0x140092cc3  nop     dword ptr [rax+rax+00h]
0x140092cc8  mov     r9d, eax; char *
0x140092ccb  lea     rax, [rbp+4C0h+Path]
0x140092ccf  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140092cd4  cmova   rax, [rbp+4C0h+Path]
0x140092cd9  mov     rcx, [rbp+4C8h]; this
0x140092ce0  mov     [rsp+5C0h+Handle], rax; char *
0x140092ce5  lea     rax, aFailedToOpenWs; "Failed to open \"%ws\""
0x140092cec  mov     [rsp+5C0h+Parameters], rax; unsigned int
0x140092cf1  mov     r8, rdi; unsigned int
0x140092cf4  mov     edx, 411h; void *
0x140092cf9  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x140092cfe  lea     rcx, [rbp+4C0h+var_190]
0x140092d05  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140092d0a  mov     [rsp+5C0h+var_578], r15
0x140092d0f  mov     esi, 1
0x140092d14  mov     edx, esi
0x140092d16  lea     rcx, [rsp+5C0h+var_578]
0x140092d1b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140092d20  mov     [rbp+4C0h+var_510], rsi
0x140092d24  mov     r8, [rbp+4C0h+var_4C0]
0x140092d28  lea     rax, [rbp+4C0h+var_4D8]
0x140092d2c  mov     rdx, [rbp+4C0h+var_4D8]
0x140092d30  cmp     r8, 7
0x140092d34  cmova   rax, rdx
0x140092d38  mov     [rbp+4C0h+var_508], rax
0x140092d3c  lea     r15, [rbx+98h]
0x140092d43  xor     r14d, r14d
0x140092d46  mov     [rbx+98h], r14
0x140092d4d  mov     [rbx+0A0h], r14
0x140092d54  mov     [rbx+0A8h], r14
0x140092d5b  mov     rax, [rsp+5C0h+var_578]
0x140092d60  mov     [rbx+0B0h], rax
0x140092d67  movzx   esi, [rsp+5C0h+var_580]
0x140092d6c  add     esi, esi
0x140092d6e  lea     rcx, [rbp+4C0h+var_4D8]
0x140092d72  cmp     r8, 7
0x140092d76  cmova   rcx, rdx
0x140092d7a  call    _anonymous_namespace___FileExists
0x140092d7f  test    al, al
0x140092d81  jz      short loc_140092D86
0x140092d83  or      esi, 1
0x140092d86  xor     edx, edx; Val
0x140092d88  mov     r8d, 150h; Size
0x140092d8e  lea     rcx, [rbp+4C0h+var_2E0]; void *
0x140092d95  call    memset_0
0x140092d9a  mov     rax, [rbp+4C0h+var_320]
0x140092da1  add     rax, 8
0x140092da5  mov     [rsp+5C0h+var_560], rax
0x140092daa  lea     rdx, [rbp+4C0h+var_530]
0x140092dae  mov     rcx, rbx
0x140092db1  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140092db6  mov     r14, rax
0x140092db9  cmp     qword ptr [rax+18h], 7
0x140092dbe  jbe     short loc_140092DC3
0x140092dc0  mov     r14, [rax]
0x140092dc3  lea     rdx, aGueststatefile_10; "GuestStateFileMirrorVirtualDisk"
0x140092dca  lea     rcx, [rbp+4C0h+var_2E0]; struct wil::details::IFailureCallback *
0x140092dd1  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140092dd6  lea     rax, ??_7GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable'
0x140092ddd  mov     [rbp+4C0h+var_2E0], rax
0x140092de4  mov     rdx, r14
0x140092de7  lea     rcx, [rbp+4C0h+Progress]
0x140092deb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092df0  movups  xmm0, xmmword ptr [rbx+60h]
0x140092df4  movdqu  [rbp+4C0h+var_540], xmm0
0x140092df9  mov     r9, [rsp+5C0h+var_560]
0x140092dfe  mov     r8, rax
0x140092e01  lea     rdx, [rbp+4C0h+var_540]
0x140092e05  lea     rcx, [rbp+4C0h+var_2E0]
0x140092e0c  call    ?StartActivity@GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140092e11  nop
0x140092e12  lea     rcx, [rbp+4C0h+var_530]
0x140092e16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140092e1b  mov     r9, r15
0x140092e1e  lea     r8, [rbp+4C0h+var_510]
0x140092e22  mov     edx, esi
0x140092e24  mov     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140092e28  call    cs:__imp_MirrorVirtualDisk
0x140092e2f  nop     dword ptr [rax+rax+00h]
0x140092e34  mov     r9d, eax; char *
0x140092e37  test    eax, eax
0x140092e39  jz      short loc_140092E46
0x140092e3b  cmp     eax, 3E5h
0x140092e40  jnz     loc_140092F21
0x140092e46  xorps   xmm0, xmm0
0x140092e49  xor     eax, eax
0x140092e4b  movups  xmmword ptr [rbp+4C0h+Progress.OperationStatus], xmm0
0x140092e4f  mov     [rbp+4C0h+Progress.CompletionValue], rax
0x140092e53  lea     r8, [rbp+4C0h+Progress]; Progress
0x140092e57  mov     rdx, r15; Overlapped
0x140092e5a  mov     rcx, [rbp+4C0h+VirtualDiskHandle]; VirtualDiskHandle
0x140092e5e  call    cs:__imp_GetVirtualDiskOperationProgress
0x140092e65  nop     dword ptr [rax+rax+00h]
0x140092e6a  mov     rcx, [rbp+4C8h]; this
0x140092e71  test    eax, eax
0x140092e73  jnz     loc_140092FA3
0x140092e79  cmp     [rbp+4C0h+Progress.OperationStatus], 3E5h
0x140092e80  jnz     loc_140092F68
0x140092e86  mov     rax, [rbp+4C0h+Progress.CompletionValue]
0x140092e8a  cmp     [rbp+4C0h+Progress.CurrentValue], rax
0x140092e8e  jz      short loc_140092EA3
0x140092e90  mov     ecx, 12Ch; dwMilliseconds
0x140092e95  call    cs:__imp_Sleep
0x140092e9c  nop     dword ptr [rax+rax+00h]
0x140092ea1  jmp     short loc_140092E46
0x140092ea3  lea     rcx, [rbp+4C0h+var_2E0]
  ... truncated ...
```
