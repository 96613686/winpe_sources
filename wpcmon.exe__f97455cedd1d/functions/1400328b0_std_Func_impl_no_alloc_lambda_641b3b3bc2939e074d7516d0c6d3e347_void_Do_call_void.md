# std::_Func_impl_no_alloc<_lambda_641b3b3bc2939e074d7516d0c6d3e347_,void,>::_Do_call(void)

- ea: `0x1400328b0`
- end: `0x140032a8d`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_641b3b3bc2939e074d7516d0c6d3e347_@@X$$V@std@@EEAAXXZ`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005530`
- `0x14002f2e0`
- `0x14002f5b8`
- `0x140031ba0`
- `0x1400328b0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400328f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400328f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140032910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140032910`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Func_impl_no_alloc<_lambda_641b3b3bc2939e074d7516d0c6d3e347_,void,>::_Do_call(__int64 a1)
{
  __int64 v2; // rdi
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 result; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v2 = *(_QWORD *)(a1 + 8);
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.FamilySafety.AppTimeLimits", 0x2Bu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
LABEL_12:
    wil::details::in1diag3::_Throw_Hr(
      v7,
      (void *)0x145,
      (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v13);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_00e2fccb_d82d_4431_a38a_699cb3a49995, v2 + 16);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  v13 = 0;
  v8 = Microsoft::WRL::Details::MakeAndInitialize<wpc::AppTimeLimits::UI::AppTimeUsageEventHandler,wpc::AppTimeLimits::UI::AppTimeUsageEventHandler,std::shared_ptr<wpc::AppTimeLimits::UI::UICallbackImpl> &,Sid const &>(
         &v13,
         *(_QWORD **)(a1 + 8),
         *(_QWORD *)(a1 + 16));
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
      (const char *)(unsigned int)v8,
      v13);
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 16LL) + 48LL))(
         *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
         (v13 + 8) & -(__int64)(v13 != 0),
         *(_QWORD *)(a1 + 8) + 24LL);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
      (const char *)(unsigned int)v9,
      v13);
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 16LL) + 64LL))(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
          (v13 + 8) & -(__int64)(v13 != 0),
          *(_QWORD *)(a1 + 8) + 32LL);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
      (const char *)(unsigned int)v10,
      v13);
  result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 16LL) + 80LL))(
             *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
             (v13 + 8) & -(__int64)(v13 != 0),
             *(_QWORD *)(a1 + 8) + 40LL);
  if ( (int)result < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"pcshell\\shell\\wpc\\monitor\\apptimelimitsviewstatecontroller.cpp",
      (const char *)(unsigned int)result,
      v13);
  v12 = v13;
  if ( v13 )
  {
    v13 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return result;
}

