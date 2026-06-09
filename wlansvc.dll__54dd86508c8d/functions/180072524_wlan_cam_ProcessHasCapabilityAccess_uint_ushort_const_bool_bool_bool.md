# wlan::cam::ProcessHasCapabilityAccess(uint,ushort const *,bool,bool,bool)

- ea: `0x180072524`
- end: `0x1800727cc`
- name: `?ProcessHasCapabilityAccess@cam@wlan@@YA_NIPEBG_N11@Z`
- size: `680`
- prototype: `bool(wlan::cam *__hidden this, unsigned int, const unsigned __int16 *, bool, bool, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007223c`
- `0x180072450`
- `0x1800daefc`

## callees

- `0x180072524`
- `0x1800727d4`
- `0x180072800`
- `0x1800b2a88`
- `0x180106340`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007258b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007264b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800727c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007258b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007264b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800727c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800725b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800725b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072634`

## string_xrefs

- `0x1800725c5`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x180072685`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x1800726be`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x1800726f6`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x18007272f`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x18007256f`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall wlan::cam::ProcessHasCapabilityAccess(
        wlan::cam *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        char a4,
        bool a5)
{
  char v6; // r14
  unsigned int v8; // r12d
  HRESULT v9; // eax
  HSTRING v10; // rbx
  int ActivationFactory; // eax
  _QWORD *v12; // rdi
  __int64 v13; // r13
  unsigned __int64 v14; // rbx
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const char *v23; // r9
  bool v24; // bl
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  bool result; // al
  int v28; // [rsp+20h] [rbp-88h]
  __int64 v29; // [rsp+40h] [rbp-68h] BYREF
  int v30; // [rsp+48h] [rbp-60h] BYREF
  _QWORD *v31; // [rsp+50h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-50h] BYREF
  HSTRING string; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = (char)a3;
  v8 = (unsigned int)this;
  v31 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string);
  if ( v9 < 0 )
    RaiseException(v9, 1u, 0, 0);
  v10 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v31);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v28);
    v29 = 0;
    v30 = 3;
    v12 = v31;
    v13 = *v31;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    string = 0;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    if ( v14 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
    }
    else
    {
      v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
      v16 = v15 - 1;
      if ( (unsigned int)v14 >= v15 )
      {
LABEL_11:
        v17 = WindowsCreateStringReference(a2, v16, &hstringHeader, &string);
        if ( v17 < 0 )
          RaiseException(v17, 1u, 0, 0);
        v18 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, _QWORD))(v13 + 56))(v12, 0, string, v8);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1F,
            (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
            (const char *)(unsigned int)v18,
            0);
        if ( !v6 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 72LL))(v29, 0);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x23,
              (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
              (const char *)(unsigned int)v20,
              0);
        }
        if ( a4 )
        {
          LOBYTE(v19) = 1;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 88LL))(v29, v19);
          if ( v21 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x27,
              (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
              (const char *)(unsigned int)v21,
              0);
        }
        v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 152LL))(v29, &v30);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
            (const char *)(unsigned int)v22,
            0);
        v24 = v30 == 3;
        v25 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v26 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
        }
        return v24;
      }
    }
    v16 = v14;
    goto LABEL_11;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
      v23);
    return a5;
  }
  return result;
}

