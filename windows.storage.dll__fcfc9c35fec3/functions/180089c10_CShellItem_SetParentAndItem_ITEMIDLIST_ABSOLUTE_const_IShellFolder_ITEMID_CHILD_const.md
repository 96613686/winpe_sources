# CShellItem::SetParentAndItem(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_ITEMID_CHILD const *)

- ea: `0x180089c10`
- end: `0x18008a181`
- name: `?SetParentAndItem@CShellItem@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@@Z`
- size: `1393`
- prototype: `int(CShellItem *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct IShellFolder *, const struct _ITEMID_CHILD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180045230`
- `0x180061860`
- `0x1800899a4`
- `0x180089c10`
- `0x18008a190`
- `0x1801b1844`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a016`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a016`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18008a130`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18008a130`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089f16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089f16`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180089d01`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180089d01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089f77`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180089f9c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180089f9c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180089ca1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180089ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089dfa`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18008a046`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18008a046`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180089ef1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180089ef1`

## string_xrefs

- `0x18008a0d1`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellItem::SetParentAndItem(
        CShellItem *this,
        const struct _ITEMIDLIST_ABSOLUTE *a2,
        struct IUnknown *a3,
        const ITEMIDLIST *a4)
{
  const ITEMIDLIST *v4; // rbp
  char *v7; // r14
  int v8; // ebx
  unsigned int v9; // r15d
  int v10; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // r13d
  int IDListFromObjectWorker; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int16 **v18; // r14
  unsigned __int16 *v19; // r14
  unsigned __int16 *v20; // rdx
  int v21; // r8d
  __int64 v22; // rcx
  __int64 v23; // rbp
  const struct _ITEMID_CHILD *v24; // rdx
  __int64 v25; // rcx
  ITEMIDLIST *v26; // rax
  LPITEMIDLIST v27; // rbx
  USHORT cb; // ax
  LPITEMIDLIST v29; // rcx
  const struct _ITEMIDLIST_ABSOLUTE *v31; // rdx
  unsigned int v32; // r8d
  __int64 v33; // rcx
  size_t v34; // rdi
  void *v35; // rbx
  size_t v36; // rbp
  int v37; // ecx
  int cchValue; // [rsp+20h] [rbp-2B8h]
  char *v39; // [rsp+30h] [rbp-2A8h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+58h] [rbp-280h] BYREF
  APTTYPE pAptType[4]; // [rsp+60h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = a4;
  v7 = (char *)this + 48;
  if ( this == (CShellItem *)32 )
    v7 = 0;
  v39 = v7;
  v8 = *((_DWORD *)v7 + 11);
  v9 = 2;
  if ( v8 != 2 )
  {
    v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    {
LABEL_5:
      if ( v10 != 1 )
        goto LABEL_16;
      goto LABEL_6;
    }
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v37 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v37;
    }
    else
    {
      v37 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    }
    if ( v37 != 1 )
      goto LABEL_16;
    if ( v8 == 1 )
    {
      if ( (unsigned int)IsAppCompatModeEnabled(16) )
      {
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
        goto LABEL_16;
      }
      v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_5;
    }
  }
LABEL_6:
  if ( *((_DWORD *)v7 + 10) != -3 )
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
      if ( CurrentThreadId != *((_DWORD *)v7 + 10) )
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
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v7) )
    ApartmentType = 0;
LABEL_18:
  if ( ApartmentType < 0 )
  {
    IDListFromObjectWorker = ApartmentType;
  }
  else
  {
    IDListFromObjectWorker = -2147024809;
    if ( (a2 || a3) && v4 )
    {
      v14 = *((_QWORD *)this + 17);
      *((_QWORD *)this + 17) = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v15 = *((_QWORD *)this + 18);
      *((_QWORD *)this + 18) = 0;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v16 = *((_QWORD *)this + 20);
      *((_QWORD *)this + 20) = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v17 = *((_QWORD *)this + 15);
      *((_QWORD *)this + 15) = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      CoTaskMemFree(*((LPVOID *)this + 13));
      v18 = (unsigned __int16 **)((char *)this + 128);
      CoTaskMemFree(*((LPVOID *)this + 16));
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 16) = 0;
      *((_QWORD *)this + 14) = 0;
      *((_QWORD *)this + 19) = 0;
      CoTaskMemFree(*((LPVOID *)this + 21));
      *((_QWORD *)this + 21) = 0;
      if ( a2 )
      {
        v31 = a2;
        v32 = 2;
        do
        {
          v33 = *(unsigned __int16 *)v31;
          if ( !(_WORD)v33 )
            break;
          v32 += v33;
          v31 = (const struct _ITEMIDLIST_ABSOLUTE *)((char *)v31 + v33);
        }
        while ( v31 );
        v34 = v32;
        v35 = CoTaskMemAlloc(v32);
        if ( v35 )
        {
          v36 = 0;
          *(_QWORD *)pAptQualifier = 0;
          if ( CoGetMalloc(1u, (LPMALLOC *)pAptQualifier) >= 0 )
          {
            v36 = (*(__int64 (__fastcall **)(_QWORD, void *))(**(_QWORD **)pAptQualifier + 48LL))(
                    *(_QWORD *)pAptQualifier,
                    v35);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          memset_0(v35, 0, v36);
          memcpy_0(v35, a2, v34);
          v4 = a4;
        }
        *v18 = (unsigned __int16 *)v35;
        IDListFromObjectWorker = 0;
        if ( !v35 )
          IDListFromObjectWorker = -2147024882;
      }
      else
      {
        *v18 = 0;
        IDListFromObjectWorker = -2147467262;
        if ( a3 )
        {
          IDListFromObjectWorker = _GetIDListFromObjectWorker(a3, (struct _ITEMIDLIST_ABSOLUTE **)this + 16);
          if ( IDListFromObjectWorker < 0 )
          {
            *(_QWORD *)pAptQualifier = 0;
            IDListFromObjectWorker = _GetItemFromObjectWorker(
                                       a3,
                                       &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
                                       (void **)pAptQualifier);
            if ( IDListFromObjectWorker >= 0 )
            {
              IDListFromObjectWorker = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pAptQualifier + 40LL))(
                                         *(_QWORD *)pAptQualifier,
                                         (char *)this + 128);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
            }
          }
        }
      }
      if ( IDListFromObjectWorker >= 0 )
      {
        v19 = *v18;
        if ( v19 )
        {
          v20 = v19;
          v21 = 2;
          do
          {
            v22 = *v20;
            if ( !(_WORD)v22 )
              break;
            v21 += v22;
            v20 = (unsigned __int16 *)((char *)v20 + v22);
          }
          while ( v20 );
          v23 = (unsigned int)(v21 - 2);
          v24 = (const struct _ITEMID_CHILD *)a4;
          do
          {
            v25 = *(unsigned __int16 *)v24;
            if ( !(_WORD)v25 )
              break;
            v9 += v25;
            v24 = (const struct _ITEMID_CHILD *)((char *)v24 + v25);
          }
          while ( v24 );
          v26 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc(v9 + (unsigned int)v23);
          v27 = v26;
          if ( v26 )
          {
            memset_0(v26, 0, v9 + (unsigned int)v23);
            memcpy_0(v27, v19, (unsigned int)v23);
            memcpy_0((char *)v27 + v23, a4, v9);
          }
        }
        else
        {
          v27 = ILClone(v4);
        }
        *((_QWORD *)this + 13) = v27;
        if ( v27 )
        {
          IDListFromObjectWorker = 0;
          cb = v27->mkid.cb;
          if ( v27->mkid.cb )
          {
            do
            {
              v29 = v27;
              v27 = (LPITEMIDLIST)((char *)v27 + cb);
              cb = v27->mkid.cb;
            }
            while ( v27->mkid.cb );
          }
          else
          {
            v29 = v27;
          }
          *((_QWORD *)this + 14) = v29;
          IUnknown_Set((IUnknown **)this + 18, a3);
          if ( *((_DWORD *)this + 44) )
            IUnknown_PrepareForCaching(*((struct IUnknown **)this + 18));
        }
        else
        {
          IDListFromObjectWorker = -2147024882;
        }
      }
      v7 = v39;
    }
  }
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  return (unsigned int)IDListFromObjectWorker;
}

```

