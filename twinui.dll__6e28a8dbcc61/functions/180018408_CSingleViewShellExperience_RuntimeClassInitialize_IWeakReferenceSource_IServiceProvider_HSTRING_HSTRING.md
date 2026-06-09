# CSingleViewShellExperience::RuntimeClassInitialize(IWeakReferenceSource *,IServiceProvider *,HSTRING__ *,HSTRING__ *)

- ea: `0x180018408`
- end: `0x1800188d6`
- name: `?RuntimeClassInitialize@CSingleViewShellExperience@@QEAAJPEAUIWeakReferenceSource@@PEAUIServiceProvider@@PEAUHSTRING__@@2@Z`
- size: `1230`
- prototype: `__int64 __usercall@<rax>(CSingleViewShellExperience *__hidden this@<rcx>, struct IWeakReferenceSource *@<rdx>, struct IServiceProvider *@<r8>, HSTRING@<r9>, HSTRING)`
- caller_count: `8`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e764`
- `0x180016764`
- `0x180016a24`
- `0x180019a84`
- `0x1801f9b70`
- `0x18020fa90`
- `0x18021d370`
- `0x180220268`

## callees

- `0x180008acc`
- `0x180018408`
- `0x1800188dc`
- `0x18003c5e4`
- `0x18003c898`
- `0x18013d330`
- `0x18013f785`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800188b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800188b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001844d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001847c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800184aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001844d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001847c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800184aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001845c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001848b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800184b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001845c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001848b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800184b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185d7`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180018603`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180018603`

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
  HSTRING *v9; // r15
  HRESULT v10; // ebx
  HSTRING *v11; // rbx
  HRESULT v12; // eax
  unsigned int v13; // edi
  HSTRING v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // r12
  __int64 v19; // rdx
  HRESULT v21; // eax
  HSTRING v22; // rbx
  _QWORD *v23; // r14
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  int v31; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-58h]
  __int64 v35; // [rsp+30h] [rbp-48h] BYREF
  __int64 v36; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v9 = (HSTRING *)((char *)this + 8);
  if ( !a4 || a4 != *v9 )
  {
    WindowsDeleteString(*v9);
    *v9 = 0;
    v10 = WindowsDuplicateString(a4, v9);
    if ( v10 < 0 )
    {
      v19 = 67;
      goto LABEL_19;
    }
  }
  v11 = (HSTRING *)((char *)this + 16);
  if ( !string || string != *v11 )
  {
    WindowsDeleteString(*v11);
    *v11 = 0;
    v12 = WindowsDuplicateString(string, (HSTRING *)this + 2);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
        (const char *)(unsigned int)v12,
        v34);
      return v13;
    }
  }
  v14 = *v11;
  if ( !v14 || v14 != *(HSTRING *)this )
  {
    WindowsDeleteString(*(HSTRING *)this);
    *(_QWORD *)this = 0;
    v10 = WindowsDuplicateString(v14, (HSTRING *)this);
    if ( v10 < 0 )
    {
      v19 = 69;
      goto LABEL_19;
    }
  }
  v15 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v36 = 0;
  v10 = ((__int64 (__fastcall *)(struct IWeakReferenceSource *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_00000038_0000_0000_c000_000000000046,
          &v36);
  v16 = v36;
  if ( v10 < 0 )
    goto LABEL_14;
  v35 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 24LL))(v36, &v35);
  if ( v10 < 0 )
  {
    v17 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v16 = v36;
LABEL_14:
    if ( v16 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_16;
  }
  v24 = v35;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  v25 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = v24;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v10 = 0;
LABEL_16:
  if ( v10 < 0 )
  {
    v19 = 71;
    goto LABEL_19;
  }
  v18 = (_QWORD *)((char *)this + 80);
  v10 = (*(__int64 (__fastcall **)(_QWORD, CSingleViewShellExperience *, char *))(**((_QWORD **)this + 11) + 136LL))(
          *((_QWORD *)this + 11),
          this,
          (char *)this + 80);
  if ( v10 < 0 )
  {
    v19 = 73;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v10,
      v34);
    return (unsigned int)v10;
  }
  v38 = 0;
  v21 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &v38);
  if ( v21 < 0 )
  {
    RaiseException(v21, 1u, 0, 0);
    __debugbreak();
  }
  v22 = v38;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  v35 = 0;
  v10 = RoActivateInstance(v22, &v35);
  if ( v10 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *((_QWORD *)this + 4) = v35;
    }
    else
    {
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v35)(
              v35,
              &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
              (char *)this + 32);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  if ( v10 < 0 )
  {
    v19 = 76;
    goto LABEL_19;
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
      v19 = 80;
      goto LABEL_19;
    }
  }
  v23 = (_QWORD *)((char *)this + 112);
  v10 = CSingleViewShellExperience::RegisterAumid(this, *v9, (struct EventRegistrationToken *)this + 14);
  if ( v10 < 0 )
  {
    v19 = 83;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 132) & 4) == 0 || !*v23 )
    goto LABEL_28;
  v35 = 0;
  v29 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 13);
  v30 = **v29;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v31 = v30(v29, &GUID_b18447e2_209d_43d3_add5_a3434f4d558b, &v35);
  v32 = retaddr;
  if ( v31 < 0 )
  {
    v33 = 90;
    goto LABEL_58;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 48LL))(v35, *v23);
  v32 = retaddr;
  if ( v31 < 0 )
  {
    v33 = 92;
LABEL_58:
    wil::details::in1diag3::_Log_Hr(
      v32,
      (void *)v33,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v31,
      v34);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
LABEL_28:
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v18 + 16LL))(*v18, a3);
  if ( v10 < 0 )
  {
    v19 = 97;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 132) & 1) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v18 + 24LL))(*v18, a3);
    if ( v10 < 0 )
    {
      v19 = 103;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018408  push    rbp
0x18001840a  push    rbx
0x18001840b  push    rsi
0x18001840c  push    rdi
0x18001840d  push    r12
0x18001840f  push    r13
0x180018411  push    r14
0x180018413  push    r15
0x180018415  mov     rbp, rsp
0x180018418  sub     rsp, 78h
0x18001841c  mov     rax, cs:__security_cookie
0x180018423  xor     rax, rsp
0x180018426  mov     [rbp+var_18], rax
0x18001842a  mov     rbx, r9
0x18001842d  mov     r13, r8
0x180018430  mov     r14, rdx
0x180018433  mov     rsi, rcx
0x180018436  mov     rdi, [rbp+string]
0x18001843a  lea     r15, [rcx+8]
0x18001843e  xor     r12d, r12d
0x180018441  test    r9, r9
0x180018444  jnz     loc_1800186AA
0x18001844a  mov     rcx, [r15]; string
0x18001844d  call    cs:__imp_WindowsDeleteString
0x180018453  mov     [r15], r12
0x180018456  mov     rdx, r15; newString
0x180018459  mov     rcx, rbx; string
0x18001845c  call    cs:__imp_WindowsDuplicateString
0x180018462  mov     ebx, eax
0x180018464  test    eax, eax
0x180018466  js      loc_1800187EA
0x18001846c  lea     rbx, [rsi+10h]
0x180018470  test    rdi, rdi
0x180018473  jnz     loc_1800186B8
0x180018479  mov     rcx, [rbx]; string
0x18001847c  call    cs:__imp_WindowsDeleteString
0x180018482  mov     [rbx], r12
0x180018485  mov     rdx, rbx; newString
0x180018488  mov     rcx, rdi; string
0x18001848b  call    cs:__imp_WindowsDuplicateString
0x180018491  mov     edi, eax
0x180018493  test    eax, eax
0x180018495  js      loc_180018879
0x18001849b  mov     rbx, [rbx]
0x18001849e  test    rbx, rbx
0x1800184a1  jnz     loc_1800186C6
0x1800184a7  mov     rcx, [rsi]; string
0x1800184aa  call    cs:__imp_WindowsDeleteString
0x1800184b0  mov     [rsi], r12
0x1800184b3  mov     rdx, rsi; newString
0x1800184b6  mov     rcx, rbx; string
0x1800184b9  call    cs:__imp_WindowsDuplicateString
0x1800184bf  mov     ebx, eax
0x1800184c1  test    eax, eax
0x1800184c3  js      loc_180018898
0x1800184c9  mov     rcx, [rsi+60h]
0x1800184cd  mov     [rsi+60h], r12
0x1800184d1  test    rcx, rcx
0x1800184d4  jz      short loc_1800184E3
0x1800184d6  mov     rax, [rcx]
0x1800184d9  mov     rax, [rax+10h]
0x1800184dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184e2  nop
0x1800184e3  mov     [rbp+var_40], r12
0x1800184e7  mov     rax, [r14]
0x1800184ea  lea     r8, [rbp+var_40]
0x1800184ee  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x1800184f5  mov     rcx, r14
0x1800184f8  mov     rax, [rax]
0x1800184fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018500  mov     ebx, eax
0x180018502  mov     rcx, [rbp+var_40]
0x180018506  test    eax, eax
0x180018508  js      short loc_180018545
0x18001850a  mov     [rbp+var_48], r12
0x18001850e  mov     rax, [rcx]
0x180018511  lea     rdx, [rbp+var_48]
0x180018515  mov     rax, [rax+18h]
0x180018519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851e  mov     ebx, eax
0x180018520  test    eax, eax
0x180018522  jns     loc_180018704
0x180018528  mov     rcx, [rbp+var_48]
0x18001852c  test    rcx, rcx
0x18001852f  jz      short loc_180018541
0x180018531  mov     [rbp+var_48], r12
0x180018535  mov     rax, [rcx]
0x180018538  mov     rax, [rax+10h]
0x18001853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018541  mov     rcx, [rbp+var_40]
0x180018545  test    rcx, rcx
0x180018548  jz      short loc_18001855B
0x18001854a  mov     [rbp+var_40], r12
0x18001854e  mov     rax, [rcx]
0x180018551  mov     rax, [rax+10h]
0x180018555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001855a  nop
0x18001855b  test    ebx, ebx
0x18001855d  js      loc_1800188A2
0x180018563  mov     rcx, [rsi+58h]
0x180018567  lea     r12, [rsi+50h]
0x18001856b  mov     rax, [rcx]
0x18001856e  mov     r8, r12
0x180018571  mov     rdx, rsi
0x180018574  mov     rax, [rax+88h]
0x18001857b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018580  mov     ebx, eax
0x180018582  xor     r14d, r14d
0x180018585  test    eax, eax
0x180018587  jns     short loc_1800185BF
0x180018589  lea     edx, [r14+49h]; void *
0x18001858d  mov     rcx, [rbp+40h]; this
0x180018591  mov     r9d, ebx; char *
0x180018594  lea     r8, aShellTwinuiExp_6; "shell\\twinui\\experiencemanagers\\core"...
0x18001859b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185a0  mov     eax, ebx
0x1800185a2  mov     rcx, [rbp+var_18]
0x1800185a6  xor     rcx, rsp; StackCookie
0x1800185a9  call    __security_check_cookie
0x1800185ae  add     rsp, 78h
0x1800185b2  pop     r15
0x1800185b4  pop     r14
0x1800185b6  pop     r13
0x1800185b8  pop     r12
0x1800185ba  pop     rdi
0x1800185bb  pop     rsi
0x1800185bc  pop     rbx
0x1800185bd  pop     rbp
0x1800185be  retn
0x1800185bf  mov     [rbp+var_20], r14
0x1800185c3  lea     r9, [rbp+var_20]; string
0x1800185c7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800185cb  mov     edx, 2Ah ; '*'; length
0x1800185d0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x1800185d7  call    cs:__imp_WindowsCreateStringReference
0x1800185dd  test    eax, eax
0x1800185df  js      loc_1800188AC
0x1800185e5  lea     rdi, [rsi+20h]
0x1800185e9  mov     rbx, [rbp+var_20]
0x1800185ed  mov     rcx, rdi
0x1800185f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800185f5  mov     [rdi], r14
0x1800185f8  mov     [rbp+var_48], r14
0x1800185fc  lea     rdx, [rbp+var_48]
0x180018600  mov     rcx, rbx
0x180018603  call    cs:__imp_RoActivateInstance
0x180018609  mov     ebx, eax
0x18001860b  test    eax, eax
0x18001860d  js      short loc_180018637
0x18001860f  mov     r8d, 10h; Size
0x180018615  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001861c  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180018623  call    memcmp_0
0x180018628  test    eax, eax
0x18001862a  jnz     loc_1800186D4
0x180018630  mov     rax, [rbp+var_48]
0x180018634  mov     [rdi], rax
0x180018637  test    ebx, ebx
0x180018639  js      loc_1800187F4
0x18001863f  lea     rdi, [rsi+68h]
0x180018643  test    byte ptr [rsi+84h], 10h
0x18001864a  jz      loc_180018779
0x180018650  lea     r14, [rsi+70h]
0x180018654  mov     r8, r14; struct EventRegistrationToken *
0x180018657  mov     rdx, [r15]; HSTRING
0x18001865a  mov     rcx, rsi; this
0x18001865d  call    ?RegisterAumid@CSingleViewShellExperience@@AEAAJPEAUHSTRING__@@PEAUEventRegistrationToken@@@Z; CSingleViewShellExperience::RegisterAumid(HSTRING__ *,EventRegistrationToken *)
0x180018662  mov     ebx, eax
0x180018664  test    eax, eax
0x180018666  js      loc_18001876F
0x18001866c  test    byte ptr [rsi+84h], 4
0x180018673  jnz     loc_1800188BF
0x180018679  mov     rcx, [r12]
0x18001867d  mov     rax, [rcx]
0x180018680  mov     rdx, r13
0x180018683  mov     rax, [rax+10h]
0x180018687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001868c  mov     ebx, eax
0x18001868e  test    eax, eax
0x180018690  js      loc_1800187B9
0x180018696  test    byte ptr [rsi+84h], 1
0x18001869d  jnz     loc_1800187C3
0x1800186a3  xor     eax, eax
0x1800186a5  jmp     loc_1800185A2
0x1800186aa  cmp     rbx, [r15]
0x1800186ad  jnz     loc_18001844A
0x1800186b3  jmp     loc_18001846C
0x1800186b8  cmp     rdi, [rbx]
0x1800186bb  jnz     loc_180018479
0x1800186c1  jmp     loc_18001849B
0x1800186c6  cmp     rbx, [rsi]
0x1800186c9  jnz     loc_1800184A7
0x1800186cf  jmp     loc_1800184C9
0x1800186d4  mov     rcx, [rbp+var_48]
0x1800186d8  mov     rax, [rcx]
0x1800186db  mov     r8, rdi
0x1800186de  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800186e5  mov     rax, [rax]
0x1800186e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186ed  mov     ebx, eax
0x1800186ef  mov     rcx, [rbp+var_48]
0x1800186f3  mov     rax, [rcx]
0x1800186f6  mov     rax, [rax+10h]
0x1800186fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186ff  jmp     loc_180018637
0x180018704  mov     rbx, [rbp+var_48]
0x180018708  test    rbx, rbx
0x18001870b  jz      short loc_18001871C
0x18001870d  mov     rax, [rbx]
0x180018710  mov     rcx, rbx
0x180018713  mov     rax, [rax+8]
0x180018717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001871c  mov     rcx, [rsi+60h]
0x180018720  mov     [rsi+60h], rbx
0x180018724  test    rcx, rcx
0x180018727  jz      short loc_180018735
0x180018729  mov     rax, [rcx]
0x18001872c  mov     rax, [rax+10h]
0x180018730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018735  mov     rcx, [rbp+var_48]
0x180018739  test    rcx, rcx
0x18001873c  jz      short loc_18001874E
0x18001873e  mov     [rbp+var_48], r12
0x180018742  mov     rax, [rcx]
0x180018745  mov     rax, [rax+10h]
0x180018749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001874e  mov     rcx, [rbp+var_40]
0x180018752  test    rcx, rcx
0x180018755  jz      short loc_180018767
0x180018757  mov     [rbp+var_40], r12
0x18001875b  mov     rax, [rcx]
0x18001875e  mov     rax, [rax+10h]
0x180018762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018767  mov     ebx, r12d
0x18001876a  jmp     loc_18001855B
0x18001876f  mov     edx, 53h ; 'S'
0x180018774  jmp     loc_18001858D
0x180018779  mov     rax, [r13+0]
0x18001877d  mov     rbx, [rax+18h]
0x180018781  mov     rcx, rdi
0x180018784  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018789  mov     r9, rdi
0x18001878c  lea     r8, _GUID_69bb2711_c5f2_41da_8d6d_448a336a24c5
0x180018793  lea     rdx, _GUID_be47f3f2_56c0_40dd_a5ad_ba88325ea0ce
0x18001879a  mov     rcx, r13
0x18001879d  mov     rax, rbx
0x1800187a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187a5  mov     ebx, eax
0x1800187a7  test    eax, eax
0x1800187a9  jns     loc_180018650
0x1800187af  mov     edx, 50h ; 'P'
0x1800187b4  jmp     loc_18001858D
0x1800187b9  mov     edx, 61h ; 'a'
0x1800187be  jmp     loc_18001858D
0x1800187c3  mov     rcx, [r12]
0x1800187c7  mov     rax, [rcx]
0x1800187ca  mov     rdx, r13
0x1800187cd  mov     rax, [rax+18h]
0x1800187d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187d6  mov     ebx, eax
0x1800187d8  test    eax, eax
0x1800187da  jns     loc_1800186A3
0x1800187e0  mov     edx, 67h ; 'g'
0x1800187e5  jmp     loc_18001858D
0x1800187ea  mov     edx, 43h ; 'C'
0x1800187ef  jmp     loc_18001858D
0x1800187f4  mov     edx, 4Ch ; 'L'
0x1800187f9  jmp     loc_18001858D
0x1800187fe  mov     [rbp+var_48], 0
0x180018806  mov     rdi, [rdi]
0x180018809  mov     rax, [rdi]
0x18001880c  mov     rbx, [rax]
0x18001880f  lea     rcx, [rbp+var_48]
0x180018813  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018818  lea     r8, [rbp+var_48]
0x18001881c  lea     rdx, _GUID_b18447e2_209d_43d3_add5_a3434f4d558b
0x180018823  mov     rcx, rdi
0x180018826  mov     rax, rbx
0x180018829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001882e  nop
0x18001882f  mov     rcx, [rbp+40h]
0x180018833  test    eax, eax
0x180018835  js      loc_1800188CE
0x18001883b  mov     rcx, [rbp+var_48]
0x18001883f  mov     rax, [rcx]
0x180018842  mov     rdx, [r14]
0x180018845  mov     rax, [rax+30h]
0x180018849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001884e  mov     rcx, [rbp+40h]; this
0x180018852  test    eax, eax
0x180018854  jns     short loc_18001886B
0x180018856  mov     edx, 5Ch ; '\'; void *
0x18001885b  mov     r9d, eax; char *
0x18001885e  lea     r8, aShellTwinuiExp_6; "shell\\twinui\\experiencemanagers\\core"...
0x180018865  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001886a  nop
0x18001886b  lea     rcx, [rbp+var_48]
0x18001886f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018874  jmp     loc_180018679
0x180018879  mov     rcx, [rbp+40h]; this
  ... truncated ...
```
