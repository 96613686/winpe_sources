# Windows::System::Internal::Launch::StateRepositorySource::Clone(ushort const *,IQuerySource * *)

- ea: `0x180033570`
- end: `0x180033a56`
- name: `?Clone@StateRepositorySource@Launch@Internal@System@Windows@@AEAAJPEBGPEAPEAUIQuerySource@@@Z`
- size: `1254`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, const unsigned __int16 *, struct IQuerySource **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033340`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180032ecc`
- `0x180033570`
- `0x180033ae8`
- `0x180033b60`
- `0x180033bf0`
- `0x1800343c0`
- `0x18003a0d0`
- `0x180043a38`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800335ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800335ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003366c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800336a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800336de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800337c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800337fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003366c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800336a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800336de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800337c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800337fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003367b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800336b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800336ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003375f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800337d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003380a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003367b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800336b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800336ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003375f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800337d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003380a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033887`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::Clone(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        const unsigned __int16 *a2,
        struct IQuerySource **a3)
{
  __int64 v6; // rbx
  HSTRING *v7; // rsi
  unsigned __int64 v8; // r8
  HRESULT String; // eax
  HRESULT Key; // esi
  __int64 v11; // rcx
  HKEY v12; // r14
  HSTRING *v13; // rsi
  HSTRING v14; // r14
  HSTRING *v15; // rsi
  HSTRING v16; // r14
  HSTRING *v17; // rsi
  HSTRING v18; // r14
  HSTRING *v19; // rsi
  HSTRING v20; // r14
  HSTRING *v21; // rsi
  HSTRING v22; // r14
  HSTRING *v23; // rsi
  HSTRING v24; // r14
  HSTRING *v25; // rsi
  HSTRING v26; // r14
  HSTRING *v27; // rsi
  HSTRING v28; // r14
  __int64 v29; // rdx
  HSTRING *v31; // rsi
  HSTRING v32; // r14
  int v33; // eax
  unsigned int v34; // edi
  struct IQuerySource *v35; // rcx
  struct IQuerySource *v36; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  struct IQuerySource *v39; // [rsp+58h] [rbp+38h] BYREF
  __int64 v40; // [rsp+68h] [rbp+48h] BYREF

  Microsoft::WRL::Details::Make<Windows::System::Internal::Launch::StateRepositorySource,>(&v40);
  v6 = v40;
  v7 = (HSTRING *)(v40 + 104);
  if ( !a2 )
  {
    WindowsDeleteString(*v7);
    *v7 = 0;
    String = WindowsCreateString(&LocaleName, 0, v7);
    goto LABEL_7;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 <= 0xFFFFFFFF )
  {
    String = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(v40 + 104), a2, v8);
LABEL_7:
    Key = String;
    goto LABEL_8;
  }
  Key = -2147024362;
LABEL_8:
  if ( Key < 0 )
  {
    v29 = 75;
    goto LABEL_31;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v6 + 112);
  v11 = *((_QWORD *)this + 14);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  *(_QWORD *)(v6 + 112) = *((_QWORD *)this + 14);
  v12 = *(HKEY *)(v6 + 120);
  if ( v12 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v40);
    RegCloseKey(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v40);
  }
  *(_QWORD *)(v6 + 120) = 0;
  Key = Windows::System::Internal::Launch::StateRepositorySource::GetKey(
          (Windows::System::Internal::Launch::StateRepositorySource *)((char *)this + 24),
          0x20019u,
          (HKEY *)(v6 + 120));
  if ( Key < 0 )
  {
    v29 = 77;
    goto LABEL_31;
  }
  v13 = (HSTRING *)(v6 + 128);
  v14 = (HSTRING)*((_QWORD *)this + 16);
  if ( !v14 || v14 != *v13 )
  {
    WindowsDeleteString(*v13);
    *v13 = 0;
    Key = WindowsDuplicateString(v14, (HSTRING *)(v6 + 128));
    if ( Key < 0 )
    {
      v29 = 78;
      goto LABEL_31;
    }
  }
  v15 = (HSTRING *)(v6 + 136);
  v16 = (HSTRING)*((_QWORD *)this + 17);
  if ( !v16 || v16 != *v15 )
  {
    WindowsDeleteString(*v15);
    *v15 = 0;
    Key = WindowsDuplicateString(v16, (HSTRING *)(v6 + 136));
    if ( Key < 0 )
    {
      v29 = 79;
      goto LABEL_31;
    }
  }
  v17 = (HSTRING *)(v6 + 144);
  v18 = (HSTRING)*((_QWORD *)this + 18);
  if ( !v18 || v18 != *v17 )
  {
    WindowsDeleteString(*v17);
    *v17 = 0;
    Key = WindowsDuplicateString(v18, (HSTRING *)(v6 + 144));
    if ( Key < 0 )
    {
      v29 = 80;
      goto LABEL_31;
    }
  }
  v19 = (HSTRING *)(v6 + 152);
  v20 = (HSTRING)*((_QWORD *)this + 19);
  if ( !v20 || v20 != *v19 )
  {
    WindowsDeleteString(*v19);
    *v19 = 0;
    Key = WindowsDuplicateString(v20, (HSTRING *)(v6 + 152));
    if ( Key < 0 )
    {
      v29 = 81;
      goto LABEL_31;
    }
  }
  v21 = (HSTRING *)(v6 + 160);
  v22 = (HSTRING)*((_QWORD *)this + 20);
  if ( !v22 || v22 != *v21 )
  {
    WindowsDeleteString(*v21);
    *v21 = 0;
    Key = WindowsDuplicateString(v22, (HSTRING *)(v6 + 160));
    if ( Key < 0 )
    {
      v29 = 82;
      goto LABEL_31;
    }
  }
  v23 = (HSTRING *)(v6 + 176);
  v24 = (HSTRING)*((_QWORD *)this + 22);
  if ( !v24 || v24 != *v23 )
  {
    WindowsDeleteString(*v23);
    *v23 = 0;
    Key = WindowsDuplicateString(v24, (HSTRING *)(v6 + 176));
    if ( Key < 0 )
    {
      v29 = 83;
      goto LABEL_31;
    }
  }
  v25 = (HSTRING *)(v6 + 184);
  v26 = (HSTRING)*((_QWORD *)this + 23);
  if ( !v26 || v26 != *v25 )
  {
    WindowsDeleteString(*v25);
    *v25 = 0;
    Key = WindowsDuplicateString(v26, (HSTRING *)(v6 + 184));
    if ( Key < 0 )
    {
      v29 = 84;
      goto LABEL_31;
    }
  }
  v27 = (HSTRING *)(v6 + 192);
  v28 = (HSTRING)*((_QWORD *)this + 24);
  if ( !v28 || v28 != *v27 )
  {
    WindowsDeleteString(*v27);
    *v27 = 0;
    Key = WindowsDuplicateString(v28, (HSTRING *)(v6 + 192));
    if ( Key < 0 )
    {
      v29 = 85;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
        (const char *)(unsigned int)Key,
        savedregs);
      if ( v6 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(v6);
      return (unsigned int)Key;
    }
  }
  v31 = (HSTRING *)(v6 + 200);
  v32 = (HSTRING)*((_QWORD *)this + 25);
  if ( !v32 || v32 != *v31 )
  {
    WindowsDeleteString(*v31);
    *v31 = 0;
    Key = WindowsDuplicateString(v32, (HSTRING *)(v6 + 200));
    if ( Key < 0 )
    {
      v29 = 86;
      goto LABEL_31;
    }
  }
  *(_DWORD *)(v6 + 208) = *((_DWORD *)this + 52);
  *(_BYTE *)(v6 + 212) = *((_BYTE *)this + 212);
  *(_BYTE *)(v6 + 213) = *((_BYTE *)this + 213);
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v33 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>>(
          v6,
          &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac,
          &v39);
  v34 = v33;
  if ( v33 >= 0 )
  {
    v36 = v39;
    v39 = 0;
    *a3 = v36;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
      (const char *)(unsigned int)v33,
      savedregs);
    v35 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct IQuerySource *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(v6);
    return v34;
  }
}

```

