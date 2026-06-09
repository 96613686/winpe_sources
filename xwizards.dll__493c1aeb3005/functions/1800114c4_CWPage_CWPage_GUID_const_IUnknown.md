# CWPage::CWPage(_GUID const *,IUnknown *)

- ea: `0x1800114c4`
- end: `0x180011684`
- name: `??0CWPage@@AEAA@PEBU_GUID@@PEAUIUnknown@@@Z`
- size: `448`
- prototype: `CWPage *(CWPage *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011cc8`

## callees

- `0x18000ae04`
- `0x1800114c4`
- `0x18001c19c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001161c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011658`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001166c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001161c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011658`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001166c`

## string_xrefs

- `0x18001164d`: `XWOnCommit`

## pseudocode

```c
CWPage *__fastcall CWPage::CWPage(CWPage *this, const struct _GUID *a2, struct IUnknown *a3)
{
  struct IUnknown *v3; // rax
  HMODULE *v5; // rdi
  int WizardCommonModule; // eax
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  HMODULE v20; // rcx
  FARPROC v21; // rax
  HMODULE v22; // rcx

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CUnknown::`vftable';
  v3 = (struct IUnknown *)this;
  if ( a3 )
    v3 = a3;
  *((_QWORD *)this + 2) = v3;
  _InterlockedIncrement(&CUnknown::s_cActiveComponents);
  v5 = (HMODULE *)((char *)this + 48);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = &CWPage::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWPage::`vftable'{for `IXWizardPageEvent'};
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 6) = 0;
  *((struct _GUID *)this + 2) = *a2;
  WizardCommonModule = HrGetWizardCommonModule(a2, (HINSTANCE *)this + 6);
  if ( WizardCommonModule >= 0 )
  {
    ProcAddress = GetProcAddress(*v5, "XWCanRunPage");
    v8 = *v5;
    *((_QWORD *)this + 7) = ProcAddress;
    v9 = GetProcAddress(v8, "XWCanRegisterPage");
    v10 = *v5;
    *((_QWORD *)this + 8) = v9;
    v11 = GetProcAddress(v10, "XWCanUnregisterPage");
    v12 = *v5;
    *((_QWORD *)this + 9) = v11;
    v13 = GetProcAddress(v12, "XWCanNavigateChildPage");
    v14 = *v5;
    *((_QWORD *)this + 10) = v13;
    v15 = GetProcAddress(v14, "XWOnRecycleChildPage");
    v16 = *v5;
    *((_QWORD *)this + 11) = v15;
    v17 = GetProcAddress(v16, "XWOnApply");
    v18 = *v5;
    *((_QWORD *)this + 12) = v17;
    v19 = GetProcAddress(v18, "XWOnReset");
    v20 = *v5;
    *((_QWORD *)this + 13) = v19;
    v21 = GetProcAddress(v20, "XWOnCommit");
    v22 = *v5;
    *((_QWORD *)this + 14) = v21;
    *((_QWORD *)this + 15) = GetProcAddress(v22, "XWOnAbort");
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids,
      (unsigned int)WizardCommonModule);
  }
  return this;
}

