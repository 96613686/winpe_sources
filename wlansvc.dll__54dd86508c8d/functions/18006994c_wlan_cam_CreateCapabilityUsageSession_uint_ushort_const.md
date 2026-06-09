# wlan::cam::CreateCapabilityUsageSession(uint,ushort const *)

- ea: `0x18006994c`
- end: `0x180069b84`
- name: `?CreateCapabilityUsageSession@cam@wlan@@YAXIPEBG@Z`
- size: `568`
- prototype: `void __fastcall(wlan::cam *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800698bc`
- `0x1800959c0`

## callees

- `0x18006994c`
- `0x1800b2a88`
- `0x180106340`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069b65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069b78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069b65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069b78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800699d3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800699d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069a16`

## string_xrefs

- `0x18006998a`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`
- `0x180069b1d`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x180069b32`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`
- `0x180069b47`: `onecoreuap\net\wlan\commoncpp\src\camhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
void __fastcall wlan::cam::CreateCapabilityUsageSession(wlan::cam *this, __int64 a2, const unsigned __int16 *a3)
{
  unsigned int v3; // esi
  HRESULT v4; // eax
  int ActivationFactory; // eax
  _QWORD *v6; // rbx
  __int64 v7; // rdi
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  int v14; // [rsp+20h] [rbp-58h]
  _QWORD *v15; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = (unsigned int)this;
  v15 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
         0x3Cu,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
LABEL_16:
    RaiseException(v8, 1u, 0, 0);
    return;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_42947746_4ea0_48c2_9274_062ed61f8daa, &v15);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v14);
  v17 = 0;
  v6 = v15;
  v7 = *v15;
  string = 0;
  v8 = WindowsCreateStringReference(L"location", 8u, &hstringHeader, &string);
  if ( v8 < 0 )
    goto LABEL_16;
  v9 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v7 + 48))(v6, string, &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
      (const char *)(unsigned int)v9,
      v14);
  v16 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v17 + 48LL))(v17, v3, 0, &v16);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\net\\wlan\\commoncpp\\src\\camhelpers.cpp",
      (const char *)(unsigned int)v10,
      v14);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 48LL))(v16);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 56LL))(v16);
  v11 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  }
}

```

## disassembly

