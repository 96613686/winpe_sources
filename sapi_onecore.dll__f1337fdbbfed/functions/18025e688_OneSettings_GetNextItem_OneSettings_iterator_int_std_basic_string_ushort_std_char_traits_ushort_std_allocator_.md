# OneSettings::GetNextItem(OneSettings::iterator &,int *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18025e688`
- end: `0x18025ea24`
- name: `?GetNextItem@OneSettings@@QEAAJAEAUiterator@1@PEAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18025cddc`

## callees

- `0x180021944`
- `0x180026508`
- `0x18002d404`
- `0x180030404`
- `0x18025e688`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e8a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e8a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025e9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025e9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025e9c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025e9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025e9c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OneSettings::GetNextItem(__int64 a1, _QWORD **a2, BOOL *a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _WORD *v11; // rcx
  __int64 v12; // rsi
  _WORD *v13; // rcx
  BOOL v14; // r15d
  _QWORD *v15; // r13
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // rbx
  __int64 v32; // r8
  PCWSTR v33; // rax
  HSTRING string; // [rsp+20h] [rbp-71h] BYREF
  HSTRING v36; // [rsp+28h] [rbp-69h] BYREF
  __int64 v37; // [rsp+30h] [rbp-61h] BYREF
  __int64 v38; // [rsp+38h] [rbp-59h] BYREF
  _DWORD v39[4]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v40[144]; // [rsp+50h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]
  char v42; // [rsp+F0h] [rbp+5Fh] BYREF

  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(a1 + 216) + 112LL))(a1 + 216, v40);
  if ( *(_DWORD *)(a1 + 704) )
  {
    if ( !*a2 )
    {
      v10 = 523;
LABEL_5:
      v9 = -2147024809;
      goto LABEL_6;
    }
    if ( !a3 )
    {
      v10 = 524;
      goto LABEL_5;
    }
    *(_QWORD *)(a4 + 16) = 0;
    if ( *(_QWORD *)(a4 + 24) <= 7u )
      v11 = (_WORD *)a4;
    else
      v11 = *(_WORD **)a4;
    *v11 = 0;
    v12 = a5;
    *(_QWORD *)(a5 + 16) = 0;
    if ( *(_QWORD *)(v12 + 24) <= 7u )
      v13 = (_WORD *)v12;
    else
      v13 = *(_WORD **)v12;
    *v13 = 0;
    v14 = 1;
    *a3 = 1;
    v36 = 0;
    string = 0;
    v42 = 0;
    v15 = *a2;
    v16 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)**a2 + 56LL))(**a2, &v42);
    v9 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
        (const char *)(unsigned int)v16,
        (int)string);
LABEL_17:
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v36);
LABEL_42:
      v36 = 0;
      goto LABEL_43;
    }
    if ( v42 )
    {
      v37 = 0;
      v17 = *v15;
      v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v15 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      v19 = v18(v17, &v37);
      v9 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21B,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
          (const char *)(unsigned int)v19,
          (int)string);
LABEL_21:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        goto LABEL_17;
      }
      v38 = 0;
      v20 = v37;
      v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v22 = v21(v20, &v38);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 542;
LABEL_24:
        v24 = (unsigned int)v22;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
          (const char *)v24,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        goto LABEL_21;
      }
      v39[0] = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v38 + 48LL))(v38, v39);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 545;
        goto LABEL_24;
      }
      if ( v39[0] != 3 )
      {
        v9 = -2147418113;
        v24 = 2147549183LL;
        v23 = 546;
        goto LABEL_25;
      }
      v25 = v37;
      v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v27 = v26(v25, &string);
      v9 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x224,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
          (const char *)(unsigned int)v27,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v36);
        v36 = 0;
        goto LABEL_43;
      }
      v28 = v38;
      v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 64LL);
      WindowsDeleteString(v36);
      v36 = 0;
      v22 = v29(v28, &v36);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 549;
        goto LABEL_24;
      }
      v22 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v15 + 64LL))(*v15, &v42);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 550;
        goto LABEL_24;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      v14 = v42 == 0;
    }
    *a3 = v14;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v31 = -1;
    v32 = -1;
    do
      ++v32;
    while ( StringRawBuffer[v32] );
    std::wstring::_Assign<unsigned short>(a4, StringRawBuffer);
    v33 = WindowsGetStringRawBuffer(v36, 0);
    do
      ++v31;
    while ( v33[v31] );
    std::wstring::_Assign<unsigned short>(v12, v33);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v9 = 0;
    goto LABEL_42;
  }
  v9 = -2147019873;
  v10 = 522;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
    (const char *)v9,
    (int)string);
