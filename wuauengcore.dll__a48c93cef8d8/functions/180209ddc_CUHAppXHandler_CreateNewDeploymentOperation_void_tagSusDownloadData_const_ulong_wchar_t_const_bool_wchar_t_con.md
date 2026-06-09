# CUHAppXHandler::CreateNewDeploymentOperation(void *,tagSusDownloadData const *,ulong,wchar_t const *,bool,wchar_t const *,ISusHandlerNotification *,CAppxDeploymentOperation * *)

- ea: `0x180209ddc`
- end: `0x18020a259`
- name: `?CreateNewDeploymentOperation@CUHAppXHandler@@IEAAJPEAXPEBUtagSusDownloadData@@KPEB_W_N2PEAUISusHandlerNotification@@PEAPEAVCAppxDeploymentOperation@@@Z`
- size: `1149`
- prototype: `int(CUHAppXHandler *__hidden this, void *, const struct tagSusDownloadData *, unsigned int, const wchar_t *, bool, const wchar_t *, struct ISusHandlerNotification *, struct CAppxDeploymentOperation **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180206a20`
- `0x180207a50`

## callees

- `0x18003a6c4`
- `0x18012b618`
- `0x18012bed4`
- `0x18020779c`
- `0x180209ddc`
- `0x18020f7ac`
- `0x180210920`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180209e80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18020a0a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18020a1ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180209e80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18020a0a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18020a1ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180209e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020a0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020a1ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180209e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020a0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020a1ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180209ff4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180209ff4`

## string_xrefs

- `0x180209e5f`: `Windows.Foundation.Uri`
- `0x18020a196`: `Staging package for update %ws [Required content only: %ws] `
- `0x180209ec6`: `CUHAppXHandler::CreateNewDeploymentOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CUHAppXHandler::CreateNewDeploymentOperation(
        CUHAppXHandler *this,
        void *a2,
        const struct tagSusDownloadData *a3,
        unsigned int a4,
        const wchar_t *a5,
        bool a6,
        const wchar_t *a7,
        struct ISusHandlerNotification *a8,
        struct CAppxDeploymentOperation **a9)
{
  int ActivationFactory; // ebx
  struct CAppxDeploymentOperation *v12; // rcx
  struct ABI::Windows::Foundation::IUriRuntimeClass *v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  const wchar_t *v17; // r8
  int v18; // eax
  HSTRING v19; // rbx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, HSTRING, struct ABI::Windows::Foundation::IUriRuntimeClass **); // r12
  struct ABI::Windows::Foundation::IUriRuntimeClass *v26; // rcx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rsi
  const WCHAR *v29; // rax
  struct CAppxDeploymentOperation *v30; // rcx
  const wchar_t *v31; // rbx
  __int64 v32; // rax
  HSTRING v33; // r9
  struct CAppxDeploymentOperation *v34; // rax
  struct CAppxDeploymentOperation *v35; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-B8h]
  PCWSTR sourceString; // [rsp+50h] [rbp-B0h]
  struct ISusHandlerNotification *v38; // [rsp+58h] [rbp-A8h]
  void *v39; // [rsp+60h] [rbp-A0h]
  CUHAppXHandler *v40; // [rsp+68h] [rbp-98h]
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER v42; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v43[80]; // [rsp+90h] [rbp-70h] BYREF
  struct ABI::Windows::Foundation::IUriRuntimeClass *v44; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-18h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+F0h] [rbp-10h] BYREF
  HSTRING hstringHeader[5]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v48[56]; // [rsp+120h] [rbp+20h] BYREF

  v36 = a4;
  v39 = a2;
  v40 = this;
  sourceString = a5;
  v38 = a8;
  memset(hstringHeader, 0, 32);
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Uri",
         0x16u,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v35 = 0;
  if ( !a9 )
  {
    ActivationFactory = -2147467261;
LABEL_5:
    WUTrace("CUHAppXHandler::CreateNewDeploymentOperation", 1937, 4096, 3, ActivationFactory, L"Method failed");
    v12 = v35;
    goto LABEL_6;
  }
  *a9 = 0;
  v17 = (const wchar_t *)*((_QWORD *)a3 + 11);
  if ( v17 )
    v18 = StringCchCopyExW(v48, 0x33u, v17, 0, 0, 0x100u);
  else
    v18 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, int, wchar_t *))(*((_QWORD *)this + 7) + 160LL))(
            (char *)this + 56,
            *((_QWORD *)a3 + 4),
            0,
            0,
            51,
            v48);
  ActivationFactory = v18;
  if ( v18 < 0 )
    goto LABEL_5;
  v19 = hstringHeader[0];
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
  }
  ActivationFactory = RoGetActivationFactory(v19, &GUID_00000035_0000_0000_c000_000000000046, &v46);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
  v22 = **v46;
  v23 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  ActivationFactory = v22(v21, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v45);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v24 = v45;
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING, struct ABI::Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v45 + 48LL);
  v26 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct ABI::Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = -1;
  v28 = -1;
  v29 = sourceString;
  do
    ++v28;
  while ( sourceString[v28] );
  if ( v28 > 0xFFFFFFFF )
  {
    LODWORD(v28) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
    v29 = sourceString;
  }
  WindowsCreateStringReference(v29, v28, &v42, &string);
  ActivationFactory = v25(v24, string, &v44);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(struct CAppxDeploymentOperation *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  ActivationFactory = CAppxDeploymentOperation::CreateInstance(
                        *((_DWORD *)a3 + 31) != 0,
                        v39,
                        v38,
                        (const struct _GUID *)a3,
                        (const struct tagDSGlobalUpdateId *)(*((_QWORD *)a3 + 4) + 4LL),
                        *((const wchar_t **)a3 + 17),
                        &v35);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  ActivationFactory = CUHAppXHandler::AddDeploymentOperation(
                        v40,
                        (const struct _GUID *)(*((_QWORD *)a3 + 4) + 4LL),
                        v35);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v31 = L"False";
  if ( *((_DWORD *)a3 + 31) )
    v31 = L"True";
  v32 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v43, (const struct _GUID *)(*((_QWORD *)a3 + 4) + 4LL));
  WUTrace(0, 0, 4096, 4, 0, L"Staging package for update %ws [Required content only: %ws] ", v32, v31);
  if ( a7 )
  {
    do
      ++v27;
    while ( a7[v27] );
    if ( v27 > 0xFFFFFFFF )
    {
      LODWORD(v27) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a7, v27, &v42, &string);
    v33 = string;
  }
  else
  {
    v33 = 0;
  }
  ActivationFactory = CAppxDeploymentOperation::StagePackageAsync(
                        v35,
                        v44,
                        v48,
                        v33,
                        *((const wchar_t **)a3 + 17),
                        *((const char **)a3 + 9),
                        v36);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v34 = v35;
  v12 = 0;
  v35 = 0;
  *a9 = v34;
