# CompositionIslandBridge::CreateInputSink(void)

- ea: `0x1800518cc`
- end: `0x180051a99`
- name: `?CreateInputSink@CompositionIslandBridge@@AEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(CompositionIslandBridge *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004fe94`
- `0x1800500bc`

## callees

- `0x18002eaa0`
- `0x180050360`
- `0x1800517f0`
- `0x1800518cc`
- `0x180061b1c`
- `0x180096c94`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1800519be`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1800519be`
- `ext-ms-win-rtcore-minuser-input-l1-1-1!GetRoutingInfoForWindowHandle` at `0x18005192d`
- `ext-ms-win-rtcore-minuser-input-l1-1-1!GetRoutingInfoForWindowHandle` at `0x18005192d`

## string_xrefs

- `0x180051a1e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180051a55`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`

## pseudocode

```c
__int64 __fastcall CompositionIslandBridge::CreateInputSink(CompositionIslandBridge *this)
{
  unsigned int v2; // edi
  int v3; // eax
  int CompositionInputSink; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  int v7; // eax
  int v8; // eax
  int v10[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v11; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  _DWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v17; // [rsp+98h] [rbp-68h]
  __int128 v18; // [rsp+A8h] [rbp-58h]
  __int128 v19; // [rsp+B8h] [rbp-48h]
  __int64 v20; // [rsp+C8h] [rbp-38h]
  __int128 v21; // [rsp+D0h] [rbp-30h]
  __int128 v22; // [rsp+E0h] [rbp-20h]
  __int128 v23; // [rsp+F0h] [rbp-10h]
  __int64 v24; // [rsp+100h] [rbp+0h]
  __int128 v25; // [rsp+108h] [rbp+8h]
  __int128 v26; // [rsp+118h] [rbp+18h]
  __int128 v27; // [rsp+128h] [rbp+28h]
  __int64 v28; // [rsp+138h] [rbp+38h]
  __int128 v29; // [rsp+140h] [rbp+40h]
  __int128 v30; // [rsp+150h] [rbp+50h]
  __int128 v31; // [rsp+160h] [rbp+60h]
  __int64 v32; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)v10 = 0;
  v11 = 0;
  v13 = 0;
  v2 = 2;
  v12 = 0;
  if ( (unsigned __int8)IsGetRoutingInfoForWindowHandlePresent()
    && (unsigned int)GetRoutingInfoForWindowHandle(*(_QWORD *)this, &v11) )
  {
    v2 = 3;
  }
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = *(_QWORD *)this;
  v3 = *((_DWORD *)this + 4);
  hstringHeader.Reserved.Reserved1 = (PVOID)v2;
  v16[0] = 232;
  v16[1] = v3;
  v29 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
  v25 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
  v21 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
  v17 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
  v30 = v11;
  v31 = v12;
  v32 = v13;
  v26 = v11;
  v27 = v12;
  v28 = v13;
  v22 = v11;
  v23 = v12;
  v24 = v13;
  v18 = v11;
  v19 = v12;
  v20 = v13;
  CompositionInputSink = NtCreateCompositionInputSink(v16, v10);
  if ( CompositionInputSink < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      v5,
      v6,
      (const char *)(unsigned int)CompositionInputSink,
      v10[0]);
  if ( !*((_QWORD *)this + 14) )
  {
    v15 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.Core.InternalCoordinateConversionStatics",
      0x34u,
      0x33u);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>(
           v15,
           (char *)this + 112);
    if ( v7 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v7,
        v10[0]);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 14) + 56LL))(
         *((_QWORD *)this + 14),
         *((unsigned int *)this + 4),
         *(_QWORD *)v10);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v8,
      v10[0]);
  *((_QWORD *)this + 1) = *(_QWORD *)v10;
  return 0;
}

