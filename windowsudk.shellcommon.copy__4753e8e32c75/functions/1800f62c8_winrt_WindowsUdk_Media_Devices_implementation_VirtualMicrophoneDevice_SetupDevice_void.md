# winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupDevice(void)

- ea: `0x1800f62c8`
- end: `0x1800f64fe`
- name: `?SetupDevice@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXXZ`
- size: `566`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f5a98`

## callees

- `0x180025348`
- `0x1800dca48`
- `0x1800f5e5c`
- `0x1802e42f0`
- `0x1804a2010`

## import_xrefs

- `Apx01000!imp_ApxDeviceInitAllocate` at `0x1800f62d8`
- `Apx01000!imp_ApxDeviceInitAllocate` at `0x1800f62d8`
- `Apx01000!imp_ApxDeviceInitSetControlInterfaceId` at `0x1800f6315`
- `Apx01000!imp_ApxDeviceInitSetControlInterfaceId` at `0x1800f6315`
- `Apx01000!imp_ApxDeviceInitSetProductId` at `0x1800f641b`
- `Apx01000!imp_ApxDeviceInitSetProductId` at `0x1800f641b`
- `Apx01000!imp_ApxDeviceInitSetProductType` at `0x1800f642a`
- `Apx01000!imp_ApxDeviceInitSetProductType` at `0x1800f642a`
- `Apx01000!imp_ApxDeviceInitSetContainerId` at `0x1800f6439`
- `Apx01000!imp_ApxDeviceInitSetContainerId` at `0x1800f6439`
- `Apx01000!imp_ApxDeviceInitAssignInstanceId` at `0x1800f6450`
- `Apx01000!imp_ApxDeviceInitAssignInstanceId` at `0x1800f6450`
- `Apx01000!imp_ApxDeviceInitAssignFriendlyName` at `0x1800f6494`
- `Apx01000!imp_ApxDeviceInitAssignFriendlyName` at `0x1800f6494`
- `Apx01000!imp_ApxDeviceCreate` at `0x1800f64cc`
- `Apx01000!imp_ApxDeviceCreate` at `0x1800f64cc`

## string_xrefs

- `0x1800f6300`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f6466`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f64aa`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f64e2`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f64d6`: `ApxDeviceCreate failed`

## pseudocode

```c
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupDevice(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *this)
{
  __int64 v2; // rax
  __int64 *v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  const wchar_t *v14; // rax
  unsigned int inited; // eax
  const wchar_t *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int16 v19; // [rsp+28h] [rbp-28h]
  char *v20; // [rsp+28h] [rbp-28h]
  char *v21; // [rsp+28h] [rbp-28h]
  char *v22; // [rsp+28h] [rbp-28h]
  _BYTE v23[8]; // [rsp+30h] [rbp-20h] BYREF
  int v24; // [rsp+38h] [rbp-18h] BYREF
  __int128 v25; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int16 v27; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int16 v28; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 v29; // [rsp+80h] [rbp+30h] BYREF
  int v30; // [rsp+88h] [rbp+38h] BYREF

  v2 = imp_ApxDeviceInitAllocate(0);
  *((_QWORD *)this + 24) = v2;
  wil::details::in1diag3::Throw_IfNullAllocMsg<APXDEVICE_INIT__ *,0>(
    retaddr,
    365,
    "shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    v2,
    "ApxDeviceInitAllocate failed");
  imp_ApxDeviceInitSetControlInterfaceId(0, *((_QWORD *)this + 24), (char *)this + 88);
  v3 = (__int64 *)*((_QWORD *)this + 18);
  v27 = 0;
  v24 = 0;
  v4 = *v3;
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(v4 + 72))(v3, &v27);
  winrt::check_hresult(&v28, v5, &v24);
  v6 = *((_QWORD *)this + 18);
  v30 = 0;
  v24 = 0;
  v25 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 64LL))(v6, &v30);
  winrt::check_hresult(&v28, v7, &v24);
  v8 = (__int64 *)*((_QWORD *)this + 18);
  v28 = 0;
  v24 = 0;
  v9 = *v8;
  v25 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *))(v9 + 56))(v8, &v28);
  winrt::check_hresult(&v29, v10, &v24);
  v11 = (__int64 *)*((_QWORD *)this + 18);
  v29 = 0;
  v24 = 0;
  v12 = *v11;
  v25 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *))(v12 + 48))(v11, &v29);
  winrt::check_hresult(v23, v13, &v24);
  v19 = v27;
  imp_ApxDeviceInitSetProductId(0, *((_QWORD *)this + 24), v29, v28, v30, v19);
  imp_ApxDeviceInitSetProductType(0, *((_QWORD *)this + 24), (char *)this + 120);
  imp_ApxDeviceInitSetContainerId(0, *((_QWORD *)this + 24), (char *)this + 104);
  v14 = winrt::hstring::c_str((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 80));
  inited = imp_ApxDeviceInitAssignInstanceId(0, *((_QWORD *)this + 24), v14);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x176,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)inited,
    (int)"ApxDeviceInitAssignInstanceId failed",
    v20);
  v16 = winrt::hstring::c_str((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 136));
  v17 = imp_ApxDeviceInitAssignFriendlyName(0, *((_QWORD *)this + 24), v16, 1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x17A,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v17,
    (int)"ApxDeviceInitAssignFriendlyName failed",
    v21);
  v18 = imp_ApxDeviceCreate(0, 0, (char *)this + 192, (char *)this + 200);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x181,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v18,
    (int)"ApxDeviceCreate failed",
    v22);
}

