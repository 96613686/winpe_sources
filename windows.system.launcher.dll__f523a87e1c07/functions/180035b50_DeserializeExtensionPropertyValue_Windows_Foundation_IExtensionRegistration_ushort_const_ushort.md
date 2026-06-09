# DeserializeExtensionPropertyValue(Windows::Foundation::IExtensionRegistration *,ushort const *,ushort)

- ea: `0x180035b50`
- end: `0x180035de1`
- name: `?DeserializeExtensionPropertyValue@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUIExtensionRegistration@Foundation@Windows@@PEBGG@Z`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b2ccc`

## callees

- `0x1800047dc`
- `0x1800049bc`
- `0x18000f194`
- `0x180023044`
- `0x1800357b8`
- `0x180035b50`
- `0x180035de8`
- `0x180036020`
- `0x180070c80`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035c0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035dae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035c0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035c45`

## string_xrefs

- `0x180035c19`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180035d90`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall DeserializeExtensionPropertyValue(_QWORD *a1, __int64 a2, const WCHAR *a3, unsigned __int16 a4)
{
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(__int64, _QWORD **); // rbx
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  _QWORD *v12; // rdi
  __int64 v13; // r15
  unsigned __int64 v14; // rbx
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  bool v18; // di
  HSTRING v19; // rbx
  bool v20; // r8
  bool v21; // r9
  int v22; // edx
  __int64 v23; // rcx
  int v24; // eax
  _QWORD *v25; // rcx
  int v27; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v29; // [rsp+20h] [rbp-69h] BYREF
  HSTRING v30; // [rsp+28h] [rbp-61h] BYREF
  struct IInspectable *v31; // [rsp+30h] [rbp-59h] BYREF
  int v32; // [rsp+38h] [rbp-51h]
  __int64 v33; // [rsp+40h] [rbp-49h] BYREF
  int v34; // [rsp+48h] [rbp-41h]
  __int64 v35; // [rsp+50h] [rbp-39h] BYREF
  int v36; // [rsp+58h] [rbp-31h]
  _QWORD *v37; // [rsp+68h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  HSTRING string; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v37 = a1;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(a1);
  v32 = 1;
  v29 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v8 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v10 = v9(a2, &v29);
  v11 = retaddr;
  if ( v10 < 0 )
LABEL_6:
    wil::details::in1diag3::Throw_Hr(
      v11,
      (void *)0x83,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v10,
      (int)v29);
  v33 = 0;
  v34 = 0;
  v12 = v29;
  v13 = *v29;
  v30 = (HSTRING)&v33;
  v31 = 0;
  string = 0;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_6;
  }
  v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
  v16 = v15 - 1;
  if ( (unsigned int)v14 < v15 )
    v16 = v14;
  v17 = WindowsCreateStringReference(a3, v16, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
LABEL_25:
    std::vector<std::wstring>::_Tidy(a1);
    *a1 = *(_QWORD *)v14;
    a1[1] = *(_QWORD *)(v14 + 8);
    a1[2] = *(_QWORD *)(v14 + 16);
    *(_QWORD *)v14 = 0;
    *(_QWORD *)(v14 + 8) = 0;
    *(_QWORD *)(v14 + 16) = 0;
LABEL_22:
    std::vector<std::wstring>::_Tidy(&v35);
    WindowsDeleteString(v30);
    goto LABEL_12;
  }
  v18 = (*(int (__fastcall **)(_QWORD *, HSTRING, struct IInspectable **))(v13 + 48))(v12, string, &v31) >= 0;
  string = 0;
  v19 = v30;
  RoVariant::RoVariant((RoVariant *)&v35, v31, v20, v21);
  v22 = v36;
  v23 = *(_QWORD *)v19;
  *(_QWORD *)v19 = v35;
  v24 = *((_DWORD *)v19 + 2);
  *((_DWORD *)v19 + 2) = v22;
  LODWORD(a3) = -5;
  if ( v23 && ((v24 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v18 )
  {
    v30 = 0;
    v35 = v33;
    v36 = v34;
    WindowsDeleteString(0);
    v30 = 0;
    v27 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v35, &v30);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v27,
        (int)v29);
    StringRawBuffer = WindowsGetStringRawBuffer(v30, 0);
    v14 = SplitString(&v35, StringRawBuffer, a4);
    if ( a1 == (_QWORD *)v14 )
      goto LABEL_22;
    goto LABEL_25;
  }
LABEL_12:
  if ( v33 && ((v34 - 3) & (unsigned int)a3) == 0 )
    (*(void (**)(void))(*(_QWORD *)v33 + 16LL))();
  v25 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  return a1;
}

```

## disassembly

