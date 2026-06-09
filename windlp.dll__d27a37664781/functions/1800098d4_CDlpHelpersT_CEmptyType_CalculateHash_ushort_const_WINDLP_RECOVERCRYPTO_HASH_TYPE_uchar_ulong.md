# CDlpHelpersT<CEmptyType>::CalculateHash(ushort const *,WINDLP_RECOVERCRYPTO_HASH_TYPE,uchar *,ulong)

- ea: `0x1800098d4`
- end: `0x180009c04`
- name: `?CalculateHash@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGW4WINDLP_RECOVERCRYPTO_HASH_TYPE@@PEAEK@Z`
- size: `816`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002e31c`

## callees

- `0x1800097ec`
- `0x1800098d4`
- `0x18000aba4`
- `0x18001fd60`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800099ab`
- `bcrypt!BCryptGetProperty` at `0x1800099ab`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180009966`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180009966`
- `bcrypt!BCryptFinishHash` at `0x180009b60`
- `bcrypt!BCryptFinishHash` at `0x180009b60`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180009b9c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180009b9c`
- `bcrypt!BCryptDestroyHash` at `0x180009bb3`
- `bcrypt!BCryptDestroyHash` at `0x180009bb3`
- `bcrypt!BCryptHashData` at `0x180009b28`
- `bcrypt!BCryptHashData` at `0x180009b28`
- `bcrypt!BCryptCreateHash` at `0x1800099f1`
- `bcrypt!BCryptCreateHash` at `0x1800099f1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009b03`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009b03`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180009a80`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180009a80`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009be8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bce`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpHelpersT<CEmptyType>::CalculateHash(LPCWSTR lpFileName, int a2, UCHAR *a3, ULONG a4)
{
  void *v7; // rsi
  __int64 v8; // rbx
  char *v9; // r14
  const WCHAR *v10; // rdx
  NTSTATUS v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  NTSTATUS Property; // eax
  NTSTATUS v15; // eax
  HANDLE ProcessHeap; // rax
  DWORD LowPart; // r15d
  LPVOID v18; // rax
  char *FileW; // rax
  signed int LastError; // eax
  union _LARGE_INTEGER i; // rdi
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  int v24; // eax
  HANDLE v25; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-45h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-41h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-39h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-31h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-29h] BYREF
  LPVOID v33; // [rsp+68h] [rbp-21h]
  __int64 v34; // [rsp+70h] [rbp-19h]
  _OVERLAPPED Overlapped; // [rsp+78h] [rbp-11h] BYREF
  int v36; // [rsp+F8h] [rbp+6Fh] BYREF

  v7 = 0;
  v33 = 0;
  NumberOfBytesRead = 0;
  v8 = -1;
  v34 = -1;
  v9 = 0;
  FileSize.QuadPart = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  phHash = 0;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v36 = 0;
  if ( a2 == 1 )
  {
    v10 = L"SHA256";
  }
  else
  {
    if ( a2 )
      goto LABEL_31;
    v10 = L"SHA1";
  }
  if ( !lpFileName || !a3 )
    goto LABEL_31;
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, v10, 0, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v11, &v36) )
    goto LABEL_8;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(Property, &v36) )
    goto LABEL_8;
  if ( *(_DWORD *)pbOutput != a4 )
  {
LABEL_31:
    v13 = 2147942487LL;
    v12 = -2147024809;
    goto LABEL_32;
  }
  v15 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v15, &v36) )
  {
LABEL_8:
    v12 = v36;
LABEL_9:
    v13 = v12;
LABEL_32:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    goto LABEL_33;
  }
  ProcessHeap = GetProcessHeap();
  LowPart = 0x100000;
  v18 = HeapAlloc(ProcessHeap, 0, 0x100000u);
  v7 = v18;
  if ( !v18 )
  {
    v12 = -2147024882;
    goto LABEL_9;
  }
  v33 = v18;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (v8 = (__int64)FileW, v34 = (__int64)FileW, !GetFileSizeEx(FileW, &FileSize)) )
  {
LABEL_17:
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
LABEL_18:
      v12 = -2147467259;
    }
    goto LABEL_9;
  }
  for ( i = FileSize; i.QuadPart > 0; i.QuadPart -= NumberOfBytesRead )
  {
    if ( LowPart > i.QuadPart )
      LowPart = i.LowPart;
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.hEvent = 0;
    Overlapped.Pointer = v9;
    if ( !ReadFile((HANDLE)v8, v7, LowPart, &NumberOfBytesRead, &Overlapped) )
      goto LABEL_17;
    if ( LowPart != NumberOfBytesRead )
      goto LABEL_18;
    v22 = BCryptHashData(phHash, (PUCHAR)v7, NumberOfBytesRead, 0);
    if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v22, &v36) )
      goto LABEL_8;
    v9 += NumberOfBytesRead;
  }
  v23 = BCryptFinishHash(phHash, a3, a4, 0);
  v24 = SErrorConverter::C_NtStatus2HR(v23, &v36);
  v12 = v36;
  if ( !v24 )
    goto LABEL_9;
LABEL_33:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  if ( v7 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v7);
  }
  return v12;
}

```

