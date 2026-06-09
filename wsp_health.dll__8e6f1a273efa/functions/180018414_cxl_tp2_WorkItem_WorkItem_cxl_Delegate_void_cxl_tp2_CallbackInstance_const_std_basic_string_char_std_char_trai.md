# cxl::tp2::WorkItem::WorkItem(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,cxl::counted_ptr<cxl::tp2::ThreadPoolGroup> const &,cxl::Delegate<void (void)>)

- ea: `0x180018414`
- end: `0x18001853a`
- name: `??0WorkItem@tp2@cxl@@QEAA@AEBU?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU?$counted_ptr@VThreadPoolGroup@tp2@cxl@@@2@U?$Delegate@$$A6AXXZ@2@@Z`
- size: `294`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, cxl::detail::DelegateBase *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ad20`
- `0x18001dfe0`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cc98`
- `0x18000cd9c`
- `0x18000ce84`
- `0x180017d30`
- `0x180018414`
- `0x180018540`
- `0x180018948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800184ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800184ad`

## string_xrefs

- `0x1800184c2`: `CreateThreadpoolWork has failed`

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
0x180018414  push    rbx
0x180018416  push    rbp
0x180018417  push    rsi
0x180018418  push    rdi
0x180018419  sub     rsp, 0E8h
0x180018420  mov     rax, cs:__security_cookie
0x180018427  xor     rax, rsp
0x18001842a  mov     [rsp+108h+var_38], rax
0x180018432  mov     rdi, r9
0x180018435  mov     rbx, rdx
0x180018438  mov     rsi, rcx
0x18001843b  mov     [rsp+108h+var_E0], rcx
0x180018440  mov     rbp, [rsp+108h+arg_20]
0x180018448  mov     [rsp+108h+var_D8], rbp
0x18001844d  call    ??0WorkItemBase@tp2@cxl@@IEAA@XZ; cxl::tp2::WorkItemBase::WorkItemBase(void)
0x180018452  nop
0x180018453  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x18001845a  mov     [rcx], rax
0x18001845d  add     rcx, 20h ; ' '
0x180018461  mov     rdx, r8
0x180018464  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180018469  nop
0x18001846a  lea     rcx, [rsi+40h]
0x18001846e  mov     rdx, rbx
0x180018471  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x180018476  nop
0x180018477  mov     qword ptr [rsi+58h], 0
0x18001847f  mov     dword ptr [rsi+60h], 0
0x180018486  lea     rcx, [rsi+68h]
0x18001848a  mov     rdx, rbp
0x18001848d  call    ??0?$Delegate@$$A6AXVCallbackInstance@tp2@cxl@@@Z@cxl@@QEAA@AEBU01@@Z; cxl::Delegate<void (cxl::tp2::CallbackInstance)>::Delegate<void (cxl::tp2::CallbackInstance)>(cxl::Delegate<void (cxl::tp2::CallbackInstance)> const &)
0x180018492  nop
0x180018493  mov     rax, [rdi]
0x180018496  lea     rcx, [rax+20h]
0x18001849a  neg     rax
0x18001849d  sbb     r8, r8
0x1800184a0  and     r8, rcx; pcbe
0x1800184a3  mov     rdx, rsi; pv
0x1800184a6  lea     rcx, ?RunCallback@WorkItem@tp2@cxl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800184ad  call    cs:__imp_CreateThreadpoolWork
0x1800184b4  nop     dword ptr [rax+rax+00h]
0x1800184b9  mov     [rsi+58h], rax
0x1800184bd  test    rax, rax
0x1800184c0  jnz     short loc_180018512
0x1800184c2  lea     rdx, aCreatethreadpo_1; "CreateThreadpoolWork has failed"
0x1800184c9  lea     rcx, [rsp+108h+var_D0]
0x1800184ce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800184d3  mov     rbx, rax
0x1800184d6  call    cs:__imp_GetLastError
0x1800184dd  nop     dword ptr [rax+rax+00h]
0x1800184e2  mov     [rsp+108h+var_E8], eax
0x1800184e6  mov     [rsp+108h+var_E4], 0
0x1800184ee  mov     r8, rbx
0x1800184f1  lea     rdx, [rsp+108h+var_E8]
0x1800184f6  lea     rcx, [rsp+108h+pExceptionObject]
0x1800184fb  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018500  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018507  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001850c  call    _CxxThrowException_0
0x180018512  mov     rcx, rbp; this
0x180018515  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001851a  mov     rax, rsi
0x18001851d  mov     rcx, [rsp+108h+var_38]
0x180018525  xor     rcx, rsp; StackCookie
0x180018528  call    __security_check_cookie
0x18001852d  add     rsp, 0E8h
0x180018534  pop     rdi
0x180018535  pop     rsi
0x180018536  pop     rbp
0x180018537  pop     rbx
0x180018538  retn
```
