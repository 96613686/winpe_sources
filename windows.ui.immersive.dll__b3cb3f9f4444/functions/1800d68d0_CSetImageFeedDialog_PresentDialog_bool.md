# CSetImageFeedDialog::_PresentDialog(bool *)

- ea: `0x1800d68d0`
- end: `0x1800d6a88`
- name: `?_PresentDialog@CSetImageFeedDialog@@AEAAJPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800d4a5c`

## callees

- `0x1800343ec`
- `0x18003729c`
- `0x180050ae4`
- `0x180054130`
- `0x1800d596c`
- `0x1800d68d0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d693f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d693f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d6920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d6920`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d696a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d696a`
- `DUI70!UnInitProcessPriv` at `0x1800d6a4e`
- `DUI70!UnInitProcessPriv` at `0x1800d6a4e`
- `DUI70!UnInitThread` at `0x1800d6a3b`
- `DUI70!UnInitThread` at `0x1800d6a3b`
- `DUI70!StartMessagePump` at `0x1800d6a25`
- `DUI70!StartMessagePump` at `0x1800d6a25`
- `DUI70!InitThread` at `0x1800d69f7`
- `DUI70!InitThread` at `0x1800d69f7`
- `DUI70!InitProcessPriv` at `0x1800d69c5`
- `DUI70!InitProcessPriv` at `0x1800d69c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSetImageFeedDialog::_PresentDialog(CSetImageFeedDialog *this, bool *a2)
{
  HSTRING v4; // rbx
  __int64 v5; // r8
  unsigned int v6; // ebx
  int inited; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-58h]
  _BYTE v13[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
    *a2 = 0;
  v13[0] = 0;
  v14 = 0;
  if ( WindowsCreateStringReference(L"Windows.Graphics.Holographic.HolographicSpace", 0x2Du, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  if ( (int)RoGetActivationFactory(v4, &GUID_0e777088_75fc_48af_8758_0652f6f07c59, &v14) >= 0
    && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 56LL))(v14, v13) >= 0
    && v13[0] )
  {
    v6 = CSetImageFeedDialog::CreateAndShowMessageDialog(this, a2);
    goto LABEL_19;
  }
  LOBYTE(v12) = 1;
  LOBYTE(v5) = 1;
  inited = InitProcessPriv(14, &_ImageBase, v5);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 293;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
      (const char *)(unsigned int)inited,
      v12);
    goto LABEL_19;
  }
  inited = InitThread(65538);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 294;
    goto LABEL_11;
  }
  inited = CSetImageFeedDialog::CreateAndShow(this);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 295;
    goto LABEL_11;
  }
  StartMessagePump(v9);
  if ( a2 )
    *a2 = *((_BYTE *)this + 40);
  UnInitThread(v10);
  UnInitProcessPriv(&_ImageBase);
  v6 = 0;
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return v6;
}

