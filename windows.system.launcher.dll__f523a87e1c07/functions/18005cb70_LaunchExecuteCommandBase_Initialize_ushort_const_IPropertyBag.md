# LaunchExecuteCommandBase::Initialize(ushort const *,IPropertyBag *)

- ea: `0x18005cb70`
- end: `0x18005cdbe`
- name: `?Initialize@LaunchExecuteCommandBase@@UEAAJPEBGPEAUIPropertyBag@@@Z`
- size: `590`
- prototype: `int(LaunchExecuteCommandBase *__hidden this, const unsigned __int16 *, struct IPropertyBag *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f194`
- `0x1800329a0`
- `0x18005cb70`
- `0x18005ce14`
- `0x18005cef8`
- `0x18008a030`
- `0x1800a1578`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005cc7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ccb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ccef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005cc7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ccb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ccef`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18005cd43`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18005cd43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cc5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cc9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ccd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cc5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cc9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ccd1`

## string_xrefs

- `0x18005cce2`: `Windows.AppUriHandler`
- `0x18005cc6f`: `Windows.Protocol`
- `0x18005cc41`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005cd1b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005cd58`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005cd87`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall LaunchExecuteCommandBase::Initialize(
        LaunchExecuteCommandBase *this,
        const unsigned __int16 *a2,
        struct IPropertyBag *a3)
{
  HSTRING *v5; // r14
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  int v9; // eax
  HRESULT v10; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-98h]
  int bIgnoreCasea; // [rsp+20h] [rbp-98h]
  DWORD value; // [rsp+30h] [rbp-88h] BYREF
  char v15; // [rsp+35h] [rbp-83h]
  struct IPropertyBag *v16; // [rsp+38h] [rbp-80h] BYREF
  const WCHAR *v17; // [rsp+40h] [rbp-78h] BYREF
  const unsigned __int16 *v18; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v19[4]; // [rsp+50h] [rbp-68h] BYREF
  int v20[2]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v18 = a2;
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      MICROSOFT_TWINUI_PUBLISHER_Context,
      AssociationLaunch_ServerInitialization_Start,
      a3,
      1,
      v20);
  v15 = 1;
  (*(void (__fastcall **)(char *, struct IPropertyBag *))(*((_QWORD *)this - 7) + 8LL))((char *)this - 56, a3);
  *(_QWORD *)v20 = 100;
  v17 = L"ContractId";
  v16 = a3;
  v19[0] = &v16;
  v19[1] = &v17;
  v19[2] = v20;
  v5 = (HSTRING *)((char *)this + 32);
  v19[3] = (char *)this + 32;
  if ( (int)lambda_93c3a0bd53f49555b988972088564648_::operator()(v19) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  StringRawBuffer = WindowsGetStringRawBuffer(*v5, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.Protocol", -1, 1) == 2 )
  {
    *((_DWORD *)this + 12) = 1;
  }
  else
  {
    v7 = WindowsGetStringRawBuffer(*v5, 0);
    if ( CompareStringOrdinal(v7, -1, L"Windows.File", -1, 1) == 2 )
    {
      *((_DWORD *)this + 12) = 0;
    }
    else
    {
      v8 = WindowsGetStringRawBuffer(*v5, 0);
      if ( CompareStringOrdinal(v8, -1, L"Windows.AppUriHandler", -1, 1) != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
          (const char *)0x80070057LL,
          bIgnoreCasea);
      *((_DWORD *)this + 12) = 2;
    }
  }
  v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 40, &v18);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCasea);
  value = 0;
  v10 = PSPropertyBag_ReadDWORD(a3, L"DesiredInitialViewState", &value);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCasea);
  *((_DWORD *)this + 13) = value;
  lambda_88bfe2589ab782f36bfc6d39d300d58e_::operator()(retaddr);
  return 0;
}

```

## disassembly

