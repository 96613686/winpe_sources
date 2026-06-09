# CSpp::SetDiffArea(ushort const *,ulong)

- ea: `0x18000f270`
- end: `0x18000f757`
- name: `?SetDiffArea@CSpp@@UEAAJPEBGK@Z`
- size: `1255`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x18000f270`
- `0x180019780`
- `0x18001b70c`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000f3a6`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000f3a6`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x18000f3f6`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x18000f3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f44b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f44b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f707`

## pseudocode

```c
__int64 __fastcall CSpp::SetDiffArea(CSpp *this, const unsigned __int16 *a2, unsigned int a3)
{
  __int16 v5; // ax
  unsigned __int16 v6; // dx
  __int64 v7; // rcx
  unsigned int v8; // esi
  __int16 v9; // r12
  int v10; // eax
  CSpp *v11; // rcx
  unsigned int v12; // eax
  ULONGLONG v13; // rbx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rbx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  int LastFailureAsHRESULT; // [rsp+30h] [rbp-99h] BYREF
  __int16 v22; // [rsp+34h] [rbp-95h]
  __int16 v23; // [rsp+36h] [rbp-93h]
  __int64 v24; // [rsp+68h] [rbp-61h] BYREF
  __int64 v25; // [rsp+70h] [rbp-59h] BYREF
  LPVOID pv[2]; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int16 *v27[2]; // [rsp+88h] [rbp-41h]
  __int128 v28; // [rsp+98h] [rbp-31h]
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+A8h] [rbp-21h] BYREF
  LPCWSTR lpDirectoryName[2]; // [rsp+B0h] [rbp-19h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+C0h] [rbp-9h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+C8h] [rbp-1h] BYREF
  GUID v33; // [rsp+D0h] [rbp+7h] BYREF
  __int128 v34[4]; // [rsp+E0h] [rbp+17h] BYREF
  int v35; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned __int64 v36; // [rsp+148h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSpp::SetDiffArea", 11534, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v24);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v25);
  lpDirectoryName[0] = &FileName;
  v35 = 0;
  v5 = 11552;
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  lpDirectoryName[1] = 0;
  v36 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  if ( !a2 || (v22 = 11552, v5 = 11553, a3 > 0x64) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_50;
  }
  LastFailureAsHRESULT = 0;
  v22 = 11553;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpDirectoryName, a2);
  v5 = 11555;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_50;
  v22 = 11555;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)lpDirectoryName, v6);
  v5 = 11556;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_50;
  v22 = 11556;
  if ( !GetDiskFreeSpaceExW(
          lpDirectoryName[0],
          &FreeBytesAvailableToCaller,
          &TotalNumberOfBytes,
          &TotalNumberOfFreeBytes) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v5 = 11558;
LABEL_50:
    v23 = v5;
    goto LABEL_51;
  }
  LastFailureAsHRESULT = 0;
  v33 = IID_IVssDifferentialSoftwareSnapshotMgmt2;
  v34[0] = xmmword_18003B620;
  v22 = 11558;
  LastFailureAsHRESULT = GetProviderMgmtInterfaceInternal(v34, &v33, &v24);
  v5 = 11562;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_50;
  v22 = 11562;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, LPCWSTR, __int64 *))(*(_QWORD *)v24 + 48LL))(
                           v24,
                           lpDirectoryName[0],
                           &v25);
  v5 = 11563;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_50;
  v8 = 0;
  v22 = 11563;
  v9 = 11574;
  while ( 1 )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v27[0]);
    v35 = 0;
    *(_OWORD *)pv = 0;
    *(_OWORD *)v27 = 0;
    v28 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v25 + 24LL))(v25, 1, pv, &v35);
    LastFailureAsHRESULT = v10;
    if ( v10 < 0 )
      goto LABEL_48;
    v22 = 11574;
    if ( v10 == 1 )
      break;
    if ( v35 == 1 && LODWORD(pv[0]) == 3 )
      ++v8;
  }
  v12 = 1;
  if ( a3 )
    v12 = a3;
  v13 = TotalNumberOfBytes.QuadPart * v12;
  LastFailureAsHRESULT = CSpp::_IsServerSku(v11);
  if ( LastFailureAsHRESULT < 0 )
  {
    v5 = 11594;
    goto LABEL_50;
  }
  v22 = 11594;
  v14 = v13 / 0x64;
  if ( v8 )
  {
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 40LL))(v25);
    if ( LastFailureAsHRESULT < 0 )
    {
      v5 = 11616;
      goto LABEL_50;
    }
    v15 = v14 / v8;
    v22 = 11616;
    v9 = 11625;
    while ( 1 )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      CoTaskMemFree(v27[0]);
      v35 = 0;
      *(_OWORD *)pv = 0;
      *(_OWORD *)v27 = 0;
      v28 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v25 + 24LL))(v25, 1, pv, &v35);
      LastFailureAsHRESULT = v16;
      if ( v16 < 0 )
        break;
      v22 = 11625;
      if ( v16 == 1 )
        goto LABEL_47;
      LastFailureAsHRESULT = CSpp::_GetMinDiffAreaSize(v27[0], &v36);
      if ( LastFailureAsHRESULT < 0 )
      {
        v23 = 11632;
        goto LABEL_51;
      }
      v22 = 11632;
      if ( v15 < v36 )
        v15 = v36;
      if ( LODWORD(pv[0]) == 3 )
      {
        LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, _DWORD))(*(_QWORD *)v24 + 72LL))(
                                 v24,
                                 a2,
                                 v27[0],
                                 v15,
                                 0);
        if ( LastFailureAsHRESULT < 0 )
        {
          v23 = 11642;
          goto LABEL_51;
        }
        v22 = 11642;
      }
    }