```

## disassembly

```asm
0x1800d68d0  mov     [rsp+arg_10], rbx
0x1800d68d5  mov     [rsp+arg_18], rsi
0x1800d68da  push    rdi
0x1800d68db  sub     rsp, 70h
0x1800d68df  mov     rax, cs:__security_cookie
0x1800d68e6  xor     rax, rsp
0x1800d68e9  mov     [rsp+78h+var_18], rax
0x1800d68ee  mov     rdi, rdx
0x1800d68f1  mov     rsi, rcx
0x1800d68f4  test    rdx, rdx
0x1800d68f7  jz      short loc_1800D68FC
0x1800d68f9  mov     byte ptr [rdx], 0
0x1800d68fc  mov     [rsp+78h+var_48], 0
0x1800d6901  mov     [rsp+78h+var_40], 0
0x1800d690a  lea     r9, [rsp+78h+string]; string
0x1800d690f  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1800d6914  mov     edx, 2Dh ; '-'; length
0x1800d6919  lea     rcx, ?RuntimeClass_Windows_Graphics_Holographic_HolographicSpace@@3QBGB; "Windows.Graphics.Holographic.Holographi"...
0x1800d6920  call    cs:__imp_WindowsCreateStringReference
0x1800d6927  nop     dword ptr [rax+rax+00h]
0x1800d692c  test    eax, eax
0x1800d692e  jns     short loc_1800D694C
0x1800d6930  xor     r9d, r9d; lpArguments
0x1800d6933  xor     r8d, r8d; nNumberOfArguments
0x1800d6936  lea     edx, [r9+1]; dwExceptionFlags
0x1800d693a  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d693f  call    cs:__imp_RaiseException
0x1800d6946  nop     dword ptr [rax+rax+00h]
0x1800d694b  nop
0x1800d694c  mov     rbx, [rsp+78h+string]
0x1800d6951  lea     rcx, [rsp+78h+var_40]
0x1800d6956  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d695b  lea     r8, [rsp+78h+var_40]
0x1800d6960  lea     rdx, _GUID_0e777088_75fc_48af_8758_0652f6f07c59
0x1800d6967  mov     rcx, rbx
0x1800d696a  call    cs:__imp_RoGetActivationFactory
0x1800d6971  nop     dword ptr [rax+rax+00h]
0x1800d6976  nop
0x1800d6977  test    eax, eax
0x1800d6979  js      short loc_1800D69AE
0x1800d697b  mov     rcx, [rsp+78h+var_40]
0x1800d6980  mov     rax, [rcx]
0x1800d6983  lea     rdx, [rsp+78h+var_48]
0x1800d6988  mov     rax, [rax+38h]
0x1800d698c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6991  test    eax, eax
0x1800d6993  js      short loc_1800D69AE
0x1800d6995  cmp     [rsp+78h+var_48], 0
0x1800d699a  jz      short loc_1800D69AE
0x1800d699c  mov     rdx, rdi; bool *
0x1800d699f  mov     rcx, rsi; this
0x1800d69a2  call    ?CreateAndShowMessageDialog@CSetImageFeedDialog@@QEAAJPEA_N@Z; CSetImageFeedDialog::CreateAndShowMessageDialog(bool *)
0x1800d69a7  mov     ebx, eax
0x1800d69a9  jmp     loc_1800D6A5C
0x1800d69ae  mov     byte ptr [rsp+78h+var_58], 1; int
0x1800d69b3  mov     r9b, 1
0x1800d69b6  mov     r8b, r9b
0x1800d69b9  lea     rdx, __ImageBase
0x1800d69c0  mov     ecx, 0Eh
0x1800d69c5  call    cs:__imp_InitProcessPriv
0x1800d69cc  nop     dword ptr [rax+rax+00h]
0x1800d69d1  mov     ebx, eax
0x1800d69d3  test    eax, eax
0x1800d69d5  jns     short loc_1800D69F2
0x1800d69d7  mov     edx, 125h; void *
0x1800d69dc  mov     rcx, [rsp+78h]; this
0x1800d69e1  mov     r9d, eax; char *
0x1800d69e4  lea     r8, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x1800d69eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d69f0  jmp     short loc_1800D6A5C
0x1800d69f2  mov     ecx, 10002h
0x1800d69f7  call    cs:__imp_InitThread
0x1800d69fe  nop     dword ptr [rax+rax+00h]
0x1800d6a03  mov     ebx, eax
0x1800d6a05  test    eax, eax
0x1800d6a07  jns     short loc_1800D6A10
0x1800d6a09  mov     edx, 126h
0x1800d6a0e  jmp     short loc_1800D69DC
0x1800d6a10  mov     rcx, rsi; this
0x1800d6a13  call    ?CreateAndShow@CSetImageFeedDialog@@QEAAJXZ; CSetImageFeedDialog::CreateAndShow(void)
0x1800d6a18  mov     ebx, eax
0x1800d6a1a  test    eax, eax
0x1800d6a1c  jns     short loc_1800D6A25
0x1800d6a1e  mov     edx, 127h
0x1800d6a23  jmp     short loc_1800D69DC
0x1800d6a25  call    cs:__imp_StartMessagePump
0x1800d6a2c  nop     dword ptr [rax+rax+00h]
0x1800d6a31  test    rdi, rdi
0x1800d6a34  jz      short loc_1800D6A3B
0x1800d6a36  mov     al, [rsi+28h]
0x1800d6a39  mov     [rdi], al
0x1800d6a3b  call    cs:__imp_UnInitThread
0x1800d6a42  nop     dword ptr [rax+rax+00h]
0x1800d6a47  lea     rcx, __ImageBase
0x1800d6a4e  call    cs:__imp_UnInitProcessPriv
0x1800d6a55  nop     dword ptr [rax+rax+00h]
0x1800d6a5a  xor     ebx, ebx
0x1800d6a5c  lea     rcx, [rsp+78h+var_40]
0x1800d6a61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d6a66  mov     eax, ebx
0x1800d6a68  mov     rcx, [rsp+78h+var_18]
0x1800d6a6d  xor     rcx, rsp; StackCookie
0x1800d6a70  call    __security_check_cookie
0x1800d6a75  lea     r11, [rsp+78h+var_8]
0x1800d6a7a  mov     rbx, [r11+20h]
0x1800d6a7e  mov     rsi, [r11+28h]
0x1800d6a82  mov     rsp, r11
0x1800d6a85  pop     rdi
0x1800d6a86  retn
```
