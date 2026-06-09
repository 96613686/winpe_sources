# CShellItem::GetDisplayName(_SIGDN,ushort * *)

- ea: `0x1800cf710`
- end: `0x1800cfc29`
- name: `?GetDisplayName@CShellItem@@UEAAJW4_SIGDN@@PEAPEAG@Z`
- size: `1305`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, enum _SIGDN, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cf710`
- `0x1800cfc30`
- `0x1800cfd30`
- `0x1800d0990`
- `0x1800dd190`
- `0x180209cd0`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x180628830`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cf9bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cf9bc`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cfb4d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cfb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cf947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cf947`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800cf7f0`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800cf7f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf7b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf7b3`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800cfbaa`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800cfbaa`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800cfb6f`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800cfb6f`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf79e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf79e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf8e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfaab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfbb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf8e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfaab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfbb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc0b`
- `SHCORE!__imp_StrRetToStrW` at `0x1800cf8a5`
- `SHCORE!__imp_StrRetToStrW` at `0x1800cf8a5`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cf9e6`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cfbe5`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cf9e6`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cfbe5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cf8f9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfaf6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfbc8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cf8f9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfaf6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfbc8`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_IShellFolder_GetDisplayNameOf` at `0x1800cf889`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_IShellFolder_GetDisplayNameOf` at `0x1800cf889`

## string_xrefs

- `0x1800cfa0e`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellItem::GetDisplayName(CShellItem *this, enum _SIGDN a2, unsigned __int16 **a3)
{
  char *v6; // rsi
  int v7; // ebx
  int v8; // eax
  DWORD CurrentThreadId; // r14d
  HRESULT ApartmentType; // ebx
  struct IUnknown **v11; // r12
  HRESULT DisplayNameOf; // r14d
  const WCHAR *v13; // rcx
  const struct _ITEMIDLIST_RELATIVE *v15; // rcx
  int v16; // ecx
  __int64 v17; // rax
  int v18; // eax
  int cchValue; // [rsp+20h] [rbp-E0h]
  struct _ITEMIDLIST_RELATIVE *pv; // [rsp+30h] [rbp-D0h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+48h] [rbp-B8h] BYREF
  APTTYPE pAptType[4]; // [rsp+50h] [rbp-B0h] BYREF
  STRRET pstr; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszUrl[2088]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1308h] [rbp+1208h]

  *a3 = 0;
  v6 = (char *)this + 72;
  if ( this == (CShellItem *)8 )
    v6 = 0;
  v7 = *((_DWORD *)v6 + 11);
  if ( v7 != 2 )
  {
    v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    {
LABEL_5:
      if ( v8 != 1 )
        goto LABEL_16;
      goto LABEL_6;
    }
    if ( GetModuleFileNameW(0, (LPWSTR)&pstr, 0x104u) )
    {
      v16 = (FindStringOrdinal(0x800000u, (LPCWSTR)&pstr, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v16;
    }
    else
    {
      v16 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    }
    if ( v16 != 1 )
      goto LABEL_16;
    if ( v7 == 1 )
    {
      if ( (unsigned int)IsAppCompatModeEnabled(16) )
      {
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
        goto LABEL_16;
      }
      v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_5;
    }
  }
LABEL_6:
  if ( *((_DWORD *)v6 + 10) != -3 )
  {
    CurrentThreadId = 0;
    pAptType[0] = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      if ( pAptType[0] == APTTYPE_MAINSTA || pAptType[0] == APTTYPE_STA )
      {
        CurrentThreadId = GetCurrentThreadId();
      }
      else if ( pAptType[0] == APTTYPE_NA )
      {
        CurrentThreadId = -1;
      }
      if ( CurrentThreadId != *((_DWORD *)v6 + 10) )
        ApartmentType = -2147417842;
    }
    if ( ApartmentType < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
        (const char *)(unsigned int)ApartmentType,
        cchValue);
      goto LABEL_18;
    }
  }
LABEL_16:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v6) )
    ApartmentType = 0;
LABEL_18:
  if ( ApartmentType < 0 )
  {
    DisplayNameOf = ApartmentType;
    goto LABEL_32;
  }
  if ( a2 == SIGDN_FILESYSPATH )
  {
    v13 = (const WCHAR *)*((_QWORD *)this + 24);
    if ( v13 )
    {
      DisplayNameOf = SHStrDupW(v13, a3);
      goto LABEL_32;
    }
    pAptQualifier[0] = 0x40000000;
    if ( (*(unsigned int (__fastcall **)(CShellItem *, __int64, APTTYPEQUALIFIER *))(*(_QWORD *)this + 48LL))(
           this,
           0x40000000,
           pAptQualifier) )
    {
      DisplayNameOf = -2147024809;
      goto LABEL_32;
    }
  }
  *(_QWORD *)pAptType = 0;
  v11 = (struct IUnknown **)((char *)this + 168);
  if ( *((_QWORD *)this + 21) )
  {
LABEL_21:
    DisplayNameOf = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, APTTYPE *))(*v11)->lpVtbl->QueryInterface)(
                      *v11,
                      &GUID_000214e6_0000_0000_c000_000000000046,
                      pAptType);
    if ( DisplayNameOf < 0 )
      goto LABEL_32;
    memset_0(&pstr, 0, sizeof(pstr));
    DisplayNameOf = IShellFolder_GetDisplayNameOf(
                      *(_QWORD *)pAptType,
                      *((_QWORD *)this + 17),
                      (unsigned __int16)a2,
                      &pstr,
                      0);
    if ( DisplayNameOf < 0 )
      goto LABEL_25;
    DisplayNameOf = StrRetToStrW(&pstr, *((LPCITEMIDLIST *)this + 17), a3);
    if ( DisplayNameOf < 0 || (unsigned __int16)a2 == a2 )
      goto LABEL_25;
    DisplayNameOf = 0;
    if ( a2 == SIGDN_URL && !UrlIsW(*a3, URLIS_URL) )
    {
      pAptQualifier[0] = 2084;
      if ( (unsigned int)CShellItem::_IsAttrib((CShellItem *)((char *)this - 8), 0x40000000u)
        && UrlCreateFromPathW(*a3, pszUrl, (DWORD *)pAptQualifier, 0) >= 0 )
      {
        CoTaskMemFree(*a3);
        DisplayNameOf = SHStrDupW(pszUrl, a3);
      }
      else if ( !(unsigned int)IsAppCompatModeEnabled(23) )
      {
        CoTaskMemFree(*a3);
        *a3 = 0;
        DisplayNameOf = -2147467263;
        goto LABEL_69;
      }
    }
    if ( DisplayNameOf >= 0 )
    {
LABEL_25:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
      if ( DisplayNameOf >= 0 && a2 == SIGDN_FILESYSPATH && *a3 )
      {
        CoTaskMemFree(*((LPVOID *)this + 24));
        SHStrDupW(*a3, (LPWSTR *)this + 24);
      }
      goto LABEL_32;
    }
LABEL_69:
    CoTaskMemFree(*a3);
    *a3 = 0;
    goto LABEL_25;
  }
  v15 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)this + 16);
  *v11 = 0;
  DisplayNameOf = -2147024809;
  if ( v15 )
  {
    pv = ILCloneParent(v15);
    if ( !pv )
    {
      DisplayNameOf = -2147024882;
      goto LABEL_32;
    }
    *v11 = 0;
    *(_QWORD *)pAptQualifier = 0;
    DisplayNameOf = CDesktopFolder_CreateInstanceWithBindContext(
                      0,
                      0,
                      &GUID_000214e6_0000_0000_c000_000000000046,
                      pAptQualifier);
    if ( DisplayNameOf >= 0 )
    {
      v17 = **(_QWORD **)pAptQualifier;
      if ( *(_WORD *)pv )
        v18 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_RELATIVE *, _QWORD, GUID *, char *))(v17 + 40))(
                *(_QWORD *)pAptQualifier,
                pv,
                0,
                &GUID_000214e6_0000_0000_c000_000000000046,
                (char *)this + 168);
      else
        v18 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))v17)(
                *(_QWORD *)pAptQualifier,
                &GUID_000214e6_0000_0000_c000_000000000046,
                (char *)this + 168);
      DisplayNameOf = v18;
      if ( v18 >= 0 && !*v11 )
        DisplayNameOf = -2147467259;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
    CoTaskMemFree(pv);
  }
  if ( DisplayNameOf >= 0 )
  {
    if ( *((_DWORD *)this + 50) )
      IUnknown_PrepareForCaching(*v11);
    goto LABEL_21;
  }
LABEL_32:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return (unsigned int)DisplayNameOf;
}

```

