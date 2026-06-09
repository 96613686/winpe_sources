# AcmGeneratePsdFormatId

- ea: `0x18003d724`
- end: `0x18003d93f`
- name: `AcmGeneratePsdFormatId`
- size: `539`
- prototype: `__int64 __fastcall(PUCHAR pbInput, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001e2f0`

## callees

- `0x18000bb00`
- `0x18000bfc0`
- `0x1800101b0`
- `0x180010950`
- `0x18003d724`
- `0x18006013c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d7c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d829`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d7c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d7b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d81a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d8d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d7b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d81a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d8d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d8e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d8e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d911`
- `ntdll!RtlNtStatusToDosError` at `0x18003d85d`
- `ntdll!RtlNtStatusToDosError` at `0x18003d88c`
- `ntdll!RtlNtStatusToDosError` at `0x18003d8ae`
- `ntdll!RtlNtStatusToDosError` at `0x18003d85d`
- `ntdll!RtlNtStatusToDosError` at `0x18003d88c`
- `ntdll!RtlNtStatusToDosError` at `0x18003d8ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d7d7`
- `bcrypt!BCryptCreateHash` at `0x18003d855`
- `bcrypt!BCryptCreateHash` at `0x18003d855`
- `bcrypt!BCryptHashData` at `0x18003d884`
- `bcrypt!BCryptHashData` at `0x18003d884`
- `bcrypt!BCryptFinishHash` at `0x18003d8a6`
- `bcrypt!BCryptFinishHash` at `0x18003d8a6`

## pseudocode

```c
__int64 __fastcall AcmGeneratePsdFormatId(PUCHAR pbInput, _DWORD *a2)
{
  UCHAR *v4; // rsi
  ULONG Property; // ebx
  int v6; // r9d
  size_t v7; // rdi
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  int v10; // r9d
  unsigned int v11; // ebx
  HANDLE v12; // rax
  UCHAR *v13; // r14
  NTSTATUS v14; // eax
  __int64 v15; // r8
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-8h] BYREF
  ULONG v23; // [rsp+90h] [rbp+40h] BYREF
  SIZE_T v24; // [rsp+A0h] [rbp+50h] BYREF
  SIZE_T dwBytes; // [rsp+A8h] [rbp+58h] BYREF

  hAlgorithm = 0;
  phHash = 0;
  v4 = 0;
  LODWORD(dwBytes) = 0;
  LODWORD(v24) = 0;
  v23 = 0;
  if ( pbInput && a2 )
  {
    Property = PvtBCryptOpenAlgorithmProvider(&hAlgorithm);
    if ( !Property )
    {
      Property = PvtBCryptGetProperty((int)hAlgorithm, (int)L"ObjectLength", (int)&dwBytes, v6, &v23);
      if ( !Property )
      {
        v7 = 4;
        if ( v23 == 4 )
        {
          v8 = dwBytes;
          ProcessHeap = GetProcessHeap();
          v4 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
          if ( !v4 )
          {
LABEL_7:
            Property = GetLastError();
            goto LABEL_21;
          }
          v23 = 4;
          Property = PvtBCryptGetProperty((int)hAlgorithm, (int)L"HashDigestLength", (int)&v24, v10, &v23);
          if ( !Property && v23 == 4 )
          {
            v11 = v24;
            v12 = GetProcessHeap();
            v13 = (UCHAR *)HeapAlloc(v12, 8u, v11);
            if ( !v13 )
              goto LABEL_7;
            v14 = BCryptCreateHash(hAlgorithm, &phHash, v4, dwBytes, 0, 0, 0);
            Property = RtlNtStatusToDosError(v14);
            if ( !Property )
            {
              v15 = -1;
              do
                ++v15;
              while ( *(_WORD *)&pbInput[2 * v15] );
              v16 = BCryptHashData(phHash, pbInput, 2 * v15, 0);
              Property = RtlNtStatusToDosError(v16);
              if ( !Property )
              {
                v17 = BCryptFinishHash(phHash, v13, v24, 0);
                Property = RtlNtStatusToDosError(v17);
                if ( !Property )
                {
                  *a2 = 0;
                  if ( (unsigned int)v24 <= 4 )
                    v7 = (unsigned int)v24;
                  memcpy_0(a2, v13, v7);
                }
              }
            }
            v18 = GetProcessHeap();
            HeapFree(v18, 0, v13);
          }
        }
      }
    }
  }
  else
  {
    Property = 87;
  }
