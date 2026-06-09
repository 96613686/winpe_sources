# GuestStateFile::MirrorFileToInternal(ushort const *,bool,_GUID const *)

- ea: `0x140081930`
- end: `0x140082005`
- name: `?MirrorFileToInternal@GuestStateFile@@AEAAXPEBG_NPEBU_GUID@@@Z`
- size: `1749`
- prototype: `void(GuestStateFile *__hidden this, const unsigned __int16 *, bool, const struct _GUID *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140022318`
- `0x140027a6c`
- `0x14002dd88`
- `0x14002ed20`
- `0x140030120`
- `0x140031ca8`
- `0x14005145c`
- `0x1400587bc`
- `0x14006af58`
- `0x14007fc6c`
- `0x140081930`
- `0x140082010`
- `0x1400820bc`
- `0x140084204`
- `0x1400843dc`
- `0x140085dd8`
- `0x14009d7cc`
- `0x1400d2d9c`
- `0x1400e8bfc`
- `0x140110a94`
- `0x140132960`
- `0x14013361c`
- `0x1401af2a4`
- `0x1401af2d0`
- `0x1401af354`
- `0x1401b0790`
- `0x1401b08a4`
- `0x1401b0bec`
- `0x1401b3430`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140081f7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140081f7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140081a32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140081a32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140081ac0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140081ac0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140081e45`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140081e45`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140081f22`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140081f22`
- `VirtDisk!OpenVirtualDisk` at `0x140081c1e`
- `VirtDisk!OpenVirtualDisk` at `0x140081c6c`
- `VirtDisk!OpenVirtualDisk` at `0x140081c1e`
- `VirtDisk!OpenVirtualDisk` at `0x140081c6c`
- `VirtDisk!MirrorVirtualDisk` at `0x140081dd8`
- `VirtDisk!MirrorVirtualDisk` at `0x140081dd8`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140081e0e`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140081e0e`

## string_xrefs

