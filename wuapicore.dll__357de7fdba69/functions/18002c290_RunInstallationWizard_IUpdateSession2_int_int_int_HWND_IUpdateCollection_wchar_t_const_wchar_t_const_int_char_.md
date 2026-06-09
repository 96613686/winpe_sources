# RunInstallationWizard(IUpdateSession2 *,int,int,int,HWND__ *,IUpdateCollection *,wchar_t const *,wchar_t const *,int,char const *,IInstallationResult * *)

- ea: `0x18002c290`
- end: `0x18002c587`
- name: `?RunInstallationWizard@@YAJPEAUIUpdateSession2@@HHHPEAUHWND__@@PEAUIUpdateCollection@@PEB_W3HPEBDPEAPEAUIInstallationResult@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(struct IUpdateSession2 *, int, int, int, HWND, struct IUpdateCollection *, const wchar_t *, const wchar_t *, int, const char *, struct IInstallationResult **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006b3dc`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180027444`
- `0x18002c290`
- `0x18004bd8c`
- `0x18009567c`
- `0x18009b050`
- `0x18009b24c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c48a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c4da`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c532`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c48a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c4da`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002c532`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c493`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c4e3`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c53b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c493`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c4e3`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002c53b`
- `COMCTL32!InitCommonControlsEx` at `0x18002c2e6`
- `COMCTL32!InitCommonControlsEx` at `0x18002c44e`
- `COMCTL32!InitCommonControlsEx` at `0x18002c2e6`
- `COMCTL32!InitCommonControlsEx` at `0x18002c44e`

## string_xrefs

- `0x18002c2fc`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`
- `0x18002c387`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RunInstallationWizard(
        struct IUpdateSession2 *a1,
        int a2,
        int a3,
        int a4,
        HWND a5,
        struct IUpdateCollection *a6,
        wchar_t *a7,
        wchar_t *a8,
        int a9,
        char *a10,
        struct IInstallationResult **a11)
{
  int LastError; // ebx
  CInstallationWizard *v16; // r10
  CInstallationWizard *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  void *v23; // r14
  HWND *v24; // r8
  const char *v25; // r9
  int v27; // [rsp+28h] [rbp-71h]
  int v28; // [rsp+78h] [rbp-21h] BYREF
  ULONG_PTR ulCookie; // [rsp+80h] [rbp-19h] BYREF
  INITCOMMONCONTROLSEX v30; // [rsp+88h] [rbp-11h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+27h]

  picce.dwSize = 8;
  picce.dwICC = 32816;
  if ( !InitCommonControlsEx(&picce) )
  {
    LastError = -2145124285;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA71,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)0x80240043LL,
      v27);
    return (unsigned int)LastError;
  }
  v16 = (CInstallationWizard *)operator new(0x2E8u, (const struct std::nothrow_t *)&std::nothrow);
  v30 = (INITCOMMONCONTROLSEX)v16;
  if ( v16 )
    v17 = CInstallationWizard::CInstallationWizard(v16, a1, a2, a3, a4, a5, a6, a7, a8, a9, a10);
  else
    v17 = 0;
  if ( !v17 )
  {
    LastError = -2147024882;
    v18 = 2688;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)(unsigned int)LastError,
      v27);
    goto LABEL_40;
  }
  v28 = 0;
  ulCookie = 0;
  if ( !a11 )
  {
    LastError = -2147467261;
    v19 = 96;
LABEL_10:
    v20 = (unsigned int)LastError;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)v20,
      v27);
