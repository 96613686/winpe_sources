# _lambda_7b4fabe6bb32ef3f000e12ab001b652f_::operator()

- ea: `0x180025f2c`
- end: `0x180026062`
- name: `_lambda_7b4fabe6bb32ef3f000e12ab001b652f_::operator()`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026600`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x18001bdec`
- `0x18001ff00`
- `0x180025f2c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025f82`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025fbc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025fbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_7b4fabe6bb32ef3f000e12ab001b652f_::operator()(__int64 *a1)
{
  __int64 v2; // rcx
  PVOID Reserved1; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // r10
  int v8; // [rsp+20h] [rbp-60h]
  _QWORD v9[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v9[0] = *(_QWORD *)(*a1 + 72);
  Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::InternalAddRef(v9);
  v2 = v9[0];
  if ( !v9[0] )
  {
    if ( WindowsCreateStringReference(
           L"Windows.ApplicationModel.Activation.Private.ApplicationActivation",
           0x41u,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    Reserved1 = hstringHeader.Reserved.Reserved1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
    ActivationFactory = RoGetActivationFactory(Reserved1, &GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f, v9);
    v5 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_7;
    v2 = v9[0];
  }
  v6 = *a1;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = ActivationType_ToastNotification;
  v8 = *(_DWORD *)(v6 + 80);
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *, _QWORD))(*(_QWORD *)v2 + 64LL))(
                        v2,
                        *(_QWORD *)a1[1],
                        &hstringHeader,
                        *(_QWORD *)a1[2]);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v5 = 0;
    goto LABEL_9;
  }
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x85,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v8);
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
  return v5;
}

```

## disassembly

```asm
0x180025f2c  mov     [rsp-8+arg_8], rbx
0x180025f31  mov     [rsp-8+arg_10], rdi
0x180025f36  push    rbp
0x180025f37  mov     rbp, rsp
0x180025f3a  sub     rsp, 80h
0x180025f41  mov     rax, cs:__security_cookie
0x180025f48  xor     rax, rsp
0x180025f4b  mov     [rbp+var_10], rax
0x180025f4f  mov     rdi, rcx
0x180025f52  mov     rax, [rcx]
0x180025f55  mov     rdx, [rax+48h]
0x180025f59  mov     [rbp+var_40], rdx
0x180025f5d  lea     rcx, [rbp+var_40]
0x180025f61  call    ?InternalAddRef@?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::InternalAddRef(void)
0x180025f66  nop
0x180025f67  mov     rcx, [rbp+var_40]
0x180025f6b  test    rcx, rcx
0x180025f6e  jnz     short loc_180025FCC
0x180025f70  lea     r9, [rbp+hstringHeader]; string
0x180025f74  lea     r8, [rbp+hstringHeader.Reserved+8]; hstringHeader
0x180025f78  lea     edx, [rcx+41h]; length
0x180025f7b  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Activation_Private_ApplicationActivation@@3QBGB; "Windows.ApplicationModel.Activation.Pri"...
0x180025f82  call    cs:__imp_WindowsCreateStringReference
0x180025f88  test    eax, eax
0x180025f8a  jns     short loc_180025FA1
0x180025f8c  xor     r9d, r9d; lpArguments
0x180025f8f  xor     r8d, r8d; nNumberOfArguments
0x180025f92  lea     edx, [r9+1]; dwExceptionFlags
0x180025f96  mov     ecx, 0C000000Dh; dwExceptionCode
0x180025f9b  call    cs:__imp_RaiseException
0x180025fa1  mov     rbx, qword ptr [rbp+hstringHeader.Reserved]
0x180025fa5  lea     rcx, [rbp+var_40]
0x180025fa9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025fae  lea     r8, [rbp+var_40]
0x180025fb2  lea     rdx, _GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f
0x180025fb9  mov     rcx, rbx
0x180025fbc  call    cs:__imp_RoGetActivationFactory
0x180025fc2  mov     ebx, eax
0x180025fc4  test    eax, eax
0x180025fc6  js      short loc_18002601A
0x180025fc8  mov     rcx, [rbp+var_40]
0x180025fcc  mov     r10, [rdi]
0x180025fcf  movups  xmm0, cs:ActivationType_ToastNotification
0x180025fd6  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180025fdb  mov     rax, [rcx]
0x180025fde  mov     r9, [rdi+10h]
0x180025fe2  mov     rdx, [rdi+8]
0x180025fe6  mov     r8, [r10+58h]
0x180025fea  mov     [rsp+80h+var_50], r8
0x180025fef  mov     r8, [r10+60h]
0x180025ff3  mov     [rsp+80h+var_58], r8
0x180025ff8  mov     r8d, [r10+50h]
0x180025ffc  mov     [rsp+80h+var_60], r8d; int
0x180026001  mov     r9, [r9]
0x180026004  lea     r8, [rbp+hstringHeader]
0x180026008  mov     rdx, [rdx]
0x18002600b  mov     rax, [rax+40h]
0x18002600f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026014  mov     ebx, eax
0x180026016  test    eax, eax
0x180026018  jns     short loc_180026034
0x18002601a  mov     rcx, [rbp+8]; this
0x18002601e  mov     r9d, eax; char *
0x180026021  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180026028  mov     edx, 85h; void *
0x18002602d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026032  jmp     short loc_180026036
0x180026034  xor     ebx, ebx
0x180026036  lea     rcx, [rbp+var_40]
0x18002603a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002603f  mov     eax, ebx
0x180026041  mov     rcx, [rbp+var_10]
0x180026045  xor     rcx, rsp; StackCookie
0x180026048  call    __security_check_cookie
0x18002604d  lea     r11, [rsp+80h+var_s0]
0x180026055  mov     rbx, [r11+18h]
0x180026059  mov     rdi, [r11+20h]
0x18002605d  mov     rsp, r11
0x180026060  pop     rbp
0x180026061  retn
```
