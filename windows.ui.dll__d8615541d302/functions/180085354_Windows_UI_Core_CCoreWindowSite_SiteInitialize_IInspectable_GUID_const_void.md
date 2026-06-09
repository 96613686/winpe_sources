# Windows::UI::Core::CCoreWindowSite::SiteInitialize(IInspectable *,_GUID const &,void * *)

- ea: `0x180085354`
- end: `0x180085604`
- name: `?SiteInitialize@CCoreWindowSite@Core@UI@Windows@@QEAAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z`
- size: `688`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreWindowSite *__hidden this, struct IInspectable *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180084240`

## callees

- `0x1800038e0`
- `0x18000f048`
- `0x180014754`
- `0x180014e44`
- `0x180016064`
- `0x18004afd8`
- `0x180085354`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180085515`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180085515`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180085528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180085528`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085447`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085447`

## string_xrefs

- `0x18008550e`: `windows.ui.core.textinput.dll`
- `0x1800853e7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180085458`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x18008555b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::SiteInitialize(
        Windows::UI::Core::CCoreWindowSite *this,
        struct IInspectable *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rdx
  LPVOID v15; // rsi
  __int64 (__fastcall *v16)(LPVOID, GUID *, GUID *, char *); // rdi
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  __int64 v19; // rbx
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+30h] [rbp-38h] BYREF
  struct Windows::UI::Core::ICoreWindow *v24; // [rsp+38h] [rbp-30h] BYREF
  __int64 v25; // [rsp+40h] [rbp-28h] BYREF
  struct IInspectable *v26; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v27[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  LPVOID v29; // [rsp+A8h] [rbp+40h] BYREF

  v25 = 0;
  v26 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
  v9 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_f2a57aa9_917a_48d5_8e22_841e6dae347a,
         &v25);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 88;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    goto LABEL_26;
  }
  v27[0] = (char *)this + 112;
  v12 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v27);
  v9 = Microsoft::WRL::AsWeak<Windows::Foundation::Private::IComponentSite>(v25, v12);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 92;
    goto LABEL_5;
  }
  v9 = (**(__int64 (__fastcall ***)(Windows::UI::Core::CCoreWindowSite *, const struct _GUID *, void **))this)(
         this,
         a3,
         a4);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 93;
    goto LABEL_5;
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
  v13 = CoCreateInstance(&CLSID_ShellServiceHostBrokerProvider, 0, 4u, &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf, &v29);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = 97;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v13,
      ppva);
