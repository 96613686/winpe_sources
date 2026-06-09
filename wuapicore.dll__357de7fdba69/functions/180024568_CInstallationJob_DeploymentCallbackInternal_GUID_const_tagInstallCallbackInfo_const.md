# CInstallationJob::DeploymentCallbackInternal(_GUID const &,tagInstallCallbackInfo const &)

- ea: `0x180024568`
- end: `0x180024d59`
- name: `?DeploymentCallbackInternal@CInstallationJob@@AEAAJAEBU_GUID@@AEBUtagInstallCallbackInfo@@@Z`
- size: `2033`
- prototype: `__int64 __fastcall(CInstallationJob *__hidden this, const struct _GUID *, const struct tagInstallCallbackInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b4f0`

## callees

- `0x180006ac4`
- `0x180024568`
- `0x180024d60`
- `0x180024fac`
- `0x180025148`
- `0x180069270`
- `0x180081a38`
- `0x1800826a0`
- `0x180083030`
- `0x1800830ac`
- `0x180090bc8`
- `0x180093404`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024973`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024973`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a08`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a08`
- `OLEAUT32!__imp_VariantInit` at `0x1800245a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800245ae`
- `OLEAUT32!__imp_VariantInit` at `0x1800245a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800245ae`
- `OLEAUT32!__imp_VariantClear` at `0x180024d2a`
- `OLEAUT32!__imp_VariantClear` at `0x180024d2a`

## string_xrefs

- `0x18002475a`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x1800249f7`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180024a65`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180024c05`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x1800248a2`: `Deployment callback complete for UpdateID = %ws, callback code = %d, CallbackInfo cookie length = %d`
- `0x1800249ac`: `Install`
- `0x1800249b3`: `Uninstall`
- `0x180024a7d`: `Commit`
- `0x180024b3b`: `Commit`
- `0x180024ba1`: `Commit`
- `0x180024cdd`: `Commit`
- `0x180024647`: `C:\__w\1\s\src\Client\comapi\UpdateInstallationStatus.cpp`

## pseudocode

