# BfspIsHashInSecurityDatabase

- ea: `0x1800377a0`
- end: `0x1800379ae`
- name: `BfspIsHashInSecurityDatabase`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800379b4`

## callees

- `0x1800377a0`
- `0x1800385a0`
- `0x18007ec76`
- `0x18007ed40`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800378b0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800378b0`
- `bcrypt!BCryptFinishHash` at `0x180037905`
- `bcrypt!BCryptFinishHash` at `0x180037905`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180037927`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180037927`
- `bcrypt!BCryptDestroyHash` at `0x180037916`
- `bcrypt!BCryptDestroyHash` at `0x180037916`
- `bcrypt!BCryptHashData` at `0x1800378ea`
- `bcrypt!BCryptHashData` at `0x1800378ea`
- `bcrypt!BCryptCreateHash` at `0x1800378d1`
- `bcrypt!BCryptCreateHash` at `0x1800378d1`
- `ntdll!RtlNtStatusToDosError` at `0x18003786d`
- `ntdll!RtlNtStatusToDosError` at `0x18003792f`
- `ntdll!RtlNtStatusToDosError` at `0x18003786d`
- `ntdll!RtlNtStatusToDosError` at `0x18003792f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003796f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003796f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003797d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003797d`

## pseudocode

```c
__int64 __fastcall BfspIsHashInSecurityDatabase(int a1, __int64 a2, _DWORD *a3)
{
  ULONG v3; // ebx
  int v6; // ecx
  NTSTATUS v7; // eax
  const WCHAR *v8; // rcx
  unsigned int i; // edi
  ULONG v10; // r12d
  UCHAR *v11; // r13
  int v12; // ebx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  char *dwFlags; // [rsp+30h] [rbp-29h]
  BCRYPT_HASH_HANDLE *p_phHash; // [rsp+38h] [rbp-21h]
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+7h]
  char v23; // [rsp+68h] [rbp+Fh] BYREF
  UCHAR pbOutput[24]; // [rsp+70h] [rbp+17h] BYREF

  v3 = 0;
  v21 = 0;
  LODWORD(v18) = 0;
  lpMem = 0;
  LODWORD(phAlgorithm) = 0;
  *a3 = 0;
  if ( a1 )
  {
    v6 = a1 - 1;
    if ( !v6 )
    {
      v7 = SbpParseSignatureDatabase(L"dbDefault", (LPGUID)EfiGlobalVariable, (__int64)&v21, (__int64)&v18, 0, 0);
      goto LABEL_9;
    }
    if ( v6 != 1 )
    {
      v7 = -1073741811;
LABEL_10:
      v3 = RtlNtStatusToDosError(v7);
      goto LABEL_24;
    }
    p_phHash = &phHash;
    v8 = L"dbx";
    dwFlags = &v23;
  }
  else
  {
    p_phHash = 0;
    v8 = L"db";
    dwFlags = 0;
  }
  v7 = SbpParseSignatureDatabase(
         v8,
         (LPGUID)&EfiImageSecurityDatabaseVariable,
         (__int64)&v21,
         (__int64)&v18,
         (__int64)dwFlags,
         (__int64)p_phHash);
LABEL_9:
  if ( v7 < 0 )
    goto LABEL_10;
  for ( i = 0; i < (unsigned int)v18; ++i )
  {
    phHash = 0;
    phAlgorithm = 0;
    v10 = *(_DWORD *)(v21 + 16LL * i);
    v11 = *(UCHAR **)(v21 + 16LL * i + 8);
    BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
    v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v12 >= 0 )
    {
      v12 = BCryptHashData(phHash, v11, v10, 0);
      if ( v12 >= 0 )
        v12 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v3 = RtlNtStatusToDosError(v12);
    if ( v3 )
      break;
    v3 = 0;
    if ( !memcmp_0(pbOutput, *(const void **)(a2 + 8), *(unsigned int *)(a2 + 4)) )
    {
      *a3 = 1;
      break;
    }
  }
LABEL_24:
  v13 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
  }
  return v3;
}

```