LABEL_11:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
    goto LABEL_26;
  }
  v15 = v29;
  v16 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, char *))(*(_QWORD *)v29 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 136);
  v13 = v16(
          v15,
          &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f,
          &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f,
          (char *)this + 136);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = 98;
    goto LABEL_10;
  }
  v24 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
  *((_BYTE *)this + 96) = (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread(&v24) == 0;
  v23 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
  v23 = 0;
  ProcAddress = (FARPROC)qword_1801354D0;
  if ( !qword_1801354D0
    && ((v10 = -2147467259, (Library = LoadLibraryExW(L"windows.ui.core.textinput.dll", 0, 0x800u)) == 0)
      ? (ProcAddress = (FARPROC)qword_1801354D0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, (LPCSTR)0x5DD), qword_1801354D0 = (__int64)ProcAddress),
        !ProcAddress)
    || (v10 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v23), v10 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v10,
      ppva);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
    goto LABEL_11;
  }
  v19 = v23;
  if ( *((_QWORD *)this + 25) != v23 )
  {
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    v27[0] = *((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = v19;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v27);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
  v10 = 0;
LABEL_26:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180085354  push    rbp
0x180085356  push    rbx
0x180085357  push    rsi
0x180085358  push    rdi
0x180085359  push    r14
0x18008535b  push    r15
0x18008535d  mov     rbp, rsp
0x180085360  sub     rsp, 68h
0x180085364  mov     rsi, r9
0x180085367  mov     r15, r8
0x18008536a  mov     rdi, rdx
0x18008536d  mov     r14, rcx
0x180085370  mov     [rbp+var_28], 0
0x180085378  mov     [rbp+var_20], rdx
0x18008537c  lea     rcx, [rbp+var_20]
0x180085380  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180085385  nop
0x180085386  mov     rax, [rdi]
0x180085389  mov     rbx, [rax]
0x18008538c  lea     rcx, [rbp+var_28]
0x180085390  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085395  lea     r8, [rbp+var_28]
0x180085399  lea     rdx, _GUID_f2a57aa9_917a_48d5_8e22_841e6dae347a
0x1800853a0  mov     rcx, rdi
0x1800853a3  mov     rax, rbx
0x1800853a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853ab  mov     ebx, eax
0x1800853ad  test    eax, eax
0x1800853af  jns     short loc_1800853B8
0x1800853b1  mov     edx, 58h ; 'X'
0x1800853b6  jmp     short loc_1800853E0
0x1800853b8  lea     rax, [r14+70h]
0x1800853bc  mov     [rbp+var_18], rax
0x1800853c0  lea     rcx, [rbp+var_18]
0x1800853c4  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1800853c9  mov     rdx, rax
0x1800853cc  mov     rcx, [rbp+var_28]
0x1800853d0  call    ??$AsWeak@UIComponentSite@Private@Foundation@Windows@@@WRL@Microsoft@@YAJPEAUIComponentSite@Private@Foundation@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Foundation::Private::IComponentSite>(Windows::Foundation::Private::IComponentSite *,Microsoft::WRL::WeakRef *)
0x1800853d5  mov     ebx, eax
0x1800853d7  test    eax, eax
0x1800853d9  jns     short loc_1800853F8
0x1800853db  mov     edx, 5Ch ; '\'; void *
0x1800853e0  mov     rcx, [rbp+30h]; this
0x1800853e4  mov     r9d, eax; char *
0x1800853e7  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800853ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800853f3  jmp     loc_1800855E2
0x1800853f8  mov     rax, [r14]
0x1800853fb  mov     r8, rsi
0x1800853fe  mov     rdx, r15
0x180085401  mov     rcx, r14
0x180085404  mov     rax, [rax]
0x180085407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008540c  mov     ebx, eax
0x18008540e  test    eax, eax
0x180085410  jns     short loc_180085419
0x180085412  mov     edx, 5Dh ; ']'
0x180085417  jmp     short loc_1800853E0
0x180085419  mov     [rbp+arg_8], 0
0x180085421  lea     rcx, [rbp+arg_8]
0x180085425  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008542a  lea     rax, [rbp+arg_8]
0x18008542e  mov     qword ptr [rsp+68h+ppv], rax; int
0x180085433  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x18008543a  xor     edx, edx; pUnkOuter
0x18008543c  lea     r8d, [rdx+4]; dwClsContext
0x180085440  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x180085447  call    cs:__imp_CoCreateInstance
0x18008544d  mov     ebx, eax
0x18008544f  test    eax, eax
0x180085451  jns     short loc_18008547A
0x180085453  mov     edx, 61h ; 'a'; void *
0x180085458  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18008545f  mov     r9d, eax; char *
0x180085462  mov     rcx, [rbp+30h]; this
0x180085466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008546b  nop
0x18008546c  lea     rcx, [rbp+arg_8]
0x180085470  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085475  jmp     loc_1800855E2
0x18008547a  mov     rsi, [rbp+arg_8]
0x18008547e  mov     rax, [rsi]
0x180085481  mov     rdi, [rax+18h]
0x180085485  lea     rbx, [r14+88h]
0x18008548c  mov     rcx, rbx
0x18008548f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085494  mov     r9, rbx
0x180085497  lea     rdx, _GUID_1f79f7de_20bf_4591_930a_d490b78fb09f
0x18008549e  mov     r8, rdx
0x1800854a1  mov     rcx, rsi
0x1800854a4  mov     rax, rdi
0x1800854a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854ac  mov     ebx, eax
0x1800854ae  test    eax, eax
0x1800854b0  jns     short loc_1800854B9
0x1800854b2  mov     edx, 62h ; 'b'
0x1800854b7  jmp     short loc_180085458
0x1800854b9  mov     [rbp+var_30], 0
0x1800854c1  lea     rcx, [rbp+var_30]
0x1800854c5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800854ca  lea     rcx, [rbp+var_30]; struct Windows::UI::Core::ICoreWindow **
0x1800854ce  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x1800854d3  test    eax, eax
0x1800854d5  setz    al
0x1800854d8  mov     [r14+60h], al
0x1800854dc  mov     [rbp+var_38], 0
0x1800854e4  lea     rcx, [rbp+var_38]
0x1800854e8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800854ed  mov     [rbp+var_38], 0
0x1800854f5  mov     rax, cs:qword_1801354D0
0x1800854fc  test    rax, rax
0x1800854ff  jnz     short loc_180085543
0x180085501  mov     ebx, 80004005h
0x180085506  xor     edx, edx; hFile
0x180085508  mov     r8d, 800h; dwFlags
0x18008550e  lea     rcx, LibFileName; "windows.ui.core.textinput.dll"
0x180085515  call    cs:__imp_LoadLibraryExW
0x18008551b  test    rax, rax
0x18008551e  jz      short loc_180085537
0x180085520  mov     edx, 5DDh; lpProcName
0x180085525  mov     rcx, rax; hModule
0x180085528  call    cs:__imp_GetProcAddress
0x18008552e  mov     cs:qword_1801354D0, rax
0x180085535  jmp     short loc_18008553E
0x180085537  mov     rax, cs:qword_1801354D0
0x18008553e  test    rax, rax
0x180085541  jz      short loc_180085554
0x180085543  lea     rdx, [rbp+var_38]
0x180085547  xor     ecx, ecx
0x180085549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008554e  mov     ebx, eax
0x180085550  test    eax, eax
0x180085552  jns     short loc_180085585
0x180085554  mov     rcx, [rbp+30h]; this
0x180085558  mov     r9d, ebx; char *
0x18008555b  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180085562  mov     edx, 69h ; 'i'; void *
0x180085567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008556c  nop
0x18008556d  lea     rcx, [rbp+var_38]
0x180085571  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085576  nop
0x180085577  lea     rcx, [rbp+var_30]
0x18008557b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085580  jmp     loc_18008546C
0x180085585  mov     rbx, [rbp+var_38]
0x180085589  cmp     [r14+0C8h], rbx
0x180085590  jz      short loc_1800855C3
0x180085592  test    rbx, rbx
0x180085595  jz      short loc_1800855A7
0x180085597  mov     rax, [rbx]
0x18008559a  mov     rcx, rbx
0x18008559d  mov     rax, [rax+8]
0x1800855a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855a6  nop
0x1800855a7  mov     rax, [r14+0C8h]
0x1800855ae  mov     [rbp+var_18], rax
0x1800855b2  mov     [r14+0C8h], rbx
0x1800855b9  lea     rcx, [rbp+var_18]
0x1800855bd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855c2  nop
0x1800855c3  lea     rcx, [rbp+var_38]
0x1800855c7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855cc  nop
0x1800855cd  lea     rcx, [rbp+var_30]
0x1800855d1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855d6  nop
0x1800855d7  lea     rcx, [rbp+arg_8]
0x1800855db  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855e0  xor     ebx, ebx
0x1800855e2  lea     rcx, [rbp+var_20]
0x1800855e6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855eb  nop
0x1800855ec  lea     rcx, [rbp+var_28]
0x1800855f0  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800855f5  mov     eax, ebx
0x1800855f7  add     rsp, 68h
0x1800855fb  pop     r15
0x1800855fd  pop     r14
0x1800855ff  pop     rdi
0x180085600  pop     rsi
0x180085601  pop     rbx
0x180085602  pop     rbp
0x180085603  retn
```
