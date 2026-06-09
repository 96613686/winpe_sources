# SplLibTelemetry::DefaultPrinterChanged(ushort const *,ushort const *,int,ulong,ushort const *,ulong)

- ea: `0x14007facc`
- end: `0x14007ff14`
- name: `?DefaultPrinterChanged@SplLibTelemetry@@SAXPEBG0HK0K@Z`
- size: `1096`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008016c`

## callees

- `0x140001c3c`
- `0x140010c4c`
- `0x1400149e8`
- `0x14002d0a0`
- `0x140056b58`
- `0x140056bb4`
- `0x140056d8c`
- `0x14005e9b4`
- `0x14007facc`
- `0x140080590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fd77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fd9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fdc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fd77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fd9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fdc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007fec8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fbf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fc5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fd63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fd8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fdb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007feb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fbf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fc5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fd63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fd8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007fdb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007feb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007fc0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007fc74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007fc0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007fc74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007fb10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007fb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007fb10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007fb70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007fde5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007fee7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007fde5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007fee7`
- `bcrypt!BCryptCreateHash` at `0x14007fcb2`
- `bcrypt!BCryptCreateHash` at `0x14007fcb2`
- `bcrypt!BCryptGetProperty` at `0x14007fbde`
- `bcrypt!BCryptGetProperty` at `0x14007fc44`
- `bcrypt!BCryptGetProperty` at `0x14007fbde`
- `bcrypt!BCryptGetProperty` at `0x14007fc44`
- `bcrypt!BCryptHashData` at `0x14007fce7`
- `bcrypt!BCryptHashData` at `0x14007fce7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14007fba4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14007fba4`
- `bcrypt!BCryptFinishHash` at `0x14007fd09`
- `bcrypt!BCryptFinishHash` at `0x14007fd09`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14007fd3c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14007fd3c`
- `bcrypt!BCryptDestroyHash` at `0x14007fd52`
- `bcrypt!BCryptDestroyHash` at `0x14007fd52`

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
      (unsigned int)byte_1400C6DB3,
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
0x14007facc  push    rbp
0x14007face  push    rbx
0x14007facf  push    rsi
0x14007fad0  push    rdi
0x14007fad1  push    r12
0x14007fad3  push    r13
0x14007fad5  push    r14
0x14007fad7  push    r15
0x14007fad9  lea     rbp, [rsp-8]
0x14007fade  sub     rsp, 108h
0x14007fae5  mov     rax, cs:__security_cookie
0x14007faec  xor     rax, rsp
0x14007faef  mov     [rbp+40h+var_50], rax
0x14007faf3  mov     ebx, r9d
0x14007faf6  mov     [rsp+140h+var_E0], r8d
0x14007fafb  mov     [rsp+140h+var_D0], ebx
0x14007faff  mov     esi, r8d
0x14007fb02  mov     r12, rdx
0x14007fb05  mov     [rbp+40h+var_B8], rdx
0x14007fb09  mov     r13, rcx
0x14007fb0c  mov     [rbp+40h+var_B0], rcx
0x14007fb10  call    cs:__imp_GetLastError
0x14007fb17  nop     dword ptr [rax+rax+00h]
0x14007fb1c  lea     rcx, [rbp+40h+var_90]; this
0x14007fb20  mov     edi, eax
0x14007fb22  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x14007fb27  xor     eax, eax
0x14007fb29  lea     r15, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14007fb30  mov     r14d, eax
0x14007fb33  mov     [rbp+40h+pbInput], r15
0x14007fb37  mov     [rbp+40h+var_A0], rax
0x14007fb3b  cmp     [rbp+40h+var_58], eax
0x14007fb3e  jl      loc_14007FDFB
0x14007fb44  lea     rdx, [rbp+40h+pbInput]; struct NCoreLibrary::TString *
0x14007fb48  lea     rcx, [rbp+40h+var_90]; this
0x14007fb4c  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x14007fb51  xor     ecx, ecx
0x14007fb53  test    eax, eax
0x14007fb55  js      loc_14007FDF7
0x14007fb5b  mov     [rbp+40h+phAlgorithm], rcx
0x14007fb5f  mov     [rsp+140h+phHash], rcx
0x14007fb64  mov     dword ptr [rsp+140h+pbOutput], ecx
0x14007fb68  mov     dword ptr [rsp+140h+var_DC], ecx
0x14007fb6c  mov     [rsp+140h+var_D8], ecx
0x14007fb70  call    cs:__imp_GetLastError
0x14007fb77  nop     dword ptr [rax+rax+00h]
0x14007fb7c  mov     r15, [rbp+40h+pbInput]
0x14007fb80  mov     ebx, eax
0x14007fb82  xor     eax, eax
0x14007fb84  test    r15, r15
0x14007fb87  jz      loc_14007FDE3
0x14007fb8d  xor     r9d, r9d; dwFlags
0x14007fb90  lea     rdx, pszAlgId; "SHA256"
0x14007fb97  xor     r8d, r8d; pszImplementation
0x14007fb9a  lea     rcx, [rbp+40h+phAlgorithm]; phAlgorithm
0x14007fb9e  mov     r13d, eax
0x14007fba1  mov     r12d, eax
0x14007fba4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14007fbab  nop     dword ptr [rax+rax+00h]
0x14007fbb0  xor     ecx, ecx
0x14007fbb2  mov     esi, eax
0x14007fbb4  test    eax, eax
0x14007fbb6  jnz     loc_14007FD31
0x14007fbbc  mov     [rsp+140h+dwFlags], ecx; dwFlags
0x14007fbc0  lea     rax, [rsp+140h+var_D8]
0x14007fbc5  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x14007fbc9  lea     r9d, [r14+4]; cbOutput
0x14007fbcd  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x14007fbd2  mov     [rsp+140h+pcbResult], rax; pcbResult
0x14007fbd7  lea     rdx, pszProperty; "ObjectLength"
0x14007fbde  call    cs:__imp_BCryptGetProperty
0x14007fbe5  nop     dword ptr [rax+rax+00h]
0x14007fbea  mov     esi, eax
0x14007fbec  test    eax, eax
0x14007fbee  jnz     loc_14007FD31
0x14007fbf4  mov     esi, dword ptr [rsp+140h+pbOutput]
0x14007fbf8  call    cs:__imp_GetProcessHeap
0x14007fbff  nop     dword ptr [rax+rax+00h]
0x14007fc04  mov     r8d, esi; dwBytes
0x14007fc07  xor     edx, edx; dwFlags
0x14007fc09  mov     rcx, rax; hHeap
0x14007fc0c  call    cs:__imp_HeapAlloc
0x14007fc13  nop     dword ptr [rax+rax+00h]
0x14007fc18  xor     ecx, ecx
0x14007fc1a  mov     r13, rax
0x14007fc1d  test    rax, rax
0x14007fc20  jz      short loc_14007FC8A
0x14007fc22  mov     [rsp+140h+dwFlags], ecx; dwFlags
0x14007fc26  lea     rax, [rsp+140h+var_D8]
0x14007fc2b  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x14007fc2f  lea     r9d, [r14+4]; cbOutput
0x14007fc33  lea     r8, [rsp+140h+var_DC]; pbOutput
0x14007fc38  mov     [rsp+140h+pcbResult], rax; pcbResult
0x14007fc3d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14007fc44  call    cs:__imp_BCryptGetProperty
0x14007fc4b  nop     dword ptr [rax+rax+00h]
0x14007fc50  mov     esi, eax
0x14007fc52  test    eax, eax
0x14007fc54  jnz     loc_14007FD31
0x14007fc5a  mov     esi, dword ptr [rsp+140h+var_DC]
0x14007fc5e  call    cs:__imp_GetProcessHeap
0x14007fc65  nop     dword ptr [rax+rax+00h]
0x14007fc6a  mov     r8d, esi; dwBytes
0x14007fc6d  lea     edx, [r14+8]; dwFlags
0x14007fc71  mov     rcx, rax; hHeap
0x14007fc74  call    cs:__imp_HeapAlloc
0x14007fc7b  nop     dword ptr [rax+rax+00h]
0x14007fc80  xor     ecx, ecx
0x14007fc82  mov     r12, rax
0x14007fc85  test    rax, rax
0x14007fc88  jnz     short loc_14007FC94
0x14007fc8a  mov     esi, 0C0000017h
0x14007fc8f  jmp     loc_14007FD31
0x14007fc94  mov     r9d, dword ptr [rsp+140h+pbOutput]; cbHashObject
0x14007fc99  lea     rdx, [rsp+140h+phHash]; phHash
0x14007fc9e  mov     [rsp+140h+var_110], ecx; dwFlags
0x14007fca2  mov     r8, r13; pbHashObject
0x14007fca5  mov     [rsp+140h+dwFlags], ecx; cbSecret
0x14007fca9  mov     [rsp+140h+pcbResult], rcx; pbSecret
0x14007fcae  mov     rcx, [rbp+40h+phAlgorithm]; hAlgorithm
0x14007fcb2  call    cs:__imp_BCryptCreateHash
0x14007fcb9  nop     dword ptr [rax+rax+00h]
0x14007fcbe  xor     ecx, ecx
0x14007fcc0  mov     esi, eax
0x14007fcc2  test    eax, eax
0x14007fcc4  jnz     short loc_14007FD31
0x14007fcc6  or      r8, 0FFFFFFFFFFFFFFFFh
0x14007fcca  inc     r8
0x14007fccd  cmp     [r15+r8*2], cx
0x14007fcd2  jnz     short loc_14007FCCA
0x14007fcd4  mov     rcx, [rsp+140h+phHash]; hHash
0x14007fcd9  lea     r8d, ds:2[r8*2]; cbInput
0x14007fce1  xor     r9d, r9d; dwFlags
0x14007fce4  mov     rdx, r15; pbInput
0x14007fce7  call    cs:__imp_BCryptHashData
0x14007fcee  nop     dword ptr [rax+rax+00h]
0x14007fcf3  mov     esi, eax
0x14007fcf5  test    eax, eax
0x14007fcf7  jnz     short loc_14007FD31
0x14007fcf9  mov     r8d, dword ptr [rsp+140h+var_DC]; cbOutput
0x14007fcfe  xor     r9d, r9d; dwFlags
0x14007fd01  mov     rcx, [rsp+140h+phHash]; hHash
0x14007fd06  mov     rdx, r12; pbOutput
0x14007fd09  call    cs:__imp_BCryptFinishHash
0x14007fd10  nop     dword ptr [rax+rax+00h]
0x14007fd15  mov     esi, eax
0x14007fd17  test    eax, eax
0x14007fd19  jnz     short loc_14007FD31
0x14007fd1b  mov     edx, dword ptr [rsp+140h+var_DC]; unsigned int
0x14007fd1f  lea     r8, [rbp+40h+var_A0]; unsigned __int16 **
0x14007fd23  mov     rcx, r12; unsigned __int8 *
0x14007fd26  call    ?WriteHexString@@YAJPEAEKPEAPEAG@Z; WriteHexString(uchar *,ulong,ushort * *)
0x14007fd2b  mov     r14, [rbp+40h+var_A0]
0x14007fd2f  mov     esi, eax
0x14007fd31  mov     rcx, [rbp+40h+phAlgorithm]; hAlgorithm
0x14007fd35  test    rcx, rcx
0x14007fd38  jz      short loc_14007FD48
0x14007fd3a  xor     edx, edx; dwFlags
0x14007fd3c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14007fd43  nop     dword ptr [rax+rax+00h]
0x14007fd48  mov     rcx, [rsp+140h+phHash]; hHash
0x14007fd4d  test    rcx, rcx
0x14007fd50  jz      short loc_14007FD5E
0x14007fd52  call    cs:__imp_BCryptDestroyHash
0x14007fd59  nop     dword ptr [rax+rax+00h]
0x14007fd5e  test    r13, r13
0x14007fd61  jz      short loc_14007FD83
0x14007fd63  call    cs:__imp_GetProcessHeap
0x14007fd6a  nop     dword ptr [rax+rax+00h]
0x14007fd6f  mov     r8, r13; lpMem
0x14007fd72  xor     edx, edx; dwFlags
0x14007fd74  mov     rcx, rax; hHeap
0x14007fd77  call    cs:__imp_HeapFree
0x14007fd7e  nop     dword ptr [rax+rax+00h]
0x14007fd83  xor     r13d, r13d
0x14007fd86  test    r12, r12
0x14007fd89  jz      short loc_14007FDAB
0x14007fd8b  call    cs:__imp_GetProcessHeap
0x14007fd92  nop     dword ptr [rax+rax+00h]
0x14007fd97  mov     r8, r12; lpMem
0x14007fd9a  xor     edx, edx; dwFlags
0x14007fd9c  mov     rcx, rax; hHeap
0x14007fd9f  call    cs:__imp_HeapFree
0x14007fda6  nop     dword ptr [rax+rax+00h]
0x14007fdab  test    esi, esi
0x14007fdad  jz      short loc_14007FDD7
0x14007fdaf  test    r14, r14
0x14007fdb2  jz      short loc_14007FDD7
0x14007fdb4  call    cs:__imp_GetProcessHeap
0x14007fdbb  nop     dword ptr [rax+rax+00h]
0x14007fdc0  mov     r8, r14; lpMem
0x14007fdc3  xor     edx, edx; dwFlags
0x14007fdc5  mov     rcx, rax; hHeap
0x14007fdc8  call    cs:__imp_HeapFree
0x14007fdcf  nop     dword ptr [rax+rax+00h]
0x14007fdd4  mov     r14, r13
0x14007fdd7  mov     esi, [rsp+140h+var_E0]
0x14007fddb  mov     r12, [rbp+40h+var_B8]
0x14007fddf  mov     r13, [rbp+40h+var_B0]
0x14007fde3  mov     ecx, ebx; dwErrCode
0x14007fde5  call    cs:__imp_SetLastError
0x14007fdec  nop     dword ptr [rax+rax+00h]
0x14007fdf1  mov     ebx, [rsp+140h+var_D0]
0x14007fdf5  jmp     short loc_14007FDFB
0x14007fdf7  mov     r15, [rbp+40h+pbInput]
0x14007fdfb  call    ?Provider@SplLibLogging@@SAPEBU_tlgProvider_t@@XZ; SplLibLogging::Provider(void)
0x14007fe00  mov     r8, rax
0x14007fe03  mov     ecx, [rax]
0x14007fe05  cmp     ecx, 5
0x14007fe08  jbe     loc_14007FEAF
0x14007fe0e  mov     rdx, 200000000000h
0x14007fe18  mov     rcx, rax
0x14007fe1b  call    _tlgKeywordOn
0x14007fe20  test    al, al
0x14007fe22  jz      loc_14007FEAF
0x14007fe28  mov     rax, [rbp+40h+arg_20]
0x14007fe2c  lea     rdx, byte_1400C6DB3
0x14007fe33  mov     ecx, [rbp+40h+arg_28]
0x14007fe36  mov     [rbp+40h+var_A0], rax
0x14007fe3a  lea     rax, [rsp+140h+var_D0]
0x14007fe3f  mov     [rsp+140h+var_E8], rax
0x14007fe44  lea     rax, [rbp+40h+var_A0]
0x14007fe48  mov     [rsp+140h+var_F0], rax
0x14007fe4d  lea     rax, [rbp+40h+pbInput]
0x14007fe51  mov     [rsp+140h+var_F8], rax
0x14007fe56  lea     rax, [rsp+140h+var_D8]
0x14007fe5b  mov     [rsp+140h+var_100], rax
0x14007fe60  lea     rax, [rsp+140h+var_E0]
0x14007fe65  mov     [rsp+140h+var_108], rax
0x14007fe6a  lea     rax, [rbp+40h+var_B0]
0x14007fe6e  mov     qword ptr [rsp+140h+var_110], rax
0x14007fe73  lea     rax, [rbp+40h+var_B8]
0x14007fe77  mov     qword ptr [rsp+140h+dwFlags], rax
0x14007fe7c  lea     rax, [rsp+140h+phHash]
0x14007fe81  mov     [rsp+140h+var_D0], ecx
0x14007fe85  mov     rcx, r8
0x14007fe88  mov     [rsp+140h+pcbResult], rax
0x14007fe8d  mov     [rbp+40h+pbInput], r14
0x14007fe91  mov     [rsp+140h+var_D8], ebx
0x14007fe95  mov     [rsp+140h+var_E0], esi
0x14007fe99  mov     [rbp+40h+var_B0], r12
0x14007fe9d  mov     [rbp+40h+var_B8], r13
0x14007fea1  mov     [rsp+140h+phHash], 1000000h
0x14007feaa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14007feaf  test    r14, r14
0x14007feb2  jz      short loc_14007FED4
0x14007feb4  call    cs:__imp_GetProcessHeap
0x14007febb  nop     dword ptr [rax+rax+00h]
0x14007fec0  mov     r8, r14; lpMem
0x14007fec3  xor     edx, edx; dwFlags
0x14007fec5  mov     rcx, rax; hHeap
0x14007fec8  call    cs:__imp_HeapFree
0x14007fecf  nop     dword ptr [rax+rax+00h]
0x14007fed4  mov     rdx, r15; void *
0x14007fed7  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14007fedc  lea     rcx, [rbp+40h+var_90]; this
0x14007fee0  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x14007fee5  mov     ecx, edi; dwErrCode
0x14007fee7  call    cs:__imp_SetLastError
0x14007feee  nop     dword ptr [rax+rax+00h]
0x14007fef3  mov     rcx, [rbp+40h+var_50]
0x14007fef7  xor     rcx, rsp; StackCookie
0x14007fefa  call    __security_check_cookie
0x14007feff  add     rsp, 108h
0x14007ff06  pop     r15
0x14007ff08  pop     r14
0x14007ff0a  pop     r13
0x14007ff0c  pop     r12
0x14007ff0e  pop     rdi
0x14007ff0f  pop     rsi
0x14007ff10  pop     rbx
0x14007ff11  pop     rbp
0x14007ff12  retn
```
