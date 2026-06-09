# NRouter::TUserTokenTable::AddSession(ulong,void *,int,int *,int *,NCoreLibrary::TString *)

- ea: `0x14000eb40`
- end: `0x14000f119`
- name: `?AddSession@TUserTokenTable@NRouter@@QEAAJKPEAXHPEAH1PEAVTString@NCoreLibrary@@@Z`
- size: `1497`
- prototype: `int(NRouter::TUserTokenTable *__hidden this, unsigned int, void *, int, int *, int *, struct NCoreLibrary::TString *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140013d64`

## callees

- `0x140004708`
- `0x140009b50`
- `0x14000a260`
- `0x14000e904`
- `0x14000eb40`
- `0x14001128c`
- `0x140011ab8`
- `0x1400140cc`
- `0x140017558`
- `0x140017b28`
- `0x14002a830`
- `0x14002abc0`
- `0x14005be08`
- `0x140064810`
- `0x14006ea50`
- `0x14006f1b8`
- `0x14006f2b4`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000ed4e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000ed4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f0ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f0ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ebfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ebfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ec04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ec04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ef5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f05f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ef5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f05f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ef4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ef4f`

## string_xrefs

- `0x14000f0cf`: `NRouter::TUserTokenTable::AddSession`

## pseudocode

```c
__int64 __fastcall NRouter::TUserTokenTable::AddSession(
        NRouter::TUserTokenTable *this,
        int a2,
        void *a3,
        int a4,
        int *a5,
        int *a6,
        struct NCoreLibrary::TString *a7)
{
  NRouter::TUserTokenTable *v7; // rbx
  HANDLE v8; // rsi
  _DWORD *v9; // r14
  int v10; // r15d
  unsigned int v11; // eax
  int v12; // edx
  int Token; // edi
  __int64 v14; // rbx
  NRouter::TUserTokenTable *v15; // rax
  int v16; // ecx
  __int64 v17; // r9
  void (__fastcall ***v18)(_QWORD, __int64); // r9
  NRouter::TUserTokenTable::TUserEntry *v19; // r9
  unsigned int UserSidStringFromToken; // eax
  int v21; // edx
  __int64 v22; // rdx
  NRouter::TUserTokenTable *v23; // r15
  _QWORD *v24; // rax
  __int64 v25; // r8
  _QWORD *v26; // r8
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  _DWORD *v30; // rax
  NRouter::TUserTokenTable::TUserEntry *v31; // r8
  int v32; // eax
  DWORD LastError; // eax
  int v34; // edx
  HLOCAL v35; // rcx
  NRouter::TUserTokenTable::TUserEntry *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // edx
  int v41; // eax
  __int64 v42; // rcx
  NCoreLibrary::TLink *v43; // r8
  NCoreLibrary::TLink *v44; // r9
  NCoreLibrary::TLink *v45; // rcx
  struct NRouter::TUserTokenTable::TUserEntry *v46; // rcx
  int v49; // [rsp+20h] [rbp-E0h]
  NRouter::TUserTokenTable::TUserEntry *v50; // [rsp+28h] [rbp-D8h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  int v52; // [rsp+38h] [rbp-C8h]
  NRouter::TUserTokenTable *v53; // [rsp+40h] [rbp-C0h]
  int v54; // [rsp+48h] [rbp-B8h] BYREF
  int v55; // [rsp+4Ch] [rbp-B4h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  NCoreLibrary::TString *v57; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h]
  HANDLE v59; // [rsp+68h] [rbp-98h] BYREF
  struct NRouter::TUserTokenTable::TUserEntry *v60; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v61[256]; // [rsp+80h] [rbp-80h] BYREF

