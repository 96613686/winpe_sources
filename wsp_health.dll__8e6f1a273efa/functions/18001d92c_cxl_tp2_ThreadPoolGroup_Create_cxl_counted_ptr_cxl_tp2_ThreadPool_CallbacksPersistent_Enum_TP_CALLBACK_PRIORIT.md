# cxl::tp2::ThreadPoolGroup::Create(cxl::counted_ptr<cxl::tp2::ThreadPool>,CallbacksPersistent::Enum,_TP_CALLBACK_PRIORITY,CallbacksRunsLong::Enum,void *)

- ea: `0x18001d92c`
- end: `0x18001da07`
- name: `?Create@ThreadPoolGroup@tp2@cxl@@AEAAXU?$counted_ptr@VThreadPool@tp2@cxl@@@3@W4Enum@CallbacksPersistent@@W4_TP_CALLBACK_PRIORITY@@W45CallbacksRunsLong@@PEAX@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001ce50`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x180018690`
- `0x18001d92c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d982`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001d956`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001d956`

## string_xrefs

- `0x18001d96e`: `CreateThreadpoolCleanupGroup has failed`

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
0x18001d92c  mov     [rsp+arg_10], rbx
0x18001d931  push    rdi
0x18001d932  sub     rsp, 0D0h
0x18001d939  mov     rax, cs:__security_cookie
0x18001d940  xor     rax, rsp
0x18001d943  mov     [rsp+0D8h+var_18], rax
0x18001d94b  mov     rdi, rdx
0x18001d94e  mov     rbx, rcx
0x18001d951  mov     [rsp+0D8h+var_B0], rdx
0x18001d956  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001d95d  nop     dword ptr [rax+rax+00h]
0x18001d962  mov     rcx, rax
0x18001d965  mov     [rbx+18h], rax
0x18001d969  test    rax, rax
0x18001d96c  jnz     short loc_18001D9BE
0x18001d96e  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolCleanupGroup has failed"
0x18001d975  lea     rcx, [rsp+0D8h+var_A8]
0x18001d97a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d97f  mov     rbx, rax
0x18001d982  call    cs:__imp_GetLastError
0x18001d989  nop     dword ptr [rax+rax+00h]
0x18001d98e  mov     [rsp+0D8h+var_B8], eax
0x18001d992  mov     [rsp+0D8h+var_B4], 0
0x18001d99a  mov     r8, rbx
0x18001d99d  lea     rdx, [rsp+0D8h+var_B8]
0x18001d9a2  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001d9a7  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001d9ac  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001d9b3  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001d9b8  call    _CxxThrowException_0
0x18001d9be  mov     rax, [rdi]
0x18001d9c1  test    rax, rax
0x18001d9c4  jz      short loc_18001D9CE
0x18001d9c6  mov     rax, [rax+18h]
0x18001d9ca  mov     [rbx+28h], rax
0x18001d9ce  mov     [rbx+30h], rcx
0x18001d9d2  lea     rax, ?OnClosedCallback@ThreadPoolGroup@tp2@cxl@@CAXPEAX0@Z; cxl::tp2::ThreadPoolGroup::OnClosedCallback(void *,void *)
0x18001d9d9  mov     [rbx+38h], rax
0x18001d9dd  mov     rcx, rdi
0x18001d9e0  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001d9e5  mov     rcx, [rsp+0D8h+var_18]
0x18001d9ed  xor     rcx, rsp; StackCookie
0x18001d9f0  call    __security_check_cookie
0x18001d9f5  mov     rbx, [rsp+0D8h+arg_10]
0x18001d9fd  add     rsp, 0D0h
0x18001da04  pop     rdi
0x18001da05  retn
```
