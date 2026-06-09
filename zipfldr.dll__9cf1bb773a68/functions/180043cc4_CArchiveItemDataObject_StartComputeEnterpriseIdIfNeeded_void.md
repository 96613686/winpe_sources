# CArchiveItemDataObject::StartComputeEnterpriseIdIfNeeded(void)

- ea: `0x180043cc4`
- end: `0x180043de1`
- name: `?StartComputeEnterpriseIdIfNeeded@CArchiveItemDataObject@@AEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(CArchiveItemDataObject *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026250`
- `0x1800433ac`

## callees

- `0x180031e94`
- `0x1800338f4`
- `0x180033928`
- `0x180039148`
- `0x180042f08`
- `0x1800438e0`
- `0x180043cc4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043cf4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043d53`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180043d72`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180043d72`

## pseudocode

```c
__int64 __fastcall CArchiveItemDataObject::StartComputeEnterpriseIdIfNeeded(CArchiveItemDataObject *this)
{
  char *v1; // rdi
  wil::details *v3; // rcx
  HANDLE Event; // rbx
  __int64 v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rsi
  DWORD CurrentThreadId; // eax
  int LastErrorFailHr; // ebx
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF
  char v15; // [rsp+48h] [rbp+10h] BYREF

  v1 = (char *)this + 648;
  if ( !*((_QWORD *)this + 81) )
  {
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v1,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
      if ( LastErrorFailHr < 0 )
      {
        v10 = 236;
        goto LABEL_12;
      }
    }
    v5 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v15, this);
    v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_bd8fcd46e4c52514adfce2bea4dc1017_____lambda_bd8fcd46e4c52514adfce2bea4dc1017___(
                      &v14,
                      v5);
    v7 = *v6;
    *v6 = 0;
    if ( v14 )
    {
      v14 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    CurrentThreadId = GetCurrentThreadId();
    v12 = v7;
    LastErrorFailHr = SHTaskPoolQueueTask(5, 0, CurrentThreadId, 0);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( LastErrorFailHr < 0 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v1,
        0);
      v10 = 249;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"shell\\ext\\zip\\idataobj.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v12);
      return (unsigned int)LastErrorFailHr;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180043cc4  mov     [rsp+arg_10], rbx
0x180043cc9  mov     [rsp+arg_18], rsi
0x180043cce  push    rdi
0x180043ccf  sub     rsp, 30h
0x180043cd3  lea     rdi, [rcx+288h]
0x180043cda  mov     rsi, rcx
0x180043cdd  cmp     qword ptr [rdi], 0
0x180043ce1  jnz     loc_180043DCF
0x180043ce7  mov     r9d, 1F0003h; dwDesiredAccess
0x180043ced  xor     r8d, r8d; dwFlags
0x180043cf0  xor     edx, edx; lpName
0x180043cf2  xor     ecx, ecx; lpEventAttributes
0x180043cf4  call    cs:__imp_CreateEventExW
0x180043cfa  mov     rbx, rax
0x180043cfd  test    rax, rax
0x180043d00  jz      loc_180043DA3
0x180043d06  call    cs:__imp_GetLastError
0x180043d0c  mov     rdx, rbx
0x180043d0f  mov     rcx, rdi
0x180043d12  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180043d17  mov     rdx, rsi
0x180043d1a  lea     rcx, [rsp+38h+arg_8]
0x180043d1f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180043d24  mov     rdx, rax
0x180043d27  lea     rcx, [rsp+38h+arg_0]
0x180043d2c  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_bd8fcd46e4c52514adfce2bea4dc1017_____lambda_bd8fcd46e4c52514adfce2bea4dc1017___
0x180043d31  mov     rsi, [rax]
0x180043d34  mov     qword ptr [rax], 0
0x180043d3b  mov     rcx, [rsp+38h+arg_0]
0x180043d40  test    rcx, rcx
0x180043d43  jz      short loc_180043D53
0x180043d45  mov     [rsp+38h+arg_0], 0
0x180043d4e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180043d53  call    cs:__imp_GetCurrentThreadId
0x180043d59  xor     edx, edx
0x180043d5b  mov     [rsp+38h+var_10], 0
0x180043d64  xor     r9d, r9d
0x180043d67  mov     [rsp+38h+var_18], rsi
0x180043d6c  mov     r8d, eax
0x180043d6f  lea     ecx, [rdx+5]
0x180043d72  call    cs:__imp_SHTaskPoolQueueTask
0x180043d78  mov     ebx, eax
0x180043d7a  test    rsi, rsi
0x180043d7d  jz      short loc_180043D8E
0x180043d7f  mov     rdx, [rsi]
0x180043d82  mov     rcx, rsi
0x180043d85  mov     rax, [rdx+10h]
0x180043d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d8e  test    ebx, ebx
0x180043d90  jns     short loc_180043DCF
0x180043d92  xor     edx, edx
0x180043d94  mov     rcx, rdi
0x180043d97  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180043d9c  mov     edx, 0F9h
0x180043da1  jmp     short loc_180043DB7
0x180043da3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043da8  mov     ebx, eax
0x180043daa  test    eax, eax
0x180043dac  jns     loc_180043D17
0x180043db2  mov     edx, 0ECh; void *
0x180043db7  mov     rcx, [rsp+38h]; this
0x180043dbc  lea     r8, aShellExtZipIda; "shell\\ext\\zip\\idataobj.cpp"
0x180043dc3  mov     r9d, ebx; char *
0x180043dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043dcb  mov     eax, ebx
0x180043dcd  jmp     short loc_180043DD1
0x180043dcf  xor     eax, eax
0x180043dd1  mov     rbx, [rsp+38h+arg_10]
0x180043dd6  mov     rsi, [rsp+38h+arg_18]
0x180043ddb  add     rsp, 30h
0x180043ddf  pop     rdi
0x180043de0  retn
```
