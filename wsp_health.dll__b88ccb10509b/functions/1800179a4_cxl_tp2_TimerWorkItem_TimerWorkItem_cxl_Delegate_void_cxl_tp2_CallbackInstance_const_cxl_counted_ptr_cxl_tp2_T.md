# cxl::tp2::TimerWorkItem::TimerWorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &)

- ea: `0x1800179a4`
- end: `0x180017a94`
- name: `??0TimerWorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a7c4`
- `0x18001d91c`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x1800173f8`
- `0x1800179a4`
- `0x180017bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017a17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017a17`

## string_xrefs

- `0x180017a26`: `CreateThreadpoolTimer has failed`

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
0x1800179a4  mov     [rsp+arg_18], rbx
0x1800179a9  push    rdi
0x1800179aa  sub     rsp, 0D0h
0x1800179b1  mov     rax, cs:__security_cookie
0x1800179b8  xor     rax, rsp
0x1800179bb  mov     [rsp+0D8h+var_18], rax
0x1800179c3  mov     rbx, r8
0x1800179c6  mov     r9, rdx
0x1800179c9  mov     rdi, rcx
0x1800179cc  mov     [rsp+0D8h+var_B0], rcx
0x1800179d1  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x1800179d6  nop
0x1800179d7  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x1800179de  mov     [rcx], rax
0x1800179e1  add     rcx, 20h ; ' '
0x1800179e5  mov     rdx, r9
0x1800179e8  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x1800179ed  nop
0x1800179ee  mov     qword ptr [rdi+38h], 0
0x1800179f6  mov     dword ptr [rdi+40h], 0
0x1800179fd  mov     rax, [rbx]
0x180017a00  lea     rcx, [rax+20h]
0x180017a04  neg     rax
0x180017a07  sbb     r8, r8
0x180017a0a  and     r8, rcx; pcbe
0x180017a0d  mov     rdx, rdi; pv
0x180017a10  lea     rcx, ?RunCallback@TimerWorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017a17  call    cs:__imp_CreateThreadpoolTimer
0x180017a1d  mov     [rdi+38h], rax
0x180017a21  test    rax, rax
0x180017a24  jnz     short loc_180017A70
0x180017a26  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer has failed"
0x180017a2d  lea     rcx, [rsp+0D8h+var_A8]
0x180017a32  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180017a37  mov     rbx, rax
0x180017a3a  call    cs:__imp_GetLastError
0x180017a40  mov     [rsp+0D8h+var_B8], eax
0x180017a44  mov     [rsp+0D8h+var_B4], 0
0x180017a4c  mov     r8, rbx
0x180017a4f  lea     rdx, [rsp+0D8h+var_B8]
0x180017a54  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180017a59  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017a5e  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017a65  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180017a6a  call    _CxxThrowException_0
0x180017a70  mov     rax, rdi
0x180017a73  mov     rcx, [rsp+0D8h+var_18]
0x180017a7b  xor     rcx, rsp; StackCookie
0x180017a7e  call    __security_check_cookie
0x180017a83  mov     rbx, [rsp+0D8h+arg_18]
0x180017a8b  add     rsp, 0D0h
0x180017a92  pop     rdi
0x180017a93  retn
```
