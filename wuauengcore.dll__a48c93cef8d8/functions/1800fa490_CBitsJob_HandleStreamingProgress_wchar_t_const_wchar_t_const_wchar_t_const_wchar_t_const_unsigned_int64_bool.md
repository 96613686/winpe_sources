# CBitsJob::HandleStreamingProgress(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * const,unsigned __int64,bool)

- ea: `0x1800fa490`
- end: `0x1800faa5a`
- name: `?HandleStreamingProgress@CBitsJob@@UEAAJPEB_W00QEA_W_K_N@Z`
- size: `1482`
- prototype: `__int64 __fastcall(CBitsJob *this, const wchar_t *, const wchar_t *, const wchar_t *, BSTR bstr, LPCWSTR, bool)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000def4`
- `0x1800e7870`
- `0x1800e90b4`
- `0x1800fa490`
- `0x1800fb260`
- `0x1800fbcb0`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x18012bed4`
- `0x1801f1c90`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa6a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fa9ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fa9ce`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800fa682`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800fa682`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa5e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa5e1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fa81c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fa81c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800fa7ea`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800fa7ea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800fa6dd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800fa97e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800fa6dd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800fa97e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800fa702`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800fa702`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800fa4ec`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800fa4ec`

## string_xrefs

- `0x1800fa644`: `Job: %ws Opened file %ws`
- `0x1800faa05`: `C:\__w\1\s\src\Client\Engine\Agent\BitsJobBlockTable.cpp`

## pseudocode

```c
__int64 __fastcall CBitsJob::HandleStreamingProgress(
        CBitsJob *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        BSTR bstr,
        LPCWSTR a6,
        bool a7)
{
  __int64 FileW; // rdi
  void *v10; // rbx
  UINT v11; // eax
  signed int v12; // r15d
  struct CBitsJob::CStreamingInfo *v13; // rsi
  unsigned int IndexOf; // eax
  struct CBitsJob::CStreamingInfo *v15; // r13
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct IAppxRawDataReceiver **); // r14
  __int64 (__fastcall *v17)(_QWORD, GUID *, struct IAppxRawDataReceiver **); // r15
  signed int LastError; // eax
  CBitsJob *v19; // r14
  __int64 v20; // rax
  signed int v21; // eax
  signed int v22; // ecx
  signed int v23; // eax
  unsigned int v24; // r9d
  char v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r14
  __int64 v28; // r12
  LARGE_INTEGER v29; // rdx
  unsigned __int64 v30; // r13
  int v31; // eax
  int v32; // r14d
  __int64 v33; // rax
  CBitsJob *v34; // r14
  unsigned int v35; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+38h] [rbp-C8h]
  char v40; // [rsp+40h] [rbp-C0h]
  struct CBitsJob::CStreamingInfo *v41; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+54h] [rbp-ACh]
  CBitsJob *v44; // [rsp+58h] [rbp-A8h]
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  void *v46; // [rsp+68h] [rbp-98h]
  struct _GUID v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER liDistanceToMove[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v50[80]; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpFileName; // [rsp+F0h] [rbp-10h] BYREF
  HCRYPTPROV hProv; // [rsp+F8h] [rbp-8h] BYREF
  struct IAppxRawDataReceiver *v53; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  lpFileName = a4;
  v44 = this;
  FileW = -1;
  v48 = -1;
  v10 = 0;
  v46 = 0;
  lpMem = 0;
  v53 = 0;
  hProv = 0;
  v11 = SysStringByteLen(bstr);
  v12 = ComputeLocalFileName(v11, (unsigned __int8 *)bstr, (wchar_t **)&lpMem);
  v13 = (struct CBitsJob::CStreamingInfo *)lpMem;
  if ( v12 >= 0 )
  {
    v41 = (struct CBitsJob::CStreamingInfo *)lpMem;
    if ( (unsigned int)CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(
                         (char *)this + 80,
                         &v41) == *((_DWORD *)this + 25) )
    {
      v12 = -2145124297;
      goto LABEL_55;
    }
    v41 = v13;
    IndexOf = CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(
                (char *)this + 80,
                &v41);
    if ( IndexOf >= *((_DWORD *)this + 25) )
    {
      v12 = -2145124345;
      goto LABEL_53;
    }
    v15 = *(struct CBitsJob::CStreamingInfo **)(*((_QWORD *)this + 11) + 16LL * IndexOf);
    v16 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IAppxRawDataReceiver **))v15;
    v17 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IAppxRawDataReceiver **))v15;
    if ( v53 )
    {
      (*(void (__fastcall **)(struct IAppxRawDataReceiver *))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    v12 = v17(v16, &GUID_b8a7d2fd_ade6_4a4c_a44c_4b8d3273dc31, &v53);
    if ( v12 < 0 )
      goto LABEL_53;
    if ( lpFileName )
      a3 = lpFileName;
    FileW = (__int64)CreateFileW(a3, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v48 = FileW;
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      if ( v12 >= 0 )
        v12 = -2147418113;
      goto LABEL_52;
    }
    v19 = v44;
    v47 = (struct _GUID)*((_OWORD *)v44 + 1);
    v20 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v50, &v47);
    WUTrace(0, 0, 2, 5, 0, L"Job: %ws Opened file %ws", v20, a3);
    if ( a7 )
    {
      lpFileName = 0;
      if ( !GetFileSizeEx((HANDLE)FileW, (PLARGE_INTEGER)&lpFileName) )
        goto LABEL_19;
      a6 = lpFileName;
    }
    if ( hProv )
    {
      CryptReleaseContext(hProv, 0);
      hProv = 0;
    }
    if ( CryptAcquireContextW(&hProv, 0, 0, 0x18u, 0xF0000040) )
    {
      v24 = 0;
      v42 = 0;
      v40 = 1;
      v25 = 0;
      v26 = 0;
      v43 = 0;
      *(_QWORD *)&v47.Data1 = (char *)v15 + 108;
      if ( *((_DWORD *)v15 + 27) )
      {
        v41 = v15;
        do
        {
          v27 = 5 * v26;
          v28 = *((_QWORD *)v15 + 12);
          v12 = 0;
          if ( *(_DWORD *)(v28 + 40 * v26 + 24) != 1 )
          {
            v29 = *(LARGE_INTEGER *)(v28 + 40 * v26 + 32);
            liDistanceToMove[0] = v29;
            if ( v29.QuadPart < (unsigned __int64)a6 )
            {
              v30 = *(unsigned int *)(v28 + 40 * v26 + 16);
              if ( v29.QuadPart + v30 > (unsigned __int64)a6 )
              {
                v15 = v41;
              }
              else
              {
                if ( (unsigned int)v30 > v24 )
                {
                  if ( v10 )
                  {
                    SusFree(v10);
                    v10 = 0;
                    v46 = 0;
                  }
                  if ( v30 )
                  {
                    v10 = SafeSusAllocArray(v30, 1u);
                    v46 = v10;
                    v12 = v10 == 0 ? 0x8007000E : 0;
                    if ( !v10 )
                      goto LABEL_53;
                  }
                  v42 = *(_DWORD *)(v28 + 8 * v27 + 16);
                  v29 = liDistanceToMove[0];
                }
                if ( v40 )
                {
                  if ( !SetFilePointerEx((HANDLE)FileW, v29, 0, 0) )
                    goto LABEL_19;
                  v40 = 0;
                }
                LODWORD(lpFileName) = 0;
                if ( !ReadFile((HANDLE)FileW, v10, *(_DWORD *)(v28 + 8 * v27 + 16), (LPDWORD)&lpFileName, 0) )
                  goto LABEL_19;
                v15 = v41;
                v31 = CAppxBlockTableBase::ValidateBlockHash(
                        **(CAppxBlockTableBase ***)(*((_QWORD *)v41 + 14) + 8LL),
                        *(_DWORD *)(v28 + 8 * v27),
                        (const unsigned __int8 *)v10,
                        *(_DWORD *)(v28 + 8 * v27 + 16),
                        hProv);
                v12 = v31;
                if ( v31 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4D,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\BitsJobBlockTable.cpp",
                    (const char *)(unsigned int)v31,
                    dwCreationDisposition);
                  LODWORD(hTemplateFile) = *(_DWORD *)(v28 + 8 * v27);
                  WUTrace(
                    0,
                    0,
                    2,
                    1,
                    v12,
                    L"Validating block %lu for file %ws failed.",
                    hTemplateFile,
                    *((_QWORD *)v15 + 6));
                  goto LABEL_52;
                }
                *(_DWORD *)(v28 + 8 * v27 + 24) = 1;
                v32 = *(_DWORD *)(v28 + 8 * v27);
                *(_OWORD *)&liDistanceToMove[0].LowPart = *((_OWORD *)v44 + 1);
                v33 = Trace::GuidToString::GuidToString(
                        (Trace::GuidToString *)v50,
                        (const struct _GUID *)liDistanceToMove);
                LODWORD(v39) = v32;
                WUTrace(0, 0, 2, 5, 0, L"Job %ws: Block %lu is valid now", v33, v39);
                v25 = 1;
                LODWORD(v26) = v43;
                v24 = v42;
              }
            }
          }
          v26 = (unsigned int)(v26 + 1);
          v43 = v26;
        }
        while ( (unsigned int)v26 < **(_DWORD **)&v47.Data1 );
        v19 = v44;
        if ( v25 )
          goto LABEL_51;
      }
      if ( a7 )
LABEL_51:
        v12 = CBitsJob::SatisfyRangesFromCache(v19, v15, (void *)FileW, v53);
LABEL_52:
      if ( v12 >= 0 )
        goto LABEL_55;
      goto LABEL_53;
    }
