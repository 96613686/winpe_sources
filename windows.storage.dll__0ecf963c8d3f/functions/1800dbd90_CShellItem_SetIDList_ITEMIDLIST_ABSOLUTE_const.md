# CShellItem::SetIDList(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1800dbd90`
- end: `0x1800dc261`
- name: `?SetIDList@CShellItem@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `1233`
- prototype: `int(CShellItem *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800432f0`
- `0x1800dbd90`
- `0x1800dd190`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dc131`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dc131`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dc1d5`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dc1d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc0ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc0ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc246`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dbe6b`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dbe6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dbe2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dbe2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dbf6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dbf6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc006`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dbf92`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dc029`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dbf92`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dc029`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dbe16`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dbe16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf44`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dc157`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dc157`

## string_xrefs

- `0x1800dc174`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

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
0x1800dbd90  mov     [rsp+arg_10], rbx
0x1800dbd95  push    rbp
0x1800dbd96  push    rsi
0x1800dbd97  push    rdi
0x1800dbd98  push    r12
0x1800dbd9a  push    r13
0x1800dbd9c  push    r14
0x1800dbd9e  push    r15
0x1800dbda0  sub     rsp, 270h
0x1800dbda7  mov     rax, cs:__security_cookie
0x1800dbdae  xor     rax, rsp
0x1800dbdb1  mov     [rsp+2A8h+var_48], rax
0x1800dbdb9  mov     rbp, rdx
0x1800dbdbc  mov     rbx, rcx
0x1800dbdbf  lea     rdx, [rcx-18h]
0x1800dbdc3  lea     r13, [rcx+38h]
0x1800dbdc7  xor     r14d, r14d
0x1800dbdca  test    rdx, rdx
0x1800dbdcd  cmovz   r13, r14
0x1800dbdd1  mov     [rsp+2A8h+var_278], r13
0x1800dbdd6  mov     edi, [r13+2Ch]
0x1800dbdda  mov     r15d, 2
0x1800dbde0  cmp     edi, r15d
0x1800dbde3  jz      short loc_1800DBDF8
0x1800dbde5  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dbdeb  test    eax, eax
0x1800dbded  jz      loc_1800DC124
0x1800dbdf3  cmp     eax, 1
0x1800dbdf6  jnz     short loc_1800DBE68
0x1800dbdf8  cmp     dword ptr [r13+28h], 0FFFFFFFDh
0x1800dbdfd  jz      short loc_1800DBE68
0x1800dbdff  mov     edi, r14d
0x1800dbe02  mov     [rsp+2A8h+pAptType], r14d
0x1800dbe07  mov     [rsp+2A8h+pAptQualifier], r14d
0x1800dbe0c  lea     rdx, [rsp+2A8h+pAptQualifier]; pAptQualifier
0x1800dbe11  lea     rcx, [rsp+2A8h+pAptType]; pAptType
0x1800dbe16  call    cs:__imp_CoGetApartmentType
0x1800dbe1c  mov     r12d, eax
0x1800dbe1f  test    eax, eax
0x1800dbe21  js      short loc_1800DBE48
0x1800dbe23  mov     eax, [rsp+2A8h+pAptType]
0x1800dbe27  cmp     eax, 3
0x1800dbe2a  jnz     short loc_1800DBE36
0x1800dbe2c  call    cs:__imp_GetCurrentThreadId
0x1800dbe32  mov     edi, eax
0x1800dbe34  jmp     short loc_1800DBE4D
0x1800dbe36  test    eax, eax
0x1800dbe38  jz      short loc_1800DBE2C
0x1800dbe3a  sub     eax, 1
0x1800dbe3d  jz      short loc_1800DBE4D
0x1800dbe3f  cmp     eax, 1
0x1800dbe42  jz      loc_1800DC1A4
0x1800dbe48  test    r12d, r12d
0x1800dbe4b  js      short loc_1800DBE57
0x1800dbe4d  cmp     edi, [r13+28h]
0x1800dbe51  jnz     loc_1800DC218
0x1800dbe57  mov     rcx, [rsp+2A8h]; this
0x1800dbe5f  test    r12d, r12d
0x1800dbe62  js      loc_1800DC171
0x1800dbe68  mov     rcx, r13; lpCriticalSection
0x1800dbe6b  call    cs:__imp_TryEnterCriticalSection
0x1800dbe71  mov     r12d, 8001010Eh
0x1800dbe77  test    eax, eax
0x1800dbe79  cmovnz  r12d, r14d
0x1800dbe7d  mov     [rsp+2A8h+var_270], r12d
0x1800dbe82  test    r12d, r12d
0x1800dbe85  js      loc_1800DC1F1
0x1800dbe8b  test    rbp, rbp
0x1800dbe8e  jz      loc_1800DC223
0x1800dbe94  mov     rcx, [rbx+90h]
0x1800dbe9b  mov     [rbx+90h], r14
0x1800dbea2  test    rcx, rcx
0x1800dbea5  jz      short loc_1800DBEB3
0x1800dbea7  mov     rax, [rcx]
0x1800dbeaa  mov     rax, [rax+10h]
0x1800dbeae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbeb3  mov     rcx, [rbx+98h]
0x1800dbeba  mov     [rbx+98h], r14
0x1800dbec1  test    rcx, rcx
0x1800dbec4  jz      short loc_1800DBED2
0x1800dbec6  mov     rax, [rcx]
0x1800dbec9  mov     rax, [rax+10h]
0x1800dbecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbed2  mov     rcx, [rbx+0A8h]
0x1800dbed9  mov     [rbx+0A8h], r14
0x1800dbee0  test    rcx, rcx
0x1800dbee3  jz      short loc_1800DBEF1
0x1800dbee5  mov     rax, [rcx]
0x1800dbee8  mov     rax, [rax+10h]
0x1800dbeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbef1  mov     rcx, [rbx+80h]
0x1800dbef8  mov     [rbx+80h], r14
0x1800dbeff  test    rcx, rcx
0x1800dbf02  jz      short loc_1800DBF10
0x1800dbf04  mov     rax, [rcx]
0x1800dbf07  mov     rax, [rax+10h]
0x1800dbf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf10  mov     rcx, [rbx+70h]; pv
0x1800dbf14  call    cs:__imp_CoTaskMemFree
0x1800dbf1a  mov     rcx, [rbx+88h]; pv
0x1800dbf21  call    cs:__imp_CoTaskMemFree
0x1800dbf27  mov     [rbx+70h], r14
0x1800dbf2b  mov     [rbx+88h], r14
0x1800dbf32  mov     [rbx+78h], r14
0x1800dbf36  mov     [rbx+0A0h], r14
0x1800dbf3d  mov     rcx, [rbx+0B0h]; pv
0x1800dbf44  call    cs:__imp_CoTaskMemFree
0x1800dbf4a  mov     [rbx+0B0h], r14
0x1800dbf51  mov     rdx, rbp
0x1800dbf54  mov     r8d, r15d
0x1800dbf57  movzx   ecx, word ptr [rdx]
0x1800dbf5a  test    cx, cx
0x1800dbf5d  jz      short loc_1800DBF67
0x1800dbf5f  add     r8d, ecx
0x1800dbf62  add     rdx, rcx
0x1800dbf65  jnz     short loc_1800DBF57
0x1800dbf67  mov     esi, r8d
0x1800dbf6a  mov     ecx, r8d; cb
0x1800dbf6d  call    cs:__imp_CoTaskMemAlloc
0x1800dbf73  mov     rdi, rax
0x1800dbf76  test    rax, rax
0x1800dbf79  jz      loc_1800DC1F9
0x1800dbf7f  mov     qword ptr [rsp+2A8h+pAptQualifier], 0
0x1800dbf88  lea     rdx, [rsp+2A8h+pAptQualifier]; ppMalloc
0x1800dbf8d  mov     ecx, 1; dwMemContext
0x1800dbf92  call    cs:__imp_CoGetMalloc
0x1800dbf98  test    eax, eax
0x1800dbf9a  js      short loc_1800DBFC4
0x1800dbf9c  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800dbfa1  mov     rax, [rcx]
0x1800dbfa4  mov     rdx, rdi
0x1800dbfa7  mov     rax, [rax+30h]
0x1800dbfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfb0  mov     r14, rax
0x1800dbfb3  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800dbfb8  mov     r9, [rcx]
0x1800dbfbb  mov     rax, [r9+10h]
0x1800dbfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfc4  mov     r8, r14; Size
0x1800dbfc7  xor     edx, edx; Val
0x1800dbfc9  mov     rcx, rdi; void *
0x1800dbfcc  call    memset_0
0x1800dbfd1  mov     r8, rsi; Size
0x1800dbfd4  mov     rdx, rbp; Src
0x1800dbfd7  mov     rcx, rdi; void *
0x1800dbfda  call    memcpy_0
0x1800dbfdf  mov     [rbx+70h], rdi
0x1800dbfe3  cmp     word ptr [rdi], 0
0x1800dbfe7  jz      loc_1800DC18A
0x1800dbfed  mov     rdx, rdi
0x1800dbff0  movzx   ecx, word ptr [rdx]
0x1800dbff3  test    cx, cx
0x1800dbff6  jz      short loc_1800DC000
0x1800dbff8  add     r15d, ecx
0x1800dbffb  add     rdx, rcx
0x1800dbffe  jnz     short loc_1800DBFF0
0x1800dc000  mov     esi, r15d
0x1800dc003  mov     ecx, r15d; cb
0x1800dc006  call    cs:__imp_CoTaskMemAlloc
0x1800dc00c  mov     r14, rax
0x1800dc00f  test    rax, rax
0x1800dc012  jz      loc_1800DC207
0x1800dc018  xor     ebp, ebp
0x1800dc01a  mov     qword ptr [rsp+2A8h+pAptQualifier], rbp
0x1800dc01f  lea     rdx, [rsp+2A8h+pAptQualifier]; ppMalloc
0x1800dc024  mov     ecx, 1; dwMemContext
0x1800dc029  call    cs:__imp_CoGetMalloc
0x1800dc02f  test    eax, eax
0x1800dc031  js      short loc_1800DC05B
0x1800dc033  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800dc038  mov     rax, [rcx]
0x1800dc03b  mov     rdx, r14
0x1800dc03e  mov     rax, [rax+30h]
0x1800dc042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc047  mov     rbp, rax
0x1800dc04a  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x1800dc04f  mov     rdx, [rcx]
0x1800dc052  mov     rax, [rdx+10h]
0x1800dc056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc05b  mov     r8, rbp; Size
0x1800dc05e  xor     edx, edx; Val
0x1800dc060  mov     rcx, r14; void *
0x1800dc063  call    memset_0
0x1800dc068  mov     r8, rsi; Size
0x1800dc06b  mov     rdx, rdi; Src
0x1800dc06e  mov     rcx, r14; void *
0x1800dc071  call    memcpy_0
0x1800dc076  movzx   eax, word ptr [r14]
0x1800dc07a  test    ax, ax
0x1800dc07d  jz      short loc_1800DC0A6
0x1800dc07f  mov     rcx, r14
0x1800dc082  nop     dword ptr [rax+00h]
0x1800dc086  nop     word ptr [rax+rax+00000000h]
0x1800dc090  mov     rdx, rcx
0x1800dc093  movzx   eax, ax
0x1800dc096  add     rcx, rax
0x1800dc099  movzx   eax, word ptr [rcx]
0x1800dc09c  test    ax, ax
0x1800dc09f  jnz     short loc_1800DC090
0x1800dc0a1  xor     eax, eax
0x1800dc0a3  mov     [rdx], ax
0x1800dc0a6  lea     rax, [rbx+88h]
0x1800dc0ad  mov     [rax], r14
0x1800dc0b0  xor     esi, esi
0x1800dc0b2  mov     rax, [rbx+70h]
0x1800dc0b6  test    rax, rax
0x1800dc0b9  jz      short loc_1800DC120
0x1800dc0bb  movzx   ecx, word ptr [rax]
0x1800dc0be  test    cx, cx
0x1800dc0c1  jz      loc_1800DC19C
0x1800dc0c7  nop     word ptr [rax+rax+00000000h]
0x1800dc0d0  mov     rdx, rax
0x1800dc0d3  movzx   ecx, cx
0x1800dc0d6  add     rax, rcx
0x1800dc0d9  movzx   ecx, word ptr [rax]
0x1800dc0dc  test    cx, cx
0x1800dc0df  jnz     short loc_1800DC0D0
0x1800dc0e1  mov     [rbx+78h], rdx
0x1800dc0e5  test    r12d, r12d
0x1800dc0e8  js      short loc_1800DC0F3
0x1800dc0ea  mov     rcx, r13; lpCriticalSection
0x1800dc0ed  call    cs:__imp_LeaveCriticalSection
0x1800dc0f3  mov     eax, esi
0x1800dc0f5  mov     rcx, [rsp+2A8h+var_48]
0x1800dc0fd  xor     rcx, rsp; StackCookie
0x1800dc100  call    __security_check_cookie
0x1800dc105  mov     rbx, [rsp+2A8h+arg_10]
0x1800dc10d  add     rsp, 270h
0x1800dc114  pop     r15
0x1800dc116  pop     r14
0x1800dc118  pop     r13
0x1800dc11a  pop     r12
0x1800dc11c  pop     rdi
0x1800dc11d  pop     rsi
0x1800dc11e  pop     rbp
0x1800dc11f  retn
0x1800dc120  xor     edx, edx
0x1800dc122  jmp     short loc_1800DC0E1
0x1800dc124  mov     r8d, 104h; nSize
0x1800dc12a  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x1800dc12f  xor     ecx, ecx; hModule
0x1800dc131  call    cs:__imp_GetModuleFileNameW
0x1800dc137  test    eax, eax
0x1800dc139  jnz     short loc_1800DC1AE
0x1800dc13b  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc141  cmp     ecx, 1
0x1800dc144  jnz     loc_1800DBE68
0x1800dc14a  cmp     edi, ecx
0x1800dc14c  jnz     loc_1800DBDF8
0x1800dc152  mov     ecx, 10h
0x1800dc157  call    cs:__imp_IsAppCompatModeEnabled
0x1800dc15d  test    eax, eax
0x1800dc15f  jz      loc_1800DC256
0x1800dc165  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, r15d; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc16c  jmp     loc_1800DBE68
0x1800dc171  mov     r9d, r12d; char *
0x1800dc174  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800dc17b  mov     edx, 0C8h; void *
0x1800dc180  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dc185  jmp     loc_1800DBE7D
0x1800dc18a  xor     esi, esi
0x1800dc18c  mov     [rbx+88h], rsi
0x1800dc193  mov     [rbx+78h], rdi
0x1800dc197  jmp     loc_1800DC0E5
0x1800dc19c  mov     rdx, rax
0x1800dc19f  jmp     loc_1800DC0E1
0x1800dc1a4  mov     edi, 0FFFFFFFFh
0x1800dc1a9  jmp     loc_1800DBE4D
0x1800dc1ae  mov     [rsp+2A8h+bIgnoreCase], 1; bIgnoreCase
0x1800dc1b6  mov     [rsp+2A8h+cchValue], 0FFFFFFFFh; cchValue
0x1800dc1be  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800dc1c5  mov     r8d, 0FFFFFFFFh; cchSource
0x1800dc1cb  lea     rdx, [rsp+2A8h+Filename]; lpStringSource
0x1800dc1d0  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800dc1d5  call    cs:__imp_FindStringOrdinal
0x1800dc1db  mov     ecx, r14d
0x1800dc1de  cmp     eax, 0FFFFFFFFh
0x1800dc1e1  setnz   cl
0x1800dc1e4  inc     ecx
0x1800dc1e6  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc1ec  jmp     loc_1800DC141
0x1800dc1f1  mov     esi, r12d
0x1800dc1f4  jmp     loc_1800DC0E5
0x1800dc1f9  mov     [rbx+70h], rdi
0x1800dc1fd  mov     esi, 8007000Eh
0x1800dc202  jmp     loc_1800DC0E5
0x1800dc207  mov     [rbx+88h], r14
0x1800dc20e  mov     esi, 8007000Eh
0x1800dc213  jmp     loc_1800DC0E5
0x1800dc218  mov     r12d, 8001010Eh
0x1800dc21e  jmp     loc_1800DBE57
0x1800dc223  mov     rcx, [rsp+2A8h]; this
0x1800dc22b  mov     r9d, 80070057h; char *
0x1800dc231  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.storage\\ite"...
0x1800dc238  mov     edx, 0BDh; void *
0x1800dc23d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc242  nop
0x1800dc243  mov     rcx, r13; lpCriticalSection
0x1800dc246  call    cs:__imp_LeaveCriticalSection
0x1800dc24c  mov     eax, 80070057h
  ... truncated ...
```
