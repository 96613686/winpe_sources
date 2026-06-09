# CSingleViewShellExperience::RuntimeClassInitialize(IWeakReferenceSource *,IServiceProvider *,HSTRING__ *,HSTRING__ *)

- ea: `0x18004a440`
- end: `0x18004a7f7`
- name: `?RuntimeClassInitialize@CSingleViewShellExperience@@QEAAJPEAUIWeakReferenceSource@@PEAUIServiceProvider@@PEAUHSTRING__@@2@Z`
- size: `951`
- prototype: `__int64 __usercall@<rax>(CSingleViewShellExperience *__hidden this@<rcx>, struct IWeakReferenceSource *@<rdx>, struct IServiceProvider *@<r8>, HSTRING@<r9>, HSTRING)`
- caller_count: `16`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053884`
- `0x18007a140`
- `0x1800d0188`
- `0x1800e6268`
- `0x1800ec994`
- `0x1801497e8`
- `0x18019fd84`
- `0x1801d98e0`
- `0x180209478`
- `0x1803fc230`
- `0x1803fce50`
- `0x180404180`
- `0x1804059f0`
- `0x180411cc4`
- `0x180439dec`
- `0x18043e594`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x18004a440`
- `0x18004a800`
- `0x18004baf0`
- `0x18004bf00`
- `0x180356360`
- `0x18035b7e5`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a7cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a4c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a4c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a56b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a56b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4e5`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004a597`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004a597`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSingleViewShellExperience::RuntimeClassInitialize(
        CSingleViewShellExperience *this,
        struct IWeakReferenceSource *a2,
        struct IServiceProvider *a3,
        HSTRING a4,
        HSTRING string)
{
  HSTRING *v9; // r14
  HRESULT v10; // ebx
  HSTRING *v11; // rbx
  HRESULT v12; // eax
  unsigned int v13; // edi
  HSTRING v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // r12
  HRESULT v17; // eax
  HSTRING v18; // rbx
  _QWORD *v19; // r15
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  __int64 v22; // rdx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, char **); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, char **); // rbx
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdx
  int v28; // [rsp+20h] [rbp-48h]
  char *v29; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v9 = (HSTRING *)((char *)this + 8);
  if ( !a4 || a4 != *v9 )
  {
    WindowsDeleteString(*v9);
    *v9 = 0;
    v10 = WindowsDuplicateString(a4, v9);
    if ( v10 < 0 )
    {
      v22 = 67;
      goto LABEL_29;
    }
  }
  v11 = (HSTRING *)((char *)this + 16);
  if ( string && string == *v11
    || (WindowsDeleteString(*v11),
        *v11 = 0,
        v12 = WindowsDuplicateString(string, (HSTRING *)this + 2),
        v13 = v12,
        v12 >= 0) )
  {
    v14 = *v11;
    if ( !v14 || v14 != *(HSTRING *)this )
    {
      WindowsDeleteString(*(HSTRING *)this);
      *(_QWORD *)this = 0;
      v10 = WindowsDuplicateString(v14, (HSTRING *)this);
      if ( v10 < 0 )
      {
        v22 = 69;
        goto LABEL_29;
      }
    }
    v29 = (char *)this + 96;
    v15 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v29);
    v10 = Microsoft::WRL::AsWeak<IDWMStoryboardListener>(a2, v15);
    if ( v10 < 0 )
    {
      v22 = 71;
      goto LABEL_29;
    }
    v16 = (_QWORD *)((char *)this + 80);
    v10 = (*(__int64 (__fastcall **)(_QWORD, CSingleViewShellExperience *, char *))(**((_QWORD **)this + 11) + 136LL))(
            *((_QWORD *)this + 11),
            this,
            (char *)this + 80);
    if ( v10 < 0 )
    {
      v22 = 73;
      goto LABEL_29;
    }
    v31 = 0;
    v17 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &v31);
    if ( v17 < 0 )
    {
      RaiseException(v17, 1u, 0, 0);
      __debugbreak();
    }
    v18 = v31;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
    *((_QWORD *)this + 4) = 0;
    v29 = 0;
    v10 = RoActivateInstance(v18, &v29);
    if ( v10 >= 0 )
    {
      if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        *((_QWORD *)this + 4) = v29;
      }
      else
      {
        v10 = (**(__int64 (__fastcall ***)(char *, GUID *, char *))v29)(
                v29,
                &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
                (char *)this + 32);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
    if ( v10 < 0 )
    {
      v22 = 76;
      goto LABEL_29;
    }
    if ( (*((_BYTE *)this + 132) & 0x10) == 0 )
    {
      QueryService = a3->lpVtbl->QueryService;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
      v10 = ((__int64 (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, char *))QueryService)(
              a3,
              &GUID_be47f3f2_56c0_40dd_a5ad_ba88325ea0ce,
              &GUID_69bb2711_c5f2_41da_8d6d_448a336a24c5,
              (char *)this + 104);
      if ( v10 < 0 )
      {
        v22 = 80;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
          (const char *)(unsigned int)v10,
          v28);
        return (unsigned int)v10;
      }
    }
    v19 = (_QWORD *)((char *)this + 112);
    v10 = CSingleViewShellExperience::RegisterAumid(this, *v9, (struct EventRegistrationToken *)this + 14);
    if ( v10 < 0 )
    {
      v22 = 83;
      goto LABEL_29;
    }
    if ( (*((_BYTE *)this + 132) & 4) == 0 || !*v19 )
    {
LABEL_20:
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v16 + 16LL))(*v16, a3);
      if ( v10 < 0 )
      {
        v22 = 97;
      }
      else
      {
        if ( (*((_BYTE *)this + 132) & 1) == 0 )
          return 0;
        v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v16 + 24LL))(*v16, a3);
        if ( v10 >= 0 )
          return 0;
        v22 = 103;
      }
      goto LABEL_29;
    }
    v29 = 0;
    v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, char **))*((_QWORD *)this + 13);
    v24 = **v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v25 = v24(v23, &GUID_b18447e2_209d_43d3_add5_a3434f4d558b, &v29);
    v26 = retaddr;
    if ( v25 < 0 )
    {
      v27 = 90;
    }
    else
    {
      v25 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v29 + 48LL))(v29, *v19);
      v26 = retaddr;
      if ( v25 >= 0 )
      {
LABEL_38:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        goto LABEL_20;
      }
      v27 = 92;
    }
    wil::details::in1diag3::_Log_Hr(
      v26,
      (void *)v27,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v25,
      v28);
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x44,
    (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
    (const char *)(unsigned int)v12,
    v28);
  return v13;
}

```