LABEL_6:
  if ( v12 )
  {
    v35 = 0;
    (*(void (__fastcall **)(struct CAppxDeploymentOperation *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct ABI::Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180209ddc  mov     [rsp-8+arg_18], rbx
0x180209de1  push    rbp
0x180209de2  push    rsi
0x180209de3  push    rdi
0x180209de4  push    r12
0x180209de6  push    r13
0x180209de8  push    r14
0x180209dea  push    r15
0x180209dec  lea     rbp, [rsp-0A0h]
0x180209df4  sub     rsp, 1A0h
0x180209dfb  mov     rax, cs:__security_cookie
0x180209e02  xor     rax, rsp
0x180209e05  mov     [rbp+0D0h+var_40], rax
0x180209e0c  mov     [rsp+1D0h+var_188], r9d
0x180209e11  mov     r14, r8
0x180209e14  mov     [rsp+1D0h+var_170], rdx
0x180209e19  mov     rbx, rcx
0x180209e1c  mov     [rsp+1D0h+var_168], rcx
0x180209e21  mov     rax, [rbp+0D0h+arg_20]
0x180209e28  mov     [rsp+1D0h+sourceString], rax
0x180209e2d  mov     r13, [rbp+0D0h+arg_30]
0x180209e34  mov     rax, [rbp+0D0h+arg_38]
0x180209e3b  mov     [rsp+1D0h+var_178], rax
0x180209e40  mov     r15, [rbp+0D0h+arg_40]
0x180209e47  xorps   xmm0, xmm0
0x180209e4a  movups  xmmword ptr [rbp+0D0h+hstringHeader], xmm0
0x180209e4e  movups  xmmword ptr [rbp+0D0h+hstringHeader+10h], xmm0
0x180209e52  lea     r9, [rbp+0D0h+hstringHeader]; string
0x180209e56  lea     r8, [rbp+0D0h+hstringHeader+8]; hstringHeader
0x180209e5a  mov     edx, 16h; length
0x180209e5f  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QB_WB; "Windows.Foundation.Uri"
0x180209e66  call    cs:__imp_WindowsCreateStringReference
0x180209e6c  xor     esi, esi
0x180209e6e  test    eax, eax
0x180209e70  jns     short loc_180209E86
0x180209e72  xor     r9d, r9d; lpArguments
0x180209e75  xor     r8d, r8d; nNumberOfArguments
0x180209e78  lea     edx, [rsi+1]; dwExceptionFlags
0x180209e7b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180209e80  call    cs:__imp_RaiseException
0x180209e86  mov     [rbp+0D0h+var_E0], rsi
0x180209e8a  mov     [rbp+0D0h+var_E8], rsi
0x180209e8e  mov     [rbp+0D0h+var_F0], rsi
0x180209e92  mov     [rsp+1D0h+var_190], rsi
0x180209e97  test    r15, r15
0x180209e9a  jnz     loc_180209F68
0x180209ea0  mov     ebx, 80004003h
0x180209ea5  lea     rax, aMethodFailed; "Method failed"
0x180209eac  mov     [rsp+1D0h+var_1A8], rax
0x180209eb1  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x180209eb5  mov     edx, 791h
0x180209eba  mov     r9d, 3
0x180209ec0  mov     r8d, 1000h
0x180209ec6  lea     rcx, aCuhappxhandler; "CUHAppXHandler::CreateNewDeploymentOper"...
0x180209ecd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180209ed2  mov     rcx, [rsp+1D0h+var_190]
0x180209ed7  test    rcx, rcx
0x180209eda  jz      short loc_180209EEE
0x180209edc  mov     [rsp+1D0h+var_190], rsi
0x180209ee1  mov     rax, [rcx]
0x180209ee4  mov     rax, [rax+10h]
0x180209ee8  call    _guard_dispatch_icall
0x180209eed  nop
0x180209eee  mov     rcx, [rbp+0D0h+var_F0]
0x180209ef2  test    rcx, rcx
0x180209ef5  jz      short loc_180209F08
0x180209ef7  mov     [rbp+0D0h+var_F0], rsi
0x180209efb  mov     rax, [rcx]
0x180209efe  mov     rax, [rax+10h]
0x180209f02  call    _guard_dispatch_icall
0x180209f07  nop
0x180209f08  mov     rcx, [rbp+0D0h+var_E8]
0x180209f0c  test    rcx, rcx
0x180209f0f  jz      short loc_180209F22
0x180209f11  mov     [rbp+0D0h+var_E8], rsi
0x180209f15  mov     rax, [rcx]
0x180209f18  mov     rax, [rax+10h]
0x180209f1c  call    _guard_dispatch_icall
0x180209f21  nop
0x180209f22  mov     rcx, [rbp+0D0h+var_E0]
0x180209f26  test    rcx, rcx
0x180209f29  jz      short loc_180209F3C
0x180209f2b  mov     [rbp+0D0h+var_E0], rsi
0x180209f2f  mov     rax, [rcx]
0x180209f32  mov     rax, [rax+10h]
0x180209f36  call    _guard_dispatch_icall
0x180209f3b  nop
0x180209f3c  mov     eax, ebx
0x180209f3e  mov     rcx, [rbp+0D0h+var_40]
0x180209f45  xor     rcx, rsp; StackCookie
0x180209f48  call    __security_check_cookie
0x180209f4d  mov     rbx, [rsp+1D0h+arg_18]
0x180209f55  add     rsp, 1A0h
0x180209f5c  pop     r15
0x180209f5e  pop     r14
0x180209f60  pop     r13
0x180209f62  pop     r12
0x180209f64  pop     rdi
0x180209f65  pop     rsi
0x180209f66  pop     rbp
0x180209f67  retn
0x180209f68  mov     [r15], rsi
0x180209f6b  mov     r8, [r14+58h]; wchar_t *
0x180209f6f  xor     r9d, r9d; wchar_t **
0x180209f72  test    r8, r8
0x180209f75  jz      short loc_180209F93
0x180209f77  mov     dword ptr [rsp+1D0h+var_1A8], 100h; unsigned int
0x180209f7f  mov     [rsp+1D0h+var_1B0], rsi; unsigned __int64 *
0x180209f84  lea     edx, [r9+33h]; unsigned __int64
0x180209f88  lea     rcx, [rbp+0D0h+var_B0]; wchar_t *
0x180209f8c  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180209f91  jmp     short loc_180209FBE
0x180209f93  lea     rcx, [rbx+38h]
0x180209f97  mov     rax, [rcx]
0x180209f9a  lea     rdx, [rbp+0D0h+var_B0]
0x180209f9e  mov     [rsp+1D0h+var_1A8], rdx
0x180209fa3  mov     dword ptr [rsp+1D0h+var_1B0], 33h ; '3'
0x180209fab  xor     r8d, r8d
0x180209fae  mov     rdx, [r14+20h]
0x180209fb2  mov     rax, [rax+0A0h]
0x180209fb9  call    _guard_dispatch_icall
0x180209fbe  test    eax, eax
0x180209fc0  mov     ebx, eax
0x180209fc2  js      loc_180209EA5
0x180209fc8  mov     rbx, [rbp+0D0h+hstringHeader]
0x180209fcc  mov     rcx, [rbp+0D0h+var_E0]
0x180209fd0  test    rcx, rcx
0x180209fd3  jz      short loc_180209FE6
0x180209fd5  mov     [rbp+0D0h+var_E0], rsi
0x180209fd9  mov     rax, [rcx]
0x180209fdc  mov     rax, [rax+10h]
0x180209fe0  call    _guard_dispatch_icall
0x180209fe5  nop
0x180209fe6  lea     r8, [rbp+0D0h+var_E0]
0x180209fea  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180209ff1  mov     rcx, rbx
0x180209ff4  call    cs:__imp_RoGetActivationFactory
0x180209ffa  mov     ebx, eax
0x180209ffc  test    eax, eax
0x180209ffe  js      loc_180209EA5
0x18020a004  mov     rbx, [rbp+0D0h+var_E0]
0x18020a008  mov     rax, [rbx]
0x18020a00b  mov     rdi, [rax]
0x18020a00e  mov     rdx, [rbp+0D0h+var_E8]
0x18020a012  test    rdx, rdx
0x18020a015  jz      short loc_18020A02B
0x18020a017  mov     [rbp+0D0h+var_E8], rsi
0x18020a01b  mov     rcx, [rdx]
0x18020a01e  mov     rax, [rcx+10h]
0x18020a022  mov     rcx, rdx
0x18020a025  call    _guard_dispatch_icall
0x18020a02a  nop
0x18020a02b  lea     r8, [rbp+0D0h+var_E8]
0x18020a02f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18020a036  mov     rcx, rbx
0x18020a039  mov     rax, rdi
0x18020a03c  call    _guard_dispatch_icall
0x18020a041  mov     ebx, eax
0x18020a043  test    eax, eax
0x18020a045  js      loc_180209EA5
0x18020a04b  mov     rbx, [rbp+0D0h+var_E8]
0x18020a04f  mov     rax, [rbx]
0x18020a052  mov     r12, [rax+30h]
0x18020a056  mov     rcx, [rbp+0D0h+var_F0]
0x18020a05a  test    rcx, rcx
0x18020a05d  jz      short loc_18020A070
0x18020a05f  mov     [rbp+0D0h+var_F0], rsi
0x18020a063  mov     rax, [rcx]
0x18020a066  mov     rax, [rax+10h]
0x18020a06a  call    _guard_dispatch_icall
0x18020a06f  nop
0x18020a070  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18020a074  mov     rsi, rdi
0x18020a077  mov     rax, [rsp+1D0h+sourceString]
0x18020a07c  xor     ecx, ecx
0x18020a07e  inc     rsi
0x18020a081  cmp     [rax+rsi*2], cx
0x18020a085  jnz     short loc_18020A07E
0x18020a087  mov     ecx, 0FFFFFFFFh
0x18020a08c  cmp     rsi, rcx
0x18020a08f  jbe     short loc_18020A0AD
0x18020a091  mov     esi, ecx
0x18020a093  xor     r9d, r9d; lpArguments
0x18020a096  xor     r8d, r8d; nNumberOfArguments
0x18020a099  lea     edx, [r9+1]; dwExceptionFlags
0x18020a09d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18020a0a2  call    cs:__imp_RaiseException
0x18020a0a8  mov     rax, [rsp+1D0h+sourceString]
0x18020a0ad  lea     r9, [rsp+1D0h+string]; string
0x18020a0b2  lea     r8, [rsp+1D0h+var_158]; hstringHeader
0x18020a0b7  mov     edx, esi; length
0x18020a0b9  mov     rcx, rax; sourceString
0x18020a0bc  call    cs:__imp_WindowsCreateStringReference
0x18020a0c2  lea     r8, [rbp+0D0h+var_F0]
0x18020a0c6  mov     rdx, [rsp+1D0h+string]
0x18020a0cb  mov     rcx, rbx
0x18020a0ce  mov     rax, r12
0x18020a0d1  call    _guard_dispatch_icall
0x18020a0d6  mov     ebx, eax
0x18020a0d8  xor     esi, esi
0x18020a0da  test    eax, eax
0x18020a0dc  js      loc_180209EA5
0x18020a0e2  mov     rcx, [rsp+1D0h+var_190]
0x18020a0e7  test    rcx, rcx
0x18020a0ea  jz      short loc_18020A0FE
0x18020a0ec  mov     [rsp+1D0h+var_190], rsi
0x18020a0f1  mov     rax, [rcx]
0x18020a0f4  mov     rax, [rax+10h]
0x18020a0f8  call    _guard_dispatch_icall
0x18020a0fd  nop
0x18020a0fe  mov     r9, [r14+20h]
0x18020a102  add     r9, 4
0x18020a106  cmp     [r14+7Ch], esi
0x18020a10a  setnz   cl; bool
0x18020a10d  lea     rax, [rsp+1D0h+var_190]
0x18020a112  mov     [rsp+1D0h+var_1A0], rax; struct CAppxDeploymentOperation **
0x18020a117  mov     rax, [r14+88h]
0x18020a11e  mov     [rsp+1D0h+var_1A8], rax; wchar_t *
0x18020a123  mov     [rsp+1D0h+var_1B0], r9; struct tagDSGlobalUpdateId *
0x18020a128  mov     r9, r14; struct _GUID *
0x18020a12b  mov     r8, [rsp+1D0h+var_178]; struct ISusHandlerNotification *
0x18020a130  mov     rdx, [rsp+1D0h+var_170]; void *
0x18020a135  call    ?CreateInstance@CAppxDeploymentOperation@@SAJ_NPEAXPEAUISusHandlerNotification@@PEBU_GUID@@PEBUtagDSGlobalUpdateId@@PEB_WPEAPEAV1@@Z; CAppxDeploymentOperation::CreateInstance(bool,void *,ISusHandlerNotification *,_GUID const *,tagDSGlobalUpdateId const *,wchar_t const *,CAppxDeploymentOperation * *)
0x18020a13a  mov     ebx, eax
0x18020a13c  test    eax, eax
0x18020a13e  js      loc_180209EA5
0x18020a144  mov     rdx, [r14+20h]
0x18020a148  add     rdx, 4; struct _GUID *
0x18020a14c  mov     r8, [rsp+1D0h+var_190]; struct CAppxDeploymentOperation *
0x18020a151  mov     rcx, [rsp+1D0h+var_168]; this
0x18020a156  call    ?AddDeploymentOperation@CUHAppXHandler@@IEAAJAEBU_GUID@@PEAVCAppxDeploymentOperation@@@Z; CUHAppXHandler::AddDeploymentOperation(_GUID const &,CAppxDeploymentOperation *)
0x18020a15b  mov     ebx, eax
0x18020a15d  test    eax, eax
0x18020a15f  js      loc_180209EA5
0x18020a165  lea     rax, aTrue_9; "True"
0x18020a16c  lea     rbx, aFalse_7; "False"
0x18020a173  cmp     [r14+7Ch], esi
0x18020a177  cmovnz  rbx, rax
0x18020a17b  mov     rdx, [r14+20h]
0x18020a17f  add     rdx, 4; struct _GUID *
0x18020a183  lea     rcx, [rbp+0D0h+var_140]; this
0x18020a187  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18020a18c  mov     [rsp+1D0h+var_198], rbx
0x18020a191  mov     [rsp+1D0h+var_1A0], rax
0x18020a196  lea     rax, aStagingPackage; "Staging package for update %ws [Require"...
0x18020a19d  mov     [rsp+1D0h+var_1A8], rax
0x18020a1a2  mov     [rsp+1D0h+var_1B0], rsi
0x18020a1a7  xor     edx, edx
0x18020a1a9  xor     ecx, ecx
0x18020a1ab  lea     r9d, [rdx+4]
0x18020a1af  mov     r8d, 1000h
0x18020a1b5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020a1ba  test    r13, r13
0x18020a1bd  jnz     short loc_18020A1C4
0x18020a1bf  mov     r9, rsi
0x18020a1c2  jmp     short loc_18020A20A
0x18020a1c4  inc     rdi
0x18020a1c7  cmp     [r13+rdi*2+0], si
0x18020a1cd  jnz     short loc_18020A1C4
0x18020a1cf  mov     eax, 0FFFFFFFFh
0x18020a1d4  cmp     rdi, rax
0x18020a1d7  jbe     short loc_18020A1F0
0x18020a1d9  mov     edi, eax
0x18020a1db  xor     r9d, r9d; lpArguments
0x18020a1de  xor     r8d, r8d; nNumberOfArguments
0x18020a1e1  lea     edx, [r9+1]; dwExceptionFlags
0x18020a1e5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18020a1ea  call    cs:__imp_RaiseException
0x18020a1f0  lea     r9, [rsp+1D0h+string]; string
0x18020a1f5  lea     r8, [rsp+1D0h+var_158]; hstringHeader
0x18020a1fa  mov     edx, edi; length
0x18020a1fc  mov     rcx, r13; sourceString
0x18020a1ff  call    cs:__imp_WindowsCreateStringReference
0x18020a205  mov     r9, [rsp+1D0h+string]; HSTRING
0x18020a20a  mov     eax, [rsp+1D0h+var_188]
0x18020a20e  mov     dword ptr [rsp+1D0h+var_1A0], eax; unsigned int
0x18020a212  mov     rax, [r14+48h]
0x18020a216  mov     [rsp+1D0h+var_1A8], rax; char *
0x18020a21b  mov     rax, [r14+88h]
0x18020a222  mov     [rsp+1D0h+var_1B0], rax; wchar_t *
0x18020a227  lea     r8, [rbp+0D0h+var_B0]; wchar_t *
0x18020a22b  mov     rdx, [rbp+0D0h+var_F0]; struct ABI::Windows::Foundation::IUriRuntimeClass *
0x18020a22f  mov     rcx, [rsp+1D0h+var_190]; this
0x18020a234  call    ?StagePackageAsync@CAppxDeploymentOperation@@QEAAJPEAUIUriRuntimeClass@Foundation@Windows@ABI@@PEB_WQEAUHSTRING__@@1PEBDK@Z; CAppxDeploymentOperation::StagePackageAsync(ABI::Windows::Foundation::IUriRuntimeClass *,wchar_t const *,HSTRING__ * const,wchar_t const *,char const *,ulong)
0x18020a239  mov     ebx, eax
0x18020a23b  test    eax, eax
0x18020a23d  js      loc_180209EA5
0x18020a243  mov     rax, [rsp+1D0h+var_190]
0x18020a248  mov     rcx, rsi
0x18020a24b  mov     [rsp+1D0h+var_190], rcx
0x18020a250  mov     [r15], rax
0x18020a253  jmp     loc_180209ED7
```
