# winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::ReleaseResources(void)

- ea: `0x1802e4eb8`
- end: `0x1802e50c4`
- name: `?ReleaseResources@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802e4afc`
- `0x18047ee35`
- `0x18047ef46`

## callees

- `0x18000b428`
- `0x180011f98`
- `0x180031f90`
- `0x18003b61c`
- `0x1802e47e4`
- `0x1802e4eb8`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1802e4f85`
- `msvcp_win!_Mtx_unlock` at `0x1802e4fdd`
- `msvcp_win!_Mtx_unlock` at `0x1802e4f85`
- `msvcp_win!_Mtx_unlock` at `0x1802e4fdd`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e5005`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e502d`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e5045`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e505a`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e506f`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e507f`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e508f`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e5005`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e502d`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e5045`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e505a`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e506f`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e507f`
- `Apx01000!imp_ApxObjectDelete` at `0x1802e508f`
- `Apx01000!imp_ApxCircuitInitFree` at `0x1802e5015`
- `Apx01000!imp_ApxCircuitInitFree` at `0x1802e5015`
- `Apx01000!imp_ApxDeviceInitFree` at `0x1802e509f`
- `Apx01000!imp_ApxDeviceInitFree` at `0x1802e509f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::ReleaseResources(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *this)
{
  struct _Mtx_internal_imp_t *v2; // rbx
  __int64 v3; // r14
  __int64 v4; // r12
  __int64 v5; // r13
  __int64 v6; // r15
  __int64 v7; // rbp
  __int64 v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+28h] [rbp-50h]
  __int64 v10; // [rsp+80h] [rbp+8h] BYREF
  __int64 v11; // [rsp+88h] [rbp+10h] BYREF
  __int64 v12; // [rsp+90h] [rbp+18h]
  __int64 v13; // [rsp+98h] [rbp+20h]

  v10 = 0;
  v2 = (winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 288);
  std::_Mutex_base::lock((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 288));
  v3 = *((_QWORD *)this + 28);
  v4 = *((_QWORD *)this + 27);
  v12 = *((_QWORD *)this + 32);
  v13 = *((_QWORD *)this + 31);
  v8 = *((_QWORD *)this + 30);
  v9 = *((_QWORD *)this + 29);
  v5 = *((_QWORD *)this + 26);
  v6 = *((_QWORD *)this + 25);
  v7 = *((_QWORD *)this + 24);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 33) = 0;
  _Mtx_unlock(v2);
  std::_Mutex_base::lock((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 368));
  winrt::Windows::Foundation::IUnknown::operator=(&v10, (char *)this + 176);
  v11 = 0;
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 176, &v11);
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v11);
  _Mtx_unlock((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 368));
  if ( v10 )
    winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Internal::Security::Isolation::VMStorage>::Close(&v10);
  if ( v3 )
    imp_ApxObjectDelete(0, v3);
  if ( v4 )
    imp_ApxCircuitInitFree(0, v4);
  if ( v12 )
    imp_ApxObjectDelete(0, v12);
  if ( v13 )
    imp_ApxObjectDelete(0, v13);
  if ( v8 )
    imp_ApxObjectDelete(0, v8);
  if ( v9 )
    imp_ApxObjectDelete(0, v9);
  if ( v5 )
    imp_ApxObjectDelete(0, v5);
  if ( v6 )
    imp_ApxObjectDelete(0, v6);
  if ( v7 )
    imp_ApxDeviceInitFree(0, v7);
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v10);
}

```

## disassembly

