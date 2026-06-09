# AcmGenerateConnectionHashId

- ea: `0x180007320`
- end: `0x1800076ba`
- name: `AcmGenerateConnectionHashId`
- size: `922`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbInput)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007090`
- `0x180007160`
- `0x18003d5b4`

## callees

- `0x180007320`
- `0x18006013c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000745a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000745a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007569`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007577`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007577`
- `ntdll!RtlNtStatusToDosError` at `0x1800073bb`
- `ntdll!RtlNtStatusToDosError` at `0x18000742c`
- `ntdll!RtlNtStatusToDosError` at `0x180007491`
- `ntdll!RtlNtStatusToDosError` at `0x1800074bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800074ef`
- `ntdll!RtlNtStatusToDosError` at `0x18000752d`
- `ntdll!RtlNtStatusToDosError` at `0x18000755e`
- `ntdll!RtlNtStatusToDosError` at `0x1800075b6`
- `ntdll!RtlNtStatusToDosError` at `0x180007612`
- `ntdll!RtlNtStatusToDosError` at `0x18000763e`
- `ntdll!RtlNtStatusToDosError` at `0x1800073bb`
- `ntdll!RtlNtStatusToDosError` at `0x18000742c`
- `ntdll!RtlNtStatusToDosError` at `0x180007491`
- `ntdll!RtlNtStatusToDosError` at `0x1800074bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800074ef`
- `ntdll!RtlNtStatusToDosError` at `0x18000752d`
- `ntdll!RtlNtStatusToDosError` at `0x18000755e`
- `ntdll!RtlNtStatusToDosError` at `0x1800075b6`
- `ntdll!RtlNtStatusToDosError` at `0x180007612`
- `ntdll!RtlNtStatusToDosError` at `0x18000763e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007676`
- `bcrypt!BCryptCreateHash` at `0x180007489`
- `bcrypt!BCryptCreateHash` at `0x180007489`
- `bcrypt!BCryptHashData` at `0x1800074b3`
- `bcrypt!BCryptHashData` at `0x1800074e7`
- `bcrypt!BCryptHashData` at `0x180007525`
- `bcrypt!BCryptHashData` at `0x18000760a`
- `bcrypt!BCryptHashData` at `0x180007636`
- `bcrypt!BCryptHashData` at `0x1800074b3`
- `bcrypt!BCryptHashData` at `0x1800074e7`
- `bcrypt!BCryptHashData` at `0x180007525`
- `bcrypt!BCryptHashData` at `0x18000760a`
- `bcrypt!BCryptHashData` at `0x180007636`
- `bcrypt!BCryptGetProperty` at `0x1800073b3`
- `bcrypt!BCryptGetProperty` at `0x180007424`
- `bcrypt!BCryptGetProperty` at `0x1800073b3`
- `bcrypt!BCryptGetProperty` at `0x180007424`
- `bcrypt!BCryptFinishHash` at `0x1800075ae`
- `bcrypt!BCryptFinishHash` at `0x1800075ae`
- `bcrypt!BCryptDestroyHash` at `0x180007556`
- `bcrypt!BCryptDestroyHash` at `0x180007556`

## pseudocode

```c
__int64 __fastcall AcmGenerateConnectionHashId(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbInput, __int64 a3, _OWORD *a4)
{
  UCHAR *v8; // r15
  NTSTATUS Property; // eax
  ULONG LastError; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  HANDLE v15; // rax
  void *v16; // r12
  NTSTATUS v17; // eax
  size_t v18; // rsi
  NTSTATUS v19; // eax
  int v20; // ecx
  NTSTATUS v21; // eax
  UCHAR *v22; // rdx
  __int64 v23; // r8
  ULONG v24; // r8d
  NTSTATUS v25; // eax
  HANDLE v26; // rax
  NTSTATUS v27; // eax
  HANDLE v28; // rax
  NTSTATUS v30; // eax
  size_t v31; // rax
  int v32; // ecx
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  int v35; // ecx
  int v36; // ecx
  UCHAR v37[4]; // [rsp+40h] [rbp-20h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-1Ch] BYREF
  BOOL v39; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+90h] [rbp+30h] BYREF

  v39 = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v37 = 0;
  pcbResult = 0;
  if ( !hAlgorithm || !pbInput || !a3 || !a4 || *(_DWORD *)(a3 + 520) > 0x20u )
    return 87;
  v8 = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  LastError = RtlNtStatusToDosError(Property);
  if ( !LastError && pcbResult == 4 )
  {
    v11 = *(_DWORD *)pbOutput;
    ProcessHeap = GetProcessHeap();
    v8 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v11);
    if ( !v8 )
    {
      LastError = GetLastError();
      goto LABEL_21;
    }
    pcbResult = 4;
    v13 = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v37, 4u, &pcbResult, 0);
    LastError = RtlNtStatusToDosError(v13);
    if ( LastError || pcbResult != 4 )
      goto LABEL_21;
    v14 = *(_DWORD *)v37;
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 8u, v14);
    if ( !v16 )
    {
      LastError = GetLastError();
      goto LABEL_21;
    }
    v17 = BCryptCreateHash(hAlgorithm, &phHash, v8, *(ULONG *)pbOutput, 0, 0, 0);
    LastError = RtlNtStatusToDosError(v17);
    if ( LastError )
      goto LABEL_20;
    v18 = 16;
    v19 = BCryptHashData(phHash, pbInput, 0x10u, 0);
    LastError = RtlNtStatusToDosError(v19);
    if ( LastError )
      goto LABEL_20;
    v20 = *(_DWORD *)(a3 + 4);
    if ( v20 )
    {
      v32 = v20 - 1;
      if ( !v32 || (v35 = v32 - 1) == 0 || (v36 = v35 - 1) == 0 )
      {
        v33 = BCryptHashData(phHash, (PUCHAR)(a3 + 524), *(_DWORD *)(a3 + 520), 0);
        LastError = RtlNtStatusToDosError(v33);
        if ( !LastError )
        {
          v34 = BCryptHashData(phHash, (PUCHAR)(a3 + 556), 4u, 0);
          LastError = RtlNtStatusToDosError(v34);
          if ( !LastError )
          {
            v22 = (UCHAR *)&v39;
            v24 = 4;
            v39 = *(_DWORD *)(a3 + 588) != 0;
            goto LABEL_19;
          }
        }
LABEL_20:
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v16);
        goto LABEL_21;
      }
      if ( v36 != 1 )
      {
        LastError = 87;
        goto LABEL_20;
      }
    }
    v21 = BCryptHashData(phHash, (PUCHAR)(a3 + 524), *(_DWORD *)(a3 + 520), 0);
    LastError = RtlNtStatusToDosError(v21);
    if ( !LastError )
    {
      v22 = (UCHAR *)(a3 + 8);
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)&v22[2 * v23] );
      v24 = 2 * v23;
