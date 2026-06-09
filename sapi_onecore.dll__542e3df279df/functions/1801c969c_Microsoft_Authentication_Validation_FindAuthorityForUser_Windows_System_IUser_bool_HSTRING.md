# Microsoft::Authentication::Validation::FindAuthorityForUser(Windows::System::IUser *,bool *,HSTRING__ * *)

- ea: `0x1801c969c`
- end: `0x1801c98b3`
- name: `?FindAuthorityForUser@Validation@Authentication@Microsoft@@SAJPEAUIUser@System@Windows@@PEA_NPEAPEAUHSTRING__@@@Z`
- size: `535`
- prototype: `static int(struct Windows::System::IUser *, bool *, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801ca044`

## callees

- `0x18001ce70`
- `0x180020be0`
- `0x180021944`
- `0x180026508`
- `0x180079e30`
- `0x1801c969c`
- `0x1801c9ab4`
- `0x1801c9e1c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c98ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c98ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801c97e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801c97e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801c97d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801c97d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c987e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c9833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c987e`

## string_xrefs

- `0x1801c981e`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Authentication::Validation::FindAuthorityForUser(
        struct Windows::System::IUser *a1,
        bool *a2,
        HSTRING *a3)
{
  int ProviderForUser; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v9; // rbx
  __int64 (__fastcall *v10)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rdi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  HRESULT v13; // eax
  int v15; // [rsp+20h] [rbp-49h] BYREF
  HSTRING string; // [rsp+28h] [rbp-41h] BYREF
  INT32 result; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v19; // [rsp+40h] [rbp-29h] BYREF
  HSTRING_HEADER v20; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v21; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string2; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  string2 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"organizations", 0xEu, 0xDu);
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v20, L"https://login.windows.local", 0x1Cu, 0x1Bu);
  v19 = 0;
  v18 = 0;
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ProviderForUser = Microsoft::Authentication::Validation::FindProviderForUser(a1, v21, 0, &v19);
  v7 = ProviderForUser;
  if ( ProviderForUser < 0 )
  {
    v8 = 47;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
      (const char *)(unsigned int)ProviderForUser,
      v15);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return v7;
  }
  v9 = v19;
  if ( v19 )
  {
    v10 = **(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v19;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    ProviderForUser = v10(v9, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v18);
    v7 = ProviderForUser;
    if ( ProviderForUser < 0 )
    {
      v8 = 50;
      goto LABEL_16;
    }
    v11 = v18;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    ProviderForUser = v12(v11, &string);
    v7 = ProviderForUser;
    if ( ProviderForUser < 0 )
    {
      v8 = 51;
      goto LABEL_16;
    }
  }
  else
  {
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, 0, 0);
  }
  if ( a3 )
    WindowsDuplicateString(string, a3);
  result = 0;
  v13 = WindowsCompareStringOrdinal(string, string2, &result);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    JUMPOUT(0x1801C98B2LL);
  }
  if ( result )
    *a2 = 1;
  LOBYTE(v15) = 0;
  ProviderForUser = Microsoft::Authentication::Validation::FindLinkedAccountsForUser(a1, (bool *)&v15);
  v7 = ProviderForUser;
  if ( ProviderForUser < 0 )
  {
    v8 = 72;
    goto LABEL_16;
  }
  if ( (_BYTE)v15 )
    *a2 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return 0;
}