LABEL_48:
    v23 = v9;
    goto LABEL_51;
  }
  if ( LastFailureAsHRESULT )
  {
    LastFailureAsHRESULT = CSpp::_GetMinDiffAreaSize(a2, &v36);
    v5 = 11649;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_50;
    v22 = 11649;
    if ( v14 < v36 )
      v14 = v36;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, _DWORD))(*(_QWORD *)v24 + 72LL))(
                             v24,
                             a2,
                             a2,
                             v14,
                             0);
    if ( LastFailureAsHRESULT < 0 )
    {
      v5 = 11656;
      goto LABEL_50;
    }
  }
  else
  {
    LastFailureAsHRESULT = CSpp::_GetMinDiffAreaSize(a2, &v36);
    v5 = 11599;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_50;
    v22 = 11599;
    if ( v14 < v36 )
      v14 = v36;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64))(*(_QWORD *)v24 + 24LL))(
                             v24,
                             a2,
                             a2,
                             v14);
    if ( LastFailureAsHRESULT < 0 )
    {
      v5 = 11608;
      goto LABEL_50;
    }
  }
LABEL_47:
  LastFailureAsHRESULT = 0;
  v22 = 11660;
LABEL_51:
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v27[0]);
  v27[0] = 0;
  v17 = LastFailureAsHRESULT;
  CBsString::_Release((unsigned __int16 **)lpDirectoryName);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v18, v19);
  return v17;
}

