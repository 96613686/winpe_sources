# cxl::tp2::TimerWorkItem::TimerWorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &)

- ea: `0x18001b4dc`
- end: `0x18001b5d9`
- name: `??0TimerWorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@@Z`
- size: `253`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e450`
- `0x18002180c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x18001aefc`
- `0x18001b4dc`
- `0x18001b70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b578`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b54f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b54f`

## string_xrefs

- `0x18001b564`: `CreateThreadpoolTimer has failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
cxl::tp2::WorkItemBase *__fastcall cxl::tp2::TimerWorkItem::TimerWorkItem(
        cxl::tp2::WorkItemBase *pv,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // r9
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v8; // rbx
  _DWORD v10[2]; // [rsp+20h] [rbp-B8h] BYREF
  cxl::tp2::WorkItemBase *v11; // [rsp+28h] [rbp-B0h]
  _BYTE v12[32]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  v11 = pv;
  cxl::tp2::WorkItemBase::WorkItemBase(pv);
  *v5 = &cxl::tp2::TimerWorkItem::`vftable';
  cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(v5 + 4, v6);
  *((_QWORD *)pv + 7) = 0;
  *((_DWORD *)pv + 16) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      cxl::tp2::TimerWorkItem::RunCallback,
                      pv,
                      (PTP_CALLBACK_ENVIRON)((*a3 + 32LL) & -(__int64)(*a3 != 0)));
  *((_QWORD *)pv + 7) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    v8 = std::wstring::wstring(v12, L"CreateThreadpoolTimer has failed");
    v10[0] = GetLastError();
    v10[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v10, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
  return pv;
}

```

## disassembly

```asm
0x18001b4dc  mov     [rsp+arg_18], rbx
0x18001b4e1  push    rdi
0x18001b4e2  sub     rsp, 0D0h
0x18001b4e9  mov     rax, cs:__security_cookie
0x18001b4f0  xor     rax, rsp
0x18001b4f3  mov     [rsp+0D8h+var_18], rax
0x18001b4fb  mov     rbx, r8
0x18001b4fe  mov     r9, rdx
0x18001b501  mov     rdi, rcx
0x18001b504  mov     [rsp+0D8h+var_B0], rcx
0x18001b509  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x18001b50e  nop
0x18001b50f  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x18001b516  mov     [rcx], rax
0x18001b519  add     rcx, 20h ; ' '
0x18001b51d  mov     rdx, r9
0x18001b520  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001b525  nop
0x18001b526  mov     qword ptr [rdi+38h], 0
0x18001b52e  mov     dword ptr [rdi+40h], 0
0x18001b535  mov     rax, [rbx]
0x18001b538  lea     rcx, [rax+20h]
0x18001b53c  neg     rax
0x18001b53f  sbb     r8, r8
0x18001b542  and     r8, rcx; pcbe
0x18001b545  mov     rdx, rdi; pv
0x18001b548  lea     rcx, ?RunCallback@TimerWorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b54f  call    cs:__imp_CreateThreadpoolTimer
0x18001b556  nop     dword ptr [rax+rax+00h]
0x18001b55b  mov     [rdi+38h], rax
0x18001b55f  test    rax, rax
0x18001b562  jnz     short loc_18001B5B4
0x18001b564  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer has failed"
0x18001b56b  lea     rcx, [rsp+0D8h+var_A8]
0x18001b570  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001b575  mov     rbx, rax
0x18001b578  call    cs:__imp_GetLastError
0x18001b57f  nop     dword ptr [rax+rax+00h]
0x18001b584  mov     [rsp+0D8h+var_B8], eax
0x18001b588  mov     [rsp+0D8h+var_B4], 0
0x18001b590  mov     r8, rbx
0x18001b593  lea     rdx, [rsp+0D8h+var_B8]
0x18001b598  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001b59d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001b5a2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001b5a9  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001b5ae  call    _CxxThrowException_0
0x18001b5b4  mov     rax, rdi
0x18001b5b7  mov     rcx, [rsp+0D8h+var_18]
0x18001b5bf  xor     rcx, rsp; StackCookie
0x18001b5c2  call    __security_check_cookie
0x18001b5c7  mov     rbx, [rsp+0D8h+arg_18]
0x18001b5cf  add     rsp, 0D0h
0x18001b5d6  pop     rdi
0x18001b5d7  retn
```