## disassembly

```asm
0x1800098d4  push    rbp
0x1800098d6  push    rbx
0x1800098d7  push    rsi
0x1800098d8  push    rdi
0x1800098d9  push    r12
0x1800098db  push    r13
0x1800098dd  push    r14
0x1800098df  push    r15
0x1800098e1  lea     rbp, [rsp-1Fh]
0x1800098e6  sub     rsp, 0A8h
0x1800098ed  mov     r12d, r9d
0x1800098f0  mov     r13, r8
0x1800098f3  mov     rdi, rcx
0x1800098f6  xor     esi, esi
0x1800098f8  mov     [rbp+57h+var_78], rsi
0x1800098fc  mov     [rbp+57h+NumberOfBytesRead], esi
0x1800098ff  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009903  mov     [rbp+57h+var_70], rbx
0x180009907  xor     r14d, r14d
0x18000990a  mov     qword ptr [rbp+57h+FileSize], r14
0x18000990e  xorps   xmm0, xmm0
0x180009911  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180009915  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180009919  mov     [rbp+57h+phHash], r14
0x18000991d  mov     [rbp+57h+phAlgorithm], r14
0x180009921  mov     dword ptr [rbp+57h+pbOutput], r14d
0x180009925  mov     [rbp+57h+var_88], r14d
0x180009929  mov     [rbp+57h+arg_8], r14d
0x18000992d  cmp     edx, 1
0x180009930  jnz     short loc_18000993B
0x180009932  lea     rdx, aSha256; "SHA256"
0x180009939  jmp     short loc_18000994A
0x18000993b  test    edx, edx
0x18000993d  jnz     loc_180009B7D
0x180009943  lea     rdx, pszAlgId; "SHA1"
0x18000994a  test    rdi, rdi
0x18000994d  jz      loc_180009B7D
0x180009953  test    r13, r13
0x180009956  jz      loc_180009B7D
0x18000995c  xor     r9d, r9d; dwFlags
0x18000995f  xor     r8d, r8d; pszImplementation
0x180009962  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180009966  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000996c  mov     ecx, eax; int
0x18000996e  lea     rdx, [rbp+57h+arg_8]; int *
0x180009972  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180009977  test    eax, eax
0x180009979  jnz     short loc_180009985
0x18000997b  mov     edi, [rbp+57h+arg_8]
0x18000997e  mov     ecx, edi
0x180009980  jmp     loc_180009B84
0x180009985  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18000998d  lea     rax, [rbp+57h+var_88]
0x180009991  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180009996  mov     r9d, 4; cbOutput
0x18000999c  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800099a0  lea     rdx, pszProperty; "HashDigestLength"
0x1800099a7  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800099ab  call    cs:__imp_BCryptGetProperty
0x1800099b1  mov     ecx, eax; int
0x1800099b3  lea     rdx, [rbp+57h+arg_8]; int *
0x1800099b7  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800099bc  test    eax, eax
0x1800099be  jz      short loc_18000997B
0x1800099c0  cmp     dword ptr [rbp+57h+pbOutput], r12d
0x1800099c4  jnz     loc_180009B7D
0x1800099ca  mov     [rsp+0E0h+var_B0], 0; dwFlags
0x1800099d2  mov     [rsp+0E0h+dwFlags], 0; cbSecret
0x1800099da  mov     [rsp+0E0h+pcbResult], 0; pbSecret
0x1800099e3  xor     r9d, r9d; cbHashObject
0x1800099e6  xor     r8d, r8d; pbHashObject
0x1800099e9  lea     rdx, [rbp+57h+phHash]; phHash
0x1800099ed  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800099f1  call    cs:__imp_BCryptCreateHash
0x1800099f7  mov     ecx, eax; int
0x1800099f9  lea     rdx, [rbp+57h+arg_8]; int *
0x1800099fd  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180009a02  test    eax, eax
0x180009a04  jz      loc_18000997B
0x180009a0a  call    cs:__imp_GetProcessHeap
0x180009a10  mov     rcx, rax; hHeap
0x180009a13  mov     r15d, 100000h
0x180009a19  mov     r8d, r15d; dwBytes
0x180009a1c  xor     edx, edx; dwFlags
0x180009a1e  call    cs:__imp_HeapAlloc
0x180009a24  mov     rsi, rax
0x180009a27  test    rax, rax
0x180009a2a  jnz     short loc_180009A36
0x180009a2c  mov     edi, 8007000Eh
0x180009a31  jmp     loc_18000997E
0x180009a36  mov     [rbp+57h+var_78], rsi
0x180009a3a  mov     qword ptr [rsp+0E0h+var_B0], 0; hTemplateFile
0x180009a43  mov     [rsp+0E0h+dwFlags], 8000000h; dwFlagsAndAttributes
0x180009a4b  mov     dword ptr [rsp+0E0h+pcbResult], 3; dwCreationDisposition
0x180009a53  xor     r9d, r9d; lpSecurityAttributes
0x180009a56  mov     edx, 80000000h; dwDesiredAccess
0x180009a5b  lea     r8d, [r9+7]; dwShareMode
0x180009a5f  mov     rcx, rdi; lpFileName
0x180009a62  call    cs:__imp_CreateFileW
0x180009a68  lea     rcx, [rax-1]
0x180009a6c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180009a70  ja      short loc_180009A8A
0x180009a72  mov     rbx, rax
0x180009a75  mov     [rbp+57h+var_70], rax
0x180009a79  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x180009a7d  mov     rcx, rax; hFile
0x180009a80  call    cs:__imp_GetFileSizeEx
0x180009a86  test    eax, eax
0x180009a88  jnz     short loc_180009AB4
0x180009a8a  call    cs:__imp_GetLastError
0x180009a90  test    eax, eax
0x180009a92  mov     edi, eax
0x180009a94  jnz     short loc_180009AA0
0x180009a96  mov     edi, 80004005h
0x180009a9b  jmp     loc_18000997E
0x180009aa0  jle     loc_18000997E
0x180009aa6  movzx   edi, ax
0x180009aa9  or      edi, 80070000h
0x180009aaf  jmp     loc_18000997E
0x180009ab4  mov     rdi, qword ptr [rbp+57h+FileSize]
0x180009ab8  jmp     loc_180009B4A
0x180009abd  mov     eax, r15d
0x180009ac0  cmp     rax, rdi
0x180009ac3  cmovg   r15d, edi
0x180009ac7  mov     [rbp+57h+Overlapped.Internal], 0
0x180009acf  mov     [rbp+57h+Overlapped.InternalHigh], 0
0x180009ad7  mov     [rbp+57h+Overlapped.hEvent], 0
0x180009adf  mov     dword ptr [rbp+57h+Overlapped.10h], r14d
0x180009ae3  mov     rax, r14
0x180009ae6  shr     rax, 20h
0x180009aea  mov     dword ptr [rbp+57h+Overlapped.10h+4], eax
0x180009aed  lea     rax, [rbp+57h+Overlapped]
0x180009af1  mov     [rsp+0E0h+pcbResult], rax; lpOverlapped
0x180009af6  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009afa  mov     r8d, r15d; nNumberOfBytesToRead
0x180009afd  mov     rdx, rsi; lpBuffer
0x180009b00  mov     rcx, rbx; hFile
0x180009b03  call    cs:__imp_ReadFile
0x180009b09  test    eax, eax
0x180009b0b  jz      loc_180009A8A
0x180009b11  mov     r8d, [rbp+57h+NumberOfBytesRead]; cbInput
0x180009b15  cmp     r15d, r8d
0x180009b18  jnz     loc_180009A96
0x180009b1e  xor     r9d, r9d; dwFlags
0x180009b21  mov     rdx, rsi; pbInput
0x180009b24  mov     rcx, [rbp+57h+phHash]; hHash
0x180009b28  call    cs:__imp_BCryptHashData
0x180009b2e  mov     ecx, eax; int
0x180009b30  lea     rdx, [rbp+57h+arg_8]; int *
0x180009b34  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180009b39  test    eax, eax
0x180009b3b  jz      loc_18000997B
0x180009b41  mov     eax, [rbp+57h+NumberOfBytesRead]
0x180009b44  add     r14, rax
0x180009b47  sub     rdi, rax
0x180009b4a  test    rdi, rdi
0x180009b4d  jg      loc_180009ABD
0x180009b53  xor     r9d, r9d; dwFlags
0x180009b56  mov     r8d, r12d; cbOutput
0x180009b59  mov     rdx, r13; pbOutput
0x180009b5c  mov     rcx, [rbp+57h+phHash]; hHash
0x180009b60  call    cs:__imp_BCryptFinishHash
0x180009b66  mov     ecx, eax; int
0x180009b68  lea     rdx, [rbp+57h+arg_8]; int *
0x180009b6c  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180009b71  mov     edi, [rbp+57h+arg_8]
0x180009b74  test    eax, eax
0x180009b76  jnz     short loc_180009B89
0x180009b78  jmp     loc_18000997E
0x180009b7d  mov     ecx, 80070057h
0x180009b82  mov     edi, ecx
0x180009b84  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180009b89  mov     ecx, edi
0x180009b8b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180009b90  nop
0x180009b91  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180009b95  test    rcx, rcx
0x180009b98  jz      short loc_180009BAA
0x180009b9a  xor     edx, edx; dwFlags
0x180009b9c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180009ba2  mov     [rbp+57h+phAlgorithm], 0
0x180009baa  mov     rcx, [rbp+57h+phHash]; hHash
0x180009bae  test    rcx, rcx
0x180009bb1  jz      short loc_180009BC1
0x180009bb3  call    cs:__imp_BCryptDestroyHash
0x180009bb9  mov     [rbp+57h+phHash], 0
0x180009bc1  lea     rax, [rbx-1]
0x180009bc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009bc9  ja      short loc_180009BD5
0x180009bcb  mov     rcx, rbx; hObject
0x180009bce  call    cs:__imp_CloseHandle
0x180009bd4  nop
0x180009bd5  test    rsi, rsi
0x180009bd8  jz      short loc_180009BEE
0x180009bda  call    cs:__imp_GetProcessHeap
0x180009be0  mov     rcx, rax; hHeap
0x180009be3  mov     r8, rsi; lpMem
0x180009be6  xor     edx, edx; dwFlags
0x180009be8  call    cs:__imp_HeapFree
0x180009bee  mov     eax, edi
0x180009bf0  add     rsp, 0A8h
0x180009bf7  pop     r15
0x180009bf9  pop     r14
0x180009bfb  pop     r13
0x180009bfd  pop     r12
0x180009bff  pop     rdi
0x180009c00  pop     rsi
0x180009c01  pop     rbx
0x180009c02  pop     rbp
0x180009c03  retn
```