LABEL_19:
    v21 = GetLastError();
    v22 = (unsigned __int16)v21 | 0x80070000;
    if ( v21 <= 0 )
      v22 = v21;
    if ( v22 >= 0 )
    {
      v12 = -2147467259;
    }
    else
    {
      v23 = GetLastError();
      v12 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v12 = v23;
    }
    goto LABEL_52;
  }
LABEL_53:
  if ( v12 != -2145124297 )
    WUTrace(0, 0, 2, 1, v12, L"Failed to stream data from file.");
LABEL_55:
  if ( a7 )
  {
    v34 = v44;
    *(_QWORD *)&v47.Data1 = v13;
    v35 = CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(
            (char *)v44 + 80,
            &v47);
    if ( v35 < *((_DWORD *)v34 + 25) )
      CSusArrayList<CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::_tagMapEntry,CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::CMapEntryOps>::RemoveArraySection(
        (char *)v34 + 80,
        v35,
        v35,
        1);
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(struct IAppxRawDataReceiver *))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v13 )
    SusFree(v13);
  if ( v10 )
    SusFree(v10);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800fa490  mov     [rsp-8+arg_8], rbx
0x1800fa495  push    rbp
0x1800fa496  push    rsi
0x1800fa497  push    rdi
0x1800fa498  push    r12
0x1800fa49a  push    r13
0x1800fa49c  push    r14
0x1800fa49e  push    r15
0x1800fa4a0  lea     rbp, [rsp-10h]
0x1800fa4a5  sub     rsp, 110h
0x1800fa4ac  mov     rax, cs:__security_cookie
0x1800fa4b3  xor     rax, rsp
0x1800fa4b6  mov     [rbp+40h+var_38], rax
0x1800fa4ba  mov     [rbp+40h+lpFileName], r9
0x1800fa4be  mov     r12, r8
0x1800fa4c1  mov     r14, rcx
0x1800fa4c4  mov     [rsp+140h+var_E8], rcx
0x1800fa4c9  mov     rsi, [rbp+40h+bstr]
0x1800fa4cd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fa4d1  mov     [rbp+40h+var_C0], rdi
0x1800fa4d5  xor     ebx, ebx
0x1800fa4d7  mov     [rsp+140h+var_D8], rbx
0x1800fa4dc  mov     [rsp+140h+lpMem], rbx
0x1800fa4e1  mov     [rbp+40h+var_40], rbx
0x1800fa4e5  mov     [rbp+40h+hProv], rbx
0x1800fa4e9  mov     rcx, rsi; bstr
0x1800fa4ec  call    cs:__imp_SysStringByteLen
0x1800fa4f2  lea     r8, [rsp+140h+lpMem]; wchar_t **
0x1800fa4f7  mov     rdx, rsi; unsigned __int8 *
0x1800fa4fa  mov     ecx, eax; unsigned int
0x1800fa4fc  call    ?ComputeLocalFileName@@YAJKPEAEPEAPEA_W@Z; ComputeLocalFileName(ulong,uchar *,wchar_t * *)
0x1800fa501  mov     r15d, eax
0x1800fa504  mov     rsi, [rsp+140h+lpMem]
0x1800fa509  test    eax, eax
0x1800fa50b  js      loc_1800FA90C
0x1800fa511  mov     [rsp+140h+var_F8], rsi
0x1800fa516  lea     rdx, [rsp+140h+var_F8]
0x1800fa51b  lea     rcx, [r14+50h]
0x1800fa51f  call    ?GetIndexOf@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(wchar_t * const &)
0x1800fa524  cmp     eax, [r14+64h]
0x1800fa528  jnz     short loc_1800FA535
0x1800fa52a  mov     r15d, 80240037h
0x1800fa530  jmp     loc_1800FA937
0x1800fa535  mov     [rsp+140h+var_F8], rsi
0x1800fa53a  lea     rdx, [rsp+140h+var_F8]
0x1800fa53f  lea     rcx, [r14+50h]
0x1800fa543  call    ?GetIndexOf@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(wchar_t * const &)
0x1800fa548  cmp     eax, [r14+64h]
0x1800fa54c  jb      short loc_1800FA559
0x1800fa54e  mov     r15d, 80240007h
0x1800fa554  jmp     loc_1800FA90C
0x1800fa559  mov     ecx, eax
0x1800fa55b  add     rcx, rcx
0x1800fa55e  mov     rax, [r14+58h]
0x1800fa562  mov     r13, [rax+rcx*8]
0x1800fa566  mov     r14, [r13+0]
0x1800fa56a  mov     rax, [r14]
0x1800fa56d  mov     r15, [rax]
0x1800fa570  mov     rcx, [rbp+40h+var_40]
0x1800fa574  test    rcx, rcx
0x1800fa577  jz      short loc_1800FA58D
0x1800fa579  mov     rdx, [rcx]
0x1800fa57c  mov     rax, [rdx+10h]
0x1800fa580  call    _guard_dispatch_icall
0x1800fa585  mov     [rbp+40h+var_40], 0
0x1800fa58d  lea     r8, [rbp+40h+var_40]
0x1800fa591  lea     rdx, _GUID_b8a7d2fd_ade6_4a4c_a44c_4b8d3273dc31
0x1800fa598  mov     rcx, r14
0x1800fa59b  mov     rax, r15
0x1800fa59e  call    _guard_dispatch_icall
0x1800fa5a3  mov     r15d, eax
0x1800fa5a6  test    eax, eax
0x1800fa5a8  js      loc_1800FA90C
0x1800fa5ae  mov     rax, [rbp+40h+lpFileName]
0x1800fa5b2  test    rax, rax
0x1800fa5b5  cmovnz  r12, rax
0x1800fa5b9  mov     [rsp+140h+hTemplateFile], 0; hTemplateFile
0x1800fa5c2  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800fa5ca  mov     [rsp+140h+dwCreationDisposition], 3; dwCreationDisposition
0x1800fa5d2  xor     r9d, r9d; lpSecurityAttributes
0x1800fa5d5  mov     edx, 80000000h; dwDesiredAccess
0x1800fa5da  lea     r8d, [r9+7]; dwShareMode
0x1800fa5de  mov     rcx, r12; lpFileName
0x1800fa5e1  call    cs:__imp_CreateFileW
0x1800fa5e7  mov     rdi, rax
0x1800fa5ea  mov     [rbp+40h+var_C0], rax
0x1800fa5ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800fa5f2  jnz     short loc_1800FA61C
0x1800fa5f4  call    cs:__imp_GetLastError
0x1800fa5fa  movzx   r15d, ax
0x1800fa5fe  or      r15d, 80070000h
0x1800fa605  test    eax, eax
0x1800fa607  cmovle  r15d, eax
0x1800fa60b  mov     eax, 8000FFFFh
0x1800fa610  test    r15d, r15d
0x1800fa613  cmovns  r15d, eax
0x1800fa617  jmp     loc_1800FA907
0x1800fa61c  mov     r14, [rsp+140h+var_E8]
0x1800fa621  movups  xmm0, xmmword ptr [r14+10h]
0x1800fa626  movdqu  xmmword ptr [rsp+140h+var_D0.Data1], xmm0
0x1800fa62c  lea     rdx, [rsp+140h+var_D0]; struct _GUID *
0x1800fa631  lea     rcx, [rbp+40h+var_A0]; this
0x1800fa635  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800fa63a  mov     [rsp+140h+var_108], r12
0x1800fa63f  mov     [rsp+140h+hTemplateFile], rax
0x1800fa644  lea     rax, aJobWsOpenedFil; "Job: %ws Opened file %ws"
0x1800fa64b  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x1800fa650  mov     qword ptr [rsp+140h+dwCreationDisposition], 0
0x1800fa659  xor     edx, edx
0x1800fa65b  xor     ecx, ecx
0x1800fa65d  lea     r9d, [rdx+5]
0x1800fa661  lea     r8d, [rdx+2]
0x1800fa665  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800fa66a  cmp     [rbp+40h+arg_30], 0
0x1800fa671  jz      short loc_1800FA6D2
0x1800fa673  mov     [rbp+40h+lpFileName], 0
0x1800fa67b  lea     rdx, [rbp+40h+lpFileName]; lpFileSize
0x1800fa67f  mov     rcx, rdi; hFile
0x1800fa682  call    cs:__imp_GetFileSizeEx
0x1800fa688  test    eax, eax
0x1800fa68a  jnz     short loc_1800FA6CA
0x1800fa68c  call    cs:__imp_GetLastError
0x1800fa692  movzx   ecx, ax
0x1800fa695  mov     r14d, 80070000h
0x1800fa69b  or      ecx, r14d
0x1800fa69e  test    eax, eax
0x1800fa6a0  cmovle  ecx, eax
0x1800fa6a3  test    ecx, ecx
0x1800fa6a5  jns     short loc_1800FA6BF
0x1800fa6a7  call    cs:__imp_GetLastError
0x1800fa6ad  movzx   r15d, ax
0x1800fa6b1  or      r15d, r14d
0x1800fa6b4  test    eax, eax
0x1800fa6b6  cmovle  r15d, eax
0x1800fa6ba  jmp     loc_1800FA907
0x1800fa6bf  mov     r15d, 80004005h
0x1800fa6c5  jmp     loc_1800FA907
0x1800fa6ca  mov     rax, [rbp+40h+lpFileName]
0x1800fa6ce  mov     [rbp+40h+arg_28], rax
0x1800fa6d2  mov     rcx, [rbp+40h+hProv]; hProv
0x1800fa6d6  test    rcx, rcx
0x1800fa6d9  jz      short loc_1800FA6EB
0x1800fa6db  xor     edx, edx; dwFlags
0x1800fa6dd  call    cs:__imp_CryptReleaseContext
0x1800fa6e3  mov     [rbp+40h+hProv], 0
0x1800fa6eb  mov     [rsp+140h+dwCreationDisposition], 0F0000040h; dwFlags
0x1800fa6f3  mov     r9d, 18h; dwProvType
0x1800fa6f9  xor     r8d, r8d; szProvider
0x1800fa6fc  xor     edx, edx; szContainer
0x1800fa6fe  lea     rcx, [rbp+40h+hProv]; phProv
0x1800fa702  call    cs:__imp_CryptAcquireContextW
0x1800fa708  test    eax, eax
0x1800fa70a  jz      short loc_1800FA68C
0x1800fa70c  xor     r9d, r9d
0x1800fa70f  mov     [rsp+140h+var_F0], r9d
0x1800fa714  mov     [rsp+140h+var_100], 1
0x1800fa719  xor     r8b, r8b
0x1800fa71c  xor     ecx, ecx
0x1800fa71e  mov     [rsp+140h+var_EC], ecx
0x1800fa722  lea     rax, [r13+6Ch]
0x1800fa726  mov     qword ptr [rsp+140h+var_D0.Data1], rax
0x1800fa72b  mov     eax, [rax]
0x1800fa72d  test    eax, eax
0x1800fa72f  jz      loc_1800FA8E9
0x1800fa735  mov     [rsp+140h+var_F8], r13
0x1800fa73a  cmp     ecx, eax
0x1800fa73c  jnb     loc_1800FAA4E
0x1800fa742  lea     r14, [rcx+rcx*4]
0x1800fa746  mov     r12, [r13+60h]
0x1800fa74a  xor     r15d, r15d
0x1800fa74d  cmp     dword ptr [r12+r14*8+18h], 1
0x1800fa753  jz      loc_1800FA8CA
0x1800fa759  mov     rdx, [r12+r14*8+20h]
0x1800fa75e  mov     qword ptr [rbp+40h+liDistanceToMove], rdx
0x1800fa762  mov     r10, [rbp+40h+arg_28]
0x1800fa766  cmp     rdx, r10
0x1800fa769  jnb     loc_1800FA8CA
0x1800fa76f  mov     r13d, [r12+r14*8+10h]
0x1800fa774  lea     rax, [rdx+r13]
0x1800fa778  cmp     rax, r10
0x1800fa77b  ja      loc_1800FA8C5
0x1800fa781  cmp     r13d, r9d
0x1800fa784  jbe     short loc_1800FA7DA
0x1800fa786  test    rbx, rbx
0x1800fa789  jz      short loc_1800FA79A
0x1800fa78b  mov     rcx, rbx; lpMem
0x1800fa78e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800fa793  xor     ebx, ebx
0x1800fa795  mov     [rsp+140h+var_D8], rbx
0x1800fa79a  test    r13, r13
0x1800fa79d  jz      short loc_1800FA7CD
0x1800fa79f  mov     edx, 1; unsigned __int64
0x1800fa7a4  mov     rcx, r13; unsigned __int64
0x1800fa7a7  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800fa7ac  mov     rbx, rax
0x1800fa7af  mov     [rsp+140h+var_D8], rax
0x1800fa7b4  neg     rax
0x1800fa7b7  sbb     r15d, r15d
0x1800fa7ba  not     r15d
0x1800fa7bd  and     r15d, 8007000Eh
0x1800fa7c4  test    rbx, rbx
0x1800fa7c7  jz      loc_1800FA90C
0x1800fa7cd  mov     eax, [r12+r14*8+10h]
0x1800fa7d2  mov     [rsp+140h+var_F0], eax
0x1800fa7d6  mov     rdx, qword ptr [rbp+40h+liDistanceToMove]; liDistanceToMove
0x1800fa7da  cmp     [rsp+140h+var_100], 0
0x1800fa7df  jz      short loc_1800FA7FD
0x1800fa7e1  xor     r9d, r9d; dwMoveMethod
0x1800fa7e4  xor     r8d, r8d; lpNewFilePointer
0x1800fa7e7  mov     rcx, rdi; hFile
0x1800fa7ea  call    cs:__imp_SetFilePointerEx
0x1800fa7f0  test    eax, eax
0x1800fa7f2  jz      loc_1800FA68C
0x1800fa7f8  mov     [rsp+140h+var_100], 0
0x1800fa7fd  mov     dword ptr [rbp+40h+lpFileName], 0
0x1800fa804  mov     qword ptr [rsp+140h+dwCreationDisposition], 0; lpOverlapped
0x1800fa80d  lea     r9, [rbp+40h+lpFileName]; lpNumberOfBytesRead
0x1800fa811  mov     r8d, [r12+r14*8+10h]; nNumberOfBytesToRead
0x1800fa816  mov     rdx, rbx; lpBuffer
0x1800fa819  mov     rcx, rdi; hFile
0x1800fa81c  call    cs:__imp_ReadFile
0x1800fa822  test    eax, eax
0x1800fa824  jz      loc_1800FA68C
0x1800fa82a  mov     rdx, [rbp+40h+hProv]
0x1800fa82e  mov     r13, [rsp+140h+var_F8]
0x1800fa833  mov     rax, [r13+70h]
0x1800fa837  mov     rcx, [rax+8]
0x1800fa83b  mov     qword ptr [rsp+140h+dwCreationDisposition], rdx; int
0x1800fa840  mov     r9d, [r12+r14*8+10h]; unsigned int
0x1800fa845  mov     r8, rbx; unsigned __int8 *
0x1800fa848  mov     edx, [r12+r14*8]; unsigned int
0x1800fa84c  mov     rcx, [rcx]; this
0x1800fa84f  call    ?ValidateBlockHash@CAppxBlockTableBase@@QEBAJKPEBEK_K@Z; CAppxBlockTableBase::ValidateBlockHash(ulong,uchar const *,ulong,unsigned __int64)
0x1800fa854  mov     r15d, eax
0x1800fa857  test    eax, eax
0x1800fa859  js      loc_1800FA9FE
0x1800fa85f  mov     dword ptr [r12+r14*8+18h], 1
0x1800fa868  mov     r14d, [r12+r14*8]
0x1800fa86c  mov     rax, [rsp+140h+var_E8]
0x1800fa871  movups  xmm0, xmmword ptr [rax+10h]
0x1800fa875  movdqu  xmmword ptr [rbp+40h+liDistanceToMove], xmm0
0x1800fa87a  lea     rdx, [rbp+40h+liDistanceToMove]; struct _GUID *
0x1800fa87e  lea     rcx, [rbp+40h+var_A0]; this
0x1800fa882  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800fa887  mov     dword ptr [rsp+140h+var_108], r14d
0x1800fa88c  mov     [rsp+140h+hTemplateFile], rax
0x1800fa891  lea     rax, aJobWsBlockLuIs; "Job %ws: Block %lu is valid now"
0x1800fa898  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x1800fa89d  mov     qword ptr [rsp+140h+dwCreationDisposition], 0
0x1800fa8a6  xor     edx, edx
0x1800fa8a8  xor     ecx, ecx
0x1800fa8aa  lea     r9d, [rdx+5]
0x1800fa8ae  lea     r8d, [rdx+2]
0x1800fa8b2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800fa8b7  mov     r8b, 1
0x1800fa8ba  mov     ecx, [rsp+140h+var_EC]
0x1800fa8be  mov     r9d, [rsp+140h+var_F0]
0x1800fa8c3  jmp     short loc_1800FA8CA
0x1800fa8c5  mov     r13, [rsp+140h+var_F8]
0x1800fa8ca  inc     ecx
0x1800fa8cc  mov     [rsp+140h+var_EC], ecx
0x1800fa8d0  mov     rax, qword ptr [rsp+140h+var_D0.Data1]
0x1800fa8d5  mov     eax, [rax]
0x1800fa8d7  cmp     ecx, eax
0x1800fa8d9  jb      loc_1800FA742
0x1800fa8df  mov     r14, [rsp+140h+var_E8]
0x1800fa8e4  test    r8b, r8b
0x1800fa8e7  jnz     short loc_1800FA8F2
0x1800fa8e9  cmp     [rbp+40h+arg_30], 0
0x1800fa8f0  jz      short loc_1800FA907
0x1800fa8f2  mov     r9, [rbp+40h+var_40]; struct IAppxRawDataReceiver *
0x1800fa8f6  mov     r8, rdi; void *
0x1800fa8f9  mov     rdx, r13; struct CBitsJob::CStreamingInfo *
0x1800fa8fc  mov     rcx, r14; this
0x1800fa8ff  call    ?SatisfyRangesFromCache@CBitsJob@@AEAAJPEAVCStreamingInfo@1@PEAXPEAUIAppxRawDataReceiver@@@Z; CBitsJob::SatisfyRangesFromCache(CBitsJob::CStreamingInfo *,void *,IAppxRawDataReceiver *)
0x1800fa904  mov     r15d, eax
0x1800fa907  test    r15d, r15d
0x1800fa90a  jns     short loc_1800FA937
0x1800fa90c  cmp     r15d, 80240037h
0x1800fa913  jz      short loc_1800FA937
0x1800fa915  lea     rax, aFailedToStream; "Failed to stream data from file."
0x1800fa91c  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x1800fa921  mov     [rsp+140h+dwCreationDisposition], r15d
0x1800fa926  xor     edx, edx
0x1800fa928  xor     ecx, ecx
0x1800fa92a  lea     r9d, [rdx+1]
0x1800fa92e  lea     r8d, [rdx+2]
0x1800fa932  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800fa937  cmp     [rbp+40h+arg_30], 0
0x1800fa93e  jz      short loc_1800FA973
0x1800fa940  mov     r14, [rsp+140h+var_E8]
0x1800fa945  mov     qword ptr [rsp+140h+var_D0.Data1], rsi
0x1800fa94a  lea     rdx, [rsp+140h+var_D0]
0x1800fa94f  lea     rcx, [r14+50h]
0x1800fa953  call    ?GetIndexOf@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(wchar_t * const &)
0x1800fa958  cmp     eax, [r14+64h]
0x1800fa95c  jnb     short loc_1800FA973
0x1800fa95e  mov     r9d, 1
0x1800fa964  mov     r8d, eax
0x1800fa967  mov     edx, eax
  ... truncated ...
```
