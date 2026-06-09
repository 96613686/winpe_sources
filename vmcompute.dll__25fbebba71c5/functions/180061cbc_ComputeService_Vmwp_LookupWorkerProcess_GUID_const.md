# ComputeService::Vmwp::LookupWorkerProcess(_GUID const &)

- ea: `0x180061cbc`
- end: `0x180061e81`
- name: `?LookupWorkerProcess@Vmwp@ComputeService@@YA?AUWorkerProcessContext@12@AEBU_GUID@@@Z`
- size: `453`
- prototype: `struct ComputeService::Vmwp::WorkerProcessContext __high(const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005095c`
- `0x180051750`

## callees

- `0x180002f50`
- `0x18000d0ec`
- `0x18000d108`
- `0x180022d10`
- `0x1800619b0`
- `0x180061cbc`
- `0x180061e88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061dcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061d86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061d86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061ddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061ddc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061d4a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061dae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061d4a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180061dae`

## string_xrefs

- `0x180061e39`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x180061e56`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x180061e6f`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComputeService::Vmwp::LookupWorkerProcess(
        __int64 a1,
        ComputeService::Vmwp::Details *a2,
        struct IUnknown **a3)
{
  __int64 (__fastcall ****v5)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // eax
  HANDLE v9; // rsi
  char *v10; // rbp
  DWORD LastError; // ebx
  HANDLE v12; // rsi
  const char *v13; // r9
  char *v14; // rbp
  DWORD v15; // ebx
  _QWORD v17[2]; // [rsp+28h] [rbp-40h] BYREF
  DWORD dwProcessId; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v17[1] = a1;
  v5 = (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = -1;
  dwProcessId = 0;
  if ( !ComputeService::Vmwp::Details::LookupWorkerProcessInterface(a2, (const struct _GUID *)(a1 + 16), a3) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4AA,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)0x490,
      1u);
  v17[0] = &dwProcessId;
  v8 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAK__ZPEAK_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAK_Z__QEAPEAK_Z(
         v6,
         *v5,
         v7,
         v17);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B0,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)v8,
      1);
  v9 = OpenProcess(0x100001u, 0, dwProcessId);
  v10 = *(char **)(a1 + 24);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v10);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 24) = v9;
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v12 = OpenProcess(0x100000u, 0, dwProcessId);
    v14 = *(char **)(a1 + 24);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v15 = GetLastError();
      CloseHandle(v14);
      SetLastError(v15);
    }
    *(_QWORD *)(a1 + 24) = v12;
    if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4C3,
        (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
        v13);
  }
  *(_OWORD *)a1 = *(_OWORD *)a2;
  return a1;
}