```

## disassembly

```asm
0x1800114c4  mov     [rsp+arg_0], rbx
0x1800114c9  push    rdi
0x1800114ca  sub     rsp, 20h
0x1800114ce  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x1800114d5  mov     dword ptr [rcx+8], 1
0x1800114dc  mov     [rcx], rax
0x1800114df  test    r8, r8
0x1800114e2  mov     rax, rcx
0x1800114e5  mov     r9, rdx
0x1800114e8  cmovnz  rax, r8
0x1800114ec  mov     rbx, rcx
0x1800114ef  mov     [rcx+10h], rax
0x1800114f3  lock inc cs:?s_cActiveComponents@CUnknown@@0JA; long CUnknown::s_cActiveComponents
0x1800114fa  lea     rdi, [rcx+30h]
0x1800114fe  mov     qword ptr [rcx+80h], 0
0x180011509  mov     qword ptr [rcx+38h], 0
0x180011511  lea     rax, ??_7CWPage@@6BCUnknown@@@; const CWPage::`vftable'{for `CUnknown'}
0x180011518  mov     [rcx], rax
0x18001151b  lea     rax, ??_7CWPage@@6BIXWizardPageEvent@@@; const CWPage::`vftable'{for `IXWizardPageEvent'}
0x180011522  mov     [rcx+18h], rax
0x180011526  mov     qword ptr [rcx+40h], 0
0x18001152e  mov     qword ptr [rcx+48h], 0
0x180011536  mov     qword ptr [rcx+50h], 0
0x18001153e  mov     qword ptr [rcx+58h], 0
0x180011546  mov     qword ptr [rcx+60h], 0
0x18001154e  mov     qword ptr [rcx+68h], 0
0x180011556  mov     qword ptr [rcx+70h], 0
0x18001155e  mov     qword ptr [rcx+78h], 0
0x180011566  mov     qword ptr [rdi], 0
0x18001156d  movups  xmm0, xmmword ptr [rdx]
0x180011570  mov     rdx, rdi; HINSTANCE *
0x180011573  movdqu  xmmword ptr [rcx+20h], xmm0
0x180011578  mov     rcx, r9; struct _GUID *
0x18001157b  call    ?HrGetWizardCommonModule@@YAJPEBU_GUID@@PEAPEAUHINSTANCE__@@@Z; HrGetWizardCommonModule(_GUID const *,HINSTANCE__ * *)
0x180011580  test    eax, eax
0x180011582  jns     short loc_1800115C2
0x180011584  mov     rcx, cs:WPP_GLOBAL_Control
0x18001158b  lea     rdx, WPP_GLOBAL_Control
0x180011592  cmp     rcx, rdx
0x180011595  jz      loc_180011676
0x18001159b  test    byte ptr [rcx+1Ch], 4
0x18001159f  jz      loc_180011676
0x1800115a5  mov     rcx, [rcx+10h]
0x1800115a9  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x1800115b0  mov     edx, 0Ah
0x1800115b5  mov     r9d, eax
0x1800115b8  call    WPP_SF_d
0x1800115bd  jmp     loc_180011676
0x1800115c2  mov     rcx, [rdi]; hModule
0x1800115c5  lea     rdx, aXwcanrunpage; "XWCanRunPage"
0x1800115cc  call    cs:__imp_GetProcAddress
0x1800115d2  mov     rcx, [rdi]; hModule
0x1800115d5  lea     rdx, aXwcanregisterp; "XWCanRegisterPage"
0x1800115dc  mov     [rbx+38h], rax
0x1800115e0  call    cs:__imp_GetProcAddress
0x1800115e6  mov     rcx, [rdi]; hModule
0x1800115e9  lea     rdx, aXwcanunregiste; "XWCanUnregisterPage"
0x1800115f0  mov     [rbx+40h], rax
0x1800115f4  call    cs:__imp_GetProcAddress
0x1800115fa  mov     rcx, [rdi]; hModule
0x1800115fd  lea     rdx, aXwcannavigatec; "XWCanNavigateChildPage"
0x180011604  mov     [rbx+48h], rax
0x180011608  call    cs:__imp_GetProcAddress
0x18001160e  mov     rcx, [rdi]; hModule
0x180011611  lea     rdx, aXwonrecyclechi; "XWOnRecycleChildPage"
0x180011618  mov     [rbx+50h], rax
0x18001161c  call    cs:__imp_GetProcAddress
0x180011622  mov     rcx, [rdi]; hModule
0x180011625  lea     rdx, aXwonapply; "XWOnApply"
0x18001162c  mov     [rbx+58h], rax
0x180011630  call    cs:__imp_GetProcAddress
0x180011636  mov     rcx, [rdi]; hModule
0x180011639  lea     rdx, aXwonreset; "XWOnReset"
0x180011640  mov     [rbx+60h], rax
0x180011644  call    cs:__imp_GetProcAddress
0x18001164a  mov     rcx, [rdi]; hModule
0x18001164d  lea     rdx, aXwoncommit; "XWOnCommit"
0x180011654  mov     [rbx+68h], rax
0x180011658  call    cs:__imp_GetProcAddress
0x18001165e  mov     rcx, [rdi]; hModule
0x180011661  lea     rdx, aXwonabort; "XWOnAbort"
0x180011668  mov     [rbx+70h], rax
0x18001166c  call    cs:__imp_GetProcAddress
0x180011672  mov     [rbx+78h], rax
0x180011676  mov     rax, rbx
0x180011679  mov     rbx, [rsp+28h+arg_0]
0x18001167e  add     rsp, 20h
0x180011682  pop     rdi
0x180011683  retn
```
