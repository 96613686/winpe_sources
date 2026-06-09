# cxl::tp2::WorkItem::WorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &,cxl::Delegate<void (void)>)

- ea: `0x18001b5e0`
- end: `0x18001b706`
- name: `??0WorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@U?$Delegate@$$A6AXXZ@2@@Z`
- size: `294`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, cxl::detail::DelegateBase *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001df00`
- `0x180021320`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d4fc`
- `0x18000d6a4`
- `0x18001aefc`
- `0x18001b5e0`
- `0x18001b70c`
- `0x18001bb14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b679`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b679`

## string_xrefs

- `0x18001b68e`: `CreateThreadpoolWork has failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
cxl::tp2::WorkItemBase *__fastcall cxl::tp2::WorkItem::WorkItem(
        cxl::tp2::WorkItemBase *pv,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        cxl::detail::DelegateBase *a5)
{
  _QWORD *v8; // rcx
  __int64 v9; // r8
  PTP_WORK ThreadpoolWork; // rax
  __int64 v11; // rbx
  _DWORD v13[2]; // [rsp+20h] [rbp-E8h] BYREF
  cxl::tp2::WorkItemBase *v14; // [rsp+28h] [rbp-E0h]
  cxl::detail::DelegateBase *v15; // [rsp+30h] [rbp-D8h]
  _BYTE v16[40]; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-A8h] BYREF

  v14 = pv;
  v15 = a5;
  cxl::tp2::WorkItemBase::WorkItemBase(pv);
  *v8 = &cxl::tp2::WorkItem::`vftable';
  std::string::string(v8 + 4, v9);
  cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>((char *)pv + 64, a2);
  *((_QWORD *)pv + 11) = 0;
  *((_DWORD *)pv + 24) = 0;
  cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>((char *)pv + 104, a5);
  ThreadpoolWork = CreateThreadpoolWork(
                     cxl::tp2::WorkItem::RunCallback,
                     pv,
                     (PTP_CALLBACK_ENVIRON)((*a4 + 32LL) & -(__int64)(*a4 != 0)));
  *((_QWORD *)pv + 11) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    v11 = std::wstring::wstring(v16, L"CreateThreadpoolWork has failed");
    v13[0] = GetLastError();
    v13[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v13, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::detail::DelegateBase::~DelegateBase(a5);
  return pv;
}

```

## disassembly

```asm
0x18001b5e0  push    rbx
0x18001b5e2  push    rbp
0x18001b5e3  push    rsi
0x18001b5e4  push    rdi
0x18001b5e5  sub     rsp, 0E8h
0x18001b5ec  mov     rax, cs:__security_cookie
0x18001b5f3  xor     rax, rsp
0x18001b5f6  mov     [rsp+108h+var_38], rax
0x18001b5fe  mov     rdi, r9
0x18001b601  mov     rbx, rdx
0x18001b604  mov     rsi, rcx
0x18001b607  mov     [rsp+108h+var_E0], rcx
0x18001b60c  mov     rbp, [rsp+108h+arg_20]
0x18001b614  mov     [rsp+108h+var_D8], rbp
0x18001b619  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x18001b61e  nop
0x18001b61f  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x18001b626  mov     [rcx], rax
0x18001b629  add     rcx, 20h ; ' '
0x18001b62d  mov     rdx, r8
0x18001b630  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001b635  nop
0x18001b636  lea     rcx, [rsi+40h]
0x18001b63a  mov     rdx, rbx
0x18001b63d  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001b642  nop
0x18001b643  mov     qword ptr [rsi+58h], 0
0x18001b64b  mov     dword ptr [rsi+60h], 0
0x18001b652  lea     rcx, [rsi+68h]
0x18001b656  mov     rdx, rbp
0x18001b659  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001b65e  nop
0x18001b65f  mov     rax, [rdi]
0x18001b662  lea     rcx, [rax+20h]
0x18001b666  neg     rax
0x18001b669  sbb     r8, r8
0x18001b66c  and     r8, rcx; pcbe
0x18001b66f  mov     rdx, rsi; pv
0x18001b672  lea     rcx, ?RunCallback@WorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b679  call    cs:__imp_CreateThreadpoolWork
0x18001b680  nop     dword ptr [rax+rax+00h]
0x18001b685  mov     [rsi+58h], rax
0x18001b689  test    rax, rax
0x18001b68c  jnz     short loc_18001B6DE
0x18001b68e  lea     rdx, aCreatethreadpo_1; "CreateThreadpoolWork has failed"
0x18001b695  lea     rcx, [rsp+108h+var_D0]
0x18001b69a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001b69f  mov     rbx, rax
0x18001b6a2  call    cs:__imp_GetLastError
0x18001b6a9  nop     dword ptr [rax+rax+00h]
0x18001b6ae  mov     [rsp+108h+var_E8], eax
0x18001b6b2  mov     [rsp+108h+var_E4], 0
0x18001b6ba  mov     r8, rbx
0x18001b6bd  lea     rdx, [rsp+108h+var_E8]
0x18001b6c2  lea     rcx, [rsp+108h+pExceptionObject]
0x18001b6c7  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001b6cc  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001b6d3  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001b6d8  call    _CxxThrowException_0
0x18001b6de  mov     rcx, rbp; this
0x18001b6e1  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001b6e6  mov     rax, rsi
0x18001b6e9  mov     rcx, [rsp+108h+var_38]
0x18001b6f1  xor     rcx, rsp; StackCookie
0x18001b6f4  call    __security_check_cookie
0x18001b6f9  add     rsp, 0E8h
0x18001b700  pop     rdi
0x18001b701  pop     rsi
0x18001b702  pop     rbp
0x18001b703  pop     rbx
0x18001b704  retn
```
