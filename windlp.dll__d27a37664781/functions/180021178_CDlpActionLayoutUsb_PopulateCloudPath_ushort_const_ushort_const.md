# CDlpActionLayoutUsb::PopulateCloudPath(ushort const *,ushort const *)

- ea: `0x180021178`
- end: `0x18002147b`
- name: `?PopulateCloudPath@CDlpActionLayoutUsb@@AEAAJPEBG0@Z`
- size: `771`
- prototype: `int(CDlpActionLayoutUsb *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000b7f8`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001fd60`
- `0x180021178`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021252`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021252`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002130c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002130c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002142c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002142c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002143b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021461`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002143b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021326`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021415`

## string_xrefs

- `0x1800211c3`: `CDlpActionLayoutUsb::PopulateCloudPath`
- `0x18002135d`: `CDlpActionLayoutUsb::PopulateCloudPath`
- `0x1800213e9`: `CDlpActionLayoutUsb::PopulateCloudPath`
- `0x1800212d5`: `RecoverUsb: Populating Cloud Path: [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionLayoutUsb::PopulateCloudPath(
        CDlpActionLayoutUsb *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v5; // edi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int StringCch; // eax
  DWORD FileAttributesW; // ebx
  int v11; // ebx
  int v12; // eax
  HANDLE FileW; // rax
  void *v14; // rbx
  signed int LastError; // eax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rbx
  HANDLE ProcessHeap; // rax
  LPCWSTR v25; // rbx
  HANDLE v26; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-20h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-18h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-18h]
  __int64 v32; // [rsp+78h] [rbp+38h] BYREF
  __int64 v33; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp+48h] BYREF

  v33 = (__int64)a3;
  lpFileName = 0;
  v32 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_43;
    dwFlagsAndAttributes = -2147024809;
    dwCreationDisposition = 2580;
LABEL_4:
    v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v6,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpActionLayoutUsb::PopulateCloudPath",
           dwCreationDisposition,
           dwFlagsAndAttributes);
    v8 = (unsigned int)v7;
    if ( v7 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    goto LABEL_43;
  }
  LODWORD(v33) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a2, &v33);
  v5 = StringCch;
  if ( StringCch < 0
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a2),
        v5 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v5 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_43;
    dwFlagsAndAttributes = v5;
    dwCreationDisposition = 2583;
    goto LABEL_4;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    v11 = 0;
  else
    v11 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v5 = 0;
  if ( !v11 )
    goto LABEL_43;
  v12 = CDlpHelpersT<CEmptyType>::CombinePath(L"sources", L"Cloud", &v32);
  v5 = v12;
  v6 = *((_QWORD *)this + 11);
  if ( v12 < 0 )
  {
    if ( !v6 )
      goto LABEL_43;
    dwFlagsAndAttributes = v12;
    dwCreationDisposition = 2589;
    goto LABEL_4;
  }
  v33 = -1;
  if ( v6 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v6, 2, L"RecoverUsb: Populating Cloud Path: [%s] -> [%s]", a2, v32);
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  v14 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v33 = (__int64)FileW;
    v18 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1160, &lpFileName);
    v5 = v18;
    if ( v18 >= 0 )
    {
      v20 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1176, &v32);
      v5 = v20;
      if ( v20 < 0 )
      {
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
        {
          LODWORD(dwFlagsAndAttributesa) = v20;
          dwCreationDispositiona[0] = 2606;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v19 = *((_QWORD *)this + 11);
      if ( v19 )
      {
        LODWORD(dwFlagsAndAttributesa) = v18;
        dwCreationDispositiona[0] = 2605;
LABEL_39:
        v21 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v19,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::PopulateCloudPath",
                *(_QWORD *)dwCreationDispositiona,
                dwFlagsAndAttributesa);
        v22 = (unsigned int)v21;
        if ( v21 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
      }
    }
    CloseHandle(v14);
    goto LABEL_43;
  }
  v33 = -1;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = -2147467259;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v16 = 0;
    if ( v5 < 0 )
    {
      LODWORD(dwFlagsAndAttributesa) = v5;
      dwCreationDispositiona[0] = 2603;
      v17 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *((_QWORD *)this + 11),
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::PopulateCloudPath",
              *(_QWORD *)dwCreationDispositiona,
              dwFlagsAndAttributesa);
      v16 = (unsigned int)v17;
      if ( v17 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
  }
LABEL_43:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  v23 = v32;
  if ( v32 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v23 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v25 = lpFileName;
  if ( lpFileName )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, (LPVOID)(v25 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021178  mov     [rsp-28h+arg_10], r8
0x18002117d  push    rbp
0x18002117e  push    rbx
0x18002117f  push    rsi
0x180021180  push    rdi
0x180021181  push    r14
0x180021183  mov     rbp, rsp
0x180021186  sub     rsp, 40h
0x18002118a  mov     r14, rdx
0x18002118d  mov     rsi, rcx
0x180021190  mov     [rbp+lpFileName], 0
0x180021198  mov     [rbp+arg_8], 0
0x1800211a0  test    rdx, rdx
0x1800211a3  jnz     short loc_1800211F0
0x1800211a5  mov     edi, 80070057h
0x1800211aa  mov     rcx, [rcx+58h]
0x1800211ae  test    rcx, rcx
0x1800211b1  jz      loc_18002141B
0x1800211b7  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], edi
0x1800211bb  mov     [rsp+40h+dwCreationDisposition], 0A14h
0x1800211c3  lea     r9, aCdlpactionlayo_22; "CDlpActionLayoutUsb::PopulateCloudPath"
0x1800211ca  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800211d1  mov     edx, 4
0x1800211d6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800211db  test    eax, eax
0x1800211dd  mov     ecx, eax
0x1800211df  jns     short loc_1800211E6
0x1800211e1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800211e6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800211eb  jmp     loc_18002141B
0x1800211f0  mov     dword ptr [rbp+arg_10], 0
0x1800211f7  lea     rdx, [rbp+arg_10]
0x1800211fb  mov     rcx, r14
0x1800211fe  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180021203  mov     edi, eax
0x180021205  test    eax, eax
0x180021207  js      short loc_18002121E
0x180021209  lea     r8, [rbp+lpFileName]
0x18002120d  mov     edx, dword ptr [rbp+arg_10]
0x180021210  mov     rcx, r14; Src
0x180021213  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180021218  mov     edi, eax
0x18002121a  test    eax, eax
0x18002121c  jns     short loc_180021225
0x18002121e  mov     ecx, eax
0x180021220  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021225  mov     ecx, edi
0x180021227  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002122c  test    edi, edi
0x18002122e  jns     short loc_18002124E
0x180021230  mov     rcx, [rsi+58h]
0x180021234  test    rcx, rcx
0x180021237  jz      loc_18002141B
0x18002123d  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], edi
0x180021241  mov     [rsp+40h+dwCreationDisposition], 0A17h
0x180021249  jmp     loc_1800211C3
0x18002124e  mov     rcx, [rbp+lpFileName]; lpFileName
0x180021252  call    cs:__imp_GetFileAttributesW
0x180021258  mov     ebx, eax
0x18002125a  cmp     eax, 0FFFFFFFFh
0x18002125d  jz      short loc_180021267
0x18002125f  shr     ebx, 4
0x180021262  and     ebx, 1
0x180021265  jmp     short loc_180021269
0x180021267  xor     ebx, ebx
0x180021269  xor     ecx, ecx
0x18002126b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021270  xor     ecx, ecx
0x180021272  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021277  xor     edi, edi
0x180021279  test    ebx, ebx
0x18002127b  jz      loc_18002141B
0x180021281  lea     r8, [rbp+arg_8]
0x180021285  lea     rdx, aCloud; "Cloud"
0x18002128c  lea     rcx, aSources; "sources"
0x180021293  call    ?CombinePath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG0PEAPEAG@Z; CDlpHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort * *)
0x180021298  mov     edi, eax
0x18002129a  mov     rcx, [rsi+58h]
0x18002129e  test    eax, eax
0x1800212a0  jns     short loc_1800212BC
0x1800212a2  test    rcx, rcx
0x1800212a5  jz      loc_18002141B
0x1800212ab  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], eax
0x1800212af  mov     [rsp+40h+dwCreationDisposition], 0A1Dh
0x1800212b7  jmp     loc_1800211C3
0x1800212bc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800212c0  mov     [rbp+arg_10], rdi
0x1800212c4  test    rcx, rcx
0x1800212c7  jz      short loc_1800212E4
0x1800212c9  mov     rax, [rbp+arg_8]
0x1800212cd  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x1800212d2  mov     r9, r14
0x1800212d5  lea     r8, aRecoverusbPopu_0; "RecoverUsb: Populating Cloud Path: [%s]"...
0x1800212dc  lea     edx, [rdi+3]
0x1800212df  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800212e4  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x1800212ed  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800212f5  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1800212fd  xor     r9d, r9d; lpSecurityAttributes
0x180021300  mov     edx, 80000000h; dwDesiredAccess
0x180021305  lea     r8d, [r9+7]; dwShareMode
0x180021309  mov     rcx, r14; lpFileName
0x18002130c  call    cs:__imp_CreateFileW
0x180021312  mov     rbx, rax
0x180021315  lea     rcx, [rax+1]
0x180021319  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180021320  jnz     short loc_18002138D
0x180021322  mov     [rbp+arg_10], rdi
0x180021326  call    cs:__imp_GetLastError
0x18002132c  mov     edi, eax
0x18002132e  test    eax, eax
0x180021330  jnz     short loc_180021339
0x180021332  mov     edi, 80004005h
0x180021337  jmp     short loc_180021344
0x180021339  jle     short loc_180021344
0x18002133b  movzx   edi, ax
0x18002133e  or      edi, 80070000h
0x180021344  cmp     qword ptr [rsi+58h], 0
0x180021349  jz      short loc_180021388
0x18002134b  xor     ecx, ecx
0x18002134d  test    edi, edi
0x18002134f  jns     short loc_180021382
0x180021351  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], edi
0x180021355  mov     [rsp+40h+dwCreationDisposition], 0A2Bh
0x18002135d  lea     r9, aCdlpactionlayo_22; "CDlpActionLayoutUsb::PopulateCloudPath"
0x180021364  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002136b  lea     edx, [rcx+4]
0x18002136e  mov     rcx, [rsi+58h]
0x180021372  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180021377  mov     ecx, eax
0x180021379  test    eax, eax
0x18002137b  jns     short loc_180021382
0x18002137d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021382  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021387  nop
0x180021388  jmp     loc_18002141B
0x18002138d  mov     [rbp+arg_10], rbx
0x180021391  lea     rcx, [rsi+488h]
0x180021398  lea     rdx, [rbp+lpFileName]
0x18002139c  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x1800213a1  mov     edi, eax
0x1800213a3  test    eax, eax
0x1800213a5  jns     short loc_1800213BE
0x1800213a7  mov     rcx, [rsi+58h]
0x1800213ab  test    rcx, rcx
0x1800213ae  jz      short loc_180021412
0x1800213b0  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], eax
0x1800213b4  mov     [rsp+40h+dwCreationDisposition], 0A2Dh
0x1800213bc  jmp     short loc_1800213E9
0x1800213be  lea     rcx, [rsi+498h]
0x1800213c5  lea     rdx, [rbp+arg_8]
0x1800213c9  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x1800213ce  mov     edi, eax
0x1800213d0  test    eax, eax
0x1800213d2  jns     short loc_180021412
0x1800213d4  mov     rcx, [rsi+58h]
0x1800213d8  test    rcx, rcx
0x1800213db  jz      short loc_180021412
0x1800213dd  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], eax
0x1800213e1  mov     [rsp+40h+dwCreationDisposition], 0A2Eh
0x1800213e9  lea     r9, aCdlpactionlayo_22; "CDlpActionLayoutUsb::PopulateCloudPath"
0x1800213f0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800213f7  mov     edx, 4
0x1800213fc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180021401  test    eax, eax
0x180021403  mov     ecx, eax
0x180021405  jns     short loc_18002140C
0x180021407  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002140c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021411  nop
0x180021412  mov     rcx, rbx; hObject
0x180021415  call    cs:__imp_CloseHandle
0x18002141b  mov     ecx, edi
0x18002141d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021422  nop
0x180021423  mov     rbx, [rbp+arg_8]
0x180021427  test    rbx, rbx
0x18002142a  jz      short loc_180021449
0x18002142c  call    cs:__imp_GetProcessHeap
0x180021432  mov     rcx, rax; hHeap
0x180021435  lea     r8, [rbx-4]; lpMem
0x180021439  xor     edx, edx; dwFlags
0x18002143b  call    cs:__imp_HeapFree
0x180021441  xor     ecx, ecx
0x180021443  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021448  nop
0x180021449  mov     rbx, [rbp+lpFileName]
0x18002144d  test    rbx, rbx
0x180021450  jz      short loc_18002146E
0x180021452  call    cs:__imp_GetProcessHeap
0x180021458  mov     rcx, rax; hHeap
0x18002145b  lea     r8, [rbx-4]; lpMem
0x18002145f  xor     edx, edx; dwFlags
0x180021461  call    cs:__imp_HeapFree
0x180021467  xor     ecx, ecx
0x180021469  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002146e  mov     eax, edi
0x180021470  add     rsp, 40h
0x180021474  pop     r14
0x180021476  pop     rdi
0x180021477  pop     rsi
0x180021478  pop     rbx
0x180021479  pop     rbp
0x18002147a  retn
```