LABEL_43:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v40);
  return v9;
}

```

## disassembly

```asm
0x18025e688  push    rbp
0x18025e68a  push    rbx
0x18025e68b  push    rsi
0x18025e68c  push    rdi
0x18025e68d  push    r12
0x18025e68f  push    r13
0x18025e691  push    r14
0x18025e693  push    r15
0x18025e695  lea     rbp, [rsp-17h]
0x18025e69a  sub     rsp, 0A8h
0x18025e6a1  mov     r14, r9
0x18025e6a4  mov     r12, r8
0x18025e6a7  mov     rdi, rdx
0x18025e6aa  mov     rbx, rcx
0x18025e6ad  add     rcx, 0D8h
0x18025e6b4  mov     rax, [rcx]
0x18025e6b7  lea     rdx, [rbp+4Fh+var_90]
0x18025e6bb  mov     rax, [rax+70h]
0x18025e6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e6c4  nop
0x18025e6c5  xor     edx, edx
0x18025e6c7  cmp     [rbx+2C0h], edx
0x18025e6cd  jnz     short loc_18025E6DB
0x18025e6cf  mov     ebx, 8007139Fh
0x18025e6d4  mov     edx, 20Ah
0x18025e6d9  jmp     short loc_18025E6EA
0x18025e6db  cmp     [rdi], rdx
0x18025e6de  jnz     short loc_18025E702
0x18025e6e0  mov     edx, 20Bh; void *
0x18025e6e5  mov     ebx, 80070057h
0x18025e6ea  mov     rcx, [rbp+57h]; this
0x18025e6ee  mov     r9d, ebx; char *
0x18025e6f1  lea     r8, aOnecoreuapEndu_240; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18025e6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025e6fd  jmp     loc_18025EA05
0x18025e702  test    r12, r12
0x18025e705  jnz     short loc_18025E70E
0x18025e707  mov     edx, 20Ch
0x18025e70c  jmp     short loc_18025E6E5
0x18025e70e  mov     [r14+10h], rdx
0x18025e712  cmp     qword ptr [r14+18h], 7
0x18025e717  jbe     short loc_18025E71E
0x18025e719  mov     rcx, [r14]
0x18025e71c  jmp     short loc_18025E721
0x18025e71e  mov     rcx, r14
0x18025e721  mov     [rcx], dx
0x18025e724  mov     rsi, [rbp+4Fh+arg_20]
0x18025e728  mov     [rsi+10h], rdx
0x18025e72c  cmp     qword ptr [rsi+18h], 7
0x18025e731  jbe     short loc_18025E738
0x18025e733  mov     rcx, [rsi]
0x18025e736  jmp     short loc_18025E73B
0x18025e738  mov     rcx, rsi
0x18025e73b  mov     [rcx], dx
0x18025e73e  mov     r15d, 1
0x18025e744  mov     [r12], r15d
0x18025e748  mov     [rbp+4Fh+var_B8], rdx
0x18025e74c  mov     [rbp+4Fh+string], rdx
0x18025e750  mov     [rbp+4Fh+arg_0], dl
0x18025e753  mov     r13, [rdi]
0x18025e756  mov     rcx, [r13+0]
0x18025e75a  mov     rax, [rcx]
0x18025e75d  lea     rdx, [rbp+4Fh+arg_0]
0x18025e761  mov     rax, [rax+38h]
0x18025e765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e76a  mov     ebx, eax
0x18025e76c  xor     edi, edi
0x18025e76e  test    eax, eax
0x18025e770  jns     short loc_18025E7A8
0x18025e772  mov     rcx, [rbp+57h]; this
0x18025e776  mov     r9d, eax; char *
0x18025e779  lea     r8, aOnecoreuapEndu_240; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18025e780  mov     edx, 216h; void *
0x18025e785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025e78a  nop
0x18025e78b  mov     rcx, [rbp+4Fh+string]; string
0x18025e78f  call    cs:__imp_WindowsDeleteString
0x18025e795  mov     [rbp+4Fh+string], rdi
0x18025e799  mov     rcx, [rbp+4Fh+var_B8]; string
0x18025e79d  call    cs:__imp_WindowsDeleteString
0x18025e7a3  jmp     loc_18025EA01
0x18025e7a8  cmp     [rbp+4Fh+arg_0], dil
0x18025e7ac  jz      loc_18025E997
0x18025e7b2  mov     [rbp+4Fh+var_B0], rdi
0x18025e7b6  mov     rdi, [r13+0]
0x18025e7ba  mov     rax, [rdi]
0x18025e7bd  mov     rbx, [rax+30h]
0x18025e7c1  lea     rcx, [rbp+4Fh+var_B0]
0x18025e7c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e7ca  lea     rdx, [rbp+4Fh+var_B0]
0x18025e7ce  mov     rcx, rdi
0x18025e7d1  mov     rax, rbx
0x18025e7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e7d9  mov     ebx, eax
0x18025e7db  xor     edi, edi
0x18025e7dd  test    eax, eax
0x18025e7df  jns     short loc_18025E805
0x18025e7e1  mov     rcx, [rbp+57h]; this
0x18025e7e5  mov     r9d, eax; char *
0x18025e7e8  lea     r8, aOnecoreuapEndu_240; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18025e7ef  mov     edx, 21Bh; void *
0x18025e7f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025e7f9  nop
0x18025e7fa  lea     rcx, [rbp+4Fh+var_B0]
0x18025e7fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e803  jmp     short loc_18025E78B
0x18025e805  mov     [rbp+4Fh+var_A8], rdi
0x18025e809  mov     rdi, [rbp+4Fh+var_B0]
0x18025e80d  mov     rax, [rdi]
0x18025e810  mov     rbx, [rax+38h]
0x18025e814  lea     rcx, [rbp+4Fh+var_A8]
0x18025e818  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e81d  lea     rdx, [rbp+4Fh+var_A8]
0x18025e821  mov     rcx, rdi
0x18025e824  mov     rax, rbx
0x18025e827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e82c  mov     ebx, eax
0x18025e82e  xor     edi, edi
0x18025e830  test    eax, eax
0x18025e832  jns     short loc_18025E858
0x18025e834  mov     edx, 21Eh; void *
0x18025e839  mov     r9d, eax; char *
0x18025e83c  mov     rcx, [rbp+57h]; this
0x18025e840  lea     r8, aOnecoreuapEndu_240; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18025e847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025e84c  nop
0x18025e84d  lea     rcx, [rbp+4Fh+var_A8]
0x18025e851  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e856  jmp     short loc_18025E7FA
0x18025e858  mov     [rbp+4Fh+var_A0], edi
0x18025e85b  mov     rcx, [rbp+4Fh+var_A8]
0x18025e85f  mov     rax, [rcx]
0x18025e862  lea     rdx, [rbp+4Fh+var_A0]
0x18025e866  mov     rax, [rax+30h]
0x18025e86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e86f  mov     ebx, eax
0x18025e871  test    eax, eax
0x18025e873  jns     short loc_18025E87C
0x18025e875  mov     edx, 221h
0x18025e87a  jmp     short loc_18025E839
0x18025e87c  cmp     [rbp+4Fh+var_A0], 3
0x18025e880  jz      short loc_18025E891
0x18025e882  mov     ebx, 8000FFFFh
0x18025e887  mov     r9d, ebx
0x18025e88a  mov     edx, 222h
0x18025e88f  jmp     short loc_18025E83C
0x18025e891  mov     rdi, [rbp+4Fh+var_B0]
0x18025e895  mov     rax, [rdi]
0x18025e898  mov     rbx, [rax+30h]
0x18025e89c  mov     rcx, [rbp+4Fh+string]; string
0x18025e8a0  call    cs:__imp_WindowsDeleteString
0x18025e8a6  mov     [rbp+4Fh+string], 0
0x18025e8ae  lea     rdx, [rbp+4Fh+string]
0x18025e8b2  mov     rcx, rdi
0x18025e8b5  mov     rax, rbx
0x18025e8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e8bd  mov     ebx, eax
0x18025e8bf  test    eax, eax
0x18025e8c1  jns     short loc_18025E919
0x18025e8c3  mov     rcx, [rbp+57h]; this
0x18025e8c7  mov     r9d, eax; char *
0x18025e8ca  lea     r8, aOnecoreuapEndu_240; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18025e8d1  mov     edx, 224h; void *
0x18025e8d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025e8db  nop
0x18025e8dc  lea     rcx, [rbp+4Fh+var_A8]
0x18025e8e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e8e5  nop
0x18025e8e6  lea     rcx, [rbp+4Fh+var_B0]
0x18025e8ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e8ef  nop
0x18025e8f0  mov     rcx, [rbp+4Fh+string]; string
0x18025e8f4  call    cs:__imp_WindowsDeleteString
0x18025e8fa  mov     [rbp+4Fh+string], 0
0x18025e902  mov     rcx, [rbp+4Fh+var_B8]; string
0x18025e906  call    cs:__imp_WindowsDeleteString
0x18025e90c  mov     [rbp+4Fh+var_B8], 0
0x18025e914  jmp     loc_18025EA05
0x18025e919  mov     rdi, [rbp+4Fh+var_A8]
0x18025e91d  mov     rax, [rdi]
0x18025e920  mov     rbx, [rax+40h]
0x18025e924  mov     rcx, [rbp+4Fh+var_B8]; string
0x18025e928  call    cs:__imp_WindowsDeleteString
0x18025e92e  mov     [rbp+4Fh+var_B8], 0
0x18025e936  lea     rdx, [rbp+4Fh+var_B8]
0x18025e93a  mov     rcx, rdi
0x18025e93d  mov     rax, rbx
0x18025e940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e945  mov     ebx, eax
0x18025e947  xor     edi, edi
0x18025e949  test    eax, eax
0x18025e94b  jns     short loc_18025E957
0x18025e94d  mov     edx, 225h
0x18025e952  jmp     loc_18025E839
0x18025e957  mov     rcx, [r13+0]
0x18025e95b  mov     rax, [rcx]
0x18025e95e  lea     rdx, [rbp+4Fh+arg_0]
0x18025e962  mov     rax, [rax+40h]
0x18025e966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025e96b  mov     ebx, eax
0x18025e96d  test    eax, eax
0x18025e96f  jns     short loc_18025E97B
0x18025e971  mov     edx, 226h
0x18025e976  jmp     loc_18025E839
0x18025e97b  lea     rcx, [rbp+4Fh+var_A8]
0x18025e97f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e984  nop
0x18025e985  lea     rcx, [rbp+4Fh+var_B0]
0x18025e989  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025e98e  cmp     [rbp+4Fh+arg_0], dil
0x18025e992  jz      short loc_18025E997
0x18025e994  mov     r15d, edi
0x18025e997  mov     [r12], r15d
0x18025e99b  xor     edx, edx; length
0x18025e99d  mov     rcx, [rbp+4Fh+string]; string
0x18025e9a1  call    cs:__imp_WindowsGetStringRawBuffer
0x18025e9a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18025e9ab  mov     r8, rbx
0x18025e9ae  inc     r8
0x18025e9b1  cmp     [rax+r8*2], di
0x18025e9b6  jnz     short loc_18025E9AE
0x18025e9b8  mov     rdx, rax
0x18025e9bb  mov     rcx, r14
0x18025e9be  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18025e9c3  xor     edx, edx; length
0x18025e9c5  mov     rcx, [rbp+4Fh+var_B8]; string
0x18025e9c9  call    cs:__imp_WindowsGetStringRawBuffer
0x18025e9cf  inc     rbx
0x18025e9d2  cmp     [rax+rbx*2], di
0x18025e9d6  jnz     short loc_18025E9CF
0x18025e9d8  mov     r8, rbx
0x18025e9db  mov     rdx, rax
0x18025e9de  mov     rcx, rsi
0x18025e9e1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18025e9e6  nop
0x18025e9e7  mov     rcx, [rbp+4Fh+string]; string
0x18025e9eb  call    cs:__imp_WindowsDeleteString
0x18025e9f1  mov     [rbp+4Fh+string], rdi
0x18025e9f5  mov     rcx, [rbp+4Fh+var_B8]; string
0x18025e9f9  call    cs:__imp_WindowsDeleteString
0x18025e9ff  mov     ebx, edi
0x18025ea01  mov     [rbp+4Fh+var_B8], rdi
0x18025ea05  lea     rcx, [rbp+4Fh+var_90]; this
0x18025ea09  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18025ea0e  mov     eax, ebx
0x18025ea10  add     rsp, 0A8h
0x18025ea17  pop     r15
0x18025ea19  pop     r14
0x18025ea1b  pop     r13
0x18025ea1d  pop     r12
0x18025ea1f  pop     rdi
0x18025ea20  pop     rsi
0x18025ea21  pop     rbx
0x18025ea22  pop     rbp
0x18025ea23  retn
```