```

## disassembly

```asm
0x1800f62c8  push    rbp
0x1800f62ca  push    rbx
0x1800f62cb  push    rdi
0x1800f62cc  mov     rbp, rsp
0x1800f62cf  sub     rsp, 50h
0x1800f62d3  mov     rdi, rcx
0x1800f62d6  xor     ecx, ecx
0x1800f62d8  call    cs:__imp_imp_ApxDeviceInitAllocate
0x1800f62de  mov     rcx, [rbp+18h]
0x1800f62e2  lea     rdx, aApxdeviceinita; "ApxDeviceInitAllocate failed"
0x1800f62e9  mov     qword ptr [rsp+50h+var_30], rdx
0x1800f62ee  lea     rbx, [rdi+0C0h]
0x1800f62f5  mov     edx, 16Dh
0x1800f62fa  mov     [rbx], rax
0x1800f62fd  mov     r9, rax
0x1800f6300  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f6307  call    ??$Throw_IfNullAllocMsg@PEAUAPXDEVICE_INIT__@@$0A@@in1diag3@details@wil@@YAPEAUAPXDEVICE_INIT__@@PEAXIPEBDPEAU3@1ZZ; wil::details::in1diag3::Throw_IfNullAllocMsg<APXDEVICE_INIT__ *,0>(void *,uint,char const *,APXDEVICE_INIT__ *,char const *,...)
0x1800f630c  mov     rdx, [rbx]
0x1800f630f  lea     r8, [rdi+58h]
0x1800f6313  xor     ecx, ecx
0x1800f6315  call    cs:__imp_imp_ApxDeviceInitSetControlInterfaceId
0x1800f631b  mov     rcx, [rdi+90h]
0x1800f6322  lea     rdx, [rbp+arg_0]
0x1800f6326  xor     eax, eax
0x1800f6328  xorps   xmm0, xmm0
0x1800f632b  mov     [rbp+arg_0], ax
0x1800f632f  mov     [rbp+var_18], eax
0x1800f6332  mov     rax, [rcx]
0x1800f6335  movdqu  [rbp+var_10], xmm0
0x1800f633a  mov     rax, [rax+48h]
0x1800f633e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6343  lea     r8, [rbp+var_18]
0x1800f6347  mov     edx, eax
0x1800f6349  lea     rcx, [rbp+arg_8]
0x1800f634d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800f6352  mov     rcx, [rdi+90h]
0x1800f6359  lea     rdx, [rbp+arg_18]
0x1800f635d  mov     [rbp+arg_18], 0
0x1800f6364  xorps   xmm0, xmm0
0x1800f6367  mov     [rbp+var_18], 0
0x1800f636e  movdqu  [rbp+var_10], xmm0
0x1800f6373  mov     rax, [rcx]
0x1800f6376  mov     rax, [rax+40h]
0x1800f637a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f637f  lea     r8, [rbp+var_18]
0x1800f6383  mov     edx, eax
0x1800f6385  lea     rcx, [rbp+arg_8]
0x1800f6389  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800f638e  mov     rcx, [rdi+90h]
0x1800f6395  lea     rdx, [rbp+arg_8]
0x1800f6399  xor     eax, eax
0x1800f639b  xorps   xmm0, xmm0
0x1800f639e  mov     [rbp+arg_8], ax
0x1800f63a2  mov     [rbp+var_18], eax
0x1800f63a5  mov     rax, [rcx]
0x1800f63a8  movdqu  [rbp+var_10], xmm0
0x1800f63ad  mov     rax, [rax+38h]
0x1800f63b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f63b6  lea     r8, [rbp+var_18]
0x1800f63ba  mov     edx, eax
0x1800f63bc  lea     rcx, [rbp+arg_10]
0x1800f63c0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800f63c5  mov     rcx, [rdi+90h]
0x1800f63cc  lea     rdx, [rbp+arg_10]
0x1800f63d0  xor     eax, eax
0x1800f63d2  xorps   xmm0, xmm0
0x1800f63d5  mov     [rbp+arg_10], ax
0x1800f63d9  mov     [rbp+var_18], eax
0x1800f63dc  mov     rax, [rcx]
0x1800f63df  movdqu  [rbp+var_10], xmm0
0x1800f63e4  mov     rax, [rax+30h]
0x1800f63e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f63ed  lea     r8, [rbp+var_18]
0x1800f63f1  mov     edx, eax
0x1800f63f3  lea     rcx, [rbp+var_20]
0x1800f63f7  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800f63fc  movzx   eax, [rbp+arg_0]
0x1800f6400  xor     ecx, ecx
0x1800f6402  movzx   r9d, [rbp+arg_8]
0x1800f6407  movzx   r8d, [rbp+arg_10]
0x1800f640c  mov     rdx, [rbx]
0x1800f640f  mov     word ptr [rsp+50h+var_28], ax; char *
0x1800f6414  mov     eax, [rbp+arg_18]
0x1800f6417  mov     [rsp+50h+var_30], eax
0x1800f641b  call    cs:__imp_imp_ApxDeviceInitSetProductId
0x1800f6421  lea     r8, [rdi+78h]
0x1800f6425  mov     rdx, [rbx]
0x1800f6428  xor     ecx, ecx
0x1800f642a  call    cs:__imp_imp_ApxDeviceInitSetProductType
0x1800f6430  mov     rdx, [rbx]
0x1800f6433  lea     r8, [rdi+68h]
0x1800f6437  xor     ecx, ecx
0x1800f6439  call    cs:__imp_imp_ApxDeviceInitSetContainerId
0x1800f643f  lea     rcx, [rdi+50h]; this
0x1800f6443  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800f6448  mov     rdx, [rbx]
0x1800f644b  mov     r8, rax
0x1800f644e  xor     ecx, ecx
0x1800f6450  call    cs:__imp_imp_ApxDeviceInitAssignInstanceId
0x1800f6456  mov     rcx, [rbp+18h]; this
0x1800f645a  lea     rdx, aApxdeviceinita_1; "ApxDeviceInitAssignInstanceId failed"
0x1800f6461  mov     qword ptr [rsp+50h+var_30], rdx; int
0x1800f6466  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f646d  mov     edx, 176h; void *
0x1800f6472  mov     r9d, eax; char *
0x1800f6475  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f647a  lea     rcx, [rdi+88h]; this
0x1800f6481  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800f6486  mov     rdx, [rbx]
0x1800f6489  mov     r8, rax
0x1800f648c  mov     r9d, 1
0x1800f6492  xor     ecx, ecx
0x1800f6494  call    cs:__imp_imp_ApxDeviceInitAssignFriendlyName
0x1800f649a  mov     rcx, [rbp+18h]; this
0x1800f649e  lea     rdx, aApxdeviceinita_0; "ApxDeviceInitAssignFriendlyName failed"
0x1800f64a5  mov     qword ptr [rsp+50h+var_30], rdx; int
0x1800f64aa  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f64b1  mov     edx, 17Ah; void *
0x1800f64b6  mov     r9d, eax; char *
0x1800f64b9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f64be  lea     r9, [rdi+0C8h]
0x1800f64c5  mov     r8, rbx
0x1800f64c8  xor     edx, edx
0x1800f64ca  xor     ecx, ecx
0x1800f64cc  call    cs:__imp_imp_ApxDeviceCreate
0x1800f64d2  mov     rcx, [rbp+18h]; this
0x1800f64d6  lea     rdx, aApxdevicecreat; "ApxDeviceCreate failed"
0x1800f64dd  mov     qword ptr [rsp+50h+var_30], rdx; int
0x1800f64e2  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f64e9  mov     edx, 181h; void *
0x1800f64ee  mov     r9d, eax; char *
0x1800f64f1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f64f6  add     rsp, 50h
0x1800f64fa  pop     rdi
0x1800f64fb  pop     rbx
0x1800f64fc  pop     rbp
0x1800f64fd  retn
```