```c
__int64 __fastcall CInstallationJob::DeploymentCallbackInternal(
        CInstallationJob *this,
        const struct _GUID *a2,
        const struct tagInstallCallbackInfo *a3)
{
  const struct tagPerUpdateInstallStatus *v5; // r12
  int v6; // ebx
  int v7; // esi
  __int64 v8; // rdi
  unsigned int v9; // r13d
  __int64 v10; // rcx
  __int64 v11; // rax
  CUpdateInstallationResult *v12; // rax
  __int64 v13; // r12
  void **v14; // rbx
  int v15; // eax
  int v16; // eax
  int updated; // ebx
  __int64 v18; // rdx
  unsigned int v19; // edx
  int v20; // edx
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // rax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // r12
  __int64 v27; // rdx
  CUpdateInstallationResult *v28; // rbx
  __int64 (__fastcall *v29)(CUpdateInstallationResult *, BSTR *); // rdi
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v31; // r9d
  int v32; // eax
  unsigned __int64 v33; // r9
  int v34; // eax
  int v35; // eax
  const wchar_t *v36; // rdi
  const wchar_t *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r9
  const wchar_t *v40; // rax
  __int64 v41; // rdx
  const wchar_t *v42; // rax
  int v43; // ebx
  const wchar_t *v44; // rcx
  int v46; // [rsp+20h] [rbp-69h]
  __int64 v47; // [rsp+30h] [rbp-59h]
  unsigned int v48; // [rsp+50h] [rbp-39h]
  BSTR bstrString; // [rsp+60h] [rbp-29h] BYREF
  CUpdateInstallationResult *v50; // [rsp+68h] [rbp-21h] BYREF
  __int64 v51; // [rsp+70h] [rbp-19h] BYREF
  struct _GUID v52; // [rsp+78h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = (const struct tagInstallCallbackInfo *)((char *)a3 + 8);
  v6 = *(_DWORD *)a3;
  VariantInit(&pvarg);
  VariantInit(&pvarg);
  v7 = 0;
  if ( *((_DWORD *)this + 82) )
    goto LABEL_121;
  if ( v6 != 2 )
    goto LABEL_56;
  v8 = (unsigned int)(*((_DWORD *)a3 + 24) - 1);
  v9 = *((_DWORD *)a3 + 24) - 1;
  v48 = v9;
  v10 = *((_QWORD *)this + 77);
  if ( v10 )
  {
    v9 = *(_DWORD *)(v10 + 4 * v8);
    v48 = v9;
  }
  v11 = *((_QWORD *)this + 57);
  if ( v9 >= *(_DWORD *)(v11 + 100) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
      (const char *)0x80240007LL,
      v46);
    v7 = -2145124345;
    goto LABEL_121;
  }
  _mm_lfence();
  v12 = *(CUpdateInstallationResult **)(*(_QWORD *)(v11 + 88) + 8LL * v9);
  v50 = v12;
  if ( v12 )
  {
    v13 = *((_QWORD *)a3 + 14);
    if ( v13 )
    {
      v14 = (void **)((char *)v12 + 88);
      if ( *((_QWORD *)v12 + 11) )
      {
        SusFree(*v14);
        *v14 = 0;
      }
      v15 = DuplicateString<wchar_t const *,wchar_t *>(v13, v14);
      if ( v15 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstallationStatus.cpp",
          (const char *)(unsigned int)v15,
          v46);
      v12 = v50;
    }
    v5 = (const struct tagInstallCallbackInfo *)((char *)a3 + 8);
  }
  if ( *((_QWORD *)this + 77) )
  {
    LODWORD(bstrString) = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*((_QWORD *)v12 + 1) + 72LL))((__int64)v12 + 8, &bstrString);
    updated = v16;
    if ( v16 < 0 )
    {
      v18 = 649;
LABEL_105:
      v39 = (unsigned int)v16;
      goto LABEL_106;
    }
    if ( !(_DWORD)bstrString )
    {
      v19 = 0;
      if ( (_DWORD)v8 )
        v19 = *(_DWORD *)(*((_QWORD *)this + 77) + 4LL * (unsigned int)(v8 - 1)) + 1;
      v16 = CInstallationJob::SignalProgressChangedForSkippedUpdates(this, v19, v9);
      updated = v16;
      if ( v16 < 0 )
      {
        v18 = 658;
        goto LABEL_105;
      }
    }
  }
  if ( *((_DWORD *)a3 + 22) == 4 )
  {
LABEL_56:
    v35 = *((_DWORD *)a3 + 22);
    if ( v35 == 3 || ((v35 - 2) & 0xFFFFFFFD) == 0 )
    {
      v36 = L"Unknown";
      switch ( *((_DWORD *)this + 148) )
      {
        case 1:
          v37 = L"Install";
          break;
        case 2:
          v37 = L"Uninstall";
          break;
        case 4:
          v37 = L"Revert";
          break;
        case 8:
          v37 = L"Commit";
          break;
        default:
          v37 = L"Unknown";
          break;
      }
      WUTrace(0, 0, 0x10000, 4, 0, L" %ws ClientId = %ws", v37, *((_QWORD *)this + 73));
      v38 = *((_QWORD *)this + 77);
      if ( v38 )
        CInstallationJob::SignalProgressChangedForSkippedUpdates(
          this,
          *(_DWORD *)(v38 + 4LL * (unsigned int)(*((_DWORD *)this + 156) - 1)) + 1,
          *(_DWORD *)(*((_QWORD *)this + 56) + 124LL));
      v50 = 0;
      if ( *((_DWORD *)a3 + 22) == 2 )
      {
        v16 = CInstallationJob::ComputeOverallResult(this, (struct OperationResult *)&v50);
        updated = v16;
        if ( v16 < 0 )
        {
          v18 = 750;
          goto LABEL_105;
        }
        v43 = HIDWORD(v50);
        v41 = (unsigned int)v50;
      }
      else
      {
        if ( *((_DWORD *)a3 + 22) == 3 )
        {
          switch ( *((_DWORD *)this + 148) )
          {
            case 1:
              v42 = L"Install";
              break;
            case 2:
              v42 = L"Uninstall";
              break;
            case 4:
              v42 = L"Revert";
              break;
            case 8:
              v42 = L"Commit";
              break;
            default:
              v42 = L"Unknown";
              break;
          }
          WUTrace(0, 0, 0x10000, 4, 0, L"%ws call aborted", v42);
          v41 = 5;
        }
        else
        {
          if ( *((_DWORD *)a3 + 22) != 4 )
          {
            updated = -2145120257;
            v39 = 2149847039LL;
            v18 = 765;
LABEL_106:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
              (const char *)v39,
              v46);
            goto LABEL_122;
          }
          switch ( *((_DWORD *)this + 148) )
          {
            case 1:
              v40 = L"Install";
              break;
            case 2:
              v40 = L"Uninstall";
              break;
            case 4:
              v40 = L"Revert";
              break;
            case 8:
              v40 = L"Commit";
              break;
            default:
              v40 = L"Unknown";
              break;
          }
          WUTrace(0, 0, 0x10000, 4, 0, L"%ws call failed", v40);
          v41 = 6;
        }
        v43 = *((_DWORD *)a3 + 23);
      }
      *(_DWORD *)(*((_QWORD *)this + 57) + 72LL) = *((_DWORD *)a3 + 25) != 0;
      (*(void (__fastcall **)(char *, __int64, _QWORD))(*((_QWORD *)this + 5) + 8LL))(
        (char *)this + 40,
        v41,
        (unsigned int)v43);
      v44 = L"False";
      if ( *(_DWORD *)(*((_QWORD *)this + 57) + 72LL) )
        v44 = L"True";
      WUTrace(0, 0, 0x10000, 4, 0, L"Reboot required = %ws", v44);
      if ( v43 < 0 )
      {
        LODWORD(v47) = v43;
        WUTrace(0, 0, 0x10000, 3, 0, L"Call error code = 0x%08lX", v47);
      }
      switch ( *((_DWORD *)this + 148) )
      {
        case 1:
          v36 = L"Install";
          break;
        case 2:
          v36 = L"Uninstall";
          break;
        case 4:
          v36 = L"Revert";
          break;
        case 8:
          v36 = L"Commit";
          break;
      }
      WUTrace(0, 0, 0x10000, 4, 0, L"* END *   %ws ClientId = %ws", v36, *((_QWORD *)this + 73));
    }
LABEL_121:
    updated = v7;
    goto LABEL_122;
  }
  if ( this != (CInstallationJob *)-224LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  updated = CUpdateInstallationResult::SetStatus(v50, v5);
  if ( updated >= 0 )
  {
    *((_DWORD *)this + 116) = *(_DWORD *)a3;
    *(_OWORD *)((char *)this + 552) = *(_OWORD *)((char *)a3 + 88);
    *((_DWORD *)this + 142) = *((_DWORD *)a3 + 26);
    *((_QWORD *)this + 72) = *((_QWORD *)a3 + 14);
    FreeObject((CInstallationJob *)((char *)this + 472), v20);
    updated = CopyPerUpdateInstallStatus(v5, (CInstallationJob *)((char *)this + 472), 0);
    if ( updated < 0 )
    {
      v21 = 682;
      goto LABEL_29;
    }
    v23 = *((_DWORD *)a3 + 22);
    if ( v23 == 3 || v23 <= 9 && (v24 = 980, _bittest(&v24, v23)) )
    {
      v50 = 0;
      v51 = 0;
      bstrString = 0;
      v52 = 0;
      v25 = *((_QWORD *)this + 56);
      if ( (unsigned int)v8 >= *(_DWORD *)(v25 + 124) )
      {
        updated = -2145124345;
        v27 = 691;
        goto LABEL_64;
      }
      _mm_lfence();
      v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*(_QWORD *)(v25 + 112) + 8 * v8);
      updated = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), CUpdateInstallationResult **))(*v26)[19])(
                  v26,
                  &v50);
      if ( updated < 0 )
      {
        v27 = 692;
LABEL_64:
        v33 = (unsigned int)updated;
        goto LABEL_65;
      }
      v28 = v50;
      v29 = *(__int64 (__fastcall **)(CUpdateInstallationResult *, BSTR *))(*(_QWORD *)v50 + 64LL);
      SysFreeString(bstrString);
      bstrString = 0;
      updated = v29(v28, &bstrString);
      if ( updated < 0 )
      {
        v27 = 693;
        goto LABEL_64;
      }
      v30 = **v26;
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      updated = v30(v26, &GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6, &v51);
      if ( updated < 0 )
      {
        v27 = 694;
        goto LABEL_64;
      }
      updated = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v51 + 24LL))(v51, &v52);
      if ( updated < 0 )
      {
        v27 = 695;
        goto LABEL_64;
      }
      WUTrace(
        0,
        0,
        0x10000,
        4,
        0,
        L"Deployment callback complete for UpdateID = %ws, callback code = %d, CallbackInfo cookie length = %d");
      v31 = *((_DWORD *)this + 134);
      if ( v31 )
      {
        v32 = PersistUpdateCallbackInfo(&v52, bstrString, *((const void **)this + 68), v31);
        updated = v32;
        if ( v32 < 0 )
        {
          v33 = (unsigned int)v32;
          v27 = 711;
LABEL_65:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
            (const char *)v33,
            v46);
          SysFreeString(bstrString);
          bstrString = 0;
          if ( v51 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
            v51 = 0;
          }
          if ( v50 )
            (*(void (__fastcall **)(CUpdateInstallationResult *))(*(_QWORD *)v50 + 16LL))(v50);
          goto LABEL_69;
        }
      }
      SysFreeString(bstrString);
      bstrString = 0;
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      if ( v50 )
        (*(void (__fastcall **)(CUpdateInstallationResult *))(*(_QWORD *)v50 + 16LL))(v50);
    }
    *((_DWORD *)this + 140) = v48 + 1;
    v34 = CInstallationJob::SignalProgressChanged(this, (CInstallationJob *)((char *)this + 464), 1);
    updated = v34;
    if ( v34 < 0 )
    {
      v22 = (unsigned int)v34;
      v21 = 718;
      goto LABEL_30;
    }
    if ( this != (CInstallationJob *)-224LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    goto LABEL_56;
  }
  v21 = 668;
LABEL_29:
  v22 = (unsigned int)updated;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
    (const char *)v22,
    v46);
LABEL_69:
  if ( this != (CInstallationJob *)-224LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
LABEL_122:
  VariantClear(&pvarg);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180024568  mov     [rsp-8+arg_8], rbx
0x18002456d  push    rbp
0x18002456e  push    rsi
0x18002456f  push    rdi
0x180024570  push    r12
0x180024572  push    r13
0x180024574  push    r14
0x180024576  push    r15
0x180024578  lea     rbp, [rsp-27h]
0x18002457d  sub     rsp, 0B0h
0x180024584  mov     rax, cs:__security_cookie
0x18002458b  xor     rax, rsp
0x18002458e  mov     [rbp+57h+var_40], rax
0x180024592  mov     r15, r8
0x180024595  mov     r14, rcx
0x180024598  lea     r12, [r8+8]
0x18002459c  mov     ebx, [r8]
0x18002459f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800245a3  call    cs:__imp_VariantInit
0x1800245a9  nop
0x1800245aa  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800245ae  call    cs:__imp_VariantInit
0x1800245b4  xor     esi, esi
0x1800245b6  cmp     [r14+148h], esi
0x1800245bd  jnz     loc_180024D24
0x1800245c3  cmp     ebx, 2
0x1800245c6  jnz     loc_180024979
0x1800245cc  mov     edi, [r15+60h]
0x1800245d0  dec     edi
0x1800245d2  mov     r13d, edi
0x1800245d5  mov     [rbp+57h+var_90], edi
0x1800245d8  mov     rcx, [r14+268h]
0x1800245df  test    rcx, rcx
0x1800245e2  jz      short loc_1800245EC
0x1800245e4  mov     r13d, [rcx+rdi*4]
0x1800245e8  mov     [rbp+57h+var_90], r13d
0x1800245ec  mov     rax, [r14+1C8h]
0x1800245f3  cmp     r13d, [rax+64h]
0x1800245f7  jnb     loc_180024A59
0x1800245fd  lfence
0x180024600  mov     ecx, r13d
0x180024603  mov     rax, [rax+58h]
0x180024607  mov     rax, [rax+rcx*8]
0x18002460b  mov     [rbp+57h+var_78], rax
0x18002460f  test    rax, rax
0x180024612  jz      short loc_180024660
0x180024614  mov     r12, [r15+70h]
0x180024618  test    r12, r12
0x18002461b  jz      short loc_18002465C
0x18002461d  lea     rbx, [rax+58h]
0x180024621  cmp     [rbx], rsi
0x180024624  jz      short loc_180024631
0x180024626  mov     rcx, [rbx]; lpMem
0x180024629  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002462e  mov     [rbx], rsi
0x180024631  mov     rdx, rbx
0x180024634  mov     rcx, r12
0x180024637  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18002463c  test    eax, eax
0x18002463e  jns     short loc_180024658
0x180024640  mov     rcx, [rbp+5Fh]; this
0x180024644  mov     r9d, eax; char *
0x180024647  lea     r8, aCW1SSrcClientC_19; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18002464e  mov     edx, 0BFh; void *
0x180024653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024658  mov     rax, [rbp+57h+var_78]
0x18002465c  lea     r12, [r15+8]
0x180024660  cmp     [r14+268h], rsi
0x180024667  jz      short loc_1800246C5
0x180024669  mov     dword ptr [rbp+57h+bstrString], esi
0x18002466c  lea     rcx, [rax+8]
0x180024670  mov     rax, [rcx]
0x180024673  lea     rdx, [rbp+57h+bstrString]
0x180024677  mov     rax, [rax+48h]
0x18002467b  call    _guard_dispatch_icall
0x180024680  mov     ebx, eax
0x180024682  test    eax, eax
0x180024684  jns     short loc_180024690
0x180024686  mov     edx, 289h
0x18002468b  jmp     loc_180024C02
0x180024690  cmp     dword ptr [rbp+57h+bstrString], esi
0x180024693  jnz     short loc_1800246C5
0x180024695  mov     edx, esi
0x180024697  test    edi, edi
0x180024699  jz      short loc_1800246AA
0x18002469b  lea     ecx, [rdi-1]
0x18002469e  mov     rax, [r14+268h]
0x1800246a5  mov     edx, [rax+rcx*4]
0x1800246a8  inc     edx; unsigned int
0x1800246aa  mov     r8d, r13d; unsigned int
0x1800246ad  mov     rcx, r14; this
0x1800246b0  call    ?SignalProgressChangedForSkippedUpdates@CInstallationJob@@IEAAJKK@Z; CInstallationJob::SignalProgressChangedForSkippedUpdates(ulong,ulong)
0x1800246b5  mov     ebx, eax
0x1800246b7  test    eax, eax
0x1800246b9  jns     short loc_1800246C5
0x1800246bb  mov     edx, 292h
0x1800246c0  jmp     loc_180024C02
0x1800246c5  cmp     dword ptr [r15+58h], 4
0x1800246ca  jz      loc_180024979
0x1800246d0  lea     r13, [r14+0E0h]
0x1800246d7  test    r13, r13
0x1800246da  jz      short loc_1800246E6
0x1800246dc  lea     rcx, [r13+8]; lpCriticalSection
0x1800246e0  call    cs:__imp_EnterCriticalSection
0x1800246e6  mov     [rbp+57h+var_88], r13
0x1800246ea  mov     rdx, r12; struct tagPerUpdateInstallStatus *
0x1800246ed  mov     rcx, [rbp+57h+var_78]; this
0x1800246f1  call    ?SetStatus@CUpdateInstallationResult@@QEAAJAEBUtagPerUpdateInstallStatus@@@Z; CUpdateInstallationResult::SetStatus(tagPerUpdateInstallStatus const &)
0x1800246f6  mov     ebx, eax
0x1800246f8  test    eax, eax
0x1800246fa  jns     short loc_180024703
0x1800246fc  mov     edx, 29Ch
0x180024701  jmp     short loc_180024757
0x180024703  lea     rcx, [r14+1D0h]
0x18002470a  mov     eax, [r15]
0x18002470d  mov     [rcx], eax
0x18002470f  movups  xmm0, xmmword ptr [r15+58h]
0x180024714  movups  xmmword ptr [r14+228h], xmm0
0x18002471c  mov     eax, [r15+68h]
0x180024720  mov     [r14+238h], eax
0x180024727  mov     rax, [r15+70h]
0x18002472b  mov     [r14+240h], rax
0x180024732  lea     rbx, [rcx+8]
0x180024736  mov     rcx, rbx; struct tagPerUpdateInstallStatus *
0x180024739  call    ?FreeObject@@YAXPEAUtagPerUpdateInstallStatus@@H@Z; FreeObject(tagPerUpdateInstallStatus *,int)
0x18002473e  xor     r8d, r8d; bool
0x180024741  mov     rdx, rbx; struct tagPerUpdateInstallStatus *
0x180024744  mov     rcx, r12; struct tagPerUpdateInstallStatus *
0x180024747  call    ?CopyPerUpdateInstallStatus@@YAJAEBUtagPerUpdateInstallStatus@@AEAU1@_N@Z; CopyPerUpdateInstallStatus(tagPerUpdateInstallStatus const &,tagPerUpdateInstallStatus &,bool)
0x18002474c  mov     ebx, eax
0x18002474e  test    eax, eax
0x180024750  jns     short loc_18002476F
0x180024752  mov     edx, 2AAh; void *
0x180024757  mov     r9d, ebx; char *
0x18002475a  lea     r8, aCW1SSrcClientC_9; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ins"...
0x180024761  mov     rcx, [rbp+5Fh]; this
0x180024765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002476a  jmp     loc_180024A41
0x18002476f  mov     eax, [r15+58h]
0x180024773  cmp     eax, 3
0x180024776  jz      short loc_18002478F
0x180024778  cmp     eax, 9
0x18002477b  ja      loc_180024936
0x180024781  mov     ecx, 3D4h
0x180024786  bt      ecx, eax
0x180024789  jnb     loc_180024936
0x18002478f  mov     [rbp+57h+var_78], rsi
0x180024793  mov     [rbp+57h+var_70], rsi
0x180024797  mov     [rbp+57h+bstrString], rsi
0x18002479b  xorps   xmm0, xmm0
0x18002479e  movups  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x1800247a2  mov     rax, [r14+1C0h]
0x1800247a9  cmp     edi, [rax+7Ch]
0x1800247ac  jnb     loc_1800249E6
0x1800247b2  lfence
0x1800247b5  mov     rax, [rax+70h]
0x1800247b9  mov     r12, [rax+rdi*8]
0x1800247bd  mov     rax, [r12]
0x1800247c1  lea     rdx, [rbp+57h+var_78]
0x1800247c5  mov     rcx, r12
0x1800247c8  mov     rax, [rax+98h]
0x1800247cf  call    _guard_dispatch_icall
0x1800247d4  mov     ebx, eax
0x1800247d6  test    eax, eax
0x1800247d8  jns     short loc_1800247E4
0x1800247da  mov     edx, 2B4h
0x1800247df  jmp     loc_1800249F0
0x1800247e4  mov     rbx, [rbp+57h+var_78]
0x1800247e8  mov     rax, [rbx]
0x1800247eb  mov     rdi, [rax+40h]
0x1800247ef  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800247f3  call    cs:__imp_SysFreeString
0x1800247f9  mov     [rbp+57h+bstrString], rsi
0x1800247fd  lea     rdx, [rbp+57h+bstrString]
0x180024801  mov     rcx, rbx
0x180024804  mov     rax, rdi
0x180024807  call    _guard_dispatch_icall
0x18002480c  mov     ebx, eax
0x18002480e  test    eax, eax
0x180024810  jns     short loc_18002481C
0x180024812  mov     edx, 2B5h
0x180024817  jmp     loc_1800249F0
0x18002481c  mov     rax, [r12]
0x180024820  mov     rbx, [rax]
0x180024823  mov     rcx, [rbp+57h+var_70]
0x180024827  test    rcx, rcx
0x18002482a  jz      short loc_18002483C
0x18002482c  mov     rdx, [rcx]
0x18002482f  mov     rax, [rdx+10h]
0x180024833  call    _guard_dispatch_icall
0x180024838  mov     [rbp+57h+var_70], rsi
0x18002483c  lea     r8, [rbp+57h+var_70]
0x180024840  lea     rdx, _GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6
0x180024847  mov     rcx, r12
0x18002484a  mov     rax, rbx
0x18002484d  call    _guard_dispatch_icall
0x180024852  mov     ebx, eax
0x180024854  test    eax, eax
0x180024856  jns     short loc_180024862
0x180024858  mov     edx, 2B6h
0x18002485d  jmp     loc_1800249F0
0x180024862  mov     rcx, [rbp+57h+var_70]
0x180024866  mov     rax, [rcx]
0x180024869  lea     rdx, [rbp+57h+var_68]
0x18002486d  mov     rax, [rax+18h]
0x180024871  call    _guard_dispatch_icall
0x180024876  mov     ebx, eax
0x180024878  test    eax, eax
0x18002487a  jns     short loc_180024886
0x18002487c  mov     edx, 2B7h
0x180024881  jmp     loc_1800249F0
0x180024886  mov     eax, [r14+218h]
0x18002488d  mov     [rsp+0E0h+var_A0], eax
0x180024891  mov     eax, [r15+58h]
0x180024895  mov     dword ptr [rsp+0E0h+var_A8], eax
0x180024899  mov     rax, [rbp+57h+bstrString]
0x18002489d  mov     [rsp+0E0h+var_B0], rax
0x1800248a2  lea     rax, aDeploymentCall; "Deployment callback complete for Update"...
0x1800248a9  mov     [rsp+0E0h+var_B8], rax
0x1800248ae  mov     qword ptr [rsp+0E0h+var_C0], rsi; int
0x1800248b3  xor     edx, edx
0x1800248b5  xor     ecx, ecx
0x1800248b7  lea     r9d, [rdx+4]
0x1800248bb  mov     r8d, 10000h
0x1800248c1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800248c6  mov     r9d, [r14+218h]; unsigned int
0x1800248cd  test    r9d, r9d
0x1800248d0  jz      short loc_1800248F9
0x1800248d2  mov     r8, [r14+220h]; void *
0x1800248d9  mov     rdx, [rbp+57h+bstrString]; wchar_t *
0x1800248dd  lea     rcx, [rbp+57h+var_68]; struct _GUID *
0x1800248e1  call    ?PersistUpdateCallbackInfo@@YAJAEBU_GUID@@PEB_WPEBXKH@Z; PersistUpdateCallbackInfo(_GUID const &,wchar_t const *,void const *,ulong,int)
0x1800248e6  mov     ebx, eax
0x1800248e8  test    eax, eax
0x1800248ea  jns     short loc_1800248F9
0x1800248ec  mov     r9d, eax
0x1800248ef  mov     edx, 2C7h
0x1800248f4  jmp     loc_1800249F3
0x1800248f9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800248fd  call    cs:__imp_SysFreeString
0x180024903  mov     [rbp+57h+bstrString], rsi
0x180024907  mov     rcx, [rbp+57h+var_70]
0x18002490b  test    rcx, rcx
0x18002490e  jz      short loc_180024920
0x180024910  mov     rax, [rcx]
0x180024913  mov     rax, [rax+10h]
0x180024917  call    _guard_dispatch_icall
0x18002491c  mov     [rbp+57h+var_70], rsi
0x180024920  mov     rcx, [rbp+57h+var_78]
0x180024924  test    rcx, rcx
0x180024927  jz      short loc_180024936
0x180024929  mov     rax, [rcx]
0x18002492c  mov     rax, [rax+10h]
0x180024930  call    _guard_dispatch_icall
0x180024935  nop
0x180024936  mov     eax, [rbp+57h+var_90]
0x180024939  inc     eax
0x18002493b  mov     [r14+230h], eax
0x180024942  mov     r8d, 1; int
0x180024948  lea     rdx, [r14+1D0h]; struct tagInstallCallbackInfo *
0x18002494f  mov     rcx, r14; this
0x180024952  call    ?SignalProgressChanged@CInstallationJob@@IEAAJAEBUtagInstallCallbackInfo@@H@Z; CInstallationJob::SignalProgressChanged(tagInstallCallbackInfo const &,int)
0x180024957  mov     ebx, eax
0x180024959  test    eax, eax
0x18002495b  jns     short loc_18002496A
0x18002495d  mov     r9d, eax
0x180024960  mov     edx, 2CEh
0x180024965  jmp     loc_18002475A
0x18002496a  test    r13, r13
0x18002496d  jz      short loc_180024979
0x18002496f  lea     rcx, [r13+8]; lpCriticalSection
0x180024973  call    cs:__imp_LeaveCriticalSection
0x180024979  mov     eax, [r15+58h]
0x18002497d  cmp     eax, 3
0x180024980  jz      short loc_180024990
0x180024982  add     eax, 0FFFFFFFEh
0x180024985  test    eax, 0FFFFFFFDh
0x18002498a  jnz     loc_180024D24
0x180024990  mov     rdx, [r14+248h]
0x180024997  mov     ecx, [r14+250h]
0x18002499e  lea     rdi, aUnknown_0; "Unknown"
0x1800249a5  lea     rbx, aRevert; "Revert"
0x1800249ac  lea     r12, aInstall; "Install"
0x1800249b3  lea     r13, aUninstall; "Uninstall"
0x1800249ba  sub     ecx, 1
0x1800249bd  jz      loc_180024A90
0x1800249c3  sub     ecx, 1
0x1800249c6  jz      loc_180024A8B
0x1800249cc  sub     ecx, 2
0x1800249cf  jz      loc_180024A86
0x1800249d5  cmp     ecx, 4
0x1800249d8  jz      loc_180024A7D
0x1800249de  mov     rax, rdi
0x1800249e1  jmp     loc_180024A93
0x1800249e6  mov     ebx, 80240007h
0x1800249eb  mov     edx, 2B3h; void *
0x1800249f0  mov     r9d, ebx; char *
0x1800249f3  mov     rcx, [rbp+5Fh]; this
0x1800249f7  lea     r8, aCW1SSrcClientC_9; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ins"...
0x1800249fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