## disassembly

```asm
0x180033570  mov     [rsp-28h+arg_0], rbx
0x180033575  mov     [rsp-28h+arg_10], rsi
0x18003357a  push    rbp
0x18003357b  push    rdi
0x18003357c  push    r12
0x18003357e  push    r14
0x180033580  push    r15; int
0x180033582  mov     rbp, rsp
0x180033585  sub     rsp, 20h
0x180033589  mov     r15, r8
0x18003358c  mov     r14, rdx
0x18003358f  mov     rdi, rcx
0x180033592  lea     rcx, [rbp+arg_18]
0x180033596  call    ??$Make@VStateRepositorySource@Launch@Internal@System@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStateRepositorySource@Launch@Internal@System@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::System::Internal::Launch::StateRepositorySource,>(void)
0x18003359b  mov     rbx, [rbp+arg_18]
0x18003359f  lea     rsi, [rbx+68h]
0x1800335a3  xor     r12d, r12d
0x1800335a6  test    r14, r14
0x1800335a9  jz      short loc_1800335D4
0x1800335ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800335af  inc     r8; unsigned int
0x1800335b2  cmp     [r14+r8*2], r12w
0x1800335b7  jnz     short loc_1800335AF
0x1800335b9  mov     eax, 0FFFFFFFFh
0x1800335be  cmp     r8, rax
0x1800335c1  ja      loc_180033854
0x1800335c7  mov     rdx, r14; unsigned __int16 *
0x1800335ca  mov     rcx, rsi; this
0x1800335cd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800335d2  jmp     short loc_1800335F2
0x1800335d4  mov     rcx, [rsi]; string
0x1800335d7  call    cs:__imp_WindowsDeleteString
0x1800335dd  mov     [rsi], r12
0x1800335e0  mov     r8, rsi; string
0x1800335e3  xor     edx, edx; length
0x1800335e5  lea     rcx, LocaleName; sourceString
0x1800335ec  call    cs:__imp_WindowsCreateString
0x1800335f2  mov     esi, eax
0x1800335f4  test    esi, esi
0x1800335f6  js      loc_180033936
0x1800335fc  lea     rcx, [rbx+70h]
0x180033600  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033605  nop
0x180033606  mov     rcx, [rdi+70h]
0x18003360a  test    rcx, rcx
0x18003360d  jz      short loc_18003361C
0x18003360f  mov     rax, [rcx]
0x180033612  mov     rax, [rax+8]
0x180033616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003361b  nop
0x18003361c  mov     rax, [rdi+70h]
0x180033620  mov     [rbx+70h], rax
0x180033624  lea     rsi, [rbx+78h]
0x180033628  mov     r14, [rsi]
0x18003362b  test    r14, r14
0x18003362e  jnz     loc_1800339FA
0x180033634  mov     [rsi], r12
0x180033637  lea     rcx, [rdi+18h]; this
0x18003363b  mov     r8, rsi; HKEY *
0x18003363e  mov     edx, 20019h; unsigned int
0x180033643  call    ?GetKey@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJKPEAPEAUHKEY__@@@Z; Windows::System::Internal::Launch::StateRepositorySource::GetKey(ulong,HKEY__ * *)
0x180033648  mov     esi, eax
0x18003364a  test    eax, eax
0x18003364c  js      loc_1800339AC
0x180033652  lea     rsi, [rbx+80h]
0x180033659  mov     r14, [rdi+80h]
0x180033660  test    r14, r14
0x180033663  jnz     loc_18003394A
0x180033669  mov     rcx, [rsi]; string
0x18003366c  call    cs:__imp_WindowsDeleteString
0x180033672  mov     [rsi], r12
0x180033675  mov     rdx, rsi; newString
0x180033678  mov     rcx, r14; string
0x18003367b  call    cs:__imp_WindowsDuplicateString
0x180033681  mov     esi, eax
0x180033683  test    eax, eax
0x180033685  js      loc_180033A1A
0x18003368b  lea     rsi, [rbx+88h]
0x180033692  mov     r14, [rdi+88h]
0x180033699  test    r14, r14
0x18003369c  jnz     loc_180033958
0x1800336a2  mov     rcx, [rsi]; string
0x1800336a5  call    cs:__imp_WindowsDeleteString
0x1800336ab  mov     [rsi], r12
0x1800336ae  mov     rdx, rsi; newString
0x1800336b1  mov     rcx, r14; string
0x1800336b4  call    cs:__imp_WindowsDuplicateString
0x1800336ba  mov     esi, eax
0x1800336bc  test    eax, eax
0x1800336be  js      loc_180033A24
0x1800336c4  lea     rsi, [rbx+90h]
0x1800336cb  mov     r14, [rdi+90h]
0x1800336d2  test    r14, r14
0x1800336d5  jnz     loc_180033966
0x1800336db  mov     rcx, [rsi]; string
0x1800336de  call    cs:__imp_WindowsDeleteString
0x1800336e4  mov     [rsi], r12
0x1800336e7  mov     rdx, rsi; newString
0x1800336ea  mov     rcx, r14; string
0x1800336ed  call    cs:__imp_WindowsDuplicateString
0x1800336f3  mov     esi, eax
0x1800336f5  test    eax, eax
0x1800336f7  js      loc_180033A2E
0x1800336fd  lea     rsi, [rbx+98h]
0x180033704  mov     r14, [rdi+98h]
0x18003370b  test    r14, r14
0x18003370e  jnz     loc_180033974
0x180033714  mov     rcx, [rsi]; string
0x180033717  call    cs:__imp_WindowsDeleteString
0x18003371d  mov     [rsi], r12
0x180033720  mov     rdx, rsi; newString
0x180033723  mov     rcx, r14; string
0x180033726  call    cs:__imp_WindowsDuplicateString
0x18003372c  mov     esi, eax
0x18003372e  test    eax, eax
0x180033730  js      loc_180033A38
0x180033736  lea     rsi, [rbx+0A0h]
0x18003373d  mov     r14, [rdi+0A0h]
0x180033744  test    r14, r14
0x180033747  jnz     loc_180033982
0x18003374d  mov     rcx, [rsi]; string
0x180033750  call    cs:__imp_WindowsDeleteString
0x180033756  mov     [rsi], r12
0x180033759  mov     rdx, rsi; newString
0x18003375c  mov     rcx, r14; string
0x18003375f  call    cs:__imp_WindowsDuplicateString
0x180033765  mov     esi, eax
0x180033767  test    eax, eax
0x180033769  js      loc_180033A42
0x18003376f  lea     rsi, [rbx+0B0h]
0x180033776  mov     r14, [rdi+0B0h]
0x18003377d  test    r14, r14
0x180033780  jnz     loc_180033990
0x180033786  mov     rcx, [rsi]; string
0x180033789  call    cs:__imp_WindowsDeleteString
0x18003378f  mov     [rsi], r12
0x180033792  mov     rdx, rsi; newString
0x180033795  mov     rcx, r14; string
0x180033798  call    cs:__imp_WindowsDuplicateString
0x18003379e  mov     esi, eax
0x1800337a0  test    eax, eax
0x1800337a2  js      loc_180033940
0x1800337a8  lea     rsi, [rbx+0B8h]
0x1800337af  mov     r14, [rdi+0B8h]
0x1800337b6  test    r14, r14
0x1800337b9  jnz     loc_18003399E
0x1800337bf  mov     rcx, [rsi]; string
0x1800337c2  call    cs:__imp_WindowsDeleteString
0x1800337c8  mov     [rsi], r12
0x1800337cb  mov     rdx, rsi; newString
0x1800337ce  mov     rcx, r14; string
0x1800337d1  call    cs:__imp_WindowsDuplicateString
0x1800337d7  mov     esi, eax
0x1800337d9  test    eax, eax
0x1800337db  js      loc_18003392C
0x1800337e1  lea     rsi, [rbx+0C0h]
0x1800337e8  mov     r14, [rdi+0C0h]
0x1800337ef  test    r14, r14
0x1800337f2  jnz     loc_1800339B6
0x1800337f8  mov     rcx, [rsi]; string
0x1800337fb  call    cs:__imp_WindowsDeleteString
0x180033801  mov     [rsi], r12
0x180033804  mov     rdx, rsi; newString
0x180033807  mov     rcx, r14; string
0x18003380a  call    cs:__imp_WindowsDuplicateString
0x180033810  mov     esi, eax
0x180033812  test    eax, eax
0x180033814  jns     short loc_18003385E
0x180033816  mov     edx, 55h ; 'U'; void *
0x18003381b  mov     rcx, [rbp+28h]; this
0x18003381f  mov     r9d, esi; char *
0x180033822  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003382e  test    rbx, rbx
0x180033831  jz      short loc_18003383B
0x180033833  mov     rcx, rbx
0x180033836  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(void)
0x18003383b  mov     eax, esi
0x18003383d  mov     rbx, [rsp+20h+arg_0]
0x180033842  mov     rsi, [rsp+20h+arg_10]
0x180033847  add     rsp, 20h
0x18003384b  pop     r15
0x18003384d  pop     r14
0x18003384f  pop     r12
0x180033851  pop     rdi
0x180033852  pop     rbp
0x180033853  retn
0x180033854  mov     esi, 80070216h
0x180033859  jmp     loc_1800335F4
0x18003385e  lea     rsi, [rbx+0C8h]
0x180033865  mov     r14, [rdi+0C8h]
0x18003386c  test    r14, r14
0x18003386f  jnz     loc_1800339C4
0x180033875  mov     rcx, [rsi]; string
0x180033878  call    cs:__imp_WindowsDeleteString
0x18003387e  mov     [rsi], r12
0x180033881  mov     rdx, rsi; newString
0x180033884  mov     rcx, r14; string
0x180033887  call    cs:__imp_WindowsDuplicateString
0x18003388d  mov     esi, eax
0x18003388f  test    eax, eax
0x180033891  js      loc_180033A4C
0x180033897  mov     eax, [rdi+0D0h]
0x18003389d  mov     [rbx+0D0h], eax
0x1800338a3  mov     al, [rdi+0D4h]
0x1800338a9  mov     [rbx+0D4h], al
0x1800338af  mov     al, [rdi+0D5h]
0x1800338b5  mov     [rbx+0D5h], al
0x1800338bb  mov     [rbp+arg_8], r12
0x1800338bf  lea     rcx, [rbp+arg_8]
0x1800338c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800338c8  lea     r8, [rbp+arg_8]
0x1800338cc  lea     rdx, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x1800338d3  mov     rcx, rbx
0x1800338d6  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1800338db  mov     edi, eax
0x1800338dd  test    eax, eax
0x1800338df  jns     loc_1800339D2
0x1800338e5  mov     rcx, [rbp+28h]; this
0x1800338e9  mov     r9d, eax; char *
0x1800338ec  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x1800338f3  mov     edx, 5Bh ; '['; void *
0x1800338f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338fd  nop
0x1800338fe  mov     rcx, [rbp+arg_8]
0x180033902  test    rcx, rcx
0x180033905  jz      short loc_180033918
0x180033907  mov     [rbp+arg_8], r12
0x18003390b  mov     rax, [rcx]
0x18003390e  mov     rax, [rax+10h]
0x180033912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033917  nop
0x180033918  test    rbx, rbx
0x18003391b  jz      short loc_180033925
0x18003391d  mov     rcx, rbx
0x180033920  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(void)
0x180033925  mov     eax, edi
0x180033927  jmp     loc_18003383D
0x18003392c  mov     edx, 54h ; 'T'
0x180033931  jmp     loc_18003381B
0x180033936  mov     edx, 4Bh ; 'K'
0x18003393b  jmp     loc_18003381B
0x180033940  mov     edx, 53h ; 'S'
0x180033945  jmp     loc_18003381B
0x18003394a  cmp     r14, [rsi]
0x18003394d  jnz     loc_180033669
0x180033953  jmp     loc_18003368B
0x180033958  cmp     r14, [rsi]
0x18003395b  jnz     loc_1800336A2
0x180033961  jmp     loc_1800336C4
0x180033966  cmp     r14, [rsi]
0x180033969  jnz     loc_1800336DB
0x18003396f  jmp     loc_1800336FD
0x180033974  cmp     r14, [rsi]
0x180033977  jnz     loc_180033714
0x18003397d  jmp     loc_180033736
0x180033982  cmp     r14, [rsi]
0x180033985  jnz     loc_18003374D
0x18003398b  jmp     loc_18003376F
0x180033990  cmp     r14, [rsi]
0x180033993  jnz     loc_180033786
0x180033999  jmp     loc_1800337A8
0x18003399e  cmp     r14, [rsi]
0x1800339a1  jnz     loc_1800337BF
0x1800339a7  jmp     loc_1800337E1
0x1800339ac  mov     edx, 4Dh ; 'M'
0x1800339b1  jmp     loc_18003381B
0x1800339b6  cmp     r14, [rsi]
0x1800339b9  jnz     loc_1800337F8
0x1800339bf  jmp     loc_18003385E
0x1800339c4  cmp     r14, [rsi]
0x1800339c7  jnz     loc_180033875
0x1800339cd  jmp     loc_180033897
0x1800339d2  mov     rax, [rbp+arg_8]
0x1800339d6  mov     [rbp+arg_8], r12
0x1800339da  mov     [r15], rax
0x1800339dd  lea     rcx, [rbp+arg_8]
0x1800339e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800339e6  test    rbx, rbx
0x1800339e9  jz      short loc_1800339F3
0x1800339eb  mov     rcx, rbx
0x1800339ee  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::Release(void)
0x1800339f3  xor     eax, eax
0x1800339f5  jmp     loc_18003383D
0x1800339fa  lea     rcx, [rbp+arg_18]; this
0x1800339fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033a03  mov     rcx, r14; hKey
0x180033a06  call    cs:__imp_RegCloseKey
0x180033a0c  lea     rcx, [rbp+arg_18]; this
0x180033a10  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033a15  jmp     loc_180033634
0x180033a1a  mov     edx, 4Eh ; 'N'
0x180033a1f  jmp     loc_18003381B
0x180033a24  mov     edx, 4Fh ; 'O'
0x180033a29  jmp     loc_18003381B
0x180033a2e  mov     edx, 50h ; 'P'
0x180033a33  jmp     loc_18003381B
0x180033a38  mov     edx, 51h ; 'Q'
0x180033a3d  jmp     loc_18003381B
0x180033a42  mov     edx, 52h ; 'R'
  ... truncated ...
```