- `0x140081ae3`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140081ff3`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140081b8b`: `GuestStateFileOpenVirtualDisk`
- `0x140081c95`: `Failed to open "%ws"`

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
0x140081930  mov     [rsp-8+arg_10], rbx
0x140081935  push    rbp
0x140081936  push    rsi
0x140081937  push    rdi
0x140081938  push    r12
0x14008193a  push    r13
0x14008193c  push    r14
0x14008193e  push    r15
0x140081940  lea     rbp, [rsp-490h]
0x140081948  sub     rsp, 590h
0x14008194f  mov     rax, cs:__security_cookie
0x140081956  xor     rax, rsp
0x140081959  mov     [rbp+4C0h+var_40], rax
0x140081960  mov     r14, r9
0x140081963  mov     r15b, r8b
0x140081966  mov     [rsp+5C0h+var_580], r8b
0x14008196b  mov     rsi, rdx
0x14008196e  mov     rbx, rcx
0x140081971  xor     edx, edx; Val
0x140081973  mov     r8d, 150h; Size
0x140081979  lea     rcx, [rbp+4C0h+var_430]; void *
0x140081980  call    memset_0
0x140081985  lea     rdx, [rbp+4C0h+Progress]
0x140081989  mov     rcx, rbx
0x14008198c  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081991  mov     rdi, rax
0x140081994  cmp     qword ptr [rax+18h], 7
0x140081999  jbe     short loc_14008199E
0x14008199b  mov     rdi, [rax]
0x14008199e  lea     rdx, aGueststatefile_3; "GuestStateFileMirrorFileToInternal"
0x1400819a5  lea     rcx, [rbp+4C0h+var_430]; struct wil::details::IFailureCallback *
0x1400819ac  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400819b1  lea     rax, ??_7GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable'
0x1400819b8  mov     [rbp+4C0h+var_430], rax
0x1400819bf  movups  xmm0, xmmword ptr [rbx+60h]
0x1400819c3  movdqu  xmmword ptr [rsp+5C0h+var_570.Data1], xmm0
0x1400819c9  mov     [rsp+5C0h+Handle], r14; struct _GUID *
0x1400819ce  mov     byte ptr [rsp+5C0h+Parameters], r15b; int
0x1400819d3  mov     r9, rsi; unsigned __int16 *
0x1400819d6  mov     r8, rdi; unsigned __int16 *
0x1400819d9  lea     rdx, [rsp+5C0h+var_570]; struct _GUID *
0x1400819de  lea     rcx, [rbp+4C0h+var_430]; this
0x1400819e5  call    ?StartActivity@GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1_NPEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(_GUID,ushort const *,ushort const *,bool,_GUID const *)
0x1400819ea  nop
0x1400819eb  lea     rcx, [rbp+4C0h+Progress]
0x1400819ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400819f4  mov     rdx, rsi
0x1400819f7  lea     rcx, [rbp+4C0h+var_4D8]
0x1400819fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081a00  nop
0x140081a01  xorps   xmm0, xmm0
0x140081a04  movups  xmmword ptr [rbp+4C0h+Path], xmm0
0x140081a08  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140081a10  movdqu  [rbp+4C0h+var_4E8], xmm1
0x140081a15  xor     r15d, r15d
0x140081a18  mov     word ptr [rbp+4C0h+Path], r15w
0x140081a1d  movups  xmmword ptr [rbp+4C0h+var_498], xmm0
0x140081a21  movdqu  [rbp+4C0h+var_488], xmm1
0x140081a26  mov     word ptr [rbp+4C0h+var_498], r15w
0x140081a2b  lea     rdi, [rbx+28h]
0x140081a2f  mov     rcx, rdi; SRWLock
0x140081a32  call    cs:__imp_AcquireSRWLockShared
0x140081a39  nop     dword ptr [rax+rax+00h]
0x140081a3e  mov     qword ptr [rsp+5C0h+var_570.Data1], rdi
0x140081a43  mov     [rsp+5C0h+var_570.Data4], 1
0x140081a48  mov     rcx, [rbx+38h]
0x140081a4c  mov     rax, [rcx]
0x140081a4f  mov     rax, [rax+28h]
0x140081a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a58  test    al, al
0x140081a5a  jz      short loc_140081A73
0x140081a5c  mov     rcx, [rbx+38h]
0x140081a60  mov     rax, [rcx]
0x140081a63  mov     rax, [rax+38h]
0x140081a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a6c  test    al, al
0x140081a6e  mov     al, r15b
0x140081a71  jz      short loc_140081A75
0x140081a73  mov     al, 1
0x140081a75  mov     rcx, [rbp+4C8h]; this
0x140081a7c  test    al, al
0x140081a7e  jnz     loc_140081FED
0x140081a84  mov     rcx, [rbx+38h]
0x140081a88  mov     rax, [rcx]
0x140081a8b  mov     rax, [rax+48h]
0x140081a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a94  mov     rdx, rax
0x140081a97  lea     rcx, [rbp+4C0h+Path]
0x140081a9b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140081aa0  mov     rcx, [rbx+38h]
0x140081aa4  mov     rax, [rcx]
0x140081aa7  mov     rax, [rax+58h]
0x140081aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081ab0  mov     rdx, rax
0x140081ab3  lea     rcx, [rbp+4C0h+var_498]
0x140081ab7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140081abc  nop
0x140081abd  mov     rcx, rdi; SRWLock
0x140081ac0  call    cs:__imp_ReleaseSRWLockShared
0x140081ac7  nop     dword ptr [rax+rax+00h]
0x140081acc  lea     r13, [rbx+78h]
0x140081ad0  mov     rcx, r13; this
0x140081ad3  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140081ad8  mov     qword ptr [rsp+5C0h+var_570.Data1], r13
0x140081add  mov     al, 1
0x140081adf  mov     [rsp+5C0h+var_570.Data4], al
0x140081ae3  lea     rdi, aOnecoreVmCommo_13; "onecore\\vm\\common\\gueststate\\guests"...
0x140081aea  test    al, al
0x140081aec  jz      loc_140081F78
0x140081af2  lea     r12, [rbx+90h]
0x140081af9  mov     rcx, [rbp+4C8h]; this
0x140081b00  cmp     [r12], r15
0x140081b04  jnz     loc_140081F64
0x140081b0a  lea     rcx, [rbp+4C0h+var_4D8]
0x140081b0e  cmp     [rbp+4C0h+var_4C0], 7
0x140081b13  cmova   rcx, [rbp+4C0h+var_4D8]; unsigned __int16 *
0x140081b18  call    ?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z; GuestStateFile::EnsureDirectoryExists(ushort const *)
0x140081b1d  mov     [rbp+4C0h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x140081b25  mov     [rbp+4C0h+VirtualStorageType.DeviceId], 2
0x140081b2c  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140081b33  movdqu  xmmword ptr [rbp+4C0h+VirtualStorageType.VendorId.Data1], xmm0
0x140081b38  xorps   xmm1, xmm1
0x140081b3b  movups  xmmword ptr [rbp+4C0h+var_460.Version], xmm1
0x140081b3f  movups  xmmword ptr [rbp+4C0h+var_460.4+0Ch], xmm1
0x140081b43  movups  xmmword ptr [rbp+4C0h+var_460.4+18h], xmm1
0x140081b47  mov     [rbp+4C0h+var_460.Version], 2
0x140081b4e  movups  xmm0, xmmword ptr [rbx+60h]
0x140081b52  movdqu  xmmword ptr [rbp+4C0h+var_460.4+8], xmm0
0x140081b57  xor     edx, edx; Val
0x140081b59  mov     r8d, 150h; Size
0x140081b5f  lea     rcx, [rbp+4C0h+var_190]; void *
0x140081b66  call    memset_0
0x140081b6b  mov     r14, [rbp+4C0h+var_320]
0x140081b72  lea     rdx, [rbp+4C0h+Progress]
0x140081b76  mov     rcx, rbx
0x140081b79  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081b7e  mov     rsi, rax
0x140081b81  cmp     qword ptr [rax+18h], 7
0x140081b86  jbe     short loc_140081B8B
0x140081b88  mov     rsi, [rax]
0x140081b8b  lea     rdx, aGueststatefile; "GuestStateFileOpenVirtualDisk"
0x140081b92  lea     rcx, [rbp+4C0h+var_190]; struct wil::details::IFailureCallback *
0x140081b99  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081b9e  lea     rax, ??_7GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable'
0x140081ba5  mov     [rbp+4C0h+var_190], rax
0x140081bac  mov     rdx, rsi
0x140081baf  lea     rcx, [rbp+4C0h+var_530]
0x140081bb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081bb8  movups  xmm0, xmmword ptr [rbx+60h]
0x140081bbc  movdqu  [rsp+5C0h+var_550], xmm0
0x140081bc2  lea     r9, [r14+8]
0x140081bc6  mov     r8, rax
0x140081bc9  lea     rdx, [rsp+5C0h+var_550]
0x140081bce  lea     rcx, [rbp+4C0h+var_190]
0x140081bd5  call    ?StartActivity@GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140081bda  nop
0x140081bdb  lea     rcx, [rbp+4C0h+Progress]
0x140081bdf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140081be4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140081be8  mov     rdx, rsi
0x140081beb  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081bef  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140081bf4  lea     rdx, [rbp+4C0h+Path]
0x140081bf8  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140081bfd  cmova   rdx, [rbp+4C0h+Path]; Path
0x140081c02  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140081c06  mov     [rsp+5C0h+Handle], rax; Handle
0x140081c0b  lea     rax, [rbp+4C0h+var_460]
0x140081c0f  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140081c14  xor     r9d, r9d; Flags
0x140081c17  xor     r8d, r8d; VirtualDiskAccessMask
0x140081c1a  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140081c1e  call    cs:__imp_OpenVirtualDisk
0x140081c25  nop     dword ptr [rax+rax+00h]
0x140081c2a  mov     r9d, eax
0x140081c2d  test    eax, eax
0x140081c2f  jz      short loc_140081CAE
0x140081c31  cmp     eax, 3
0x140081c34  jnz     short loc_140081C7B
0x140081c36  mov     rdx, rsi
0x140081c39  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081c3d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140081c42  lea     rdx, [rbp+4C0h+var_498]
0x140081c46  cmp     qword ptr [rbp+4C0h+var_488+8], 7
0x140081c4b  cmova   rdx, [rbp+4C0h+var_498]; Path
0x140081c50  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140081c54  mov     [rsp+5C0h+Handle], rax; Handle
0x140081c59  lea     rax, [rbp+4C0h+var_460]
0x140081c5d  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140081c62  xor     r9d, r9d; Flags
0x140081c65  xor     r8d, r8d; VirtualDiskAccessMask
0x140081c68  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140081c6c  call    cs:__imp_OpenVirtualDisk
0x140081c73  nop     dword ptr [rax+rax+00h]
0x140081c78  mov     r9d, eax; char *
0x140081c7b  lea     rax, [rbp+4C0h+Path]
0x140081c7f  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140081c84  cmova   rax, [rbp+4C0h+Path]
0x140081c89  mov     rcx, [rbp+4C8h]; this
0x140081c90  mov     [rsp+5C0h+Handle], rax; char *
0x140081c95  lea     rax, aFailedToOpenWs; "Failed to open \"%ws\""
0x140081c9c  mov     [rsp+5C0h+Parameters], rax; unsigned int
0x140081ca1  mov     r8, rdi; unsigned int
0x140081ca4  mov     edx, 411h; void *
0x140081ca9  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x140081cae  lea     rcx, [rbp+4C0h+var_190]
0x140081cb5  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140081cba  mov     [rsp+5C0h+var_578], r15
0x140081cbf  mov     esi, 1
0x140081cc4  mov     edx, esi
0x140081cc6  lea     rcx, [rsp+5C0h+var_578]
0x140081ccb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140081cd0  mov     [rbp+4C0h+var_510], rsi
0x140081cd4  mov     r8, [rbp+4C0h+var_4C0]
0x140081cd8  lea     rax, [rbp+4C0h+var_4D8]
0x140081cdc  mov     rdx, [rbp+4C0h+var_4D8]
0x140081ce0  cmp     r8, 7
0x140081ce4  cmova   rax, rdx
0x140081ce8  mov     [rbp+4C0h+var_508], rax
0x140081cec  lea     r15, [rbx+98h]
0x140081cf3  xor     r14d, r14d
0x140081cf6  mov     [rbx+98h], r14
0x140081cfd  mov     [rbx+0A0h], r14
0x140081d04  mov     [rbx+0A8h], r14
0x140081d0b  mov     rax, [rsp+5C0h+var_578]
0x140081d10  mov     [rbx+0B0h], rax
0x140081d17  movzx   esi, [rsp+5C0h+var_580]
0x140081d1c  add     esi, esi
0x140081d1e  lea     rcx, [rbp+4C0h+var_4D8]
0x140081d22  cmp     r8, 7
0x140081d26  cmova   rcx, rdx
0x140081d2a  call    _anonymous_namespace___FileExists
0x140081d2f  test    al, al
0x140081d31  jz      short loc_140081D36
0x140081d33  or      esi, 1
0x140081d36  xor     edx, edx; Val
0x140081d38  mov     r8d, 150h; Size
0x140081d3e  lea     rcx, [rbp+4C0h+var_2E0]; void *
0x140081d45  call    memset_0
0x140081d4a  mov     rax, [rbp+4C0h+var_320]
0x140081d51  add     rax, 8
0x140081d55  mov     [rsp+5C0h+var_560], rax
0x140081d5a  lea     rdx, [rbp+4C0h+var_530]
0x140081d5e  mov     rcx, rbx
0x140081d61  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081d66  mov     r14, rax
0x140081d69  cmp     qword ptr [rax+18h], 7
0x140081d6e  jbe     short loc_140081D73
0x140081d70  mov     r14, [rax]
0x140081d73  lea     rdx, aGueststatefile_10; "GuestStateFileMirrorVirtualDisk"
0x140081d7a  lea     rcx, [rbp+4C0h+var_2E0]; struct wil::details::IFailureCallback *
0x140081d81  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081d86  lea     rax, ??_7GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable'
0x140081d8d  mov     [rbp+4C0h+var_2E0], rax
0x140081d94  mov     rdx, r14
0x140081d97  lea     rcx, [rbp+4C0h+Progress]
0x140081d9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081da0  movups  xmm0, xmmword ptr [rbx+60h]
0x140081da4  movdqu  [rbp+4C0h+var_540], xmm0
0x140081da9  mov     r9, [rsp+5C0h+var_560]
0x140081dae  mov     r8, rax
0x140081db1  lea     rdx, [rbp+4C0h+var_540]
0x140081db5  lea     rcx, [rbp+4C0h+var_2E0]
0x140081dbc  call    ?StartActivity@GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140081dc1  nop
0x140081dc2  lea     rcx, [rbp+4C0h+var_530]
0x140081dc6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140081dcb  mov     r9, r15
0x140081dce  lea     r8, [rbp+4C0h+var_510]
0x140081dd2  mov     edx, esi
0x140081dd4  mov     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081dd8  call    cs:__imp_MirrorVirtualDisk
0x140081ddf  nop     dword ptr [rax+rax+00h]
0x140081de4  mov     r9d, eax; char *
0x140081de7  test    eax, eax
0x140081de9  jz      short loc_140081DF6
0x140081deb  cmp     eax, 3E5h
0x140081df0  jnz     loc_140081ED1
0x140081df6  xorps   xmm0, xmm0
0x140081df9  xor     eax, eax
0x140081dfb  movups  xmmword ptr [rbp+4C0h+Progress.OperationStatus], xmm0
0x140081dff  mov     [rbp+4C0h+Progress.CompletionValue], rax
0x140081e03  lea     r8, [rbp+4C0h+Progress]; Progress
0x140081e07  mov     rdx, r15; Overlapped
0x140081e0a  mov     rcx, [rbp+4C0h+VirtualDiskHandle]; VirtualDiskHandle
0x140081e0e  call    cs:__imp_GetVirtualDiskOperationProgress
0x140081e15  nop     dword ptr [rax+rax+00h]
0x140081e1a  mov     rcx, [rbp+4C8h]; this
0x140081e21  test    eax, eax
0x140081e23  jnz     loc_140081F53
0x140081e29  cmp     [rbp+4C0h+Progress.OperationStatus], 3E5h
0x140081e30  jnz     loc_140081F18
0x140081e36  mov     rax, [rbp+4C0h+Progress.CompletionValue]
0x140081e3a  cmp     [rbp+4C0h+Progress.CurrentValue], rax
0x140081e3e  jz      short loc_140081E53
0x140081e40  mov     ecx, 12Ch; dwMilliseconds
0x140081e45  call    cs:__imp_Sleep
0x140081e4c  nop     dword ptr [rax+rax+00h]
0x140081e51  jmp     short loc_140081DF6
0x140081e53  lea     rcx, [rbp+4C0h+var_2E0]
  ... truncated ...
```
