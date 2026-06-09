# SplLibTelemetry::DefaultPrinterChanged(ushort const *,ushort const *,int,ulong,ushort const *,ulong)

- ea: `0x1400786b0`
- end: `0x140078a67`
- name: `?DefaultPrinterChanged@SplLibTelemetry@@SAXPEBG0HK0K@Z`
- size: `951`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140078ce8`

## callees

- `0x140001c24`
- `0x14000fa4c`
- `0x140013788`
- `0x14002abc0`
- `0x140051bd4`
- `0x140051c2c`
- `0x140051de4`
- `0x140059208`
- `0x1400786b0`
- `0x1400790c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140078901`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007891d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007893a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140078a28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140078901`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007891d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007893a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140078a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400787c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140078818`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400788f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007890f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007892c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140078a1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400787c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140078818`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400788f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007890f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007892c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140078a1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400787d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140078828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400787d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140078828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400786f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007874e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400786f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007874e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140078951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140078a41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140078951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140078a41`
- `bcrypt!BCryptCreateHash` at `0x140078860`
- `bcrypt!BCryptCreateHash` at `0x140078860`
- `bcrypt!BCryptGetProperty` at `0x1400787b0`
- `bcrypt!BCryptGetProperty` at `0x140078804`
- `bcrypt!BCryptGetProperty` at `0x1400787b0`
- `bcrypt!BCryptGetProperty` at `0x140078804`
- `bcrypt!BCryptHashData` at `0x14007888f`
- `bcrypt!BCryptHashData` at `0x14007888f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14007877c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14007877c`
- `bcrypt!BCryptFinishHash` at `0x1400788ab`
- `bcrypt!BCryptFinishHash` at `0x1400788ab`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400788d8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400788d8`
- `bcrypt!BCryptDestroyHash` at `0x1400788e8`
- `bcrypt!BCryptDestroyHash` at `0x1400788e8`

## pseudocode