## disassembly

```asm
0x1800cf710  mov     [rsp-8+arg_18], rbx
0x1800cf715  push    rbp
0x1800cf716  push    rsi
0x1800cf717  push    rdi
0x1800cf718  push    r12
0x1800cf71a  push    r13
0x1800cf71c  push    r14
0x1800cf71e  push    r15
0x1800cf720  lea     rbp, [rsp-11D0h]
0x1800cf728  mov     eax, 12D0h
0x1800cf72d  call    _alloca_probe
0x1800cf732  sub     rsp, rax
0x1800cf735  mov     rax, cs:__security_cookie
0x1800cf73c  xor     rax, rsp
0x1800cf73f  mov     [rbp+1200h+var_40], rax
0x1800cf746  mov     r13, r8
0x1800cf749  mov     r15d, edx
0x1800cf74c  mov     rdi, rcx
0x1800cf74f  xor     r12d, r12d
0x1800cf752  mov     [r8], r12
0x1800cf755  lea     rsi, [rcx+48h]
0x1800cf759  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800cf75d  cmovz   rsi, r12
0x1800cf761  mov     [rsp+1300h+var_12C8], rsi
0x1800cf766  mov     ebx, [rsi+2Ch]
0x1800cf769  cmp     ebx, 2
0x1800cf76c  jz      short loc_1800CF781
0x1800cf76e  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf774  test    eax, eax
0x1800cf776  jz      loc_1800CF9AF
0x1800cf77c  cmp     eax, 1
0x1800cf77f  jnz     short loc_1800CF7ED
0x1800cf781  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x1800cf785  jz      short loc_1800CF7ED
0x1800cf787  mov     r14d, r12d
0x1800cf78a  mov     [rsp+1300h+pAptType], r12d
0x1800cf78f  mov     [rsp+1300h+pAptQualifier], r12d
0x1800cf794  lea     rdx, [rsp+1300h+pAptQualifier]; pAptQualifier
0x1800cf799  lea     rcx, [rsp+1300h+pAptType]; pAptType
0x1800cf79e  call    cs:__imp_CoGetApartmentType
0x1800cf7a4  mov     ebx, eax
0x1800cf7a6  test    eax, eax
0x1800cf7a8  js      short loc_1800CF7DE
0x1800cf7aa  mov     ecx, [rsp+1300h+pAptType]
0x1800cf7ae  cmp     ecx, 3
0x1800cf7b1  jnz     short loc_1800CF7BE
0x1800cf7b3  call    cs:__imp_GetCurrentThreadId
0x1800cf7b9  mov     r14d, eax
0x1800cf7bc  jmp     short loc_1800CF7D4
0x1800cf7be  test    ecx, ecx
0x1800cf7c0  jz      short loc_1800CF7B3
0x1800cf7c2  sub     ecx, 1
0x1800cf7c5  jz      short loc_1800CF7D4
0x1800cf7c7  cmp     ecx, 1
0x1800cf7ca  jz      loc_1800CFB1B
0x1800cf7d0  test    eax, eax
0x1800cf7d2  js      short loc_1800CF7DE
0x1800cf7d4  cmp     r14d, [rsi+28h]
0x1800cf7d8  jnz     loc_1800CFBD6
0x1800cf7de  mov     rcx, [rbp+1208h]; this
0x1800cf7e5  test    ebx, ebx
0x1800cf7e7  js      loc_1800CFA0B
0x1800cf7ed  mov     rcx, rsi; lpCriticalSection
0x1800cf7f0  call    cs:__imp_TryEnterCriticalSection
0x1800cf7f6  mov     ebx, 8001010Eh
0x1800cf7fb  test    eax, eax
0x1800cf7fd  cmovnz  ebx, r12d
0x1800cf801  mov     [rsp+1300h+var_12C0], ebx
0x1800cf805  test    ebx, ebx
0x1800cf807  js      loc_1800CFA03
0x1800cf80d  cmp     r15d, 80058000h
0x1800cf814  jz      loc_1800CF901
0x1800cf81a  mov     qword ptr [rsp+1300h+pAptType], r12
0x1800cf81f  lea     r12, [rdi+0A8h]
0x1800cf826  cmp     qword ptr [r12], 0
0x1800cf82b  jz      loc_1800CF97A
0x1800cf831  mov     rcx, [r12]
0x1800cf835  mov     rax, [rcx]
0x1800cf838  lea     r8, [rsp+1300h+pAptType]
0x1800cf83d  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cf844  mov     rax, [rax]
0x1800cf847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf84c  mov     r14d, eax
0x1800cf84f  test    eax, eax
0x1800cf851  js      loc_1800CF940
0x1800cf857  movzx   r12d, r15w
0x1800cf85b  xor     edx, edx; Val
0x1800cf85d  mov     r8d, 110h; Size
0x1800cf863  lea     rcx, [rsp+1300h+pstr]; void *
0x1800cf868  call    memset_0
0x1800cf86d  mov     [rsp+1300h+cchValue], 0
0x1800cf875  lea     r9, [rsp+1300h+pstr]
0x1800cf87a  mov     r8d, r12d
0x1800cf87d  mov     rdx, [rdi+88h]
0x1800cf884  mov     rcx, qword ptr [rsp+1300h+pAptType]
0x1800cf889  call    cs:__imp_IShellFolder_GetDisplayNameOf
0x1800cf88f  mov     r14d, eax
0x1800cf892  test    eax, eax
0x1800cf894  js      short loc_1800CF8BB
0x1800cf896  mov     r8, r13; ppsz
0x1800cf899  mov     rdx, [rdi+88h]; pidl
0x1800cf8a0  lea     rcx, [rsp+1300h+pstr]; pstr
0x1800cf8a5  call    cs:__imp_StrRetToStrW
0x1800cf8ab  mov     r14d, eax
0x1800cf8ae  test    eax, eax
0x1800cf8b0  js      short loc_1800CF8BB
0x1800cf8b2  cmp     r12d, r15d
0x1800cf8b5  jnz     loc_1800CFAD5
0x1800cf8bb  mov     rcx, qword ptr [rsp+1300h+pAptType]
0x1800cf8c0  mov     rax, [rcx]
0x1800cf8c3  mov     rax, [rax+10h]
0x1800cf8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf8cc  test    r14d, r14d
0x1800cf8cf  js      short loc_1800CF940
0x1800cf8d1  cmp     r15d, 80058000h
0x1800cf8d8  jnz     short loc_1800CF940
0x1800cf8da  cmp     qword ptr [r13+0], 0
0x1800cf8df  jz      short loc_1800CF940
0x1800cf8e1  mov     rcx, [rdi+0C0h]; pv
0x1800cf8e8  call    cs:__imp_CoTaskMemFree
0x1800cf8ee  lea     rdx, [rdi+0C0h]; ppwsz
0x1800cf8f5  mov     rcx, [r13+0]; psz
0x1800cf8f9  call    cs:__imp_SHStrDupW
0x1800cf8ff  jmp     short loc_1800CF940
0x1800cf901  mov     rcx, [rdi+0C0h]; psz
0x1800cf908  test    rcx, rcx
0x1800cf90b  jnz     loc_1800CFAF3
0x1800cf911  mov     [rsp+1300h+pAptQualifier], 40000000h
0x1800cf919  mov     rax, [rdi]
0x1800cf91c  lea     r8, [rsp+1300h+pAptQualifier]
0x1800cf921  mov     edx, 40000000h
0x1800cf926  mov     rcx, rdi
0x1800cf929  mov     rax, [rax+30h]
0x1800cf92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf932  test    eax, eax
0x1800cf934  jz      loc_1800CF81A
0x1800cf93a  mov     r14d, 80070057h
0x1800cf940  test    ebx, ebx
0x1800cf942  js      short loc_1800CF94D
0x1800cf944  mov     rcx, rsi; lpCriticalSection
0x1800cf947  call    cs:__imp_LeaveCriticalSection
0x1800cf94d  mov     eax, r14d
0x1800cf950  mov     rcx, [rbp+1200h+var_40]
0x1800cf957  xor     rcx, rsp; StackCookie
0x1800cf95a  call    __security_check_cookie
0x1800cf95f  mov     rbx, [rsp+1300h+arg_18]
0x1800cf967  add     rsp, 12D0h
0x1800cf96e  pop     r15
0x1800cf970  pop     r14
0x1800cf972  pop     r13
0x1800cf974  pop     r12
0x1800cf976  pop     rdi
0x1800cf977  pop     rsi
0x1800cf978  pop     rbp
0x1800cf979  retn
0x1800cf97a  mov     rcx, [rdi+80h]; Src
0x1800cf981  mov     qword ptr [r12], 0
0x1800cf989  mov     r14d, 80070057h
0x1800cf98f  test    rcx, rcx
0x1800cf992  jz      loc_1800CFAB1
0x1800cf998  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x1800cf99d  mov     [rsp+1300h+pv], rax
0x1800cf9a2  test    rax, rax
0x1800cf9a5  jnz     short loc_1800CFA24
0x1800cf9a7  mov     r14d, 8007000Eh
0x1800cf9ad  jmp     short loc_1800CF940
0x1800cf9af  mov     r8d, 104h; nSize
0x1800cf9b5  lea     rdx, [rsp+1300h+pstr]; lpFilename
0x1800cf9ba  xor     ecx, ecx; hModule
0x1800cf9bc  call    cs:__imp_GetModuleFileNameW
0x1800cf9c2  test    eax, eax
0x1800cf9c4  jnz     loc_1800CFB26
0x1800cf9ca  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf9d0  cmp     ecx, 1
0x1800cf9d3  jnz     loc_1800CF7ED
0x1800cf9d9  cmp     ebx, ecx
0x1800cf9db  jnz     loc_1800CF781
0x1800cf9e1  mov     ecx, 10h
0x1800cf9e6  call    cs:__imp_IsAppCompatModeEnabled
0x1800cf9ec  test    eax, eax
0x1800cf9ee  jz      loc_1800CFC1E
0x1800cf9f4  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf9fe  jmp     loc_1800CF7ED
0x1800cfa03  mov     r14d, ebx
0x1800cfa06  jmp     loc_1800CF940
0x1800cfa0b  mov     r9d, ebx; char *
0x1800cfa0e  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800cfa15  mov     edx, 0C8h; void *
0x1800cfa1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cfa1f  jmp     loc_1800CF801
0x1800cfa24  mov     qword ptr [r12], 0
0x1800cfa2c  mov     qword ptr [rsp+1300h+pAptQualifier], 0
0x1800cfa35  lea     r9, [rsp+1300h+pAptQualifier]
0x1800cfa3a  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cfa41  xor     edx, edx
0x1800cfa43  xor     ecx, ecx
0x1800cfa45  call    CDesktopFolder_CreateInstanceWithBindContext
0x1800cfa4a  mov     r14d, eax
0x1800cfa4d  test    eax, eax
0x1800cfa4f  js      short loc_1800CFAA6
0x1800cfa51  mov     rdx, [rsp+1300h+pv]
0x1800cfa56  mov     rcx, qword ptr [rsp+1300h+pAptQualifier]
0x1800cfa5b  mov     rax, [rcx]
0x1800cfa5e  cmp     word ptr [rdx], 0
0x1800cfa62  jz      loc_1800CFB04
0x1800cfa68  mov     qword ptr [rsp+1300h+cchValue], r12
0x1800cfa6d  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cfa74  xor     r8d, r8d
0x1800cfa77  mov     rax, [rax+28h]
0x1800cfa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfa80  mov     r14d, eax
0x1800cfa83  test    eax, eax
0x1800cfa85  js      short loc_1800CFA95
0x1800cfa87  mov     eax, 80004005h
0x1800cfa8c  cmp     qword ptr [r12], 0
0x1800cfa91  cmovz   r14d, eax
0x1800cfa95  mov     rcx, qword ptr [rsp+1300h+pAptQualifier]
0x1800cfa9a  mov     rax, [rcx]
0x1800cfa9d  mov     rax, [rax+10h]
0x1800cfaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfaa6  mov     rcx, [rsp+1300h+pv]; pv
0x1800cfaab  call    cs:__imp_CoTaskMemFree
0x1800cfab1  test    r14d, r14d
0x1800cfab4  js      loc_1800CF940
0x1800cfaba  cmp     dword ptr [rdi+0C8h], 0
0x1800cfac1  jz      loc_1800CF831
0x1800cfac7  mov     rcx, [r12]; struct IUnknown *
0x1800cfacb  call    ?IUnknown_PrepareForCaching@@YAJPEAUIUnknown@@@Z; IUnknown_PrepareForCaching(IUnknown *)
0x1800cfad0  jmp     loc_1800CF831
0x1800cfad5  xor     r14d, r14d
0x1800cfad8  cmp     r15d, 80068000h
0x1800cfadf  jz      loc_1800CFB69
0x1800cfae5  test    r14d, r14d
0x1800cfae8  jns     loc_1800CF8BB
0x1800cfaee  jmp     loc_1800CFC07
0x1800cfaf3  mov     rdx, r13; ppwsz
0x1800cfaf6  call    cs:__imp_SHStrDupW
0x1800cfafc  mov     r14d, eax
0x1800cfaff  jmp     loc_1800CF940
0x1800cfb04  mov     r8, r12
0x1800cfb07  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cfb0e  mov     rax, [rax]
0x1800cfb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfb16  jmp     loc_1800CFA80
0x1800cfb1b  mov     r14d, 0FFFFFFFFh
0x1800cfb21  jmp     loc_1800CF7D4
0x1800cfb26  mov     [rsp+1300h+bIgnoreCase], 1; bIgnoreCase
0x1800cfb2e  mov     [rsp+1300h+cchValue], 0FFFFFFFFh; cchValue
0x1800cfb36  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800cfb3d  mov     r8d, 0FFFFFFFFh; cchSource
0x1800cfb43  lea     rdx, [rsp+1300h+pstr]; lpStringSource
0x1800cfb48  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800cfb4d  call    cs:__imp_FindStringOrdinal
0x1800cfb53  mov     ecx, r12d
0x1800cfb56  cmp     eax, 0FFFFFFFFh
0x1800cfb59  setnz   cl
0x1800cfb5c  inc     ecx
0x1800cfb5e  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cfb64  jmp     loc_1800CF9D0
0x1800cfb69  xor     edx, edx; UrlIs
0x1800cfb6b  mov     rcx, [r13+0]; pszUrl
0x1800cfb6f  call    cs:__imp_UrlIsW
0x1800cfb75  test    eax, eax
0x1800cfb77  jnz     loc_1800CFAE5
0x1800cfb7d  mov     [rsp+1300h+pAptQualifier], 824h
0x1800cfb85  mov     edx, 40000000h; unsigned int
0x1800cfb8a  lea     rcx, [rdi-8]; this
0x1800cfb8e  call    ?_IsAttrib@CShellItem@@IEAAHK@Z; CShellItem::_IsAttrib(ulong)
0x1800cfb93  test    eax, eax
0x1800cfb95  jz      short loc_1800CFBE0
0x1800cfb97  xor     r9d, r9d; dwFlags
0x1800cfb9a  lea     r8, [rsp+1300h+pAptQualifier]; pcchUrl
0x1800cfb9f  lea     rdx, [rbp+1200h+pszUrl]; pszUrl
0x1800cfba6  mov     rcx, [r13+0]; pszPath
0x1800cfbaa  call    cs:__imp_UrlCreateFromPathW
0x1800cfbb0  test    eax, eax
0x1800cfbb2  js      short loc_1800CFBE0
0x1800cfbb4  mov     rcx, [r13+0]; pv
0x1800cfbb8  call    cs:__imp_CoTaskMemFree
0x1800cfbbe  mov     rdx, r13; ppwsz
0x1800cfbc1  lea     rcx, [rbp+1200h+pszUrl]; psz
0x1800cfbc8  call    cs:__imp_SHStrDupW
0x1800cfbce  mov     r14d, eax
0x1800cfbd1  jmp     loc_1800CFAE5
0x1800cfbd6  mov     ebx, 8001010Eh
0x1800cfbdb  jmp     loc_1800CF7DE
0x1800cfbe0  mov     ecx, 17h
0x1800cfbe5  call    cs:__imp_IsAppCompatModeEnabled
0x1800cfbeb  test    eax, eax
0x1800cfbed  jnz     loc_1800CFAE5
0x1800cfbf3  mov     rcx, [r13+0]; pv
0x1800cfbf7  call    cs:__imp_CoTaskMemFree
0x1800cfbfd  mov     [r13+0], r14
0x1800cfc01  mov     r14d, 80004001h
0x1800cfc07  mov     rcx, [r13+0]; pv
0x1800cfc0b  call    cs:__imp_CoTaskMemFree
0x1800cfc11  mov     qword ptr [r13+0], 0
0x1800cfc19  jmp     loc_1800CF8BB
0x1800cfc1e  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cfc24  jmp     loc_1800CF77C
  ... truncated ...
```
