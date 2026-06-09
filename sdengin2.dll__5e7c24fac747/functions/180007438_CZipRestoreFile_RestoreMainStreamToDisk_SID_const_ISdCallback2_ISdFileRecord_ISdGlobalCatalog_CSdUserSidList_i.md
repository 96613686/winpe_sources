# CZipRestoreFile::_RestoreMainStreamToDisk(_SID const *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,int,ISdReadObj *)

- ea: `0x180007438`
- end: `0x180007910`
- name: `?_RestoreMainStreamToDisk@CZipRestoreFile@@AEAAJPEBU_SID@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@HPEAUISdReadObj@@@Z`
- size: `1240`
- prototype: `__int64 __fastcall(CZipRestoreFile *this, struct _SID *, struct ISdCallback2 *, struct ISdFileRecord *, struct ISdGlobalCatalog *, struct CSdUserSidList *, int, struct ISdReadObj *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x180005330`
- `0x1800055f0`

## callees

- `0x18000640c`
- `0x180006e84`
- `0x180007438`
- `0x180025794`
- `0x180025bb0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180099764`
- `0x18009a08c`
- `0x18009a0bc`
- `0x18009a26c`
- `0x18009ae34`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180007620`
- `KERNEL32!CreateFileW` at `0x180007620`
- `KERNEL32!CloseHandle` at `0x18000765a`
- `KERNEL32!CloseHandle` at `0x1800078cc`
- `KERNEL32!CloseHandle` at `0x18000765a`
- `KERNEL32!CloseHandle` at `0x1800078cc`
- `ole32!CoTaskMemFree` at `0x1800078a3`
- `ole32!CoTaskMemFree` at `0x1800078b5`
- `ole32!CoTaskMemFree` at `0x1800078a3`
- `ole32!CoTaskMemFree` at `0x1800078b5`
- `ole32!CoCreateGuid` at `0x180007567`
- `ole32!CoCreateGuid` at `0x180007567`

## pseudocode

```c
__int64 __fastcall CZipRestoreFile::_RestoreMainStreamToDisk(
        CZipRestoreFile *this,
        struct _SID *a2,
        struct ISdCallback2 *a3,
        struct ISdFileRecord *a4,
        struct ISdGlobalCatalog *a5,
        struct CSdUserSidList *a6,
        int a7,
        struct ISdReadObj *a8)
{
  struct ISdGlobalCatalog *v11; // rdi
  __int64 FileW; // rbx
  __int16 v13; // ax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  CZipRestoreFile *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // r15d
  _WORD *v20; // rdi
  int v21; // eax
  bool v22; // sf
  _WORD *v23; // rax
  CZipRestoreFile *v24; // rcx
  unsigned int v25; // edi
  int v27; // [rsp+70h] [rbp-90h] BYREF
  HRESULT LastFailureAsHRESULT; // [rsp+78h] [rbp-88h] BYREF
  __int16 v29; // [rsp+7Ch] [rbp-84h]
  __int16 v30; // [rsp+7Eh] [rbp-82h]
  unsigned int v31; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v32; // [rsp+B4h] [rbp-4Ch] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v34; // [rsp+C0h] [rbp-40h] BYREF
  struct ISdGlobalCatalog *v35; // [rsp+C8h] [rbp-38h]
  struct CSdUserSidList *v36; // [rsp+D0h] [rbp-30h]
  PSID pSid; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpFileName[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v39[2]; // [rsp+F0h] [rbp-10h] BYREF
  GUID pguid; // [rsp+100h] [rbp+0h] BYREF
  _WORD v41[16]; // [rsp+110h] [rbp+10h] BYREF

  pSid = a2;
  v11 = a5;
  v35 = a5;
  v36 = a6;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CZipRestoreFile::_RestoreMainStreamToDisk",
    0x219u,
    1u);
  pv = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  v27 = 0;
  pguid = GUID_NULL;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  v39[0] = (unsigned __int16 *)qword_1800E8530;
  v39[1] = 0;
  FileW = -1;
  v13 = 552;
  if ( !pSid )
    goto LABEL_2;
  v29 = 552;
  v13 = 553;
  if ( !a3 )
    goto LABEL_2;
  v29 = 553;
  v13 = 554;
  if ( !a4 || (v29 = 554, v13 = 555, !a5) || (v29 = 555, v13 = 556, !v36) || (v29 = 556, v13 = 557, !a8) )
  {
LABEL_2:
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v30 = v13;
    goto LABEL_41;
  }
  LastFailureAsHRESULT = 0;
  v29 = 557;
  if ( a7 )
  {
    LastFailureAsHRESULT = CoCreateGuid(&pguid);
    v13 = 564;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 564;
    LastFailureAsHRESULT = CBsString::Set((CBsString *)v39, &pguid);
    v13 = 565;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 565;
    v14 = CBsString::ReverseFind((CZipRestoreFile *)((char *)this + 64), 0x5Cu);
    LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, *((const unsigned __int16 **)this + 8), v14 + 1);
    v13 = 568;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 568;
    LastFailureAsHRESULT = CBsString::Append((CBsString *)lpFileName, v39[0]);
    v13 = 570;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 570;
    FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 0x4000000u, 0);
    if ( FileW == -1 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15);
      v13 = 573;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v29 = 573;
    if ( FileW )
    {
      CloseHandle((HANDLE)FileW);
      FileW = -1;
    }
    v11 = v35;
  }
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, int *))(*(_QWORD *)a4 + 128LL))(a4, &v27);
  v13 = 577;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v29 = 577;
  v16 = v27 | 0x8000000;
  v27 |= 0x8000000u;
  if ( *((_DWORD *)this + 26) == 11 )
  {
    LastFailureAsHRESULT = GetRelativeSDFromFileRecordForUserModeRestore(
                             pSid,
                             a4,
                             1,
                             (unsigned __int8 **)&pv,
                             &v31,
                             &v34,
                             &v32);
    v18 = 0;
    v13 = 598;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v19 = -1073479680;
  }
  else
  {
    v27 = v16 | 0x2000000;
    LastFailureAsHRESULT = GetRelativeSDFromFileRecordForAdminRestore(
                             *((struct ISdAsyncPriv **)this + 5),
                             a3,
                             a4,
                             v11,
                             v36,
                             (unsigned __int8 **)&pv,
                             &v31);
    v18 = 0;
    v13 = 592;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v19 = -1056112640;
  }
  v29 = v13;
  v20 = 0;
  if ( *((_DWORD *)this + 26) != 11 )
  {
    v21 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, _WORD *))(*(_QWORD *)a4 + 40LL))(a4, v41);
    v17 = (CZipRestoreFile *)(unsigned int)v21;
    LastFailureAsHRESULT = v21;
    v18 = 0;
    v22 = v21 < 0;
    v13 = 603;
    if ( v22 )
      goto LABEL_3;
    v29 = 603;
    if ( !(_DWORD)v17 )
    {
      v23 = v41;
      if ( !v41[0] )
        v23 = 0;
      v20 = v23;
    }
  }
  if ( a7 )
  {
    LastFailureAsHRESULT = CZipRestoreFile::_CheckFreeSpaceForRestore(v17, *((const unsigned __int16 **)this + 8), a4);
    v13 = 612;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 612;
  }
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdReadObj *, __int64))(*(_QWORD *)a8 + 72LL))(a8, v18);
  v13 = 615;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v29 = 615;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdReadObj *, _QWORD, _WORD *, _QWORD, _DWORD, LPVOID, unsigned int, unsigned __int8 *, unsigned int, int, int, _DWORD, int))(*(_QWORD *)a8 + 24LL))(
                           a8,
                           *((_QWORD *)this + 8),
                           v20,
                           v19,
                           0,
                           pv,
                           v31,
                           v34,
                           v32,
                           1,
                           v27,
                           *((_DWORD *)this + 27),
                           a7);
  v13 = 617;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v29 = 617;
  if ( !a7 )
  {
    LastFailureAsHRESULT = CZipRestoreFile::_CheckFreeSpaceForRestore(v24, *((const unsigned __int16 **)this + 8), a4);
    v13 = 621;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v29 = 621;
  }
  LastFailureAsHRESULT = CZipRestoreFile::_RestoreFromZipToFileStreamed(this, a4, a8);
  v13 = 625;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v29 = 625;
