# NRouter::TUserTokenTable::AddSession(ulong,void *,int,int *,int *,NCoreLibrary::TString *)

- ea: `0x14000fd70`
- end: `0x1400102ef`
- name: `?AddSession@TUserTokenTable@NRouter@@QEAAJKPEAXHPEAH1PEAVTString@NCoreLibrary@@@Z`
- size: `1407`
- prototype: `int(NRouter::TUserTokenTable *__hidden this, unsigned int, void *, int, int *, int *, struct NCoreLibrary::TString *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140015004`

## callees

- `0x140004e08`
- `0x14000a930`
- `0x14000b0d0`
- `0x14000fb58`
- `0x14000fd70`
- `0x140012654`
- `0x140015378`
- `0x140018994`
- `0x140018fdc`
- `0x14002cd10`
- `0x14002d0a0`
- `0x1400618f8`
- `0x14006aae0`
- `0x1400757e8`
- `0x140075d40`
- `0x140075ff4`
- `0x140076110`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400102bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400102bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fe30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fe30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fe3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fe3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010228`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001010c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001010c`

## string_xrefs

- `0x14001029e`: `NRouter::TUserTokenTable::AddSession`

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
  unsigned int UserSidStringFromToken; // eax
  int v20; // edx
  NRouter::TUserTokenTable *v21; // r15
  int v22; // eax
  _DWORD *v23; // rax
  NRouter::TUserTokenTable::TUserEntry *v24; // r8
  int v25; // eax
  DWORD LastError; // eax
  int v27; // edx
  HLOCAL v28; // rcx
  NRouter::TUserTokenTable::TUserEntry *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // edx
  int v34; // eax
  __int64 v35; // rcx
  NCoreLibrary::TLink *v36; // r8
  NCoreLibrary::TLink *v37; // r9
  NCoreLibrary::TLink *v38; // rcx
  struct NRouter::TUserTokenTable::TUserEntry *v39; // rcx
  int v42; // [rsp+20h] [rbp-E0h]
  NRouter::TUserTokenTable::TUserEntry *v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+30h] [rbp-D0h]
  NRouter::TUserTokenTable *v45; // [rsp+38h] [rbp-C8h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+44h] [rbp-BCh]
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  NRouter::TUserTokenTable::TUserEntry *v50; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v51; // [rsp+60h] [rbp-A0h] BYREF
  struct NRouter::TUserTokenTable::TUserEntry *v52; // [rsp+68h] [rbp-98h] BYREF
  NCoreLibrary::TString *v53; // [rsp+70h] [rbp-90h]
  unsigned __int16 v54[256]; // [rsp+80h] [rbp-80h] BYREF

  v7 = gpUserTokenTable;
  v8 = a3;
  v9 = 0;
  v10 = 0;
  LODWORD(hObject) = a4;
  v47 = a2;
  v51 = a3;
  v53 = a7;
  v45 = gpUserTokenTable;
  v50 = 0;
  v43 = 0;
  v52 = 0;
  LODWORD(hMem) = 0;
  v44 = 0;
  v42 = 0;
  v46 = 0;
  if ( a3 && a5 && a6 && a7 )
  {
    v11 = IsCurrentUserLocalAdmin(&v46);
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
  v15 = v45;
  if ( Token >= 0 )
  {
    if ( v45 == (NRouter::TUserTokenTable *)-56LL )
    {
      Token = -2147024809;
      goto LABEL_10;
    }
    if ( v45 != (NRouter::TUserTokenTable *)-64LL )
    {
      v17 = *((_QWORD *)v45 + 10);
      while ( (NRouter::TUserTokenTable *)v17 != (NRouter::TUserTokenTable *)((char *)v45 + 64)
           && v47 - *(_DWORD *)(v17 + 36) >= 0 )
      {
        if ( v47 == *(_DWORD *)(v17 + 36) )
        {
          Token = 0;
          if ( !(_DWORD)hObject )
          {
            v16 = 0;
            goto LABEL_78;
          }
          if ( v17 )
          {
            Token = NRouter::TUserTokenTable::TSessionEntry::ReleaseUserEntry(
                      (NRouter::TUserTokenTable::TSessionEntry *)v17,
                      &v52);
            (**v18)(v18, 1);
            if ( Token < 0 )
              goto LABEL_24;
          }
          break;
        }
        if ( v17 )
          v17 = *(_QWORD *)(v17 + 16);
      }
    }
    UserSidStringFromToken = SplGetUserSidStringFromToken(v8, v54, 512, &hMem);
    Token = NCoreLibrary::HResultFromWin32((NCoreLibrary *)UserSidStringFromToken, v20);
    if ( Token < 0 || (Token = NCoreLibrary::TString::Update(v53, v54), Token < 0) )
    {
LABEL_24:
      v21 = v45;
    }
    else
    {
      v21 = v45;
      Token = NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,unsigned short [256],NRouter::TUserTokenTable::TUserEntry>::Find(
                (char *)v45 + 8,
                v54,
                &v50);
    }
    if ( Token )
    {
      if ( Token == 1 )
      {
        v29 = (NRouter::TUserTokenTable::TUserEntry *)operator new(0x48u);
        if ( v29 )
        {
          v30 = NRouter::TUserTokenTable::TUserEntry::TUserEntry(v29, v54, v8, v46);
          v43 = (NRouter::TUserTokenTable::TUserEntry *)v30;
          v24 = (NRouter::TUserTokenTable::TUserEntry *)v30;
          if ( v30 )
          {
            v31 = *(_QWORD *)(v30 + 48);
            Token = 0;
            if ( !v31 )
              Token = -2147467259;
            v32 = 1;
            v42 = 1;
            if ( !v31 )
            {
              v43 = v24;
              goto LABEL_46;
            }
            v8 = 0;
            Token = NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,unsigned short [256],NRouter::TUserTokenTable::TUserEntry>::Insert(
                      (char *)v21 + 8,
                      v54,
                      v24);
            if ( Token < 0 )
            {
              v24 = v43;
              goto LABEL_45;
            }
            ++*((_DWORD *)v21 + 12);
            goto LABEL_28;
          }
        }
        else
        {
          v24 = 0;
          v43 = 0;
        }
        Token = -2147024882;
        v32 = 1;
        goto LABEL_46;
      }
    }
    else
    {
      v43 = v50;
      v22 = NRouter::TUserTokenTable::TUserEntry::SetToken(v50, &v51, v46);
      v8 = v51;
      Token = v22;
    }
    if ( Token < 0 )
    {
      v32 = 0;
      goto LABEL_76;
    }
LABEL_28:
    v23 = operator new(0x38u);
    v24 = v43;
    v9 = v23;
    if ( !v23 )
    {
      v9 = 0;
      Token = -2147024882;
      goto LABEL_45;
    }
    v23[2] = 1802398836;
    *((_QWORD *)v23 + 2) = v23;
    *((_QWORD *)v23 + 3) = v23;
    *(_QWORD *)v23 = &NRouter::TUserTokenTable::TSessionEntry::`vftable';
    v25 = v47;
    v9[8] = 1953391987;
    v9[9] = v25;
    *((_QWORD *)v9 + 5) = v43;
    *((_QWORD *)v9 + 6) = &NCoreLibrary::TString::gszNullState;
    if ( !v43 )
    {
      Token = -2147467259;
LABEL_45:
      v32 = v42;
LABEL_46:
      v33 = 0;
      v10 = v32;
      v15 = v45;
      v16 = 0;
      v42 = 0;
      goto LABEL_79;
    }
    hObject = 0;
    Token = NRouter::TUserTokenTable::TUserEntry::GetToken(v43, &hObject);
    if ( Token >= 0 )
    {
      hMem = 0;
      if ( (unsigned int)GetUniqueSessionKey(hObject, (LPWSTR *)&hMem)
        || (LastError = GetLastError(),
            Token = NCoreLibrary::HResultFromWin32((NCoreLibrary *)LastError, v27),
            Token >= 0) )
      {
        v28 = hMem;
        if ( hMem )
        {
          v34 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)(v9 + 12), (const unsigned __int16 *)hMem);
          v28 = hMem;
          Token = v34;
        }
        else
        {
          Token = -2147024809;
        }
        LocalFree(v28);
      }
    }
    if ( hObject )
      CloseHandle(hObject);
    if ( Token >= 0 )
    {
      if ( v21 != (NRouter::TUserTokenTable *)-64LL )
      {
        v35 = *((_QWORD *)v21 + 10);
        while ( (NRouter::TUserTokenTable *)v35 != (NRouter::TUserTokenTable *)((char *)v21 + 64)
             && v47 - *(_DWORD *)(v35 + 36) > 0 )
        {
          if ( v35 )
            v35 = *(_QWORD *)(v35 + 16);
        }
        v21 = v45;
      }
      Token = NCoreLibrary::TLink::IsValid((NCoreLibrary::TLink *)v9);
      if ( Token >= 0 )
      {
        if ( !v37 || (int)NCoreLibrary::TLink::IsValid(v37) < 0 )
          v38 = v36;
        Token = NCoreLibrary::TLink::Link(v38, (struct NCoreLibrary::TLink *)v9);
      }
      v24 = v43;
      if ( Token >= 0 )
      {
        ++*((_DWORD *)v43 + 9);
        v39 = v52;
        if ( v52 )
        {
          if ( !*((_DWORD *)v52 + 9) )
          {
            --*((_DWORD *)v21 + 12);
            if ( v39 )
            {
              (**(void (__fastcall ***)(struct NRouter::TUserTokenTable::TUserEntry *, __int64, NRouter::TUserTokenTable::TUserEntry *))v39)(
                v39,
                1,
                v43);
              v24 = v43;
            }
          }
        }
        v15 = v45;
        v10 = 0;
        v33 = v42;
        v16 = 1;
        v44 = 1;
        v9 = 0;
        goto LABEL_79;
      }
      goto LABEL_45;
    }
    v32 = v42;
LABEL_76:
    v24 = v43;
    goto LABEL_46;
  }
LABEL_10:
  v16 = 0;
LABEL_78:
  v33 = 0;
  v24 = 0;
LABEL_79:
  if ( v8 )
  {
    CloseHandle(v8);
    v15 = v45;
    v16 = v44;
    v33 = v42;
    v24 = v43;
  }
  if ( a5 )
    *a5 = v16;
  if ( a6 )
    *a6 = v33;
  if ( v10 )
  {
    --*((_DWORD *)v15 + 12);
    if ( v24 )
      (**(void (__fastcall ***)(NRouter::TUserTokenTable::TUserEntry *, __int64))v24)(v24, 1);
  }
  if ( v9 )
    (**(void (__fastcall ***)(_DWORD *, __int64, NRouter::TUserTokenTable::TUserEntry *))v9)(v9, 1, v24);
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
0x14000fd70  push    rbp
0x14000fd72  push    rbx
0x14000fd73  push    rsi
0x14000fd74  push    rdi
0x14000fd75  push    r12
0x14000fd77  push    r13
0x14000fd79  push    r14
0x14000fd7b  push    r15
0x14000fd7d  lea     rbp, [rsp-198h]
0x14000fd85  sub     rsp, 298h
0x14000fd8c  mov     rax, cs:__security_cookie
0x14000fd93  xor     rax, rsp
0x14000fd96  mov     [rbp+1D0h+var_50], rax
0x14000fd9d  mov     rax, [rbp+1D0h+arg_30]
0x14000fda4  xor     ecx, ecx
0x14000fda6  mov     rbx, cs:?gpUserTokenTable@@3PEAVTUserTokenTable@NRouter@@EA; NRouter::TUserTokenTable * gpUserTokenTable
0x14000fdad  mov     rsi, r8
0x14000fdb0  mov     r13, [rbp+1D0h+arg_20]
0x14000fdb7  mov     r14d, ecx
0x14000fdba  mov     r12, [rbp+1D0h+arg_28]
0x14000fdc1  mov     r15d, ecx
0x14000fdc4  mov     dword ptr [rsp+2D0h+hObject], r9d
0x14000fdc9  mov     [rsp+2D0h+var_28C], edx
0x14000fdcd  mov     [rsp+2D0h+var_270], r8
0x14000fdd2  mov     [rsp+2D0h+var_260], rax
0x14000fdd7  mov     [rsp+2D0h+var_298], rbx
0x14000fddc  mov     [rsp+2D0h+var_278], rcx
0x14000fde1  mov     [rsp+2D0h+var_2A8], rcx
0x14000fde6  mov     [rsp+2D0h+var_268], rcx
0x14000fdeb  mov     dword ptr [rsp+2D0h+hMem], ecx
0x14000fdef  mov     [rsp+2D0h+var_2A0], ecx
0x14000fdf3  mov     [rsp+2D0h+var_2B0], ecx
0x14000fdf7  mov     [rsp+2D0h+var_290], ecx
0x14000fdfb  test    r8, r8
0x14000fdfe  jz      short loc_14000FE24
0x14000fe00  test    r13, r13
0x14000fe03  jz      short loc_14000FE24
0x14000fe05  test    r12, r12
0x14000fe08  jz      short loc_14000FE24
0x14000fe0a  test    rax, rax
0x14000fe0d  jz      short loc_14000FE24
0x14000fe0f  lea     rcx, [rsp+2D0h+var_290]; int *
0x14000fe14  call    ?IsCurrentUserLocalAdmin@@YAKPEAH@Z; IsCurrentUserLocalAdmin(int *)
0x14000fe19  mov     ecx, eax; this
0x14000fe1b  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14000fe20  mov     edi, eax
0x14000fe22  jmp     short loc_14000FE29
0x14000fe24  mov     edi, 80070057h
0x14000fe29  mov     rbx, [rbx+60h]
0x14000fe2d  mov     rcx, rbx; lpCriticalSection
0x14000fe30  call    cs:__imp_EnterCriticalSection
0x14000fe37  nop     dword ptr [rax+rax+00h]
0x14000fe3c  inc     dword ptr [rbx+2Ch]
0x14000fe3f  call    cs:__imp_GetCurrentThreadId
0x14000fe46  nop     dword ptr [rax+rax+00h]
0x14000fe4b  mov     [rbx+28h], eax
0x14000fe4e  mov     rax, [rsp+2D0h+var_298]
0x14000fe53  test    edi, edi
0x14000fe55  js      short loc_14000FE65
0x14000fe57  lea     rdx, [rax+38h]
0x14000fe5b  test    rdx, rdx
0x14000fe5e  jnz     short loc_14000FE6D
0x14000fe60  mov     edi, 80070057h
0x14000fe65  mov     ecx, r14d
0x14000fe68  jmp     loc_14001021B
0x14000fe6d  xor     r9d, r9d
0x14000fe70  add     rdx, 8
0x14000fe74  jz      short loc_14000FE7A
0x14000fe76  mov     r9, [rdx+10h]
0x14000fe7a  test    rdx, rdx
0x14000fe7d  jz      short loc_14000FED8
0x14000fe7f  mov     ecx, [rsp+2D0h+var_28C]
0x14000fe83  cmp     r9, rdx
0x14000fe86  jz      short loc_14000FED8
0x14000fe88  mov     r8d, ecx
0x14000fe8b  sub     r8d, [r9+24h]
0x14000fe8f  js      short loc_14000FED8
0x14000fe91  test    r8d, r8d
0x14000fe94  jz      short loc_14000FEA1
0x14000fe96  test    r9, r9
0x14000fe99  jz      short loc_14000FE83
0x14000fe9b  mov     r9, [r9+10h]
0x14000fe9f  jmp     short loc_14000FE83
0x14000fea1  xor     edi, edi
0x14000fea3  cmp     dword ptr [rsp+2D0h+hObject], edi
0x14000fea7  jz      loc_140010219
0x14000fead  test    r9, r9
0x14000feb0  jz      short loc_14000FED8
0x14000feb2  lea     rdx, [rsp+2D0h+var_268]; struct NRouter::TUserTokenTable::TUserEntry **
0x14000feb7  mov     rcx, r9; this
0x14000feba  call    ?ReleaseUserEntry@TSessionEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAVTUserEntry@23@@Z; NRouter::TUserTokenTable::TSessionEntry::ReleaseUserEntry(NRouter::TUserTokenTable::TUserEntry * *)
0x14000febf  mov     edi, eax
0x14000fec1  mov     edx, 1
0x14000fec6  mov     rax, [r9]
0x14000fec9  mov     rcx, r9
0x14000fecc  mov     rax, [rax]
0x14000fecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fed4  test    edi, edi
0x14000fed6  js      short loc_14000FF2B
0x14000fed8  lea     r9, [rsp+2D0h+hMem]
0x14000fedd  mov     r8d, 200h
0x14000fee3  lea     rdx, [rbp+1D0h+var_250]
0x14000fee7  mov     rcx, rsi
0x14000feea  call    SplGetUserSidStringFromToken
0x14000feef  mov     ecx, eax; this
0x14000fef1  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14000fef6  mov     edi, eax
0x14000fef8  test    eax, eax
0x14000fefa  js      short loc_14000FF2B
0x14000fefc  mov     rcx, [rsp+2D0h+var_260]; this
0x14000ff01  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x14000ff05  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x14000ff0a  mov     edi, eax
0x14000ff0c  test    eax, eax
0x14000ff0e  js      short loc_14000FF2B
0x14000ff10  mov     r15, [rsp+2D0h+var_298]
0x14000ff15  lea     r8, [rsp+2D0h+var_278]
0x14000ff1a  lea     rdx, [rbp+1D0h+var_250]
0x14000ff1e  lea     rcx, [r15+8]
0x14000ff22  call    ?Find@?$TOrderListImp@VTUserEntry@TUserTokenTable@NRouter@@V?$TList@VTUserEntry@TUserTokenTable@NRouter@@@NCoreLibrary@@V123@$$BY0BAA@GV123@@NCoreLibrary@@SAJPEAV?$TList@VTUserEntry@TUserTokenTable@NRouter@@@2@AEAY0BAA@$$CBGPEAPEAVTUserEntry@TUserTokenTable@NRouter@@@Z; NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,ushort [256],NRouter::TUserTokenTable::TUserEntry>::Find(NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry> *,ushort const (&)[256],NRouter::TUserTokenTable::TUserEntry * *)
0x14000ff27  mov     edi, eax
0x14000ff29  jmp     short loc_14000FF30
0x14000ff2b  mov     r15, [rsp+2D0h+var_298]
0x14000ff30  test    edi, edi
0x14000ff32  jnz     loc_14001003A
0x14000ff38  mov     rax, [rsp+2D0h+var_278]
0x14000ff3d  lea     rdx, [rsp+2D0h+var_270]; void **
0x14000ff42  mov     r8d, [rsp+2D0h+var_290]; int
0x14000ff47  mov     rcx, rax; this
0x14000ff4a  mov     [rsp+2D0h+var_2A8], rax
0x14000ff4f  call    ?SetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAXH@Z; NRouter::TUserTokenTable::TUserEntry::SetToken(void * *,int)
0x14000ff54  mov     rsi, [rsp+2D0h+var_270]
0x14000ff59  mov     edi, eax
0x14000ff5b  test    edi, edi
0x14000ff5d  js      loc_140010206
0x14000ff63  mov     ecx, 38h ; '8'; Size
0x14000ff68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ff6d  mov     r8, [rsp+2D0h+var_2A8]
0x14000ff72  mov     r14, rax
0x14000ff75  test    rax, rax
0x14000ff78  jz      loc_1400101F9
0x14000ff7e  mov     dword ptr [rax+8], 6B6E6C74h
0x14000ff85  xor     edi, edi
0x14000ff87  mov     [rax+10h], rax
0x14000ff8b  test    r8, r8
0x14000ff8e  mov     [rax+18h], rax
0x14000ff92  lea     rax, ??_7TSessionEntry@TUserTokenTable@NRouter@@6B@; const NRouter::TUserTokenTable::TSessionEntry::`vftable'
0x14000ff99  mov     [r14], rax
0x14000ff9c  mov     eax, [rsp+2D0h+var_28C]
0x14000ffa0  mov     dword ptr [r14+20h], 746E6573h
0x14000ffa8  mov     [r14+24h], eax
0x14000ffac  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14000ffb3  mov     [r14+28h], r8
0x14000ffb7  mov     [r14+30h], rax
0x14000ffbb  mov     eax, 80004005h
0x14000ffc0  cmovz   edi, eax
0x14000ffc3  jz      loc_1400100C5
0x14000ffc9  lea     rdx, [rsp+2D0h+hObject]; void **
0x14000ffce  mov     [rsp+2D0h+hObject], 0
0x14000ffd7  mov     rcx, r8; this
0x14000ffda  call    ?GetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAX@Z; NRouter::TUserTokenTable::TUserEntry::GetToken(void * *)
0x14000ffdf  mov     edi, eax
0x14000ffe1  test    eax, eax
0x14000ffe3  js      loc_140010118
0x14000ffe9  mov     rcx, [rsp+2D0h+hObject]
0x14000ffee  lea     rdx, [rsp+2D0h+hMem]
0x14000fff3  mov     [rsp+2D0h+hMem], 0
0x14000fffc  call    GetUniqueSessionKey
0x140010001  test    eax, eax
0x140010003  jnz     short loc_140010022
0x140010005  call    cs:__imp_GetLastError
0x14001000c  nop     dword ptr [rax+rax+00h]
0x140010011  mov     ecx, eax; this
0x140010013  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x140010018  mov     edi, eax
0x14001001a  test    eax, eax
0x14001001c  js      loc_140010118
0x140010022  mov     rcx, [rsp+2D0h+hMem]
0x140010027  test    rcx, rcx
0x14001002a  jnz     loc_1400100F9
0x140010030  mov     edi, 80070057h
0x140010035  jmp     loc_14001010C
0x14001003a  cmp     edi, 1
0x14001003d  jnz     loc_14000FF5B
0x140010043  mov     ecx, 48h ; 'H'; Size
0x140010048  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001004d  test    rax, rax
0x140010050  jz      loc_1400100E5
0x140010056  mov     r9d, [rsp+2D0h+var_290]; int
0x14001005b  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x14001005f  mov     r8, rsi; void *
0x140010062  mov     rcx, rax; this
0x140010065  call    ??0TUserEntry@TUserTokenTable@NRouter@@QEAA@PEBGPEAXH@Z; NRouter::TUserTokenTable::TUserEntry::TUserEntry(ushort const *,void *,int)
0x14001006a  mov     [rsp+2D0h+var_2A8], rax
0x14001006f  mov     r8, rax
0x140010072  test    rax, rax
0x140010075  jz      short loc_1400100ED
0x140010077  mov     rcx, [rax+30h]
0x14001007b  xor     edi, edi
0x14001007d  mov     eax, 80004005h
0x140010082  test    rcx, rcx
0x140010085  cmovz   edi, eax
0x140010088  mov     eax, 1
0x14001008d  mov     [rsp+2D0h+var_2B0], eax
0x140010091  jz      short loc_1400100DE
0x140010093  lea     rcx, [r15+8]
0x140010097  xor     esi, esi
0x140010099  lea     rdx, [rbp+1D0h+var_250]
0x14001009d  call    ?Insert@?$TOrderListImp@VTUserEntry@TUserTokenTable@NRouter@@V?$TList@VTUserEntry@TUserTokenTable@NRouter@@@NCoreLibrary@@V123@$$BY0BAA@GV123@@NCoreLibrary@@SAJPEAV?$TList@VTUserEntry@TUserTokenTable@NRouter@@@2@AEAY0BAA@$$CBGPEAVTUserEntry@TUserTokenTable@NRouter@@@Z; NCoreLibrary::TOrderListImp<NRouter::TUserTokenTable::TUserEntry,NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry>,NRouter::TUserTokenTable::TUserEntry,ushort [256],NRouter::TUserTokenTable::TUserEntry>::Insert(NCoreLibrary::TList<NRouter::TUserTokenTable::TUserEntry> *,ushort const (&)[256],NRouter::TUserTokenTable::TUserEntry *)
0x1400100a2  mov     edi, eax
0x1400100a4  test    eax, eax
0x1400100a6  js      short loc_1400100BB
0x1400100a8  mov     rax, [rsp+2D0h+var_2A8]
0x1400100ad  inc     dword ptr [r15+30h]
0x1400100b1  mov     [rsp+2D0h+var_2A8], rax
0x1400100b6  jmp     loc_14000FF63
0x1400100bb  mov     r8, [rsp+2D0h+var_2A8]
0x1400100c0  mov     [rsp+2D0h+var_2A8], r8
0x1400100c5  mov     eax, [rsp+2D0h+var_2B0]
0x1400100c9  xor     edx, edx
0x1400100cb  mov     r15d, eax
0x1400100ce  mov     rax, [rsp+2D0h+var_298]
0x1400100d3  mov     ecx, edx
0x1400100d5  mov     [rsp+2D0h+var_2B0], edx
0x1400100d9  jmp     loc_140010220
0x1400100de  mov     [rsp+2D0h+var_2A8], r8
0x1400100e3  jmp     short loc_1400100C9
0x1400100e5  xor     r8d, r8d
0x1400100e8  mov     [rsp+2D0h+var_2A8], r8
0x1400100ed  mov     edi, 8007000Eh
0x1400100f2  mov     eax, 1
0x1400100f7  jmp     short loc_1400100C9
0x1400100f9  mov     rdx, rcx; unsigned __int16 *
0x1400100fc  lea     rcx, [r14+30h]; this
0x140010100  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x140010105  mov     rcx, [rsp+2D0h+hMem]; hMem
0x14001010a  mov     edi, eax
0x14001010c  call    cs:__imp_LocalFree
0x140010113  nop     dword ptr [rax+rax+00h]
0x140010118  mov     rcx, [rsp+2D0h+hObject]; hObject
0x14001011d  test    rcx, rcx
0x140010120  jz      short loc_14001012E
0x140010122  call    cs:__imp_CloseHandle
0x140010129  nop     dword ptr [rax+rax+00h]
0x14001012e  test    edi, edi
0x140010130  js      loc_14001020B
0x140010136  lea     r8, [r15+40h]
0x14001013a  xor     ecx, ecx
0x14001013c  test    r8, r8
0x14001013f  jz      short loc_140010145
0x140010141  mov     rcx, [r8+10h]
0x140010145  xor     r9d, r9d
0x140010148  test    r8, r8
0x14001014b  jz      short loc_140010174
0x14001014d  mov     r15d, [rsp+2D0h+var_28C]
0x140010152  cmp     rcx, r8
0x140010155  jz      short loc_14001016F
0x140010157  mov     eax, r15d
0x14001015a  sub     eax, [rcx+24h]
0x14001015d  test    eax, eax
0x14001015f  jle     short loc_14001016F
0x140010161  mov     r9, rcx
0x140010164  test    rcx, rcx
0x140010167  jz      short loc_140010152
0x140010169  mov     rcx, [rcx+10h]
0x14001016d  jmp     short loc_140010152
0x14001016f  mov     r15, [rsp+2D0h+var_298]
0x140010174  mov     rcx, r14; this
0x140010177  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x14001017c  mov     edi, eax
0x14001017e  test    eax, eax
0x140010180  js      short loc_1400101A0
0x140010182  test    r9, r9
0x140010185  jz      short loc_140010193
0x140010187  mov     rcx, r9; this
0x14001018a  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x14001018f  test    eax, eax
0x140010191  jns     short loc_140010196
0x140010193  mov     rcx, r8; this
0x140010196  mov     rdx, r14; struct NCoreLibrary::TLink *
0x140010199  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x14001019e  mov     edi, eax
0x1400101a0  mov     r8, [rsp+2D0h+var_2A8]
0x1400101a5  test    edi, edi
0x1400101a7  js      loc_1400100C5
0x1400101ad  inc     dword ptr [r8+24h]
0x1400101b1  mov     rcx, [rsp+2D0h+var_268]
0x1400101b6  test    rcx, rcx
0x1400101b9  jz      short loc_1400101DF
0x1400101bb  cmp     dword ptr [rcx+24h], 0
0x1400101bf  jnz     short loc_1400101DF
0x1400101c1  dec     dword ptr [r15+30h]
0x1400101c5  test    rcx, rcx
0x1400101c8  jz      short loc_1400101DF
0x1400101ca  mov     rax, [rcx]
0x1400101cd  mov     edx, 1
0x1400101d2  mov     rax, [rax]
0x1400101d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101da  mov     r8, [rsp+2D0h+var_2A8]
0x1400101df  mov     rax, [rsp+2D0h+var_298]
  ... truncated ...
```
