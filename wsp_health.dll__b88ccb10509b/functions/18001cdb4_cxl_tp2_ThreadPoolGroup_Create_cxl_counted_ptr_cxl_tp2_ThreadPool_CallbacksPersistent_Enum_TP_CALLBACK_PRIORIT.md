# cxl::tp2::ThreadPoolGroup::Create(cxl::counted_ptr<cxl::tp2::ThreadPool>,CallbacksPersistent::Enum,_TP_CALLBACK_PRIORITY,CallbacksRunsLong::Enum,void *)

- ea: `0x18001cdb4`
- end: `0x18001ce82`
- name: `?Create@ThreadPoolGroup@tp2@cxl@@AEAAXU?$counted_ptr@VThreadPool@tp2@cxl@@@3@W4Enum@CallbacksPersistent@@W4_TP_CALLBACK_PRIORITY@@W45CallbacksRunsLong@@PEAX@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c314`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x180017d08`
- `0x18001cdb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce04`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001cdde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001cdde`

## string_xrefs

- `0x18001cdf0`: `CreateThreadpoolCleanupGroup has failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall cxl::tp2::ThreadPoolGroup::Create(_QWORD *a1, __int64 a2)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 v5; // rbx
  _DWORD v7[2]; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v8; // [rsp+28h] [rbp-B0h]
  _BYTE v9[32]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  v8 = a2;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  a1[3] = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    v5 = std::wstring::wstring(v9, L"CreateThreadpoolCleanupGroup has failed");
    v7[0] = GetLastError();
    v7[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v7, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( *(_QWORD *)a2 )
    a1[5] = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
  a1[6] = ThreadpoolCleanupGroup;
  a1[7] = cxl::tp2::ThreadPoolGroup::OnClosedCallback;
  return cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(a2);
}

```

## disassembly

```asm
0x18001cdb4  mov     [rsp+arg_10], rbx
0x18001cdb9  push    rdi
0x18001cdba  sub     rsp, 0D0h
0x18001cdc1  mov     rax, cs:__security_cookie
0x18001cdc8  xor     rax, rsp
0x18001cdcb  mov     [rsp+0D8h+var_18], rax
0x18001cdd3  mov     rdi, rdx
0x18001cdd6  mov     rbx, rcx
0x18001cdd9  mov     [rsp+0D8h+var_B0], rdx
0x18001cdde  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001cde4  mov     rcx, rax
0x18001cde7  mov     [rbx+18h], rax
0x18001cdeb  test    rax, rax
0x18001cdee  jnz     short loc_18001CE3A
0x18001cdf0  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolCleanupGroup has failed"
0x18001cdf7  lea     rcx, [rsp+0D8h+var_A8]
0x18001cdfc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ce01  mov     rbx, rax
0x18001ce04  call    cs:__imp_GetLastError
0x18001ce0a  mov     [rsp+0D8h+var_B8], eax
0x18001ce0e  mov     [rsp+0D8h+var_B4], 0
0x18001ce16  mov     r8, rbx
0x18001ce19  lea     rdx, [rsp+0D8h+var_B8]
0x18001ce1e  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001ce23  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001ce28  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001ce2f  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001ce34  call    _CxxThrowException_0
0x18001ce3a  mov     rax, [rdi]
0x18001ce3d  test    rax, rax
0x18001ce40  jz      short loc_18001CE4A
0x18001ce42  mov     rax, [rax+18h]
0x18001ce46  mov     [rbx+28h], rax
0x18001ce4a  mov     [rbx+30h], rcx
0x18001ce4e  lea     rax, ?OnClosedCallback@ThreadPoolGroup@tp2@cxl@@CAXPEAX0@Z; cxl::tp2::ThreadPoolGroup::OnClosedCallback(void *,void *)
0x18001ce55  mov     [rbx+38h], rax
0x18001ce59  mov     rcx, rdi
0x18001ce5c  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001ce61  mov     rcx, [rsp+0D8h+var_18]
0x18001ce69  xor     rcx, rsp; StackCookie
0x18001ce6c  call    __security_check_cookie
0x18001ce71  mov     rbx, [rsp+0D8h+arg_10]
0x18001ce79  add     rsp, 0D0h
0x18001ce80  pop     rdi
0x18001ce81  retn
```
