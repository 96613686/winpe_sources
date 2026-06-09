# QueryAssociationBroker::GetActivationInfoForAumIdAndContract(HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18002e150`
- end: `0x18002e50f`
- name: `?GetActivationInfoForAumIdAndContract@QueryAssociationBroker@@UEAAJPEAUHSTRING__@@00EPEAPEAU2@1@Z`
- size: `959`
- prototype: `int(QueryAssociationBroker *__hidden this, HSTRING, HSTRING, HSTRING, unsigned __int8, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180023044`
- `0x18002cec0`
- `0x18002e150`
- `0x18002e518`
- `0x18002e5b4`
- `0x18008a030`
- `0x1800ae208`
- `0x1800b03cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e4c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e4c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e1f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e224`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e24e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e27a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e1f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e224`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e24e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e2b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e2b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e484`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e484`

## string_xrefs

- `0x18002e26e`: `Windows.AppUriHandler`
- `0x18002e310`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18002e447`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18002e218`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall QueryAssociationBroker::GetActivationInfoForAumIdAndContract(
        QueryAssociationBroker *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        unsigned __int8 a5,
        HSTRING *a6,
        HSTRING *a7)
{
  HSTRING *v9; // r15
  HSTRING *v10; // r12
  const WCHAR *v11; // rsi
  char v12; // di
  unsigned __int64 v13; // rbx
  const wchar_t *v14; // rax
  unsigned __int16 **v15; // r8
  int v16; // eax
  __int128 *v17; // rax
  __int128 v18; // xmm6
  __int128 v19; // xmm7
  __int128 v20; // xmm8
  __int128 v21; // xmm9
  const WCHAR *v22; // rsi
  unsigned int v23; // eax
  HSTRING v24; // rcx
  HSTRING v25; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-1A8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-1A8h]
  char v29[8]; // [rsp+50h] [rbp-178h] BYREF
  HSTRING string; // [rsp+58h] [rbp-170h] BYREF
  const wchar_t *v31; // [rsp+60h] [rbp-168h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-160h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-158h] BYREF
  __int64 v34; // [rsp+78h] [rbp-150h]
  __int64 v35; // [rsp+80h] [rbp-148h]
  const unsigned __int16 *v36; // [rsp+88h] [rbp-140h] BYREF
  _BYTE v37[8]; // [rsp+90h] [rbp-138h] BYREF
  PCWSTR StringRawBuffer; // [rsp+98h] [rbp-130h] BYREF
  _OWORD v39[4]; // [rsp+A0h] [rbp-128h] BYREF
  char v40; // [rsp+E0h] [rbp-E8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+120h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+138h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v9 = a6;
  v10 = a7;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  *v9 = 0;
  *v10 = 0;
  v31 = 0;
  v32 = 0;
  string = 0;
  v11 = WindowsGetStringRawBuffer(a2, 0);
  v29[0] = 0;
  v12 = 1;
  v13 = -1;
  if ( CompareStringOrdinal(v11, -1, L"Windows.File", 12, 1) == 2 )
  {
    v14 = L"SupportedFileTypes";
LABEL_9:
    v31 = v14;
    goto LABEL_10;
  }
  if ( CompareStringOrdinal(v11, -1, L"Windows.Protocol", 16, 1) == 2 )
  {
    v14 = L"Name";
    goto LABEL_9;
  }
  if ( CompareStringOrdinal(v11, -1, L"Windows.Launch", 14, 1) == 2 )
  {
    v31 = 0;
    goto LABEL_10;
  }
  if ( CompareStringOrdinal(v11, -1, L"Windows.AppUriHandler", 21, 1) == 2 )
  {
    v14 = L"HostNames";
    v29[0] = 1;
    goto LABEL_9;
  }
LABEL_10:
  pv = 0;
  v36 = WindowsGetStringRawBuffer(a4, 0);
  v34 = -1;
  v35 = -1;
  v16 = ParseAppUserModelId(v36, (unsigned __int16 **)&pv, v15);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x413,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v16,
      bIgnoreCase);
  ExtensionDatabaseProvider::ExtensionDatabaseProvider((ExtensionDatabaseProvider *)v37);
  v17 = (__int128 *)lambda_e38df6b79d544ed5fff633626cb07f41_::_lambda_e38df6b79d544ed5fff633626cb07f41_(
                      (unsigned int)&v40,
                      (unsigned int)&v36,
                      (unsigned int)&v31,
                      (unsigned int)&a5,
                      (__int64)&v32,
                      (__int64)&string,
                      (__int64)&StringRawBuffer,
                      (__int64)v29,
                      (__int64)&pv);
  v18 = *v17;
  v19 = v17[1];
  v20 = v17[2];
  v21 = v17[3];
  v42 = 0;
  v22 = (const WCHAR *)pv;
  do
    ++v13;
  while ( *((_WORD *)pv + v13) );
  if ( v13 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    return (unsigned int)string;
  }
  else
  {
    v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v13);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v22, v23, v13);
    v39[0] = v18;
    v39[1] = v19;
    v39[2] = v20;
    v39[3] = v21;
    ExtensionDatabaseProvider::ForEachExtension__lambda_e38df6b79d544ed5fff633626cb07f41___(v37, a2, v42, v39);
    v24 = v32;
    v25 = string;
    if ( !v32 || !string )
      v12 = 0;
    if ( !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x8000FFFFLL,
        bIgnoreCasea);
    v32 = 0;
    *v10 = v24;
    string = 0;
    *v9 = v25;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v37);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v34 = 0;
    v35 = 0;
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v32);
    return 0;
  }
}

```

