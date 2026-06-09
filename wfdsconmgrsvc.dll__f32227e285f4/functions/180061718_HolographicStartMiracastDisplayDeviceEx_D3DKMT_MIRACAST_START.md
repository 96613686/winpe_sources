# HolographicStartMiracastDisplayDeviceEx(_D3DKMT_MIRACAST_START *)

- ea: `0x180061718`
- end: `0x180061829`
- name: `?HolographicStartMiracastDisplayDeviceEx@@YA?AW4D3DKMT_MIRACAST_DEVICE_STATUS@@PEAU_D3DKMT_MIRACAST_START@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180061a80`

## callees

- `0x180002600`
- `0x180061584`
- `0x180061718`
- `0x180061938`
- `0x180061964`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061773`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800617fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800617fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006175e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006175e`

## pseudocode

```c
__int64 __fastcall HolographicStartMiracastDisplayDeviceEx(__int64 a1)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax
  const unsigned __int16 *v4; // rdx
  unsigned __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rax
  int v9; // [rsp+30h] [rbp-19h] BYREF
  HSTRING v10; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF

  v11[0] = 0;
  v2 = -2147483647;
  string = 0;
  v9 = -2147483647;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Holographic.Miracast.HolographicMiracastControl",
         0x40u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v10 = 0;
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(
              (__int64)string,
              (__int64)v11) < 0 )
    goto LABEL_10;
  v4 = (const unsigned __int16 *)(a1 + 4);
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  if ( v5 > 0xFFFFFFFF
    || (int)Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v10, v4, v5) < 0
    || (v6 = *(_QWORD *)(a1 + 528),
        v7 = *(_QWORD *)v11[0],
        *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)(a1 + 536),
        (*(int (__fastcall **)(_QWORD, HSTRING, __int64, HSTRING_HEADER *, int *))(v7 + 48))(
          v11[0],
          v10,
          v6,
          &hstringHeader,
          &v9) < 0) )
  {
LABEL_10:
    v9 = -2147483647;
  }
  else
  {
    v2 = v9;
  }
  WindowsDeleteString(v10);
  v10 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(v11);
  return v2;
}

```

## disassembly

```asm
0x180061718  push    rbp
0x18006171a  push    rbx
0x18006171b  push    rsi
0x18006171c  push    rdi
0x18006171d  lea     rbp, [rsp-3Fh]
0x180061722  sub     rsp, 88h
0x180061729  mov     rax, cs:__security_cookie
0x180061730  xor     rax, rsp
0x180061733  mov     [rbp+57h+var_30], rax
0x180061737  xor     esi, esi
0x180061739  lea     r9, [rbp+57h+string]; string
0x18006173d  mov     rdi, rcx
0x180061740  mov     [rbp+57h+var_60], rsi
0x180061744  mov     ebx, 80000001h
0x180061749  mov     [rbp+57h+string], rsi
0x18006174d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180061751  mov     [rbp+57h+var_70], ebx
0x180061754  lea     edx, [rsi+40h]; length
0x180061757  lea     rcx, ?RuntimeClass_Windows_Internal_Holographic_Miracast_HolographicMiracastControl@@3QBGB; "Windows.Internal.Holographic.Miracast.H"...
0x18006175e  call    cs:__imp_WindowsCreateStringReference
0x180061764  test    eax, eax
0x180061766  jns     short loc_18006177A
0x180061768  xor     r9d, r9d; lpArguments
0x18006176b  lea     edx, [rsi+1]; dwExceptionFlags
0x18006176e  xor     r8d, r8d; nNumberOfArguments
0x180061771  mov     ecx, eax; dwExceptionCode
0x180061773  call    cs:__imp_RaiseException
0x180061779  int     3; Trap to Debugger
0x18006177a  mov     rcx, [rbp+57h+string]
0x18006177e  lea     rdx, [rbp+57h+var_60]
0x180061782  call    ??$GetActivationFactory@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>)
0x180061787  mov     [rbp+57h+var_68], rsi
0x18006178b  test    eax, eax
0x18006178d  js      short loc_1800617F5
0x18006178f  lea     rdx, [rdi+4]; unsigned __int16 *
0x180061793  or      r8, 0FFFFFFFFFFFFFFFFh
0x180061797  inc     r8; unsigned int
0x18006179a  cmp     [rdx+r8*2], si
0x18006179f  jnz     short loc_180061797
0x1800617a1  mov     eax, 0FFFFFFFFh
0x1800617a6  cmp     r8, rax
0x1800617a9  ja      short loc_1800617F5
0x1800617ab  lea     rcx, [rbp+57h+var_68]; this
0x1800617af  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800617b4  test    eax, eax
0x1800617b6  js      short loc_1800617F5
0x1800617b8  mov     rcx, [rbp+57h+var_60]
0x1800617bc  lea     rdx, [rbp+57h+var_70]
0x1800617c0  movups  xmm0, xmmword ptr [rdi+218h]
0x1800617c7  mov     r8, [rdi+210h]
0x1800617ce  lea     r9, [rbp+57h+hstringHeader]
0x1800617d2  mov     [rsp+0A0h+var_80], rdx
0x1800617d7  mov     rax, [rcx]
0x1800617da  mov     rdx, [rbp+57h+var_68]
0x1800617de  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800617e3  mov     rax, [rax+30h]
0x1800617e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617ec  test    eax, eax
0x1800617ee  js      short loc_1800617F5
0x1800617f0  mov     ebx, [rbp+57h+var_70]
0x1800617f3  jmp     short loc_1800617F8
0x1800617f5  mov     [rbp+57h+var_70], ebx
0x1800617f8  mov     rcx, [rbp+57h+var_68]; string
0x1800617fc  call    cs:__imp_WindowsDeleteString
0x180061802  lea     rcx, [rbp+57h+var_60]
0x180061806  mov     [rbp+57h+var_68], rsi
0x18006180a  call    ?InternalRelease@?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(void)
0x18006180f  mov     eax, ebx
0x180061811  mov     rcx, [rbp+57h+var_30]
0x180061815  xor     rcx, rsp; StackCookie
0x180061818  call    __security_check_cookie
0x18006181d  add     rsp, 88h
0x180061824  pop     rdi
0x180061825  pop     rsi
0x180061826  pop     rbx
0x180061827  pop     rbp
0x180061828  retn
```
