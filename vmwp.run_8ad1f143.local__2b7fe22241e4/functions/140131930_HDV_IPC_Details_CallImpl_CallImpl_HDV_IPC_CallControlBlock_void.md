# HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)

- ea: `0x140131930`
- end: `0x140131b4c`
- name: `??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z`
- size: `540`
- prototype: `_QWORD(HDV::IPC::Details::CallImpl *__hidden this, struct HDV::IPC::CallControlBlock *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140131440`

## callees

- `0x1400216b4`
- `0x14005b648`
- `0x140084204`
- `0x140096760`
- `0x140131930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401319f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140131a99`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401319f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140131a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131adf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131a6a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131b10`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131a6a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131b10`

## string_xrefs

- `0x140131a24`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131a7f`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131ac9`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131b25`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HDV::IPC::Details::CallImpl *__fastcall HDV::IPC::Details::CallImpl::CallImpl(
        HDV::IPC::Details::CallImpl *this,
        struct HDV::IPC::CallControlBlock *a2,
        void *a3)
{
  const char *v6; // r9
  void *v7; // r14
  HANDLE *v8; // rbx
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  const char *v11; // r9
  void *v12; // rdi
  __int64 v13; // rbx
  HANDLE v14; // rax
  const char *v15; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *((_QWORD *)this + 1) = MigrationTransferTransportAdapterTarget::`vbtable'{for `IMigrationTransferTransportAdapterTarget'};
  Vml::VmSharableObject::VmSharableObject((HDV::IPC::Details::CallImpl *)((char *)this + 80));
  *((_QWORD *)this + 2) = 0;
  Vml::VmComLockServerImp<0>::VmComLockServerImp<0>((char *)this + 24);
  *(_QWORD *)this = &HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmComObject'};
  *((_QWORD *)this + 3) = &HDV::IPC::Details::CallImpl::`vftable';
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmSharableObject'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 4) = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) - 72;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset((char *)this + 40);
  v7 = (void *)*((_QWORD *)this + 5);
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v6);
  v8 = (HANDLE *)*((_QWORD *)this + 4);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v7, a3, v8, 0x100002u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v10);
  CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset((char *)this + 48);
  v12 = (void *)*((_QWORD *)this + 6);
  if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v11);
  v13 = *((_QWORD *)this + 4);
  v14 = GetCurrentProcess();
  if ( !DuplicateHandle(v14, v12, a3, (LPHANDLE)(v13 + 8), 0x100002u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v15);
  return this;
}

```

## disassembly

