# ComputeService::Resource::MemoryResourceAllocator::OpenVmmpHandleIfPresent(void)

- ea: `0x1400a3cc4`
- end: `0x1400a3d8b`
- name: `?OpenVmmpHandleIfPresent@MemoryResourceAllocator@Resource@ComputeService@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a39a0`
- `0x14028bc40`

## callees

- `0x140042468`
- `0x140080180`
- `0x1400a02f8`
- `0x1400a3cc4`
- `0x1400c4154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a3d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a3d45`
- `vid!VidMemPartOpen` at `0x1400a3d35`
- `vid!VidMemPartOpen` at `0x1400a3d35`
- `vid!VidOpenStatisticsHandle` at `0x1400a3cde`
- `vid!VidOpenStatisticsHandle` at `0x1400a3cde`

## string_xrefs

- `0x1400a3d02`: `onecore\vm\compute\management\resources\memory\memoryresourceallocator.cpp`
- `0x1400a3d60`: `onecore\vm\compute\management\resources\memory\memoryresourceallocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ComputeService::Resource::MemoryResourceAllocator::OpenVmmpHandleIfPresent(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  const char *v4; // r9
  __int64 v5; // rax
  DWORD LastError; // eax
  _QWORD v8[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8[1] = a2;
  v3 = VidOpenStatisticsHandle(a1);
  v8[0] = v3;
  if ( ((v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x456,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceallocator.cpp",
      v4);
  *a2 = 0;
  v5 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a2);
  if ( !(unsigned int)VidMemPartOpen(v3, 0, 1, v5) )
  {
    LastError = GetLastError();
    if ( LastError != 1168 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x466,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceallocator.cpp",
        (const char *)LastError,
        1u);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v8);
  return a2;
}

```

## disassembly

```asm
0x1400a3cc4  mov     [rsp+arg_0], rbx
0x1400a3cc9  push    rdi
0x1400a3cca  sub     rsp, 40h
0x1400a3cce  mov     rdi, rdx
0x1400a3cd1  mov     [rsp+48h+var_18], rdx
0x1400a3cd6  mov     [rsp+48h+var_28], 0
0x1400a3cde  call    cs:__imp_VidOpenStatisticsHandle
0x1400a3ce5  nop     dword ptr [rax+rax+00h]
0x1400a3cea  mov     rbx, rax
0x1400a3ced  mov     [rsp+48h+var_20], rax
0x1400a3cf2  inc     rax
0x1400a3cf5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400a3cfb  jnz     short loc_1400A3D14
0x1400a3cfd  mov     rcx, [rsp+48h]; this
0x1400a3d02  lea     r8, aOnecoreVmCompu_48; "onecore\\vm\\compute\\management\\resou"...
0x1400a3d09  mov     edx, 456h; void *
0x1400a3d0e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a3d14  xor     eax, eax
0x1400a3d16  mov     [rdi], rax
0x1400a3d19  mov     [rsp+48h+var_28], 1; unsigned int
0x1400a3d21  mov     rcx, rdi
0x1400a3d24  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1400a3d29  mov     r9, rax
0x1400a3d2c  xor     edx, edx
0x1400a3d2e  lea     r8d, [rdx+1]
0x1400a3d32  mov     rcx, rbx
0x1400a3d35  call    cs:__imp_VidMemPartOpen
0x1400a3d3c  nop     dword ptr [rax+rax+00h]
0x1400a3d41  test    eax, eax
0x1400a3d43  jnz     short loc_1400A3D72
0x1400a3d45  call    cs:__imp_GetLastError
0x1400a3d4c  nop     dword ptr [rax+rax+00h]
0x1400a3d51  cmp     eax, 490h
0x1400a3d56  jz      short loc_1400A3D72
0x1400a3d58  mov     rcx, [rsp+48h]; this
0x1400a3d5d  mov     r9d, eax; char *
0x1400a3d60  lea     r8, aOnecoreVmCompu_48; "onecore\\vm\\compute\\management\\resou"...
0x1400a3d67  mov     edx, 466h; void *
0x1400a3d6c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a3d72  lea     rcx, [rsp+48h+var_20]
0x1400a3d77  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x1400a3d7c  mov     rax, rdi
0x1400a3d7f  mov     rbx, [rsp+48h+arg_0]
0x1400a3d84  add     rsp, 40h
0x1400a3d88  pop     rdi
0x1400a3d89  retn
```