```asm
0x18006994c  mov     r11, rsp
0x18006994f  mov     [r11+10h], rbx
0x180069953  mov     [r11+18h], rsi
0x180069957  push    rdi
0x180069958  sub     rsp, 70h
0x18006995c  mov     rax, cs:__security_cookie
0x180069963  xor     rax, rsp
0x180069966  mov     [rsp+78h+var_10], rax
0x18006996b  mov     esi, ecx
0x18006996d  mov     qword ptr [r11-48h], 0
0x180069975  mov     qword ptr [r11-18h], 0
0x18006997d  lea     r9, [r11-18h]; string
0x180069981  lea     r8, [r11-30h]; hstringHeader
0x180069985  mov     edx, 3Ch ; '<'; length
0x18006998a  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180069991  call    cs:__imp_WindowsCreateStringReference
0x180069997  test    eax, eax
0x180069999  js      loc_180069B59
0x18006999f  mov     rbx, [rsp+78h+string]
0x1800699a4  mov     rcx, [rsp+78h+var_48]
0x1800699a9  test    rcx, rcx
0x1800699ac  jz      short loc_1800699C4
0x1800699ae  mov     [rsp+78h+var_48], 0
0x1800699b7  mov     rax, [rcx]
0x1800699ba  mov     rax, [rax+10h]
0x1800699be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699c3  nop
0x1800699c4  lea     r8, [rsp+78h+var_48]
0x1800699c9  lea     rdx, _GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x1800699d0  mov     rcx, rbx
0x1800699d3  call    cs:__imp_RoGetActivationFactory
0x1800699d9  mov     rcx, [rsp+78h]; this
0x1800699de  test    eax, eax
0x1800699e0  js      loc_180069B1A
0x1800699e6  mov     [rsp+78h+var_38], 0
0x1800699ef  mov     rbx, [rsp+78h+var_48]
0x1800699f4  mov     rdi, [rbx]
0x1800699f7  mov     [rsp+78h+string], 0
0x180069a00  lea     r9, [rsp+78h+string]; string
0x180069a05  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x180069a0a  mov     edx, 8; length
0x180069a0f  lea     rcx, sourceString; "location"
0x180069a16  call    cs:__imp_WindowsCreateStringReference
0x180069a1c  test    eax, eax
0x180069a1e  js      loc_180069B6C
0x180069a24  lea     r8, [rsp+78h+var_38]
0x180069a29  mov     rdx, [rsp+78h+string]
0x180069a2e  mov     rcx, rbx
0x180069a31  mov     rax, [rdi+30h]
0x180069a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a3a  mov     rcx, [rsp+78h]; this
0x180069a3f  test    eax, eax
0x180069a41  js      loc_180069B2F
0x180069a47  mov     [rsp+78h+var_40], 0
0x180069a50  mov     rcx, [rsp+78h+var_38]
0x180069a55  mov     rax, [rcx]
0x180069a58  lea     r9, [rsp+78h+var_40]
0x180069a5d  xor     r8d, r8d
0x180069a60  mov     edx, esi
0x180069a62  mov     rax, [rax+30h]
0x180069a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a6b  mov     rcx, [rsp+78h]; this
0x180069a70  test    eax, eax
0x180069a72  js      loc_180069B44
0x180069a78  mov     rcx, [rsp+78h+var_40]
0x180069a7d  mov     rax, [rcx]
0x180069a80  mov     rax, [rax+30h]
0x180069a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a89  mov     rcx, [rsp+78h+var_40]
0x180069a8e  mov     rax, [rcx]
0x180069a91  mov     rax, [rax+38h]
0x180069a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a9a  nop
0x180069a9b  mov     rcx, [rsp+78h+var_40]
0x180069aa0  test    rcx, rcx
0x180069aa3  jz      short loc_180069ABB
0x180069aa5  mov     [rsp+78h+var_40], 0
0x180069aae  mov     rax, [rcx]
0x180069ab1  mov     rax, [rax+10h]
0x180069ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069aba  nop
0x180069abb  mov     rcx, [rsp+78h+var_38]
0x180069ac0  test    rcx, rcx
0x180069ac3  jz      short loc_180069ADB
0x180069ac5  mov     [rsp+78h+var_38], 0
0x180069ace  mov     rax, [rcx]
0x180069ad1  mov     rax, [rax+10h]
0x180069ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ada  nop
0x180069adb  mov     rcx, [rsp+78h+var_48]
0x180069ae0  test    rcx, rcx
0x180069ae3  jz      short loc_180069AFB
0x180069ae5  mov     [rsp+78h+var_48], 0
0x180069aee  mov     rax, [rcx]
0x180069af1  mov     rax, [rax+10h]
0x180069af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069afa  nop
0x180069afb  mov     rcx, [rsp+78h+var_10]
0x180069b00  xor     rcx, rsp; StackCookie
0x180069b03  call    __security_check_cookie
0x180069b08  lea     r11, [rsp+78h+var_8]
0x180069b0d  mov     rbx, [r11+18h]
0x180069b11  mov     rsi, [r11+20h]
0x180069b15  mov     rsp, r11
0x180069b18  pop     rdi
0x180069b19  retn
0x180069b1a  mov     r9d, eax; char *
0x180069b1d  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x180069b24  mov     edx, 39h ; '9'; void *
0x180069b29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069b2f  mov     r9d, eax; char *
0x180069b32  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x180069b39  mov     edx, 3Bh ; ';'; void *
0x180069b3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069b44  mov     r9d, eax; char *
0x180069b47  lea     r8, aOnecoreuapNetW_62; "onecoreuap\\net\\wlan\\commoncpp\\src\\"...
0x180069b4e  mov     edx, 3Dh ; '='; void *
0x180069b53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069b59  xor     r9d, r9d; lpArguments
0x180069b5c  xor     r8d, r8d; nNumberOfArguments
0x180069b5f  lea     edx, [r9+1]; dwExceptionFlags
0x180069b63  mov     ecx, eax; dwExceptionCode
0x180069b65  call    cs:__imp_RaiseException
0x180069b6b  nop
0x180069b6c  xor     r9d, r9d; lpArguments
0x180069b6f  xor     r8d, r8d; nNumberOfArguments
0x180069b72  lea     edx, [r9+1]; dwExceptionFlags
0x180069b76  mov     ecx, eax; dwExceptionCode
0x180069b78  call    cs:__imp_RaiseException
0x180069b7e  nop
0x180069b7f  jmp     loc_180069AFB
```
