# CShellItem::GetDisplayName(_SIGDN,ushort * *)

- ea: `0x1800612c0`
- end: `0x180061856`
- name: `?GetDisplayName@CShellItem@@UEAAJW4_SIGDN@@PEAPEAG@Z`
- size: `1430`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, enum _SIGDN, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800612c0`
- `0x180061860`
- `0x180061960`
- `0x1800625e0`
- `0x1800899a4`
- `0x180227ec0`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x180649650`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800615a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800615a1`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18006174a`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18006174a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061521`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800613ac`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800613ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061369`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800617b3`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800617b3`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180061772`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180061772`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18006134e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18006134e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800614b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006169c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800617c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800614b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006169c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800617c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061832`
- `SHCORE!__imp_StrRetToStrW` at `0x18006146d`
- `SHCORE!__imp_StrRetToStrW` at `0x18006146d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800615d1`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180061800`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800615d1`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180061800`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800614cd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800616ed`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800617dd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800614cd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800616ed`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800617dd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_IShellFolder_GetDisplayNameOf` at `0x18006144b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_IShellFolder_GetDisplayNameOf` at `0x18006144b`

## string_xrefs

- `0x1800615ff`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

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
0x1800612c0  mov     [rsp-8+arg_18], rbx
0x1800612c5  push    rbp
0x1800612c6  push    rsi
0x1800612c7  push    rdi
0x1800612c8  push    r12
0x1800612ca  push    r13
0x1800612cc  push    r14
0x1800612ce  push    r15
0x1800612d0  lea     rbp, [rsp-11D0h]
0x1800612d8  mov     eax, 12D0h
0x1800612dd  call    _alloca_probe
0x1800612e2  sub     rsp, rax
0x1800612e5  mov     rax, cs:__security_cookie
0x1800612ec  xor     rax, rsp
0x1800612ef  mov     [rbp+1200h+var_40], rax
0x1800612f6  mov     r13, r8
0x1800612f9  mov     r15d, edx
0x1800612fc  mov     rdi, rcx
0x1800612ff  xor     r12d, r12d
0x180061302  mov     [r8], r12
0x180061305  lea     rsi, [rcx+48h]
0x180061309  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18006130d  cmovz   rsi, r12
0x180061311  mov     [rsp+1300h+var_12C8], rsi
0x180061316  mov     ebx, [rsi+2Ch]
0x180061319  cmp     ebx, 2
0x18006131c  jz      short loc_180061331
0x18006131e  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180061324  test    eax, eax
0x180061326  jz      loc_180061594
0x18006132c  cmp     eax, 1
0x18006132f  jnz     short loc_1800613A9
0x180061331  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x180061335  jz      short loc_1800613A9
0x180061337  mov     r14d, r12d
0x18006133a  mov     [rsp+1300h+pAptType], r12d
0x18006133f  mov     [rsp+1300h+pAptQualifier], r12d
0x180061344  lea     rdx, [rsp+1300h+pAptQualifier]; pAptQualifier
0x180061349  lea     rcx, [rsp+1300h+pAptType]; pAptType
0x18006134e  call    cs:__imp_CoGetApartmentType
0x180061355  nop     dword ptr [rax+rax+00h]
0x18006135a  mov     ebx, eax
0x18006135c  test    eax, eax
0x18006135e  js      short loc_18006139A
0x180061360  mov     ecx, [rsp+1300h+pAptType]
0x180061364  cmp     ecx, 3
0x180061367  jnz     short loc_18006137A
0x180061369  call    cs:__imp_GetCurrentThreadId
0x180061370  nop     dword ptr [rax+rax+00h]
0x180061375  mov     r14d, eax
0x180061378  jmp     short loc_180061390
0x18006137a  test    ecx, ecx
0x18006137c  jz      short loc_180061369
0x18006137e  sub     ecx, 1
0x180061381  jz      short loc_180061390
0x180061383  cmp     ecx, 1
0x180061386  jz      loc_180061718
0x18006138c  test    eax, eax
0x18006138e  js      short loc_18006139A
0x180061390  cmp     r14d, [rsi+28h]
0x180061394  jnz     loc_1800617F1
0x18006139a  mov     rcx, [rbp+1208h]; this
0x1800613a1  test    ebx, ebx
0x1800613a3  js      loc_1800615FC
0x1800613a9  mov     rcx, rsi; lpCriticalSection
0x1800613ac  call    cs:__imp_TryEnterCriticalSection
0x1800613b3  nop     dword ptr [rax+rax+00h]
0x1800613b8  mov     ebx, 8001010Eh
0x1800613bd  test    eax, eax
0x1800613bf  cmovnz  ebx, r12d
0x1800613c3  mov     [rsp+1300h+var_12C0], ebx
0x1800613c7  test    ebx, ebx
0x1800613c9  js      loc_1800615F4
0x1800613cf  cmp     r15d, 80058000h
0x1800613d6  jz      loc_1800614DB
0x1800613dc  mov     qword ptr [rsp+1300h+pAptType], r12
0x1800613e1  lea     r12, [rdi+0A8h]
0x1800613e8  cmp     qword ptr [r12], 0
0x1800613ed  jz      loc_18006155B
0x1800613f3  mov     rcx, [r12]
0x1800613f7  mov     rax, [rcx]
0x1800613fa  lea     r8, [rsp+1300h+pAptType]
0x1800613ff  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180061406  mov     rax, [rax]
0x180061409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006140e  mov     r14d, eax
0x180061411  test    eax, eax
0x180061413  js      loc_18006151A
0x180061419  movzx   r12d, r15w
0x18006141d  xor     edx, edx; Val
0x18006141f  mov     r8d, 110h; Size
0x180061425  lea     rcx, [rsp+1300h+pstr]; void *
0x18006142a  call    memset_0
0x18006142f  mov     [rsp+1300h+cchValue], 0
0x180061437  lea     r9, [rsp+1300h+pstr]
0x18006143c  mov     r8d, r12d
0x18006143f  mov     rdx, [rdi+88h]
0x180061446  mov     rcx, qword ptr [rsp+1300h+pAptType]
0x18006144b  call    cs:__imp_IShellFolder_GetDisplayNameOf
0x180061452  nop     dword ptr [rax+rax+00h]
0x180061457  mov     r14d, eax
0x18006145a  test    eax, eax
0x18006145c  js      short loc_180061489
0x18006145e  mov     r8, r13; ppsz
0x180061461  mov     rdx, [rdi+88h]; pidl
0x180061468  lea     rcx, [rsp+1300h+pstr]; pstr
0x18006146d  call    cs:__imp_StrRetToStrW
0x180061474  nop     dword ptr [rax+rax+00h]
0x180061479  mov     r14d, eax
0x18006147c  test    eax, eax
0x18006147e  js      short loc_180061489
0x180061480  cmp     r12d, r15d
0x180061483  jnz     loc_1800616CC
0x180061489  mov     rcx, qword ptr [rsp+1300h+pAptType]
0x18006148e  mov     rax, [rcx]
0x180061491  mov     rax, [rax+10h]
0x180061495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006149a  test    r14d, r14d
0x18006149d  js      short loc_18006151A
0x18006149f  cmp     r15d, 80058000h
0x1800614a6  jnz     short loc_18006151A
0x1800614a8  cmp     qword ptr [r13+0], 0
0x1800614ad  jz      short loc_18006151A
0x1800614af  mov     rcx, [rdi+0C0h]; pv
0x1800614b6  call    cs:__imp_CoTaskMemFree
0x1800614bd  nop     dword ptr [rax+rax+00h]
0x1800614c2  lea     rdx, [rdi+0C0h]; ppwsz
0x1800614c9  mov     rcx, [r13+0]; psz
0x1800614cd  call    cs:__imp_SHStrDupW
0x1800614d4  nop     dword ptr [rax+rax+00h]
0x1800614d9  jmp     short loc_18006151A
0x1800614db  mov     rcx, [rdi+0C0h]; psz
0x1800614e2  test    rcx, rcx
0x1800614e5  jnz     loc_1800616EA
0x1800614eb  mov     [rsp+1300h+pAptQualifier], 40000000h
0x1800614f3  mov     rax, [rdi]
0x1800614f6  lea     r8, [rsp+1300h+pAptQualifier]
0x1800614fb  mov     edx, 40000000h
0x180061500  mov     rcx, rdi
0x180061503  mov     rax, [rax+30h]
0x180061507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006150c  test    eax, eax
0x18006150e  jz      loc_1800613DC
0x180061514  mov     r14d, 80070057h
0x18006151a  test    ebx, ebx
0x18006151c  js      short loc_18006152D
0x18006151e  mov     rcx, rsi; lpCriticalSection
0x180061521  call    cs:__imp_LeaveCriticalSection
0x180061528  nop     dword ptr [rax+rax+00h]
0x18006152d  mov     eax, r14d
0x180061530  mov     rcx, [rbp+1200h+var_40]
0x180061537  xor     rcx, rsp; StackCookie
0x18006153a  call    __security_check_cookie
0x18006153f  mov     rbx, [rsp+1300h+arg_18]
0x180061547  add     rsp, 12D0h
0x18006154e  pop     r15
0x180061550  pop     r14
0x180061552  pop     r13
0x180061554  pop     r12
0x180061556  pop     rdi
0x180061557  pop     rsi
0x180061558  pop     rbp
0x180061559  retn
0x18006155b  mov     rcx, [rdi+80h]; Src
0x180061562  mov     qword ptr [r12], 0
0x18006156a  mov     r14d, 80070057h
0x180061570  test    rcx, rcx
0x180061573  jz      loc_1800616A8
0x180061579  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x18006157e  mov     [rsp+1300h+pv], rax
0x180061583  test    rax, rax
0x180061586  jnz     loc_180061615
0x18006158c  mov     r14d, 8007000Eh
0x180061592  jmp     short loc_18006151A
0x180061594  mov     r8d, 104h; nSize
0x18006159a  lea     rdx, [rsp+1300h+pstr]; lpFilename
0x18006159f  xor     ecx, ecx; hModule
0x1800615a1  call    cs:__imp_GetModuleFileNameW
0x1800615a8  nop     dword ptr [rax+rax+00h]
0x1800615ad  test    eax, eax
0x1800615af  jnz     loc_180061723
0x1800615b5  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800615bb  cmp     ecx, 1
0x1800615be  jnz     loc_1800613A9
0x1800615c4  cmp     ebx, ecx
0x1800615c6  jnz     loc_180061331
0x1800615cc  mov     ecx, 10h
0x1800615d1  call    cs:__imp_IsAppCompatModeEnabled
0x1800615d8  nop     dword ptr [rax+rax+00h]
0x1800615dd  test    eax, eax
0x1800615df  jz      loc_18006184B
0x1800615e5  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800615ef  jmp     loc_1800613A9
0x1800615f4  mov     r14d, ebx
0x1800615f7  jmp     loc_18006151A
0x1800615fc  mov     r9d, ebx; char *
0x1800615ff  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180061606  mov     edx, 0C8h; void *
0x18006160b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061610  jmp     loc_1800613C3
0x180061615  mov     qword ptr [r12], 0
0x18006161d  mov     qword ptr [rsp+1300h+pAptQualifier], 0
0x180061626  lea     r9, [rsp+1300h+pAptQualifier]
0x18006162b  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x180061632  xor     edx, edx
0x180061634  xor     ecx, ecx
0x180061636  call    CDesktopFolder_CreateInstanceWithBindContext
0x18006163b  mov     r14d, eax
0x18006163e  test    eax, eax
0x180061640  js      short loc_180061697
0x180061642  mov     rdx, [rsp+1300h+pv]
0x180061647  mov     rcx, qword ptr [rsp+1300h+pAptQualifier]
0x18006164c  mov     rax, [rcx]
0x18006164f  cmp     word ptr [rdx], 0
0x180061653  jz      loc_180061701
0x180061659  mov     qword ptr [rsp+1300h+cchValue], r12
0x18006165e  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180061665  xor     r8d, r8d
0x180061668  mov     rax, [rax+28h]
0x18006166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061671  mov     r14d, eax
0x180061674  test    eax, eax
0x180061676  js      short loc_180061686
0x180061678  mov     eax, 80004005h
0x18006167d  cmp     qword ptr [r12], 0
0x180061682  cmovz   r14d, eax
0x180061686  mov     rcx, qword ptr [rsp+1300h+pAptQualifier]
0x18006168b  mov     rax, [rcx]
0x18006168e  mov     rax, [rax+10h]
0x180061692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061697  mov     rcx, [rsp+1300h+pv]; pv
0x18006169c  call    cs:__imp_CoTaskMemFree
0x1800616a3  nop     dword ptr [rax+rax+00h]
0x1800616a8  test    r14d, r14d
0x1800616ab  js      loc_18006151A
0x1800616b1  cmp     dword ptr [rdi+0C8h], 0
0x1800616b8  jz      loc_1800613F3
0x1800616be  mov     rcx, [r12]; struct IUnknown *
0x1800616c2  call    ?IUnknown_PrepareForCaching@@YAJPEAUIUnknown@@@Z; IUnknown_PrepareForCaching(IUnknown *)
0x1800616c7  jmp     loc_1800613F3
0x1800616cc  xor     r14d, r14d
0x1800616cf  cmp     r15d, 80068000h
0x1800616d6  jz      loc_18006176C
0x1800616dc  test    r14d, r14d
0x1800616df  jns     loc_180061489
0x1800616e5  jmp     loc_18006182E
0x1800616ea  mov     rdx, r13; ppwsz
0x1800616ed  call    cs:__imp_SHStrDupW
0x1800616f4  nop     dword ptr [rax+rax+00h]
0x1800616f9  mov     r14d, eax
0x1800616fc  jmp     loc_18006151A
0x180061701  mov     r8, r12
0x180061704  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18006170b  mov     rax, [rax]
0x18006170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061713  jmp     loc_180061671
0x180061718  mov     r14d, 0FFFFFFFFh
0x18006171e  jmp     loc_180061390
0x180061723  mov     [rsp+1300h+bIgnoreCase], 1; bIgnoreCase
0x18006172b  mov     [rsp+1300h+cchValue], 0FFFFFFFFh; cchValue
0x180061733  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18006173a  mov     r8d, 0FFFFFFFFh; cchSource
0x180061740  lea     rdx, [rsp+1300h+pstr]; lpStringSource
0x180061745  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18006174a  call    cs:__imp_FindStringOrdinal
0x180061751  nop     dword ptr [rax+rax+00h]
0x180061756  mov     ecx, r12d
0x180061759  cmp     eax, 0FFFFFFFFh
0x18006175c  setnz   cl
0x18006175f  inc     ecx
0x180061761  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180061767  jmp     loc_1800615BB
0x18006176c  xor     edx, edx; UrlIs
0x18006176e  mov     rcx, [r13+0]; pszUrl
0x180061772  call    cs:__imp_UrlIsW
0x180061779  nop     dword ptr [rax+rax+00h]
0x18006177e  test    eax, eax
0x180061780  jnz     loc_1800616DC
0x180061786  mov     [rsp+1300h+pAptQualifier], 824h
0x18006178e  mov     edx, 40000000h; unsigned int
0x180061793  lea     rcx, [rdi-8]; this
0x180061797  call    ?_IsAttrib@CShellItem@@IEAAHK@Z; CShellItem::_IsAttrib(ulong)
0x18006179c  test    eax, eax
0x18006179e  jz      short loc_1800617FB
0x1800617a0  xor     r9d, r9d; dwFlags
0x1800617a3  lea     r8, [rsp+1300h+pAptQualifier]; pcchUrl
0x1800617a8  lea     rdx, [rbp+1200h+pszUrl]; pszUrl
0x1800617af  mov     rcx, [r13+0]; pszPath
0x1800617b3  call    cs:__imp_UrlCreateFromPathW
0x1800617ba  nop     dword ptr [rax+rax+00h]
0x1800617bf  test    eax, eax
0x1800617c1  js      short loc_1800617FB
0x1800617c3  mov     rcx, [r13+0]; pv
0x1800617c7  call    cs:__imp_CoTaskMemFree
0x1800617ce  nop     dword ptr [rax+rax+00h]
0x1800617d3  mov     rdx, r13; ppwsz
0x1800617d6  lea     rcx, [rbp+1200h+pszUrl]; psz
0x1800617dd  call    cs:__imp_SHStrDupW
0x1800617e4  nop     dword ptr [rax+rax+00h]
0x1800617e9  mov     r14d, eax
  ... truncated ...
```