```asm
0x18005cb70  push    rbx
0x18005cb72  push    rsi
0x18005cb73  push    r12
0x18005cb75  push    r14
0x18005cb77  push    r15
0x18005cb79  sub     rsp, 90h
0x18005cb80  mov     rax, cs:__security_cookie
0x18005cb87  xor     rax, rsp
0x18005cb8a  mov     [rsp+0B8h+var_38], rax
0x18005cb92  mov     rsi, r8
0x18005cb95  mov     rbx, rcx
0x18005cb98  mov     [rsp+0B8h+var_70], rdx
0x18005cb9d  test    cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18005cba4  jz      short loc_18005CBC9
0x18005cba6  lea     rax, [rsp+0B8h+var_48]
0x18005cbab  mov     qword ptr [rsp+0B8h+bIgnoreCase], rax; int
0x18005cbb0  mov     r9d, 1
0x18005cbb6  lea     rdx, AssociationLaunch_ServerInitialization_Start
0x18005cbbd  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18005cbc4  call    McGenEventWrite_EventWriteTransfer
0x18005cbc9  mov     [rsp+0B8h+var_83], 1
0x18005cbce  lea     rcx, [rbx-38h]
0x18005cbd2  mov     rax, [rcx]
0x18005cbd5  mov     rdx, rsi
0x18005cbd8  mov     rax, [rax+8]
0x18005cbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbe1  mov     qword ptr [rsp+0B8h+var_48], 64h ; 'd'
0x18005cbea  lea     rax, aContractid; "ContractId"
0x18005cbf1  mov     [rsp+0B8h+var_78], rax
0x18005cbf6  mov     [rsp+0B8h+var_80], rsi
0x18005cbfb  lea     rax, [rsp+0B8h+var_80]
0x18005cc00  mov     [rsp+0B8h+var_68], rax
0x18005cc05  lea     rax, [rsp+0B8h+var_78]
0x18005cc0a  mov     [rsp+0B8h+var_60], rax
0x18005cc0f  lea     rax, [rsp+0B8h+var_48]
0x18005cc14  mov     [rsp+0B8h+var_58], rax
0x18005cc19  lea     r14, [rbx+20h]
0x18005cc1d  mov     [rsp+0B8h+var_50], r14
0x18005cc22  mov     r15, [rsp+0B8h]
0x18005cc2a  lea     rcx, [rsp+0B8h+var_68]
0x18005cc2f  call    _lambda_93c3a0bd53f49555b988972088564648___operator__
0x18005cc34  shr     eax, 1Fh
0x18005cc37  xor     al, 1
0x18005cc39  jnz     short loc_18005CC55
0x18005cc3b  mov     r9d, 80070057h; char *
0x18005cc41  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005cc48  mov     edx, 67h ; 'g'; void *
0x18005cc4d  mov     rcx, r15; this
0x18005cc50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005cc55  xor     edx, edx; length
0x18005cc57  mov     rcx, [r14]; string
0x18005cc5a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005cc60  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x18005cc68  or      r12d, 0FFFFFFFFh
0x18005cc6c  mov     r9d, r12d; cchCount2
0x18005cc6f  lea     r8, aWindowsProtoco; "Windows.Protocol"
0x18005cc76  mov     edx, r12d; cchCount1
0x18005cc79  mov     rcx, rax; lpString1
0x18005cc7c  call    cs:__imp_CompareStringOrdinal
0x18005cc82  lea     r15d, [r12+3]
0x18005cc87  cmp     eax, r15d
0x18005cc8a  jnz     short loc_18005CC95
0x18005cc8c  mov     dword ptr [rbx+30h], 1
0x18005cc93  jmp     short loc_18005CCFE
0x18005cc95  xor     edx, edx; length
0x18005cc97  mov     rcx, [r14]; string
0x18005cc9a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005cca0  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x18005cca8  mov     r9d, r12d; cchCount2
0x18005ccab  lea     r8, aWindowsFile; "Windows.File"
0x18005ccb2  mov     edx, r12d; cchCount1
0x18005ccb5  mov     rcx, rax; lpString1
0x18005ccb8  call    cs:__imp_CompareStringOrdinal
0x18005ccbe  cmp     eax, r15d
0x18005ccc1  jnz     short loc_18005CCCC
0x18005ccc3  mov     dword ptr [rbx+30h], 0
0x18005ccca  jmp     short loc_18005CCFE
0x18005cccc  xor     edx, edx; length
0x18005ccce  mov     rcx, [r14]; string
0x18005ccd1  call    cs:__imp_WindowsGetStringRawBuffer
0x18005ccd7  mov     [rsp+0B8h+bIgnoreCase], 1; int
0x18005ccdf  mov     r9d, r12d; cchCount2
0x18005cce2  lea     r8, aWindowsAppurih; "Windows.AppUriHandler"
0x18005cce9  mov     edx, r12d; cchCount1
0x18005ccec  mov     rcx, rax; lpString1
0x18005ccef  call    cs:__imp_CompareStringOrdinal
0x18005ccf5  cmp     eax, r15d
0x18005ccf8  jnz     short loc_18005CD79
0x18005ccfa  mov     [rbx+30h], r15d
0x18005ccfe  lea     rcx, [rbx+28h]
0x18005cd02  lea     rdx, [rsp+0B8h+var_70]
0x18005cd07  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005cd0c  mov     rcx, [rsp+0B8h]; this
0x18005cd14  test    eax, eax
0x18005cd16  jns     short loc_18005CD2C
0x18005cd18  mov     r9d, eax; char *
0x18005cd1b  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005cd22  mov     edx, 7Bh ; '{'; void *
0x18005cd27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005cd2c  mov     [rsp+0B8h+value], 0
0x18005cd34  lea     r8, [rsp+0B8h+value]; value
0x18005cd39  lea     rdx, propName; "DesiredInitialViewState"
0x18005cd40  mov     rcx, rsi; propBag
0x18005cd43  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18005cd49  mov     rcx, [rsp+0B8h]; this
0x18005cd51  test    eax, eax
0x18005cd53  jns     short loc_18005CD69
0x18005cd55  mov     r9d, eax; char *
0x18005cd58  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005cd5f  mov     edx, 80h; void *
0x18005cd64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005cd69  mov     eax, [rsp+0B8h+value]
0x18005cd6d  mov     [rbx+34h], eax
0x18005cd70  call    _lambda_88bfe2589ab782f36bfc6d39d300d58e___operator__
0x18005cd75  xor     eax, eax
0x18005cd77  jmp     short loc_18005CD9D
0x18005cd79  mov     rcx, [rsp+0B8h]; this
0x18005cd81  mov     r9d, 80070057h; char *
0x18005cd87  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005cd8e  mov     edx, 78h ; 'x'; void *
0x18005cd93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005cd99  mov     eax, [rsp+0B8h+value]
0x18005cd9d  mov     rcx, [rsp+0B8h+var_38]
0x18005cda5  xor     rcx, rsp; StackCookie
0x18005cda8  call    __security_check_cookie
0x18005cdad  add     rsp, 90h
0x18005cdb4  pop     r15
0x18005cdb6  pop     r14
0x18005cdb8  pop     r12
0x18005cdba  pop     rsi
0x18005cdbb  pop     rbx
0x18005cdbc  retn
```