LABEL_41:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v34);
  v25 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)v39);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v25;
}

```

## disassembly

```asm
0x180007438  push    rbp
0x18000743a  push    rbx
0x18000743b  push    rsi
0x18000743c  push    rdi
0x18000743d  push    r12
0x18000743f  push    r13
0x180007441  push    r14
0x180007443  push    r15
0x180007445  lea     rbp, [rsp-48h]
0x18000744a  sub     rsp, 148h
0x180007451  mov     rax, cs:__security_cookie
0x180007458  xor     rax, rsp
0x18000745b  mov     [rbp+80h+var_50], rax
0x18000745f  mov     rsi, r9
0x180007462  mov     r15, r8
0x180007465  mov     [rbp+80h+pSid], rdx
0x180007469  mov     r14, rcx
0x18000746c  mov     rdi, [rbp+80h+arg_20]
0x180007473  mov     [rbp+80h+var_B8], rdi
0x180007477  mov     rax, [rbp+80h+arg_28]
0x18000747e  mov     [rbp+80h+var_B0], rax
0x180007482  mov     r13d, [rbp+80h+arg_30]
0x180007489  mov     r12, [rbp+80h+arg_38]
0x180007490  mov     r9d, 1; unsigned __int16
0x180007496  mov     r8d, 219h; unsigned __int16
0x18000749c  lea     rdx, aCziprestorefil_10; "CZipRestoreFile::_RestoreMainStreamToDi"...
0x1800074a3  lea     rcx, [rsp+180h+var_108]; this
0x1800074a8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800074ad  xor     ecx, ecx
0x1800074af  mov     [rbp+80h+pv], rcx
0x1800074b3  mov     [rbp+80h+var_C0], rcx
0x1800074b7  mov     [rbp+80h+var_D0], ecx
0x1800074ba  mov     [rbp+80h+var_CC], ecx
0x1800074bd  mov     [rsp+180h+var_110], ecx
0x1800074c1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800074c8  movdqu  xmmword ptr [rbp+80h+pguid.Data1], xmm0
0x1800074cd  lea     rax, qword_1800E8530
0x1800074d4  mov     [rbp+80h+lpFileName], rax
0x1800074d8  mov     [rbp+80h+var_98], rcx
0x1800074dc  mov     [rbp+80h+var_90], rax
0x1800074e0  mov     [rbp+80h+var_88], rcx
0x1800074e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800074e8  mov     eax, 228h
0x1800074ed  cmp     [rbp+80h+pSid], rcx
0x1800074f1  jnz     short loc_180007505
0x1800074f3  mov     [rsp+180h+var_108], 80070057h
0x1800074fb  mov     [rsp+180h+var_102], ax
0x180007500  jmp     loc_18000789F
0x180007505  mov     [rsp+180h+var_104], ax
0x18000750a  mov     eax, 229h
0x18000750f  test    r15, r15
0x180007512  jz      short loc_1800074F3
0x180007514  mov     [rsp+180h+var_104], ax
0x180007519  mov     eax, 22Ah
0x18000751e  test    rsi, rsi
0x180007521  jz      short loc_1800074F3
0x180007523  mov     [rsp+180h+var_104], ax
0x180007528  mov     eax, 22Bh
0x18000752d  test    rdi, rdi
0x180007530  jz      short loc_1800074F3
0x180007532  mov     [rsp+180h+var_104], ax
0x180007537  mov     eax, 22Ch
0x18000753c  cmp     [rbp+80h+var_B0], rcx
0x180007540  jz      short loc_1800074F3
0x180007542  mov     [rsp+180h+var_104], ax
0x180007547  mov     eax, 22Dh
0x18000754c  test    r12, r12
0x18000754f  jz      short loc_1800074F3
0x180007551  mov     [rsp+180h+var_108], ecx
0x180007555  mov     [rsp+180h+var_104], ax
0x18000755a  test    r13d, r13d
0x18000755d  jz      loc_180007668
0x180007563  lea     rcx, [rbp+80h+pguid]; pguid
0x180007567  call    cs:__imp_CoCreateGuid
0x18000756d  mov     [rsp+180h+var_108], eax
0x180007571  test    eax, eax
0x180007573  mov     eax, 234h
0x180007578  js      short loc_1800074FB
0x18000757a  mov     [rsp+180h+var_104], ax
0x18000757f  lea     rdx, [rbp+80h+pguid]; struct _GUID *
0x180007583  lea     rcx, [rbp+80h+var_90]; this
0x180007587  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x18000758c  mov     [rsp+180h+var_108], eax
0x180007590  test    eax, eax
0x180007592  mov     eax, 235h
0x180007597  js      loc_1800074FB
0x18000759d  mov     [rsp+180h+var_104], ax
0x1800075a2  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800075a7  lea     rcx, [r14+40h]; this
0x1800075ab  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x1800075b0  lea     r8d, [rax+1]; unsigned int
0x1800075b4  mov     rdx, [r14+40h]; unsigned __int16 *
0x1800075b8  lea     rcx, [rbp+80h+lpFileName]; this
0x1800075bc  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x1800075c1  mov     [rsp+180h+var_108], eax
0x1800075c5  test    eax, eax
0x1800075c7  mov     eax, 238h
0x1800075cc  js      loc_1800074FB
0x1800075d2  mov     [rsp+180h+var_104], ax
0x1800075d7  mov     rdx, [rbp+80h+var_90]; unsigned __int16 *
0x1800075db  lea     rcx, [rbp+80h+lpFileName]; this
0x1800075df  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800075e4  mov     [rsp+180h+var_108], eax
0x1800075e8  xor     ecx, ecx
0x1800075ea  test    eax, eax
0x1800075ec  mov     eax, 23Ah
0x1800075f1  js      loc_1800074FB
0x1800075f7  mov     [rsp+180h+var_104], ax
0x1800075fc  mov     [rsp+180h+hTemplateFile], rcx; hTemplateFile
0x180007601  mov     [rsp+180h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180007609  mov     [rsp+180h+dwCreationDisposition], 1; dwCreationDisposition
0x180007611  xor     r9d, r9d; lpSecurityAttributes
0x180007614  xor     r8d, r8d; dwShareMode
0x180007617  mov     edx, 0C0000000h; dwDesiredAccess
0x18000761c  mov     rcx, [rbp+80h+lpFileName]; lpFileName
0x180007620  call    cs:__imp_CreateFileW
0x180007626  mov     rbx, rax
0x180007629  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000762d  jnz     short loc_180007642
0x18000762f  call    GetLastFailureAsHRESULT
0x180007634  mov     [rsp+180h+var_108], eax
0x180007638  mov     eax, 23Dh
0x18000763d  jmp     loc_1800074FB
0x180007642  xor     ecx, ecx
0x180007644  mov     [rsp+180h+var_108], ecx
0x180007648  mov     eax, 23Dh
0x18000764d  mov     [rsp+180h+var_104], ax
0x180007652  test    rbx, rbx
0x180007655  jz      short loc_180007664
0x180007657  mov     rcx, rbx; hObject
0x18000765a  call    cs:__imp_CloseHandle
0x180007660  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007664  mov     rdi, [rbp+80h+var_B8]
0x180007668  mov     rax, [rsi]
0x18000766b  lea     rdx, [rsp+180h+var_110]
0x180007670  mov     rcx, rsi
0x180007673  mov     rax, [rax+80h]
0x18000767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767f  mov     [rsp+180h+var_108], eax
0x180007683  test    eax, eax
0x180007685  mov     eax, 241h
0x18000768a  js      loc_1800074FB
0x180007690  mov     [rsp+180h+var_104], ax
0x180007695  mov     eax, [rsp+180h+var_110]
0x180007699  bts     eax, 1Bh
0x18000769d  mov     [rsp+180h+var_110], eax
0x1800076a1  cmp     dword ptr [r14+68h], 0Bh
0x1800076a6  jz      short loc_1800076F8
0x1800076a8  bts     eax, 19h
0x1800076ac  mov     [rsp+180h+var_110], eax
0x1800076b0  lea     rax, [rbp+80h+var_D0]
0x1800076b4  mov     [rsp+180h+hTemplateFile], rax; unsigned int *
0x1800076b9  lea     rax, [rbp+80h+pv]
0x1800076bd  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x1800076c2  mov     rax, [rbp+80h+var_B0]
0x1800076c6  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; struct CSdUserSidList *
0x1800076cb  mov     r9, rdi; struct ISdGlobalCatalog *
0x1800076ce  mov     r8, rsi; struct ISdFileRecord *
0x1800076d1  mov     rdx, r15; struct ISdCallback2 *
0x1800076d4  mov     rcx, [r14+28h]; struct ISdAsyncPriv *
0x1800076d8  call    ?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z; GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)
0x1800076dd  mov     [rsp+180h+var_108], eax
0x1800076e1  xor     edx, edx
0x1800076e3  test    eax, eax
0x1800076e5  mov     eax, 250h
0x1800076ea  js      loc_1800074FB
0x1800076f0  mov     r15d, 0C10D0000h
0x1800076f6  jmp     short loc_180007742
0x1800076f8  lea     rax, [rbp+80h+var_CC]
0x1800076fc  mov     [rsp+180h+hTemplateFile], rax; unsigned int *
0x180007701  lea     rax, [rbp+80h+var_C0]
0x180007705  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x18000770a  lea     rax, [rbp+80h+var_D0]
0x18000770e  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; unsigned int *
0x180007713  lea     r9, [rbp+80h+pv]; unsigned __int8 **
0x180007717  mov     r8d, 1; int
0x18000771d  mov     rdx, rsi; struct ISdFileRecord *
0x180007720  mov     rcx, [rbp+80h+pSid]; pSid
0x180007724  call    ?GetRelativeSDFromFileRecordForUserModeRestore@@YAJPEBU_SID@@PEAUISdFileRecord@@HPEAPEAEPEAK23@Z; GetRelativeSDFromFileRecordForUserModeRestore(_SID const *,ISdFileRecord *,int,uchar * *,ulong *,uchar * *,ulong *)
0x180007729  mov     [rsp+180h+var_108], eax
0x18000772d  xor     edx, edx
0x18000772f  test    eax, eax
0x180007731  mov     eax, 256h
0x180007736  js      loc_1800074FB
0x18000773c  mov     r15d, 0C0040000h
0x180007742  mov     [rsp+180h+var_104], ax
0x180007747  mov     rdi, rdx
0x18000774a  cmp     dword ptr [r14+68h], 0Bh
0x18000774f  jz      short loc_180007791
0x180007751  mov     rax, [rsi]
0x180007754  lea     rdx, [rbp+80h+var_70]
0x180007758  mov     rcx, rsi
0x18000775b  mov     rax, [rax+28h]
0x18000775f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007764  mov     ecx, eax; this
0x180007766  mov     [rsp+180h+var_108], eax
0x18000776a  xor     edx, edx
0x18000776c  test    eax, eax
0x18000776e  mov     eax, 25Bh
0x180007773  js      loc_1800074FB
0x180007779  mov     [rsp+180h+var_104], ax
0x18000777e  test    ecx, ecx
0x180007780  jnz     short loc_180007791
0x180007782  lea     rax, [rbp+80h+var_70]
0x180007786  cmp     [rbp+80h+var_70], dx
0x18000778a  cmovz   rax, rdi
0x18000778e  mov     rdi, rax
0x180007791  test    r13d, r13d
0x180007794  jz      short loc_1800077B8
0x180007796  mov     r8, rsi; struct ISdFileRecord *
0x180007799  mov     rdx, [r14+40h]; unsigned __int16 *
0x18000779d  call    ?_CheckFreeSpaceForRestore@CZipRestoreFile@@AEAAJPEBGPEAUISdFileRecord@@@Z; CZipRestoreFile::_CheckFreeSpaceForRestore(ushort const *,ISdFileRecord *)
0x1800077a2  mov     [rsp+180h+var_108], eax
0x1800077a6  test    eax, eax
0x1800077a8  mov     eax, 264h
0x1800077ad  js      loc_1800074FB
0x1800077b3  mov     [rsp+180h+var_104], ax
0x1800077b8  mov     rax, [r12]
0x1800077bc  mov     rcx, r12
0x1800077bf  mov     rax, [rax+48h]
0x1800077c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c8  mov     [rsp+180h+var_108], eax
0x1800077cc  xor     edx, edx
0x1800077ce  test    eax, eax
0x1800077d0  mov     eax, 267h
0x1800077d5  js      loc_1800074FB
0x1800077db  mov     [rsp+180h+var_104], ax
0x1800077e0  mov     rax, [r12]
0x1800077e4  mov     r10, [rax+18h]
0x1800077e8  mov     [rsp+180h+var_120], r13d
0x1800077ed  mov     eax, [r14+6Ch]
0x1800077f1  mov     [rsp+180h+var_128], eax
0x1800077f5  mov     ecx, [rsp+180h+var_110]
0x1800077f9  mov     [rsp+180h+var_130], ecx
0x1800077fd  mov     [rsp+180h+var_138], 1
0x180007805  mov     eax, [rbp+80h+var_CC]
0x180007808  mov     [rsp+180h+var_140], eax
0x18000780c  mov     rax, [rbp+80h+var_C0]
0x180007810  mov     [rsp+180h+var_148], rax
0x180007815  mov     ecx, [rbp+80h+var_D0]
0x180007818  mov     dword ptr [rsp+180h+hTemplateFile], ecx
0x18000781c  mov     rcx, [rbp+80h+pv]
0x180007820  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rcx
0x180007825  mov     [rsp+180h+dwCreationDisposition], edx
0x180007829  mov     r9d, r15d
0x18000782c  mov     r8, rdi
0x18000782f  mov     rdx, [r14+40h]
0x180007833  mov     rcx, r12
0x180007836  mov     rax, r10
0x180007839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000783e  mov     [rsp+180h+var_108], eax
0x180007842  test    eax, eax
0x180007844  mov     eax, 269h
0x180007849  js      loc_1800074FB
0x18000784f  mov     [rsp+180h+var_104], ax
0x180007854  test    r13d, r13d
0x180007857  jnz     short loc_18000787B
0x180007859  mov     r8, rsi; struct ISdFileRecord *
0x18000785c  mov     rdx, [r14+40h]; unsigned __int16 *
0x180007860  call    ?_CheckFreeSpaceForRestore@CZipRestoreFile@@AEAAJPEBGPEAUISdFileRecord@@@Z; CZipRestoreFile::_CheckFreeSpaceForRestore(ushort const *,ISdFileRecord *)
0x180007865  mov     [rsp+180h+var_108], eax
0x180007869  test    eax, eax
0x18000786b  mov     eax, 26Dh
0x180007870  js      loc_1800074FB
0x180007876  mov     [rsp+180h+var_104], ax
0x18000787b  mov     r8, r12; struct ISdReadObj *
0x18000787e  mov     rdx, rsi; struct ISdFileRecord *
0x180007881  mov     rcx, r14; this
0x180007884  call    ?_RestoreFromZipToFileStreamed@CZipRestoreFile@@AEAAJPEAUISdFileRecord@@PEAUISdReadObj@@@Z; CZipRestoreFile::_RestoreFromZipToFileStreamed(ISdFileRecord *,ISdReadObj *)
0x180007889  mov     [rsp+180h+var_108], eax
0x18000788d  test    eax, eax
0x18000788f  mov     eax, 271h
0x180007894  js      loc_1800074FB
0x18000789a  mov     [rsp+180h+var_104], ax
0x18000789f  mov     rcx, [rbp+80h+pv]; pv
0x1800078a3  call    cs:__imp_CoTaskMemFree
0x1800078a9  mov     [rbp+80h+pv], 0
0x1800078b1  mov     rcx, [rbp+80h+var_C0]; pv
0x1800078b5  call    cs:__imp_CoTaskMemFree
0x1800078bb  mov     edi, [rsp+180h+var_108]
0x1800078bf  lea     rcx, [rbx-1]
0x1800078c3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800078c7  ja      short loc_1800078D2
0x1800078c9  mov     rcx, rbx; hObject
0x1800078cc  call    cs:__imp_CloseHandle
0x1800078d2  lea     rcx, [rbp+80h+var_90]; this
0x1800078d6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800078db  lea     rcx, [rbp+80h+lpFileName]; this
0x1800078df  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800078e4  lea     rcx, [rsp+180h+var_108]; this
0x1800078e9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800078ee  mov     eax, edi
0x1800078f0  mov     rcx, [rbp+80h+var_50]
0x1800078f4  xor     rcx, rsp; StackCookie
0x1800078f7  call    __security_check_cookie
0x1800078fc  add     rsp, 148h
0x180007903  pop     r15
0x180007905  pop     r14
0x180007907  pop     r13
0x180007909  pop     r12
  ... truncated ...
```