LABEL_21:
  if ( phHash )
    PvtBCryptDestroyHash();
  if ( v4 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v4);
  }
  if ( hAlgorithm )
    PvtBCryptCloseAlgorithmProvider();
  return Property;
}

```

## disassembly

```asm
0x18003d724  mov     [rsp-38h+arg_8], rbx
0x18003d729  push    rbp
0x18003d72a  push    rsi
0x18003d72b  push    rdi
0x18003d72c  push    r12
0x18003d72e  push    r13
0x18003d730  push    r14
0x18003d732  push    r15
0x18003d734  mov     rbp, rsp
0x18003d737  sub     rsp, 50h
0x18003d73b  xor     r13d, r13d
0x18003d73e  mov     r15, rdx
0x18003d741  mov     [rbp+hAlgorithm], r13
0x18003d745  mov     r12, rcx
0x18003d748  mov     [rbp+phHash], r13
0x18003d74c  mov     esi, r13d
0x18003d74f  mov     dword ptr [rbp+dwBytes], r13d
0x18003d753  mov     dword ptr [rbp+arg_10], r13d
0x18003d757  mov     [rbp+arg_0], r13d
0x18003d75b  test    rcx, rcx
0x18003d75e  jz      loc_18003D8EB
0x18003d764  test    rdx, rdx
0x18003d767  jz      loc_18003D8EB
0x18003d76d  lea     rcx, [rbp+hAlgorithm]
0x18003d771  call    PvtBCryptOpenAlgorithmProvider
0x18003d776  mov     ebx, eax
0x18003d778  test    eax, eax
0x18003d77a  jnz     loc_18003D8F0
0x18003d780  mov     rcx, [rbp+hAlgorithm]; int
0x18003d784  lea     rax, [rbp+arg_0]
0x18003d788  lea     r8, [rbp+dwBytes]; int
0x18003d78c  mov     [rsp+50h+pbSecret], rax; ULONG *
0x18003d791  lea     rdx, pszProperty; "ObjectLength"
0x18003d798  call    PvtBCryptGetProperty
0x18003d79d  mov     ebx, eax
0x18003d79f  test    eax, eax
0x18003d7a1  jnz     loc_18003D8F0
0x18003d7a7  lea     edi, [rax+4]
0x18003d7aa  cmp     [rbp+arg_0], edi
0x18003d7ad  jnz     loc_18003D8F0
0x18003d7b3  mov     ebx, dword ptr [rbp+dwBytes]
0x18003d7b6  call    cs:__imp_GetProcessHeap
0x18003d7bc  lea     r14d, [r13+8]
0x18003d7c0  mov     r8d, ebx; dwBytes
0x18003d7c3  mov     rcx, rax; hHeap
0x18003d7c6  mov     edx, r14d; dwFlags
0x18003d7c9  call    cs:__imp_HeapAlloc
0x18003d7cf  mov     rsi, rax
0x18003d7d2  test    rax, rax
0x18003d7d5  jnz     short loc_18003D7E4
0x18003d7d7  call    cs:__imp_GetLastError
0x18003d7dd  mov     ebx, eax
0x18003d7df  jmp     loc_18003D8F0
0x18003d7e4  mov     rcx, [rbp+hAlgorithm]; int
0x18003d7e8  lea     rax, [rbp+arg_0]
0x18003d7ec  lea     r8, [rbp+arg_10]; int
0x18003d7f0  mov     [rsp+50h+pbSecret], rax; ULONG *
0x18003d7f5  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003d7fc  mov     [rbp+arg_0], edi
0x18003d7ff  call    PvtBCryptGetProperty
0x18003d804  mov     ebx, eax
0x18003d806  test    eax, eax
0x18003d808  jnz     loc_18003D8F0
0x18003d80e  cmp     [rbp+arg_0], edi
0x18003d811  jnz     loc_18003D8F0
0x18003d817  mov     ebx, dword ptr [rbp+arg_10]
0x18003d81a  call    cs:__imp_GetProcessHeap
0x18003d820  mov     r8d, ebx; dwBytes
0x18003d823  mov     edx, r14d; dwFlags
0x18003d826  mov     rcx, rax; hHeap
0x18003d829  call    cs:__imp_HeapAlloc
0x18003d82f  mov     r14, rax
0x18003d832  test    rax, rax
0x18003d835  jz      short loc_18003D7D7
0x18003d837  mov     r9d, dword ptr [rbp+dwBytes]; cbHashObject
0x18003d83b  lea     rdx, [rbp+phHash]; phHash
0x18003d83f  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18003d843  mov     r8, rsi; pbHashObject
0x18003d846  mov     [rsp+50h+dwFlags], r13d; dwFlags
0x18003d84b  mov     [rsp+50h+cbSecret], r13d; cbSecret
0x18003d850  mov     [rsp+50h+pbSecret], r13; pbSecret
0x18003d855  call    cs:__imp_BCryptCreateHash
0x18003d85b  mov     ecx, eax; Status
0x18003d85d  call    cs:__imp_RtlNtStatusToDosError
0x18003d863  mov     ebx, eax
0x18003d865  test    eax, eax
0x18003d867  jnz     short loc_18003D8D5
0x18003d869  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d86d  inc     r8
0x18003d870  cmp     [r12+r8*2], r13w
0x18003d875  jnz     short loc_18003D86D
0x18003d877  mov     rcx, [rbp+phHash]; hHash
0x18003d87b  add     r8d, r8d; cbInput
0x18003d87e  xor     r9d, r9d; dwFlags
0x18003d881  mov     rdx, r12; pbInput
0x18003d884  call    cs:__imp_BCryptHashData
0x18003d88a  mov     ecx, eax; Status
0x18003d88c  call    cs:__imp_RtlNtStatusToDosError
0x18003d892  mov     ebx, eax
0x18003d894  test    eax, eax
0x18003d896  jnz     short loc_18003D8D5
0x18003d898  mov     r8d, dword ptr [rbp+arg_10]; cbOutput
0x18003d89c  xor     r9d, r9d; dwFlags
0x18003d89f  mov     rcx, [rbp+phHash]; hHash
0x18003d8a3  mov     rdx, r14; pbOutput
0x18003d8a6  call    cs:__imp_BCryptFinishHash
0x18003d8ac  mov     ecx, eax; Status
0x18003d8ae  call    cs:__imp_RtlNtStatusToDosError
0x18003d8b4  mov     ebx, eax
0x18003d8b6  test    eax, eax
0x18003d8b8  jnz     short loc_18003D8D5
0x18003d8ba  xor     eax, eax
0x18003d8bc  mov     [r15], eax
0x18003d8bf  cmp     dword ptr [rbp+arg_10], edi
0x18003d8c2  ja      short loc_18003D8C7
0x18003d8c4  mov     edi, dword ptr [rbp+arg_10]
0x18003d8c7  mov     r8, rdi; Size
0x18003d8ca  mov     rdx, r14; Src
0x18003d8cd  mov     rcx, r15; void *
0x18003d8d0  call    memcpy_0
0x18003d8d5  call    cs:__imp_GetProcessHeap
0x18003d8db  mov     r8, r14; lpMem
0x18003d8de  xor     edx, edx; dwFlags
0x18003d8e0  mov     rcx, rax; hHeap
0x18003d8e3  call    cs:__imp_HeapFree
0x18003d8e9  jmp     short loc_18003D8F0
0x18003d8eb  mov     ebx, 57h ; 'W'
0x18003d8f0  mov     rcx, [rbp+phHash]
0x18003d8f4  test    rcx, rcx
0x18003d8f7  jz      short loc_18003D8FE
0x18003d8f9  call    PvtBCryptDestroyHash
0x18003d8fe  test    rsi, rsi
0x18003d901  jz      short loc_18003D917
0x18003d903  call    cs:__imp_GetProcessHeap
0x18003d909  mov     r8, rsi; lpMem
0x18003d90c  xor     edx, edx; dwFlags
0x18003d90e  mov     rcx, rax; hHeap
0x18003d911  call    cs:__imp_HeapFree
0x18003d917  mov     rcx, [rbp+hAlgorithm]
0x18003d91b  test    rcx, rcx
0x18003d91e  jz      short loc_18003D925
0x18003d920  call    PvtBCryptCloseAlgorithmProvider
0x18003d925  mov     eax, ebx
0x18003d927  mov     rbx, [rsp+50h+arg_8]
0x18003d92f  add     rsp, 50h
0x18003d933  pop     r15
0x18003d935  pop     r14
0x18003d937  pop     r13
0x18003d939  pop     r12
0x18003d93b  pop     rdi
0x18003d93c  pop     rsi
0x18003d93d  pop     rbp
0x18003d93e  retn
```