```

## disassembly

```asm
0x18000f270  mov     [rsp-8+arg_0], rbx
0x18000f275  push    rbp
0x18000f276  push    rsi
0x18000f277  push    rdi
0x18000f278  push    r12
0x18000f27a  push    r13
0x18000f27c  push    r14
0x18000f27e  push    r15
0x18000f280  lea     rbp, [rsp-27h]
0x18000f285  sub     rsp, 0F0h
0x18000f28c  mov     ebx, r8d
0x18000f28f  mov     rdi, rdx
0x18000f292  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f299  lea     rax, WPP_GLOBAL_Control
0x18000f2a0  cmp     rcx, rax
0x18000f2a3  jz      short loc_18000F2C3
0x18000f2a5  test    dword ptr [rcx+1Ch], 20000000h
0x18000f2ac  jz      short loc_18000F2C3
0x18000f2ae  mov     rcx, [rcx+10h]
0x18000f2b2  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000f2b9  mov     edx, 0C8h
0x18000f2be  call    WPP_SF_
0x18000f2c3  mov     r15d, 1
0x18000f2c9  lea     rdx, aCsppSetdiffare; "CSpp::SetDiffArea"
0x18000f2d0  mov     r9d, r15d; unsigned __int16
0x18000f2d3  lea     rcx, [rsp+120h+var_F0]; this
0x18000f2d8  mov     r8d, 2D0Eh; unsigned __int16
0x18000f2de  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f2e3  lea     rcx, [rbp+57h+var_B8]
0x18000f2e7  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000f2ec  lea     rcx, [rbp+57h+var_B0]
0x18000f2f0  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000f2f5  xor     r14d, r14d
0x18000f2f8  lea     rax, FileName
0x18000f2ff  mov     [rbp+57h+lpDirectoryName], rax
0x18000f303  xorps   xmm0, xmm0
0x18000f306  mov     [rbp+57h+arg_8], r14d
0x18000f30a  mov     eax, 2D20h
0x18000f30f  mov     qword ptr [rbp+57h+FreeBytesAvailableToCaller], r14
0x18000f313  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r14
0x18000f317  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], r14
0x18000f31b  mov     [rbp+57h+var_68], r14
0x18000f31f  mov     [rbp+57h+arg_18], r14
0x18000f323  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18000f327  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x18000f32b  movups  [rbp+57h+var_88], xmm0
0x18000f32f  test    rdi, rdi
0x18000f332  jz      loc_18000F6E8
0x18000f338  mov     [rsp+120h+var_EC], ax
0x18000f33d  mov     eax, 2D21h
0x18000f342  cmp     ebx, 64h ; 'd'
0x18000f345  ja      loc_18000F6E8
0x18000f34b  mov     rdx, rdi; unsigned __int16 *
0x18000f34e  mov     [rsp+120h+var_F0], r14d
0x18000f353  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x18000f357  mov     [rsp+120h+var_EC], ax
0x18000f35c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000f361  mov     [rsp+120h+var_F0], eax
0x18000f365  test    eax, eax
0x18000f367  mov     eax, 2D23h
0x18000f36c  js      loc_18000F6F0
0x18000f372  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x18000f376  mov     [rsp+120h+var_EC], ax
0x18000f37b  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000f380  mov     [rsp+120h+var_F0], eax
0x18000f384  test    eax, eax
0x18000f386  mov     eax, 2D24h
0x18000f38b  js      loc_18000F6F0
0x18000f391  mov     rcx, [rbp+57h+lpDirectoryName]; lpDirectoryName
0x18000f395  lea     r9, [rbp+57h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18000f399  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18000f39d  mov     [rsp+120h+var_EC], ax
0x18000f3a2  lea     rdx, [rbp+57h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18000f3a6  call    cs:__imp_GetDiskFreeSpaceExW
0x18000f3ac  test    eax, eax
0x18000f3ae  jnz     short loc_18000F3C3
0x18000f3b0  call    GetLastFailureAsHRESULT
0x18000f3b5  mov     [rsp+120h+var_F0], eax
0x18000f3b9  mov     eax, 2D26h
0x18000f3be  jmp     loc_18000F6F0
0x18000f3c3  movups  xmm1, xmmword ptr cs:IID_IVssDifferentialSoftwareSnapshotMgmt2.Data1
0x18000f3ca  mov     eax, 2D26h
0x18000f3cf  lea     r8, [rbp+57h+var_B8]
0x18000f3d3  movups  xmm0, cs:xmmword_18003B620
0x18000f3da  lea     rdx, [rbp+57h+var_50]
0x18000f3de  mov     [rsp+120h+var_F0], r14d
0x18000f3e3  lea     rcx, [rbp+57h+var_40]
0x18000f3e7  movdqa  [rbp+57h+var_50], xmm1
0x18000f3ec  movdqa  [rbp+57h+var_40], xmm0
0x18000f3f1  mov     [rsp+120h+var_EC], ax
0x18000f3f6  call    cs:__imp_GetProviderMgmtInterfaceInternal
0x18000f3fc  mov     [rsp+120h+var_F0], eax
0x18000f400  test    eax, eax
0x18000f402  mov     eax, 2D2Ah
0x18000f407  js      loc_18000F6F0
0x18000f40d  mov     rcx, [rbp+57h+var_B8]
0x18000f411  lea     r8, [rbp+57h+var_B0]
0x18000f415  mov     rdx, [rbp+57h+lpDirectoryName]
0x18000f419  mov     [rsp+120h+var_EC], ax
0x18000f41e  mov     rax, [rcx]
0x18000f421  mov     rax, [rax+30h]
0x18000f425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f42a  mov     [rsp+120h+var_F0], eax
0x18000f42e  test    eax, eax
0x18000f430  mov     eax, 2D2Bh
0x18000f435  js      loc_18000F6F0
0x18000f43b  mov     esi, r14d
0x18000f43e  mov     [rsp+120h+var_EC], ax
0x18000f443  lea     r12d, [rax+0Bh]
0x18000f447  mov     rcx, [rbp+57h+pv+8]; pv
0x18000f44b  call    cs:__imp_CoTaskMemFree
0x18000f451  mov     rcx, [rbp+57h+var_98]; pv
0x18000f455  mov     [rbp+57h+pv+8], r14
0x18000f459  call    cs:__imp_CoTaskMemFree
0x18000f45f  mov     rcx, [rbp+57h+var_B0]
0x18000f463  lea     r9, [rbp+57h+arg_8]
0x18000f467  xorps   xmm0, xmm0
0x18000f46a  mov     [rbp+57h+arg_8], r14d
0x18000f46e  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18000f472  lea     r8, [rbp+57h+pv]
0x18000f476  mov     edx, r15d
0x18000f479  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x18000f47d  movups  [rbp+57h+var_88], xmm0
0x18000f481  mov     rax, [rcx]
0x18000f484  mov     rax, [rax+18h]
0x18000f488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f48d  mov     [rsp+120h+var_F0], eax
0x18000f491  test    eax, eax
0x18000f493  js      loc_18000F6E0
0x18000f499  mov     [rsp+120h+var_EC], r12w
0x18000f49f  cmp     eax, r15d
0x18000f4a2  jz      short loc_18000F4B5
0x18000f4a4  cmp     [rbp+57h+arg_8], r15d
0x18000f4a8  jnz     short loc_18000F447
0x18000f4aa  cmp     dword ptr [rbp+57h+pv], 3
0x18000f4ae  jnz     short loc_18000F447
0x18000f4b0  add     esi, r15d
0x18000f4b3  jmp     short loc_18000F447
0x18000f4b5  cmp     ebx, r15d
0x18000f4b8  mov     eax, r15d
0x18000f4bb  cmovnb  eax, ebx
0x18000f4be  mov     ebx, eax
0x18000f4c0  imul    rbx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x18000f4c5  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x18000f4ca  mov     [rsp+120h+var_F0], eax
0x18000f4ce  mov     ecx, eax
0x18000f4d0  test    eax, eax
0x18000f4d2  jns     short loc_18000F4DE
0x18000f4d4  mov     eax, 2D4Ah
0x18000f4d9  jmp     loc_18000F6F0
0x18000f4de  mov     rax, 47AE147AE147AE15h
0x18000f4e8  mul     rbx
0x18000f4eb  mov     eax, 2D4Ah
0x18000f4f0  sub     rbx, rdx
0x18000f4f3  mov     [rsp+120h+var_EC], ax
0x18000f4f8  shr     rbx, 1
0x18000f4fb  add     rbx, rdx
0x18000f4fe  shr     rbx, 6
0x18000f502  test    esi, esi
0x18000f504  jnz     loc_18000F5C0
0x18000f50a  test    ecx, ecx
0x18000f50c  lea     rdx, [rbp+57h+arg_18]; unsigned __int64 *
0x18000f510  mov     rcx, rdi; unsigned __int16 *
0x18000f513  jnz     short loc_18000F568
0x18000f515  call    ?_GetMinDiffAreaSize@CSpp@@CAJPEBGPEA_K@Z; CSpp::_GetMinDiffAreaSize(ushort const *,unsigned __int64 *)
0x18000f51a  mov     [rsp+120h+var_F0], eax
0x18000f51e  test    eax, eax
0x18000f520  mov     eax, 2D4Fh
0x18000f525  js      loc_18000F6F0
0x18000f52b  mov     rcx, [rbp+57h+var_B8]
0x18000f52f  mov     r8, rdi
0x18000f532  cmp     rbx, [rbp+57h+arg_18]
0x18000f536  mov     rdx, rdi
0x18000f539  mov     [rsp+120h+var_EC], ax
0x18000f53e  cmovb   rbx, [rbp+57h+arg_18]
0x18000f543  mov     rax, [rcx]
0x18000f546  mov     r9, rbx
0x18000f549  mov     rax, [rax+18h]
0x18000f54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f552  mov     [rsp+120h+var_F0], eax
0x18000f556  test    eax, eax
0x18000f558  jns     loc_18000F6CF
0x18000f55e  mov     eax, 2D58h
0x18000f563  jmp     loc_18000F6F0
0x18000f568  call    ?_GetMinDiffAreaSize@CSpp@@CAJPEBGPEA_K@Z; CSpp::_GetMinDiffAreaSize(ushort const *,unsigned __int64 *)
0x18000f56d  mov     [rsp+120h+var_F0], eax
0x18000f571  test    eax, eax
0x18000f573  mov     eax, 2D81h
0x18000f578  js      loc_18000F6F0
0x18000f57e  mov     rcx, [rbp+57h+var_B8]
0x18000f582  mov     r8, rdi
0x18000f585  cmp     rbx, [rbp+57h+arg_18]
0x18000f589  mov     rdx, rdi
0x18000f58c  mov     [rsp+120h+var_EC], ax
0x18000f591  cmovb   rbx, [rbp+57h+arg_18]
0x18000f596  mov     rax, [rcx]
0x18000f599  mov     r9, rbx
0x18000f59c  mov     [rsp+120h+var_100], r14d
0x18000f5a1  mov     rax, [rax+48h]
0x18000f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5aa  mov     [rsp+120h+var_F0], eax
0x18000f5ae  test    eax, eax
0x18000f5b0  jns     loc_18000F6CF
0x18000f5b6  mov     eax, 2D88h
0x18000f5bb  jmp     loc_18000F6F0
0x18000f5c0  mov     rcx, [rbp+57h+var_B0]
0x18000f5c4  mov     rax, [rcx]
0x18000f5c7  mov     rax, [rax+28h]
0x18000f5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d0  mov     [rsp+120h+var_F0], eax
0x18000f5d4  test    eax, eax
0x18000f5d6  jns     short loc_18000F5E2
0x18000f5d8  mov     eax, 2D60h
0x18000f5dd  jmp     loc_18000F6F0
0x18000f5e2  mov     ecx, esi
0x18000f5e4  mov     rax, rbx
0x18000f5e7  xor     edx, edx
0x18000f5e9  div     rcx
0x18000f5ec  mov     rbx, rax
0x18000f5ef  mov     eax, 2D60h
0x18000f5f4  mov     [rsp+120h+var_EC], ax
0x18000f5f9  lea     esi, [rax+1Ah]
0x18000f5fc  lea     r12d, [rax+9]
0x18000f600  lea     r13d, [rax+10h]
0x18000f604  mov     rcx, [rbp+57h+pv+8]; pv
0x18000f608  call    cs:__imp_CoTaskMemFree
0x18000f60e  mov     rcx, [rbp+57h+var_98]; pv
0x18000f612  mov     [rbp+57h+pv+8], r14
0x18000f616  call    cs:__imp_CoTaskMemFree
0x18000f61c  mov     rcx, [rbp+57h+var_B0]
0x18000f620  lea     r9, [rbp+57h+arg_8]
0x18000f624  xorps   xmm0, xmm0
0x18000f627  mov     [rbp+57h+arg_8], r14d
0x18000f62b  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18000f62f  lea     r8, [rbp+57h+pv]
0x18000f633  mov     edx, r15d
0x18000f636  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x18000f63a  movups  [rbp+57h+var_88], xmm0
0x18000f63e  mov     rax, [rcx]
0x18000f641  mov     rax, [rax+18h]
0x18000f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64a  mov     [rsp+120h+var_F0], eax
0x18000f64e  test    eax, eax
0x18000f650  js      loc_18000F6E0
0x18000f656  mov     [rsp+120h+var_EC], r12w
0x18000f65c  cmp     eax, r15d
0x18000f65f  jz      short loc_18000F6CF
0x18000f661  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x18000f665  lea     rdx, [rbp+57h+arg_18]; unsigned __int64 *
0x18000f669  call    ?_GetMinDiffAreaSize@CSpp@@CAJPEBGPEA_K@Z; CSpp::_GetMinDiffAreaSize(ushort const *,unsigned __int64 *)
0x18000f66e  mov     [rsp+120h+var_F0], eax
0x18000f672  test    eax, eax
0x18000f674  js      short loc_18000F6C7
0x18000f676  cmp     rbx, [rbp+57h+arg_18]
0x18000f67a  mov     [rsp+120h+var_EC], r13w
0x18000f680  cmovb   rbx, [rbp+57h+arg_18]
0x18000f685  cmp     dword ptr [rbp+57h+pv], 3
0x18000f689  jnz     loc_18000F604
0x18000f68f  mov     rcx, [rbp+57h+var_B8]
0x18000f693  mov     r9, rbx
0x18000f696  mov     r8, [rbp+57h+var_98]
0x18000f69a  mov     rdx, rdi
0x18000f69d  mov     [rsp+120h+var_100], r14d
0x18000f6a2  mov     rax, [rcx]
0x18000f6a5  mov     rax, [rax+48h]
0x18000f6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ae  mov     [rsp+120h+var_F0], eax
0x18000f6b2  test    eax, eax
0x18000f6b4  js      short loc_18000F6C0
0x18000f6b6  mov     [rsp+120h+var_EC], si
0x18000f6bb  jmp     loc_18000F604
0x18000f6c0  mov     [rsp+120h+var_EA], si
0x18000f6c5  jmp     short loc_18000F6F5
0x18000f6c7  mov     [rsp+120h+var_EA], r13w
0x18000f6cd  jmp     short loc_18000F6F5
0x18000f6cf  mov     eax, 2D8Ch
0x18000f6d4  mov     [rsp+120h+var_F0], r14d
0x18000f6d9  mov     [rsp+120h+var_EC], ax
0x18000f6de  jmp     short loc_18000F6F5
0x18000f6e0  mov     [rsp+120h+var_EA], r12w
0x18000f6e6  jmp     short loc_18000F6F5
0x18000f6e8  mov     [rsp+120h+var_F0], 80070057h
0x18000f6f0  mov     [rsp+120h+var_EA], ax
0x18000f6f5  mov     rcx, [rbp+57h+pv+8]; pv
0x18000f6f9  call    cs:__imp_CoTaskMemFree
0x18000f6ff  mov     rcx, [rbp+57h+var_98]; pv
0x18000f703  mov     [rbp+57h+pv+8], r14
0x18000f707  call    cs:__imp_CoTaskMemFree
0x18000f70d  mov     [rbp+57h+var_98], r14
0x18000f711  mov     ebx, [rsp+120h+var_F0]
0x18000f715  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x18000f719  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000f71e  lea     rcx, [rbp+57h+var_B0]
0x18000f722  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18000f727  lea     rcx, [rbp+57h+var_B8]
0x18000f72b  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18000f730  lea     rcx, [rsp+120h+var_F0]; this
0x18000f735  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f73a  mov     eax, ebx
0x18000f73c  mov     rbx, [rsp+120h+arg_0]
  ... truncated ...
```
