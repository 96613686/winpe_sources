# cxl::tp2::TimerWorkItem::TimerWorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &)

- ea: `0x18001aa8c`
- end: `0x18001ab7c`
- name: `??0TimerWorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d8a4`
- `0x180020b6c`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x18001a4e0`
- `0x18001aa8c`
- `0x18001aca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001aaff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001aaff`

## string_xrefs

- `0x18001ab0e`: `CreateThreadpoolTimer has failed`

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
0x18001aa8c  mov     [rsp+arg_18], rbx
0x18001aa91  push    rdi
0x18001aa92  sub     rsp, 0D0h
0x18001aa99  mov     rax, cs:__security_cookie
0x18001aaa0  xor     rax, rsp
0x18001aaa3  mov     [rsp+0D8h+var_18], rax
0x18001aaab  mov     rbx, r8
0x18001aaae  mov     r9, rdx
0x18001aab1  mov     rdi, rcx
0x18001aab4  mov     [rsp+0D8h+var_B0], rcx
0x18001aab9  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x18001aabe  nop
0x18001aabf  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x18001aac6  mov     [rcx], rax
0x18001aac9  add     rcx, 20h ; ' '
0x18001aacd  mov     rdx, r9
0x18001aad0  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001aad5  nop
0x18001aad6  mov     qword ptr [rdi+38h], 0
0x18001aade  mov     dword ptr [rdi+40h], 0
0x18001aae5  mov     rax, [rbx]
0x18001aae8  lea     rcx, [rax+20h]
0x18001aaec  neg     rax
0x18001aaef  sbb     r8, r8
0x18001aaf2  and     r8, rcx; pcbe
0x18001aaf5  mov     rdx, rdi; pv
0x18001aaf8  lea     rcx, ?RunCallback@TimerWorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001aaff  call    cs:__imp_CreateThreadpoolTimer
0x18001ab05  mov     [rdi+38h], rax
0x18001ab09  test    rax, rax
0x18001ab0c  jnz     short loc_18001AB58
0x18001ab0e  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer has failed"
0x18001ab15  lea     rcx, [rsp+0D8h+var_A8]
0x18001ab1a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ab1f  mov     rbx, rax
0x18001ab22  call    cs:__imp_GetLastError
0x18001ab28  mov     [rsp+0D8h+var_B8], eax
0x18001ab2c  mov     [rsp+0D8h+var_B4], 0
0x18001ab34  mov     r8, rbx
0x18001ab37  lea     rdx, [rsp+0D8h+var_B8]
0x18001ab3c  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001ab41  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001ab46  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001ab4d  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001ab52  call    _CxxThrowException_0
0x18001ab58  mov     rax, rdi
0x18001ab5b  mov     rcx, [rsp+0D8h+var_18]
0x18001ab63  xor     rcx, rsp; StackCookie
0x18001ab66  call    __security_check_cookie
0x18001ab6b  mov     rbx, [rsp+0D8h+arg_18]
0x18001ab73  add     rsp, 0D0h
0x18001ab7a  pop     rdi
0x18001ab7b  retn
```
