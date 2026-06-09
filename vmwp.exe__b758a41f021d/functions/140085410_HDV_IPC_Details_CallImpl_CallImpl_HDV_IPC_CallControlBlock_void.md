# HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)

- ea: `0x140085410`
- end: `0x14008562c`
- name: `??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z`
- size: `540`
- prototype: `_QWORD(HDV::IPC::Details::CallImpl *__hidden this, struct HDV::IPC::CallControlBlock *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140084f20`

## callees

- `0x140021c24`
- `0x1400812e4`
- `0x140083990`
- `0x140085410`
- `0x140085634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400854d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140085579`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400854d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140085579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400855bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400855bf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14008554a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400855f0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14008554a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400855f0`

## string_xrefs

- `0x140085504`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x14008555f`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x1400855a9`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140085605`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

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
0x140085410  mov     rax, rsp
0x140085413  mov     [rax+10h], rbx
0x140085417  mov     [rax+18h], rbp
0x14008541b  mov     [rax+20h], r9d
0x14008541f  mov     [rax+8], rcx
0x140085423  push    rsi
0x140085424  push    rdi
0x140085425  push    r14
0x140085427  sub     rsp, 40h
0x14008542b  mov     rbp, r8
0x14008542e  mov     rdi, rdx
0x140085431  mov     rsi, rcx
0x140085434  mov     dword ptr [rax+20h], 0
0x14008543b  lea     rax, ??_8MigrationTransferTransportAdapterTarget@@7BIMigrationTransferTransportAdapterTarget@@@; const MigrationTransferTransportAdapterTarget::`vbtable'{for `IMigrationTransferTransportAdapterTarget'}
0x140085442  mov     [rcx+8], rax
0x140085446  add     rcx, 50h ; 'P'; this
0x14008544a  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x14008544f  nop
0x140085450  mov     [rsp+58h+arg_18], 1
0x140085458  mov     qword ptr [rsi+10h], 0
0x140085460  lea     rcx, [rsi+18h]
0x140085464  call    ??0?$VmComLockServerImp@$0A@@Vml@@IEAA@XZ; Vml::VmComLockServerImp<0>::VmComLockServerImp<0>(void)
0x140085469  nop
0x14008546a  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmComObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmComObject'}
0x140085471  mov     [rsi], rax
0x140085474  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6B@; const HDV::IPC::Details::CallImpl::`vftable'
0x14008547b  mov     [rsi+18h], rax
0x14008547f  mov     rax, [rsi+8]
0x140085483  movsxd  rcx, dword ptr [rax+4]
0x140085487  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmSharableObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmSharableObject'}
0x14008548e  mov     [rcx+rsi+8], rax
0x140085493  mov     rax, [rsi+8]
0x140085497  movsxd  rcx, dword ptr [rax+4]
0x14008549b  lea     edx, [rcx-48h]
0x14008549e  mov     [rcx+rsi+4], edx
0x1400854a2  mov     [rsi+20h], rdi
0x1400854a6  lea     rbx, [rsi+28h]
0x1400854aa  mov     qword ptr [rbx], 0
0x1400854b1  lea     rdi, [rsi+30h]
0x1400854b5  mov     qword ptr [rdi], 0
0x1400854bc  mov     qword ptr [rsi+38h], 0
0x1400854c4  mov     word ptr [rsi+40h], 0
0x1400854ca  xor     r9d, r9d; lpName
0x1400854cd  xor     r8d, r8d; bInitialState
0x1400854d0  xor     edx, edx; bManualReset
0x1400854d2  xor     ecx, ecx; lpEventAttributes
0x1400854d4  call    cs:__imp_CreateEventW
0x1400854db  nop     dword ptr [rax+rax+00h]
0x1400854e0  mov     rdx, rax
0x1400854e3  mov     rcx, rbx
0x1400854e6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400854eb  mov     r14, [rbx]
0x1400854ee  lea     rax, [r14+1]
0x1400854f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400854f8  setz    al
0x1400854fb  mov     rcx, [rsp+58h]; this
0x140085500  test    al, al
0x140085502  jz      short loc_140085516
0x140085504  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14008550b  mov     edx, 26h ; '&'; void *
0x140085510  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140085516  mov     rbx, [rsi+20h]
0x14008551a  call    cs:__imp_GetCurrentProcess
0x140085521  nop     dword ptr [rax+rax+00h]
0x140085526  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14008552e  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x140085536  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x14008553e  mov     r9, rbx; lpTargetHandle
0x140085541  mov     r8, rbp; hTargetProcessHandle
0x140085544  mov     rdx, r14; hSourceHandle
0x140085547  mov     rcx, rax; hSourceProcessHandle
0x14008554a  call    cs:__imp_DuplicateHandle
0x140085551  nop     dword ptr [rax+rax+00h]
0x140085556  mov     rcx, [rsp+58h]; this
0x14008555b  test    eax, eax
0x14008555d  jnz     short loc_14008556F
0x14008555f  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140085566  lea     edx, [rax+2Dh]; void *
0x140085569  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14008556f  xor     r9d, r9d; lpName
0x140085572  xor     r8d, r8d; bInitialState
0x140085575  xor     edx, edx; bManualReset
0x140085577  xor     ecx, ecx; lpEventAttributes
0x140085579  call    cs:__imp_CreateEventW
0x140085580  nop     dword ptr [rax+rax+00h]
0x140085585  mov     rdx, rax
0x140085588  mov     rcx, rdi
0x14008558b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140085590  mov     rdi, [rdi]
0x140085593  lea     rax, [rdi+1]
0x140085597  test    rax, 0FFFFFFFFFFFFFFFEh
0x14008559d  setz    al
0x1400855a0  mov     rcx, [rsp+58h]; this
0x1400855a5  test    al, al
0x1400855a7  jz      short loc_1400855BB
0x1400855a9  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x1400855b0  mov     edx, 30h ; '0'; void *
0x1400855b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400855bb  mov     rbx, [rsi+20h]
0x1400855bf  call    cs:__imp_GetCurrentProcess
0x1400855c6  nop     dword ptr [rax+rax+00h]
0x1400855cb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1400855d3  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x1400855db  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x1400855e3  lea     r9, [rbx+8]; lpTargetHandle
0x1400855e7  mov     r8, rbp; hTargetProcessHandle
0x1400855ea  mov     rdx, rdi; hSourceHandle
0x1400855ed  mov     rcx, rax; hSourceProcessHandle
0x1400855f0  call    cs:__imp_DuplicateHandle
0x1400855f7  nop     dword ptr [rax+rax+00h]
0x1400855fc  mov     rcx, [rsp+58h]; this
0x140085601  test    eax, eax
0x140085603  jnz     short loc_140085615
0x140085605  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14008560c  lea     edx, [rax+37h]; void *
0x14008560f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140085615  mov     rax, rsi
0x140085618  mov     rbx, [rsp+58h+arg_8]
0x14008561d  mov     rbp, [rsp+58h+arg_10]
0x140085622  add     rsp, 40h
0x140085626  pop     r14
0x140085628  pop     rdi
0x140085629  pop     rsi
0x14008562a  retn
```
