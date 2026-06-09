# XamlUI::PreTranslateMessage(tagMSG const *)

- ea: `0x1400250f4`
- end: `0x14002517a`
- name: `?PreTranslateMessage@XamlUI@@QEAA_NPEBUtagMSG@@@Z`
- size: `134`
- prototype: `bool(XamlUI *__hidden this, const struct tagMSG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140022098`

## callees

- `0x140022de8`
- `0x1400236e4`
- `0x1400250f4`
- `0x1400258a8`
- `0x140029010`

## string_xrefs

- `0x140025140`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall XamlUI::PreTranslateMessage(XamlUI *this, const struct tagMSG *a2)
{
  __int64 v3; // rdi
  int v4; // eax
  const char *v5; // r9
  bool v6; // bl
  bool result; // al
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  try
  {
    winrt::impl::as<IDesktopWindowXamlSourceNative2,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>();
    v3 = v11;
    v4 = (*(__int64 (__fastcall **)(__int64, const struct tagMSG *, int *))(*(_QWORD *)v11 + 40LL))(v11, a2, &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
        (const char *)(unsigned int)v4,
        v8);
    v6 = v10 != 0;
    if ( v3 )
      winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v11);
    result = v6;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x14D,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400250f4  mov     [rsp+arg_8], rbx
0x1400250f9  push    rdi; int
0x1400250fa  sub     rsp, 20h
0x1400250fe  mov     rbx, rdx
0x140025101  mov     [rsp+28h+arg_0], 0
0x140025109  mov     rdx, [rcx+20h]
0x14002510d  lea     rcx, [rsp+28h+arg_10]
0x140025112  call    ??$as@UIDesktopWindowXamlSourceNative2@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UIDesktopWindowXamlSourceNative2@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<IDesktopWindowXamlSourceNative2,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x140025117  nop
0x140025118  mov     rdi, [rsp+28h+arg_10]
0x14002511d  mov     rax, [rdi]
0x140025120  lea     r8, [rsp+28h+arg_0]
0x140025125  mov     rdx, rbx
0x140025128  mov     rcx, rdi
0x14002512b  mov     rax, [rax+28h]
0x14002512f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025134  mov     rcx, [rsp+28h]; this
0x140025139  test    eax, eax
0x14002513b  jns     short loc_140025151
0x14002513d  mov     r9d, eax; char *
0x140025140  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140025147  mov     edx, 147h; void *
0x14002514c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140025151  cmp     [rsp+28h+arg_0], 0
0x140025156  setnz   bl
0x140025159  test    rdi, rdi
0x14002515c  jz      short loc_140025168
0x14002515e  lea     rcx, [rsp+28h+arg_10]
0x140025163  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x140025168  mov     al, bl
0x14002516a  jmp     short loc_14002516E
0x14002516c  xor     al, al
0x14002516e  mov     rbx, [rsp+28h+arg_8]
0x140025173  add     rsp, 20h
0x140025177  pop     rdi
0x140025178  retn
```
