# GetUserSid(void *,void * *)

- ea: `0x1800318f8`
- end: `0x180031a4d`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800316a8`
- `0x180031a54`

## callees

- `0x1800318f8`
- `0x180032708`
- `0x180032754`
- `0x18003279c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800319db`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800319db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031959`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800319bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031959`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800319bf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a0a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031974`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180031988`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180031988`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  int Error; // ebx
  PSID *v5; // rdi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v8; // rax
  DWORD LengthSid; // eax
  void *v10; // rsi
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 200;
  Error = ResultFromHeapAlloc(0xC8u, &TokenInformation);
  if ( Error >= 0 )
  {
    v5 = (PSID *)TokenInformation;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_8;
    Error = ResultFromKnownLastError();
    if ( Error != -2147024774 )
      goto LABEL_10;
    v6 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v8 = (PSID *)HeapReAlloc(ProcessHeap, 8u, v5, v6);
    if ( v8 )
    {
      v5 = v8;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_17;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
LABEL_8:
      Error = 0;
    else
      Error = ResultFromKnownLastError();
LABEL_10:
    if ( Error < 0 )
      goto LABEL_17;
    LengthSid = GetLengthSid(*v5);
    TokenInformation = 0;
    TokenInformationLength = LengthSid;
    Error = ResultFromHeapAlloc(LengthSid, &TokenInformation);
    if ( Error < 0 )
      goto LABEL_17;
    v10 = TokenInformation;
    if ( CopySid(TokenInformationLength, TokenInformation, *v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v10);
        goto LABEL_17;
      }
    }
    *a2 = v10;
LABEL_17:
    ResultFromHeapFree(v5);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800318f8  mov     [rsp-18h+arg_0], rbx
0x1800318fd  mov     [rsp-18h+arg_18], rsi
0x180031902  push    rbp
0x180031903  push    rdi
0x180031904  push    r14
0x180031906  mov     rbp, rsp
0x180031909  sub     rsp, 30h
0x18003190d  mov     rsi, rcx
0x180031910  mov     qword ptr [rdx], 0
0x180031917  mov     ecx, 0C8h; dwBytes
0x18003191c  mov     [rbp+TokenInformation], 0
0x180031924  mov     r14, rdx
0x180031927  mov     [rbp+TokenInformationLength], ecx
0x18003192a  lea     rdx, [rbp+TokenInformation]; void **
0x18003192e  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180031933  mov     ebx, eax
0x180031935  test    eax, eax
0x180031937  js      loc_180031A38
0x18003193d  mov     rdi, [rbp+TokenInformation]
0x180031941  lea     rax, [rbp+TokenInformationLength]
0x180031945  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180031949  mov     r8, rdi; TokenInformation
0x18003194c  mov     edx, 1; TokenInformationClass
0x180031951  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180031956  mov     rcx, rsi; TokenHandle
0x180031959  call    cs:__imp_GetTokenInformation
0x18003195f  test    eax, eax
0x180031961  jnz     short loc_1800319C9
0x180031963  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180031968  mov     ebx, eax
0x18003196a  cmp     eax, 8007007Ah
0x18003196f  jnz     short loc_1800319D4
0x180031971  mov     ebx, [rbp+TokenInformationLength]
0x180031974  call    cs:__imp_GetProcessHeap
0x18003197a  mov     r9d, ebx; dwBytes
0x18003197d  mov     r8, rdi; lpMem
0x180031980  mov     rcx, rax; hHeap
0x180031983  mov     edx, 8; dwFlags
0x180031988  call    cs:__imp_HeapReAlloc
0x18003198e  test    rax, rax
0x180031991  jz      short loc_180031998
0x180031993  mov     rdi, rax
0x180031996  jmp     short loc_1800319A7
0x180031998  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003199d  mov     ebx, eax
0x18003199f  test    eax, eax
0x1800319a1  js      loc_180031A30
0x1800319a7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800319ab  lea     rax, [rbp+TokenInformationLength]
0x1800319af  mov     r8, rdi; TokenInformation
0x1800319b2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800319b7  mov     edx, 1; TokenInformationClass
0x1800319bc  mov     rcx, rsi; TokenHandle
0x1800319bf  call    cs:__imp_GetTokenInformation
0x1800319c5  test    eax, eax
0x1800319c7  jz      short loc_1800319CD
0x1800319c9  xor     ebx, ebx
0x1800319cb  jmp     short loc_1800319D4
0x1800319cd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800319d2  mov     ebx, eax
0x1800319d4  test    ebx, ebx
0x1800319d6  js      short loc_180031A30
0x1800319d8  mov     rcx, [rdi]; pSid
0x1800319db  call    cs:__imp_GetLengthSid
0x1800319e1  lea     rdx, [rbp+TokenInformation]; void **
0x1800319e5  mov     [rbp+TokenInformation], 0
0x1800319ed  mov     ecx, eax; dwBytes
0x1800319ef  mov     [rbp+TokenInformationLength], ecx
0x1800319f2  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800319f7  mov     ebx, eax
0x1800319f9  test    eax, eax
0x1800319fb  js      short loc_180031A30
0x1800319fd  mov     rsi, [rbp+TokenInformation]
0x180031a01  mov     r8, [rdi]; pSourceSid
0x180031a04  mov     rdx, rsi; pDestinationSid
0x180031a07  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180031a0a  call    cs:__imp_CopySid
0x180031a10  test    eax, eax
0x180031a12  jz      short loc_180031A18
0x180031a14  xor     ebx, ebx
0x180031a16  jmp     short loc_180031A23
0x180031a18  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180031a1d  mov     ebx, eax
0x180031a1f  test    eax, eax
0x180031a21  js      short loc_180031A28
0x180031a23  mov     [r14], rsi
0x180031a26  jmp     short loc_180031A30
0x180031a28  mov     rcx, rsi; lpMem
0x180031a2b  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180031a30  mov     rcx, rdi; lpMem
0x180031a33  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180031a38  mov     rsi, [rsp+30h+arg_18]
0x180031a3d  mov     eax, ebx
0x180031a3f  mov     rbx, [rsp+30h+arg_0]
0x180031a44  add     rsp, 30h
0x180031a48  pop     r14
0x180031a4a  pop     rdi
0x180031a4b  pop     rbp
0x180031a4c  retn
```
