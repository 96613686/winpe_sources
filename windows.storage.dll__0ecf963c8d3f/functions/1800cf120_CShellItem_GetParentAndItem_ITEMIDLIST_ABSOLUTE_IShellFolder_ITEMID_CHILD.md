# CShellItem::GetParentAndItem(_ITEMIDLIST_ABSOLUTE * *,IShellFolder * *,_ITEMID_CHILD * *)

- ea: `0x1800cf120`
- end: `0x1800cf709`
- name: `?GetParentAndItem@CShellItem@@UEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIShellFolder@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct _ITEMIDLIST_ABSOLUTE **, struct IShellFolder **, struct _ITEMID_CHILD **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180054c30`
- `0x1800551a0`
- `0x1800cf120`
- `0x1800cfc30`
- `0x1800cfd30`
- `0x1800d0990`
- `0x1800dd190`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cf4b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cf4b9`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cf69e`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cf69e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cf3a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cf3a6`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800cf20e`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800cf20e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf1ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf2d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf2d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf422`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800cf2f9`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800cf446`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800cf2f9`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800cf446`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf1b9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf6eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf6eb`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cf4e3`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cf4e3`

## string_xrefs

- `0x1800cf605`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellItem::GetParentAndItem(CShellItem *this, LPVOID *a2, struct IShellFolder **a3, LPVOID *a4)
{
  char *v8; // rdi
  char *v9; // rsi
  int v10; // ebx
  int v11; // eax
  DWORD CurrentThreadId; // ebp
  HRESULT ApartmentType; // ebx
  HRESULT v14; // ebp
  _QWORD *v15; // rax
  struct _ITEMID_CHILD *v16; // rax
  void *v17; // rdi
  __int64 v18; // rdi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  void *v24; // rdi
  int v25; // ecx
  const struct _ITEMIDLIST_RELATIVE *v26; // rcx
  __int64 v27; // rax
  APTTYPE v28; // eax
  int cchValue; // [rsp+20h] [rbp-2B8h]
  __int64 Size; // [rsp+30h] [rbp-2A8h]
  size_t Sizea; // [rsp+30h] [rbp-2A8h]
  struct _ITEMID_CHILD *Src; // [rsp+38h] [rbp-2A0h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-288h] BYREF
  LPMALLOC ppMalloc; // [rsp+58h] [rbp-280h] BYREF
  APTTYPE pAptType[2]; // [rsp+60h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = (char *)this - 32;
  if ( this == (CShellItem *)32 )
    v9 = 0;
  else
    v9 = (char *)this + 48;
  v10 = *((_DWORD *)v9 + 11);
  if ( v10 != 2 )
  {
    v11 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    {
LABEL_11:
      if ( v11 != 1 )
        goto LABEL_23;
      goto LABEL_12;
    }
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v25 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v25;
    }
    else
    {
      v25 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    }
    if ( v25 != 1 )
      goto LABEL_23;
    if ( v10 == 1 )
    {
      if ( (unsigned int)IsAppCompatModeEnabled(16) )
      {
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
        goto LABEL_23;
      }
      v11 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( *((_DWORD *)v9 + 10) != -3 )
  {
    CurrentThreadId = 0;
    pAptType[0] = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      switch ( pAptType[0] )
      {
        case APTTYPE_MAINSTA:
        case APTTYPE_STA:
          CurrentThreadId = GetCurrentThreadId();
          break;
        case APTTYPE_MTA:
          CurrentThreadId = 0;
          break;
        case APTTYPE_NA:
          CurrentThreadId = -1;
          break;
      }
      if ( CurrentThreadId != *((_DWORD *)v9 + 10) )
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
      goto LABEL_25;
    }
  }
LABEL_23:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v9) )
    ApartmentType = 0;
