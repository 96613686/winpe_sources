# CDlpActionLayoutUsb::PopulateOemPath(ushort const *,ushort const *)

- ea: `0x180021698`
- end: `0x180021982`
- name: `?PopulateOemPath@CDlpActionLayoutUsb@@AEAAJPEBG0@Z`
- size: `746`
- prototype: `int(CDlpActionLayoutUsb *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180021988`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001fd60`
- `0x180021698`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021762`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002192a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002192a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021950`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002195f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002195f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002177a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002177a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002191a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002191a`

## string_xrefs

- `0x1800218dd`: `CDlpActionLayoutUsb::PopulateOemPath`
- `0x180021729`: `RecoverUsb: Populating Oem Path: [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionLayoutUsb::PopulateOemPath(CDlpActionLayoutUsb *this, WCHAR *a2, unsigned __int16 *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  signed int v8; // edi
  HANDLE FileW; // rcx
  signed int LastError; // eax
  __int64 v11; // rcx
  int StringCch; // eax
  int v13; // eax
  int Internal; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-30h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-28h]
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+48h] [rbp-8h]
  int v26; // [rsp+88h] [rbp+38h] BYREF
  __int64 v27; // [rsp+98h] [rbp+48h] BYREF

  v24 = 0;
  v27 = 0;
  v6 = -1;
  v25 = -1;
  v7 = *((_QWORD *)this + 11);
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !v7 )
      goto LABEL_38;
    LODWORD(dwFlagsAndAttributes) = -2147024809;
    dwCreationDisposition[0] = 2036;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    if ( !v7 )
      goto LABEL_38;
    LODWORD(dwFlagsAndAttributes) = -2147024809;
    dwCreationDisposition[0] = 2037;
    goto LABEL_35;
  }
  if ( v7 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v7, 2, L"RecoverUsb: Populating Oem Path: [%s] -> [%s]", a2, a3);
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = (__int64)FileW;
    v25 = (__int64)FileW;
    v26 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a2, &v26);
    v8 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a2),
          v8 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v7 = *((_QWORD *)this + 11);
      if ( !v7 )
        goto LABEL_38;
      LODWORD(dwFlagsAndAttributes) = v8;
      dwCreationDisposition[0] = 2052;
      goto LABEL_35;
    }
    v13 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1064, &v24);
    v8 = v13;
    if ( v13 < 0 )
    {
      v7 = *((_QWORD *)this + 11);
      if ( !v7 )
        goto LABEL_38;
      LODWORD(dwFlagsAndAttributes) = v13;
      dwCreationDisposition[0] = 2053;
      goto LABEL_35;
    }
    v26 = 0;
    Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a3, &v26);
    v8 = Internal;
    if ( Internal < 0
      || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a3),
          v8 = Internal,
          Internal < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v7 = *((_QWORD *)this + 11);
      if ( !v7 )
        goto LABEL_38;
      LODWORD(dwFlagsAndAttributes) = v8;
      dwCreationDisposition[0] = 2055;
      goto LABEL_35;
    }
    v15 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1080, &v27);
    v8 = v15;
    if ( v15 < 0 )
    {
      v7 = *((_QWORD *)this + 11);
      if ( v7 )
      {
        LODWORD(dwFlagsAndAttributes) = v15;
        dwCreationDisposition[0] = 2056;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v25 = -1;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v11 = 0;
      if ( v8 >= 0 )
      {
LABEL_37:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
        goto LABEL_38;
      }
      LODWORD(dwFlagsAndAttributes) = v8;
      dwCreationDisposition[0] = 2050;
      v7 = *((_QWORD *)this + 11);
LABEL_35:
      v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v7,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::PopulateOemPath",
              *(_QWORD *)dwCreationDisposition,
              dwFlagsAndAttributes);
      v11 = (unsigned int)v16;
      if ( v16 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
      goto LABEL_37;
    }
  }
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  v17 = v27;
  if ( v27 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v17 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v19 = v24;
  if ( v24 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, (LPVOID)(v19 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021698  mov     [rsp-28h+arg_0], rbx
0x18002169d  push    rbp
0x18002169e  push    rsi
0x18002169f  push    rdi
0x1800216a0  push    r14
0x1800216a2  push    r15
0x1800216a4  mov     rbp, rsp
0x1800216a7  sub     rsp, 50h
0x1800216ab  mov     r15, r8
0x1800216ae  mov     r14, rdx
0x1800216b1  mov     rsi, rcx
0x1800216b4  mov     [rbp+var_10], 0
0x1800216bc  mov     [rbp+arg_18], 0
0x1800216c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800216c8  mov     [rbp+var_8], rbx
0x1800216cc  mov     rcx, [rcx+58h]
0x1800216d0  test    rdx, rdx
0x1800216d3  jnz     short loc_1800216F6
0x1800216d5  mov     eax, 80070057h
0x1800216da  mov     edi, eax
0x1800216dc  test    rcx, rcx
0x1800216df  jz      loc_180021905
0x1800216e5  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x1800216e9  mov     [rsp+50h+dwCreationDisposition], 7F4h
0x1800216f1  jmp     loc_1800218DD
0x1800216f6  test    r15, r15
0x1800216f9  jnz     short loc_18002171C
0x1800216fb  mov     eax, 80070057h
0x180021700  mov     edi, eax
0x180021702  test    rcx, rcx
0x180021705  jz      loc_180021905
0x18002170b  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x18002170f  mov     [rsp+50h+dwCreationDisposition], 7F5h
0x180021717  jmp     loc_1800218DD
0x18002171c  test    rcx, rcx
0x18002171f  jz      short loc_18002173A
0x180021721  mov     qword ptr [rsp+50h+dwCreationDisposition], r15
0x180021726  mov     r9, r14
0x180021729  lea     r8, aRecoverusbPopu; "RecoverUsb: Populating Oem Path: [%s] -"...
0x180021730  mov     edx, 2
0x180021735  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002173a  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180021743  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002174b  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x180021753  xor     r9d, r9d; lpSecurityAttributes
0x180021756  mov     edx, 80000000h; dwDesiredAccess
0x18002175b  lea     r8d, [r9+7]; dwShareMode
0x18002175f  mov     rcx, r14; lpFileName
0x180021762  call    cs:__imp_CreateFileW
0x180021768  mov     rcx, rax
0x18002176b  inc     rax
0x18002176e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180021774  jnz     short loc_1800217C2
0x180021776  mov     [rbp+var_8], rbx
0x18002177a  call    cs:__imp_GetLastError
0x180021780  mov     edi, eax
0x180021782  test    eax, eax
0x180021784  jnz     short loc_18002178D
0x180021786  mov     edi, 80004005h
0x18002178b  jmp     short loc_180021798
0x18002178d  jle     short loc_180021798
0x18002178f  movzx   edi, ax
0x180021792  or      edi, 80070000h
0x180021798  cmp     qword ptr [rsi+58h], 0
0x18002179d  jz      loc_180021905
0x1800217a3  xor     ecx, ecx
0x1800217a5  test    edi, edi
0x1800217a7  jns     loc_180021900
0x1800217ad  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], edi
0x1800217b1  mov     [rsp+50h+dwCreationDisposition], 802h
0x1800217b9  mov     rcx, [rsi+58h]
0x1800217bd  jmp     loc_1800218DD
0x1800217c2  mov     rbx, rcx
0x1800217c5  mov     [rbp+var_8], rcx
0x1800217c9  mov     [rbp+arg_8], 0
0x1800217d0  lea     rdx, [rbp+arg_8]
0x1800217d4  mov     rcx, r14
0x1800217d7  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800217dc  mov     edi, eax
0x1800217de  test    eax, eax
0x1800217e0  js      short loc_1800217F7
0x1800217e2  lea     r8, [rbp+var_10]
0x1800217e6  mov     edx, [rbp+arg_8]
0x1800217e9  mov     rcx, r14; Src
0x1800217ec  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800217f1  mov     edi, eax
0x1800217f3  test    eax, eax
0x1800217f5  jns     short loc_1800217FE
0x1800217f7  mov     ecx, eax
0x1800217f9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800217fe  mov     ecx, edi
0x180021800  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021805  test    edi, edi
0x180021807  jns     short loc_180021827
0x180021809  mov     rcx, [rsi+58h]
0x18002180d  test    rcx, rcx
0x180021810  jz      loc_180021905
0x180021816  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], edi
0x18002181a  mov     [rsp+50h+dwCreationDisposition], 804h
0x180021822  jmp     loc_1800218DD
0x180021827  lea     rcx, [rsi+428h]
0x18002182e  lea     rdx, [rbp+var_10]
0x180021832  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180021837  mov     edi, eax
0x180021839  test    eax, eax
0x18002183b  jns     short loc_18002185B
0x18002183d  mov     rcx, [rsi+58h]
0x180021841  test    rcx, rcx
0x180021844  jz      loc_180021905
0x18002184a  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x18002184e  mov     [rsp+50h+dwCreationDisposition], 805h
0x180021856  jmp     loc_1800218DD
0x18002185b  mov     [rbp+arg_8], 0
0x180021862  lea     rdx, [rbp+arg_8]
0x180021866  mov     rcx, r15
0x180021869  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002186e  mov     edi, eax
0x180021870  test    eax, eax
0x180021872  js      short loc_180021889
0x180021874  lea     r8, [rbp+arg_18]
0x180021878  mov     edx, [rbp+arg_8]
0x18002187b  mov     rcx, r15; Src
0x18002187e  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180021883  mov     edi, eax
0x180021885  test    eax, eax
0x180021887  jns     short loc_180021890
0x180021889  mov     ecx, eax
0x18002188b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021890  mov     ecx, edi
0x180021892  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021897  test    edi, edi
0x180021899  jns     short loc_1800218B2
0x18002189b  mov     rcx, [rsi+58h]
0x18002189f  test    rcx, rcx
0x1800218a2  jz      short loc_180021905
0x1800218a4  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], edi
0x1800218a8  mov     [rsp+50h+dwCreationDisposition], 807h
0x1800218b0  jmp     short loc_1800218DD
0x1800218b2  lea     rcx, [rsi+438h]
0x1800218b9  lea     rdx, [rbp+arg_18]
0x1800218bd  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x1800218c2  mov     edi, eax
0x1800218c4  test    eax, eax
0x1800218c6  jns     short loc_180021905
0x1800218c8  mov     rcx, [rsi+58h]
0x1800218cc  test    rcx, rcx
0x1800218cf  jz      short loc_180021905
0x1800218d1  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x1800218d5  mov     [rsp+50h+dwCreationDisposition], 808h
0x1800218dd  lea     r9, aCdlpactionlayo_29; "CDlpActionLayoutUsb::PopulateOemPath"
0x1800218e4  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800218eb  mov     edx, 4
0x1800218f0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800218f5  mov     ecx, eax
0x1800218f7  test    eax, eax
0x1800218f9  jns     short loc_180021900
0x1800218fb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021900  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021905  mov     ecx, edi
0x180021907  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002190c  nop
0x18002190d  lea     rax, [rbx-1]
0x180021911  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021915  ja      short loc_180021921
0x180021917  mov     rcx, rbx; hObject
0x18002191a  call    cs:__imp_CloseHandle
0x180021920  nop
0x180021921  mov     rbx, [rbp+arg_18]
0x180021925  test    rbx, rbx
0x180021928  jz      short loc_180021947
0x18002192a  call    cs:__imp_GetProcessHeap
0x180021930  mov     rcx, rax; hHeap
0x180021933  lea     r8, [rbx-4]; lpMem
0x180021937  xor     edx, edx; dwFlags
0x180021939  call    cs:__imp_HeapFree
0x18002193f  xor     ecx, ecx
0x180021941  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021946  nop
0x180021947  mov     rbx, [rbp+var_10]
0x18002194b  test    rbx, rbx
0x18002194e  jz      short loc_18002196C
0x180021950  call    cs:__imp_GetProcessHeap
0x180021956  mov     rcx, rax; hHeap
0x180021959  lea     r8, [rbx-4]; lpMem
0x18002195d  xor     edx, edx; dwFlags
0x18002195f  call    cs:__imp_HeapFree
0x180021965  xor     ecx, ecx
0x180021967  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002196c  mov     eax, edi
0x18002196e  mov     rbx, [rsp+50h+arg_0]
0x180021976  add     rsp, 50h
0x18002197a  pop     r15
0x18002197c  pop     r14
0x18002197e  pop     rdi
0x18002197f  pop     rsi
0x180021980  pop     rbp
0x180021981  retn
```
