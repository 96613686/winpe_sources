# cxl::tp2::ThreadPoolGroup::Create(cxl::counted_ptr<cxl::tp2::ThreadPool>,CallbacksPersistent::Enum,_TP_CALLBACK_PRIORITY,CallbacksRunsLong::Enum,void *)

- ea: `0x180020c6c`
- end: `0x180020d47`
- name: `?Create@ThreadPoolGroup@tp2@cxl@@AEAAXU?$counted_ptr@VThreadPool@tp2@cxl@@@3@W4Enum@CallbacksPersistent@@W4_TP_CALLBACK_PRIORITY@@W45CallbacksRunsLong@@PEAX@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020194`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x18001b85c`
- `0x180020c6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180020c96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180020c96`

## string_xrefs

- `0x180020cae`: `CreateThreadpoolCleanupGroup has failed`

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
0x180020c6c  mov     [rsp+arg_10], rbx
0x180020c71  push    rdi
0x180020c72  sub     rsp, 0D0h
0x180020c79  mov     rax, cs:__security_cookie
0x180020c80  xor     rax, rsp
0x180020c83  mov     [rsp+0D8h+var_18], rax
0x180020c8b  mov     rdi, rdx
0x180020c8e  mov     rbx, rcx
0x180020c91  mov     [rsp+0D8h+var_B0], rdx
0x180020c96  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180020c9d  nop     dword ptr [rax+rax+00h]
0x180020ca2  mov     rcx, rax
0x180020ca5  mov     [rbx+18h], rax
0x180020ca9  test    rax, rax
0x180020cac  jnz     short loc_180020CFE
0x180020cae  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolCleanupGroup has failed"
0x180020cb5  lea     rcx, [rsp+0D8h+var_A8]
0x180020cba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020cbf  mov     rbx, rax
0x180020cc2  call    cs:__imp_GetLastError
0x180020cc9  nop     dword ptr [rax+rax+00h]
0x180020cce  mov     [rsp+0D8h+var_B8], eax
0x180020cd2  mov     [rsp+0D8h+var_B4], 0
0x180020cda  mov     r8, rbx
0x180020cdd  lea     rdx, [rsp+0D8h+var_B8]
0x180020ce2  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180020ce7  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020cec  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020cf3  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180020cf8  call    _CxxThrowException_0
0x180020cfe  mov     rax, [rdi]
0x180020d01  test    rax, rax
0x180020d04  jz      short loc_180020D0E
0x180020d06  mov     rax, [rax+18h]
0x180020d0a  mov     [rbx+28h], rax
0x180020d0e  mov     [rbx+30h], rcx
0x180020d12  lea     rax, ?OnClosedCallback@ThreadPoolGroup@tp2@cxl@@CAXPEAX0@Z; cxl::tp2::ThreadPoolGroup::OnClosedCallback(void *,void *)
0x180020d19  mov     [rbx+38h], rax
0x180020d1d  mov     rcx, rdi
0x180020d20  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x180020d25  mov     rcx, [rsp+0D8h+var_18]
0x180020d2d  xor     rcx, rsp; StackCookie
0x180020d30  call    __security_check_cookie
0x180020d35  mov     rbx, [rsp+0D8h+arg_10]
0x180020d3d  add     rsp, 0D0h
0x180020d44  pop     rdi
0x180020d45  retn
```