## disassembly

```asm
0x1800377a0  mov     [rsp-8+arg_0], rbx
0x1800377a5  mov     [rsp-8+arg_8], rdi
0x1800377aa  push    rbp
0x1800377ab  push    r12
0x1800377ad  push    r13
0x1800377af  push    r14
0x1800377b1  push    r15
0x1800377b3  lea     rbp, [rsp-37h]
0x1800377b8  sub     rsp, 90h
0x1800377bf  mov     rax, cs:__security_cookie
0x1800377c6  xor     rax, rsp
0x1800377c9  mov     [rbp+57h+var_28], rax
0x1800377cd  xor     ebx, ebx
0x1800377cf  mov     r14, r8
0x1800377d2  mov     [rbp+57h+var_58], rbx
0x1800377d6  mov     r15, rdx
0x1800377d9  mov     dword ptr [rbp+57h+var_70], ebx
0x1800377dc  mov     [rbp+57h+lpMem], rbx
0x1800377e0  mov     dword ptr [rbp+57h+phAlgorithm], ebx
0x1800377e3  mov     [r8], ebx
0x1800377e6  test    ecx, ecx
0x1800377e8  jz      short loc_180037830
0x1800377ea  sub     ecx, 1
0x1800377ed  jz      short loc_180037816
0x1800377ef  cmp     ecx, 1
0x1800377f2  jz      short loc_1800377FB
0x1800377f4  mov     eax, 0C000000Dh
0x1800377f9  jmp     short loc_18003786B
0x1800377fb  lea     rax, [rbp+57h+phHash]
0x1800377ff  mov     [rsp+0B0h+var_78], rax
0x180037804  lea     rcx, aDbx; "dbx"
0x18003780b  lea     rax, [rbp+57h+var_48]
0x18003780f  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180037814  jmp     short loc_180037841
0x180037816  mov     [rsp+0B0h+var_78], rbx
0x18003781b  lea     rdx, EfiGlobalVariable
0x180037822  mov     qword ptr [rsp+0B0h+dwFlags], rbx
0x180037827  lea     rcx, aDbdefault; "dbDefault"
0x18003782e  jmp     short loc_180037848
0x180037830  mov     [rsp+0B0h+var_78], rbx; __int64
0x180037835  lea     rcx, aDb; "db"
0x18003783c  mov     qword ptr [rsp+0B0h+dwFlags], rbx; __int64
0x180037841  lea     rdx, EfiImageSecurityDatabaseVariable; VendorGuid
0x180037848  lea     rax, [rbp+57h+var_70]
0x18003784c  mov     qword ptr [rsp+0B0h+cbSecret], rax; __int64
0x180037851  lea     r9, [rbp+57h+phAlgorithm]
0x180037855  lea     rax, [rbp+57h+var_58]
0x180037859  lea     r8, [rbp+57h+lpMem]
0x18003785d  mov     [rsp+0B0h+pbSecret], rax; __int64
0x180037862  call    SbpParseSignatureDatabase
0x180037867  test    eax, eax
0x180037869  jns     short loc_18003787A
0x18003786b  mov     ecx, eax; Status
0x18003786d  call    cs:__imp_RtlNtStatusToDosError
0x180037873  mov     ebx, eax
0x180037875  jmp     loc_180037966
0x18003787a  mov     edi, ebx
0x18003787c  cmp     dword ptr [rbp+57h+var_70], ebx
0x18003787f  jbe     loc_180037966
0x180037885  mov     rcx, [rbp+57h+var_58]
0x180037889  lea     rdx, pszAlgId; "SHA1"
0x180037890  mov     eax, edi
0x180037892  xor     r9d, r9d; dwFlags
0x180037895  add     rax, rax
0x180037898  mov     [rbp+57h+phHash], rbx
0x18003789c  xor     r8d, r8d; pszImplementation
0x18003789f  mov     [rbp+57h+phAlgorithm], rbx
0x1800378a3  mov     r12d, [rcx+rax*8]
0x1800378a7  mov     r13, [rcx+rax*8+8]
0x1800378ac  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800378b0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800378b6  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800378ba  lea     rdx, [rbp+57h+phHash]; phHash
0x1800378be  mov     [rsp+0B0h+dwFlags], ebx; dwFlags
0x1800378c2  xor     r9d, r9d; cbHashObject
0x1800378c5  mov     [rsp+0B0h+cbSecret], ebx; cbSecret
0x1800378c9  xor     r8d, r8d; pbHashObject
0x1800378cc  mov     [rsp+0B0h+pbSecret], rbx; pbSecret
0x1800378d1  call    cs:__imp_BCryptCreateHash
0x1800378d7  mov     ebx, eax
0x1800378d9  test    eax, eax
0x1800378db  js      short loc_18003790D
0x1800378dd  mov     rcx, [rbp+57h+phHash]; hHash
0x1800378e1  xor     r9d, r9d; dwFlags
0x1800378e4  mov     r8d, r12d; cbInput
0x1800378e7  mov     rdx, r13; pbInput
0x1800378ea  call    cs:__imp_BCryptHashData
0x1800378f0  mov     ebx, eax
0x1800378f2  test    eax, eax
0x1800378f4  js      short loc_18003790D
0x1800378f6  mov     rcx, [rbp+57h+phHash]; hHash
0x1800378fa  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x1800378fe  xor     r9d, r9d; dwFlags
0x180037901  lea     r8d, [r9+14h]; cbOutput
0x180037905  call    cs:__imp_BCryptFinishHash
0x18003790b  mov     ebx, eax
0x18003790d  mov     rcx, [rbp+57h+phHash]; hHash
0x180037911  test    rcx, rcx
0x180037914  jz      short loc_18003791C
0x180037916  call    cs:__imp_BCryptDestroyHash
0x18003791c  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180037920  test    rcx, rcx
0x180037923  jz      short loc_18003792D
0x180037925  xor     edx, edx; dwFlags
0x180037927  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003792d  mov     ecx, ebx; Status
0x18003792f  call    cs:__imp_RtlNtStatusToDosError
0x180037935  mov     ebx, eax
0x180037937  test    eax, eax
0x180037939  jnz     short loc_180037966
0x18003793b  mov     r8d, [r15+4]; Size
0x18003793f  lea     rcx, [rbp+57h+pbOutput]; Buf1
0x180037943  mov     rdx, [r15+8]; Buf2
0x180037947  call    memcmp_0
0x18003794c  xor     ebx, ebx
0x18003794e  test    eax, eax
0x180037950  jz      short loc_18003795F
0x180037952  inc     edi
0x180037954  cmp     edi, dword ptr [rbp+57h+var_70]
0x180037957  jb      loc_180037885
0x18003795d  jmp     short loc_180037966
0x18003795f  mov     dword ptr [r14], 1
0x180037966  mov     rdi, [rbp+57h+lpMem]
0x18003796a  test    rdi, rdi
0x18003796d  jz      short loc_180037983
0x18003796f  call    cs:__imp_GetProcessHeap
0x180037975  mov     r8, rdi; lpMem
0x180037978  xor     edx, edx; dwFlags
0x18003797a  mov     rcx, rax; hHeap
0x18003797d  call    cs:__imp_HeapFree
0x180037983  mov     eax, ebx
0x180037985  mov     rcx, [rbp+57h+var_28]
0x180037989  xor     rcx, rsp; StackCookie
0x18003798c  call    __security_check_cookie
0x180037991  lea     r11, [rsp+0B0h+var_20]
0x180037999  mov     rbx, [r11+30h]
0x18003799d  mov     rdi, [r11+38h]
0x1800379a1  mov     rsp, r11
0x1800379a4  pop     r15
0x1800379a6  pop     r14
0x1800379a8  pop     r13
0x1800379aa  pop     r12
0x1800379ac  pop     rbp
0x1800379ad  retn
```