LABEL_25:
  v14 = ApartmentType;
  if ( ApartmentType < 0 )
    goto LABEL_26;
  if ( a3 )
  {
    *a3 = 0;
    v15 = (_QWORD *)((char *)this + 144);
    if ( *((_QWORD *)this + 18) )
    {
LABEL_33:
      (**(void (__fastcall ***)(_QWORD, GUID *, struct IShellFolder **))*v15)(
        *v15,
        &GUID_000214e6_0000_0000_c000_000000000046,
        a3);
      goto LABEL_34;
    }
    v26 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)this + 13);
    *v15 = 0;
    if ( v26 )
    {
      ppMalloc = (LPMALLOC)ILCloneParent(v26);
      if ( ppMalloc )
      {
        *((_QWORD *)this + 18) = 0;
        *(_QWORD *)pAptQualifier = 0;
        pAptType[0] = CDesktopFolder_CreateInstanceWithBindContext(
                        0,
                        0,
                        &GUID_000214e6_0000_0000_c000_000000000046,
                        pAptQualifier);
        if ( pAptType[0] >= APTTYPE_STA )
        {
          v27 = **(_QWORD **)pAptQualifier;
          if ( LOWORD(ppMalloc->lpVtbl) )
            v28 = (*(unsigned int (__fastcall **)(_QWORD, LPMALLOC, _QWORD, GUID *, char *))(v27 + 40))(
                    *(_QWORD *)pAptQualifier,
                    ppMalloc,
                    0,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    (char *)this + 144);
          else
            v28 = (*(unsigned int (__fastcall **)(_QWORD, GUID *, char *))v27)(
                    *(_QWORD *)pAptQualifier,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    (char *)this + 144);
          pAptType[0] = v28;
          if ( v28 >= APTTYPE_STA )
          {
            if ( !*((_QWORD *)this + 18) )
              v28 = -2147467259;
            pAptType[0] = v28;
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
        }
        CoTaskMemFree(ppMalloc);
        if ( pAptType[0] >= APTTYPE_STA )
        {
          if ( *((_DWORD *)this + 44) )
            IUnknown_PrepareForCaching(*((struct IUnknown **)this + 18));
          v15 = (_QWORD *)((char *)this + 144);
          goto LABEL_33;
        }
      }
    }
  }
