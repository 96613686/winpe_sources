# CZipRestoreFile::_RestoreMainStreamToDisk(_SID const *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,int,ISdReadObj *)

- ea: `0x180007588`
- end: `0x180007a89`
- name: `?_RestoreMainStreamToDisk@CZipRestoreFile@@AEAAJPEBU_SID@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@HPEAUISdReadObj@@@Z`
- size: `1281`
- prototype: `__int64 __usercall@<rax>(CZipRestoreFile *__hidden this@<rcx>, const struct _SID *@<rdx>, struct ISdCallback2 *@<r8>, struct ISdFileRecord *@<r9>, struct ISdGlobalCatalog *, struct CSdUserSidList *, int, struct ISdReadObj *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800054c0`
- `0x180005780`

## callees

- `0x180006530`
- `0x180006fd0`
- `0x180007588`
- `0x180026738`
- `0x180026b6c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009dd7c`
- `0x18009e718`
- `0x18009e750`
- `0x18009e924`
- `0x18009f560`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000777a`
- `KERNEL32!CreateFileW` at `0x18000777a`
- `KERNEL32!CloseHandle` at `0x1800077ba`
- `KERNEL32!CloseHandle` at `0x180007a3e`
- `KERNEL32!CloseHandle` at `0x1800077ba`
- `KERNEL32!CloseHandle` at `0x180007a3e`
- `ole32!CoTaskMemFree` at `0x180007a09`
- `ole32!CoTaskMemFree` at `0x180007a21`
- `ole32!CoTaskMemFree` at `0x180007a09`
- `ole32!CoTaskMemFree` at `0x180007a21`
- `ole32!CoCreateGuid` at `0x1800076b7`
- `ole32!CoCreateGuid` at `0x1800076b7`

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
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  v39[0] = (unsigned __int16 *)qword_1800EE510;
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
0x180007588  push    rbp
0x18000758a  push    rbx
0x18000758b  push    rsi
0x18000758c  push    rdi
0x18000758d  push    r12
0x18000758f  push    r13
0x180007591  push    r14
0x180007593  push    r15
0x180007595  lea     rbp, [rsp-48h]
0x18000759a  sub     rsp, 148h
0x1800075a1  mov     rax, cs:__security_cookie
0x1800075a8  xor     rax, rsp
0x1800075ab  mov     [rbp+80h+var_50], rax
0x1800075af  mov     rsi, r9
0x1800075b2  mov     r15, r8
0x1800075b5  mov     [rbp+80h+pSid], rdx
0x1800075b9  mov     r14, rcx
0x1800075bc  mov     rdi, [rbp+80h+arg_20]
0x1800075c3  mov     [rbp+80h+var_B8], rdi
0x1800075c7  mov     rax, [rbp+80h+arg_28]
0x1800075ce  mov     [rbp+80h+var_B0], rax
0x1800075d2  mov     r13d, [rbp+80h+arg_30]
0x1800075d9  mov     r12, [rbp+80h+arg_38]
0x1800075e0  mov     r9d, 1; unsigned __int16
0x1800075e6  mov     r8d, 219h; unsigned __int16
0x1800075ec  lea     rdx, aCziprestorefil_10; "CZipRestoreFile::_RestoreMainStreamToDi"...
0x1800075f3  lea     rcx, [rsp+180h+var_108]; this
0x1800075f8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800075fd  xor     ecx, ecx
0x1800075ff  mov     [rbp+80h+pv], rcx
0x180007603  mov     [rbp+80h+var_C0], rcx
0x180007607  mov     [rbp+80h+var_D0], ecx
0x18000760a  mov     [rbp+80h+var_CC], ecx
0x18000760d  mov     [rsp+180h+var_110], ecx
0x180007611  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007618  movdqu  xmmword ptr [rbp+80h+pguid.Data1], xmm0
0x18000761d  lea     rax, qword_1800EE510
0x180007624  mov     [rbp+80h+lpFileName], rax
0x180007628  mov     [rbp+80h+var_98], rcx
0x18000762c  mov     [rbp+80h+var_90], rax
0x180007630  mov     [rbp+80h+var_88], rcx
0x180007634  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007638  mov     eax, 228h
0x18000763d  cmp     [rbp+80h+pSid], rcx
0x180007641  jnz     short loc_180007655
0x180007643  mov     [rsp+180h+var_108], 80070057h
0x18000764b  mov     [rsp+180h+var_102], ax
0x180007650  jmp     loc_180007A05
0x180007655  mov     [rsp+180h+var_104], ax
0x18000765a  mov     eax, 229h
0x18000765f  test    r15, r15
0x180007662  jz      short loc_180007643
0x180007664  mov     [rsp+180h+var_104], ax
0x180007669  mov     eax, 22Ah
0x18000766e  test    rsi, rsi
0x180007671  jz      short loc_180007643
0x180007673  mov     [rsp+180h+var_104], ax
0x180007678  mov     eax, 22Bh
0x18000767d  test    rdi, rdi
0x180007680  jz      short loc_180007643
0x180007682  mov     [rsp+180h+var_104], ax
0x180007687  mov     eax, 22Ch
0x18000768c  cmp     [rbp+80h+var_B0], rcx
0x180007690  jz      short loc_180007643
0x180007692  mov     [rsp+180h+var_104], ax
0x180007697  mov     eax, 22Dh
0x18000769c  test    r12, r12
0x18000769f  jz      short loc_180007643
0x1800076a1  mov     [rsp+180h+var_108], ecx
0x1800076a5  mov     [rsp+180h+var_104], ax
0x1800076aa  test    r13d, r13d
0x1800076ad  jz      loc_1800077CE
0x1800076b3  lea     rcx, [rbp+80h+pguid]; pguid
0x1800076b7  call    cs:__imp_CoCreateGuid
0x1800076be  nop     dword ptr [rax+rax+00h]
0x1800076c3  mov     [rsp+180h+var_108], eax
0x1800076c7  test    eax, eax
0x1800076c9  mov     eax, 234h
0x1800076ce  js      loc_18000764B
0x1800076d4  mov     [rsp+180h+var_104], ax
0x1800076d9  lea     rdx, [rbp+80h+pguid]; struct _GUID *
0x1800076dd  lea     rcx, [rbp+80h+var_90]; this
0x1800076e1  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x1800076e6  mov     [rsp+180h+var_108], eax
0x1800076ea  test    eax, eax
0x1800076ec  mov     eax, 235h
0x1800076f1  js      loc_18000764B
0x1800076f7  mov     [rsp+180h+var_104], ax
0x1800076fc  mov     edx, 5Ch ; '\'; unsigned __int16
0x180007701  lea     rcx, [r14+40h]; this
0x180007705  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18000770a  lea     r8d, [rax+1]; unsigned int
0x18000770e  mov     rdx, [r14+40h]; unsigned __int16 *
0x180007712  lea     rcx, [rbp+80h+lpFileName]; this
0x180007716  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x18000771b  mov     [rsp+180h+var_108], eax
0x18000771f  test    eax, eax
0x180007721  mov     eax, 238h
0x180007726  js      loc_18000764B
0x18000772c  mov     [rsp+180h+var_104], ax
0x180007731  mov     rdx, [rbp+80h+var_90]; unsigned __int16 *
0x180007735  lea     rcx, [rbp+80h+lpFileName]; this
0x180007739  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000773e  mov     [rsp+180h+var_108], eax
0x180007742  xor     ecx, ecx
0x180007744  test    eax, eax
0x180007746  mov     eax, 23Ah
0x18000774b  js      loc_18000764B
0x180007751  mov     [rsp+180h+var_104], ax
0x180007756  mov     [rsp+180h+hTemplateFile], rcx; hTemplateFile
0x18000775b  mov     [rsp+180h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180007763  mov     [rsp+180h+dwCreationDisposition], 1; dwCreationDisposition
0x18000776b  xor     r9d, r9d; lpSecurityAttributes
0x18000776e  xor     r8d, r8d; dwShareMode
0x180007771  mov     edx, 0C0000000h; dwDesiredAccess
0x180007776  mov     rcx, [rbp+80h+lpFileName]; lpFileName
0x18000777a  call    cs:__imp_CreateFileW
0x180007781  nop     dword ptr [rax+rax+00h]
0x180007786  mov     rbx, rax
0x180007789  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000778d  jnz     short loc_1800077A2
0x18000778f  call    GetLastFailureAsHRESULT
0x180007794  mov     [rsp+180h+var_108], eax
0x180007798  mov     eax, 23Dh
0x18000779d  jmp     loc_18000764B
0x1800077a2  xor     ecx, ecx
0x1800077a4  mov     [rsp+180h+var_108], ecx
0x1800077a8  mov     eax, 23Dh
0x1800077ad  mov     [rsp+180h+var_104], ax
0x1800077b2  test    rbx, rbx
0x1800077b5  jz      short loc_1800077CA
0x1800077b7  mov     rcx, rbx; hObject
0x1800077ba  call    cs:__imp_CloseHandle
0x1800077c1  nop     dword ptr [rax+rax+00h]
0x1800077c6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800077ca  mov     rdi, [rbp+80h+var_B8]
0x1800077ce  mov     rax, [rsi]
0x1800077d1  lea     rdx, [rsp+180h+var_110]
0x1800077d6  mov     rcx, rsi
0x1800077d9  mov     rax, [rax+80h]
0x1800077e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e5  mov     [rsp+180h+var_108], eax
0x1800077e9  test    eax, eax
0x1800077eb  mov     eax, 241h
0x1800077f0  js      loc_18000764B
0x1800077f6  mov     [rsp+180h+var_104], ax
0x1800077fb  mov     eax, [rsp+180h+var_110]
0x1800077ff  bts     eax, 1Bh
0x180007803  mov     [rsp+180h+var_110], eax
0x180007807  cmp     dword ptr [r14+68h], 0Bh
0x18000780c  jz      short loc_18000785E
0x18000780e  bts     eax, 19h
0x180007812  mov     [rsp+180h+var_110], eax
0x180007816  lea     rax, [rbp+80h+var_D0]
0x18000781a  mov     [rsp+180h+hTemplateFile], rax; unsigned int *
0x18000781f  lea     rax, [rbp+80h+pv]
0x180007823  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x180007828  mov     rax, [rbp+80h+var_B0]
0x18000782c  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; struct CSdUserSidList *
0x180007831  mov     r9, rdi; struct ISdGlobalCatalog *
0x180007834  mov     r8, rsi; struct ISdFileRecord *
0x180007837  mov     rdx, r15; struct ISdCallback2 *
0x18000783a  mov     rcx, [r14+28h]; struct ISdAsyncPriv *
0x18000783e  call    ?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z; GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)
0x180007843  mov     [rsp+180h+var_108], eax
0x180007847  xor     edx, edx
0x180007849  test    eax, eax
0x18000784b  mov     eax, 250h
0x180007850  js      loc_18000764B
0x180007856  mov     r15d, 0C10D0000h
0x18000785c  jmp     short loc_1800078A8
0x18000785e  lea     rax, [rbp+80h+var_CC]
0x180007862  mov     [rsp+180h+hTemplateFile], rax; unsigned int *
0x180007867  lea     rax, [rbp+80h+var_C0]
0x18000786b  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x180007870  lea     rax, [rbp+80h+var_D0]
0x180007874  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; unsigned int *
0x180007879  lea     r9, [rbp+80h+pv]; unsigned __int8 **
0x18000787d  mov     r8d, 1; int
0x180007883  mov     rdx, rsi; struct ISdFileRecord *
0x180007886  mov     rcx, [rbp+80h+pSid]; pSid
0x18000788a  call    ?GetRelativeSDFromFileRecordForUserModeRestore@@YAJPEBU_SID@@PEAUISdFileRecord@@HPEAPEAEPEAK23@Z; GetRelativeSDFromFileRecordForUserModeRestore(_SID const *,ISdFileRecord *,int,uchar * *,ulong *,uchar * *,ulong *)
0x18000788f  mov     [rsp+180h+var_108], eax
0x180007893  xor     edx, edx
0x180007895  test    eax, eax
0x180007897  mov     eax, 256h
0x18000789c  js      loc_18000764B
0x1800078a2  mov     r15d, 0C0040000h
0x1800078a8  mov     [rsp+180h+var_104], ax
0x1800078ad  mov     rdi, rdx
0x1800078b0  cmp     dword ptr [r14+68h], 0Bh
0x1800078b5  jz      short loc_1800078F7
0x1800078b7  mov     rax, [rsi]
0x1800078ba  lea     rdx, [rbp+80h+var_70]
0x1800078be  mov     rcx, rsi
0x1800078c1  mov     rax, [rax+28h]
0x1800078c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ca  mov     ecx, eax; this
0x1800078cc  mov     [rsp+180h+var_108], eax
0x1800078d0  xor     edx, edx
0x1800078d2  test    eax, eax
0x1800078d4  mov     eax, 25Bh
0x1800078d9  js      loc_18000764B
0x1800078df  mov     [rsp+180h+var_104], ax
0x1800078e4  test    ecx, ecx
0x1800078e6  jnz     short loc_1800078F7
0x1800078e8  lea     rax, [rbp+80h+var_70]
0x1800078ec  cmp     [rbp+80h+var_70], dx
0x1800078f0  cmovz   rax, rdi
0x1800078f4  mov     rdi, rax
0x1800078f7  test    r13d, r13d
0x1800078fa  jz      short loc_18000791E
0x1800078fc  mov     r8, rsi; struct ISdFileRecord *
0x1800078ff  mov     rdx, [r14+40h]; unsigned __int16 *
0x180007903  call    ?_CheckFreeSpaceForRestore@CZipRestoreFile@@AEAAJPEBGPEAUISdFileRecord@@@Z; CZipRestoreFile::_CheckFreeSpaceForRestore(ushort const *,ISdFileRecord *)
0x180007908  mov     [rsp+180h+var_108], eax
0x18000790c  test    eax, eax
0x18000790e  mov     eax, 264h
0x180007913  js      loc_18000764B
0x180007919  mov     [rsp+180h+var_104], ax
0x18000791e  mov     rax, [r12]
0x180007922  mov     rcx, r12
0x180007925  mov     rax, [rax+48h]
0x180007929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792e  mov     [rsp+180h+var_108], eax
0x180007932  xor     edx, edx
0x180007934  test    eax, eax
0x180007936  mov     eax, 267h
0x18000793b  js      loc_18000764B
0x180007941  mov     [rsp+180h+var_104], ax
0x180007946  mov     rax, [r12]
0x18000794a  mov     r10, [rax+18h]
0x18000794e  mov     [rsp+180h+var_120], r13d
0x180007953  mov     eax, [r14+6Ch]
0x180007957  mov     [rsp+180h+var_128], eax
0x18000795b  mov     ecx, [rsp+180h+var_110]
0x18000795f  mov     [rsp+180h+var_130], ecx
0x180007963  mov     [rsp+180h+var_138], 1
0x18000796b  mov     eax, [rbp+80h+var_CC]
0x18000796e  mov     [rsp+180h+var_140], eax
0x180007972  mov     rax, [rbp+80h+var_C0]
0x180007976  mov     [rsp+180h+var_148], rax
0x18000797b  mov     ecx, [rbp+80h+var_D0]
0x18000797e  mov     dword ptr [rsp+180h+hTemplateFile], ecx
0x180007982  mov     rcx, [rbp+80h+pv]
0x180007986  mov     qword ptr [rsp+180h+dwFlagsAndAttributes], rcx
0x18000798b  mov     [rsp+180h+dwCreationDisposition], edx
0x18000798f  mov     r9d, r15d
0x180007992  mov     r8, rdi
0x180007995  mov     rdx, [r14+40h]
0x180007999  mov     rcx, r12
0x18000799c  mov     rax, r10
0x18000799f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a4  mov     [rsp+180h+var_108], eax
0x1800079a8  test    eax, eax
0x1800079aa  mov     eax, 269h
0x1800079af  js      loc_18000764B
0x1800079b5  mov     [rsp+180h+var_104], ax
0x1800079ba  test    r13d, r13d
0x1800079bd  jnz     short loc_1800079E1
0x1800079bf  mov     r8, rsi; struct ISdFileRecord *
0x1800079c2  mov     rdx, [r14+40h]; unsigned __int16 *
0x1800079c6  call    ?_CheckFreeSpaceForRestore@CZipRestoreFile@@AEAAJPEBGPEAUISdFileRecord@@@Z; CZipRestoreFile::_CheckFreeSpaceForRestore(ushort const *,ISdFileRecord *)
0x1800079cb  mov     [rsp+180h+var_108], eax
0x1800079cf  test    eax, eax
0x1800079d1  mov     eax, 26Dh
0x1800079d6  js      loc_18000764B
0x1800079dc  mov     [rsp+180h+var_104], ax
0x1800079e1  mov     r8, r12; struct ISdReadObj *
0x1800079e4  mov     rdx, rsi; struct ISdFileRecord *
0x1800079e7  mov     rcx, r14; this
0x1800079ea  call    ?_RestoreFromZipToFileStreamed@CZipRestoreFile@@AEAAJPEAUISdFileRecord@@PEAUISdReadObj@@@Z; CZipRestoreFile::_RestoreFromZipToFileStreamed(ISdFileRecord *,ISdReadObj *)
0x1800079ef  mov     [rsp+180h+var_108], eax
0x1800079f3  test    eax, eax
0x1800079f5  mov     eax, 271h
0x1800079fa  js      loc_18000764B
0x180007a00  mov     [rsp+180h+var_104], ax
0x180007a05  mov     rcx, [rbp+80h+pv]; pv
0x180007a09  call    cs:__imp_CoTaskMemFree
0x180007a10  nop     dword ptr [rax+rax+00h]
0x180007a15  mov     [rbp+80h+pv], 0
0x180007a1d  mov     rcx, [rbp+80h+var_C0]; pv
0x180007a21  call    cs:__imp_CoTaskMemFree
0x180007a28  nop     dword ptr [rax+rax+00h]
0x180007a2d  mov     edi, [rsp+180h+var_108]
0x180007a31  lea     rcx, [rbx-1]
0x180007a35  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007a39  ja      short loc_180007A4A
0x180007a3b  mov     rcx, rbx; hObject
0x180007a3e  call    cs:__imp_CloseHandle
0x180007a45  nop     dword ptr [rax+rax+00h]
0x180007a4a  lea     rcx, [rbp+80h+var_90]; this
0x180007a4e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180007a53  lea     rcx, [rbp+80h+lpFileName]; this
0x180007a57  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180007a5c  lea     rcx, [rsp+180h+var_108]; this
0x180007a61  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180007a66  mov     eax, edi
0x180007a68  mov     rcx, [rbp+80h+var_50]
0x180007a6c  xor     rcx, rsp; StackCookie
  ... truncated ...
```
