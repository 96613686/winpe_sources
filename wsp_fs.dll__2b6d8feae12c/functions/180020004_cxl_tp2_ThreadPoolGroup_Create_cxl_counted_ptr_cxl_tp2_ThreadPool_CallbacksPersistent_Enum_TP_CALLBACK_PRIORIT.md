# cxl::tp2::ThreadPoolGroup::Create(cxl::counted_ptr<cxl::tp2::ThreadPool>,CallbacksPersistent::Enum,_TP_CALLBACK_PRIORITY,CallbacksRunsLong::Enum,void *)

- ea: `0x180020004`
- end: `0x1800200d2`
- name: `?Create@ThreadPoolGroup@tp2@cxl@@AEAAXU?$counted_ptr@VThreadPool@tp2@cxl@@@3@W4Enum@CallbacksPersistent@@W4_TP_CALLBACK_PRIORITY@@W45CallbacksRunsLong@@PEAX@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001f558`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x18001adf0`
- `0x180020004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020054`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002002e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002002e`

## string_xrefs

- `0x180020040`: `CreateThreadpoolCleanupGroup has failed`

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
0x180020004  mov     [rsp+arg_10], rbx
0x180020009  push    rdi
0x18002000a  sub     rsp, 0D0h
0x180020011  mov     rax, cs:__security_cookie
0x180020018  xor     rax, rsp
0x18002001b  mov     [rsp+0D8h+var_18], rax
0x180020023  mov     rdi, rdx
0x180020026  mov     rbx, rcx
0x180020029  mov     [rsp+0D8h+var_B0], rdx
0x18002002e  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180020034  mov     rcx, rax
0x180020037  mov     [rbx+18h], rax
0x18002003b  test    rax, rax
0x18002003e  jnz     short loc_18002008A
0x180020040  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolCleanupGroup has failed"
0x180020047  lea     rcx, [rsp+0D8h+var_A8]
0x18002004c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020051  mov     rbx, rax
0x180020054  call    cs:__imp_GetLastError
0x18002005a  mov     [rsp+0D8h+var_B8], eax
0x18002005e  mov     [rsp+0D8h+var_B4], 0
0x180020066  mov     r8, rbx
0x180020069  lea     rdx, [rsp+0D8h+var_B8]
0x18002006e  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180020073  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020078  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18002007f  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180020084  call    _CxxThrowException_0
0x18002008a  mov     rax, [rdi]
0x18002008d  test    rax, rax
0x180020090  jz      short loc_18002009A
0x180020092  mov     rax, [rax+18h]
0x180020096  mov     [rbx+28h], rax
0x18002009a  mov     [rbx+30h], rcx
0x18002009e  lea     rax, ?OnClosedCallback@ThreadPoolGroup@tp2@cxl@@CAXPEAX0@Z; cxl::tp2::ThreadPoolGroup::OnClosedCallback(void *,void *)
0x1800200a5  mov     [rbx+38h], rax
0x1800200a9  mov     rcx, rdi
0x1800200ac  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x1800200b1  mov     rcx, [rsp+0D8h+var_18]
0x1800200b9  xor     rcx, rsp; StackCookie
0x1800200bc  call    __security_check_cookie
0x1800200c1  mov     rbx, [rsp+0D8h+arg_10]
0x1800200c9  add     rsp, 0D0h
0x1800200d0  pop     rdi
0x1800200d1  retn
```