LABEL_34:
  if ( a2 )
  {
    v14 = 0;
    if ( !*((_QWORD *)v8 + 20) && !(unsigned int)CShellItem::_IsDesktop((CShellItem *)v8) )
      v14 = SHGetIDListFromObject(*((IUnknown **)v8 + 22), (LPITEMIDLIST *)v8 + 20);
    if ( v14 >= 0 )
    {
      v20 = (unsigned __int16 *)*((_QWORD *)this + 16);
      *(_QWORD *)pAptType = v20;
      if ( v20 )
      {
        v21 = v20;
        v22 = 2;
        do
        {
          v23 = *v21;
          if ( !(_WORD)v23 )
            break;
          v22 += v23;
          v21 = (unsigned __int16 *)((char *)v21 + v23);
        }
        while ( v21 );
        Sizea = v22;
        v24 = CoTaskMemAlloc(v22);
        if ( v24 )
        {
          ppMalloc = 0;
          *(_QWORD *)pAptQualifier = 0;
          if ( CoGetMalloc(1u, (LPMALLOC *)pAptQualifier) >= 0 )
          {
            ppMalloc = (LPMALLOC)(*(__int64 (__fastcall **)(_QWORD, void *))(**(_QWORD **)pAptQualifier + 48LL))(
                                   *(_QWORD *)pAptQualifier,
                                   v24);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          memset_0(v24, 0, (size_t)ppMalloc);
          memcpy_0(v24, *(const void **)pAptType, Sizea);
        }
        *a2 = v24;
      }
      else
      {
        *a2 = 0;
      }
    }
  }
  if ( a4 )
  {
    v16 = (struct _ITEMID_CHILD *)*((_QWORD *)this + 14);
    Src = v16;
    if ( v16 )
    {
      pAptQualifier[0] = *(unsigned __int16 *)v16;
      *(_QWORD *)pAptType = 0;
      if ( (unsigned int)(pAptQualifier[0] + 2) >= pAptQualifier[0] )
      {
        v17 = CoTaskMemAlloc((unsigned int)(pAptQualifier[0] + 2));
        *(_QWORD *)pAptType = v17;
        if ( v17 )
        {
          Size = 0;
          ppMalloc = 0;
          if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
          {
            Size = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v17);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
          memset_0(v17, 0, Size);
          v18 = LOWORD(pAptQualifier[0]);
          memcpy_0(*(void **)pAptType, Src, LOWORD(pAptQualifier[0]));
          *(_WORD *)(v18 + *(_QWORD *)pAptType) = 0;
        }
      }
      v16 = *(struct _ITEMID_CHILD **)pAptType;
    }
    *a4 = v16;
  }
  if ( *((_QWORD *)this + 16) && a2 && !*a2 || a3 && !*a3 || a4 && !*a4 )
  {
    v14 = -2147024882;
  }
  else if ( v14 >= 0 )
  {
    goto LABEL_51;
  }
LABEL_26:
  if ( a3 && *a3 )
  {
    ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
    *a3 = 0;
  }
  if ( a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  if ( a4 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
LABEL_51:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800cf120  push    rbx
0x1800cf122  push    rbp
0x1800cf123  push    rsi
0x1800cf124  push    rdi
0x1800cf125  push    r12
0x1800cf127  push    r13
0x1800cf129  push    r14
0x1800cf12b  push    r15
0x1800cf12d  sub     rsp, 298h
0x1800cf134  mov     rax, cs:__security_cookie
0x1800cf13b  xor     rax, rsp
0x1800cf13e  mov     [rsp+2D8h+var_58], rax
0x1800cf146  mov     r15, r9
0x1800cf149  mov     r14, r8
0x1800cf14c  mov     r12, rdx
0x1800cf14f  mov     r13, rcx
0x1800cf152  xor     eax, eax
0x1800cf154  test    rdx, rdx
0x1800cf157  jz      short loc_1800CF15C
0x1800cf159  mov     [rdx], rax
0x1800cf15c  test    r14, r14
0x1800cf15f  jz      short loc_1800CF164
0x1800cf161  mov     [r8], rax
0x1800cf164  test    r15, r15
0x1800cf167  jz      short loc_1800CF16C
0x1800cf169  mov     [r9], rax
0x1800cf16c  lea     rdi, [rcx-20h]
0x1800cf170  test    rdi, rdi
0x1800cf173  jz      loc_1800CF4A4
0x1800cf179  lea     rsi, [rcx+30h]
0x1800cf17d  mov     [rsp+2D8h+var_298], rsi
0x1800cf182  mov     ebx, [rsi+2Ch]
0x1800cf185  cmp     ebx, 2
0x1800cf188  jz      short loc_1800CF19F
0x1800cf18a  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf190  test    eax, eax
0x1800cf192  jz      loc_1800CF4AC
0x1800cf198  cmp     eax, 1
0x1800cf19b  jnz     short loc_1800CF20B
0x1800cf19d  xor     eax, eax
0x1800cf19f  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x1800cf1a3  jz      short loc_1800CF20B
0x1800cf1a5  mov     ebp, eax
0x1800cf1a7  mov     [rsp+2D8h+pAptType], eax
0x1800cf1ab  mov     [rsp+2D8h+pAptQualifier], eax
0x1800cf1af  lea     rdx, [rsp+2D8h+pAptQualifier]; pAptQualifier
0x1800cf1b4  lea     rcx, [rsp+2D8h+pAptType]; pAptType
0x1800cf1b9  call    cs:__imp_CoGetApartmentType
0x1800cf1bf  mov     ebx, eax
0x1800cf1c1  test    eax, eax
0x1800cf1c3  js      short loc_1800CF1FB
0x1800cf1c5  mov     ecx, [rsp+2D8h+pAptType]
0x1800cf1c9  cmp     ecx, 3
0x1800cf1cc  jnz     short loc_1800CF1D8
0x1800cf1ce  call    cs:__imp_GetCurrentThreadId
0x1800cf1d4  mov     ebp, eax
0x1800cf1d6  jmp     short loc_1800CF1F2
0x1800cf1d8  test    ecx, ecx
0x1800cf1da  jz      short loc_1800CF1CE
0x1800cf1dc  sub     ecx, 1
0x1800cf1df  jz      loc_1800CF61B
0x1800cf1e5  cmp     ecx, 1
0x1800cf1e8  jz      loc_1800CF660
0x1800cf1ee  test    eax, eax
0x1800cf1f0  js      short loc_1800CF1FB
0x1800cf1f2  cmp     ebp, [rsi+28h]
0x1800cf1f5  jnz     loc_1800CF6B9
0x1800cf1fb  mov     rcx, [rsp+2D8h]; this
0x1800cf203  test    ebx, ebx
0x1800cf205  js      loc_1800CF602
0x1800cf20b  mov     rcx, rsi; lpCriticalSection
0x1800cf20e  call    cs:__imp_TryEnterCriticalSection
0x1800cf214  mov     ebx, 8001010Eh
0x1800cf219  xor     ecx, ecx
0x1800cf21b  test    eax, eax
0x1800cf21d  cmovnz  ebx, ecx
0x1800cf220  mov     [rsp+2D8h+var_290], ebx
0x1800cf224  mov     ebp, ebx
0x1800cf226  test    ebx, ebx
0x1800cf228  jns     short loc_1800CF25A
0x1800cf22a  test    r14, r14
0x1800cf22d  jnz     loc_1800CF6C3
0x1800cf233  test    r12, r12
0x1800cf236  jnz     loc_1800CF6E7
0x1800cf23c  test    r15, r15
0x1800cf23f  jz      loc_1800CF39F
0x1800cf245  mov     rcx, [r15]; pv
0x1800cf248  call    cs:__imp_CoTaskMemFree
0x1800cf24e  mov     qword ptr [r15], 0
0x1800cf255  jmp     loc_1800CF39F
0x1800cf25a  test    r14, r14
0x1800cf25d  jz      short loc_1800CF28F
0x1800cf25f  mov     qword ptr [r14], 0
0x1800cf266  lea     rax, [r13+90h]
0x1800cf26d  cmp     qword ptr [rax], 0
0x1800cf271  jz      loc_1800CF500
0x1800cf277  mov     rcx, [rax]
0x1800cf27a  mov     rax, [rcx]
0x1800cf27d  mov     r8, r14
0x1800cf280  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cf287  mov     rax, [rax]
0x1800cf28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf28f  test    r12, r12
0x1800cf292  jnz     loc_1800CF3D2
0x1800cf298  test    r15, r15
0x1800cf29b  jz      loc_1800CF366
0x1800cf2a1  mov     rax, [r13+70h]
0x1800cf2a5  mov     [rsp+2D8h+Src], rax
0x1800cf2aa  test    rax, rax
0x1800cf2ad  jz      loc_1800CF363
0x1800cf2b3  movzx   eax, word ptr [rax]
0x1800cf2b6  mov     [rsp+2D8h+pAptQualifier], eax
0x1800cf2ba  mov     qword ptr [rsp+2D8h+pAptType], 0
0x1800cf2c3  lea     edx, [rax+2]
0x1800cf2c6  cmp     edx, eax
0x1800cf2c8  jb      loc_1800CF35E
0x1800cf2ce  mov     ecx, edx; cb
0x1800cf2d0  call    cs:__imp_CoTaskMemAlloc
0x1800cf2d6  mov     rdi, rax
0x1800cf2d9  mov     qword ptr [rsp+2D8h+pAptType], rax
0x1800cf2de  test    rax, rax
0x1800cf2e1  jz      short loc_1800CF35E
0x1800cf2e3  xor     eax, eax
0x1800cf2e5  mov     [rsp+2D8h+Size], rax
0x1800cf2ea  mov     [rsp+2D8h+ppMalloc], rax
0x1800cf2ef  lea     rdx, [rsp+2D8h+ppMalloc]; ppMalloc
0x1800cf2f4  mov     ecx, 1; dwMemContext
0x1800cf2f9  call    cs:__imp_CoGetMalloc
0x1800cf2ff  test    eax, eax
0x1800cf301  js      short loc_1800CF32D
0x1800cf303  mov     rcx, [rsp+2D8h+ppMalloc]
0x1800cf308  mov     rdx, [rcx]
0x1800cf30b  mov     rax, [rdx+30h]
0x1800cf30f  mov     rdx, rdi
0x1800cf312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf317  mov     [rsp+2D8h+Size], rax
0x1800cf31c  mov     rcx, [rsp+2D8h+ppMalloc]
0x1800cf321  mov     r8, [rcx]
0x1800cf324  mov     rax, [r8+10h]
0x1800cf328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf32d  mov     r8, [rsp+2D8h+Size]; Size
0x1800cf332  xor     edx, edx; Val
0x1800cf334  mov     rcx, rdi; void *
0x1800cf337  call    memset_0
0x1800cf33c  movzx   edi, word ptr [rsp+2D8h+pAptQualifier]
0x1800cf341  mov     r8d, edi; Size
0x1800cf344  mov     rdx, [rsp+2D8h+Src]; Src
0x1800cf349  mov     rcx, qword ptr [rsp+2D8h+pAptType]; void *
0x1800cf34e  call    memcpy_0
0x1800cf353  xor     eax, eax
0x1800cf355  mov     rcx, qword ptr [rsp+2D8h+pAptType]
0x1800cf35a  mov     [rdi+rcx], ax
0x1800cf35e  mov     rax, qword ptr [rsp+2D8h+pAptType]
0x1800cf363  mov     [r15], rax
0x1800cf366  cmp     qword ptr [r13+80h], 0
0x1800cf36e  jz      short loc_1800CF379
0x1800cf370  test    r12, r12
0x1800cf373  jnz     loc_1800CF5ED
0x1800cf379  test    r14, r14
0x1800cf37c  jz      short loc_1800CF388
0x1800cf37e  cmp     qword ptr [r14], 0
0x1800cf382  jz      loc_1800CF5F8
0x1800cf388  test    r15, r15
0x1800cf38b  jz      short loc_1800CF397
0x1800cf38d  cmp     qword ptr [r15], 0
0x1800cf391  jz      loc_1800CF5F8
0x1800cf397  test    ebp, ebp
0x1800cf399  js      loc_1800CF22A
0x1800cf39f  test    ebx, ebx
0x1800cf3a1  js      short loc_1800CF3AC
0x1800cf3a3  mov     rcx, rsi; lpCriticalSection
0x1800cf3a6  call    cs:__imp_LeaveCriticalSection
0x1800cf3ac  mov     eax, ebp
0x1800cf3ae  mov     rcx, [rsp+2D8h+var_58]
0x1800cf3b6  xor     rcx, rsp; StackCookie
0x1800cf3b9  call    __security_check_cookie
0x1800cf3be  add     rsp, 298h
0x1800cf3c5  pop     r15
0x1800cf3c7  pop     r14
0x1800cf3c9  pop     r13
0x1800cf3cb  pop     r12
0x1800cf3cd  pop     rdi
0x1800cf3ce  pop     rsi
0x1800cf3cf  pop     rbp
0x1800cf3d0  pop     rbx
0x1800cf3d1  retn
0x1800cf3d2  xor     ebp, ebp
0x1800cf3d4  cmp     [rdi+0A0h], rbp
0x1800cf3db  jz      loc_1800CF636
0x1800cf3e1  test    ebp, ebp
0x1800cf3e3  js      loc_1800CF298
0x1800cf3e9  mov     rax, [r13+80h]
0x1800cf3f0  mov     qword ptr [rsp+2D8h+pAptType], rax
0x1800cf3f5  test    rax, rax
0x1800cf3f8  jz      loc_1800CF66A
0x1800cf3fe  mov     rdx, rax
0x1800cf401  mov     r8d, 2
0x1800cf407  movzx   ecx, word ptr [rdx]
0x1800cf40a  test    cx, cx
0x1800cf40d  jz      short loc_1800CF417
0x1800cf40f  add     r8d, ecx
0x1800cf412  add     rdx, rcx
0x1800cf415  jnz     short loc_1800CF407
0x1800cf417  mov     eax, r8d
0x1800cf41a  mov     [rsp+2D8h+Size], rax
0x1800cf41f  mov     ecx, r8d; cb
0x1800cf422  call    cs:__imp_CoTaskMemAlloc
0x1800cf428  mov     rdi, rax
0x1800cf42b  test    rax, rax
0x1800cf42e  jz      short loc_1800CF49B
0x1800cf430  xor     eax, eax
0x1800cf432  mov     [rsp+2D8h+ppMalloc], rax
0x1800cf437  mov     qword ptr [rsp+2D8h+pAptQualifier], rax
0x1800cf43c  lea     rdx, [rsp+2D8h+pAptQualifier]; ppMalloc
0x1800cf441  mov     ecx, 1; dwMemContext
0x1800cf446  call    cs:__imp_CoGetMalloc
0x1800cf44c  test    eax, eax
0x1800cf44e  js      short loc_1800CF47A
0x1800cf450  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800cf455  mov     rax, [rcx]
0x1800cf458  mov     rdx, rdi
0x1800cf45b  mov     rax, [rax+30h]
0x1800cf45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf464  mov     [rsp+2D8h+ppMalloc], rax
0x1800cf469  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800cf46e  mov     r9, [rcx]
0x1800cf471  mov     rax, [r9+10h]
0x1800cf475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf47a  mov     r8, [rsp+2D8h+ppMalloc]; Size
0x1800cf47f  xor     edx, edx; Val
0x1800cf481  mov     rcx, rdi; void *
0x1800cf484  call    memset_0
0x1800cf489  mov     r8, [rsp+2D8h+Size]; Size
0x1800cf48e  mov     rdx, qword ptr [rsp+2D8h+pAptType]; Src
0x1800cf493  mov     rcx, rdi; void *
0x1800cf496  call    memcpy_0
0x1800cf49b  mov     [r12], rdi
0x1800cf49f  jmp     loc_1800CF298
0x1800cf4a4  mov     rsi, rax
0x1800cf4a7  jmp     loc_1800CF17D
0x1800cf4ac  mov     r8d, 104h; nSize
0x1800cf4b2  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x1800cf4b7  xor     ecx, ecx; hModule
0x1800cf4b9  call    cs:__imp_GetModuleFileNameW
0x1800cf4bf  test    eax, eax
0x1800cf4c1  jnz     loc_1800CF677
0x1800cf4c7  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf4cd  cmp     ecx, 1
0x1800cf4d0  jnz     loc_1800CF20B
0x1800cf4d6  cmp     ebx, ecx
0x1800cf4d8  jnz     loc_1800CF19D
0x1800cf4de  mov     ecx, 10h
0x1800cf4e3  call    cs:__imp_IsAppCompatModeEnabled
0x1800cf4e9  test    eax, eax
0x1800cf4eb  jz      loc_1800CF6FE
0x1800cf4f1  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800cf4fb  jmp     loc_1800CF20B
0x1800cf500  mov     rcx, [r13+68h]; Src
0x1800cf504  mov     qword ptr [rax], 0
0x1800cf50b  test    rcx, rcx
0x1800cf50e  jz      loc_1800CF28F
0x1800cf514  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x1800cf519  mov     [rsp+2D8h+ppMalloc], rax
0x1800cf51e  test    rax, rax
0x1800cf521  jz      loc_1800CF28F
0x1800cf527  xor     eax, eax
0x1800cf529  mov     [r13+90h], rax
0x1800cf530  mov     qword ptr [rsp+2D8h+pAptQualifier], rax
0x1800cf535  lea     r9, [rsp+2D8h+pAptQualifier]
0x1800cf53a  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cf541  xor     edx, edx
0x1800cf543  xor     ecx, ecx
0x1800cf545  call    CDesktopFolder_CreateInstanceWithBindContext
0x1800cf54a  mov     [rsp+2D8h+pAptType], eax
0x1800cf54e  test    eax, eax
0x1800cf550  js      short loc_1800CF5B5
0x1800cf552  mov     rdx, [rsp+2D8h+ppMalloc]
0x1800cf557  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800cf55c  lea     r8, [r13+90h]
0x1800cf563  mov     rax, [rcx]
0x1800cf566  cmp     word ptr [rdx], 0
0x1800cf56a  jz      loc_1800CF622
0x1800cf570  mov     qword ptr [rsp+2D8h+cchValue], r8
0x1800cf575  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800cf57c  xor     r8d, r8d
0x1800cf57f  mov     rax, [rax+28h]
0x1800cf583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf588  mov     [rsp+2D8h+pAptType], eax
0x1800cf58c  test    eax, eax
0x1800cf58e  js      short loc_1800CF5A4
0x1800cf590  mov     ecx, 80004005h
0x1800cf595  cmp     qword ptr [r13+90h], 0
0x1800cf59d  cmovz   eax, ecx
0x1800cf5a0  mov     [rsp+2D8h+pAptType], eax
0x1800cf5a4  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800cf5a9  mov     rax, [rcx]
0x1800cf5ac  mov     rax, [rax+10h]
0x1800cf5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf5b5  mov     rcx, [rsp+2D8h+ppMalloc]; pv
0x1800cf5ba  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