```c
void __fastcall SplLibTelemetry::DefaultPrinterChanged(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        ULONG a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  ULONG v6; // ebx
  int v7; // esi
  const unsigned __int16 *v8; // r12
  const unsigned __int16 *v9; // r13
  DWORD LastError; // edi
  int v11; // edx
  int v12; // r8d
  UCHAR *v13; // r15
  unsigned __int16 *v14; // r14
  DWORD v15; // eax
  DWORD v16; // ebx
  UCHAR *v17; // r13
  UCHAR *v18; // r12
  NTSTATUS Property; // esi
  unsigned int v20; // esi
  HANDLE ProcessHeap; // rax
  unsigned int v22; // esi
  HANDLE v23; // rax
  __int64 v24; // r8
  NTSTATUS v25; // eax
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  const struct _tlgProvider_t *v29; // rax
  NCoreLibrary::TString *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  HANDLE v33; // rax
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  UCHAR v35[4]; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v38; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-88h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v41; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v42; // [rsp+90h] [rbp-70h] BYREF
  PUCHAR pbInput; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[56]; // [rsp+B0h] [rbp-50h] BYREF
  int v46; // [rsp+E8h] [rbp-18h]

  v6 = a4;
  v34 = a3;
  v38 = a4;
  v7 = a3;
  v8 = a2;
  v41 = a2;
  v9 = a1;
  v42 = a1;
  LastError = GetLastError();
  NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v45, v11, v12);
  v13 = (UCHAR *)&NCoreLibrary::TString::gszNullState;
  v14 = 0;
  pbInput = (PUCHAR)&NCoreLibrary::TString::gszNullState;
  v44[0] = 0;
  if ( v46 >= 0 )
  {
    if ( NSecurityLibrary::TSidUserContext::GetSidAsString(
           (NSecurityLibrary::TSidUserContext *)v45,
           (struct NCoreLibrary::TString *)&pbInput) < 0 )
    {
      v13 = pbInput;
      goto LABEL_30;
    }
    phAlgorithm = 0;
    phHash = 0;
    *(_DWORD *)pbOutput = 0;
    *(_DWORD *)v35 = 0;
    pcbResult = 0;
    v15 = GetLastError();
    v13 = pbInput;
    v16 = v15;
    if ( !pbInput )
      goto LABEL_28;
    v17 = 0;
    v18 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
    if ( !Property )
    {
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( !Property )
      {
        v20 = *(_DWORD *)pbOutput;
        ProcessHeap = GetProcessHeap();
        v17 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v20);
        if ( !v17 )
        {
LABEL_9:
          Property = -1073741801;
          goto LABEL_16;
        }
        Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v35, 4u, &pcbResult, 0);
        if ( !Property )
        {
          v22 = *(_DWORD *)v35;
          v23 = GetProcessHeap();
          v18 = (UCHAR *)HeapAlloc(v23, 8u, v22);
          if ( v18 )
          {
            Property = BCryptCreateHash(phAlgorithm, &phHash, v17, *(ULONG *)pbOutput, 0, 0, 0);
            if ( !Property )
            {
              v24 = -1;
              do
                ++v24;
              while ( *(_WORD *)&v13[2 * v24] );
              Property = BCryptHashData(phHash, v13, 2 * v24 + 2, 0);
              if ( !Property )
              {
                Property = BCryptFinishHash(phHash, v18, *(ULONG *)v35, 0);
                if ( !Property )
                {
                  v25 = WriteHexString(v18, *(unsigned int *)v35, v44);
                  v14 = v44[0];
                  Property = v25;
                }
              }
            }
            goto LABEL_16;
          }
          goto LABEL_9;
        }
      }
    }
LABEL_16:
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( v17 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v17);
    }
    if ( v18 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v18);
    }
    if ( Property && v14 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v14);
      v14 = 0;
    }
    v7 = v34;
    v8 = v41;
    v9 = v42;
LABEL_28:
    SetLastError(v16);
    v6 = v38;
  }
LABEL_30:
  v29 = SplLibLogging::Provider();
  v30 = (NCoreLibrary::TString *)*(unsigned int *)v29;
  if ( (unsigned int)v30 > 5 && (unsigned __int8)tlgKeywordOn(v29, 0x200000000000LL, v29) )
  {
    v44[0] = a5;
    v38 = a6;
    pbInput = (PUCHAR)v14;
    pcbResult = v6;
    v34 = v7;
    v42 = v8;
    v41 = v9;
    phHash = (BCRYPT_HASH_HANDLE)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v31,
      (unsigned int)byte_1400BFDC3,
      v31,
      v32,
      (__int64)&phHash,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v34,
      (__int64)&pcbResult,
      (__int64)&pbInput,
      (__int64)v44,
      (__int64)&v38);
  }
  if ( v14 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v14);
  }
  NCoreLibrary::TString::vFree(v30, v13);
  NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v45);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x1400786b0  push    rbp
0x1400786b2  push    rbx
0x1400786b3  push    rsi
0x1400786b4  push    rdi
0x1400786b5  push    r12
0x1400786b7  push    r13
0x1400786b9  push    r14
0x1400786bb  push    r15
0x1400786bd  lea     rbp, [rsp-8]
0x1400786c2  sub     rsp, 108h
0x1400786c9  mov     rax, cs:__security_cookie
0x1400786d0  xor     rax, rsp
0x1400786d3  mov     [rbp+40h+var_50], rax
0x1400786d7  mov     ebx, r9d
0x1400786da  mov     [rsp+140h+var_E0], r8d
0x1400786df  mov     [rsp+140h+var_D0], ebx
0x1400786e3  mov     esi, r8d
0x1400786e6  mov     r12, rdx
0x1400786e9  mov     [rbp+40h+var_B8], rdx
0x1400786ed  mov     r13, rcx
0x1400786f0  mov     [rbp+40h+var_B0], rcx
0x1400786f4  call    cs:__imp_GetLastError
0x1400786fa  lea     rcx, [rbp+40h+var_90]; this
0x1400786fe  mov     edi, eax
0x140078700  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x140078705  xor     eax, eax
0x140078707  lea     r15, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14007870e  mov     r14d, eax
0x140078711  mov     [rbp+40h+pbInput], r15
0x140078715  mov     [rbp+40h+var_A0], rax
0x140078719  cmp     [rbp+40h+var_58], eax
0x14007871c  jl      loc_140078961
0x140078722  lea     rdx, [rbp+40h+pbInput]; struct NCoreLibrary::TString *
0x140078726  lea     rcx, [rbp+40h+var_90]; this
0x14007872a  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x14007872f  xor     ecx, ecx
0x140078731  test    eax, eax
0x140078733  js      loc_14007895D
0x140078739  mov     [rbp+40h+phAlgorithm], rcx
0x14007873d  mov     [rsp+140h+phHash], rcx
0x140078742  mov     dword ptr [rsp+140h+pbOutput], ecx
0x140078746  mov     dword ptr [rsp+140h+var_DC], ecx
0x14007874a  mov     [rsp+140h+var_D8], ecx
0x14007874e  call    cs:__imp_GetLastError
0x140078754  mov     r15, [rbp+40h+pbInput]
0x140078758  mov     ebx, eax
0x14007875a  xor     eax, eax
0x14007875c  test    r15, r15
0x14007875f  jz      loc_14007894F
0x140078765  xor     r9d, r9d; dwFlags
0x140078768  lea     rdx, pszAlgId; "SHA256"
0x14007876f  xor     r8d, r8d; pszImplementation
0x140078772  lea     rcx, [rbp+40h+phAlgorithm]; phAlgorithm
0x140078776  mov     r13d, eax
0x140078779  mov     r12d, eax
0x14007877c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140078782  xor     ecx, ecx
0x140078784  mov     esi, eax
0x140078786  test    eax, eax
0x140078788  jnz     loc_1400788CD
0x14007878e  mov     [rsp+140h+dwFlags], ecx; dwFlags
0x140078792  lea     rax, [rsp+140h+var_D8]
0x140078797  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x14007879b  lea     r9d, [r14+4]; cbOutput
0x14007879f  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x1400787a4  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1400787a9  lea     rdx, pszProperty; "ObjectLength"
0x1400787b0  call    cs:__imp_BCryptGetProperty
0x1400787b6  mov     esi, eax
0x1400787b8  test    eax, eax
0x1400787ba  jnz     loc_1400788CD
0x1400787c0  mov     esi, dword ptr [rsp+140h+pbOutput]
0x1400787c4  call    cs:__imp_GetProcessHeap
0x1400787ca  mov     r8d, esi; dwBytes
0x1400787cd  xor     edx, edx; dwFlags
0x1400787cf  mov     rcx, rax; hHeap
0x1400787d2  call    cs:__imp_HeapAlloc
0x1400787d8  xor     ecx, ecx
0x1400787da  mov     r13, rax
0x1400787dd  test    rax, rax
0x1400787e0  jz      short loc_140078838
0x1400787e2  mov     [rsp+140h+dwFlags], ecx; dwFlags
0x1400787e6  lea     rax, [rsp+140h+var_D8]
0x1400787eb  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x1400787ef  lea     r9d, [r14+4]; cbOutput
0x1400787f3  lea     r8, [rsp+140h+var_DC]; pbOutput
0x1400787f8  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1400787fd  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140078804  call    cs:__imp_BCryptGetProperty
0x14007880a  mov     esi, eax
0x14007880c  test    eax, eax
0x14007880e  jnz     loc_1400788CD
0x140078814  mov     esi, dword ptr [rsp+140h+var_DC]
0x140078818  call    cs:__imp_GetProcessHeap
0x14007881e  mov     r8d, esi; dwBytes
0x140078821  lea     edx, [r14+8]; dwFlags
0x140078825  mov     rcx, rax; hHeap
0x140078828  call    cs:__imp_HeapAlloc
0x14007882e  xor     ecx, ecx
0x140078830  mov     r12, rax
0x140078833  test    rax, rax
0x140078836  jnz     short loc_140078842
0x140078838  mov     esi, 0C0000017h
0x14007883d  jmp     loc_1400788CD
0x140078842  mov     r9d, dword ptr [rsp+140h+pbOutput]; cbHashObject
0x140078847  lea     rdx, [rsp+140h+phHash]; phHash
0x14007884c  mov     [rsp+140h+var_110], ecx; dwFlags
0x140078850  mov     r8, r13; pbHashObject
0x140078853  mov     [rsp+140h+dwFlags], ecx; cbSecret
0x140078857  mov     [rsp+140h+pcbResult], rcx; pbSecret
0x14007885c  mov     rcx, [rbp+40h+phAlgorithm]; hAlgorithm
0x140078860  call    cs:__imp_BCryptCreateHash
0x140078866  xor     ecx, ecx
0x140078868  mov     esi, eax
0x14007886a  test    eax, eax
0x14007886c  jnz     short loc_1400788CD
0x14007886e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140078872  inc     r8
0x140078875  cmp     [r15+r8*2], cx
0x14007887a  jnz     short loc_140078872
0x14007887c  mov     rcx, [rsp+140h+phHash]; hHash
0x140078881  lea     r8d, ds:2[r8*2]; cbInput
0x140078889  xor     r9d, r9d; dwFlags
0x14007888c  mov     rdx, r15; pbInput
0x14007888f  call    cs:__imp_BCryptHashData
0x140078895  mov     esi, eax
0x140078897  test    eax, eax
0x140078899  jnz     short loc_1400788CD
0x14007889b  mov     r8d, dword ptr [rsp+140h+var_DC]; cbOutput
0x1400788a0  xor     r9d, r9d; dwFlags
0x1400788a3  mov     rcx, [rsp+140h+phHash]; hHash
0x1400788a8  mov     rdx, r12; pbOutput
0x1400788ab  call    cs:__imp_BCryptFinishHash
0x1400788b1  mov     esi, eax
0x1400788b3  test    eax, eax
0x1400788b5  jnz     short loc_1400788CD
0x1400788b7  mov     edx, dword ptr [rsp+140h+var_DC]; unsigned int
0x1400788bb  lea     r8, [rbp+40h+var_A0]; unsigned __int16 **
0x1400788bf  mov     rcx, r12; unsigned __int8 *
0x1400788c2  call    ?WriteHexString@@YAJPEAEKPEAPEAG@Z; WriteHexString(uchar *,ulong,ushort * *)
0x1400788c7  mov     r14, [rbp+40h+var_A0]
0x1400788cb  mov     esi, eax
0x1400788cd  mov     rcx, [rbp+40h+phAlgorithm]; hAlgorithm
0x1400788d1  test    rcx, rcx
0x1400788d4  jz      short loc_1400788DE
0x1400788d6  xor     edx, edx; dwFlags
0x1400788d8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400788de  mov     rcx, [rsp+140h+phHash]; hHash
0x1400788e3  test    rcx, rcx
0x1400788e6  jz      short loc_1400788EE
0x1400788e8  call    cs:__imp_BCryptDestroyHash
0x1400788ee  test    r13, r13
0x1400788f1  jz      short loc_140078907
0x1400788f3  call    cs:__imp_GetProcessHeap
0x1400788f9  mov     r8, r13; lpMem
0x1400788fc  xor     edx, edx; dwFlags
0x1400788fe  mov     rcx, rax; hHeap
0x140078901  call    cs:__imp_HeapFree
0x140078907  xor     r13d, r13d
0x14007890a  test    r12, r12
0x14007890d  jz      short loc_140078923
0x14007890f  call    cs:__imp_GetProcessHeap
0x140078915  mov     r8, r12; lpMem
0x140078918  xor     edx, edx; dwFlags
0x14007891a  mov     rcx, rax; hHeap
0x14007891d  call    cs:__imp_HeapFree
0x140078923  test    esi, esi
0x140078925  jz      short loc_140078943
0x140078927  test    r14, r14
0x14007892a  jz      short loc_140078943
0x14007892c  call    cs:__imp_GetProcessHeap
0x140078932  mov     r8, r14; lpMem
0x140078935  xor     edx, edx; dwFlags
0x140078937  mov     rcx, rax; hHeap
0x14007893a  call    cs:__imp_HeapFree
0x140078940  mov     r14, r13
0x140078943  mov     esi, [rsp+140h+var_E0]
0x140078947  mov     r12, [rbp+40h+var_B8]
0x14007894b  mov     r13, [rbp+40h+var_B0]
0x14007894f  mov     ecx, ebx; dwErrCode
0x140078951  call    cs:__imp_SetLastError
0x140078957  mov     ebx, [rsp+140h+var_D0]
0x14007895b  jmp     short loc_140078961
0x14007895d  mov     r15, [rbp+40h+pbInput]
0x140078961  call    ?Provider@SplLibLogging@@SAPEBU_tlgProvider_t@@XZ; SplLibLogging::Provider(void)
0x140078966  mov     r8, rax
0x140078969  mov     ecx, [rax]
0x14007896b  cmp     ecx, 5
0x14007896e  jbe     loc_140078A15
0x140078974  mov     rdx, 200000000000h
0x14007897e  mov     rcx, rax
0x140078981  call    _tlgKeywordOn
0x140078986  test    al, al
0x140078988  jz      loc_140078A15
0x14007898e  mov     rax, [rbp+40h+arg_20]
0x140078992  lea     rdx, byte_1400BFDC3
0x140078999  mov     ecx, [rbp+40h+arg_28]
0x14007899c  mov     [rbp+40h+var_A0], rax
0x1400789a0  lea     rax, [rsp+140h+var_D0]
0x1400789a5  mov     [rsp+140h+var_E8], rax
0x1400789aa  lea     rax, [rbp+40h+var_A0]
0x1400789ae  mov     [rsp+140h+var_F0], rax
0x1400789b3  lea     rax, [rbp+40h+pbInput]
0x1400789b7  mov     [rsp+140h+var_F8], rax
0x1400789bc  lea     rax, [rsp+140h+var_D8]
0x1400789c1  mov     [rsp+140h+var_100], rax
0x1400789c6  lea     rax, [rsp+140h+var_E0]
0x1400789cb  mov     [rsp+140h+var_108], rax
0x1400789d0  lea     rax, [rbp+40h+var_B0]
0x1400789d4  mov     qword ptr [rsp+140h+var_110], rax
0x1400789d9  lea     rax, [rbp+40h+var_B8]
0x1400789dd  mov     qword ptr [rsp+140h+dwFlags], rax
0x1400789e2  lea     rax, [rsp+140h+phHash]
0x1400789e7  mov     [rsp+140h+var_D0], ecx
0x1400789eb  mov     rcx, r8
0x1400789ee  mov     [rsp+140h+pcbResult], rax
0x1400789f3  mov     [rbp+40h+pbInput], r14
0x1400789f7  mov     [rsp+140h+var_D8], ebx
0x1400789fb  mov     [rsp+140h+var_E0], esi
0x1400789ff  mov     [rbp+40h+var_B0], r12
0x140078a03  mov     [rbp+40h+var_B8], r13
0x140078a07  mov     [rsp+140h+phHash], 1000000h
0x140078a10  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140078a15  test    r14, r14
0x140078a18  jz      short loc_140078A2E
0x140078a1a  call    cs:__imp_GetProcessHeap
0x140078a20  mov     r8, r14; lpMem
0x140078a23  xor     edx, edx; dwFlags
0x140078a25  mov     rcx, rax; hHeap
0x140078a28  call    cs:__imp_HeapFree
0x140078a2e  mov     rdx, r15; void *
0x140078a31  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x140078a36  lea     rcx, [rbp+40h+var_90]; this
0x140078a3a  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140078a3f  mov     ecx, edi; dwErrCode
0x140078a41  call    cs:__imp_SetLastError
0x140078a47  mov     rcx, [rbp+40h+var_50]
0x140078a4b  xor     rcx, rsp; StackCookie
0x140078a4e  call    __security_check_cookie
0x140078a53  add     rsp, 108h
0x140078a5a  pop     r15
0x140078a5c  pop     r14
0x140078a5e  pop     r13
0x140078a60  pop     r12
0x140078a62  pop     rdi
0x140078a63  pop     rsi
0x140078a64  pop     rbx
0x140078a65  pop     rbp
0x140078a66  retn
```