```asm
0x1802e4eb8  mov     rax, rsp
0x1802e4ebb  push    rbx
0x1802e4ebc  push    rbp
0x1802e4ebd  push    rsi
0x1802e4ebe  push    rdi
0x1802e4ebf  push    r12
0x1802e4ec1  push    r13
0x1802e4ec3  push    r14
0x1802e4ec5  push    r15
0x1802e4ec7  sub     rsp, 38h
0x1802e4ecb  mov     rsi, rcx
0x1802e4ece  xor     edi, edi
0x1802e4ed0  mov     [rax+8], rdi
0x1802e4ed4  lea     rbx, [rcx+120h]
0x1802e4edb  mov     rcx, rbx; this
0x1802e4ede  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802e4ee3  mov     r14, [rsi+0E0h]
0x1802e4eea  mov     r12, [rsi+0D8h]
0x1802e4ef1  mov     rax, [rsi+100h]
0x1802e4ef8  mov     [rsp+78h+arg_10], rax
0x1802e4f00  mov     rax, [rsi+0F8h]
0x1802e4f07  mov     [rsp+78h+arg_18], rax
0x1802e4f0f  mov     rax, [rsi+0F0h]
0x1802e4f16  mov     [rsp+78h+var_58], rax
0x1802e4f1b  mov     rax, [rsi+0E8h]
0x1802e4f22  mov     [rsp+78h+var_50], rax
0x1802e4f27  mov     r13, [rsi+0D0h]
0x1802e4f2e  mov     r15, [rsi+0C8h]
0x1802e4f35  mov     rbp, [rsi+0C0h]
0x1802e4f3c  mov     [rsi+0E0h], rdi
0x1802e4f43  mov     [rsi+0D8h], rdi
0x1802e4f4a  mov     [rsi+100h], rdi
0x1802e4f51  mov     [rsi+0F8h], rdi
0x1802e4f58  mov     [rsi+0F0h], rdi
0x1802e4f5f  mov     [rsi+0E8h], rdi
0x1802e4f66  mov     [rsi+0D0h], rdi
0x1802e4f6d  mov     [rsi+0C8h], rdi
0x1802e4f74  mov     [rsi+0C0h], rdi
0x1802e4f7b  mov     [rsi+108h], rdi
0x1802e4f82  mov     rcx, rbx; _Mtx_t
0x1802e4f85  call    cs:__imp__Mtx_unlock
0x1802e4f8b  lea     rdi, [rsi+170h]
0x1802e4f92  mov     rcx, rdi; this
0x1802e4f95  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802e4f9a  lea     rbx, [rsi+0B0h]
0x1802e4fa1  mov     rdx, rbx
0x1802e4fa4  lea     rcx, [rsp+78h+arg_0]
0x1802e4fac  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x1802e4fb1  mov     [rsp+78h+arg_8], 0
0x1802e4fbd  lea     rdx, [rsp+78h+arg_8]
0x1802e4fc5  mov     rcx, rbx
0x1802e4fc8  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1802e4fcd  lea     rcx, [rsp+78h+arg_8]; this
0x1802e4fd5  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1802e4fda  mov     rcx, rdi; _Mtx_t
0x1802e4fdd  call    cs:__imp__Mtx_unlock
0x1802e4fe3  cmp     [rsp+78h+arg_0], 0
0x1802e4fec  jz      short loc_1802E4FFB
0x1802e4fee  lea     rcx, [rsp+78h+arg_0]
0x1802e4ff6  call    ?Close@?$consume_Windows_Foundation_IClosable@UVMStorage@Isolation@Security@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Internal::Security::Isolation::VMStorage>::Close(void)
0x1802e4ffb  test    r14, r14
0x1802e4ffe  jz      short loc_1802E500B
0x1802e5000  mov     rdx, r14
0x1802e5003  xor     ecx, ecx
0x1802e5005  call    cs:__imp_imp_ApxObjectDelete
0x1802e500b  test    r12, r12
0x1802e500e  jz      short loc_1802E501B
0x1802e5010  mov     rdx, r12
0x1802e5013  xor     ecx, ecx
0x1802e5015  call    cs:__imp_imp_ApxCircuitInitFree
0x1802e501b  mov     rax, [rsp+78h+arg_10]
0x1802e5023  test    rax, rax
0x1802e5026  jz      short loc_1802E5033
0x1802e5028  mov     rdx, rax
0x1802e502b  xor     ecx, ecx
0x1802e502d  call    cs:__imp_imp_ApxObjectDelete
0x1802e5033  mov     rax, [rsp+78h+arg_18]
0x1802e503b  test    rax, rax
0x1802e503e  jz      short loc_1802E504B
0x1802e5040  mov     rdx, rax
0x1802e5043  xor     ecx, ecx
0x1802e5045  call    cs:__imp_imp_ApxObjectDelete
0x1802e504b  mov     rax, [rsp+78h+var_58]
0x1802e5050  test    rax, rax
0x1802e5053  jz      short loc_1802E5060
0x1802e5055  mov     rdx, rax
0x1802e5058  xor     ecx, ecx
0x1802e505a  call    cs:__imp_imp_ApxObjectDelete
0x1802e5060  mov     rax, [rsp+78h+var_50]
0x1802e5065  test    rax, rax
0x1802e5068  jz      short loc_1802E5075
0x1802e506a  mov     rdx, rax
0x1802e506d  xor     ecx, ecx
0x1802e506f  call    cs:__imp_imp_ApxObjectDelete
0x1802e5075  test    r13, r13
0x1802e5078  jz      short loc_1802E5085
0x1802e507a  mov     rdx, r13
0x1802e507d  xor     ecx, ecx
0x1802e507f  call    cs:__imp_imp_ApxObjectDelete
0x1802e5085  test    r15, r15
0x1802e5088  jz      short loc_1802E5095
0x1802e508a  mov     rdx, r15
0x1802e508d  xor     ecx, ecx
0x1802e508f  call    cs:__imp_imp_ApxObjectDelete
0x1802e5095  test    rbp, rbp
0x1802e5098  jz      short loc_1802E50A6
0x1802e509a  mov     rdx, rbp
0x1802e509d  xor     ecx, ecx
0x1802e509f  call    cs:__imp_imp_ApxDeviceInitFree
0x1802e50a5  nop
0x1802e50a6  lea     rcx, [rsp+78h+arg_0]; this
0x1802e50ae  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1802e50b3  add     rsp, 38h
0x1802e50b7  pop     r15
0x1802e50b9  pop     r14
0x1802e50bb  pop     r13
0x1802e50bd  pop     r12
0x1802e50bf  pop     rdi
0x1802e50c0  pop     rsi
0x1802e50c1  pop     rbp
0x1802e50c2  pop     rbx
0x1802e50c3  retn
```
