# CShellItem::SetParentAndItem(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_ITEMID_CHILD const *)

- ea: `0x1800dd3e0`
- end: `0x1800dd906`
- name: `?SetParentAndItem@CShellItem@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@@Z`
- size: `1318`
- prototype: `int(CShellItem *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct IShellFolder *, const struct _ITEMID_CHILD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180093c20`
- `0x1800cfc30`
- `0x1800dd190`
- `0x1800dd3e0`
- `0x1800dd910`
- `0x180170cf0`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dd7ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dd7ad`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dd8bb`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dd8bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dd6c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dd6c0`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dd4c5`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dd4c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dd487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dd487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dd71a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dd71a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dd739`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dd739`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dd471`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dd471`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd58d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd5ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd58d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd5ac`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dd7d7`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dd7d7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dd6a1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dd6a1`

## string_xrefs

- `0x1800dd85c`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

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
0x1800dd3e0  push    rbx
0x1800dd3e2  push    rbp
0x1800dd3e3  push    rsi
0x1800dd3e4  push    rdi
0x1800dd3e5  push    r12
0x1800dd3e7  push    r13
0x1800dd3e9  push    r14
0x1800dd3eb  push    r15
0x1800dd3ed  sub     rsp, 298h
0x1800dd3f4  mov     rax, cs:__security_cookie
0x1800dd3fb  xor     rax, rsp
0x1800dd3fe  mov     [rsp+2D8h+var_58], rax
0x1800dd406  mov     rbp, r9
0x1800dd409  mov     [rsp+2D8h+Src], r9
0x1800dd40e  mov     [rsp+2D8h+punk], r8
0x1800dd413  mov     r12, rdx
0x1800dd416  mov     rsi, rcx
0x1800dd419  lea     rdx, [rcx-20h]
0x1800dd41d  lea     r14, [rcx+30h]
0x1800dd421  xor     edi, edi
0x1800dd423  test    rdx, rdx
0x1800dd426  cmovz   r14, rdi
0x1800dd42a  mov     [rsp+2D8h+var_2A8], r14
0x1800dd42f  mov     [rsp+2D8h+var_290], r14
0x1800dd434  mov     ebx, [r14+2Ch]
0x1800dd438  mov     r15d, 2
0x1800dd43e  cmp     ebx, r15d
0x1800dd441  jz      short loc_1800DD456
0x1800dd443  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dd449  test    eax, eax
0x1800dd44b  jz      loc_1800DD7A0
0x1800dd451  cmp     eax, 1
0x1800dd454  jnz     short loc_1800DD4C2
0x1800dd456  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x1800dd45b  jz      short loc_1800DD4C2
0x1800dd45d  mov     ebx, edi
0x1800dd45f  mov     [rsp+2D8h+pAptType], edi
0x1800dd463  mov     [rsp+2D8h+pAptQualifier], edi
0x1800dd467  lea     rdx, [rsp+2D8h+pAptQualifier]; pAptQualifier
0x1800dd46c  lea     rcx, [rsp+2D8h+pAptType]; pAptType
0x1800dd471  call    cs:__imp_CoGetApartmentType
0x1800dd477  mov     r13d, eax
0x1800dd47a  test    eax, eax
0x1800dd47c  js      short loc_1800DD4B1
0x1800dd47e  mov     edx, [rsp+2D8h+pAptType]
0x1800dd482  cmp     edx, 3
0x1800dd485  jnz     short loc_1800DD491
0x1800dd487  call    cs:__imp_GetCurrentThreadId
0x1800dd48d  mov     ebx, eax
0x1800dd48f  jmp     short loc_1800DD4A7
0x1800dd491  test    edx, edx
0x1800dd493  jz      short loc_1800DD487
0x1800dd495  sub     edx, 1
0x1800dd498  jz      short loc_1800DD4A7
0x1800dd49a  cmp     edx, 1
0x1800dd49d  jz      loc_1800DD87A
0x1800dd4a3  test    eax, eax
0x1800dd4a5  js      short loc_1800DD4B1
0x1800dd4a7  cmp     ebx, [r14+28h]
0x1800dd4ab  jnz     loc_1800DD8D6
0x1800dd4b1  mov     rcx, [rsp+2D8h]; this
0x1800dd4b9  test    r13d, r13d
0x1800dd4bc  js      loc_1800DD859
0x1800dd4c2  mov     rcx, r14; lpCriticalSection
0x1800dd4c5  call    cs:__imp_TryEnterCriticalSection
0x1800dd4cb  mov     r13d, 8001010Eh
0x1800dd4d1  test    eax, eax
0x1800dd4d3  cmovnz  r13d, edi
0x1800dd4d7  mov     [rsp+2D8h+var_288], r13d
0x1800dd4dc  test    r13d, r13d
0x1800dd4df  js      loc_1800DD8FD
0x1800dd4e5  mov     edi, 80070057h
0x1800dd4ea  mov     rbx, [rsp+2D8h+punk]
0x1800dd4ef  test    r12, r12
0x1800dd4f2  jz      loc_1800DD6F3
0x1800dd4f8  test    rbp, rbp
0x1800dd4fb  jz      loc_1800DD6B8
0x1800dd501  mov     rcx, [rsi+88h]
0x1800dd508  xor     edi, edi
0x1800dd50a  mov     [rsi+88h], rdi
0x1800dd511  test    rcx, rcx
0x1800dd514  jz      short loc_1800DD522
0x1800dd516  mov     rax, [rcx]
0x1800dd519  mov     rax, [rax+10h]
0x1800dd51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd522  mov     rcx, [rsi+90h]
0x1800dd529  mov     [rsi+90h], rdi
0x1800dd530  test    rcx, rcx
0x1800dd533  jz      short loc_1800DD541
0x1800dd535  mov     rax, [rcx]
0x1800dd538  mov     rax, [rax+10h]
0x1800dd53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd541  mov     rcx, [rsi+0A0h]
0x1800dd548  mov     [rsi+0A0h], rdi
0x1800dd54f  test    rcx, rcx
0x1800dd552  jz      short loc_1800DD560
0x1800dd554  mov     rax, [rcx]
0x1800dd557  mov     rax, [rax+10h]
0x1800dd55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd560  mov     rcx, [rsi+78h]
0x1800dd564  mov     [rsi+78h], rdi
0x1800dd568  test    rcx, rcx
0x1800dd56b  jz      short loc_1800DD579
0x1800dd56d  mov     rax, [rcx]
0x1800dd570  mov     rax, [rax+10h]
0x1800dd574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd579  mov     rcx, [rsi+68h]; pv
0x1800dd57d  call    cs:__imp_CoTaskMemFree
0x1800dd583  lea     r14, [rsi+80h]
0x1800dd58a  mov     rcx, [r14]; pv
0x1800dd58d  call    cs:__imp_CoTaskMemFree
0x1800dd593  mov     [rsi+68h], rdi
0x1800dd597  mov     [r14], rdi
0x1800dd59a  mov     [rsi+70h], rdi
0x1800dd59e  mov     [rsi+98h], rdi
0x1800dd5a5  mov     rcx, [rsi+0A8h]; pv
0x1800dd5ac  call    cs:__imp_CoTaskMemFree
0x1800dd5b2  mov     [rsi+0A8h], rdi
0x1800dd5b9  test    r12, r12
0x1800dd5bc  jnz     loc_1800DD6FE
0x1800dd5c2  mov     [r14], rdi
0x1800dd5c5  mov     edi, 80004002h
0x1800dd5ca  test    rbx, rbx
0x1800dd5cd  jnz     loc_1800DD7F1
0x1800dd5d3  test    edi, edi
0x1800dd5d5  js      loc_1800DD6B3
0x1800dd5db  mov     r14, [r14]
0x1800dd5de  test    r14, r14
0x1800dd5e1  jz      loc_1800DD884
0x1800dd5e7  mov     rdx, r14
0x1800dd5ea  mov     r8d, r15d
0x1800dd5ed  nop     dword ptr [rax]
0x1800dd5f0  movzx   ecx, word ptr [rdx]
0x1800dd5f3  test    cx, cx
0x1800dd5f6  jz      short loc_1800DD600
0x1800dd5f8  add     r8d, ecx
0x1800dd5fb  add     rdx, rcx
0x1800dd5fe  jnz     short loc_1800DD5F0
0x1800dd600  lea     ebp, [r8-2]
0x1800dd604  mov     r12, [rsp+2D8h+Src]
0x1800dd609  mov     rdx, r12
0x1800dd60c  nop     dword ptr [rax+00h]
0x1800dd610  movzx   ecx, word ptr [rdx]
0x1800dd613  test    cx, cx
0x1800dd616  jz      short loc_1800DD620
0x1800dd618  add     r15d, ecx
0x1800dd61b  add     rdx, rcx
0x1800dd61e  jnz     short loc_1800DD610
0x1800dd620  lea     eax, [r15+rbp]
0x1800dd624  mov     edi, eax
0x1800dd626  mov     ecx, eax; cb
0x1800dd628  call    WINRT_IMPL_CoTaskMemAlloc
0x1800dd62d  mov     rbx, rax
0x1800dd630  test    rax, rax
0x1800dd633  jz      short loc_1800DD65F
0x1800dd635  mov     r8d, edi; Size
0x1800dd638  xor     edx, edx; Val
0x1800dd63a  mov     rcx, rax; void *
0x1800dd63d  call    memset_0
0x1800dd642  mov     r8d, ebp; Size
0x1800dd645  mov     rdx, r14; Src
0x1800dd648  mov     rcx, rbx; void *
0x1800dd64b  call    memcpy_0
0x1800dd650  mov     r8d, r15d; Size
0x1800dd653  lea     rcx, [rbx+rbp]; void *
0x1800dd657  mov     rdx, r12; Src
0x1800dd65a  call    memcpy_0
0x1800dd65f  mov     [rsi+68h], rbx
0x1800dd663  test    rbx, rbx
0x1800dd666  jz      loc_1800DD6EC
0x1800dd66c  xor     edi, edi
0x1800dd66e  movzx   eax, word ptr [rbx]
0x1800dd671  test    ax, ax
0x1800dd674  jz      loc_1800DD872
0x1800dd67a  nop     word ptr [rax+rax+00h]
0x1800dd680  mov     rcx, rbx
0x1800dd683  movzx   eax, ax
0x1800dd686  add     rbx, rax
0x1800dd689  movzx   eax, word ptr [rbx]
0x1800dd68c  test    ax, ax
0x1800dd68f  jnz     short loc_1800DD680
0x1800dd691  mov     [rsi+70h], rcx
0x1800dd695  mov     rdx, [rsp+2D8h+punk]; punk
0x1800dd69a  lea     rcx, [rsi+90h]; ppunk
0x1800dd6a1  call    cs:__imp_IUnknown_Set
0x1800dd6a7  cmp     [rsi+0B0h], edi
0x1800dd6ad  jnz     loc_1800DD8EC
0x1800dd6b3  mov     r14, [rsp+2D8h+var_2A8]
0x1800dd6b8  test    r13d, r13d
0x1800dd6bb  js      short loc_1800DD6C6
0x1800dd6bd  mov     rcx, r14; lpCriticalSection
0x1800dd6c0  call    cs:__imp_LeaveCriticalSection
0x1800dd6c6  mov     eax, edi
0x1800dd6c8  mov     rcx, [rsp+2D8h+var_58]
0x1800dd6d0  xor     rcx, rsp; StackCookie
0x1800dd6d3  call    __security_check_cookie
0x1800dd6d8  add     rsp, 298h
0x1800dd6df  pop     r15
0x1800dd6e1  pop     r14
0x1800dd6e3  pop     r13
0x1800dd6e5  pop     r12
0x1800dd6e7  pop     rdi
0x1800dd6e8  pop     rsi
0x1800dd6e9  pop     rbp
0x1800dd6ea  pop     rbx
0x1800dd6eb  retn
0x1800dd6ec  mov     edi, 8007000Eh
0x1800dd6f1  jmp     short loc_1800DD6B3
0x1800dd6f3  test    rbx, rbx
0x1800dd6f6  jnz     loc_1800DD4F8
0x1800dd6fc  jmp     short loc_1800DD6B8
0x1800dd6fe  mov     rdx, r12
0x1800dd701  mov     r8d, r15d
0x1800dd704  movzx   ecx, word ptr [rdx]
0x1800dd707  test    cx, cx
0x1800dd70a  jz      short loc_1800DD714
0x1800dd70c  add     r8d, ecx
0x1800dd70f  add     rdx, rcx
0x1800dd712  jnz     short loc_1800DD704
0x1800dd714  mov     edi, r8d
0x1800dd717  mov     ecx, r8d; cb
0x1800dd71a  call    cs:__imp_CoTaskMemAlloc
0x1800dd720  mov     rbx, rax
0x1800dd723  test    rax, rax
0x1800dd726  jz      short loc_1800DD78B
0x1800dd728  xor     ebp, ebp
0x1800dd72a  mov     qword ptr [rsp+2D8h+pAptQualifier], rbp
0x1800dd72f  lea     rdx, [rsp+2D8h+pAptQualifier]; ppMalloc
0x1800dd734  mov     ecx, 1; dwMemContext
0x1800dd739  call    cs:__imp_CoGetMalloc
0x1800dd73f  test    eax, eax
0x1800dd741  js      short loc_1800DD76B
0x1800dd743  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800dd748  mov     rdx, [rcx]
0x1800dd74b  mov     rax, [rdx+30h]
0x1800dd74f  mov     rdx, rbx
0x1800dd752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd757  mov     rbp, rax
0x1800dd75a  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800dd75f  mov     r9, [rcx]
0x1800dd762  mov     rax, [r9+10h]
0x1800dd766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd76b  mov     r8, rbp; Size
0x1800dd76e  xor     edx, edx; Val
0x1800dd770  mov     rcx, rbx; void *
0x1800dd773  call    memset_0
0x1800dd778  mov     r8, rdi; Size
0x1800dd77b  mov     rdx, r12; Src
0x1800dd77e  mov     rcx, rbx; void *
0x1800dd781  call    memcpy_0
0x1800dd786  mov     rbp, [rsp+2D8h+Src]
0x1800dd78b  mov     [r14], rbx
0x1800dd78e  xor     edi, edi
0x1800dd790  test    rbx, rbx
0x1800dd793  mov     eax, 8007000Eh
0x1800dd798  cmovz   edi, eax
0x1800dd79b  jmp     loc_1800DD5D3
0x1800dd7a0  mov     r8d, 104h; nSize
0x1800dd7a6  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x1800dd7ab  xor     ecx, ecx; hModule
0x1800dd7ad  call    cs:__imp_GetModuleFileNameW
0x1800dd7b3  test    eax, eax
0x1800dd7b5  jnz     loc_1800DD894
0x1800dd7bb  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dd7c1  cmp     ecx, 1
0x1800dd7c4  jnz     loc_1800DD4C2
0x1800dd7ca  cmp     ebx, ecx
0x1800dd7cc  jnz     loc_1800DD456
0x1800dd7d2  mov     ecx, 10h
0x1800dd7d7  call    cs:__imp_IsAppCompatModeEnabled
0x1800dd7dd  test    eax, eax
0x1800dd7df  jz      loc_1800DD8E1
0x1800dd7e5  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, r15d; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dd7ec  jmp     loc_1800DD4C2
0x1800dd7f1  mov     rdx, r14; struct _ITEMIDLIST_ABSOLUTE **
0x1800dd7f4  mov     rcx, rbx; struct IUnknown *
0x1800dd7f7  call    ?_GetIDListFromObjectWorker@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObjectWorker(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x1800dd7fc  mov     edi, eax
0x1800dd7fe  test    eax, eax
0x1800dd800  jns     loc_1800DD5D3
0x1800dd806  mov     qword ptr [rsp+2D8h+pAptQualifier], 0
0x1800dd80f  lea     r8, [rsp+2D8h+pAptQualifier]; void **
0x1800dd814  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5; struct _GUID *
0x1800dd81b  mov     rcx, rbx; struct IUnknown *
0x1800dd81e  call    ?_GetItemFromObjectWorker@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; _GetItemFromObjectWorker(IUnknown *,_GUID const &,void * *)
0x1800dd823  mov     edi, eax
0x1800dd825  test    eax, eax
0x1800dd827  js      loc_1800DD5D3
0x1800dd82d  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800dd832  mov     rax, [rcx]
0x1800dd835  mov     rdx, r14
0x1800dd838  mov     rax, [rax+28h]
0x1800dd83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd841  mov     edi, eax
0x1800dd843  mov     rcx, qword ptr [rsp+2D8h+pAptQualifier]
0x1800dd848  mov     rax, [rcx]
0x1800dd84b  mov     rax, [rax+10h]
0x1800dd84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd854  jmp     loc_1800DD5D3
0x1800dd859  mov     r9d, r13d; char *
  ... truncated ...
```