  v7 = gpUserTokenTable;
  v8 = a3;
  v9 = 0;
  v10 = 0;
  LODWORD(hObject) = a4;
  v55 = a2;
  v59 = a3;
  v57 = a7;
  v53 = gpUserTokenTable;
  v50 = 0;
  v60 = 0;
  LODWORD(hMem) = 0;
  v52 = 0;
  v49 = 0;
  v54 = 0;
  if ( a3 && a5 && a6 && a7 )
  {
    v11 = IsCurrentUserLocalAdmin(&v54);
    Token = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v11, v12);
  }
  else
  {
    Token = -2147024809;
  }
  v14 = *((_QWORD *)v7 + 12);
  EnterCriticalSection((LPCRITICAL_SECTION)v14);
  ++*(_DWORD *)(v14 + 44);
  *(_DWORD *)(v14 + 40) = GetCurrentThreadId();
  v15 = v53;
  if ( Token >= 0 )
  {
    if ( v53 == (NRouter::TUserTokenTable *)-56LL )
    {
      Token = -2147024809;
      goto LABEL_10;
    }
    if ( v53 != (NRouter::TUserTokenTable *)-64LL )
    {
      v17 = *((_QWORD *)v53 + 10);
      while ( (NRouter::TUserTokenTable *)v17 != (NRouter::TUserTokenTable *)((char *)v53 + 64) )
      {
        if ( v55 - *(_DWORD *)(v17 + 36) < 0 )
        {
          hObject = 0;
          goto LABEL_24;
        }
        if ( v55 == *(_DWORD *)(v17 + 36) )
        {
          Token = 0;
          if ( !(_DWORD)hObject )
          {
            v16 = 0;
            goto LABEL_92;
          }
          hObject = 0;
          if ( v17 )
          {
            Token = NRouter::TUserTokenTable::TSessionEntry::ReleaseUserEntry(
                      (NRouter::TUserTokenTable::TSessionEntry *)v17,
                      &v60);
            (**v18)(v18, 1);
            if ( Token < 0 )
            {
              v19 = 0;
              goto LABEL_38;
            }
          }
          goto LABEL_24;
        }
        if ( v17 )
          v17 = *(_QWORD *)(v17 + 16);
      }
    }
    hObject = 0;
LABEL_24:
    UserSidStringFromToken = SplGetUserSidStringFromToken(v8, v61, 512, &hMem);
    Token = NCoreLibrary::HResultFromWin32((NCoreLibrary *)UserSidStringFromToken, v21);
    if ( Token < 0 || (Token = NCoreLibrary::TString::Update(v57, v61), Token < 0) )
    {
      v19 = (NRouter::TUserTokenTable::TUserEntry *)hObject;
LABEL_38:
      v23 = v53;
    }
    else
    {
      v23 = v53;
      if ( v53 == (NRouter::TUserTokenTable *)-8LL )
      {
        Token = -2147024809;
LABEL_28:
        v19 = 0;
      }
      else
      {
        v24 = (_QWORD *)((char *)v53 + 16);
        v25 = 0;
        v57 = (NRouter::TUserTokenTable *)((char *)v53 + 16);
        Token = 1;
        v58 = 0;
        if ( v53 == (NRouter::TUserTokenTable *)-16LL )
          goto LABEL_31;
LABEL_30:
        v25 = v24[2];
        v58 = v25;
LABEL_31:
        while ( !(unsigned int)NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(&v57, v22, v25, 0) )
        {
          v27 = v26[5];
          hObject = v26;
          v28 = _o__wcsicmp(v61, v27);
          if ( v28 < 0 )
            goto LABEL_28;
          if ( !v28 )
          {
            v19 = (NRouter::TUserTokenTable::TUserEntry *)hObject;
            Token = 0;
            break;
          }
          v24 = hObject;
          v25 = v58;
          if ( hObject )
            goto LABEL_30;
        }
      }
    }
    if ( Token )
    {
      if ( Token == 1 )
      {
        v36 = (NRouter::TUserTokenTable::TUserEntry *)operator new(0x48u);
        if ( v36 )
        {
          v37 = NRouter::TUserTokenTable::TUserEntry::TUserEntry(v36, v61, v8, v54);
          v50 = (NRouter::TUserTokenTable::TUserEntry *)v37;
          v31 = (NRouter::TUserTokenTable::TUserEntry *)v37;
          if ( v37 )
          {
            v38 = *(_QWORD *)(v37 + 48);
            Token = 0;
            if ( !v38 )
              Token = -2147467259;
            v39 = 1;
            v49 = 1;
            if ( !v38 )
            {
              v50 = v31;
              goto LABEL_60;
            }
            v8 = 0;
            Token = NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,unsigned short [256],NRouter::TUserTokenTable::TUserEntry>::Insert(
                      (char *)v23 + 8,
                      v61,
                      v31);
            if ( Token < 0 )
            {
              v31 = v50;
              goto LABEL_59;
            }
            ++*((_DWORD *)v23 + 12);
            goto LABEL_42;
          }
        }
        else
        {
          v31 = 0;
          v50 = 0;
        }
        Token = -2147024882;
        v39 = 1;
        goto LABEL_60;
      }
    }
    else
    {
      v50 = v19;
      v29 = NRouter::TUserTokenTable::TUserEntry::SetToken(v19, &v59, v54);
      v8 = v59;
      Token = v29;
    }
    if ( Token < 0 )
    {
      v39 = 0;
      goto LABEL_90;
    }
LABEL_42:
    v30 = operator new(0x38u);
    v31 = v50;
    v9 = v30;
    if ( !v30 )
    {
      v9 = 0;
      Token = -2147024882;
      goto LABEL_59;
    }
    v30[2] = 1802398836;
    *((_QWORD *)v30 + 2) = v30;
    *((_QWORD *)v30 + 3) = v30;
    *(_QWORD *)v30 = &NRouter::TUserTokenTable::TSessionEntry::`vftable';
    v32 = v55;
    v9[8] = 1953391987;
    v9[9] = v32;
    *((_QWORD *)v9 + 5) = v50;
    *((_QWORD *)v9 + 6) = &NCoreLibrary::TString::gszNullState;
    if ( !v50 )
    {
      Token = -2147467259;
LABEL_59:
      v39 = v49;
LABEL_60:
      v40 = 0;
      v10 = v39;
      v15 = v53;
      v16 = 0;
      v49 = 0;
      goto LABEL_93;
    }
    hObject = 0;
    Token = NRouter::TUserTokenTable::TUserEntry::GetToken(v50, &hObject);
    if ( Token >= 0 )
    {
      hMem = 0;
      if ( (unsigned int)GetUniqueSessionKey(hObject, (LPWSTR *)&hMem)
        || (LastError = GetLastError(),
            Token = NCoreLibrary::HResultFromWin32((NCoreLibrary *)LastError, v34),
            Token >= 0) )
      {
        v35 = hMem;
        if ( hMem )
        {
          v41 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)(v9 + 12), (const unsigned __int16 *)hMem);
          v35 = hMem;
          Token = v41;
        }
        else
        {
          Token = -2147024809;
        }
        LocalFree(v35);
      }
    }
    if ( hObject )
      CloseHandle(hObject);
    if ( Token >= 0 )
    {
      if ( v23 != (NRouter::TUserTokenTable *)-64LL )
      {
        v42 = *((_QWORD *)v23 + 10);
        while ( (NRouter::TUserTokenTable *)v42 != (NRouter::TUserTokenTable *)((char *)v23 + 64)
             && v55 - *(_DWORD *)(v42 + 36) > 0 )
        {
          if ( v42 )
            v42 = *(_QWORD *)(v42 + 16);
        }
        v23 = v53;
      }
      Token = NCoreLibrary::TLink::IsValid((NCoreLibrary::TLink *)v9);
      if ( Token >= 0 )
      {
        if ( !v44 || (int)NCoreLibrary::TLink::IsValid(v44) < 0 )
          v45 = v43;
        Token = NCoreLibrary::TLink::Link(v45, (struct NCoreLibrary::TLink *)v9);
      }
      v31 = v50;
      if ( Token >= 0 )
      {
        ++*((_DWORD *)v50 + 9);
        v46 = v60;
        if ( v60 )
        {
          if ( !*((_DWORD *)v60 + 9) )
          {
            --*((_DWORD *)v23 + 12);
            if ( v46 )
            {
              (**(void (__fastcall ***)(struct NRouter::TUserTokenTable::TUserEntry *, __int64, NRouter::TUserTokenTable::TUserEntry *))v46)(
                v46,
                1,
                v50);
              v31 = v50;
            }
          }
        }
        v15 = v53;
        v10 = 0;
        v40 = v49;
        v16 = 1;
        v52 = 1;
        v9 = 0;
        goto LABEL_93;
      }
      goto LABEL_59;
    }
    v39 = v49;
LABEL_90:
    v31 = v50;
    goto LABEL_60;
  }
LABEL_10:
  v16 = 0;
LABEL_92:
  v40 = 0;
  v31 = 0;
LABEL_93:
  if ( v8 )
  {
    CloseHandle(v8);
    v15 = v53;
    v16 = v52;
    v40 = v49;
    v31 = v50;
  }
  if ( a5 )
    *a5 = v16;
  if ( a6 )
    *a6 = v40;
  if ( v10 )
  {
    --*((_DWORD *)v15 + 12);
    if ( v31 )
      (**(void (__fastcall ***)(NRouter::TUserTokenTable::TUserEntry *, __int64))v31)(v31, 1);
  }
  if ( v9 )
    (**(void (__fastcall ***)(_DWORD *, __int64, NRouter::TUserTokenTable::TUserEntry *))v9)(v9, 1, v31);
  if ( Token < 0 )
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "NRouter::TUserTokenTable::AddSession",
      L"Failed.  Error hr: 0x%x.",
      (unsigned int)Token);
  if ( (*(_DWORD *)(v14 + 44))-- == 1 )
    *(_DWORD *)(v14 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v14);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x14000eb40  push    rbp
0x14000eb42  push    rbx
0x14000eb43  push    rsi
0x14000eb44  push    rdi
0x14000eb45  push    r12
0x14000eb47  push    r13
0x14000eb49  push    r14
0x14000eb4b  push    r15
0x14000eb4d  lea     rbp, [rsp-198h]
0x14000eb55  sub     rsp, 298h
0x14000eb5c  mov     rax, cs:__security_cookie
0x14000eb63  xor     rax, rsp
0x14000eb66  mov     [rbp+1D0h+var_50], rax
0x14000eb6d  mov     rax, [rbp+1D0h+arg_30]
0x14000eb74  xor     ecx, ecx
0x14000eb76  mov     rbx, cs:?gpUserTokenTable@@3PEAVTUserTokenTable@NRouter@@EA; NRouter::TUserTokenTable * gpUserTokenTable
0x14000eb7d  mov     rsi, r8
0x14000eb80  mov     r13, [rbp+1D0h+arg_20]
0x14000eb87  mov     r14d, ecx
0x14000eb8a  mov     r12, [rbp+1D0h+arg_28]
0x14000eb91  mov     r15d, ecx
0x14000eb94  mov     dword ptr [rsp+2D0h+hObject], r9d
0x14000eb99  mov     [rsp+2D0h+var_284], edx
0x14000eb9d  mov     [rsp+2D0h+var_268], r8
0x14000eba2  mov     [rsp+2D0h+var_278], rax
0x14000eba7  mov     [rsp+2D0h+var_290], rbx
0x14000ebac  mov     [rsp+2D0h+var_2A8], rcx
0x14000ebb1  mov     [rsp+2D0h+var_260], rcx
0x14000ebb6  mov     dword ptr [rsp+2D0h+hMem], ecx
0x14000ebba  mov     [rsp+2D0h+var_298], ecx
0x14000ebbe  mov     [rsp+2D0h+var_2B0], ecx
0x14000ebc2  mov     [rsp+2D0h+var_288], ecx
0x14000ebc6  test    r8, r8
0x14000ebc9  jz      short loc_14000EBEF
0x14000ebcb  test    r13, r13
0x14000ebce  jz      short loc_14000EBEF
0x14000ebd0  test    r12, r12
0x14000ebd3  jz      short loc_14000EBEF
0x14000ebd5  test    rax, rax
0x14000ebd8  jz      short loc_14000EBEF
0x14000ebda  lea     rcx, [rsp+2D0h+var_288]; int *
0x14000ebdf  call    ?IsCurrentUserLocalAdmin@@YAKPEAH@Z; IsCurrentUserLocalAdmin(int *)
0x14000ebe4  mov     ecx, eax; this
0x14000ebe6  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14000ebeb  mov     edi, eax
0x14000ebed  jmp     short loc_14000EBF4
0x14000ebef  mov     edi, 80070057h
0x14000ebf4  mov     rbx, [rbx+60h]
0x14000ebf8  mov     rcx, rbx; lpCriticalSection
0x14000ebfb  call    cs:__imp_EnterCriticalSection
0x14000ec01  inc     dword ptr [rbx+2Ch]
0x14000ec04  call    cs:__imp_GetCurrentThreadId
0x14000ec0a  mov     [rbx+28h], eax
0x14000ec0d  mov     rax, [rsp+2D0h+var_290]
0x14000ec12  test    edi, edi
0x14000ec14  js      short loc_14000EC24
0x14000ec16  lea     rdx, [rax+38h]
0x14000ec1a  test    rdx, rdx
0x14000ec1d  jnz     short loc_14000EC2C
0x14000ec1f  mov     edi, 80070057h
0x14000ec24  mov     ecx, r14d
0x14000ec27  jmp     loc_14000F052
0x14000ec2c  xor     r9d, r9d
0x14000ec2f  add     rdx, 8
0x14000ec33  jz      short loc_14000EC39
0x14000ec35  mov     r9, [rdx+10h]
0x14000ec39  test    rdx, rdx
0x14000ec3c  jz      short loc_14000ECAD
0x14000ec3e  mov     ecx, [rsp+2D0h+var_284]
0x14000ec42  cmp     r9, rdx
0x14000ec45  jz      short loc_14000ECAD
0x14000ec47  mov     r8d, ecx
0x14000ec4a  sub     r8d, [r9+24h]
0x14000ec4e  js      short loc_14000ECA6
0x14000ec50  test    r8d, r8d
0x14000ec53  jz      short loc_14000EC60
0x14000ec55  test    r9, r9
0x14000ec58  jz      short loc_14000EC42
0x14000ec5a  mov     r9, [r9+10h]
0x14000ec5e  jmp     short loc_14000EC42
0x14000ec60  xor     edi, edi
0x14000ec62  cmp     dword ptr [rsp+2D0h+hObject], edi
0x14000ec66  jz      loc_14000F050
0x14000ec6c  xor     eax, eax
0x14000ec6e  mov     [rsp+2D0h+hObject], rax
0x14000ec73  test    r9, r9
0x14000ec76  jz      short loc_14000ECB4
0x14000ec78  lea     rdx, [rsp+2D0h+var_260]; struct NRouter::TUserTokenTable::TUserEntry **
0x14000ec7d  mov     rcx, r9; this
0x14000ec80  call    ?ReleaseUserEntry@TSessionEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAVTUserEntry@23@@Z; NRouter::TUserTokenTable::TSessionEntry::ReleaseUserEntry(NRouter::TUserTokenTable::TUserEntry * *)
0x14000ec85  mov     edi, eax
0x14000ec87  mov     edx, 1
0x14000ec8c  mov     rax, [r9]
0x14000ec8f  mov     rcx, r9
0x14000ec92  mov     rax, [rax]
0x14000ec95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec9a  test    edi, edi
0x14000ec9c  jns     short loc_14000ECB4
0x14000ec9e  mov     r9, r14
0x14000eca1  jmp     loc_14000ED79
0x14000eca6  mov     [rsp+2D0h+hObject], r14
0x14000ecab  jmp     short loc_14000ECB4
0x14000ecad  xor     eax, eax
0x14000ecaf  mov     [rsp+2D0h+hObject], rax
0x14000ecb4  lea     r9, [rsp+2D0h+hMem]
0x14000ecb9  mov     r8d, 200h
0x14000ecbf  lea     rdx, [rbp+1D0h+var_250]
0x14000ecc3  mov     rcx, rsi
0x14000ecc6  call    SplGetUserSidStringFromToken
0x14000eccb  mov     ecx, eax; this
0x14000eccd  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14000ecd2  mov     edi, eax
0x14000ecd4  test    eax, eax
0x14000ecd6  js      loc_14000ED74
0x14000ecdc  mov     rcx, [rsp+2D0h+var_278]; this
0x14000ece1  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x14000ece5  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x14000ecea  mov     edi, eax
0x14000ecec  test    eax, eax
0x14000ecee  js      loc_14000ED74
0x14000ecf4  mov     r15, [rsp+2D0h+var_290]
0x14000ecf9  lea     rax, [r15+8]
0x14000ecfd  test    rax, rax
0x14000ed00  jnz     short loc_14000ED0C
0x14000ed02  mov     edi, 80070057h
0x14000ed07  xor     r9d, r9d
0x14000ed0a  jmp     short loc_14000ED7E
0x14000ed0c  add     rax, 8
0x14000ed10  xor     r8d, r8d
0x14000ed13  mov     [rsp+2D0h+var_278], rax
0x14000ed18  mov     edi, 1
0x14000ed1d  mov     [rsp+2D0h+var_270], r8
0x14000ed22  test    rax, rax
0x14000ed25  jz      short loc_14000ED30
0x14000ed27  mov     r8, [rax+10h]
0x14000ed2b  mov     [rsp+2D0h+var_270], r8
0x14000ed30  lea     rcx, [rsp+2D0h+var_278]
0x14000ed35  xor     r9d, r9d
0x14000ed38  call    ?IsDone@TIterator@?$TList@VTResolutionCacheNode@@@NCoreLibrary@@QEBAHXZ; NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(void)
0x14000ed3d  test    eax, eax
0x14000ed3f  jnz     short loc_14000ED7E
0x14000ed41  mov     rdx, [r8+28h]
0x14000ed45  lea     rcx, [rbp+1D0h+var_250]
0x14000ed49  mov     [rsp+2D0h+hObject], r8
0x14000ed4e  call    cs:__imp__o__wcsicmp
0x14000ed54  test    eax, eax
0x14000ed56  js      short loc_14000ED07
0x14000ed58  jz      short loc_14000ED6B
0x14000ed5a  mov     rax, [rsp+2D0h+hObject]
0x14000ed5f  mov     r8, [rsp+2D0h+var_270]
0x14000ed64  test    rax, rax
0x14000ed67  jz      short loc_14000ED30
0x14000ed69  jmp     short loc_14000ED27
0x14000ed6b  mov     r9, [rsp+2D0h+hObject]
0x14000ed70  xor     edi, edi
0x14000ed72  jmp     short loc_14000ED7E
0x14000ed74  mov     r9, [rsp+2D0h+hObject]
0x14000ed79  mov     r15, [rsp+2D0h+var_290]
0x14000ed7e  test    edi, edi
0x14000ed80  jnz     loc_14000EE7D
0x14000ed86  mov     r8d, [rsp+2D0h+var_288]; int
0x14000ed8b  lea     rdx, [rsp+2D0h+var_268]; void **
0x14000ed90  mov     rcx, r9; this
0x14000ed93  mov     [rsp+2D0h+var_2A8], r9
0x14000ed98  call    ?SetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAXH@Z; NRouter::TUserTokenTable::TUserEntry::SetToken(void * *,int)
0x14000ed9d  mov     rsi, [rsp+2D0h+var_268]
0x14000eda2  mov     edi, eax
0x14000eda4  test    edi, edi
0x14000eda6  js      loc_14000F03D
0x14000edac  mov     ecx, 38h ; '8'; Size
0x14000edb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000edb6  mov     r8, [rsp+2D0h+var_2A8]
0x14000edbb  mov     r14, rax
0x14000edbe  test    rax, rax
0x14000edc1  jz      loc_14000F030
0x14000edc7  mov     dword ptr [rax+8], 6B6E6C74h
0x14000edce  xor     edi, edi
0x14000edd0  mov     [rax+10h], rax
0x14000edd4  test    r8, r8
0x14000edd7  mov     [rax+18h], rax
0x14000eddb  lea     rax, ??_7TSessionEntry@TUserTokenTable@NRouter@@6B@; const NRouter::TUserTokenTable::TSessionEntry::`vftable'
0x14000ede2  mov     [r14], rax
0x14000ede5  mov     eax, [rsp+2D0h+var_284]
0x14000ede9  mov     dword ptr [r14+20h], 746E6573h
0x14000edf1  mov     [r14+24h], eax
0x14000edf5  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14000edfc  mov     [r14+28h], r8
0x14000ee00  mov     [r14+30h], rax
0x14000ee04  mov     eax, 80004005h
0x14000ee09  cmovz   edi, eax
0x14000ee0c  jz      loc_14000EF08
0x14000ee12  lea     rdx, [rsp+2D0h+hObject]; void **
0x14000ee17  mov     [rsp+2D0h+hObject], 0
0x14000ee20  mov     rcx, r8; this
0x14000ee23  call    ?GetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAX@Z; NRouter::TUserTokenTable::TUserEntry::GetToken(void * *)
0x14000ee28  mov     edi, eax
0x14000ee2a  test    eax, eax
0x14000ee2c  js      loc_14000EF55
0x14000ee32  mov     rcx, [rsp+2D0h+hObject]
0x14000ee37  lea     rdx, [rsp+2D0h+hMem]
0x14000ee3c  mov     [rsp+2D0h+hMem], 0
0x14000ee45  call    GetUniqueSessionKey
0x14000ee4a  test    eax, eax
0x14000ee4c  jnz     short loc_14000EE65
0x14000ee4e  call    cs:__imp_GetLastError
0x14000ee54  mov     ecx, eax; this
0x14000ee56  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14000ee5b  mov     edi, eax
0x14000ee5d  test    eax, eax
0x14000ee5f  js      loc_14000EF55
0x14000ee65  mov     rcx, [rsp+2D0h+hMem]
0x14000ee6a  test    rcx, rcx
0x14000ee6d  jnz     loc_14000EF3C
0x14000ee73  mov     edi, 80070057h
0x14000ee78  jmp     loc_14000EF4F
0x14000ee7d  cmp     edi, 1
0x14000ee80  jnz     loc_14000EDA4
0x14000ee86  mov     ecx, 48h ; 'H'; Size
0x14000ee8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ee90  test    rax, rax
0x14000ee93  jz      loc_14000EF28
0x14000ee99  mov     r9d, [rsp+2D0h+var_288]; int
0x14000ee9e  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x14000eea2  mov     r8, rsi; void *
0x14000eea5  mov     rcx, rax; this
0x14000eea8  call    ??0TUserEntry@TUserTokenTable@NRouter@@QEAA@PEBGPEAXH@Z; NRouter::TUserTokenTable::TUserEntry::TUserEntry(ushort const *,void *,int)
0x14000eead  mov     [rsp+2D0h+var_2A8], rax
0x14000eeb2  mov     r8, rax
0x14000eeb5  test    rax, rax
0x14000eeb8  jz      short loc_14000EF30
0x14000eeba  mov     rcx, [rax+30h]
0x14000eebe  xor     edi, edi
0x14000eec0  mov     eax, 80004005h
0x14000eec5  test    rcx, rcx
0x14000eec8  cmovz   edi, eax
0x14000eecb  mov     eax, 1
0x14000eed0  mov     [rsp+2D0h+var_2B0], eax
0x14000eed4  jz      short loc_14000EF21
0x14000eed6  lea     rcx, [r15+8]
0x14000eeda  xor     esi, esi
0x14000eedc  lea     rdx, [rbp+1D0h+var_250]
0x14000eee0  call    ?Insert@?$TOrderListImp@VTUserEntry@TUserTokenTable@NRouter@@V?$TList@VTUserEntry@TUserTokenTable@NRouter@@@NCoreLibrary@@V123@$$BY0BAA@GV123@@NCoreLibrary@@SAJPEAV?$TList@VTUserEntry@TUserTokenTable@NRouter@@@2@AEAY0BAA@$$CBGPEAVTUserEntry@TUserTokenTable@NRouter@@@Z; NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,ushort [256],NRouter::TUserTokenTable::TUserEntry>::Insert(NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry> *,ushort const (&)[256],NRouter::TUserTokenTable::TUserEntry *)
0x14000eee5  mov     edi, eax
0x14000eee7  test    eax, eax
0x14000eee9  js      short loc_14000EEFE
0x14000eeeb  mov     rax, [rsp+2D0h+var_2A8]
0x14000eef0  inc     dword ptr [r15+30h]
0x14000eef4  mov     [rsp+2D0h+var_2A8], rax
0x14000eef9  jmp     loc_14000EDAC
0x14000eefe  mov     r8, [rsp+2D0h+var_2A8]
0x14000ef03  mov     [rsp+2D0h+var_2A8], r8
0x14000ef08  mov     eax, [rsp+2D0h+var_2B0]
0x14000ef0c  xor     edx, edx
0x14000ef0e  mov     r15d, eax
0x14000ef11  mov     rax, [rsp+2D0h+var_290]
0x14000ef16  mov     ecx, edx
0x14000ef18  mov     [rsp+2D0h+var_2B0], edx
0x14000ef1c  jmp     loc_14000F057
0x14000ef21  mov     [rsp+2D0h+var_2A8], r8
0x14000ef26  jmp     short loc_14000EF0C
0x14000ef28  xor     r8d, r8d
0x14000ef2b  mov     [rsp+2D0h+var_2A8], r8
0x14000ef30  mov     edi, 8007000Eh
0x14000ef35  mov     eax, 1
0x14000ef3a  jmp     short loc_14000EF0C
0x14000ef3c  mov     rdx, rcx; unsigned __int16 *
0x14000ef3f  lea     rcx, [r14+30h]; this
0x14000ef43  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x14000ef48  mov     rcx, [rsp+2D0h+hMem]; hMem
0x14000ef4d  mov     edi, eax
0x14000ef4f  call    cs:__imp_LocalFree
0x14000ef55  mov     rcx, [rsp+2D0h+hObject]; hObject
0x14000ef5a  test    rcx, rcx
0x14000ef5d  jz      short loc_14000EF65
0x14000ef5f  call    cs:__imp_CloseHandle
0x14000ef65  test    edi, edi
0x14000ef67  js      loc_14000F042
0x14000ef6d  lea     r8, [r15+40h]
0x14000ef71  xor     ecx, ecx
0x14000ef73  test    r8, r8
0x14000ef76  jz      short loc_14000EF7C
0x14000ef78  mov     rcx, [r8+10h]
0x14000ef7c  xor     r9d, r9d
0x14000ef7f  test    r8, r8
0x14000ef82  jz      short loc_14000EFAB
0x14000ef84  mov     r15d, [rsp+2D0h+var_284]
0x14000ef89  cmp     rcx, r8
0x14000ef8c  jz      short loc_14000EFA6
0x14000ef8e  mov     eax, r15d
0x14000ef91  sub     eax, [rcx+24h]
0x14000ef94  test    eax, eax
0x14000ef96  jle     short loc_14000EFA6
0x14000ef98  mov     r9, rcx
0x14000ef9b  test    rcx, rcx
0x14000ef9e  jz      short loc_14000EF89
0x14000efa0  mov     rcx, [rcx+10h]
0x14000efa4  jmp     short loc_14000EF89
0x14000efa6  mov     r15, [rsp+2D0h+var_290]
0x14000efab  mov     rcx, r14; this
0x14000efae  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
  ... truncated ...
```