## disassembly

```asm
0x18002e150  mov     rax, rsp
0x18002e153  push    rbx
0x18002e154  push    rsi
0x18002e155  push    rdi
0x18002e156  push    r12
0x18002e158  push    r13
0x18002e15a  push    r14
0x18002e15c  push    r15
0x18002e15e  sub     rsp, 190h
0x18002e165  movaps  xmmword ptr [rax-48h], xmm6
0x18002e169  movaps  xmmword ptr [rax-58h], xmm7
0x18002e16d  movaps  xmmword ptr [rax-68h], xmm8
0x18002e172  movaps  xmmword ptr [rax-78h], xmm9
0x18002e177  mov     rax, cs:__security_cookie
0x18002e17e  xor     rax, rsp
0x18002e181  mov     [rsp+1C8h+var_88], rax
0x18002e189  mov     r14, r9
0x18002e18c  mov     r13, rdx
0x18002e18f  mov     r15, [rsp+1C8h+arg_28]
0x18002e197  mov     r12, [rsp+1C8h+arg_30]
0x18002e19f  xor     edx, edx; length
0x18002e1a1  mov     rcx, r8; string
0x18002e1a4  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e1aa  mov     [rsp+1C8h+var_130], rax
0x18002e1b2  xor     ebx, ebx
0x18002e1b4  mov     [r15], rbx
0x18002e1b7  mov     [r12], rbx
0x18002e1bb  mov     [rsp+1C8h+var_168], rbx
0x18002e1c0  mov     [rsp+1C8h+var_160], rbx
0x18002e1c5  mov     [rsp+1C8h+string], rbx
0x18002e1ca  xor     edx, edx; length
0x18002e1cc  mov     rcx, r13; string
0x18002e1cf  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e1d5  mov     rsi, rax
0x18002e1d8  mov     [rsp+1C8h+var_178], bl
0x18002e1dc  lea     edi, [rbx+1]
0x18002e1df  mov     [rsp+1C8h+bIgnoreCase], edi; bIgnoreCase
0x18002e1e3  lea     r9d, [rbx+0Ch]; cchCount2
0x18002e1e7  lea     r8, aWindowsFile; "Windows.File"
0x18002e1ee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e1f2  mov     edx, ebx; cchCount1
0x18002e1f4  mov     rcx, rax; lpString1
0x18002e1f7  call    cs:__imp_CompareStringOrdinal
0x18002e1fd  cmp     eax, 2
0x18002e200  jnz     short loc_18002E20E
0x18002e202  lea     rax, aSupportedfilet; "SupportedFileTypes"
0x18002e209  jmp     loc_18002E291
0x18002e20e  mov     [rsp+1C8h+bIgnoreCase], edi; bIgnoreCase
0x18002e212  mov     r9d, 10h; cchCount2
0x18002e218  lea     r8, aWindowsProtoco; "Windows.Protocol"
0x18002e21f  mov     edx, ebx; cchCount1
0x18002e221  mov     rcx, rsi; lpString1
0x18002e224  call    cs:__imp_CompareStringOrdinal
0x18002e22a  cmp     eax, 2
0x18002e22d  jnz     short loc_18002E238
0x18002e22f  lea     rax, aName; "Name"
0x18002e236  jmp     short loc_18002E291
0x18002e238  mov     [rsp+1C8h+bIgnoreCase], edi; bIgnoreCase
0x18002e23c  mov     r9d, 0Eh; cchCount2
0x18002e242  lea     r8, aWindowsLaunch; "Windows.Launch"
0x18002e249  mov     edx, ebx; cchCount1
0x18002e24b  mov     rcx, rsi; lpString1
0x18002e24e  call    cs:__imp_CompareStringOrdinal
0x18002e254  cmp     eax, 2
0x18002e257  jnz     short loc_18002E264
0x18002e259  mov     [rsp+1C8h+var_168], 0
0x18002e262  jmp     short loc_18002E296
0x18002e264  mov     [rsp+1C8h+bIgnoreCase], edi; int
0x18002e268  mov     r9d, 15h; cchCount2
0x18002e26e  lea     r8, aWindowsAppurih; "Windows.AppUriHandler"
0x18002e275  mov     edx, ebx; cchCount1
0x18002e277  mov     rcx, rsi; lpString1
0x18002e27a  call    cs:__imp_CompareStringOrdinal
0x18002e280  cmp     eax, 2
0x18002e283  jnz     short loc_18002E296
0x18002e285  lea     rax, aHostnames; "HostNames"
0x18002e28c  mov     [rsp+1C8h+var_178], dil
0x18002e291  mov     [rsp+1C8h+var_168], rax
0x18002e296  mov     [rsp+1C8h+pv], 0
0x18002e29f  mov     [rsp+1C8h+var_150], 0
0x18002e2a8  mov     [rsp+1C8h+var_148], 0
0x18002e2b4  xor     edx, edx; length
0x18002e2b6  mov     rcx, r14; string
0x18002e2b9  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e2bf  mov     [rsp+1C8h+var_140], rax
0x18002e2c7  mov     rcx, [rsp+1C8h+pv]; pv
0x18002e2cc  xor     r14d, r14d
0x18002e2cf  test    rcx, rcx
0x18002e2d2  jz      short loc_18002E2E7
0x18002e2d4  call    cs:__imp_CoTaskMemFree
0x18002e2da  mov     [rsp+1C8h+pv], r14
0x18002e2df  mov     rax, [rsp+1C8h+var_140]
0x18002e2e7  mov     [rsp+1C8h+var_150], rbx
0x18002e2ec  mov     [rsp+1C8h+var_148], rbx
0x18002e2f4  lea     rdx, [rsp+1C8h+pv]; unsigned __int16 **
0x18002e2f9  mov     rcx, rax; unsigned __int16 *
0x18002e2fc  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x18002e301  mov     rcx, [rsp+1C8h]; this
0x18002e309  test    eax, eax
0x18002e30b  jns     short loc_18002E321
0x18002e30d  mov     r9d, eax; char *
0x18002e310  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18002e317  mov     edx, 413h; void *
0x18002e31c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e321  lea     rcx, [rsp+1C8h+var_138]; this
0x18002e329  call    ??0ExtensionDatabaseProvider@@QEAA@XZ; ExtensionDatabaseProvider::ExtensionDatabaseProvider(void)
0x18002e32e  nop
0x18002e32f  lea     rax, [rsp+1C8h+pv]
0x18002e334  mov     [rsp+1C8h+var_188], rax
0x18002e339  lea     rax, [rsp+1C8h+var_178]
0x18002e33e  mov     [rsp+1C8h+var_190], rax
0x18002e343  lea     rax, [rsp+1C8h+var_130]
0x18002e34b  mov     [rsp+1C8h+var_198], rax
0x18002e350  lea     rax, [rsp+1C8h+string]
0x18002e355  mov     [rsp+1C8h+var_1A0], rax
0x18002e35a  lea     rax, [rsp+1C8h+var_160]
0x18002e35f  mov     qword ptr [rsp+1C8h+bIgnoreCase], rax; int
0x18002e364  lea     r9, [rsp+1C8h+arg_20]
0x18002e36c  lea     r8, [rsp+1C8h+var_168]
0x18002e371  lea     rdx, [rsp+1C8h+var_140]
0x18002e379  lea     rcx, [rsp+1C8h+var_E8]
0x18002e381  call    _lambda_e38df6b79d544ed5fff633626cb07f41____lambda_e38df6b79d544ed5fff633626cb07f41_
0x18002e386  movups  xmm6, xmmword ptr [rax]
0x18002e389  movups  xmm7, xmmword ptr [rax+10h]
0x18002e38d  movups  xmm8, xmmword ptr [rax+20h]
0x18002e392  movups  xmm9, xmmword ptr [rax+30h]
0x18002e397  mov     [rsp+1C8h+var_90], r14
0x18002e39f  mov     rsi, [rsp+1C8h+pv]
0x18002e3a4  inc     rbx
0x18002e3a7  cmp     [rsi+rbx*2], r14w
0x18002e3ac  jnz     short loc_18002E3A4
0x18002e3ae  mov     eax, 0FFFFFFFFh
0x18002e3b3  cmp     rbx, rax
0x18002e3b6  ja      loc_18002E4BB
0x18002e3bc  mov     ecx, ebx; unsigned int
0x18002e3be  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002e3c3  mov     r9d, ebx; unsigned int
0x18002e3c6  mov     r8d, eax; unsigned int
0x18002e3c9  mov     rdx, rsi; sourceString
0x18002e3cc  lea     rcx, [rsp+1C8h+hstringHeader]; hstringHeader
0x18002e3d4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e3d9  nop
0x18002e3da  movaps  [rsp+1C8h+var_128], xmm6
0x18002e3e2  movaps  [rsp+1C8h+var_118], xmm7
0x18002e3ea  movaps  [rsp+1C8h+var_108], xmm8
0x18002e3f3  movaps  [rsp+1C8h+var_F8], xmm9
0x18002e3fc  lea     r9, [rsp+1C8h+var_128]
0x18002e404  mov     r8, [rsp+1C8h+var_90]
0x18002e40c  mov     rdx, r13
0x18002e40f  lea     rcx, [rsp+1C8h+var_138]
0x18002e417  call    ExtensionDatabaseProvider__ForEachExtension__lambda_e38df6b79d544ed5fff633626cb07f41___
0x18002e41c  nop
0x18002e41d  mov     rcx, [rsp+1C8h+var_160]
0x18002e422  mov     rax, [rsp+1C8h+string]
0x18002e427  test    rcx, rcx
0x18002e42a  jz      short loc_18002E431
0x18002e42c  test    rax, rax
0x18002e42f  jnz     short loc_18002E434
0x18002e431  mov     dil, r14b
0x18002e434  mov     r10, [rsp+1C8h]
0x18002e43c  test    dil, dil
0x18002e43f  jnz     short loc_18002E45B
0x18002e441  mov     r9d, 8000FFFFh; char *
0x18002e447  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18002e44e  mov     edx, 45Eh; void *
0x18002e453  mov     rcx, r10; this
0x18002e456  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e45b  mov     [rsp+1C8h+var_160], r14
0x18002e460  mov     [r12], rcx
0x18002e464  mov     [rsp+1C8h+string], r14
0x18002e469  mov     [r15], rax
0x18002e46c  lea     rcx, [rsp+1C8h+var_138]
0x18002e474  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e479  nop
0x18002e47a  mov     rcx, [rsp+1C8h+pv]; pv
0x18002e47f  test    rcx, rcx
0x18002e482  jz      short loc_18002E48F
0x18002e484  call    cs:__imp_CoTaskMemFree
0x18002e48a  mov     [rsp+1C8h+pv], r14
0x18002e48f  mov     [rsp+1C8h+var_150], r14
0x18002e494  mov     [rsp+1C8h+var_148], r14
0x18002e49c  mov     rcx, [rsp+1C8h+string]; string
0x18002e4a1  call    cs:__imp_WindowsDeleteString
0x18002e4a7  mov     [rsp+1C8h+string], r14
0x18002e4ac  mov     rcx, [rsp+1C8h+var_160]; string
0x18002e4b1  call    cs:__imp_WindowsDeleteString
0x18002e4b7  xor     eax, eax
0x18002e4b9  jmp     short loc_18002E4D3
0x18002e4bb  xor     r9d, r9d; lpArguments
0x18002e4be  xor     r8d, r8d; nNumberOfArguments
0x18002e4c1  mov     edx, edi; dwExceptionFlags
0x18002e4c3  mov     ecx, 80070216h; dwExceptionCode
0x18002e4c8  call    cs:__imp_RaiseException
0x18002e4ce  nop
0x18002e4cf  mov     eax, dword ptr [rsp+1C8h+string]
0x18002e4d3  mov     rcx, [rsp+1C8h+var_88]
0x18002e4db  xor     rcx, rsp; StackCookie
0x18002e4de  call    __security_check_cookie
0x18002e4e3  lea     r11, [rsp+1C8h+var_38]
0x18002e4eb  movaps  xmm6, xmmword ptr [r11-10h]
0x18002e4f0  movaps  xmm7, xmmword ptr [r11-20h]
0x18002e4f5  movaps  xmm8, xmmword ptr [r11-30h]
0x18002e4fa  movaps  xmm9, xmmword ptr [r11-40h]
0x18002e4ff  mov     rsp, r11
0x18002e502  pop     r15
0x18002e504  pop     r14
0x18002e506  pop     r13
0x18002e508  pop     r12
0x18002e50a  pop     rdi
0x18002e50b  pop     rsi
0x18002e50c  pop     rbx
0x18002e50d  retn
```