LABEL_33:
    v18 = 2690;
    goto LABEL_34;
  }
  *a11 = 0;
  LastError = *((_DWORD *)v17 + 176);
  if ( LastError < 0 )
  {
    v19 = 101;
    goto LABEL_10;
  }
  v21 = *((_QWORD *)v17 + 13);
  if ( !v21 )
  {
    LastError = -2145124348;
    v19 = 103;
    goto LABEL_10;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 80LL))(v21, &v28);
  LastError = v22;
  if ( v22 < 0 )
  {
    v20 = (unsigned int)v22;
    v19 = 107;
    goto LABEL_11;
  }
  if ( v28 <= 0 )
  {
    LastError = -2145124316;
    v19 = 109;
    goto LABEL_10;
  }
  v23 = CreateAndActivateContext(&ulCookie);
  v30.dwSize = 8;
  v30.dwICC = 49200;
  InitCommonControlsEx(&v30);
  if ( CSimpleDialogBase::DoModal((LPARAM)v17, *((HWND *)v17 + 12), v24) == -1 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
                  v25);
    if ( v23 != (void *)-1LL )
    {
      if ( ulCookie )
        DeactivateActCtx(0, ulCookie);
      ReleaseActCtx(v23);
    }
    if ( LastError < 0 )
      goto LABEL_33;
  }
  else
  {
    LastError = *((_DWORD *)v17 + 184);
    if ( LastError < 0 && LastError != -2145124317 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
        (const char *)(unsigned int)LastError,
        v27);
      if ( v23 != (void *)-1LL )
      {
        if ( ulCookie )
          DeactivateActCtx(0, ulCookie);
        ReleaseActCtx(v23);
      }
      goto LABEL_33;
    }
    *a11 = (struct IInstallationResult *)((*((_QWORD *)v17 + 16) + 8LL) & -(__int64)(*((_QWORD *)v17 + 16) != 0));
    *((_QWORD *)v17 + 16) = 0;
    if ( v23 != (void *)-1LL )
    {
      if ( ulCookie )
        DeactivateActCtx(0, ulCookie);
      ReleaseActCtx(v23);
    }
  }
  LastError = 0;
LABEL_40:
  if ( v17 )
    (*(void (__fastcall **)(CInstallationWizard *))(*(_QWORD *)v17 + 24LL))(v17);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002c290  mov     rax, rsp
