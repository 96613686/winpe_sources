# cxl::tp2::TimerWorkItem::TimerWorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &)

- ea: `0x180018310`
- end: `0x18001840d`
- name: `??0TimerWorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@@Z`
- size: `253`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b270`
- `0x18001e4cc`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x180017d30`
- `0x180018310`
- `0x180018540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018383`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018383`

## string_xrefs

- `0x180018398`: `CreateThreadpoolTimer has failed`

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
0x180018310  mov     [rsp+arg_18], rbx
0x180018315  push    rdi
0x180018316  sub     rsp, 0D0h
0x18001831d  mov     rax, cs:__security_cookie
0x180018324  xor     rax, rsp
0x180018327  mov     [rsp+0D8h+var_18], rax
0x18001832f  mov     rbx, r8
0x180018332  mov     r9, rdx
0x180018335  mov     rdi, rcx
0x180018338  mov     [rsp+0D8h+var_B0], rcx
0x18001833d  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x180018342  nop
0x180018343  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x18001834a  mov     [rcx], rax
0x18001834d  add     rcx, 20h ; ' '
0x180018351  mov     rdx, r9
0x180018354  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x180018359  nop
0x18001835a  mov     qword ptr [rdi+38h], 0
0x180018362  mov     dword ptr [rdi+40h], 0
0x180018369  mov     rax, [rbx]
0x18001836c  lea     rcx, [rax+20h]
0x180018370  neg     rax
0x180018373  sbb     r8, r8
0x180018376  and     r8, rcx; pcbe
0x180018379  mov     rdx, rdi; pv
0x18001837c  lea     rcx, ?RunCallback@TimerWorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018383  call    cs:__imp_CreateThreadpoolTimer
0x18001838a  nop     dword ptr [rax+rax+00h]
0x18001838f  mov     [rdi+38h], rax
0x180018393  test    rax, rax
0x180018396  jnz     short loc_1800183E8
0x180018398  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer has failed"
0x18001839f  lea     rcx, [rsp+0D8h+var_A8]
0x1800183a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800183a9  mov     rbx, rax
0x1800183ac  call    cs:__imp_GetLastError
0x1800183b3  nop     dword ptr [rax+rax+00h]
0x1800183b8  mov     [rsp+0D8h+var_B8], eax
0x1800183bc  mov     [rsp+0D8h+var_B4], 0
0x1800183c4  mov     r8, rbx
0x1800183c7  lea     rdx, [rsp+0D8h+var_B8]
0x1800183cc  lea     rcx, [rsp+0D8h+pExceptionObject]
0x1800183d1  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800183d6  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800183dd  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800183e2  call    _CxxThrowException_0
0x1800183e8  mov     rax, rdi
0x1800183eb  mov     rcx, [rsp+0D8h+var_18]
0x1800183f3  xor     rcx, rsp; StackCookie
0x1800183f6  call    __security_check_cookie
0x1800183fb  mov     rbx, [rsp+0D8h+arg_18]
0x180018403  add     rsp, 0D0h
0x18001840a  pop     rdi
0x18001840b  retn
```