```

## disassembly

```asm
0x180072524  mov     r11, rsp
0x180072527  mov     [r11+18h], rbx
0x18007252b  mov     [r11+20h], rsi
0x18007252f  push    rdi
0x180072530  push    r12
0x180072532  push    r13
0x180072534  push    r14
0x180072536  push    r15
0x180072538  sub     rsp, 80h
0x18007253f  mov     rax, cs:__security_cookie
0x180072546  xor     rax, rsp
0x180072549  mov     [rsp+0A8h+var_30], rax
0x18007254e  mov     r15b, r9b
0x180072551  mov     r14b, r8b
0x180072554  mov     rsi, rdx
0x180072557  mov     r12d, ecx
0x18007255a  xor     edi, edi
0x18007255c  mov     [r11-58h], rdi
0x180072560  mov     [r11-38h], rdi
0x180072564  lea     r9, [r11-38h]; string
0x180072568  lea     r8, [r11-50h]; hstringHeader
0x18007256c  lea     edx, [rdi+32h]; length
0x18007256f  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x180072576  call    cs:__imp_WindowsCreateStringReference
0x18007257c  test    eax, eax
0x18007257e  jns     short loc_180072592
0x180072580  xor     r9d, r9d; lpArguments
0x180072583  xor     r8d, r8d; nNumberOfArguments
0x180072586  lea     edx, [rdi+1]; dwExceptionFlags
0x180072589  mov     ecx, eax; dwExceptionCode
0x18007258b  call    cs:__imp_RaiseException
0x180072591  nop
0x180072592  mov     rbx, [rsp+0A8h+string]
0x180072597  lea     rcx, [rsp+0A8h+var_58]
0x18007259c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800725a1  lea     r8, [rsp+0A8h+var_58]
0x1800725a6  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x1800725ad  mov     rcx, rbx
0x1800725b0  call    cs:__imp_RoGetActivationFactory
0x1800725b6  mov     rcx, [rsp+0A8h]; this
0x1800725be  test    eax, eax
0x1800725c0  jns     short loc_1800725D7
0x1800725c2  mov     r9d, eax; char *
0x1800725c5  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x1800725cc  mov     edx, 1Bh; void *
0x1800725d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800725d7  mov     [rsp+0A8h+var_68], rdi
0x1800725dc  mov     [rsp+0A8h+var_60], 3
0x1800725e4  mov     rdi, [rsp+0A8h+var_58]
0x1800725e9  mov     r13, [rdi]
0x1800725ec  lea     rcx, [rsp+0A8h+var_68]
0x1800725f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800725f6  xor     eax, eax
0x1800725f8  mov     [rsp+0A8h+string], rax
0x1800725fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180072601  inc     rbx
0x180072604  cmp     [rsi+rbx*2], ax
0x180072608  jnz     short loc_180072601
0x18007260a  mov     eax, 0FFFFFFFFh
0x18007260f  cmp     rbx, rax
0x180072612  ja      loc_1800727B5
0x180072618  mov     ecx, ebx; unsigned int
0x18007261a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007261f  lea     edx, [rax-1]
0x180072622  cmp     ebx, eax
0x180072624  cmovb   edx, ebx; length
0x180072627  lea     r9, [rsp+0A8h+string]; string
0x18007262c  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180072631  mov     rcx, rsi; sourceString
0x180072634  call    cs:__imp_WindowsCreateStringReference
0x18007263a  xor     esi, esi
0x18007263c  test    eax, eax
0x18007263e  jns     short loc_180072652
0x180072640  xor     r9d, r9d; lpArguments
0x180072643  xor     r8d, r8d; nNumberOfArguments
0x180072646  lea     edx, [rsi+1]; dwExceptionFlags
0x180072649  mov     ecx, eax; dwExceptionCode
0x18007264b  call    cs:__imp_RaiseException
0x180072651  nop
0x180072652  lea     rax, [rsp+0A8h+var_68]
0x180072657  mov     [rsp+0A8h+var_80], rax
0x18007265c  mov     [rsp+0A8h+var_88], esi; int
0x180072660  mov     r9d, r12d
0x180072663  mov     r8, [rsp+0A8h+string]
0x180072668  xor     edx, edx
0x18007266a  mov     rcx, rdi
0x18007266d  mov     rax, [r13+38h]
0x180072671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072676  mov     rcx, [rsp+0A8h]; this
0x18007267e  test    eax, eax
0x180072680  jns     short loc_180072697
0x180072682  mov     r9d, eax; char *
0x180072685  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x18007268c  mov     edx, 1Fh; void *
0x180072691  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072697  test    r14b, r14b
0x18007269a  jnz     short loc_1800726CF
0x18007269c  mov     rcx, [rsp+0A8h+var_68]
0x1800726a1  mov     rax, [rcx]
0x1800726a4  xor     edx, edx
0x1800726a6  mov     rax, [rax+48h]
0x1800726aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726af  mov     rcx, [rsp+0A8h]; this
0x1800726b7  test    eax, eax
0x1800726b9  jns     short loc_1800726CF
0x1800726bb  mov     r9d, eax; char *
0x1800726be  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x1800726c5  mov     edx, 23h ; '#'; void *
0x1800726ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800726cf  test    r15b, r15b
0x1800726d2  jz      short loc_180072707
0x1800726d4  mov     rcx, [rsp+0A8h+var_68]
0x1800726d9  mov     rax, [rcx]
0x1800726dc  mov     dl, 1
0x1800726de  mov     rax, [rax+58h]
0x1800726e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726e7  mov     rcx, [rsp+0A8h]; this
0x1800726ef  test    eax, eax
0x1800726f1  jns     short loc_180072707
0x1800726f3  mov     r9d, eax; char *
0x1800726f6  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x1800726fd  mov     edx, 27h ; '''; void *
0x180072702  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072707  mov     rcx, [rsp+0A8h+var_68]
0x18007270c  mov     rax, [rcx]
0x18007270f  lea     rdx, [rsp+0A8h+var_60]
0x180072714  mov     rax, [rax+98h]
0x18007271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072720  mov     rcx, [rsp+0A8h]; this
0x180072728  test    eax, eax
0x18007272a  jns     short loc_180072740
0x18007272c  mov     r9d, eax; char *
0x18007272f  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x180072736  mov     edx, 29h ; ')'; void *
0x18007273b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072740  cmp     [rsp+0A8h+var_60], 3
0x180072745  setz    bl
0x180072748  mov     rcx, [rsp+0A8h+var_68]
0x18007274d  test    rcx, rcx
0x180072750  jz      short loc_180072764
0x180072752  mov     [rsp+0A8h+var_68], rsi
0x180072757  mov     rax, [rcx]
0x18007275a  mov     rax, [rax+10h]
0x18007275e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072763  nop
0x180072764  mov     rcx, [rsp+0A8h+var_58]
0x180072769  test    rcx, rcx
0x18007276c  jz      short loc_180072780
0x18007276e  mov     [rsp+0A8h+var_58], rsi
0x180072773  mov     rdx, [rcx]
0x180072776  mov     rax, [rdx+10h]
0x18007277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007277f  nop
0x180072780  mov     al, bl
0x180072782  jmp     short loc_18007278B
0x180072784  mov     al, [rsp+0A8h+arg_20]
0x18007278b  mov     rcx, [rsp+0A8h+var_30]
0x180072790  xor     rcx, rsp; StackCookie
0x180072793  call    __security_check_cookie
0x180072798  lea     r11, [rsp+0A8h+var_28]
0x1800727a0  mov     rbx, [r11+40h]
0x1800727a4  mov     rsi, [r11+48h]
0x1800727a8  mov     rsp, r11
0x1800727ab  pop     r15
0x1800727ad  pop     r14
0x1800727af  pop     r13
0x1800727b1  pop     r12
0x1800727b3  pop     rdi
0x1800727b4  retn
0x1800727b5  xor     r9d, r9d; lpArguments
0x1800727b8  xor     r8d, r8d; nNumberOfArguments
0x1800727bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800727bf  mov     ecx, 80070216h; dwExceptionCode
0x1800727c4  call    cs:__imp_RaiseException
```