0x18002c293  mov     [rax+8], rbx
0x18002c297  mov     [rax+10h], rsi
0x18002c29b  mov     [rax+18h], rdi
0x18002c29f  mov     [rax+20h], r12
0x18002c2a3  push    rbp
0x18002c2a4  push    r14
0x18002c2a6  push    r15
0x18002c2a8  lea     rbp, [rax-27h]
0x18002c2ac  sub     rsp, 0A0h
0x18002c2b3  mov     rax, cs:__security_cookie
0x18002c2ba  xor     rax, rsp
0x18002c2bd  mov     [rbp+1Fh+var_20], rax
0x18002c2c1  mov     ebx, r9d
0x18002c2c4  mov     edi, r8d
0x18002c2c7  mov     esi, edx
0x18002c2c9  mov     r14, rcx
0x18002c2cc  mov     r12, [rbp+1Fh+arg_48]
0x18002c2d0  mov     r15, [rbp+1Fh+arg_50]
0x18002c2d4  mov     [rbp+1Fh+picce.dwSize], 8
0x18002c2db  mov     [rbp+1Fh+picce.dwICC], 8030h
0x18002c2e2  lea     rcx, [rbp+1Fh+picce]; picce
0x18002c2e6  call    cs:__imp_InitCommonControlsEx
0x18002c2ec  test    eax, eax
0x18002c2ee  jnz     short loc_18002C312
0x18002c2f0  mov     rcx, [rbp+27h]; this
0x18002c2f4  mov     ebx, 80240043h
0x18002c2f9  mov     r9d, ebx; char *
0x18002c2fc  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x18002c303  mov     edx, 0A71h; void *
0x18002c308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c30d  jmp     loc_18002C558
0x18002c312  mov     [rbp+1Fh+var_50], 0
0x18002c31a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c321  mov     ecx, 2E8h; unsigned __int64
0x18002c326  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c32b  mov     r10, rax
0x18002c32e  mov     qword ptr [rbp+1Fh+var_30.dwSize], rax
0x18002c332  test    rax, rax
0x18002c335  jz      short loc_18002C381
0x18002c337  mov     [rsp+0B0h+var_60], r12; char *
0x18002c33c  mov     ecx, [rbp+1Fh+arg_40]
0x18002c33f  mov     [rsp+0B0h+var_68], ecx; int
0x18002c343  mov     rcx, [rbp+1Fh+arg_38]
0x18002c347  mov     [rsp+0B0h+var_70], rcx; wchar_t *
0x18002c34c  mov     rcx, [rbp+1Fh+arg_30]
0x18002c350  mov     [rsp+0B0h+var_78], rcx; wchar_t *
0x18002c355  mov     rcx, [rbp+1Fh+arg_28]
0x18002c359  mov     [rsp+0B0h+var_80], rcx; struct IUpdateCollection *
0x18002c35e  mov     rax, [rbp+1Fh+arg_20]
0x18002c362  mov     [rsp+0B0h+var_88], rax; HWND
0x18002c367  mov     [rsp+0B0h+var_90], ebx; int
0x18002c36b  mov     r9d, edi; int
0x18002c36e  mov     r8d, esi; int
0x18002c371  mov     rdx, r14; struct IUpdateSession2 *
0x18002c374  mov     rcx, r10; this
0x18002c377  call    ??0CInstallationWizard@@QEAA@PEAUIUpdateSession2@@HHHPEAUHWND__@@PEAUIUpdateCollection@@PEB_W3HPEBD@Z; CInstallationWizard::CInstallationWizard(IUpdateSession2 *,int,int,int,HWND__ *,IUpdateCollection *,wchar_t const *,wchar_t const *,int,char const *)
0x18002c37c  mov     rdi, rax
0x18002c37f  jmp     short loc_18002C383
0x18002c381  xor     edi, edi
0x18002c383  mov     [rbp+1Fh+var_50], rdi
0x18002c387  lea     rsi, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x18002c38e  test    rdi, rdi
0x18002c391  jnz     short loc_18002C3A2
0x18002c393  mov     ebx, 8007000Eh
0x18002c398  mov     edx, 0A80h
0x18002c39d  jmp     loc_18002C4EE
0x18002c3a2  mov     [rbp+1Fh+var_40], 0
0x18002c3a9  mov     [rbp+1Fh+ulCookie], 0
0x18002c3b1  test    r15, r15
0x18002c3b4  jnz     short loc_18002C3D3
0x18002c3b6  mov     ebx, 80004003h
0x18002c3bb  lea     edx, [r15+60h]; void *
0x18002c3bf  mov     r9d, ebx; char *
0x18002c3c2  mov     rcx, [rbp+27h]; this
0x18002c3c6  mov     r8, rsi; unsigned int
0x18002c3c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3ce  jmp     loc_18002C4E9
0x18002c3d3  mov     qword ptr [r15], 0
0x18002c3da  mov     ebx, [rdi+2C0h]
0x18002c3e0  test    ebx, ebx
0x18002c3e2  jns     short loc_18002C3EB
0x18002c3e4  mov     edx, 65h ; 'e'
0x18002c3e9  jmp     short loc_18002C3BF
0x18002c3eb  mov     rcx, [rdi+68h]
0x18002c3ef  test    rcx, rcx
0x18002c3f2  jnz     short loc_18002C3FE
0x18002c3f4  mov     ebx, 80240004h
0x18002c3f9  lea     edx, [rcx+67h]
0x18002c3fc  jmp     short loc_18002C3BF
0x18002c3fe  mov     rax, [rcx]
0x18002c401  lea     rdx, [rbp+1Fh+var_40]
0x18002c405  mov     rax, [rax+50h]
0x18002c409  call    _guard_dispatch_icall
0x18002c40e  mov     ebx, eax
0x18002c410  test    eax, eax
0x18002c412  jns     short loc_18002C41E
0x18002c414  mov     r9d, eax
0x18002c417  mov     edx, 6Bh ; 'k'
0x18002c41c  jmp     short loc_18002C3C2
0x18002c41e  cmp     [rbp+1Fh+var_40], 0
0x18002c422  jg      short loc_18002C430
0x18002c424  mov     ebx, 80240024h
0x18002c429  mov     edx, 6Dh ; 'm'
0x18002c42e  jmp     short loc_18002C3BF
0x18002c430  lea     rcx, [rbp+1Fh+ulCookie]; lpCookie
0x18002c434  call    ?CreateAndActivateContext@@YAPEAXPEA_K@Z; CreateAndActivateContext(unsigned __int64 *)
0x18002c439  mov     r14, rax
0x18002c43c  mov     [rbp+1Fh+var_30.dwSize], 8
0x18002c443  mov     [rbp+1Fh+var_30.dwICC], 0C030h
0x18002c44a  lea     rcx, [rbp+1Fh+var_30]; picce
0x18002c44e  call    cs:__imp_InitCommonControlsEx
0x18002c454  mov     rdx, [rdi+60h]; hWndParent
0x18002c458  mov     rcx, rdi; dwInitParam
0x18002c45b  call    ?DoModal@CSimpleDialogBase@@QEAA_JPEAUHWND__@@PEAPEAU2@@Z; CSimpleDialogBase::DoModal(HWND__ *,HWND__ * *)
0x18002c460  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c464  jnz     short loc_18002C4A3
0x18002c466  mov     rcx, [rbp+27h]; this
0x18002c46a  mov     r8, rsi; unsigned int
0x18002c46d  mov     edx, 81h; void *
0x18002c472  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c477  mov     ebx, eax
0x18002c479  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c47d  jz      short loc_18002C499
0x18002c47f  mov     rdx, [rbp+1Fh+ulCookie]; ulCookie
0x18002c483  test    rdx, rdx
0x18002c486  jz      short loc_18002C490
0x18002c488  xor     ecx, ecx; dwFlags
0x18002c48a  call    cs:__imp_DeactivateActCtx
0x18002c490  mov     rcx, r14; hActCtx
0x18002c493  call    cs:__imp_ReleaseActCtx
0x18002c499  test    ebx, ebx
0x18002c49b  jns     loc_18002C541
0x18002c4a1  jmp     short loc_18002C4E9
0x18002c4a3  mov     ebx, [rdi+2E0h]
0x18002c4a9  test    ebx, ebx
0x18002c4ab  jns     short loc_18002C4FF
0x18002c4ad  cmp     ebx, 80240023h
0x18002c4b3  jz      short loc_18002C4FF
0x18002c4b5  mov     rcx, [rbp+27h]; this
0x18002c4b9  mov     r9d, ebx; char *
0x18002c4bc  mov     r8, rsi; unsigned int
0x18002c4bf  mov     edx, 87h; void *
0x18002c4c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4c9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c4cd  jz      short loc_18002C4E9
0x18002c4cf  mov     rdx, [rbp+1Fh+ulCookie]; ulCookie
0x18002c4d3  test    rdx, rdx
0x18002c4d6  jz      short loc_18002C4E0
0x18002c4d8  xor     ecx, ecx; dwFlags
0x18002c4da  call    cs:__imp_DeactivateActCtx
0x18002c4e0  mov     rcx, r14; hActCtx
0x18002c4e3  call    cs:__imp_ReleaseActCtx
0x18002c4e9  mov     edx, 0A82h; void *
0x18002c4ee  mov     rcx, [rbp+27h]; this
0x18002c4f2  mov     r9d, ebx; char *
0x18002c4f5  mov     r8, rsi; unsigned int
0x18002c4f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4fd  jmp     short loc_18002C543
0x18002c4ff  mov     rax, [rdi+80h]
0x18002c506  lea     rcx, [rax+8]
0x18002c50a  neg     rax
0x18002c50d  sbb     rax, rax
0x18002c510  and     rax, rcx
0x18002c513  mov     [r15], rax
0x18002c516  mov     qword ptr [rdi+80h], 0
0x18002c521  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c525  jz      short loc_18002C541
0x18002c527  mov     rdx, [rbp+1Fh+ulCookie]; ulCookie
0x18002c52b  test    rdx, rdx
0x18002c52e  jz      short loc_18002C538
0x18002c530  xor     ecx, ecx; dwFlags
0x18002c532  call    cs:__imp_DeactivateActCtx
0x18002c538  mov     rcx, r14; hActCtx
0x18002c53b  call    cs:__imp_ReleaseActCtx
0x18002c541  xor     ebx, ebx
0x18002c543  test    rdi, rdi
0x18002c546  jz      short loc_18002C558
0x18002c548  mov     rcx, [rdi]
0x18002c54b  mov     rax, [rcx+18h]
0x18002c54f  mov     rcx, rdi
0x18002c552  call    _guard_dispatch_icall
0x18002c557  nop
0x18002c558  mov     eax, ebx
0x18002c55a  mov     rcx, [rbp+1Fh+var_20]
0x18002c55e  xor     rcx, rsp; StackCookie
0x18002c561  call    __security_check_cookie
0x18002c566  lea     r11, [rsp+0B0h+var_10]
0x18002c56e  mov     rbx, [r11+20h]
0x18002c572  mov     rsi, [r11+28h]
0x18002c576  mov     rdi, [r11+30h]
0x18002c57a  mov     r12, [r11+38h]
0x18002c57e  mov     rsp, r11
0x18002c581  pop     r15
0x18002c583  pop     r14
0x18002c585  pop     rbp
0x18002c586  retn
```
