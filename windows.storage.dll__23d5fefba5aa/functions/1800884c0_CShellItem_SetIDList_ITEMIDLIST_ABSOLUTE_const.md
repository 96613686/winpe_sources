# CShellItem::SetIDList(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1800884c0`
- end: `0x1800889f0`
- name: `?SetIDList@CShellItem@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `1328`
- prototype: `int(CShellItem *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180038f50`
- `0x1800884c0`
- `0x1800899a4`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800888a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800888a8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180088958`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180088958`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008885d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800889cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008885d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800889cf`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800885a7`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800885a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800886c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008876b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800886c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008876b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800886f1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180088794`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800886f1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180088794`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180088546`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180088546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088692`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800888d4`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800888d4`

## string_xrefs

- `0x1800888f7`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellItem::SetIDList(CShellItem *this, const struct _ITEMIDLIST_ABSOLUTE *a2)
{
  char *v4; // r13
  size_t v5; // r14
  int v6; // edi
  unsigned int v7; // r15d
  int v8; // eax
  DWORD CurrentThreadId; // edi
  HRESULT ApartmentType; // r12d
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const struct _ITEMIDLIST_ABSOLUTE *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  size_t v18; // rsi
  _WORD *v19; // rdi
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  _WORD *v22; // r14
  size_t v23; // rbp
  unsigned __int16 v24; // ax
  _WORD *v25; // rcx
  _WORD *v26; // rdx
  unsigned int v27; // esi
  unsigned __int16 *v28; // rax
  unsigned __int16 v29; // cx
  unsigned __int16 *v30; // rdx
  int v32; // ecx
  int cchValue; // [rsp+20h] [rbp-288h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+40h] [rbp-268h] BYREF
  APTTYPE pAptType; // [rsp+48h] [rbp-260h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v4 = (char *)this + 56;
  v5 = 0;
  if ( this == (CShellItem *)24 )
    v4 = 0;
  v6 = *((_DWORD *)v4 + 11);
  v7 = 2;
  if ( v6 == 2 )
    goto LABEL_6;
  v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v32 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v32;
  }
  else
  {
    v32 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v32 != 1 )
    goto LABEL_17;
  if ( v6 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v8 != 1 )
      goto LABEL_17;
  }
LABEL_6:
  if ( *((_DWORD *)v4 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
  {
LABEL_13:
    if ( ApartmentType < 0 )
      goto LABEL_16;
    goto LABEL_14;
  }
  if ( pAptType == APTTYPE_MAINSTA || pAptType == APTTYPE_STA )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( pAptType != APTTYPE_MTA )
  {
    if ( pAptType != APTTYPE_NA )
      goto LABEL_13;
    CurrentThreadId = -1;
  }
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v4 + 10) )
    ApartmentType = -2147417842;
LABEL_16:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_19;
  }
LABEL_17:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v4) )
    ApartmentType = 0;
LABEL_19:
  if ( ApartmentType < 0 )
  {
    v27 = ApartmentType;
  }
  else
  {
    if ( !a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\item.cpp",
        (const char *)0x80070057LL,
        cchValue);
      LeaveCriticalSection((LPCRITICAL_SECTION)v4);
      return 2147942487LL;
    }
    v11 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v12 = *((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = *((_QWORD *)this + 16);
    *((_QWORD *)this + 16) = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    CoTaskMemFree(*((LPVOID *)this + 14));
    CoTaskMemFree(*((LPVOID *)this + 17));
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 20) = 0;
    CoTaskMemFree(*((LPVOID *)this + 22));
    *((_QWORD *)this + 22) = 0;
    v15 = a2;
    v16 = 2;
    do
    {
      v17 = *(unsigned __int16 *)v15;
      if ( !(_WORD)v17 )
        break;
      v16 += v17;
      v15 = (const struct _ITEMIDLIST_ABSOLUTE *)((char *)v15 + v17);
    }
    while ( v15 );
    v18 = v16;
    v19 = CoTaskMemAlloc(v16);
    if ( v19 )
    {
      *(_QWORD *)pAptQualifier = 0;
      if ( CoGetMalloc(1u, (LPMALLOC *)pAptQualifier) >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**(_QWORD **)pAptQualifier + 48LL))(
               *(_QWORD *)pAptQualifier,
               v19);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
      }
      memset_0(v19, 0, v5);
      memcpy_0(v19, a2, v18);
      *((_QWORD *)this + 14) = v19;
      if ( *v19 )
      {
        v20 = v19;
        do
        {
          v21 = *v20;
          if ( !(_WORD)v21 )
            break;
          v7 += v21;
          v20 = (unsigned __int16 *)((char *)v20 + v21);
        }
        while ( v20 );
        v22 = CoTaskMemAlloc(v7);
        if ( v22 )
        {
          v23 = 0;
          *(_QWORD *)pAptQualifier = 0;
          if ( CoGetMalloc(1u, (LPMALLOC *)pAptQualifier) >= 0 )
          {
            v23 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**(_QWORD **)pAptQualifier + 48LL))(
                    *(_QWORD *)pAptQualifier,
                    v22);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          memset_0(v22, 0, v23);
          memcpy_0(v22, v19, v7);
          v24 = *v22;
          if ( *v22 )
          {
            v25 = v22;
            do
            {
              v26 = v25;
              v25 = (_WORD *)((char *)v25 + v24);
              v24 = *v25;
            }
            while ( *v25 );
            *v26 = 0;
          }
          *((_QWORD *)this + 17) = v22;
          v27 = 0;
          v28 = (unsigned __int16 *)*((_QWORD *)this + 14);
          if ( v28 )
          {
            v29 = *v28;
            if ( *v28 )
            {
              do
              {
                v30 = v28;
                v28 = (unsigned __int16 *)((char *)v28 + v29);
                v29 = *v28;
              }
              while ( *v28 );
            }
            else
            {
              v30 = (unsigned __int16 *)*((_QWORD *)this + 14);
            }
          }
          else
          {
            v30 = 0;
          }
          *((_QWORD *)this + 15) = v30;
        }
        else
        {
          *((_QWORD *)this + 17) = 0;
          v27 = -2147024882;
        }
      }
      else
      {
        v27 = 0;
        *((_QWORD *)this + 17) = 0;
        *((_QWORD *)this + 15) = v19;
      }
    }
    else
    {
      *((_QWORD *)this + 14) = 0;
      v27 = -2147024882;
    }
  }
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  return v27;
}

```

## disassembly

```asm
0x1800884c0  mov     [rsp+arg_10], rbx
0x1800884c5  push    rbp
0x1800884c6  push    rsi
0x1800884c7  push    rdi
0x1800884c8  push    r12
0x1800884ca  push    r13
0x1800884cc  push    r14
0x1800884ce  push    r15
0x1800884d0  sub     rsp, 270h
0x1800884d7  mov     rax, cs:__security_cookie
0x1800884de  xor     rax, rsp
0x1800884e1  mov     [rsp+2A8h+var_48], rax
0x1800884e9  mov     rbp, rdx
0x1800884ec  mov     rbx, rcx
0x1800884ef  lea     rdx, [rcx-18h]
0x1800884f3  lea     r13, [rcx+38h]
0x1800884f7  xor     r14d, r14d
0x1800884fa  test    rdx, rdx
0x1800884fd  cmovz   r13, r14
0x180088501  mov     [rsp+2A8h+var_278], r13
0x180088506  mov     edi, [r13+2Ch]
0x18008850a  mov     r15d, 2
0x180088510  cmp     edi, r15d
0x180088513  jz      short loc_180088528
0x180088515  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18008851b  test    eax, eax
0x18008851d  jz      loc_18008889B
0x180088523  cmp     eax, 1
0x180088526  jnz     short loc_1800885A4
0x180088528  cmp     dword ptr [r13+28h], 0FFFFFFFDh
0x18008852d  jz      short loc_1800885A4
0x18008852f  mov     edi, r14d
0x180088532  mov     [rsp+2A8h+pAptType], r14d
0x180088537  mov     [rsp+2A8h+pAptQualifier], r14d
0x18008853c  lea     rdx, [rsp+2A8h+pAptQualifier]; pAptQualifier
0x180088541  lea     rcx, [rsp+2A8h+pAptType]; pAptType
0x180088546  call    cs:__imp_CoGetApartmentType
0x18008854d  nop     dword ptr [rax+rax+00h]
0x180088552  mov     r12d, eax
0x180088555  test    eax, eax
0x180088557  js      short loc_180088584
0x180088559  mov     eax, [rsp+2A8h+pAptType]
0x18008855d  cmp     eax, 3
0x180088560  jnz     short loc_180088572
0x180088562  call    cs:__imp_GetCurrentThreadId
0x180088569  nop     dword ptr [rax+rax+00h]
0x18008856e  mov     edi, eax
0x180088570  jmp     short loc_180088589
0x180088572  test    eax, eax
0x180088574  jz      short loc_180088562
0x180088576  sub     eax, 1
0x180088579  jz      short loc_180088589
0x18008857b  cmp     eax, 1
0x18008857e  jz      loc_180088927
0x180088584  test    r12d, r12d
0x180088587  js      short loc_180088593
0x180088589  cmp     edi, [r13+28h]
0x18008858d  jnz     loc_1800889A1
0x180088593  mov     rcx, [rsp+2A8h]; this
0x18008859b  test    r12d, r12d
0x18008859e  js      loc_1800888F4
0x1800885a4  mov     rcx, r13; lpCriticalSection
0x1800885a7  call    cs:__imp_TryEnterCriticalSection
0x1800885ae  nop     dword ptr [rax+rax+00h]
0x1800885b3  mov     r12d, 8001010Eh
0x1800885b9  test    eax, eax
0x1800885bb  cmovnz  r12d, r14d
0x1800885bf  mov     [rsp+2A8h+var_270], r12d
0x1800885c4  test    r12d, r12d
0x1800885c7  js      loc_18008897A
0x1800885cd  test    rbp, rbp
0x1800885d0  jz      loc_1800889AC
0x1800885d6  mov     rcx, [rbx+90h]
0x1800885dd  mov     [rbx+90h], r14
0x1800885e4  test    rcx, rcx
0x1800885e7  jz      short loc_1800885F5
0x1800885e9  mov     rax, [rcx]
0x1800885ec  mov     rax, [rax+10h]
0x1800885f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800885f5  mov     rcx, [rbx+98h]
0x1800885fc  mov     [rbx+98h], r14
0x180088603  test    rcx, rcx
0x180088606  jz      short loc_180088614
0x180088608  mov     rax, [rcx]
0x18008860b  mov     rax, [rax+10h]
0x18008860f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088614  mov     rcx, [rbx+0A8h]
0x18008861b  mov     [rbx+0A8h], r14
0x180088622  test    rcx, rcx
0x180088625  jz      short loc_180088633
0x180088627  mov     rax, [rcx]
0x18008862a  mov     rax, [rax+10h]
0x18008862e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088633  mov     rcx, [rbx+80h]
0x18008863a  mov     [rbx+80h], r14
0x180088641  test    rcx, rcx
0x180088644  jz      short loc_180088652
0x180088646  mov     rax, [rcx]
0x180088649  mov     rax, [rax+10h]
0x18008864d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088652  mov     rcx, [rbx+70h]; pv
0x180088656  call    cs:__imp_CoTaskMemFree
0x18008865d  nop     dword ptr [rax+rax+00h]
0x180088662  mov     rcx, [rbx+88h]; pv
0x180088669  call    cs:__imp_CoTaskMemFree
0x180088670  nop     dword ptr [rax+rax+00h]
0x180088675  mov     [rbx+70h], r14
0x180088679  mov     [rbx+88h], r14
0x180088680  mov     [rbx+78h], r14
0x180088684  mov     [rbx+0A0h], r14
0x18008868b  mov     rcx, [rbx+0B0h]; pv
0x180088692  call    cs:__imp_CoTaskMemFree
0x180088699  nop     dword ptr [rax+rax+00h]
0x18008869e  mov     [rbx+0B0h], r14
0x1800886a5  mov     rdx, rbp
0x1800886a8  mov     r8d, r15d
0x1800886ab  nop     dword ptr [rax+rax+00h]
0x1800886b0  movzx   ecx, word ptr [rdx]
0x1800886b3  test    cx, cx
0x1800886b6  jz      short loc_1800886C0
0x1800886b8  add     r8d, ecx
0x1800886bb  add     rdx, rcx
0x1800886be  jnz     short loc_1800886B0
0x1800886c0  mov     esi, r8d
0x1800886c3  mov     ecx, r8d; cb
0x1800886c6  call    cs:__imp_CoTaskMemAlloc
0x1800886cd  nop     dword ptr [rax+rax+00h]
0x1800886d2  mov     rdi, rax
0x1800886d5  test    rax, rax
0x1800886d8  jz      loc_180088982
0x1800886de  mov     qword ptr [rsp+2A8h+pAptQualifier], 0
0x1800886e7  lea     rdx, [rsp+2A8h+pAptQualifier]; ppMalloc
0x1800886ec  mov     ecx, 1; dwMemContext
0x1800886f1  call    cs:__imp_CoGetMalloc
0x1800886f8  nop     dword ptr [rax+rax+00h]
0x1800886fd  test    eax, eax
0x1800886ff  js      short loc_180088729
0x180088701  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x180088706  mov     rax, [rcx]
0x180088709  mov     rdx, rdi
0x18008870c  mov     rax, [rax+30h]
0x180088710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088715  mov     r14, rax
0x180088718  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x18008871d  mov     r9, [rcx]
0x180088720  mov     rax, [r9+10h]
0x180088724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088729  mov     r8, r14; Size
0x18008872c  xor     edx, edx; Val
0x18008872e  mov     rcx, rdi; void *
0x180088731  call    memset_0
0x180088736  mov     r8, rsi; Size
0x180088739  mov     rdx, rbp; Src
0x18008873c  mov     rcx, rdi; void *
0x18008873f  call    memcpy_0
0x180088744  mov     [rbx+70h], rdi
0x180088748  cmp     word ptr [rdi], 0
0x18008874c  jz      loc_18008890D
0x180088752  mov     rdx, rdi
0x180088755  movzx   ecx, word ptr [rdx]
0x180088758  test    cx, cx
0x18008875b  jz      short loc_180088765
0x18008875d  add     r15d, ecx
0x180088760  add     rdx, rcx
0x180088763  jnz     short loc_180088755
0x180088765  mov     esi, r15d
0x180088768  mov     ecx, r15d; cb
0x18008876b  call    cs:__imp_CoTaskMemAlloc
0x180088772  nop     dword ptr [rax+rax+00h]
0x180088777  mov     r14, rax
0x18008877a  test    rax, rax
0x18008877d  jz      loc_180088990
0x180088783  xor     ebp, ebp
0x180088785  mov     qword ptr [rsp+2A8h+pAptQualifier], rbp
0x18008878a  lea     rdx, [rsp+2A8h+pAptQualifier]; ppMalloc
0x18008878f  mov     ecx, 1; dwMemContext
0x180088794  call    cs:__imp_CoGetMalloc
0x18008879b  nop     dword ptr [rax+rax+00h]
0x1800887a0  test    eax, eax
0x1800887a2  js      short loc_1800887CC
0x1800887a4  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800887a9  mov     rax, [rcx]
0x1800887ac  mov     rdx, r14
0x1800887af  mov     rax, [rax+30h]
0x1800887b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887b8  mov     rbp, rax
0x1800887bb  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800887c0  mov     rdx, [rcx]
0x1800887c3  mov     rax, [rdx+10h]
0x1800887c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887cc  mov     r8, rbp; Size
0x1800887cf  xor     edx, edx; Val
0x1800887d1  mov     rcx, r14; void *
0x1800887d4  call    memset_0
0x1800887d9  mov     r8, rsi; Size
0x1800887dc  mov     rdx, rdi; Src
0x1800887df  mov     rcx, r14; void *
0x1800887e2  call    memcpy_0
0x1800887e7  movzx   eax, word ptr [r14]
0x1800887eb  test    ax, ax
0x1800887ee  jz      short loc_180088816
0x1800887f0  mov     rcx, r14
0x1800887f3  nop     dword ptr [rax+00h]
0x1800887f7  nop     word ptr [rax+rax+00000000h]
0x180088800  mov     rdx, rcx
0x180088803  movzx   eax, ax
0x180088806  add     rcx, rax
0x180088809  movzx   eax, word ptr [rcx]
0x18008880c  test    ax, ax
0x18008880f  jnz     short loc_180088800
0x180088811  xor     eax, eax
0x180088813  mov     [rdx], ax
0x180088816  lea     rax, [rbx+88h]
0x18008881d  mov     [rax], r14
0x180088820  xor     esi, esi
0x180088822  mov     rax, [rbx+70h]
0x180088826  test    rax, rax
0x180088829  jz      short loc_180088897
0x18008882b  movzx   ecx, word ptr [rax]
0x18008882e  test    cx, cx
0x180088831  jz      loc_18008891F
0x180088837  nop     word ptr [rax+rax+00000000h]
0x180088840  mov     rdx, rax
0x180088843  movzx   ecx, cx
0x180088846  add     rax, rcx
0x180088849  movzx   ecx, word ptr [rax]
0x18008884c  test    cx, cx
0x18008884f  jnz     short loc_180088840
0x180088851  mov     [rbx+78h], rdx
0x180088855  test    r12d, r12d
0x180088858  js      short loc_180088869
0x18008885a  mov     rcx, r13; lpCriticalSection
0x18008885d  call    cs:__imp_LeaveCriticalSection
0x180088864  nop     dword ptr [rax+rax+00h]
0x180088869  mov     eax, esi
0x18008886b  mov     rcx, [rsp+2A8h+var_48]
0x180088873  xor     rcx, rsp; StackCookie
0x180088876  call    __security_check_cookie
0x18008887b  mov     rbx, [rsp+2A8h+arg_10]
0x180088883  add     rsp, 270h
0x18008888a  pop     r15
0x18008888c  pop     r14
0x18008888e  pop     r13
0x180088890  pop     r12
0x180088892  pop     rdi
0x180088893  pop     rsi
0x180088894  pop     rbp
0x180088895  retn
0x180088897  xor     edx, edx
0x180088899  jmp     short loc_180088851
0x18008889b  mov     r8d, 104h; nSize
0x1800888a1  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x1800888a6  xor     ecx, ecx; hModule
0x1800888a8  call    cs:__imp_GetModuleFileNameW
0x1800888af  nop     dword ptr [rax+rax+00h]
0x1800888b4  test    eax, eax
0x1800888b6  jnz     short loc_180088931
0x1800888b8  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800888be  cmp     ecx, 1
0x1800888c1  jnz     loc_1800885A4
0x1800888c7  cmp     edi, ecx
0x1800888c9  jnz     loc_180088528
0x1800888cf  mov     ecx, 10h
0x1800888d4  call    cs:__imp_IsAppCompatModeEnabled
0x1800888db  nop     dword ptr [rax+rax+00h]
0x1800888e0  test    eax, eax
0x1800888e2  jz      loc_1800889E5
0x1800888e8  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, r15d; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800888ef  jmp     loc_1800885A4
0x1800888f4  mov     r9d, r12d; char *
0x1800888f7  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800888fe  mov     edx, 0C8h; void *
0x180088903  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180088908  jmp     loc_1800885BF
0x18008890d  xor     esi, esi
0x18008890f  mov     [rbx+88h], rsi
0x180088916  mov     [rbx+78h], rdi
0x18008891a  jmp     loc_180088855
0x18008891f  mov     rdx, rax
0x180088922  jmp     loc_180088851
0x180088927  mov     edi, 0FFFFFFFFh
0x18008892c  jmp     loc_180088589
0x180088931  mov     [rsp+2A8h+bIgnoreCase], 1; bIgnoreCase
0x180088939  mov     [rsp+2A8h+cchValue], 0FFFFFFFFh; cchValue
0x180088941  lea     r9, StringValue; "\\EXPLORER.EXE"
0x180088948  mov     r8d, 0FFFFFFFFh; cchSource
0x18008894e  lea     rdx, [rsp+2A8h+Filename]; lpStringSource
0x180088953  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180088958  call    cs:__imp_FindStringOrdinal
0x18008895f  nop     dword ptr [rax+rax+00h]
0x180088964  mov     ecx, r14d
0x180088967  cmp     eax, 0FFFFFFFFh
0x18008896a  setnz   cl
0x18008896d  inc     ecx
0x18008896f  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180088975  jmp     loc_1800888BE
0x18008897a  mov     esi, r12d
0x18008897d  jmp     loc_180088855
0x180088982  mov     [rbx+70h], rdi
0x180088986  mov     esi, 8007000Eh
  ... truncated ...
```