## disassembly

```asm
0x18004a440  push    rbp
0x18004a442  push    rbx
0x18004a443  push    rsi
0x18004a444  push    rdi
0x18004a445  push    r12
0x18004a447  push    r13
0x18004a449  push    r14
0x18004a44b  push    r15
0x18004a44d  mov     rbp, rsp
0x18004a450  sub     rsp, 68h
0x18004a454  mov     rax, cs:__security_cookie
0x18004a45b  xor     rax, rsp
0x18004a45e  mov     [rbp+var_10], rax
0x18004a462  mov     rbx, r9
0x18004a465  mov     r13, r8
0x18004a468  mov     r15, rdx
0x18004a46b  mov     rsi, rcx
0x18004a46e  mov     rdi, [rbp+string]
0x18004a472  lea     r14, [rcx+8]
0x18004a476  xor     r12d, r12d
0x18004a479  test    r9, r9
0x18004a47c  jz      short loc_18004A483
0x18004a47e  cmp     rbx, [r14]
0x18004a481  jz      short loc_18004A4A5
0x18004a483  mov     rcx, [r14]; string
0x18004a486  call    cs:__imp_WindowsDeleteString
0x18004a48c  mov     [r14], r12
0x18004a48f  mov     rdx, r14; newString
0x18004a492  mov     rcx, rbx; string
0x18004a495  call    cs:__imp_WindowsDuplicateString
0x18004a49b  mov     ebx, eax
0x18004a49d  test    eax, eax
0x18004a49f  js      loc_18004A731
0x18004a4a5  lea     rbx, [rsi+10h]
0x18004a4a9  test    rdi, rdi
0x18004a4ac  jz      short loc_18004A4B3
0x18004a4ae  cmp     rdi, [rbx]
0x18004a4b1  jz      short loc_18004A4D5
0x18004a4b3  mov     rcx, [rbx]; string
0x18004a4b6  call    cs:__imp_WindowsDeleteString
0x18004a4bc  mov     [rbx], r12
0x18004a4bf  mov     rdx, rbx; newString
0x18004a4c2  mov     rcx, rdi; string
0x18004a4c5  call    cs:__imp_WindowsDuplicateString
0x18004a4cb  mov     edi, eax
0x18004a4cd  test    eax, eax
0x18004a4cf  js      loc_18004A70B
0x18004a4d5  mov     rbx, [rbx]
0x18004a4d8  test    rbx, rbx
0x18004a4db  jz      short loc_18004A4E2
0x18004a4dd  cmp     rbx, [rsi]
0x18004a4e0  jz      short loc_18004A504
0x18004a4e2  mov     rcx, [rsi]; string
0x18004a4e5  call    cs:__imp_WindowsDeleteString
0x18004a4eb  mov     [rsi], r12
0x18004a4ee  mov     rdx, rsi; newString
0x18004a4f1  mov     rcx, rbx; string
0x18004a4f4  call    cs:__imp_WindowsDuplicateString
0x18004a4fa  mov     ebx, eax
0x18004a4fc  test    eax, eax
0x18004a4fe  js      loc_18004A7AF
0x18004a504  lea     rax, [rsi+60h]
0x18004a508  mov     [rbp+var_38], rax
0x18004a50c  lea     rcx, [rbp+var_38]
0x18004a510  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18004a515  mov     rdx, rax
0x18004a518  mov     rcx, r15
0x18004a51b  call    ??$AsWeak@UIDWMStoryboardListener@@@WRL@Microsoft@@YAJPEAUIDWMStoryboardListener@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IDWMStoryboardListener>(IDWMStoryboardListener *,Microsoft::WRL::WeakRef *)
0x18004a520  mov     ebx, eax
0x18004a522  test    eax, eax
0x18004a524  js      loc_18004A7B9
0x18004a52a  mov     rcx, [rsi+58h]
0x18004a52e  lea     r12, [rsi+50h]
0x18004a532  mov     rax, [rcx]
0x18004a535  mov     r8, r12
0x18004a538  mov     rdx, rsi
0x18004a53b  mov     rax, [rax+88h]
0x18004a542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a547  mov     ebx, eax
0x18004a549  xor     r15d, r15d
0x18004a54c  test    eax, eax
0x18004a54e  js      loc_18004A704
0x18004a554  mov     [rbp+var_18], r15
0x18004a558  lea     r9, [rbp+var_18]; string
0x18004a55c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004a560  lea     edx, [r15+2Ah]; length
0x18004a564  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18004a56b  call    cs:__imp_WindowsCreateStringReference
0x18004a571  test    eax, eax
0x18004a573  js      loc_18004A7C3
0x18004a579  lea     rdi, [rsi+20h]
0x18004a57d  mov     rbx, [rbp+var_18]
0x18004a581  mov     rcx, rdi
0x18004a584  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a589  mov     [rdi], r15
0x18004a58c  mov     [rbp+var_38], r15
0x18004a590  lea     rdx, [rbp+var_38]
0x18004a594  mov     rcx, rbx
0x18004a597  call    cs:__imp_RoActivateInstance
0x18004a59d  mov     ebx, eax
0x18004a59f  test    eax, eax
0x18004a5a1  js      short loc_18004A5C9
0x18004a5a3  lea     r8d, [r15+10h]; Size
0x18004a5a7  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18004a5ae  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18004a5b5  call    memcmp_0
0x18004a5ba  test    eax, eax
0x18004a5bc  jnz     loc_18004A654
0x18004a5c2  mov     rax, [rbp+var_38]
0x18004a5c6  mov     [rdi], rax
0x18004a5c9  test    ebx, ebx
0x18004a5cb  js      loc_18004A72A
0x18004a5d1  lea     rdi, [rsi+68h]
0x18004a5d5  test    byte ptr [rsi+84h], 10h
0x18004a5dc  jz      loc_18004A684
0x18004a5e2  lea     r15, [rsi+70h]
0x18004a5e6  mov     r8, r15; struct EventRegistrationToken *
0x18004a5e9  mov     rdx, [r14]; HSTRING
0x18004a5ec  mov     rcx, rsi; this
0x18004a5ef  call    ?RegisterAumid@CSingleViewShellExperience@@AEAAJPEAUHSTRING__@@PEAUEventRegistrationToken@@@Z; CSingleViewShellExperience::RegisterAumid(HSTRING__ *,EventRegistrationToken *)
0x18004a5f4  mov     ebx, eax
0x18004a5f6  test    eax, eax
0x18004a5f8  js      loc_18004A7D6
0x18004a5fe  test    byte ptr [rsi+84h], 4
0x18004a605  jnz     loc_18004A7E0
0x18004a60b  mov     rcx, [r12]
0x18004a60f  mov     rax, [rcx]
0x18004a612  mov     rdx, r13
0x18004a615  mov     rax, [rax+10h]
0x18004a619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a61e  mov     ebx, eax
0x18004a620  test    eax, eax
0x18004a622  js      loc_18004A6E5
0x18004a628  test    byte ptr [rsi+84h], 1
0x18004a62f  jnz     loc_18004A6C1
0x18004a635  xor     eax, eax
0x18004a637  mov     rcx, [rbp+var_10]
0x18004a63b  xor     rcx, rsp; StackCookie
0x18004a63e  call    __security_check_cookie
0x18004a643  add     rsp, 68h
0x18004a647  pop     r15
0x18004a649  pop     r14
0x18004a64b  pop     r13
0x18004a64d  pop     r12
0x18004a64f  pop     rdi
0x18004a650  pop     rsi
0x18004a651  pop     rbx
0x18004a652  pop     rbp
0x18004a653  retn
0x18004a654  mov     rcx, [rbp+var_38]
0x18004a658  mov     rax, [rcx]
0x18004a65b  mov     r8, rdi
0x18004a65e  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18004a665  mov     rax, [rax]
0x18004a668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a66d  mov     ebx, eax
0x18004a66f  mov     rcx, [rbp+var_38]
0x18004a673  mov     rax, [rcx]
0x18004a676  mov     rax, [rax+10h]
0x18004a67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a67f  jmp     loc_18004A5C9
0x18004a684  mov     rax, [r13+0]
0x18004a688  mov     rbx, [rax+18h]
0x18004a68c  mov     rcx, rdi
0x18004a68f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a694  mov     r9, rdi
0x18004a697  lea     r8, _GUID_69bb2711_c5f2_41da_8d6d_448a336a24c5
0x18004a69e  lea     rdx, _GUID_be47f3f2_56c0_40dd_a5ad_ba88325ea0ce
0x18004a6a5  mov     rcx, r13
0x18004a6a8  mov     rax, rbx
0x18004a6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6b0  mov     ebx, eax
0x18004a6b2  test    eax, eax
0x18004a6b4  jns     loc_18004A5E2
0x18004a6ba  mov     edx, 50h ; 'P'
0x18004a6bf  jmp     short loc_18004A6EA
0x18004a6c1  mov     rcx, [r12]
0x18004a6c5  mov     rax, [rcx]
0x18004a6c8  mov     rdx, r13
0x18004a6cb  mov     rax, [rax+18h]
0x18004a6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6d4  mov     ebx, eax
0x18004a6d6  test    eax, eax
0x18004a6d8  jns     loc_18004A635
0x18004a6de  mov     edx, 67h ; 'g'
0x18004a6e3  jmp     short loc_18004A6EA
0x18004a6e5  mov     edx, 61h ; 'a'; void *
0x18004a6ea  mov     rcx, [rbp+40h]; this
0x18004a6ee  mov     r9d, ebx; char *
0x18004a6f1  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x18004a6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a6fd  mov     eax, ebx
0x18004a6ff  jmp     loc_18004A637
0x18004a704  mov     edx, 49h ; 'I'
0x18004a709  jmp     short loc_18004A6EA
0x18004a70b  mov     rcx, [rbp+40h]; this
0x18004a70f  mov     r9d, edi; char *
0x18004a712  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x18004a719  mov     edx, 44h ; 'D'; void *
0x18004a71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a723  mov     eax, edi
0x18004a725  jmp     loc_18004A637
0x18004a72a  mov     edx, 4Ch ; 'L'
0x18004a72f  jmp     short loc_18004A6EA
0x18004a731  mov     edx, 43h ; 'C'
0x18004a736  jmp     short loc_18004A6EA
0x18004a738  mov     [rbp+var_38], 0
0x18004a740  mov     rdi, [rdi]
0x18004a743  mov     rax, [rdi]
0x18004a746  mov     rbx, [rax]
0x18004a749  lea     rcx, [rbp+var_38]
0x18004a74d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a752  lea     r8, [rbp+var_38]
0x18004a756  lea     rdx, _GUID_b18447e2_209d_43d3_add5_a3434f4d558b
0x18004a75d  mov     rcx, rdi
0x18004a760  mov     rax, rbx
0x18004a763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a768  nop
0x18004a769  mov     rcx, [rbp+40h]
0x18004a76d  test    eax, eax
0x18004a76f  js      short loc_18004A7EF
0x18004a771  mov     rcx, [rbp+var_38]
0x18004a775  mov     rax, [rcx]
0x18004a778  mov     rdx, [r15]
0x18004a77b  mov     rax, [rax+30h]
0x18004a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a784  mov     rcx, [rbp+40h]; this
0x18004a788  test    eax, eax
0x18004a78a  jns     short loc_18004A7A1
0x18004a78c  mov     edx, 5Ch ; '\'; void *
0x18004a791  mov     r9d, eax; char *
0x18004a794  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x18004a79b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a7a0  nop
0x18004a7a1  lea     rcx, [rbp+var_38]
0x18004a7a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a7aa  jmp     loc_18004A60B
0x18004a7af  mov     edx, 45h ; 'E'
0x18004a7b4  jmp     loc_18004A6EA
0x18004a7b9  mov     edx, 47h ; 'G'
0x18004a7be  jmp     loc_18004A6EA
0x18004a7c3  xor     r9d, r9d; lpArguments
0x18004a7c6  xor     r8d, r8d; nNumberOfArguments
0x18004a7c9  lea     edx, [r9+1]; dwExceptionFlags
0x18004a7cd  mov     ecx, eax; dwExceptionCode
0x18004a7cf  call    cs:__imp_RaiseException
0x18004a7d5  int     3; Trap to Debugger
0x18004a7d6  mov     edx, 53h ; 'S'
0x18004a7db  jmp     loc_18004A6EA
0x18004a7e0  cmp     qword ptr [r15], 0
0x18004a7e4  jz      loc_18004A60B
0x18004a7ea  jmp     loc_18004A738
0x18004a7ef  mov     edx, 5Ah ; 'Z'
0x18004a7f4  jmp     short loc_18004A791
```