```

## disassembly

```asm
0x180061cbc  mov     [rsp+arg_10], rbx
0x180061cc1  mov     [rsp+arg_18], rbp
0x180061cc6  push    rsi
0x180061cc7  push    rdi
0x180061cc8  push    r14
0x180061cca  sub     rsp, 50h
0x180061cce  mov     rax, cs:__security_cookie
0x180061cd5  xor     rax, rsp
0x180061cd8  mov     [rsp+68h+var_28], rax
0x180061cdd  mov     r14, rdx
0x180061ce0  mov     rdi, rcx
0x180061ce3  mov     [rsp+68h+var_38], rcx
0x180061ce8  xor     esi, esi
0x180061cea  mov     [rsp+68h+var_48], esi
0x180061cee  lea     rbx, [rcx+10h]
0x180061cf2  mov     [rbx], rsi
0x180061cf5  mov     [rcx+18h], rsi
0x180061cf9  mov     dword ptr [rcx+20h], 0FFFFFFFFh
0x180061d00  mov     [rsp+68h+var_48], 1; int
0x180061d08  mov     [rsp+68h+dwProcessId], esi
0x180061d0c  mov     rdx, rbx; struct _GUID *
0x180061d0f  mov     rcx, r14; this
0x180061d12  call    ?LookupWorkerProcessInterface@Details@Vmwp@ComputeService@@YA_NAEBU_GUID@@PEAPEAUIUnknown@@@Z; ComputeService::Vmwp::Details::LookupWorkerProcessInterface(_GUID const &,IUnknown * *)
0x180061d17  test    al, al
0x180061d19  jz      loc_180061E4B
0x180061d1f  lea     rax, [rsp+68h+dwProcessId]
0x180061d24  mov     [rsp+68h+var_40], rax
0x180061d29  lea     r9, [rsp+68h+var_40]
0x180061d2e  mov     rdx, [rbx]
0x180061d31  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAK$$ZPEAK@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAK@Z$$QEAPEAK@Z
0x180061d36  test    eax, eax
0x180061d38  js      loc_180061E67
0x180061d3e  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x180061d43  xor     edx, edx; bInheritHandle
0x180061d45  mov     ecx, 100001h; dwDesiredAccess
0x180061d4a  call    cs:__imp_OpenProcess
0x180061d51  nop     dword ptr [rax+rax+00h]
0x180061d56  mov     rsi, rax
0x180061d59  mov     rbp, [rdi+18h]
0x180061d5d  lea     rdx, [rbp-1]
0x180061d61  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180061d65  ja      short loc_180061D92
0x180061d67  call    cs:__imp_GetLastError
0x180061d6e  nop     dword ptr [rax+rax+00h]
0x180061d73  mov     ebx, eax
0x180061d75  mov     rcx, rbp; hObject
0x180061d78  call    cs:__imp_CloseHandle
0x180061d7f  nop     dword ptr [rax+rax+00h]
0x180061d84  mov     ecx, ebx; dwErrCode
0x180061d86  call    cs:__imp_SetLastError
0x180061d8d  nop     dword ptr [rax+rax+00h]
0x180061d92  mov     [rdi+18h], rsi
0x180061d96  lea     rax, [rsi+1]
0x180061d9a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180061da0  jnz     short loc_180061E06
0x180061da2  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x180061da7  xor     edx, edx; bInheritHandle
0x180061da9  mov     ecx, 100000h; dwDesiredAccess
0x180061dae  call    cs:__imp_OpenProcess
0x180061db5  nop     dword ptr [rax+rax+00h]
0x180061dba  mov     rsi, rax
0x180061dbd  mov     rbp, [rdi+18h]
0x180061dc1  lea     rdx, [rbp-1]
0x180061dc5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180061dc9  ja      short loc_180061DF6
0x180061dcb  call    cs:__imp_GetLastError
0x180061dd2  nop     dword ptr [rax+rax+00h]
0x180061dd7  mov     ebx, eax
0x180061dd9  mov     rcx, rbp; hObject
0x180061ddc  call    cs:__imp_CloseHandle
0x180061de3  nop     dword ptr [rax+rax+00h]
0x180061de8  mov     ecx, ebx; dwErrCode
0x180061dea  call    cs:__imp_SetLastError
0x180061df1  nop     dword ptr [rax+rax+00h]
0x180061df6  mov     [rdi+18h], rsi
0x180061dfa  lea     rax, [rsi+1]
0x180061dfe  test    rax, 0FFFFFFFFFFFFFFFEh
0x180061e04  jz      short loc_180061E34
0x180061e06  movups  xmm0, xmmword ptr [r14]
0x180061e0a  movdqu  xmmword ptr [rdi], xmm0
0x180061e0e  mov     rax, rdi
0x180061e11  mov     rcx, [rsp+68h+var_28]
0x180061e16  xor     rcx, rsp; StackCookie
0x180061e19  call    __security_check_cookie
0x180061e1e  lea     r11, [rsp+68h+var_18]
0x180061e23  mov     rbx, [r11+30h]
0x180061e27  mov     rbp, [r11+38h]
0x180061e2b  mov     rsp, r11
0x180061e2e  pop     r14
0x180061e30  pop     rdi
0x180061e31  pop     rsi
0x180061e32  retn
0x180061e34  mov     rcx, [rsp+68h]; this
0x180061e39  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x180061e40  mov     edx, 4C3h; void *
0x180061e45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180061e4b  mov     rcx, [rsp+68h]; this
0x180061e50  mov     r9d, 490h; char *
0x180061e56  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x180061e5d  lea     edx, [r9+1Ah]; void *
0x180061e61  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180061e67  mov     rcx, [rsp+68h]; this
0x180061e6c  mov     r9d, eax; char *
0x180061e6f  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x180061e76  mov     edx, 4B0h; void *
0x180061e7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
