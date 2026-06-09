# Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(ushort const *)

- ea: `0x180010270`
- end: `0x1800104b7`
- name: `?IsModernApp@CToastActivator_Foreground@Notifications@Internal@Windows@@AEAA_NPEBG@Z`
- size: `583`
- prototype: `bool(Windows::Internal::Notifications::CToastActivator_Foreground *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010160`
- `0x1800101f0`

## callees

- `0x180005670`
- `0x180010270`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001033a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001044b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001033a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001044b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800102b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001034f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800102b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001034f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800102f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800102f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall Windows::Internal::Notifications::CToastActivator_Foreground::IsModernApp(
        Windows::Internal::Notifications::CToastActivator_Foreground *this,
        const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // eax
  unsigned __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool result; // al
  int v12; // [rsp+20h] [rbp-78h]
  __int64 v13; // [rsp+30h] [rbp-68h] BYREF
  __int64 v14; // [rsp+38h] [rbp-60h] BYREF
  int v15; // [rsp+40h] [rbp-58h] BYREF
  HSTRING string; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  HSTRING v18; // [rsp+68h] [rbp-30h] BYREF
  HSTRING_HEADER v19; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v14 = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  try
  {
    if ( v3 < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v14);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v12);
    v13 = 0;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 > 0xFFFFFFFF )
    {
      LODWORD(v5) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a2, v5, &v19, &v18);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v14 + 240LL))(v14, 0, v18, &v13);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v6,
        v12);
    v15 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 88LL))(v13, &v15);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v7,
        v12);
    if ( v15 == 1 )
    {
      v9 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = v14;
      if ( v14 )
      {
        v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      result = 1;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      result = 0;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
      v8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010270  mov     [rsp+arg_0], rbx
0x180010275  mov     [rsp+arg_10], rsi
0x18001027a  push    rdi
0x18001027b  sub     rsp, 90h
0x180010282  mov     rax, cs:__security_cookie
0x180010289  xor     rax, rsp
0x18001028c  mov     [rsp+98h+var_10], rax
0x180010294  mov     rdi, rdx
0x180010297  xor     esi, esi
0x180010299  mov     [rsp+98h+var_60], rsi
0x18001029e  lea     r9, [rsp+98h+string]; string
0x1800102a3  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x1800102a8  mov     edx, 2Ch ; ','; length
0x1800102ad  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800102b4  call    cs:__imp_WindowsCreateStringReference
0x1800102ba  test    eax, eax
0x1800102bc  js      loc_18001043B
0x1800102c2  mov     rbx, [rsp+98h+string]
0x1800102c7  mov     rcx, [rsp+98h+var_60]
0x1800102cc  test    rcx, rcx
0x1800102cf  jz      short loc_1800102E3
0x1800102d1  mov     [rsp+98h+var_60], rsi
0x1800102d6  mov     rax, [rcx]
0x1800102d9  mov     rax, [rax+10h]
0x1800102dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e2  nop
0x1800102e3  lea     r8, [rsp+98h+var_60]
0x1800102e8  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800102ef  mov     rcx, rbx
0x1800102f2  call    cs:__imp_RoGetActivationFactory
0x1800102f8  mov     rcx, [rsp+98h]; this
0x180010300  test    eax, eax
0x180010302  js      loc_180010456
0x180010308  mov     [rsp+98h+var_68], rsi
0x18001030d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180010314  inc     rbx
0x180010317  cmp     word ptr [rdi+rbx*2], 0
0x18001031c  jnz     short loc_180010314
0x18001031e  mov     eax, 0FFFFFFFFh
0x180010323  cmp     rbx, rax
0x180010326  jbe     short loc_180010340
0x180010328  mov     ebx, eax
0x18001032a  xor     r9d, r9d; lpArguments
0x18001032d  xor     r8d, r8d; nNumberOfArguments
0x180010330  mov     edx, 1; dwExceptionFlags
0x180010335  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001033a  call    cs:__imp_RaiseException
0x180010340  lea     r9, [rsp+98h+var_30]; string
0x180010345  lea     r8, [rsp+98h+var_28]; hstringHeader
0x18001034a  mov     edx, ebx; length
0x18001034c  mov     rcx, rdi; sourceString
0x18001034f  call    cs:__imp_WindowsCreateStringReference
0x180010355  mov     rbx, [rsp+98h+var_60]
0x18001035a  mov     rax, [rbx]
0x18001035d  mov     rdi, [rax+0F0h]
0x180010364  mov     rcx, [rsp+98h+var_68]
0x180010369  test    rcx, rcx
0x18001036c  jz      short loc_180010380
0x18001036e  mov     [rsp+98h+var_68], rsi
0x180010373  mov     rax, [rcx]
0x180010376  mov     rax, [rax+10h]
0x18001037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001037f  nop
0x180010380  lea     r9, [rsp+98h+var_68]
0x180010385  mov     r8, [rsp+98h+var_30]
0x18001038a  xor     edx, edx
0x18001038c  mov     rcx, rbx
0x18001038f  mov     rax, rdi
0x180010392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010397  mov     rcx, [rsp+98h]; this
0x18001039f  test    eax, eax
0x1800103a1  js      loc_18001046B
0x1800103a7  mov     [rsp+98h+var_58], esi
0x1800103ab  mov     rcx, [rsp+98h+var_68]
0x1800103b0  mov     rax, [rcx]
0x1800103b3  lea     rdx, [rsp+98h+var_58]
0x1800103b8  mov     rax, [rax+58h]
0x1800103bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c1  mov     rcx, [rsp+98h]; this
0x1800103c9  test    eax, eax
0x1800103cb  js      loc_18001047F
0x1800103d1  cmp     [rsp+98h+var_58], 1
0x1800103d6  jnz     loc_180010494
0x1800103dc  mov     rcx, [rsp+98h+var_68]
0x1800103e1  test    rcx, rcx
0x1800103e4  jz      short loc_1800103F8
0x1800103e6  mov     [rsp+98h+var_68], rsi
0x1800103eb  mov     rax, [rcx]
0x1800103ee  mov     rax, [rax+10h]
0x1800103f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f7  nop
0x1800103f8  mov     rcx, [rsp+98h+var_60]
0x1800103fd  test    rcx, rcx
0x180010400  jz      short loc_180010414
0x180010402  mov     [rsp+98h+var_60], rsi
0x180010407  mov     rax, [rcx]
0x18001040a  mov     rax, [rax+10h]
0x18001040e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010413  nop
0x180010414  mov     al, 1
0x180010416  mov     rcx, [rsp+98h+var_10]
0x18001041e  xor     rcx, rsp; StackCookie
0x180010421  call    __security_check_cookie
0x180010426  lea     r11, [rsp+98h+var_8]
0x18001042e  mov     rbx, [r11+10h]
0x180010432  mov     rsi, [r11+20h]
0x180010436  mov     rsp, r11
0x180010439  pop     rdi
0x18001043a  retn
0x18001043b  xor     r9d, r9d; lpArguments
0x18001043e  xor     r8d, r8d; nNumberOfArguments
0x180010441  mov     edx, 1; dwExceptionFlags
0x180010446  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001044b  call    cs:__imp_RaiseException
0x180010451  jmp     loc_1800102C2
0x180010456  mov     r9d, eax; char *
0x180010459  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010460  mov     edx, 0BBh; void *
0x180010465  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001046b  mov     r9d, eax; char *
0x18001046e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010475  mov     edx, 0BFh; void *
0x18001047a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001047f  mov     r9d, eax; char *
0x180010482  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010489  mov     edx, 0C2h; void *
0x18001048e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010494  lea     rcx, [rsp+98h+var_68]
0x180010499  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001049e  nop
0x18001049f  lea     rcx, [rsp+98h+var_60]
0x1800104a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800104a9  xor     al, al
0x1800104ab  jmp     loc_180010416
0x1800104b0  xor     al, al
0x1800104b2  jmp     loc_180010416
```
