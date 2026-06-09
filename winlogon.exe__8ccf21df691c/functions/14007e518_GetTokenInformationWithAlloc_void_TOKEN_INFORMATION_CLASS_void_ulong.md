# GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)

- ea: `0x14007e518`
- end: `0x14007e60d`
- name: `?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z`
- size: `245`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14007d9b8`

## callees

- `0x14007e518`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007e546`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007e5b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007e546`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007e5b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e589`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e589`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e5ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e57b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e5a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e5df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e57b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e5a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e596`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007e568`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007e5d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007e568`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007e5d0`

## pseudocode

```c
BOOL __fastcall GetTokenInformationWithAlloc(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        void **a3,
        unsigned int *a4)
{
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  BOOL result; // eax
  BOOL TokenInformation; // edi
  void *v12; // rbx
  HANDLE v13; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  void *v16; // rax
  void *v17; // rbx
  HANDLE v18; // rax

  *a4 = 128;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x80u);
  *a3 = v9;
  if ( v9 )
  {
    result = GetTokenInformation(TokenHandle, TokenInformationClass, v9, *a4, a4);
    TokenInformation = result;
    if ( result )
      return result;
    v12 = *a3;
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
    *a3 = 0;
    if ( GetLastError() != 122 )
      return TokenInformation;
    v14 = *a4;
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 0, v14);
    *a3 = v16;
    if ( v16 )
    {
      TokenInformation = GetTokenInformation(TokenHandle, TokenInformationClass, v16, *a4, a4);
      if ( !TokenInformation )
      {
        v17 = *a3;
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v17);
        *a3 = 0;
      }
      return TokenInformation;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14007e518  push    rbx
0x14007e51a  push    rbp
0x14007e51b  push    rsi
0x14007e51c  push    rdi
0x14007e51d  push    r14
0x14007e51f  push    r15
0x14007e521  sub     rsp, 38h
0x14007e525  mov     ebx, 80h
0x14007e52a  mov     r14, r9
0x14007e52d  mov     [r9], ebx
0x14007e530  mov     rsi, r8
0x14007e533  mov     ebp, edx
0x14007e535  mov     r15, rcx
0x14007e538  call    cs:__imp_GetProcessHeap
0x14007e53e  mov     r8d, ebx; dwBytes
0x14007e541  xor     edx, edx; dwFlags
0x14007e543  mov     rcx, rax; hHeap
0x14007e546  call    cs:__imp_HeapAlloc
0x14007e54c  mov     [rsi], rax
0x14007e54f  test    rax, rax
0x14007e552  jz      loc_14007E5FE
0x14007e558  mov     r9d, [r14]; TokenInformationLength
0x14007e55b  mov     r8, rax; TokenInformation
0x14007e55e  mov     edx, ebp; TokenInformationClass
0x14007e560  mov     [rsp+68h+ReturnLength], r14; ReturnLength
0x14007e565  mov     rcx, r15; TokenHandle
0x14007e568  call    cs:__imp_GetTokenInformation
0x14007e56e  mov     edi, eax
0x14007e570  test    eax, eax
0x14007e572  jnz     loc_14007E600
0x14007e578  mov     rbx, [rsi]
0x14007e57b  call    cs:__imp_GetProcessHeap
0x14007e581  mov     r8, rbx; lpMem
0x14007e584  xor     edx, edx; dwFlags
0x14007e586  mov     rcx, rax; hHeap
0x14007e589  call    cs:__imp_HeapFree
0x14007e58f  mov     qword ptr [rsi], 0
0x14007e596  call    cs:__imp_GetLastError
0x14007e59c  cmp     eax, 7Ah ; 'z'
0x14007e59f  jnz     short loc_14007E5FA
0x14007e5a1  mov     ebx, [r14]
0x14007e5a4  call    cs:__imp_GetProcessHeap
0x14007e5aa  mov     r8d, ebx; dwBytes
0x14007e5ad  xor     edx, edx; dwFlags
0x14007e5af  mov     rcx, rax; hHeap
0x14007e5b2  call    cs:__imp_HeapAlloc
0x14007e5b8  mov     [rsi], rax
0x14007e5bb  test    rax, rax
0x14007e5be  jz      short loc_14007E5FE
0x14007e5c0  mov     r9d, [r14]; TokenInformationLength
0x14007e5c3  mov     r8, rax; TokenInformation
0x14007e5c6  mov     edx, ebp; TokenInformationClass
0x14007e5c8  mov     [rsp+68h+ReturnLength], r14; ReturnLength
0x14007e5cd  mov     rcx, r15; TokenHandle
0x14007e5d0  call    cs:__imp_GetTokenInformation
0x14007e5d6  mov     edi, eax
0x14007e5d8  test    eax, eax
0x14007e5da  jnz     short loc_14007E5FA
0x14007e5dc  mov     rbx, [rsi]
0x14007e5df  call    cs:__imp_GetProcessHeap
0x14007e5e5  mov     r8, rbx; lpMem
0x14007e5e8  xor     edx, edx; dwFlags
0x14007e5ea  mov     rcx, rax; hHeap
0x14007e5ed  call    cs:__imp_HeapFree
0x14007e5f3  mov     qword ptr [rsi], 0
0x14007e5fa  mov     eax, edi
0x14007e5fc  jmp     short loc_14007E600
0x14007e5fe  xor     eax, eax
0x14007e600  add     rsp, 38h
0x14007e604  pop     r15
0x14007e606  pop     r14
0x14007e608  pop     rdi
0x14007e609  pop     rsi
0x14007e60a  pop     rbp
0x14007e60b  pop     rbx
0x14007e60c  retn
```