```

## disassembly

```asm
0x1400328b0  mov     [rsp-8+arg_8], rbx
0x1400328b5  mov     [rsp-8+arg_10], rdi
0x1400328ba  push    rbp
0x1400328bb  mov     rbp, rsp
0x1400328be  sub     rsp, 50h
0x1400328c2  mov     rax, cs:__security_cookie
0x1400328c9  xor     rax, rsp
0x1400328cc  mov     [rbp+var_8], rax
0x1400328d0  mov     rbx, rcx
0x1400328d3  mov     rdi, [rcx+8]
0x1400328d7  mov     [rbp+string], 0
0x1400328df  lea     r9, [rbp+string]; string
0x1400328e3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400328e7  mov     edx, 2Bh ; '+'; length
0x1400328ec  lea     rcx, ?RuntimeClass_Windows_Internal_FamilySafety_AppTimeLimits@@3QBGB; "Windows.Internal.FamilySafety.AppTimeLi"...
0x1400328f3  call    cs:__imp_WindowsCreateStringReference
0x1400328f9  test    eax, eax
0x1400328fb  js      loc_140032A31
0x140032901  lea     r8, [rdi+10h]
0x140032905  lea     rdx, _GUID_00e2fccb_d82d_4431_a38a_699cb3a49995
0x14003290c  mov     rcx, [rbp+string]
0x140032910  call    cs:__imp_RoGetActivationFactory
0x140032916  mov     rcx, [rbp+8]
0x14003291a  test    eax, eax
0x14003291c  js      loc_140032A39
0x140032922  mov     [rbp+var_30], 0
0x14003292a  mov     r8, [rbx+10h]
0x14003292e  mov     rdx, [rbx+8]
0x140032932  lea     rcx, [rbp+var_30]
0x140032936  call    ??$MakeAndInitialize@VAppTimeUsageEventHandler@UI@AppTimeLimits@wpc@@V1234@AEAV?$shared_ptr@VUICallbackImpl@UI@AppTimeLimits@wpc@@@std@@AEBVSid@@@Details@WRL@Microsoft@@YAJPEAPEAVAppTimeUsageEventHandler@UI@AppTimeLimits@wpc@@AEAV?$shared_ptr@VUICallbackImpl@UI@AppTimeLimits@wpc@@@std@@AEBVSid@@@Z; Microsoft::WRL::Details::MakeAndInitialize<wpc::AppTimeLimits::UI::AppTimeUsageEventHandler,wpc::AppTimeLimits::UI::AppTimeUsageEventHandler,std::shared_ptr<wpc::AppTimeLimits::UI::UICallbackImpl> &,Sid const &>(wpc::AppTimeLimits::UI::AppTimeUsageEventHandler * *,std::shared_ptr<wpc::AppTimeLimits::UI::UICallbackImpl> &,Sid const &)
0x14003293b  mov     rcx, [rbp+8]; this
0x14003293f  test    eax, eax
0x140032941  js      loc_140032A4E
0x140032947  mov     r8, [rbx+8]
0x14003294b  mov     rcx, [r8+10h]
0x14003294f  mov     rdx, [rbp+var_30]
0x140032953  mov     r9, [rcx]
0x140032956  add     r8, 18h
0x14003295a  lea     rax, [rdx+8]
0x14003295e  neg     rdx
0x140032961  sbb     rdx, rdx
0x140032964  and     rdx, rax
0x140032967  mov     rax, [r9+30h]
0x14003296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032970  mov     rcx, [rbp+8]; this
0x140032974  test    eax, eax
0x140032976  js      loc_140032A63
0x14003297c  mov     r8, [rbx+8]
0x140032980  mov     rcx, [r8+10h]
0x140032984  mov     rdx, [rbp+var_30]
0x140032988  mov     r9, [rcx]
0x14003298b  add     r8, 20h ; ' '
0x14003298f  lea     rax, [rdx+8]
0x140032993  neg     rdx
0x140032996  sbb     rdx, rdx
0x140032999  and     rdx, rax
0x14003299c  mov     rax, [r9+40h]
0x1400329a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400329a5  mov     rcx, [rbp+8]; this
0x1400329a9  test    eax, eax
0x1400329ab  js      loc_140032A78
0x1400329b1  mov     r8, [rbx+8]
0x1400329b5  mov     rcx, [r8+10h]
0x1400329b9  mov     rdx, [rbp+var_30]
0x1400329bd  mov     r9, [rcx]
0x1400329c0  add     r8, 28h ; '('
0x1400329c4  lea     rax, [rdx+8]
0x1400329c8  neg     rdx
0x1400329cb  sbb     rdx, rdx
0x1400329ce  and     rdx, rax
0x1400329d1  mov     rax, [r9+50h]
0x1400329d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400329da  mov     rcx, [rbp+8]; this
0x1400329de  test    eax, eax
0x1400329e0  js      short loc_140032A1C
0x1400329e2  mov     rcx, [rbp+var_30]
0x1400329e6  test    rcx, rcx
0x1400329e9  jz      short loc_140032A00
0x1400329eb  mov     [rbp+var_30], 0
0x1400329f3  mov     rax, [rcx]
0x1400329f6  mov     rax, [rax+10h]
0x1400329fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400329ff  nop
0x140032a00  mov     rcx, [rbp+var_8]
0x140032a04  xor     rcx, rsp; StackCookie
0x140032a07  call    __security_check_cookie
0x140032a0c  mov     rbx, [rsp+50h+arg_8]
0x140032a11  mov     rdi, [rsp+50h+arg_10]
0x140032a16  add     rsp, 50h
0x140032a1a  pop     rbp
0x140032a1b  retn
0x140032a1c  mov     r9d, eax; char *
0x140032a1f  lea     r8, aPcshellShellWp_0; "pcshell\\shell\\wpc\\monitor\\apptimeli"...
0x140032a26  mov     edx, 14Ch; void *
0x140032a2b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140032a31  mov     ecx, eax; this
0x140032a33  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140032a38  nop
0x140032a39  mov     r9d, eax; char *
0x140032a3c  lea     r8, aPcshellShellWp_0; "pcshell\\shell\\wpc\\monitor\\apptimeli"...
0x140032a43  mov     edx, 145h; void *
0x140032a48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140032a4e  mov     r9d, eax; char *
0x140032a51  lea     r8, aPcshellShellWp_0; "pcshell\\shell\\wpc\\monitor\\apptimeli"...
0x140032a58  mov     edx, 148h; void *
0x140032a5d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140032a63  mov     r9d, eax; char *
0x140032a66  lea     r8, aPcshellShellWp_0; "pcshell\\shell\\wpc\\monitor\\apptimeli"...
0x140032a6d  mov     edx, 14Ah; void *
0x140032a72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140032a78  mov     r9d, eax; char *
0x140032a7b  lea     r8, aPcshellShellWp_0; "pcshell\\shell\\wpc\\monitor\\apptimeli"...
0x140032a82  mov     edx, 14Bh; void *
0x140032a87  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