LABEL_19:
      v25 = BCryptHashData(phHash, v22, v24, 0);
      LastError = RtlNtStatusToDosError(v25);
      if ( !LastError )
      {
        v30 = BCryptFinishHash(phHash, (PUCHAR)v16, *(ULONG *)v37, 0);
        LastError = RtlNtStatusToDosError(v30);
        if ( !LastError )
        {
          v31 = *(unsigned int *)v37;
          *a4 = 0;
          if ( (unsigned int)v31 <= 0x10 )
            v18 = v31;
          memcpy_0(a4, v16, v18);
        }
      }
      goto LABEL_20;
    }
    goto LABEL_20;
  }
LABEL_21:
  if ( phHash )
  {
    v27 = BCryptDestroyHash(phHash);
    RtlNtStatusToDosError(v27);
  }
  if ( v8 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v8);
  }
  return LastError;
}

```

## disassembly

```asm
0x180007320  mov     r11, rsp
0x180007323  mov     [r11+18h], rbx
0x180007327  mov     [r11+20h], rsi
0x18000732b  push    rbp
0x18000732c  push    rdi
0x18000732d  push    r12
0x18000732f  push    r13
0x180007331  push    r14
0x180007333  mov     rbp, rsp
0x180007336  sub     rsp, 60h
0x18000733a  xor     r12d, r12d
0x18000733d  mov     r13, r9
0x180007340  mov     [rbp+var_18], r12d
0x180007344  mov     rdi, r8
0x180007347  mov     [rbp+phHash], r12
0x18000734b  mov     r14, rdx
0x18000734e  mov     dword ptr [rbp+pbOutput], r12d
0x180007352  mov     rsi, rcx
0x180007355  mov     dword ptr [rbp+var_20], r12d
0x180007359  mov     [rbp+arg_0], r12d
0x18000735d  test    rcx, rcx
0x180007360  jz      loc_1800076B0
0x180007366  test    rdx, rdx
0x180007369  jz      loc_1800076B0
0x18000736f  test    r8, r8
0x180007372  jz      loc_1800076B0
0x180007378  test    r9, r9
0x18000737b  jz      loc_1800076B0
0x180007381  cmp     dword ptr [r8+208h], 20h ; ' '
0x180007389  ja      loc_1800076B0
0x18000738f  lea     rax, [rbp+arg_0]
0x180007393  mov     [r11+10h], r15
0x180007397  mov     [r11-60h], r12d
0x18000739b  lea     r8, [rbp+pbOutput]; pbOutput
0x18000739f  mov     r9d, 4; cbOutput
0x1800073a5  mov     [r11-68h], rax
0x1800073a9  lea     rdx, pszProperty; "ObjectLength"
0x1800073b0  mov     r15d, r12d
0x1800073b3  call    cs:__imp_BCryptGetProperty
0x1800073b9  mov     ecx, eax; Status
0x1800073bb  call    cs:__imp_RtlNtStatusToDosError
0x1800073c1  mov     ebx, eax
0x1800073c3  test    eax, eax
0x1800073c5  jnz     loc_18000754D
0x1800073cb  cmp     [rbp+arg_0], 4
0x1800073cf  jnz     loc_18000754D
0x1800073d5  mov     ebx, dword ptr [rbp+pbOutput]
0x1800073d8  call    cs:__imp_GetProcessHeap
0x1800073de  mov     r8d, ebx; dwBytes
0x1800073e1  mov     edx, 8; dwFlags
0x1800073e6  mov     rcx, rax; hHeap
0x1800073e9  call    cs:__imp_HeapAlloc
0x1800073ef  mov     r15, rax
0x1800073f2  test    rax, rax
0x1800073f5  jz      loc_180007669
0x1800073fb  lea     rax, [rbp+arg_0]
0x1800073ff  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x180007404  mov     r9d, 4; cbOutput
0x18000740a  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18000740f  lea     r8, [rbp+var_20]; pbOutput
0x180007413  mov     [rbp+arg_0], 4
0x18000741a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180007421  mov     rcx, rsi; hObject
0x180007424  call    cs:__imp_BCryptGetProperty
0x18000742a  mov     ecx, eax; Status
0x18000742c  call    cs:__imp_RtlNtStatusToDosError
0x180007432  mov     ebx, eax
0x180007434  test    eax, eax
0x180007436  jnz     loc_18000754D
0x18000743c  cmp     [rbp+arg_0], 4
0x180007440  jnz     loc_18000754D
0x180007446  mov     ebx, dword ptr [rbp+var_20]
0x180007449  call    cs:__imp_GetProcessHeap
0x18000744f  mov     r8d, ebx; dwBytes
0x180007452  mov     edx, 8; dwFlags
0x180007457  mov     rcx, rax; hHeap
0x18000745a  call    cs:__imp_HeapAlloc
0x180007460  mov     r12, rax
0x180007463  test    rax, rax
0x180007466  jz      loc_180007676
0x18000746c  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180007470  lea     rdx, [rbp+phHash]; phHash
0x180007474  xor     eax, eax
0x180007476  mov     r8, r15; pbHashObject
0x180007479  mov     [rsp+60h+var_30], eax; dwFlags
0x18000747d  mov     rcx, rsi; hAlgorithm
0x180007480  mov     [rsp+60h+dwFlags], eax; cbSecret
0x180007484  mov     [rsp+60h+pcbResult], rax; pbSecret
0x180007489  call    cs:__imp_BCryptCreateHash
0x18000748f  mov     ecx, eax; Status
0x180007491  call    cs:__imp_RtlNtStatusToDosError
0x180007497  mov     ebx, eax
0x180007499  test    eax, eax
0x18000749b  jnz     loc_180007539
0x1800074a1  mov     rcx, [rbp+phHash]; hHash
0x1800074a5  mov     esi, 10h
0x1800074aa  mov     r8d, esi; cbInput
0x1800074ad  xor     r9d, r9d; dwFlags
0x1800074b0  mov     rdx, r14; pbInput
0x1800074b3  call    cs:__imp_BCryptHashData
0x1800074b9  mov     ecx, eax; Status
0x1800074bb  call    cs:__imp_RtlNtStatusToDosError
0x1800074c1  mov     ebx, eax
0x1800074c3  test    eax, eax
0x1800074c5  jnz     short loc_180007539
0x1800074c7  mov     ecx, [rdi+4]
0x1800074ca  test    ecx, ecx
0x1800074cc  jnz     loc_1800075EC
0x1800074d2  mov     r8d, [rdi+208h]; cbInput
0x1800074d9  lea     rdx, [rdi+20Ch]; pbInput
0x1800074e0  mov     rcx, [rbp+phHash]; hHash
0x1800074e4  xor     r9d, r9d; dwFlags
0x1800074e7  call    cs:__imp_BCryptHashData
0x1800074ed  mov     ecx, eax; Status
0x1800074ef  call    cs:__imp_RtlNtStatusToDosError
0x1800074f5  mov     ebx, eax
0x1800074f7  test    eax, eax
0x1800074f9  jnz     short loc_180007539
0x1800074fb  lea     rdx, [rdi+8]; pbInput
0x1800074ff  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180007506  nop     word ptr [rax+rax+00000000h]
0x180007510  inc     r8
0x180007513  cmp     word ptr [rdx+r8*2], 0
0x180007519  jnz     short loc_180007510
0x18000751b  add     r8d, r8d; cbInput
0x18000751e  mov     rcx, [rbp+phHash]; hHash
0x180007522  xor     r9d, r9d; dwFlags
0x180007525  call    cs:__imp_BCryptHashData
0x18000752b  mov     ecx, eax; Status
0x18000752d  call    cs:__imp_RtlNtStatusToDosError
0x180007533  mov     ebx, eax
0x180007535  test    eax, eax
0x180007537  jz      short loc_1800075A0
0x180007539  call    cs:__imp_GetProcessHeap
0x18000753f  mov     r8, r12; lpMem
0x180007542  xor     edx, edx; dwFlags
0x180007544  mov     rcx, rax; hHeap
0x180007547  call    cs:__imp_HeapFree
0x18000754d  mov     rcx, [rbp+phHash]; hHash
0x180007551  test    rcx, rcx
0x180007554  jz      short loc_180007564
0x180007556  call    cs:__imp_BCryptDestroyHash
0x18000755c  mov     ecx, eax; Status
0x18000755e  call    cs:__imp_RtlNtStatusToDosError
0x180007564  test    r15, r15
0x180007567  jz      short loc_18000757D
0x180007569  call    cs:__imp_GetProcessHeap
0x18000756f  mov     r8, r15; lpMem
0x180007572  xor     edx, edx; dwFlags
0x180007574  mov     rcx, rax; hHeap
0x180007577  call    cs:__imp_HeapFree
0x18000757d  mov     r15, [rsp+60h+arg_8]
0x180007585  mov     eax, ebx
0x180007587  lea     r11, [rsp+60h+var_s0]
0x18000758c  mov     rbx, [r11+40h]
0x180007590  mov     rsi, [r11+48h]
0x180007594  mov     rsp, r11
0x180007597  pop     r14
0x180007599  pop     r13
0x18000759b  pop     r12
0x18000759d  pop     rdi
0x18000759e  pop     rbp
0x18000759f  retn
0x1800075a0  mov     r8d, dword ptr [rbp+var_20]; cbOutput
0x1800075a4  xor     r9d, r9d; dwFlags
0x1800075a7  mov     rcx, [rbp+phHash]; hHash
0x1800075ab  mov     rdx, r12; pbOutput
0x1800075ae  call    cs:__imp_BCryptFinishHash
0x1800075b4  mov     ecx, eax; Status
0x1800075b6  call    cs:__imp_RtlNtStatusToDosError
0x1800075bc  mov     ebx, eax
0x1800075be  test    eax, eax
0x1800075c0  jnz     loc_180007539
0x1800075c6  mov     eax, dword ptr [rbp+var_20]
0x1800075c9  xorps   xmm0, xmm0
0x1800075cc  movups  xmmword ptr [r13+0], xmm0
0x1800075d1  cmp     eax, esi
0x1800075d3  jbe     loc_1800076A8
0x1800075d9  mov     r8, rsi; Size
0x1800075dc  mov     rdx, r12; Src
0x1800075df  mov     rcx, r13; void *
0x1800075e2  call    memcpy_0
0x1800075e7  jmp     loc_180007539
0x1800075ec  sub     ecx, 1
0x1800075ef  jnz     loc_180007683
0x1800075f5  mov     r8d, [rdi+208h]; cbInput
0x1800075fc  lea     rdx, [rdi+20Ch]; pbInput
0x180007603  mov     rcx, [rbp+phHash]; hHash
0x180007607  xor     r9d, r9d; dwFlags
0x18000760a  call    cs:__imp_BCryptHashData
0x180007610  mov     ecx, eax; Status
0x180007612  call    cs:__imp_RtlNtStatusToDosError
0x180007618  mov     ebx, eax
0x18000761a  test    eax, eax
0x18000761c  jnz     loc_180007539
0x180007622  mov     rcx, [rbp+phHash]; hHash
0x180007626  lea     rdx, [rdi+22Ch]; pbInput
0x18000762d  xor     r9d, r9d; dwFlags
0x180007630  mov     r8d, 4; cbInput
0x180007636  call    cs:__imp_BCryptHashData
0x18000763c  mov     ecx, eax; Status
0x18000763e  call    cs:__imp_RtlNtStatusToDosError
0x180007644  mov     ebx, eax
0x180007646  test    eax, eax
0x180007648  jnz     loc_180007539
0x18000764e  cmp     [rdi+24Ch], eax
0x180007654  lea     rdx, [rbp+var_18]
0x180007658  mov     r8d, 4
0x18000765e  setnz   al
0x180007661  mov     [rbp+var_18], eax
0x180007664  jmp     loc_18000751E
0x180007669  call    cs:__imp_GetLastError
0x18000766f  mov     ebx, eax
0x180007671  jmp     loc_18000754D
0x180007676  call    cs:__imp_GetLastError
0x18000767c  mov     ebx, eax
0x18000767e  jmp     loc_18000754D
0x180007683  sub     ecx, 1
0x180007686  jz      loc_1800075F5
0x18000768c  sub     ecx, 1
0x18000768f  jz      loc_1800075F5
0x180007695  cmp     ecx, 1
0x180007698  jz      loc_1800074D2
0x18000769e  mov     ebx, 57h ; 'W'
0x1800076a3  jmp     loc_180007539
0x1800076a8  mov     rsi, rax
0x1800076ab  jmp     loc_1800075D9
0x1800076b0  mov     eax, 57h ; 'W'
0x1800076b5  jmp     loc_180007587
```
