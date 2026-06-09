# cxl::tp2::WorkItem::WorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &,cxl::Delegate<void (void)>)

- ea: `0x18001ab84`
- end: `0x18001ac9d`
- name: `??0WorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@U?$Delegate@$$A6AXXZ@2@@Z`
- size: `281`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, cxl::detail::DelegateBase *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001d398`
- `0x18002068c`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d194`
- `0x18000d33c`
- `0x18001a4e0`
- `0x18001ab84`
- `0x18001aca4`
- `0x18001b0a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac40`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ac1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ac1d`

## string_xrefs

- `0x18001ac2c`: `CreateThreadpoolWork has failed`

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
0x18001ab84  push    rbx
0x18001ab86  push    rbp
0x18001ab87  push    rsi
0x18001ab88  push    rdi
0x18001ab89  sub     rsp, 0E8h
0x18001ab90  mov     rax, cs:__security_cookie
0x18001ab97  xor     rax, rsp
0x18001ab9a  mov     [rsp+108h+var_38], rax
0x18001aba2  mov     rdi, r9
0x18001aba5  mov     rbx, rdx
0x18001aba8  mov     rsi, rcx
0x18001abab  mov     [rsp+108h+var_E0], rcx
0x18001abb0  mov     rbp, [rsp+108h+arg_20]
0x18001abb8  mov     [rsp+108h+var_D8], rbp
0x18001abbd  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x18001abc2  nop
0x18001abc3  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x18001abca  mov     [rcx], rax
0x18001abcd  add     rcx, 20h ; ' '
0x18001abd1  mov     rdx, r8
0x18001abd4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001abd9  nop
0x18001abda  lea     rcx, [rsi+40h]
0x18001abde  mov     rdx, rbx
0x18001abe1  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001abe6  nop
0x18001abe7  mov     qword ptr [rsi+58h], 0
0x18001abef  mov     dword ptr [rsi+60h], 0
0x18001abf6  lea     rcx, [rsi+68h]
0x18001abfa  mov     rdx, rbp
0x18001abfd  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x18001ac02  nop
0x18001ac03  mov     rax, [rdi]
0x18001ac06  lea     rcx, [rax+20h]
0x18001ac0a  neg     rax
0x18001ac0d  sbb     r8, r8
0x18001ac10  and     r8, rcx; pcbe
0x18001ac13  mov     rdx, rsi; pv
0x18001ac16  lea     rcx, ?RunCallback@WorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001ac1d  call    cs:__imp_CreateThreadpoolWork
0x18001ac23  mov     [rsi+58h], rax
0x18001ac27  test    rax, rax
0x18001ac2a  jnz     short loc_18001AC76
0x18001ac2c  lea     rdx, aCreatethreadpo_1; "CreateThreadpoolWork has failed"
0x18001ac33  lea     rcx, [rsp+108h+var_D0]
0x18001ac38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ac3d  mov     rbx, rax
0x18001ac40  call    cs:__imp_GetLastError
0x18001ac46  mov     [rsp+108h+var_E8], eax
0x18001ac4a  mov     [rsp+108h+var_E4], 0
0x18001ac52  mov     r8, rbx
0x18001ac55  lea     rdx, [rsp+108h+var_E8]
0x18001ac5a  lea     rcx, [rsp+108h+pExceptionObject]
0x18001ac5f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001ac64  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001ac6b  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001ac70  call    _CxxThrowException_0
0x18001ac76  mov     rcx, rbp; this
0x18001ac79  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001ac7e  mov     rax, rsi
0x18001ac81  mov     rcx, [rsp+108h+var_38]
0x18001ac89  xor     rcx, rsp; StackCookie
0x18001ac8c  call    __security_check_cookie
0x18001ac91  add     rsp, 0E8h
0x18001ac98  pop     rdi
0x18001ac99  pop     rsi
0x18001ac9a  pop     rbp
0x18001ac9b  pop     rbx
0x18001ac9c  retn
```