```asm
0x180035b50  push    rbp
0x180035b52  push    rbx
0x180035b53  push    rsi
0x180035b54  push    rdi
0x180035b55  push    r12
0x180035b57  push    r13
0x180035b59  push    r14
0x180035b5b  push    r15
0x180035b5d  lea     rbp, [rsp-1Fh]
0x180035b62  sub     rsp, 0A8h
0x180035b69  mov     rax, cs:__security_cookie
0x180035b70  xor     rax, rsp
0x180035b73  mov     [rbp+57h+var_50], rax
0x180035b77  movzx   r12d, r9w
0x180035b7b  mov     r14, r8
0x180035b7e  mov     rdi, rdx
0x180035b81  mov     rsi, rcx
0x180035b84  mov     [rbp+57h+var_78], rcx
0x180035b88  xor     r13d, r13d
0x180035b8b  mov     [rbp+57h+var_A8], r13d
0x180035b8f  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>> const &)
0x180035b94  mov     [rbp+57h+var_A8], 1
0x180035b9b  mov     [rbp+57h+var_C0], r13
0x180035b9f  mov     rax, [rdx]
0x180035ba2  mov     rbx, [rax+80h]
0x180035ba9  lea     rcx, [rbp+57h+var_C0]
0x180035bad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035bb2  lea     rdx, [rbp+57h+var_C0]
0x180035bb6  mov     rcx, rdi
0x180035bb9  mov     rax, rbx
0x180035bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bc1  mov     rcx, [rbp+5Fh]
0x180035bc5  test    eax, eax
0x180035bc7  js      short loc_180035C16
0x180035bc9  mov     [rbp+57h+var_A0], r13
0x180035bcd  mov     [rbp+57h+var_98], r13d
0x180035bd1  mov     rdi, [rbp+57h+var_C0]
0x180035bd5  mov     r15, [rdi]
0x180035bd8  lea     rax, [rbp+57h+var_A0]
0x180035bdc  mov     [rbp+57h+var_B8], rax
0x180035be0  mov     [rbp+57h+var_B0], r13
0x180035be4  mov     [rbp+57h+string], r13
0x180035be8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180035bec  inc     rbx
0x180035bef  cmp     [r14+rbx*2], r13w
0x180035bf4  jnz     short loc_180035BEC
0x180035bf6  mov     eax, 0FFFFFFFFh
0x180035bfb  cmp     rbx, rax
0x180035bfe  jbe     short loc_180035C2B
0x180035c00  xor     r9d, r9d; lpArguments
0x180035c03  xor     r8d, r8d; nNumberOfArguments
0x180035c06  lea     edx, [r9+1]; dwExceptionFlags
0x180035c0a  mov     ecx, 80070216h; dwExceptionCode
0x180035c0f  call    cs:__imp_RaiseException
0x180035c15  nop
0x180035c16  mov     r9d, eax; char *
0x180035c19  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180035c20  mov     edx, 83h; void *
0x180035c25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035c2b  mov     ecx, ebx; unsigned int
0x180035c2d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180035c32  lea     edx, [rax-1]
0x180035c35  cmp     ebx, eax
0x180035c37  cmovb   edx, ebx; length
0x180035c3a  lea     r9, [rbp+57h+string]; string
0x180035c3e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180035c42  mov     rcx, r14; sourceString
0x180035c45  call    cs:__imp_WindowsCreateStringReference
0x180035c4b  test    eax, eax
0x180035c4d  js      loc_180035DA2
0x180035c53  lea     r8, [rbp+57h+var_B0]
0x180035c57  mov     rdx, [rbp+57h+string]
0x180035c5b  mov     rcx, rdi
0x180035c5e  mov     rax, [r15+30h]
0x180035c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c67  mov     edi, eax
0x180035c69  shr     edi, 1Fh
0x180035c6c  xor     dil, 1
0x180035c70  mov     [rbp+57h+string], r13
0x180035c74  mov     rbx, [rbp+57h+var_B8]
0x180035c78  mov     rdx, [rbp+57h+var_B0]; struct IInspectable *
0x180035c7c  lea     rcx, [rbp+57h+var_90]; this
0x180035c80  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180035c85  mov     rax, [rbp+57h+var_90]
0x180035c89  mov     edx, [rbp+57h+var_88]
0x180035c8c  mov     rcx, [rbx]
0x180035c8f  mov     [rbx], rax
0x180035c92  mov     eax, [rbx+8]
0x180035c95  mov     [rbx+8], edx
0x180035c98  mov     r14d, 0FFFFFFFBh
0x180035c9e  test    rcx, rcx
0x180035ca1  jnz     short loc_180035CEE
0x180035ca3  test    dil, dil
0x180035ca6  jnz     short loc_180035D1D
0x180035ca8  mov     rcx, [rbp+57h+var_A0]
0x180035cac  test    rcx, rcx
0x180035caf  jnz     short loc_180035D04
0x180035cb1  mov     rcx, [rbp+57h+var_C0]
0x180035cb5  test    rcx, rcx
0x180035cb8  jz      short loc_180035CCB
0x180035cba  mov     [rbp+57h+var_C0], r13
0x180035cbe  mov     rdx, [rcx]
0x180035cc1  mov     rax, [rdx+10h]
0x180035cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cca  nop
0x180035ccb  mov     rax, rsi
0x180035cce  mov     rcx, [rbp+57h+var_50]
0x180035cd2  xor     rcx, rsp; StackCookie
0x180035cd5  call    __security_check_cookie
0x180035cda  add     rsp, 0A8h
0x180035ce1  pop     r15
0x180035ce3  pop     r14
0x180035ce5  pop     r13
0x180035ce7  pop     r12
0x180035ce9  pop     rdi
0x180035cea  pop     rsi
0x180035ceb  pop     rbx
0x180035cec  pop     rbp
0x180035ced  retn
0x180035cee  add     eax, 0FFFFFFFDh
0x180035cf1  test    r14d, eax
0x180035cf4  jnz     short loc_180035CA3
0x180035cf6  mov     rax, [rcx]
0x180035cf9  mov     rax, [rax+10h]
0x180035cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d02  jmp     short loc_180035CA3
0x180035d04  mov     eax, [rbp+57h+var_98]
0x180035d07  add     eax, 0FFFFFFFDh
0x180035d0a  test    r14d, eax
0x180035d0d  jnz     short loc_180035CB1
0x180035d0f  mov     rax, [rcx]
0x180035d12  mov     rax, [rax+10h]
0x180035d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d1b  jmp     short loc_180035CB1
0x180035d1d  mov     [rbp+57h+var_B8], r13
0x180035d21  mov     rax, [rbp+57h+var_A0]
0x180035d25  mov     [rbp+57h+var_90], rax
0x180035d29  mov     eax, [rbp+57h+var_98]
0x180035d2c  mov     [rbp+57h+var_88], eax
0x180035d2f  xor     ecx, ecx; string
0x180035d31  call    cs:__imp_WindowsDeleteString
0x180035d37  mov     [rbp+57h+var_B8], r13
0x180035d3b  lea     rdx, [rbp+57h+var_B8]; HSTRING *
0x180035d3f  lea     rcx, [rbp+57h+var_90]; this
0x180035d43  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x180035d48  mov     rcx, [rbp+5Fh]; this
0x180035d4c  test    eax, eax
0x180035d4e  js      short loc_180035D8D
0x180035d50  xor     edx, edx; length
0x180035d52  mov     rcx, [rbp+57h+var_B8]; string
0x180035d56  call    cs:__imp_WindowsGetStringRawBuffer
0x180035d5c  movzx   r8d, r12w
0x180035d60  mov     rdx, rax
0x180035d63  lea     rcx, [rbp+57h+var_90]
0x180035d67  call    ?SplitString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; SplitString(ushort const *,ushort)
0x180035d6c  mov     rbx, rax
0x180035d6f  cmp     rsi, rax
0x180035d72  jnz     short loc_180035DB5
0x180035d74  lea     rcx, [rbp+57h+var_90]
0x180035d78  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180035d7d  nop
0x180035d7e  mov     rcx, [rbp+57h+var_B8]; string
0x180035d82  call    cs:__imp_WindowsDeleteString
0x180035d88  jmp     loc_180035CA8
0x180035d8d  mov     r9d, eax; char *
0x180035d90  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180035d97  mov     edx, 89h; void *
0x180035d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035da2  xor     r9d, r9d; lpArguments
0x180035da5  xor     r8d, r8d; nNumberOfArguments
0x180035da8  lea     edx, [r9+1]; dwExceptionFlags
0x180035dac  mov     ecx, eax; dwExceptionCode
0x180035dae  call    cs:__imp_RaiseException
0x180035db4  nop
0x180035db5  mov     rcx, rsi
0x180035db8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180035dbd  mov     rax, [rbx]
0x180035dc0  mov     [rsi], rax
0x180035dc3  mov     rax, [rbx+8]
0x180035dc7  mov     [rsi+8], rax
0x180035dcb  mov     rax, [rbx+10h]
0x180035dcf  mov     [rsi+10h], rax
0x180035dd3  mov     [rbx], r13
0x180035dd6  mov     [rbx+8], r13
0x180035dda  mov     [rbx+10h], r13
0x180035dde  jmp     short loc_180035D74
```
