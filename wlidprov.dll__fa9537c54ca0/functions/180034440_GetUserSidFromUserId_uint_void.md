# GetUserSidFromUserId(uint,void * *)

- ea: `0x180034440`
- end: `0x18003465d`
- name: `?GetUserSidFromUserId@@YAJIPEAPEAX@Z`
- size: `541`
- prototype: `int(unsigned int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032940`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x180021e84`
- `0x180028810`
- `0x180029b38`
- `0x18002ae68`
- `0x180034440`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800345e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800345e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800344b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800344b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800345ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800345ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetUserSidFromUserId(unsigned int a1, void **a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  const WCHAR *StringRawBuffer; // rax
  const char *v14; // r9
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 **); // [rsp+20h] [rbp-50h] BYREF
  __int64 *v17; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a2 = 0;
  v19 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  v4 = v21;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v19);
  LastError = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v16 = 0;
    v7 = v19;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v9 = v8(v7, a1, &v16);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v17 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      v10 = (**v16)(v16, &GUID_2a426936_3887_4e38_9b4b_6064463481b8, &v17);
      LastError = v10;
      if ( v10 >= 0 )
      {
        string = 0;
        v11 = *v17;
        string = 0;
        v12 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v11 + 56))(v17, &string);
        LastError = v12;
        if ( v12 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( ConvertStringSidToSidW(StringRawBuffer, a2) )
          {
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
            LastError = 0;
            goto LABEL_15;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x4B4,
                        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerim"
                                      "plementation.cpp",
                        v14);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4B3,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
            (const char *)(unsigned int)v12,
            (int)v16);
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B0,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
          (const char *)(unsigned int)v10,
          (int)v16);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4AE,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        (const char *)(unsigned int)v9,
        (int)v16);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v16);
  }
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  return LastError;
}

```

## disassembly

```asm
0x180034440  mov     [rsp-18h+arg_10], rbx
0x180034445  mov     [rsp-18h+arg_18], rsi
0x18003444a  push    rbp
0x18003444b  push    rdi
0x18003444c  push    r14
0x18003444e  mov     rbp, rsp
0x180034451  sub     rsp, 70h
0x180034455  mov     rax, cs:__security_cookie
0x18003445c  xor     rax, rsp
0x18003445f  mov     [rbp+var_10], rax
0x180034463  mov     rsi, rdx
0x180034466  mov     r14d, ecx
0x180034469  mov     qword ptr [rdx], 0
0x180034470  mov     [rbp+var_38], 0
0x180034478  mov     [rbp+var_18], 0
0x180034480  mov     r9d, 23h ; '#'; unsigned int
0x180034486  lea     r8d, [r9+1]; unsigned int
0x18003448a  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180034491  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180034495  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003449a  mov     rbx, [rbp+var_18]
0x18003449e  lea     rcx, [rbp+var_38]
0x1800344a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800344a7  lea     r8, [rbp+var_38]
0x1800344ab  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x1800344b2  mov     rcx, rbx
0x1800344b5  call    cs:__imp_RoGetActivationFactory
0x1800344bb  mov     ebx, eax
0x1800344bd  test    eax, eax
0x1800344bf  jns     short loc_1800344DE
0x1800344c1  mov     rcx, [rbp+18h]; this
0x1800344c5  mov     r9d, eax; char *
0x1800344c8  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800344cf  mov     edx, 4ABh; void *
0x1800344d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800344d9  jmp     loc_180034631
0x1800344de  mov     [rbp+var_50], 0
0x1800344e6  mov     rdi, [rbp+var_38]
0x1800344ea  mov     rax, [rdi]
0x1800344ed  mov     rbx, [rax+60h]
0x1800344f1  lea     rcx, [rbp+var_50]
0x1800344f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800344fa  lea     r8, [rbp+var_50]
0x1800344fe  mov     edx, r14d
0x180034501  mov     rcx, rdi
0x180034504  mov     rax, rbx
0x180034507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003450c  mov     ebx, eax
0x18003450e  test    eax, eax
0x180034510  jns     short loc_180034539
0x180034512  mov     rcx, [rbp+18h]; this
0x180034516  mov     r9d, eax; char *
0x180034519  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034520  mov     edx, 4AEh; void *
0x180034525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003452a  nop
0x18003452b  lea     rcx, [rbp+var_50]
0x18003452f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034534  jmp     loc_180034631
0x180034539  mov     [rbp+var_48], 0
0x180034541  lea     rcx, [rbp+var_48]
0x180034545  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003454a  nop
0x18003454b  mov     rcx, [rbp+var_50]
0x18003454f  mov     rax, [rcx]
0x180034552  lea     r8, [rbp+var_48]
0x180034556  lea     rdx, _GUID_2a426936_3887_4e38_9b4b_6064463481b8
0x18003455d  mov     rax, [rax]
0x180034560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034565  mov     ebx, eax
0x180034567  test    eax, eax
0x180034569  jns     short loc_18003458F
0x18003456b  mov     rcx, [rbp+18h]; this
0x18003456f  mov     r9d, eax; char *
0x180034572  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034579  mov     edx, 4B0h; void *
0x18003457e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034583  nop
0x180034584  lea     rcx, [rbp+var_48]
0x180034588  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003458d  jmp     short loc_18003452B
0x18003458f  mov     [rbp+string], 0
0x180034597  mov     rcx, [rbp+var_48]
0x18003459b  mov     rax, [rcx]
0x18003459e  mov     [rbp+string], 0
0x1800345a6  lea     rdx, [rbp+string]
0x1800345aa  mov     rax, [rax+38h]
0x1800345ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345b3  mov     ebx, eax
0x1800345b5  test    eax, eax
0x1800345b7  jns     short loc_1800345DD
0x1800345b9  mov     rcx, [rbp+18h]; this
0x1800345bd  mov     r9d, eax; char *
0x1800345c0  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800345c7  mov     edx, 4B3h; void *
0x1800345cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800345d1  nop
0x1800345d2  lea     rcx, [rbp+string]; this
0x1800345d6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800345db  jmp     short loc_180034584
0x1800345dd  xor     edx, edx; length
0x1800345df  mov     rcx, [rbp+string]; string
0x1800345e3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800345e9  mov     rcx, rax; StringSid
0x1800345ec  mov     rdx, rsi; Sid
0x1800345ef  call    cs:__imp_ConvertStringSidToSidW
0x1800345f5  test    eax, eax
0x1800345f7  jnz     short loc_180034612
0x1800345f9  mov     rcx, [rbp+18h]; this
0x1800345fd  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034604  mov     edx, 4B4h; void *
0x180034609  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003460e  mov     ebx, eax
0x180034610  jmp     short loc_1800345D2
0x180034612  lea     rcx, [rbp+string]; this
0x180034616  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003461b  nop
0x18003461c  lea     rcx, [rbp+var_48]
0x180034620  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034625  nop
0x180034626  lea     rcx, [rbp+var_50]
0x18003462a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003462f  xor     ebx, ebx
0x180034631  lea     rcx, [rbp+var_38]
0x180034635  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003463a  mov     eax, ebx
0x18003463c  mov     rcx, [rbp+var_10]
0x180034640  xor     rcx, rsp; StackCookie
0x180034643  call    __security_check_cookie
0x180034648  lea     r11, [rsp+70h+var_s0]
0x18003464d  mov     rbx, [r11+30h]
0x180034651  mov     rsi, [r11+38h]
0x180034655  mov     rsp, r11
0x180034658  pop     r14
0x18003465a  pop     rdi
0x18003465b  pop     rbp
0x18003465c  retn
```
