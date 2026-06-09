# Windows::System::Internal::Launch::StoreLauncher::ShowProductResultsForStorageFile(Windows::Storage::IStorageFile *)

- ea: `0x1800ce9c0`
- end: `0x1800ceb8b`
- name: `?ShowProductResultsForStorageFile@StoreLauncher@Launch@Internal@System@Windows@@UEAAJPEAUIStorageFile@Storage@5@@Z`
- size: `459`
- prototype: `__int64 __fastcall(Windows::System::Internal::Launch::StoreLauncher *__hidden this, struct Windows::Storage::IStorageFile *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x1800329a0`
- `0x1800343c0`
- `0x1800ce9c0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800cea9a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800cea9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ceb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ceb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cea91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cea91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cea61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cea61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ceb76`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StoreLauncher::ShowProductResultsForStorageFile(
        Windows::System::Internal::Launch::StoreLauncher *this,
        struct Windows::Storage::IStorageFile *a2)
{
  __int64 (__fastcall **v2)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v5)(struct Windows::Storage::IStorageFile *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall **v8)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v9)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v15; // rdx
  LPWSTR v17[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+58h] [rbp+28h] BYREF
  HSTRING v20; // [rsp+60h] [rbp+30h] BYREF
  __int64 v21; // [rsp+68h] [rbp+38h] BYREF

  v2 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  v20 = 0;
  v5 = (__int64 (__fastcall *)(struct Windows::Storage::IStorageFile *, HSTRING *))v2[6];
  WindowsDeleteString(0);
  v20 = 0;
  v6 = v5(a2, &v20);
  v7 = v6;
  if ( v6 != -2147467263 )
  {
    if ( v6 < 0 )
    {
      v15 = 96;
      goto LABEL_17;
    }
LABEL_10:
    if ( WindowsIsStringEmpty(v20)
      && (v6 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v20, L".", 1u),
          v7 = v6,
          v6 < 0) )
    {
      v15 = 101;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(Windows::System::Internal::Launch::StoreLauncher *, HSTRING, _QWORD))(*(_QWORD *)this + 56LL))(
             this,
             v20,
             0);
      v7 = v6;
      if ( v6 >= 0 )
        goto LABEL_18;
      v15 = 104;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\storelauncher.cpp",
      (const char *)(unsigned int)v6,
      (int)v17[0]);
    goto LABEL_18;
  }
  v8 = *(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *))a2;
  string = 0;
  v21 = 0;
  v9 = *v8;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v10 = v9(a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v21);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v12 = v21;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 96LL);
    WindowsDeleteString(string);
    string = 0;
    v10 = v13(v12, &string);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = 92;
      goto LABEL_8;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v17[0] = PathFindExtensionW(StringRawBuffer);
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v20, v17);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = 93;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    WindowsDeleteString(string);
    goto LABEL_10;
  }
  v11 = 91;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\storelauncher.cpp",
    (const char *)(unsigned int)v10,
    (int)v17[0]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  WindowsDeleteString(string);
  string = 0;
LABEL_18:
  WindowsDeleteString(v20);
  return v7;
}

