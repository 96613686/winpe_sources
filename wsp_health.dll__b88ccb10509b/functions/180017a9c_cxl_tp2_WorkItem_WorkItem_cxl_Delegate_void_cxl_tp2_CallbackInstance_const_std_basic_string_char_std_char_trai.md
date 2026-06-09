# cxl::tp2::WorkItem::WorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &,cxl::Delegate<void (void)>)

- ea: `0x180017a9c`
- end: `0x180017bb5`
- name: `??0WorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@U?$Delegate@$$A6AXXZ@2@@Z`
- size: `281`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, cxl::detail::DelegateBase *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001a2b8`
- `0x18001d43c`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c8ec`
- `0x18000c9f0`
- `0x18000cad8`
- `0x1800173f8`
- `0x180017a9c`
- `0x180017bbc`
- `0x180017fbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017b35`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017b35`

## string_xrefs

- `0x180017b44`: `CreateThreadpoolWork has failed`

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
0x180017a9c  push    rbx
0x180017a9e  push    rbp
0x180017a9f  push    rsi
0x180017aa0  push    rdi
0x180017aa1  sub     rsp, 0E8h
0x180017aa8  mov     rax, cs:__security_cookie
0x180017aaf  xor     rax, rsp
0x180017ab2  mov     [rsp+108h+var_38], rax
0x180017aba  mov     rdi, r9
0x180017abd  mov     rbx, rdx
0x180017ac0  mov     rsi, rcx
0x180017ac3  mov     [rsp+108h+var_E0], rcx
0x180017ac8  mov     rbp, [rsp+108h+arg_20]
0x180017ad0  mov     [rsp+108h+var_D8], rbp
0x180017ad5  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x180017ada  nop
0x180017adb  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x180017ae2  mov     [rcx], rax
0x180017ae5  add     rcx, 20h ; ' '
0x180017ae9  mov     rdx, r8
0x180017aec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180017af1  nop
0x180017af2  lea     rcx, [rsi+40h]
0x180017af6  mov     rdx, rbx
0x180017af9  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x180017afe  nop
0x180017aff  mov     qword ptr [rsi+58h], 0
0x180017b07  mov     dword ptr [rsi+60h], 0
0x180017b0e  lea     rcx, [rsi+68h]
0x180017b12  mov     rdx, rbp
0x180017b15  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x180017b1a  nop
0x180017b1b  mov     rax, [rdi]
0x180017b1e  lea     rcx, [rax+20h]
0x180017b22  neg     rax
0x180017b25  sbb     r8, r8
0x180017b28  and     r8, rcx; pcbe
0x180017b2b  mov     rdx, rsi; pv
0x180017b2e  lea     rcx, ?RunCallback@WorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180017b35  call    cs:__imp_CreateThreadpoolWork
0x180017b3b  mov     [rsi+58h], rax
0x180017b3f  test    rax, rax
0x180017b42  jnz     short loc_180017B8E
0x180017b44  lea     rdx, aCreatethreadpo_1; "CreateThreadpoolWork has failed"
0x180017b4b  lea     rcx, [rsp+108h+var_D0]
0x180017b50  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180017b55  mov     rbx, rax
0x180017b58  call    cs:__imp_GetLastError
0x180017b5e  mov     [rsp+108h+var_E8], eax
0x180017b62  mov     [rsp+108h+var_E4], 0
0x180017b6a  mov     r8, rbx
0x180017b6d  lea     rdx, [rsp+108h+var_E8]
0x180017b72  lea     rcx, [rsp+108h+pExceptionObject]
0x180017b77  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017b7c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017b83  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180017b88  call    _CxxThrowException_0
0x180017b8e  mov     rcx, rbp; this
0x180017b91  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x180017b96  mov     rax, rsi
0x180017b99  mov     rcx, [rsp+108h+var_38]
0x180017ba1  xor     rcx, rsp; StackCookie
0x180017ba4  call    __security_check_cookie
0x180017ba9  add     rsp, 0E8h
0x180017bb0  pop     rdi
0x180017bb1  pop     rsi
0x180017bb2  pop     rbp
0x180017bb3  pop     rbx
0x180017bb4  retn
```
