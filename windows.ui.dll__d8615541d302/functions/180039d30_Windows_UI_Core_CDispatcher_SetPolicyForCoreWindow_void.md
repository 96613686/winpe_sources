# Windows::UI::Core::CDispatcher::SetPolicyForCoreWindow(void)

- ea: `0x180039d30`
- end: `0x180039ee9`
- name: `?SetPolicyForCoreWindow@CDispatcher@Core@UI@Windows@@QEAAXXZ`
- size: `441`
- prototype: `void __fastcall(Windows::UI::Core::CDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004d010`

## callees

- `0x1800038e0`
- `0x180039d30`
- `0x180050360`
- `0x180056d3c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039ee2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039d88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039d88`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039dae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039dae`

## string_xrefs

- `0x180039ec4`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::UI::Core::CDispatcher::SetPolicyForCoreWindow(Windows::UI::Core::CDispatcher *this)
{
  HRESULT v2; // eax
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, __int64 *); // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-58h]
  _BYTE v8[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v9; // [rsp+38h] [rbp-40h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  if ( *((_DWORD *)this + 56) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x712,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)0x8000FFFFLL,
      v7);
  *((_DWORD *)this + 56) = 1;
  v10 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    JUMPOUT(0x180039EE8LL);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v10);
  if ( (int)RoGetActivationFactory(string, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &v10) >= 0 )
  {
    v8[0] = 0;
    v9 = 0;
    v3 = v10;
    v4 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 96LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v9);
    if ( v4(v3, &v9) >= 0 && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 72LL))(v9, v8) >= 0 && v8[0] )
      *((_BYTE *)this + 212) = 1;
    v5 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
      this,
      *((_DWORD *)this + 30));
  }
  string = 0;
  v6 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x180039d30  push    rbp
0x180039d32  push    rbx
0x180039d33  push    rsi
0x180039d34  push    rdi
0x180039d35  mov     rbp, rsp
0x180039d38  sub     rsp, 78h
0x180039d3c  mov     rax, cs:__security_cookie
0x180039d43  xor     rax, rsp
0x180039d46  mov     [rbp+var_10], rax
0x180039d4a  mov     rsi, rcx
0x180039d4d  cmp     dword ptr [rcx+0E0h], 0
0x180039d54  jnz     loc_180039EBA
0x180039d5a  mov     dword ptr [rcx+0E0h], 1
0x180039d64  mov     [rbp+var_38], 0
0x180039d6c  mov     [rbp+string], 0
0x180039d74  lea     r9, [rbp+string]; string
0x180039d78  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180039d7c  mov     edx, 2Dh ; '-'; length
0x180039d81  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180039d88  call    cs:__imp_WindowsCreateStringReference
0x180039d8e  test    eax, eax
0x180039d90  js      loc_180039ED6
0x180039d96  lea     rcx, [rbp+var_38]
0x180039d9a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180039d9f  lea     r8, [rbp+var_38]
0x180039da3  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180039daa  mov     rcx, [rbp+string]
0x180039dae  call    cs:__imp_RoGetActivationFactory
0x180039db4  test    eax, eax
0x180039db6  js      short loc_180039E0D
0x180039db8  mov     [rbp+var_48], 0
0x180039dbc  mov     [rbp+var_40], 0
0x180039dc4  mov     rdi, [rbp+var_38]
0x180039dc8  mov     rax, [rdi]
0x180039dcb  mov     rbx, [rax+60h]
0x180039dcf  lea     rcx, [rbp+var_40]
0x180039dd3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180039dd8  lea     rdx, [rbp+var_40]
0x180039ddc  mov     rcx, rdi
0x180039ddf  mov     rax, rbx
0x180039de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039de7  test    eax, eax
0x180039de9  jns     loc_180039E88
0x180039def  mov     rcx, [rbp+var_40]
0x180039df3  test    rcx, rcx
0x180039df6  jz      short loc_180039E0D
0x180039df8  mov     [rbp+var_40], 0
0x180039e00  mov     rax, [rcx]
0x180039e03  mov     rax, [rax+10h]
0x180039e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e0c  nop
0x180039e0d  lea     rax, WPP_GLOBAL_Control
0x180039e14  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e1b  cmp     rcx, rax
0x180039e1e  jnz     short loc_180039E5B
0x180039e20  mov     [rbp+string], 0
0x180039e28  mov     rcx, [rbp+var_38]
0x180039e2c  test    rcx, rcx
0x180039e2f  jz      short loc_180039E46
0x180039e31  mov     [rbp+var_38], 0
0x180039e39  mov     rax, [rcx]
0x180039e3c  mov     rax, [rax+10h]
0x180039e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e45  nop
0x180039e46  mov     rcx, [rbp+var_10]
0x180039e4a  xor     rcx, rsp; StackCookie
0x180039e4d  call    __security_check_cookie
0x180039e52  add     rsp, 78h
0x180039e56  pop     rdi
0x180039e57  pop     rsi
0x180039e58  pop     rbx
0x180039e59  pop     rbp
0x180039e5a  retn
0x180039e5b  test    byte ptr [rcx+1Ch], 4
0x180039e5f  jz      short loc_180039E20
0x180039e61  cmp     byte ptr [rcx+19h], 4
0x180039e65  jb      short loc_180039E20
0x180039e67  mov     edx, 24h ; '$'
0x180039e6c  mov     eax, [rsi+78h]
0x180039e6f  mov     [rsp+78h+var_58], eax
0x180039e73  mov     r9, rsi
0x180039e76  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180039e7d  mov     rcx, [rcx+10h]
0x180039e81  call    WPP_SF_qD
0x180039e86  jmp     short loc_180039E20
0x180039e88  mov     rcx, [rbp+var_40]
0x180039e8c  mov     rax, [rcx]
0x180039e8f  lea     rdx, [rbp+var_48]
0x180039e93  mov     rax, [rax+48h]
0x180039e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e9c  test    eax, eax
0x180039e9e  js      loc_180039DEF
0x180039ea4  cmp     [rbp+var_48], 0
0x180039ea8  jz      loc_180039DEF
0x180039eae  mov     byte ptr [rsi+0D4h], 1
0x180039eb5  jmp     loc_180039DEF
0x180039eba  mov     rcx, [rbp+20h]; this
0x180039ebe  mov     r9d, 8000FFFFh; char *
0x180039ec4  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180039ecb  mov     edx, 712h; void *
0x180039ed0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180039ed6  xor     r9d, r9d; lpArguments
0x180039ed9  xor     r8d, r8d; nNumberOfArguments
0x180039edc  lea     edx, [r9+1]; dwExceptionFlags
0x180039ee0  mov     ecx, eax; dwExceptionCode
0x180039ee2  call    cs:__imp_RaiseException
```
