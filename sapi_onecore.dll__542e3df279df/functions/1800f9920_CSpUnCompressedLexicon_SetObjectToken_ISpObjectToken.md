# CSpUnCompressedLexicon::SetObjectToken(ISpObjectToken *)

- ea: `0x1800f9920`
- end: `0x1800f9fe1`
- name: `?SetObjectToken@CSpUnCompressedLexicon@@UEAAJPEAUISpObjectToken@@@Z`
- size: `1729`
- prototype: `__int64 __fastcall(CSpUnCompressedLexicon *__hidden this, struct ISpObjectToken *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000e518`
- `0x180013ec0`
- `0x18001d5a0`
- `0x18001f5dc`
- `0x18003ccb4`
- `0x180045938`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007aae4`
- `0x18009c8fc`
- `0x1800a72a4`
- `0x1800f69c8`
- `0x1800f70f4`
- `0x1800f9920`
- `0x1800f9fe8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f99e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f9a0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f99e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f9a0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800f9a3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800f9a3a`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800f9b06`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800f9b06`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800f9ad7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800f9ad7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f9975`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f9975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f9987`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f9fb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f9987`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f9fb2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800f9d85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800f9d85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9e91`

## string_xrefs

- `0x1800f9ee9`: `... Created user lexicon.`
- `0x1800f9f7a`: `... Created user shortcut.`
- `0x1800f9f81`: `... Created application lexicon.`
- `0x1800f9f9d`: `... Failed to create lexicon (%d).`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSpUnCompressedLexicon::SetObjectToken(CSpUnCompressedLexicon *this, struct ISpObjectToken *a2)
{
  CSpUnCompressedLexicon *v4; // r13
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  unsigned int v6; // r15d
  signed int Win32Error; // ebx
  const unsigned __int16 *FolderPath; // rax
  int v10; // eax
  PCNZWCH *v11; // r12
  unsigned __int64 v12; // rax
  PCNZWCH *v13; // rax
  int v14; // esi
  int v15; // eax
  char v16; // si
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int i; // esi
  unsigned int j; // esi
  const char *v22; // rdx
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH lpString2; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v26; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *EndPtr; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+68h] [rbp-98h]
  unsigned __int64 v29; // [rsp+70h] [rbp-90h]
  _BYTE v30[128]; // [rsp+80h] [rbp-80h] BYREF

  v4 = (CSpUnCompressedLexicon *)((char *)this - 16);
  v29 = ((unsigned __int64)this + 8) & -(__int64)(this != (CSpUnCompressedLexicon *)16);
  v5 = (struct _RTL_CRITICAL_SECTION *)(v29 + 8);
  v28 = (struct _RTL_CRITICAL_SECTION *)(v29 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
  v6 = 0;
  if ( !a2 )
  {
    LeaveCriticalSection(v5);
    return 2147500035LL;
  }
  Win32Error = SpGenericSetObjectToken(a2, (char *)this + 664);
  if ( Win32Error >= 0 )
  {
    lpString2 = 0;
    Win32Error = ((__int64 (__fastcall *)(struct ISpObjectToken *, PCNZWCH *))a2->lpVtbl->GetId)(a2, &lpString2);
    if ( Win32Error >= 0 )
    {
      if ( (unsigned int)_o__wcsicmp(
                           lpString2,
                           L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Speech_OneCore\\CurrentUserLexicon") )
      {
        if ( (unsigned int)_o__wcsicmp(
                             lpString2,
                             L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Speech_OneCore\\CurrentUserShortcut") )
        {
          if ( (unsigned int)_o__wcsnicmp(lpString2) )
          {
            *((_DWORD *)this + 17) = 2;
            DoTraceMessage(16, "Creating application lexicon (%S) ...", lpString2);
          }
          else
          {
            *((_DWORD *)this + 17) = 64;
            DoTraceMessage(16, "Creating text normalizer shortcut (%S) ...", lpString2);
          }
        }
        else
        {
          *((_DWORD *)this + 17) = 64;
          DoTraceMessage(16, "Creating user shortcut (%S) ...", lpString2);
        }
      }
      else
      {
        *((_DWORD *)this + 17) = 1;
        DoTraceMessage(16, "Creating user lexicon (%S) ...", lpString2);
      }
    }
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpString2);
  }
  if ( *((_DWORD *)v4 + 21) != 2 && *((_BYTE *)this + 66) )
  {
    *((_DWORD *)this + 163) = 1;
    goto LABEL_20;
  }
  if ( Win32Error < 0 )
    goto LABEL_24;
  String = 0;
  if ( ((int (__fastcall *)(struct ISpObjectToken *, const wchar_t *, wchar_t **))a2->lpVtbl->GetStringValue)(
         a2,
         L"FlushRate",
         &String) < 0 )
  {
    *((_DWORD *)this + 163) = 10;
    _o__itow_s(10, v30, 64, 10);
    Win32Error = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, _BYTE *))a2->lpVtbl->SetStringValue)(
                   a2,
                   L"FlushRate",
                   v30);
LABEL_20:
    if ( Win32Error < 0 )
      goto LABEL_24;
    goto LABEL_21;
  }
  EndPtr = 0;
  *((_DWORD *)this + 163) = wcstol(String, &EndPtr, 10);
  CoTaskMemFree(String);
LABEL_21:
  String = 0;
  v23 = 0;
  FolderPath = CSpUnCompressedLexicon::GetFolderPath(v4, &v23);
  v10 = ((__int64 (__fastcall *)(struct ISpObjectToken *, GUID *, const wchar_t *, const unsigned __int16 *, unsigned int, wchar_t **))a2->lpVtbl->GetStorageFileName)(
          a2,
          &CLSID_SpUnCompressedLexicon,
          L"Datafile",
          FolderPath,
          v23 | 0x8000,
          &String);
  Win32Error = v10;
  if ( v10 >= 0 )
    Win32Error = CSpUnCompressedLexicon::Init(v4, String, v10 == 1);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&String);
LABEL_24:
  if ( *((_DWORD *)this + 17) == 1 )
  {
    String = 0;
    EndPtr = 0;
    if ( Win32Error >= 0 )
      Win32Error = SpEnumTokens(
                     L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AppLexicons",
                     0,
                     0,
                     (struct IEnumSpObjectTokens **)&String);
    v23 = 0;
    if ( Win32Error == 1 )
    {
      Win32Error = 0;
      v11 = 0;
      goto LABEL_46;
    }
    if ( !Win32Error )
      Win32Error = (*(__int64 (__fastcall **)(wchar_t *, unsigned int *, __int64))(*(_QWORD *)String + 64LL))(
                     String,
                     &v23,
                     -1);
    v11 = 0;
    if ( Win32Error >= 0 )
    {
      if ( v23 )
      {
        v12 = 8LL * v23;
        if ( !is_mul_ok(v23, 8u) )
          v12 = -1;
        v13 = (PCNZWCH *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
        v11 = v13;
        if ( !v13 )
        {
          Win32Error = -2147024882;
          goto LABEL_46;
        }
        memset_0(v13, 0, 8LL * v23);
      }
      if ( v23 )
      {
        v14 = 0;
        LODWORD(lpString2) = 0;
        do
        {
          Win32Error = (*(__int64 (__fastcall **)(wchar_t *, __int64, wchar_t **, PCNZWCH *))(*(_QWORD *)String + 24LL))(
                         String,
                         1,
                         &EndPtr,
                         &lpString2);
          if ( Win32Error )
            break;
          Win32Error = (*(__int64 (__fastcall **)(wchar_t *, PCNZWCH *))(*(_QWORD *)EndPtr + 128LL))(EndPtr, &v11[v14]);
          ATL::CComPtr<ISpStreamFormat>::operator=(&EndPtr, 0);
          v15 = v14 + 1;
          if ( Win32Error < 0 )
            v15 = v14;
          v14 = v15;
        }
        while ( Win32Error >= 0 );
        if ( Win32Error >= 0 )
          Win32Error = v23 != v14 ? 0x80004005 : 0;
      }
    }
LABEL_46:
    v26 = 0;
    v16 = 0;
    if ( Win32Error >= 0 )
    {
      Win32Error = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, struct IUnknown **))a2->lpVtbl->OpenKey)(
                     a2,
                     L"AppLexicons",
                     &v26);
      if ( Win32Error == -2147200966 )
      {
        v16 = 1;
        Win32Error = 0;
      }
      while ( 1 )
      {
        if ( Win32Error < 0 )
          goto LABEL_57;
        if ( v6 >= v23 )
          break;
        if ( v16 )
          goto LABEL_57;
        lpString2 = 0;
        v17 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, PCNZWCH *))v26->lpVtbl[4].Release)(
                v26,
                v6,
                &lpString2);
        Win32Error = v17;
        if ( v17 < 0 )
        {
          if ( v17 == -2147200967 )
          {
            v16 = 1;
            Win32Error = 0;
LABEL_80:
            SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpString2);
            goto LABEL_57;
          }
        }
        else
        {
          v18 = CompareStringW(0x409u, 1u, v11[v6], -1, lpString2, -1);
          if ( v18 )
          {
            if ( v18 != 2 )
            {
              v16 = 1;
              SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpString2);
              goto LABEL_57;
            }
          }
          else
          {
            Win32Error = SpHrFromLastWin32Error();
          }
        }
        SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpString2);
        ++v6;
      }
      if ( !v16 )
      {
        if ( v6 >= v23 )
        {
          lpString2 = 0;
          Win32Error = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, PCNZWCH *))v26->lpVtbl[4].Release)(
                         v26,
                         v6,
                         &lpString2);
          if ( Win32Error < 0 )
          {
            if ( Win32Error == -2147200967 )
              Win32Error = 0;
          }
          else
          {
            v16 = 1;
          }
          goto LABEL_80;
        }
        v16 = 1;
      }
    }
LABEL_57:
    if ( v26 )
      ATL::AtlComPtrAssign(&v26, 0);
    if ( Win32Error >= 0 )
    {
      if ( v16 )
      {
        Win32Error = CSpUnCompressedLexicon::SetTooMuchChange(v4);
        if ( Win32Error >= 0 )
        {
          lpString2 = 0;
          Win32Error = CSpAutoMutexLock::Init((CSpAutoMutexLock *)&lpString2, *((void **)this + 80), v19);
          if ( Win32Error >= 0 )
          {
            Win32Error = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *))a2->lpVtbl->DeleteKey)(
                           a2,
                           L"AppLexicons");
            if ( Win32Error >= 0 )
              Win32Error = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, struct IUnknown **))a2->lpVtbl->CreateKey)(
                             a2,
                             L"AppLexicons",
                             &v26);
          }
          for ( i = 0;
                Win32Error >= 0;
                Win32Error = ((__int64 (__fastcall *)(struct IUnknown *, PCNZWCH, const WCHAR *))v26->lpVtbl[1].Release)(
                               v26,
                               v11[i++],
                               &cchOriginalDestLength) )
          {
            if ( i >= v23 )
              break;
          }
          CSpAutoMutexLock::~CSpAutoMutexLock((CSpAutoMutexLock *)&lpString2);
        }
      }
    }
    if ( v11 )
    {
      for ( j = 0; j < v23; ++j )
        CoTaskMemFree((LPVOID)v11[j]);
      operator delete(v11);
    }
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v26);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&EndPtr);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&String);
    v5 = v28;
  }
  if ( Win32Error < 0 )
  {
    DoTraceMessage(2, "... Failed to create lexicon (%d).", Win32Error);
  }
  else
  {
    *((_BYTE *)this + 64) = 1;
    if ( *((_DWORD *)this + 17) == 1 )
    {
      DoTraceMessage(16, "... Created user lexicon.");
    }
    else
    {
      v22 = "... Created user shortcut.";
      if ( *((_DWORD *)this + 17) != 64 )
        v22 = "... Created application lexicon.";
      DoTraceMessage(16, v22);
    }
  }
  LeaveCriticalSection(v5);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800f9920  mov     [rsp-8+arg_10], rbx
0x1800f9925  push    rbp
0x1800f9926  push    rsi
0x1800f9927  push    rdi
0x1800f9928  push    r12
0x1800f992a  push    r13
0x1800f992c  push    r14
0x1800f992e  push    r15
0x1800f9930  lea     rbp, [rsp-10h]
0x1800f9935  sub     rsp, 110h
0x1800f993c  mov     rax, cs:__security_cookie
0x1800f9943  xor     rax, rsp
0x1800f9946  mov     [rbp+40h+var_40], rax
0x1800f994a  mov     r14, rdx
0x1800f994d  mov     rdi, rcx
0x1800f9950  lea     r13, [rcx-10h]
0x1800f9954  mov     rax, r13
0x1800f9957  lea     rdx, [rcx+8]
0x1800f995b  neg     rax
0x1800f995e  sbb     r8, r8
0x1800f9961  and     r8, rdx
0x1800f9964  mov     [rsp+140h+var_D0], r8
0x1800f9969  lea     rsi, [r8+8]
0x1800f996d  mov     [rsp+140h+var_D8], rsi
0x1800f9972  mov     rcx, rsi; lpCriticalSection
0x1800f9975  call    cs:__imp_EnterCriticalSection
0x1800f997b  nop
0x1800f997c  xor     r15d, r15d
0x1800f997f  test    r14, r14
0x1800f9982  jnz     short loc_1800F9997
0x1800f9984  mov     rcx, rsi; lpCriticalSection
0x1800f9987  call    cs:__imp_LeaveCriticalSection
0x1800f998d  mov     eax, 80004003h
0x1800f9992  jmp     loc_1800F9FBA
0x1800f9997  lea     rdx, [rdi+298h]
0x1800f999e  mov     rcx, r14
0x1800f99a1  call    ?SpGenericSetObjectToken@@YAJPEAUISpObjectToken@@AEAV?$CComPtr@UISpObjectToken@@@ATL@@@Z; SpGenericSetObjectToken(ISpObjectToken *,ATL::CComPtr<ISpObjectToken> &)
0x1800f99a6  mov     ebx, eax
0x1800f99a8  mov     r12d, 10h
0x1800f99ae  test    eax, eax
0x1800f99b0  js      loc_1800F9A7A
0x1800f99b6  mov     [rsp+140h+var_F8], r15
0x1800f99bb  mov     rax, [r14]
0x1800f99be  lea     rdx, [rsp+140h+var_F8]
0x1800f99c3  mov     rcx, r14
0x1800f99c6  mov     rax, [rax+80h]
0x1800f99cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f99d2  mov     ebx, eax
0x1800f99d4  test    eax, eax
0x1800f99d6  js      loc_1800F9A70
0x1800f99dc  lea     rdx, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800f99e3  mov     rcx, [rsp+140h+var_F8]
0x1800f99e8  call    cs:__imp__o__wcsicmp
0x1800f99ee  test    eax, eax
0x1800f99f0  jnz     short loc_1800F9A02
0x1800f99f2  mov     dword ptr [rdi+44h], 1
0x1800f99f9  lea     rdx, aCreatingUserLe; "Creating user lexicon (%S) ..."
0x1800f9a00  jmp     short loc_1800F9A62
0x1800f9a02  lea     rdx, aHkeyCurrentUse_1; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800f9a09  mov     rcx, [rsp+140h+var_F8]
0x1800f9a0e  call    cs:__imp__o__wcsicmp
0x1800f9a14  test    eax, eax
0x1800f9a16  jnz     short loc_1800F9A28
0x1800f9a18  mov     dword ptr [rdi+44h], 40h ; '@'
0x1800f9a1f  lea     rdx, aCreatingUserSh; "Creating user shortcut (%S) ..."
0x1800f9a26  jmp     short loc_1800F9A62
0x1800f9a28  mov     r8d, 44h ; 'D'
0x1800f9a2e  lea     rdx, aHkeyLocalMachi_11; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800f9a35  mov     rcx, [rsp+140h+var_F8]
0x1800f9a3a  call    cs:__imp__o__wcsnicmp
0x1800f9a40  test    eax, eax
0x1800f9a42  jnz     short loc_1800F9A54
0x1800f9a44  mov     dword ptr [rdi+44h], 40h ; '@'
0x1800f9a4b  lea     rdx, aCreatingTextNo; "Creating text normalizer shortcut (%S) "...
0x1800f9a52  jmp     short loc_1800F9A62
0x1800f9a54  mov     dword ptr [rdi+44h], 2
0x1800f9a5b  lea     rdx, aCreatingApplic; "Creating application lexicon (%S) ..."
0x1800f9a62  mov     r8, [rsp+140h+var_F8]
0x1800f9a67  mov     ecx, r12d; int
0x1800f9a6a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f9a6f  nop
0x1800f9a70  lea     rcx, [rsp+140h+var_F8]; this
0x1800f9a75  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800f9a7a  cmp     dword ptr [r13+54h], 2
0x1800f9a7f  jz      short loc_1800F9A96
0x1800f9a81  cmp     [rdi+42h], r15b
0x1800f9a85  jz      short loc_1800F9A96
0x1800f9a87  mov     dword ptr [rdi+28Ch], 1
0x1800f9a91  jmp     loc_1800F9B28
0x1800f9a96  test    ebx, ebx
0x1800f9a98  js      loc_1800F9BA8
0x1800f9a9e  mov     [rsp+140h+String], r15
0x1800f9aa3  mov     rax, [r14]
0x1800f9aa6  lea     r8, [rsp+140h+String]
0x1800f9aab  lea     rdx, aFlushrate; "FlushRate"
0x1800f9ab2  mov     rcx, r14
0x1800f9ab5  mov     rax, [rax+30h]
0x1800f9ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9abe  test    eax, eax
0x1800f9ac0  js      short loc_1800F9AF0
0x1800f9ac2  mov     [rsp+140h+EndPtr], r15
0x1800f9ac7  mov     r8d, 0Ah; Radix
0x1800f9acd  lea     rdx, [rsp+140h+EndPtr]; EndPtr
0x1800f9ad2  mov     rcx, [rsp+140h+String]; String
0x1800f9ad7  call    cs:__imp_wcstol
0x1800f9add  mov     [rdi+28Ch], eax
0x1800f9ae3  mov     rcx, [rsp+140h+String]; pv
0x1800f9ae8  call    cs:__imp_CoTaskMemFree
0x1800f9aee  jmp     short loc_1800F9B2C
0x1800f9af0  mov     ecx, 0Ah
0x1800f9af5  mov     [rdi+28Ch], ecx
0x1800f9afb  mov     r9d, ecx
0x1800f9afe  lea     r8d, [rcx+36h]
0x1800f9b02  lea     rdx, [rbp+40h+var_C0]
0x1800f9b06  call    cs:__imp__o__itow_s
0x1800f9b0c  mov     rax, [r14]
0x1800f9b0f  lea     r8, [rbp+40h+var_C0]
0x1800f9b13  lea     rdx, aFlushrate; "FlushRate"
0x1800f9b1a  mov     rcx, r14
0x1800f9b1d  mov     rax, [rax+28h]
0x1800f9b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9b26  mov     ebx, eax
0x1800f9b28  test    ebx, ebx
0x1800f9b2a  js      short loc_1800F9BA8
0x1800f9b2c  mov     [rsp+140h+String], r15
0x1800f9b31  mov     [rsp+140h+var_100], r15d
0x1800f9b36  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x1800f9b3b  mov     rcx, r13; this
0x1800f9b3e  call    ?GetFolderPath@CSpUnCompressedLexicon@@AEAAPEBGPEAK@Z; CSpUnCompressedLexicon::GetFolderPath(ulong *)
0x1800f9b43  mov     rcx, [r14]
0x1800f9b46  mov     edx, [rsp+140h+var_100]
0x1800f9b4a  bts     edx, 0Fh
0x1800f9b4e  mov     r10, [rcx+98h]
0x1800f9b55  lea     rcx, [rsp+140h+String]
0x1800f9b5a  mov     qword ptr [rsp+140h+cchCount2], rcx
0x1800f9b5f  mov     dword ptr [rsp+140h+lpString2], edx
0x1800f9b63  mov     r9, rax
0x1800f9b66  lea     r8, aDatafile_0; "Datafile"
0x1800f9b6d  lea     rdx, CLSID_SpUnCompressedLexicon
0x1800f9b74  mov     rcx, r14
0x1800f9b77  mov     rax, r10
0x1800f9b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9b7f  mov     ebx, eax
0x1800f9b81  test    eax, eax
0x1800f9b83  js      short loc_1800F9B9E
0x1800f9b85  mov     r8d, r15d
0x1800f9b88  cmp     eax, 1
0x1800f9b8b  setz    r8b; int
0x1800f9b8f  mov     rdx, [rsp+140h+String]; unsigned __int16 *
0x1800f9b94  mov     rcx, r13; this
0x1800f9b97  call    ?Init@CSpUnCompressedLexicon@@AEAAJPEBGH@Z; CSpUnCompressedLexicon::Init(ushort const *,int)
0x1800f9b9c  mov     ebx, eax
0x1800f9b9e  lea     rcx, [rsp+140h+String]; this
0x1800f9ba3  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800f9ba8  cmp     dword ptr [rdi+44h], 1
0x1800f9bac  jnz     loc_1800F9ED3
0x1800f9bb2  mov     [rsp+140h+String], r15
0x1800f9bb7  mov     [rsp+140h+EndPtr], r15
0x1800f9bbc  test    ebx, ebx
0x1800f9bbe  js      short loc_1800F9BD8
0x1800f9bc0  lea     r9, [rsp+140h+String]; struct IEnumSpObjectTokens **
0x1800f9bc5  xor     r8d, r8d; unsigned __int16 *
0x1800f9bc8  xor     edx, edx; unsigned __int16 *
0x1800f9bca  lea     rcx, aHkeyLocalMachi_6; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800f9bd1  call    ?SpEnumTokens@@YAJPEBG00PEAPEAUIEnumSpObjectTokens@@@Z; SpEnumTokens(ushort const *,ushort const *,ushort const *,IEnumSpObjectTokens * *)
0x1800f9bd6  mov     ebx, eax
0x1800f9bd8  mov     [rsp+140h+var_100], r15d
0x1800f9bdd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f9be1  cmp     ebx, 1
0x1800f9be4  jnz     short loc_1800F9BF1
0x1800f9be6  mov     ebx, r15d
0x1800f9be9  mov     r12, r15
0x1800f9bec  jmp     loc_1800F9CE1
0x1800f9bf1  test    ebx, ebx
0x1800f9bf3  jnz     short loc_1800F9C11
0x1800f9bf5  mov     rcx, [rsp+140h+String]
0x1800f9bfa  mov     rax, [rcx]
0x1800f9bfd  lea     rdx, [rsp+140h+var_100]
0x1800f9c02  mov     rax, [rax+40h]
0x1800f9c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c0b  mov     ebx, eax
0x1800f9c0d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f9c11  mov     r12, r15
0x1800f9c14  test    ebx, ebx
0x1800f9c16  js      loc_1800F9CE1
0x1800f9c1c  mov     eax, [rsp+140h+var_100]
0x1800f9c20  test    eax, eax
0x1800f9c22  jz      short loc_1800F9C66
0x1800f9c24  mov     ecx, eax
0x1800f9c26  mov     eax, 8
0x1800f9c2b  mul     rcx
0x1800f9c2e  cmovb   rax, r8
0x1800f9c32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f9c39  mov     rcx, rax; unsigned __int64
0x1800f9c3c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f9c41  mov     r12, rax
0x1800f9c44  test    rax, rax
0x1800f9c47  jnz     short loc_1800F9C53
0x1800f9c49  mov     ebx, 8007000Eh
0x1800f9c4e  jmp     loc_1800F9CE1
0x1800f9c53  mov     r8d, [rsp+140h+var_100]
0x1800f9c58  shl     r8, 3; Size
0x1800f9c5c  xor     edx, edx; Val
0x1800f9c5e  mov     rcx, rax; void *
0x1800f9c61  call    memset_0
0x1800f9c66  cmp     [rsp+140h+var_100], r15d
0x1800f9c6b  jz      short loc_1800F9CE1
0x1800f9c6d  mov     esi, r15d
0x1800f9c70  mov     dword ptr [rsp+140h+var_F8], r15d
0x1800f9c75  mov     rcx, [rsp+140h+String]
0x1800f9c7a  mov     rax, [rcx]
0x1800f9c7d  lea     r9, [rsp+140h+var_F8]
0x1800f9c82  lea     r8, [rsp+140h+EndPtr]
0x1800f9c87  mov     edx, 1
0x1800f9c8c  mov     rax, [rax+18h]
0x1800f9c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c95  mov     ebx, eax
0x1800f9c97  test    eax, eax
0x1800f9c99  jnz     short loc_1800F9CCF
0x1800f9c9b  mov     rcx, [rsp+140h+EndPtr]
0x1800f9ca0  mov     r8, [rcx]
0x1800f9ca3  mov     eax, esi
0x1800f9ca5  lea     rdx, [r12+rax*8]
0x1800f9ca9  mov     rax, [r8+80h]
0x1800f9cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9cb5  mov     ebx, eax
0x1800f9cb7  xor     edx, edx
0x1800f9cb9  lea     rcx, [rsp+140h+EndPtr]
0x1800f9cbe  call    ??4?$CComPtr@UISpStreamFormat@@@ATL@@QEAAPEAUISpStreamFormat@@PEAU2@@Z; ATL::CComPtr<ISpStreamFormat>::operator=(ISpStreamFormat *)
0x1800f9cc3  lea     eax, [rsi+1]
0x1800f9cc6  test    ebx, ebx
0x1800f9cc8  cmovs   eax, esi
0x1800f9ccb  mov     esi, eax
0x1800f9ccd  jns     short loc_1800F9C75
0x1800f9ccf  test    ebx, ebx
0x1800f9cd1  js      short loc_1800F9CE1
0x1800f9cd3  sub     esi, [rsp+140h+var_100]
0x1800f9cd7  neg     esi
0x1800f9cd9  sbb     ebx, ebx
0x1800f9cdb  and     ebx, 80004005h
0x1800f9ce1  mov     [rsp+140h+var_E8], r15
0x1800f9ce6  mov     sil, r15b
0x1800f9ce9  test    ebx, ebx
0x1800f9ceb  js      loc_1800F9DB1
0x1800f9cf1  mov     rax, [r14]
0x1800f9cf4  lea     r8, [rsp+140h+var_E8]
0x1800f9cf9  lea     rdx, aApplexicons; "AppLexicons"
0x1800f9d00  mov     rcx, r14
0x1800f9d03  mov     rax, [rax+48h]
0x1800f9d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9d0c  mov     ebx, eax
0x1800f9d0e  cmp     eax, 8004503Ah
0x1800f9d13  jnz     short loc_1800F9D1B
0x1800f9d15  mov     sil, 1
0x1800f9d18  mov     ebx, r15d
0x1800f9d1b  test    ebx, ebx
0x1800f9d1d  js      loc_1800F9DB1
0x1800f9d23  cmp     r15d, [rsp+140h+var_100]
0x1800f9d28  jnb     loc_1800F9F26
0x1800f9d2e  test    sil, sil
0x1800f9d31  jnz     short loc_1800F9DB1
0x1800f9d33  mov     [rsp+140h+var_F8], 0
0x1800f9d3c  mov     rcx, [rsp+140h+var_E8]
0x1800f9d41  mov     rax, [rcx]
0x1800f9d44  lea     r8, [rsp+140h+var_F8]
0x1800f9d49  mov     edx, r15d
0x1800f9d4c  mov     rax, [rax+70h]
0x1800f9d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9d55  mov     ebx, eax
0x1800f9d57  test    eax, eax
0x1800f9d59  js      loc_1800F9EF5
0x1800f9d5f  mov     rax, [rsp+140h+var_F8]
0x1800f9d64  mov     r8d, r15d
0x1800f9d67  mov     [rsp+140h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800f9d6f  mov     [rsp+140h+lpString2], rax; lpString2
0x1800f9d74  or      r9d, 0FFFFFFFFh; cchCount1
0x1800f9d78  mov     r8, [r12+r8*8]; lpString1
0x1800f9d7c  lea     edx, [r9+2]; dwCmpFlags
0x1800f9d80  mov     ecx, 409h; Locale
0x1800f9d85  call    cs:__imp_CompareStringW
0x1800f9d8b  test    eax, eax
0x1800f9d8d  jnz     short loc_1800F9D9B
0x1800f9d8f  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f9d94  mov     ebx, eax
0x1800f9d96  jmp     loc_1800F9EFC
0x1800f9d9b  cmp     eax, 2
0x1800f9d9e  jz      loc_1800F9EFC
0x1800f9da4  mov     sil, 1
0x1800f9da7  lea     rcx, [rsp+140h+var_F8]; this
0x1800f9dac  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800f9db1  xor     r15d, r15d
0x1800f9db4  cmp     [rsp+140h+var_E8], r15
0x1800f9db9  jz      short loc_1800F9DC7
0x1800f9dbb  xor     edx, edx; struct IUnknown *
0x1800f9dbd  lea     rcx, [rsp+140h+var_E8]; struct IUnknown **
0x1800f9dc2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f9dc7  test    ebx, ebx
0x1800f9dc9  js      loc_1800F9E7C
0x1800f9dcf  test    sil, sil
0x1800f9dd2  jz      loc_1800F9E7C
  ... truncated ...
```