## disassembly

```asm
0x180089c10  push    rbx
0x180089c12  push    rbp
0x180089c13  push    rsi
0x180089c14  push    rdi
0x180089c15  push    r12
0x180089c17  push    r13
0x180089c19  push    r14
0x180089c1b  push    r15
0x180089c1d  sub     rsp, 298h
0x180089c24  mov     rax, cs:__security_cookie
0x180089c2b  xor     rax, rsp
0x180089c2e  mov     [rsp+2D8h+var_58], rax
0x180089c36  mov     rbp, r9
0x180089c39  mov     [rsp+2D8h+Src], r9
0x180089c3e  mov     [rsp+2D8h+punk], r8
0x180089c43  mov     r12, rdx
0x180089c46  mov     rsi, rcx
0x180089c49  lea     rdx, [rcx-20h]
0x180089c4d  lea     r14, [rcx+30h]
0x180089c51  xor     edi, edi
0x180089c53  test    rdx, rdx
0x180089c56  cmovz   r14, rdi
0x180089c5a  mov     [rsp+2D8h+var_2A8], r14
0x180089c5f  mov     [rsp+2D8h+var_290], r14
0x180089c64  mov     ebx, [r14+2Ch]
0x180089c68  mov     r15d, 2
0x180089c6e  cmp     ebx, r15d
0x180089c71  jz      short loc_180089C86
0x180089c73  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180089c79  test    eax, eax
0x180089c7b  jz      loc_18008A009
0x180089c81  cmp     eax, 1
0x180089c84  jnz     short loc_180089CFE
0x180089c86  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x180089c8b  jz      short loc_180089CFE
0x180089c8d  mov     ebx, edi
0x180089c8f  mov     [rsp+2D8h+pAptType], edi
0x180089c93  mov     [rsp+2D8h+pAptQualifier], edi
0x180089c97  lea     rdx, [rsp+2D8h+pAptQualifier]; pAptQualifier
0x180089c9c  lea     rcx, [rsp+2D8h+pAptType]; pAptType
0x180089ca1  call    cs:__imp_CoGetApartmentType
0x180089ca8  nop     dword ptr [rax+rax+00h]
0x180089cad  mov     r13d, eax
0x180089cb0  test    eax, eax
0x180089cb2  js      short loc_180089CED
0x180089cb4  mov     edx, [rsp+2D8h+pAptType]
0x180089cb8  cmp     edx, 3
0x180089cbb  jnz     short loc_180089CCD
0x180089cbd  call    cs:__imp_GetCurrentThreadId
0x180089cc4  nop     dword ptr [rax+rax+00h]
0x180089cc9  mov     ebx, eax
0x180089ccb  jmp     short loc_180089CE3
0x180089ccd  test    edx, edx
0x180089ccf  jz      short loc_180089CBD
0x180089cd1  sub     edx, 1
0x180089cd4  jz      short loc_180089CE3
0x180089cd6  cmp     edx, 1
0x180089cd9  jz      loc_18008A0EF
0x180089cdf  test    eax, eax
0x180089ce1  js      short loc_180089CED
0x180089ce3  cmp     ebx, [r14+28h]
0x180089ce7  jnz     loc_18008A151
0x180089ced  mov     rcx, [rsp+2D8h]; this
0x180089cf5  test    r13d, r13d
0x180089cf8  js      loc_18008A0CE
0x180089cfe  mov     rcx, r14; lpCriticalSection
0x180089d01  call    cs:__imp_TryEnterCriticalSection
0x180089d08  nop     dword ptr [rax+rax+00h]
0x180089d0d  mov     r13d, 8001010Eh
0x180089d13  test    eax, eax
0x180089d15  cmovnz  r13d, edi
0x180089d19  mov     [rsp+2D8h+var_288], r13d
0x180089d1e  test    r13d, r13d
0x180089d21  js      loc_18008A178
0x180089d27  mov     edi, 80070057h
0x180089d2c  mov     rbx, [rsp+2D8h+punk]
0x180089d31  test    r12, r12
0x180089d34  jz      loc_180089F50
0x180089d3a  test    rbp, rbp
0x180089d3d  jz      loc_180089F0E
0x180089d43  mov     rcx, [rsi+88h]
0x180089d4a  xor     edi, edi
0x180089d4c  mov     [rsi+88h], rdi
0x180089d53  test    rcx, rcx
0x180089d56  jz      short loc_180089D64
0x180089d58  mov     rax, [rcx]
0x180089d5b  mov     rax, [rax+10h]
0x180089d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d64  mov     rcx, [rsi+90h]
0x180089d6b  mov     [rsi+90h], rdi
0x180089d72  test    rcx, rcx
0x180089d75  jz      short loc_180089D83
0x180089d77  mov     rax, [rcx]
0x180089d7a  mov     rax, [rax+10h]
0x180089d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d83  mov     rcx, [rsi+0A0h]
0x180089d8a  mov     [rsi+0A0h], rdi
0x180089d91  test    rcx, rcx
0x180089d94  jz      short loc_180089DA2
0x180089d96  mov     rax, [rcx]
0x180089d99  mov     rax, [rax+10h]
0x180089d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089da2  mov     rcx, [rsi+78h]
0x180089da6  mov     [rsi+78h], rdi
0x180089daa  test    rcx, rcx
0x180089dad  jz      short loc_180089DBB
0x180089daf  mov     rax, [rcx]
0x180089db2  mov     rax, [rax+10h]
0x180089db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089dbb  mov     rcx, [rsi+68h]; pv
0x180089dbf  call    cs:__imp_CoTaskMemFree
0x180089dc6  nop     dword ptr [rax+rax+00h]
0x180089dcb  lea     r14, [rsi+80h]
0x180089dd2  mov     rcx, [r14]; pv
0x180089dd5  call    cs:__imp_CoTaskMemFree
0x180089ddc  nop     dword ptr [rax+rax+00h]
0x180089de1  mov     [rsi+68h], rdi
0x180089de5  mov     [r14], rdi
0x180089de8  mov     [rsi+70h], rdi
0x180089dec  mov     [rsi+98h], rdi
0x180089df3  mov     rcx, [rsi+0A8h]; pv
0x180089dfa  call    cs:__imp_CoTaskMemFree
0x180089e01  nop     dword ptr [rax+rax+00h]
0x180089e06  mov     [rsi+0A8h], rdi
0x180089e0d  test    r12, r12
0x180089e10  jnz     loc_180089F5B
0x180089e16  mov     [r14], rdi
0x180089e19  mov     edi, 80004002h
0x180089e1e  test    rbx, rbx
0x180089e21  jnz     loc_18008A066
0x180089e27  test    edi, edi
0x180089e29  js      loc_180089F09
0x180089e2f  mov     r14, [r14]
0x180089e32  test    r14, r14
0x180089e35  jz      loc_18008A0F9
0x180089e3b  mov     rdx, r14
0x180089e3e  mov     r8d, r15d
0x180089e41  movzx   ecx, word ptr [rdx]
0x180089e44  test    cx, cx
0x180089e47  jz      short loc_180089E51
0x180089e49  add     r8d, ecx
0x180089e4c  add     rdx, rcx
0x180089e4f  jnz     short loc_180089E41
0x180089e51  lea     ebp, [r8-2]
0x180089e55  mov     r12, [rsp+2D8h+Src]
0x180089e5a  mov     rdx, r12
0x180089e5d  nop     dword ptr [rax]
0x180089e60  movzx   ecx, word ptr [rdx]
0x180089e63  test    cx, cx
0x180089e66  jz      short loc_180089E70
0x180089e68  add     r15d, ecx
0x180089e6b  add     rdx, rcx
0x180089e6e  jnz     short loc_180089E60
0x180089e70  lea     eax, [r15+rbp]
0x180089e74  mov     edi, eax
0x180089e76  mov     ecx, eax; cb
0x180089e78  call    WINRT_IMPL_CoTaskMemAlloc
0x180089e7d  mov     rbx, rax
0x180089e80  test    rax, rax
0x180089e83  jz      short loc_180089EAF
0x180089e85  mov     r8d, edi; Size
0x180089e88  xor     edx, edx; Val
0x180089e8a  mov     rcx, rax; void *
0x180089e8d  call    memset_0
0x180089e92  mov     r8d, ebp; Size
0x180089e95  mov     rdx, r14; Src
0x180089e98  mov     rcx, rbx; void *
0x180089e9b  call    memcpy_0
0x180089ea0  mov     r8d, r15d; Size
0x180089ea3  lea     rcx, [rbx+rbp]; void *
0x180089ea7  mov     rdx, r12; Src
0x180089eaa  call    memcpy_0
0x180089eaf  mov     [rsi+68h], rbx
0x180089eb3  test    rbx, rbx
0x180089eb6  jz      loc_180089F49
0x180089ebc  xor     edi, edi
0x180089ebe  movzx   eax, word ptr [rbx]
0x180089ec1  test    ax, ax
0x180089ec4  jz      loc_18008A0E7
0x180089eca  nop     word ptr [rax+rax+00h]
0x180089ed0  mov     rcx, rbx
0x180089ed3  movzx   eax, ax
0x180089ed6  add     rbx, rax
0x180089ed9  movzx   eax, word ptr [rbx]
0x180089edc  test    ax, ax
0x180089edf  jnz     short loc_180089ED0
0x180089ee1  mov     [rsi+70h], rcx
0x180089ee5  mov     rdx, [rsp+2D8h+punk]; punk
0x180089eea  lea     rcx, [rsi+90h]; ppunk
0x180089ef1  call    cs:__imp_IUnknown_Set
0x180089ef8  nop     dword ptr [rax+rax+00h]
0x180089efd  cmp     [rsi+0B0h], edi
0x180089f03  jnz     loc_18008A167
0x180089f09  mov     r14, [rsp+2D8h+var_2A8]
0x180089f0e  test    r13d, r13d
0x180089f11  js      short loc_180089F22
0x180089f13  mov     rcx, r14; lpCriticalSection
0x180089f16  call    cs:__imp_LeaveCriticalSection
0x180089f1d  nop     dword ptr [rax+rax+00h]
0x180089f22  mov     eax, edi
0x180089f24  mov     rcx, [rsp+2D8h+var_58]
0x180089f2c  xor     rcx, rsp; StackCookie
0x180089f2f  call    __security_check_cookie
0x180089f34  add     rsp, 298h
0x180089f3b  pop     r15
0x180089f3d  pop     r14
0x180089f3f  pop     r13
0x180089f41  pop     r12
0x180089f43  pop     rdi
0x180089f44  pop     rsi
0x180089f45  pop     rbp
0x180089f46  pop     rbx
0x180089f47  retn
0x180089f49  mov     edi, 8007000Eh
0x180089f4e  jmp     short loc_180089F09
0x180089f50  test    rbx, rbx
0x180089f53  jnz     loc_180089D3A
0x180089f59  jmp     short loc_180089F0E
0x180089f5b  mov     rdx, r12
0x180089f5e  mov     r8d, r15d
0x180089f61  movzx   ecx, word ptr [rdx]
0x180089f64  test    cx, cx
0x180089f67  jz      short loc_180089F71
0x180089f69  add     r8d, ecx
0x180089f6c  add     rdx, rcx
0x180089f6f  jnz     short loc_180089F61
0x180089f71  mov     edi, r8d
0x180089f74  mov     ecx, r8d; cb
0x180089f77  call    cs:__imp_CoTaskMemAlloc
0x180089f7e  nop     dword ptr [rax+rax+00h]
0x180089f83  mov     rbx, rax
0x180089f86  test    rax, rax
0x180089f89  jz      short loc_180089FF4
0x180089f8b  xor     ebp, ebp
0x180089f8d  mov     qword ptr [rsp+2D8h+pAptQualifier], rbp
0x180089f92  lea     rdx, [rsp+2D8h+pAptQualifier]; ppMalloc
0x180089f97  mov     ecx, 1; dwMemContext
0x180089f9c  call    cs:__imp_CoGetMalloc
0x180089fa3  nop     dword ptr [rax+rax+00h]
0x180089fa8  test    eax, eax
0x180089faa  js      short loc_180089FD4
0x180089fac  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x180089fb1  mov     rdx, [rcx]
0x180089fb4  mov     rax, [rdx+30h]
0x180089fb8  mov     rdx, rbx
0x180089fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fc0  mov     rbp, rax
0x180089fc3  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x180089fc8  mov     r9, [rcx]
0x180089fcb  mov     rax, [r9+10h]
0x180089fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fd4  mov     r8, rbp; Size
0x180089fd7  xor     edx, edx; Val
0x180089fd9  mov     rcx, rbx; void *
0x180089fdc  call    memset_0
0x180089fe1  mov     r8, rdi; Size
0x180089fe4  mov     rdx, r12; Src
0x180089fe7  mov     rcx, rbx; void *
0x180089fea  call    memcpy_0
0x180089fef  mov     rbp, [rsp+2D8h+Src]
0x180089ff4  mov     [r14], rbx
0x180089ff7  xor     edi, edi
0x180089ff9  test    rbx, rbx
0x180089ffc  mov     eax, 8007000Eh
0x18008a001  cmovz   edi, eax
0x18008a004  jmp     loc_180089E27
0x18008a009  mov     r8d, 104h; nSize
0x18008a00f  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x18008a014  xor     ecx, ecx; hModule
0x18008a016  call    cs:__imp_GetModuleFileNameW
0x18008a01d  nop     dword ptr [rax+rax+00h]
0x18008a022  test    eax, eax
0x18008a024  jnz     loc_18008A109
0x18008a02a  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18008a030  cmp     ecx, 1
0x18008a033  jnz     loc_180089CFE
0x18008a039  cmp     ebx, ecx
0x18008a03b  jnz     loc_180089C86
0x18008a041  mov     ecx, 10h
0x18008a046  call    cs:__imp_IsAppCompatModeEnabled
0x18008a04d  nop     dword ptr [rax+rax+00h]
0x18008a052  test    eax, eax
0x18008a054  jz      loc_18008A15C
0x18008a05a  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, r15d; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18008a061  jmp     loc_180089CFE
0x18008a066  mov     rdx, r14; struct _ITEMIDLIST_ABSOLUTE **
0x18008a069  mov     rcx, rbx; struct IUnknown *
0x18008a06c  call    ?_GetIDListFromObjectWorker@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObjectWorker(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x18008a071  mov     edi, eax
0x18008a073  test    eax, eax
0x18008a075  jns     loc_180089E27
0x18008a07b  mov     qword ptr [rsp+2D8h+pAptQualifier], 0
0x18008a084  lea     r8, [rsp+2D8h+pAptQualifier]; void **
0x18008a089  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5; struct _GUID *
0x18008a090  mov     rcx, rbx; struct IUnknown *
0x18008a093  call    ?_GetItemFromObjectWorker@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; _GetItemFromObjectWorker(IUnknown *,_GUID const &,void * *)
0x18008a098  mov     edi, eax
0x18008a09a  test    eax, eax
0x18008a09c  js      loc_180089E27
0x18008a0a2  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
  ... truncated ...
```