```

## disassembly

```asm
0x1801c969c  push    rbp
0x1801c969e  push    rbx
0x1801c969f  push    rsi
0x1801c96a0  push    rdi
0x1801c96a1  push    r12
0x1801c96a3  push    r14
0x1801c96a5  push    r15
0x1801c96a7  lea     rbp, [rsp-27h]
0x1801c96ac  sub     rsp, 90h
0x1801c96b3  mov     rax, cs:__security_cookie
0x1801c96ba  xor     rax, rsp
0x1801c96bd  mov     [rbp+57h+var_38], rax
0x1801c96c1  mov     r14, r8
0x1801c96c4  mov     rsi, rdx
0x1801c96c7  mov     r15, rcx
0x1801c96ca  xor     r12d, r12d
0x1801c96cd  mov     [rdx], r12b
0x1801c96d0  mov     [rbp+57h+string2], r12
0x1801c96d4  lea     r9d, [r12+0Dh]; unsigned int
0x1801c96d9  lea     r8d, [r12+0Eh]; unsigned int
0x1801c96de  lea     rdx, aOrganizations; "organizations"
0x1801c96e5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801c96e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801c96ee  nop
0x1801c96ef  mov     [rbp+57h+var_60], r12
0x1801c96f3  lea     r9d, [r12+1Bh]; unsigned int
0x1801c96f8  lea     r8d, [r12+1Ch]; unsigned int
0x1801c96fd  lea     rdx, aHttpsLoginWind; "https://login.windows.local"
0x1801c9704  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x1801c9708  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801c970d  nop
0x1801c970e  mov     [rbp+57h+var_80], r12
0x1801c9712  mov     [rbp+57h+var_88], r12
0x1801c9716  mov     [rbp+57h+string], r12
0x1801c971a  lea     rcx, [rbp+57h+var_80]
0x1801c971e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c9723  lea     r9, [rbp+57h+var_80]; struct Windows::Security::Credentials::IWebAccountProvider **
0x1801c9727  xor     r8d, r8d; HSTRING
0x1801c972a  mov     rdx, [rbp+57h+var_60]; HSTRING
0x1801c972e  mov     rcx, r15; struct Windows::System::IUser *
0x1801c9731  call    ?FindProviderForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEAUHSTRING__@@1PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z; Microsoft::Authentication::Validation::FindProviderForUser(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)
0x1801c9736  mov     ebx, eax
0x1801c9738  test    eax, eax
0x1801c973a  jns     short loc_1801C9746
0x1801c973c  lea     edx, [r12+2Fh]
0x1801c9741  jmp     loc_1801C981B
0x1801c9746  mov     rbx, [rbp+57h+var_80]
0x1801c974a  test    rbx, rbx
0x1801c974d  jz      short loc_1801C97B9
0x1801c974f  mov     rax, [rbx]
0x1801c9752  mov     rdi, [rax]
0x1801c9755  lea     rcx, [rbp+57h+var_88]
0x1801c9759  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c975e  lea     r8, [rbp+57h+var_88]
0x1801c9762  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1801c9769  mov     rcx, rbx
0x1801c976c  mov     rax, rdi
0x1801c976f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9774  mov     ebx, eax
0x1801c9776  test    eax, eax
0x1801c9778  jns     short loc_1801C9784
0x1801c977a  mov     edx, 32h ; '2'
0x1801c977f  jmp     loc_1801C981B
0x1801c9784  mov     rdi, [rbp+57h+var_88]
0x1801c9788  mov     rax, [rdi]
0x1801c978b  mov     rbx, [rax+38h]
0x1801c978f  mov     rcx, [rbp+57h+string]; string
0x1801c9793  call    cs:__imp_WindowsDeleteString
0x1801c9799  mov     [rbp+57h+string], r12
0x1801c979d  lea     rdx, [rbp+57h+string]
0x1801c97a1  mov     rcx, rdi
0x1801c97a4  mov     rax, rbx
0x1801c97a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c97ac  mov     ebx, eax
0x1801c97ae  test    eax, eax
0x1801c97b0  jns     short loc_1801C97C7
0x1801c97b2  mov     edx, 33h ; '3'
0x1801c97b7  jmp     short loc_1801C981B
0x1801c97b9  xor     r8d, r8d; unsigned int
0x1801c97bc  xor     edx, edx; unsigned __int16 *
0x1801c97be  lea     rcx, [rbp+57h+string]; this
0x1801c97c2  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801c97c7  test    r14, r14
0x1801c97ca  jz      short loc_1801C97D9
0x1801c97cc  mov     rdx, r14; newString
0x1801c97cf  mov     rcx, [rbp+57h+string]; string
0x1801c97d3  call    cs:__imp_WindowsDuplicateString
0x1801c97d9  mov     [rbp+57h+result], r12d
0x1801c97dd  lea     r8, [rbp+57h+result]; result
0x1801c97e1  mov     rdx, [rbp+57h+string2]; string2
0x1801c97e5  mov     rcx, [rbp+57h+string]; string1
0x1801c97e9  call    cs:__imp_WindowsCompareStringOrdinal
0x1801c97ef  test    eax, eax
0x1801c97f1  js      loc_1801C98A0
0x1801c97f7  cmp     [rbp+57h+result], r12d
0x1801c97fb  jz      short loc_1801C9800
0x1801c97fd  mov     byte ptr [rsi], 1
0x1801c9800  mov     byte ptr [rbp+57h+var_A0], r12b
0x1801c9804  lea     rdx, [rbp+57h+var_A0]; bool *
0x1801c9808  mov     rcx, r15; struct Windows::System::IUser *
0x1801c980b  call    ?FindLinkedAccountsForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEA_N@Z; Microsoft::Authentication::Validation::FindLinkedAccountsForUser(Windows::System::IUser *,bool *)
0x1801c9810  mov     ebx, eax
0x1801c9812  test    eax, eax
0x1801c9814  jns     short loc_1801C9871
0x1801c9816  mov     edx, 48h ; 'H'; void *
0x1801c981b  mov     r9d, eax; char *
0x1801c981e  lea     r8, aOnecoreuapEndu_212; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x1801c9825  mov     rcx, [rbp+5Fh]; this
0x1801c9829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c982e  nop
0x1801c982f  mov     rcx, [rbp+57h+string]; string
0x1801c9833  call    cs:__imp_WindowsDeleteString
0x1801c9839  mov     [rbp+57h+string], r12
0x1801c983d  lea     rcx, [rbp+57h+var_88]
0x1801c9841  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c9846  nop
0x1801c9847  lea     rcx, [rbp+57h+var_80]
0x1801c984b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c9850  nop
0x1801c9851  mov     eax, ebx
0x1801c9853  mov     rcx, [rbp+57h+var_38]
0x1801c9857  xor     rcx, rsp; StackCookie
0x1801c985a  call    __security_check_cookie
0x1801c985f  add     rsp, 90h
0x1801c9866  pop     r15
0x1801c9868  pop     r14
0x1801c986a  pop     r12
0x1801c986c  pop     rdi
0x1801c986d  pop     rsi
0x1801c986e  pop     rbx
0x1801c986f  pop     rbp
0x1801c9870  retn
0x1801c9871  cmp     byte ptr [rbp+57h+var_A0], r12b
0x1801c9875  jz      short loc_1801C987A
0x1801c9877  mov     [rsi], r12b
0x1801c987a  mov     rcx, [rbp+57h+string]; string
0x1801c987e  call    cs:__imp_WindowsDeleteString
0x1801c9884  mov     [rbp+57h+string], r12
0x1801c9888  lea     rcx, [rbp+57h+var_88]
0x1801c988c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c9891  nop
0x1801c9892  lea     rcx, [rbp+57h+var_80]
0x1801c9896  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c989b  nop
0x1801c989c  xor     eax, eax
0x1801c989e  jmp     short loc_1801C9853
0x1801c98a0  xor     r9d, r9d; lpArguments
0x1801c98a3  xor     r8d, r8d; nNumberOfArguments
0x1801c98a6  lea     edx, [r9+1]; dwExceptionFlags
0x1801c98aa  mov     ecx, eax; dwExceptionCode
0x1801c98ac  call    cs:__imp_RaiseException
```