```asm
0x140131930  mov     rax, rsp
0x140131933  mov     [rax+10h], rbx
0x140131937  mov     [rax+18h], rbp
0x14013193b  mov     [rax+20h], r9d
0x14013193f  mov     [rax+8], rcx
0x140131943  push    rsi
0x140131944  push    rdi
0x140131945  push    r14
0x140131947  sub     rsp, 40h
0x14013194b  mov     rbp, r8
0x14013194e  mov     rdi, rdx
0x140131951  mov     rsi, rcx
0x140131954  mov     dword ptr [rax+20h], 0
0x14013195b  lea     rax, ??_8MigrationTransferTransportAdapterTarget@@7BIMigrationTransferTransportAdapterTarget@@@; const MigrationTransferTransportAdapterTarget::`vbtable'{for `IMigrationTransferTransportAdapterTarget'}
0x140131962  mov     [rcx+8], rax
0x140131966  add     rcx, 50h ; 'P'; this
0x14013196a  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x14013196f  nop
0x140131970  mov     [rsp+58h+arg_18], 1
0x140131978  mov     qword ptr [rsi+10h], 0
0x140131980  lea     rcx, [rsi+18h]
0x140131984  call    ??0?$VmComLockServerImp@$0A@@Vml@@IEAA@XZ; Vml::VmComLockServerImp<0>::VmComLockServerImp<0>(void)
0x140131989  nop
0x14013198a  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmComObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmComObject'}
0x140131991  mov     [rsi], rax
0x140131994  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6B@; const HDV::IPC::Details::CallImpl::`vftable'
0x14013199b  mov     [rsi+18h], rax
0x14013199f  mov     rax, [rsi+8]
0x1401319a3  movsxd  rcx, dword ptr [rax+4]
0x1401319a7  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmSharableObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmSharableObject'}
0x1401319ae  mov     [rcx+rsi+8], rax
0x1401319b3  mov     rax, [rsi+8]
0x1401319b7  movsxd  rcx, dword ptr [rax+4]
0x1401319bb  lea     edx, [rcx-48h]
0x1401319be  mov     [rcx+rsi+4], edx
0x1401319c2  mov     [rsi+20h], rdi
0x1401319c6  lea     rbx, [rsi+28h]
0x1401319ca  mov     qword ptr [rbx], 0
0x1401319d1  lea     rdi, [rsi+30h]
0x1401319d5  mov     qword ptr [rdi], 0
0x1401319dc  mov     qword ptr [rsi+38h], 0
0x1401319e4  mov     word ptr [rsi+40h], 0
0x1401319ea  xor     r9d, r9d; lpName
0x1401319ed  xor     r8d, r8d; bInitialState
0x1401319f0  xor     edx, edx; bManualReset
0x1401319f2  xor     ecx, ecx; lpEventAttributes
0x1401319f4  call    cs:__imp_CreateEventW
0x1401319fb  nop     dword ptr [rax+rax+00h]
0x140131a00  mov     rdx, rax
0x140131a03  mov     rcx, rbx
0x140131a06  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140131a0b  mov     r14, [rbx]
0x140131a0e  lea     rax, [r14+1]
0x140131a12  test    rax, 0FFFFFFFFFFFFFFFEh
0x140131a18  setz    al
0x140131a1b  mov     rcx, [rsp+58h]; this
0x140131a20  test    al, al
0x140131a22  jz      short loc_140131A36
0x140131a24  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131a2b  mov     edx, 26h ; '&'; void *
0x140131a30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131a36  mov     rbx, [rsi+20h]
0x140131a3a  call    cs:__imp_GetCurrentProcess
0x140131a41  nop     dword ptr [rax+rax+00h]
0x140131a46  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140131a4e  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x140131a56  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x140131a5e  mov     r9, rbx; lpTargetHandle
0x140131a61  mov     r8, rbp; hTargetProcessHandle
0x140131a64  mov     rdx, r14; hSourceHandle
0x140131a67  mov     rcx, rax; hSourceProcessHandle
0x140131a6a  call    cs:__imp_DuplicateHandle
0x140131a71  nop     dword ptr [rax+rax+00h]
0x140131a76  mov     rcx, [rsp+58h]; this
0x140131a7b  test    eax, eax
0x140131a7d  jnz     short loc_140131A8F
0x140131a7f  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131a86  lea     edx, [rax+2Dh]; void *
0x140131a89  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131a8f  xor     r9d, r9d; lpName
0x140131a92  xor     r8d, r8d; bInitialState
0x140131a95  xor     edx, edx; bManualReset
0x140131a97  xor     ecx, ecx; lpEventAttributes
0x140131a99  call    cs:__imp_CreateEventW
0x140131aa0  nop     dword ptr [rax+rax+00h]
0x140131aa5  mov     rdx, rax
0x140131aa8  mov     rcx, rdi
0x140131aab  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140131ab0  mov     rdi, [rdi]
0x140131ab3  lea     rax, [rdi+1]
0x140131ab7  test    rax, 0FFFFFFFFFFFFFFFEh
0x140131abd  setz    al
0x140131ac0  mov     rcx, [rsp+58h]; this
0x140131ac5  test    al, al
0x140131ac7  jz      short loc_140131ADB
0x140131ac9  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131ad0  mov     edx, 30h ; '0'; void *
0x140131ad5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131adb  mov     rbx, [rsi+20h]
0x140131adf  call    cs:__imp_GetCurrentProcess
0x140131ae6  nop     dword ptr [rax+rax+00h]
0x140131aeb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140131af3  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x140131afb  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x140131b03  lea     r9, [rbx+8]; lpTargetHandle
0x140131b07  mov     r8, rbp; hTargetProcessHandle
0x140131b0a  mov     rdx, rdi; hSourceHandle
0x140131b0d  mov     rcx, rax; hSourceProcessHandle
0x140131b10  call    cs:__imp_DuplicateHandle
0x140131b17  nop     dword ptr [rax+rax+00h]
0x140131b1c  mov     rcx, [rsp+58h]; this
0x140131b21  test    eax, eax
0x140131b23  jnz     short loc_140131B35
0x140131b25  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131b2c  lea     edx, [rax+37h]; void *
0x140131b2f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131b35  mov     rax, rsi
0x140131b38  mov     rbx, [rsp+58h+arg_8]
0x140131b3d  mov     rbp, [rsp+58h+arg_10]
0x140131b42  add     rsp, 40h
0x140131b46  pop     r14
0x140131b48  pop     rdi
0x140131b49  pop     rsi
0x140131b4a  retn
```