```

## disassembly

```asm
0x1800ce9c0  mov     [rsp-18h+arg_0], rbx
0x1800ce9c5  push    rbp
0x1800ce9c6  push    rsi
0x1800ce9c7  push    rdi
0x1800ce9c8  mov     rbp, rsp
0x1800ce9cb  sub     rsp, 30h
0x1800ce9cf  mov     rax, [rdx]
0x1800ce9d2  mov     rsi, rcx
0x1800ce9d5  xor     ecx, ecx; string
0x1800ce9d7  mov     [rbp+arg_10], 0
0x1800ce9df  mov     rdi, rdx
0x1800ce9e2  mov     rbx, [rax+30h]
0x1800ce9e6  call    cs:__imp_WindowsDeleteString
0x1800ce9ec  lea     rdx, [rbp+arg_10]
0x1800ce9f0  mov     [rbp+arg_10], 0
0x1800ce9f8  mov     rcx, rdi
0x1800ce9fb  mov     rax, rbx
0x1800ce9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea03  mov     ebx, eax
0x1800cea05  cmp     eax, 80004001h
0x1800cea0a  jnz     loc_1800CEB33
0x1800cea10  mov     rax, [rdi]
0x1800cea13  lea     rcx, [rbp+arg_18]
0x1800cea17  mov     [rbp+string], 0
0x1800cea1f  mov     [rbp+arg_18], 0
0x1800cea27  mov     rbx, [rax]
0x1800cea2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cea2f  lea     r8, [rbp+arg_18]
0x1800cea33  mov     rcx, rdi
0x1800cea36  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800cea3d  mov     rax, rbx
0x1800cea40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea45  mov     ebx, eax
0x1800cea47  test    eax, eax
0x1800cea49  jns     short loc_1800CEA52
0x1800cea4b  mov     edx, 5Bh ; '['
0x1800cea50  jmp     short loc_1800CEABC
0x1800cea52  mov     rdi, [rbp+arg_18]
0x1800cea56  mov     rcx, [rbp+string]; string
0x1800cea5a  mov     rax, [rdi]
0x1800cea5d  mov     rbx, [rax+60h]
0x1800cea61  call    cs:__imp_WindowsDeleteString
0x1800cea67  lea     rdx, [rbp+string]
0x1800cea6b  mov     [rbp+string], 0
0x1800cea73  mov     rcx, rdi
0x1800cea76  mov     rax, rbx
0x1800cea79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea7e  mov     ebx, eax
0x1800cea80  test    eax, eax
0x1800cea82  jns     short loc_1800CEA8B
0x1800cea84  mov     edx, 5Ch ; '\'
0x1800cea89  jmp     short loc_1800CEABC
0x1800cea8b  mov     rcx, [rbp+string]; string
0x1800cea8f  xor     edx, edx; length
0x1800cea91  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cea97  mov     rcx, rax; pszPath
0x1800cea9a  call    cs:__imp_PathFindExtensionW
0x1800ceaa0  lea     rdx, [rbp+var_10]
0x1800ceaa4  mov     [rbp+var_10], rax
0x1800ceaa8  lea     rcx, [rbp+arg_10]
0x1800ceaac  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ceab1  mov     ebx, eax
0x1800ceab3  test    eax, eax
0x1800ceab5  jns     short loc_1800CEAEF
0x1800ceab7  mov     edx, 5Dh ; ']'; void *
0x1800ceabc  mov     rcx, [rbp+18h]; this
0x1800ceac0  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\windows.system.launc"...
0x1800ceac7  mov     r9d, eax; char *
0x1800ceaca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ceacf  lea     rcx, [rbp+arg_18]
0x1800cead3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cead8  mov     rcx, [rbp+string]; string
0x1800ceadc  call    cs:__imp_WindowsDeleteString
0x1800ceae2  mov     [rbp+string], 0
0x1800ceaea  jmp     loc_1800CEB72
0x1800ceaef  lea     rcx, [rbp+arg_18]
0x1800ceaf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ceaf8  mov     rcx, [rbp+string]; string
0x1800ceafc  call    cs:__imp_WindowsDeleteString
0x1800ceb02  mov     rcx, [rbp+arg_10]; string
0x1800ceb06  call    cs:__imp_WindowsIsStringEmpty
0x1800ceb0c  test    eax, eax
0x1800ceb0e  jz      short loc_1800CEB3E
0x1800ceb10  mov     r8d, 1; unsigned int
0x1800ceb16  lea     rdx, asc_18012B798; "."
0x1800ceb1d  lea     rcx, [rbp+arg_10]; this
0x1800ceb21  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800ceb26  mov     ebx, eax
0x1800ceb28  test    eax, eax
0x1800ceb2a  jns     short loc_1800CEB3E
0x1800ceb2c  mov     edx, 65h ; 'e'
0x1800ceb31  jmp     short loc_1800CEB5F
0x1800ceb33  test    eax, eax
0x1800ceb35  jns     short loc_1800CEB02
0x1800ceb37  mov     edx, 60h ; '`'
0x1800ceb3c  jmp     short loc_1800CEB5F
0x1800ceb3e  mov     rax, [rsi]
0x1800ceb41  xor     r8d, r8d
0x1800ceb44  mov     rdx, [rbp+arg_10]
0x1800ceb48  mov     rcx, rsi
0x1800ceb4b  mov     rax, [rax+38h]
0x1800ceb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb54  mov     ebx, eax
0x1800ceb56  test    eax, eax
0x1800ceb58  jns     short loc_1800CEB72
0x1800ceb5a  mov     edx, 68h ; 'h'; void *
0x1800ceb5f  mov     rcx, [rbp+18h]; this
0x1800ceb63  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\windows.system.launc"...
0x1800ceb6a  mov     r9d, eax; char *
0x1800ceb6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ceb72  mov     rcx, [rbp+arg_10]; string
0x1800ceb76  call    cs:__imp_WindowsDeleteString
0x1800ceb7c  mov     eax, ebx
0x1800ceb7e  mov     rbx, [rsp+30h+arg_0]
0x1800ceb83  add     rsp, 30h
0x1800ceb87  pop     rdi
0x1800ceb88  pop     rsi
0x1800ceb89  pop     rbp
0x1800ceb8a  retn
```