```

## disassembly

```asm
0x1800518cc  mov     [rsp-8+arg_8], rbx
0x1800518d1  mov     [rsp-8+arg_10], rdi
0x1800518d6  push    rbp
0x1800518d7  lea     rbp, [rsp-90h]
0x1800518df  sub     rsp, 190h
0x1800518e6  mov     rax, cs:__security_cookie
0x1800518ed  xor     rax, rsp
0x1800518f0  mov     [rbp+90h+var_10], rax
0x1800518f7  xorps   xmm0, xmm0
0x1800518fa  mov     qword ptr [rsp+190h+var_170], 0; int
0x180051903  xor     eax, eax
0x180051905  mov     rbx, rcx
0x180051908  movups  [rsp+190h+var_168], xmm0
0x18005190d  mov     [rsp+190h+var_148], rax
0x180051912  mov     edi, 2
0x180051917  movups  [rsp+190h+var_158], xmm0
0x18005191c  call    IsGetRoutingInfoForWindowHandlePresent
0x180051921  test    al, al
0x180051923  jz      short loc_18005193B
0x180051925  mov     rcx, [rbx]
0x180051928  lea     rdx, [rsp+190h+var_168]
0x18005192d  call    cs:__imp_GetRoutingInfoForWindowHandle
0x180051933  test    eax, eax
0x180051935  lea     ecx, [rdi+1]
0x180051938  cmovnz  edi, ecx
0x18005193b  movups  xmm1, [rsp+190h+var_168]
0x180051940  mov     rax, [rbx]
0x180051943  lea     rdx, [rsp+190h+var_170]
0x180051948  movups  xmm2, [rsp+190h+var_158]
0x18005194d  lea     rcx, [rbp+90h+var_100]
0x180051951  mov     qword ptr [rsp+190h+hstringHeader.Reserved+8], rax
0x180051956  movsd   xmm3, [rsp+190h+var_148]
0x18005195c  mov     eax, [rbx+10h]
0x18005195f  mov     dword ptr [rsp+190h+hstringHeader.Reserved+4], 0
0x180051967  mov     dword ptr [rsp+190h+hstringHeader.Reserved], edi
0x18005196b  movups  xmm0, xmmword ptr [rsp+190h+hstringHeader.Reserved]
0x180051970  mov     [rbp+90h+var_100], 0E8h
0x180051977  mov     [rbp+90h+var_FC], eax
0x18005197a  movaps  [rbp+90h+var_50], xmm0
0x18005197e  movups  [rbp+90h+var_88], xmm0
0x180051982  movaps  [rbp+90h+var_C0], xmm0
0x180051986  movups  [rbp+90h+var_F8], xmm0
0x18005198a  movaps  [rbp+90h+var_40], xmm1
0x18005198e  movaps  [rbp+90h+var_30], xmm2
0x180051992  movsd   [rbp+90h+var_20], xmm3
0x180051997  movups  [rbp+90h+var_78], xmm1
0x18005199b  movups  [rbp+90h+var_68], xmm2
0x18005199f  movsd   [rbp+90h+var_58], xmm3
0x1800519a4  movaps  [rbp+90h+var_B0], xmm1
0x1800519a8  movaps  [rbp+90h+var_A0], xmm2
0x1800519ac  movsd   [rbp+90h+var_90], xmm3
0x1800519b1  movups  [rbp+90h+var_E8], xmm1
0x1800519b5  movups  [rbp+90h+var_D8], xmm2
0x1800519b9  movsd   [rbp+90h+var_C8], xmm3
0x1800519be  call    cs:__imp_NtCreateCompositionInputSink
0x1800519c4  test    eax, eax
0x1800519c6  jns     short loc_1800519D8
0x1800519c8  mov     rcx, [rbp+98h]; this
0x1800519cf  mov     r9d, eax; char *
0x1800519d2  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x1800519d8  lea     rdi, [rbx+70h]
0x1800519dc  cmp     qword ptr [rdi], 0
0x1800519e0  jnz     short loc_180051A33
0x1800519e2  mov     r9d, 33h ; '3'; unsigned int
0x1800519e8  mov     [rsp+190h+var_128], 0
0x1800519f1  lea     rdx, ?RuntimeClass_Windows_UI_Core_InternalCoordinateConversionStatics@@3QBGB; "Windows.UI.Core.InternalCoordinateConve"...
0x1800519f8  lea     rcx, [rsp+190h+hstringHeader]; hstringHeader
0x1800519fd  lea     r8d, [r9+1]; unsigned int
0x180051a01  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180051a06  mov     rcx, [rsp+190h+var_128]
0x180051a0b  mov     rdx, rdi
0x180051a0e  call    ??$GetActivationFactory@V?$ComPtr@UIInternalCoordinateConversionStatics@Core@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInternalCoordinateConversionStatics@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>)
0x180051a13  test    eax, eax
0x180051a15  jns     short loc_180051A33
0x180051a17  mov     rcx, [rbp+98h]; this
0x180051a1e  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180051a25  mov     r9d, eax; char *
0x180051a28  mov     edx, 17Ah; void *
0x180051a2d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180051a33  mov     rcx, [rdi]
0x180051a36  mov     r8, qword ptr [rsp+190h+var_170]
0x180051a3b  mov     edx, [rbx+10h]
0x180051a3e  mov     rax, [rcx]
0x180051a41  mov     rax, [rax+38h]
0x180051a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a4a  test    eax, eax
0x180051a4c  jns     short loc_180051A6A
0x180051a4e  mov     rcx, [rbp+98h]; this
0x180051a55  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180051a5c  mov     r9d, eax; char *
0x180051a5f  mov     edx, 17Eh; void *
0x180051a64  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180051a6a  mov     rax, qword ptr [rsp+190h+var_170]
0x180051a6f  mov     [rbx+8], rax
0x180051a73  xor     eax, eax
0x180051a75  mov     rcx, [rbp+90h+var_10]
0x180051a7c  xor     rcx, rsp; StackCookie
0x180051a7f  call    __security_check_cookie
0x180051a84  lea     r11, [rsp+190h+var_s0]
0x180051a8c  mov     rbx, [r11+18h]
0x180051a90  mov     rdi, [r11+20h]
0x180051a94  mov     rsp, r11
0x180051a97  pop     rbp
0x180051a98  retn
```
