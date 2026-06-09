# CShellItem::GetParentAndItem(_ITEMIDLIST_ABSOLUTE * *,IShellFolder * *,_ITEMID_CHILD * *)

- ea: `0x180060a40`
- end: `0x180061082`
- name: `?GetParentAndItem@CShellItem@@UEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIShellFolder@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1602`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct _ITEMIDLIST_ABSOLUTE **, struct IShellFolder **, struct _ITEMID_CHILD **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005ee50`
- `0x18005f600`
- `0x180060a40`
- `0x180061860`
- `0x180061960`
- `0x1800625e0`
- `0x1800899a4`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180060e14`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180060e14`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18006100b`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18006100b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060cee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060cee`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180060b3a`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180060b3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060af4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060c08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060c08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060d71`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180060c3b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180060d9b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180060c3b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180060d9b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180060ad9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180060ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006105e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006105e`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180060e44`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180060e44`

## string_xrefs

- `0x180060f72`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

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
0x180060a40  push    rbx
0x180060a42  push    rbp
0x180060a43  push    rsi
0x180060a44  push    rdi
0x180060a45  push    r12
0x180060a47  push    r13
0x180060a49  push    r14
0x180060a4b  push    r15
0x180060a4d  sub     rsp, 298h
0x180060a54  mov     rax, cs:__security_cookie
0x180060a5b  xor     rax, rsp
0x180060a5e  mov     [rsp+2D8h+var_58], rax
0x180060a66  mov     r15, r9
0x180060a69  mov     r14, r8
0x180060a6c  mov     r12, rdx
0x180060a6f  mov     r13, rcx
0x180060a72  xor     eax, eax
0x180060a74  test    rdx, rdx
0x180060a77  jz      short loc_180060A7C
0x180060a79  mov     [rdx], rax
0x180060a7c  test    r14, r14
0x180060a7f  jz      short loc_180060A84
0x180060a81  mov     [r8], rax
0x180060a84  test    r15, r15
0x180060a87  jz      short loc_180060A8C
0x180060a89  mov     [r9], rax
0x180060a8c  lea     rdi, [rcx-20h]
0x180060a90  test    rdi, rdi
0x180060a93  jz      loc_180060DFF
0x180060a99  lea     rsi, [rcx+30h]
0x180060a9d  mov     [rsp+2D8h+var_298], rsi
0x180060aa2  mov     ebx, [rsi+2Ch]
0x180060aa5  cmp     ebx, 2
0x180060aa8  jz      short loc_180060ABF
0x180060aaa  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180060ab0  test    eax, eax
0x180060ab2  jz      loc_180060E07
0x180060ab8  cmp     eax, 1
0x180060abb  jnz     short loc_180060B37
0x180060abd  xor     eax, eax
0x180060abf  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x180060ac3  jz      short loc_180060B37
0x180060ac5  mov     ebp, eax
0x180060ac7  mov     [rsp+2D8h+pAptType], eax
0x180060acb  mov     [rsp+2D8h+pAptQualifier], eax
0x180060acf  lea     rdx, [rsp+2D8h+pAptQualifier]; pAptQualifier
0x180060ad4  lea     rcx, [rsp+2D8h+pAptType]; pAptType
0x180060ad9  call    cs:__imp_CoGetApartmentType
0x180060ae0  nop     dword ptr [rax+rax+00h]
0x180060ae5  mov     ebx, eax
0x180060ae7  test    eax, eax
0x180060ae9  js      short loc_180060B27
0x180060aeb  mov     ecx, [rsp+2D8h+pAptType]
0x180060aef  cmp     ecx, 3
0x180060af2  jnz     short loc_180060B04
0x180060af4  call    cs:__imp_GetCurrentThreadId
0x180060afb  nop     dword ptr [rax+rax+00h]
0x180060b00  mov     ebp, eax
0x180060b02  jmp     short loc_180060B1E
0x180060b04  test    ecx, ecx
0x180060b06  jz      short loc_180060AF4
0x180060b08  sub     ecx, 1
0x180060b0b  jz      loc_180060F88
0x180060b11  cmp     ecx, 1
0x180060b14  jz      loc_180060FCD
0x180060b1a  test    eax, eax
0x180060b1c  js      short loc_180060B27
0x180060b1e  cmp     ebp, [rsi+28h]
0x180060b21  jnz     loc_18006102C
0x180060b27  mov     rcx, [rsp+2D8h]; this
0x180060b2f  test    ebx, ebx
0x180060b31  js      loc_180060F6F
0x180060b37  mov     rcx, rsi; lpCriticalSection
0x180060b3a  call    cs:__imp_TryEnterCriticalSection
0x180060b41  nop     dword ptr [rax+rax+00h]
0x180060b46  mov     ebx, 8001010Eh
0x180060b4b  xor     ecx, ecx
0x180060b4d  test    eax, eax
0x180060b4f  cmovnz  ebx, ecx
0x180060b52  mov     [rsp+2D8h+var_290], ebx
0x180060b56  mov     ebp, ebx
0x180060b58  test    ebx, ebx
0x180060b5a  jns     short loc_180060B92
0x180060b5c  test    r14, r14
0x180060b5f  jnz     loc_180061036
0x180060b65  test    r12, r12
0x180060b68  jnz     loc_18006105A
0x180060b6e  test    r15, r15
0x180060b71  jz      loc_180060CE7
0x180060b77  mov     rcx, [r15]; pv
0x180060b7a  call    cs:__imp_CoTaskMemFree
0x180060b81  nop     dword ptr [rax+rax+00h]
0x180060b86  mov     qword ptr [r15], 0
0x180060b8d  jmp     loc_180060CE7
0x180060b92  test    r14, r14
0x180060b95  jz      short loc_180060BC7
0x180060b97  mov     qword ptr [r14], 0
0x180060b9e  lea     rax, [r13+90h]
0x180060ba5  cmp     qword ptr [rax], 0
0x180060ba9  jz      loc_180060E67
0x180060baf  mov     rcx, [rax]
0x180060bb2  mov     rax, [rcx]
0x180060bb5  mov     r8, r14
0x180060bb8  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180060bbf  mov     rax, [rax]
0x180060bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bc7  test    r12, r12
0x180060bca  jnz     loc_180060D21
0x180060bd0  test    r15, r15
0x180060bd3  jz      loc_180060CAE
0x180060bd9  mov     rax, [r13+70h]
0x180060bdd  mov     [rsp+2D8h+Src], rax
0x180060be2  test    rax, rax
0x180060be5  jz      loc_180060CAB
0x180060beb  movzx   eax, word ptr [rax]
0x180060bee  mov     [rsp+2D8h+pAptQualifier], eax
0x180060bf2  mov     qword ptr [rsp+2D8h+pAptType], 0
0x180060bfb  lea     edx, [rax+2]
0x180060bfe  cmp     edx, eax
0x180060c00  jb      loc_180060CA6
0x180060c06  mov     ecx, edx; cb
0x180060c08  call    cs:__imp_CoTaskMemAlloc
0x180060c0f  nop     dword ptr [rax+rax+00h]
0x180060c14  mov     rdi, rax
0x180060c17  mov     qword ptr [rsp+2D8h+pAptType], rax
0x180060c1c  test    rax, rax
0x180060c1f  jz      loc_180060CA6
0x180060c25  xor     eax, eax
0x180060c27  mov     [rsp+2D8h+Size], rax
0x180060c2c  mov     [rsp+2D8h+ppMalloc], rax
0x180060c31  lea     rdx, [rsp+2D8h+ppMalloc]; ppMalloc
0x180060c36  mov     ecx, 1; dwMemContext
0x180060c3b  call    cs:__imp_CoGetMalloc
0x180060c42  nop     dword ptr [rax+rax+00h]
0x180060c47  test    eax, eax
0x180060c49  js      short loc_180060C75
0x180060c4b  mov     rcx, [rsp+2D8h+ppMalloc]
0x180060c50  mov     rdx, [rcx]
0x180060c53  mov     rax, [rdx+30h]
0x180060c57  mov     rdx, rdi
0x180060c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c5f  mov     [rsp+2D8h+Size], rax
0x180060c64  mov     rcx, [rsp+2D8h+ppMalloc]
0x180060c69  mov     r8, [rcx]
0x180060c6c  mov     rax, [r8+10h]
0x180060c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c75  mov     r8, [rsp+2D8h+Size]; Size
0x180060c7a  xor     edx, edx; Val
0x180060c7c  mov     rcx, rdi; void *
0x180060c7f  call    memset_0
0x180060c84  movzx   edi, word ptr [rsp+2D8h+pAptQualifier]
0x180060c89  mov     r8d, edi; Size
0x180060c8c  mov     rdx, [rsp+2D8h+Src]; Src
0x180060c91  mov     rcx, qword ptr [rsp+2D8h+pAptType]; void *
0x180060c96  call    memcpy_0
0x180060c9b  xor     eax, eax
0x180060c9d  mov     rcx, qword ptr [rsp+2D8h+pAptType]
0x180060ca2  mov     [rdi+rcx], ax
0x180060ca6  mov     rax, qword ptr [rsp+2D8h+pAptType]
0x180060cab  mov     [r15], rax
0x180060cae  cmp     qword ptr [r13+80h], 0
0x180060cb6  jz      short loc_180060CC1
0x180060cb8  test    r12, r12
0x180060cbb  jnz     loc_180060F5A
0x180060cc1  test    r14, r14
0x180060cc4  jz      short loc_180060CD0
0x180060cc6  cmp     qword ptr [r14], 0
0x180060cca  jz      loc_180060F65
0x180060cd0  test    r15, r15
0x180060cd3  jz      short loc_180060CDF
0x180060cd5  cmp     qword ptr [r15], 0
0x180060cd9  jz      loc_180060F65
0x180060cdf  test    ebp, ebp
0x180060ce1  js      loc_180060B5C
0x180060ce7  test    ebx, ebx
0x180060ce9  js      short loc_180060CFA
0x180060ceb  mov     rcx, rsi; lpCriticalSection
0x180060cee  call    cs:__imp_LeaveCriticalSection
0x180060cf5  nop     dword ptr [rax+rax+00h]
0x180060cfa  mov     eax, ebp
0x180060cfc  mov     rcx, [rsp+2D8h+var_58]
0x180060d04  xor     rcx, rsp; StackCookie
0x180060d07  call    __security_check_cookie
0x180060d0c  add     rsp, 298h
0x180060d13  pop     r15
0x180060d15  pop     r14
0x180060d17  pop     r13
0x180060d19  pop     r12
0x180060d1b  pop     rdi
0x180060d1c  pop     rsi
0x180060d1d  pop     rbp
0x180060d1e  pop     rbx
0x180060d1f  retn
0x180060d21  xor     ebp, ebp
0x180060d23  cmp     [rdi+0A0h], rbp
0x180060d2a  jz      loc_180060FA3
0x180060d30  test    ebp, ebp
0x180060d32  js      loc_180060BD0
0x180060d38  mov     rax, [r13+80h]
0x180060d3f  mov     qword ptr [rsp+2D8h+pAptType], rax
0x180060d44  test    rax, rax
0x180060d47  jz      loc_180060FD7
0x180060d4d  mov     rdx, rax
0x180060d50  mov     r8d, 2
0x180060d56  movzx   ecx, word ptr [rdx]
0x180060d59  test    cx, cx
0x180060d5c  jz      short loc_180060D66
0x180060d5e  add     r8d, ecx
0x180060d61  add     rdx, rcx
0x180060d64  jnz     short loc_180060D56
0x180060d66  mov     eax, r8d
0x180060d69  mov     [rsp+2D8h+Size], rax
0x180060d6e  mov     ecx, r8d; cb
0x180060d71  call    cs:__imp_CoTaskMemAlloc
0x180060d78  nop     dword ptr [rax+rax+00h]
0x180060d7d  mov     rdi, rax
0x180060d80  test    rax, rax
0x180060d83  jz      short loc_180060DF6
0x180060d85  xor     eax, eax
0x180060d87  mov     [rsp+2D8h+ppMalloc], rax
0x180060d8c  mov     qword ptr [rsp+2D8h+pAptQualifier], rax
0x180060d91  lea     rdx, [rsp+2D8h+pAptQualifier]; ppMalloc
0x180060d96  mov     ecx, 1; dwMemContext
0x180060d9b  call    cs:__imp_CoGetMalloc
0x180060da2  nop     dword ptr [rax+rax+00h]
0x180060da7  test    eax, eax
0x180060da9  js      short loc_180060DD5
0x180060dab  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x180060db0  mov     rax, [rcx]
0x180060db3  mov     rdx, rdi
0x180060db6  mov     rax, [rax+30h]
0x180060dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dbf  mov     [rsp+2D8h+ppMalloc], rax
0x180060dc4  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x180060dc9  mov     r9, [rcx]
0x180060dcc  mov     rax, [r9+10h]
0x180060dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dd5  mov     r8, [rsp+2D8h+ppMalloc]; Size
0x180060dda  xor     edx, edx; Val
0x180060ddc  mov     rcx, rdi; void *
0x180060ddf  call    memset_0
0x180060de4  mov     r8, [rsp+2D8h+Size]; Size
0x180060de9  mov     rdx, qword ptr [rsp+2D8h+pAptType]; Src
0x180060dee  mov     rcx, rdi; void *
0x180060df1  call    memcpy_0
0x180060df6  mov     [r12], rdi
0x180060dfa  jmp     loc_180060BD0
0x180060dff  mov     rsi, rax
0x180060e02  jmp     loc_180060A9D
0x180060e07  mov     r8d, 104h; nSize
0x180060e0d  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x180060e12  xor     ecx, ecx; hModule
0x180060e14  call    cs:__imp_GetModuleFileNameW
0x180060e1b  nop     dword ptr [rax+rax+00h]
0x180060e20  test    eax, eax
0x180060e22  jnz     loc_180060FE4
0x180060e28  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180060e2e  cmp     ecx, 1
0x180060e31  jnz     loc_180060B37
0x180060e37  cmp     ebx, ecx
0x180060e39  jnz     loc_180060ABD
0x180060e3f  mov     ecx, 10h
0x180060e44  call    cs:__imp_IsAppCompatModeEnabled
0x180060e4b  nop     dword ptr [rax+rax+00h]
0x180060e50  test    eax, eax
0x180060e52  jz      loc_180061077
0x180060e58  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180060e62  jmp     loc_180060B37
0x180060e67  mov     rcx, [r13+68h]; Src
0x180060e6b  mov     qword ptr [rax], 0
0x180060e72  test    rcx, rcx
0x180060e75  jz      loc_180060BC7
0x180060e7b  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x180060e80  mov     [rsp+2D8h+ppMalloc], rax
0x180060e85  test    rax, rax
0x180060e88  jz      loc_180060BC7
0x180060e8e  xor     eax, eax
0x180060e90  mov     [r13+90h], rax
0x180060e97  mov     qword ptr [rsp+2D8h+pAptQualifier], rax
0x180060e9c  lea     r9, [rsp+2D8h+pAptQualifier]
0x180060ea1  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x180060ea8  xor     edx, edx
0x180060eaa  xor     ecx, ecx
0x180060eac  call    CDesktopFolder_CreateInstanceWithBindContext
0x180060eb1  mov     [rsp+2D8h+pAptType], eax
0x180060eb5  test    eax, eax
0x180060eb7  js      short loc_180060F1C
0x180060eb9  mov     rdx, [rsp+2D8h+ppMalloc]
0x180060ebe  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x180060ec3  lea     r8, [r13+90h]
0x180060eca  mov     rax, [rcx]
0x180060ecd  cmp     word ptr [rdx], 0
0x180060ed1  jz      loc_180060F8F
0x180060ed7  mov     qword ptr [rsp+2D8h+cchValue], r8
0x180060edc  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180060ee3  xor     r8d, r8d
0x180060ee6  mov     rax, [rax+28h]
0x180060eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eef  mov     [rsp+2D8h+pAptType], eax
0x180060ef3  test    eax, eax
  ... truncated ...
```
