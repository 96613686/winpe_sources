# GetUserSid(void *,void * *)

- ea: `0x1800056a0`
- end: `0x180005835`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018b50`
- `0x18001a6a0`

## callees

- `0x180004fc0`
- `0x1800051f0`
- `0x1800053f0`
- `0x1800056a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005771`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005771`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800057bc`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800057bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005733`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005763`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005763`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000580d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000580d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005716`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005716`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000574f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000574f`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rdi
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  DWORD v13; // ebx
  HANDLE v14; // rax
  PSID *v15; // rax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  v5 = (PSID *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  if ( v5 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147024774 )
      {
        v13 = TokenInformationLength;
        v14 = GetProcessHeap();
        v15 = (PSID *)HeapReAlloc(v14, 8u, v5, v13);
        if ( v15 )
        {
          v5 = v15;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            goto LABEL_10;
        }
        TokenInformation = GetTokenInformation(
                             TokenHandle,
                             TokenUser,
                             v5,
                             TokenInformationLength,
                             &TokenInformationLength);
        Error = ResultFromWin32Bool(TokenInformation);
      }
    }
    if ( Error < 0 )
      goto LABEL_10;
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, LengthSid);
    v10 = v9;
    if ( v9 )
    {
      if ( CopySid(TokenInformationLength, v9, *v5) )
      {
        Error = 0;
LABEL_8:
        *a2 = v10;
        goto LABEL_9;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_8;
      ResultFromHeapFree(v10);
    }
    else
    {
      Error = -2147024882;
    }
LABEL_9:
    if ( !v5 )
      return (unsigned int)Error;
LABEL_10:
    v11 = GetProcessHeap();
    if ( !HeapFree(v11, 0, v5) )
      ResultFromKnownLastError();
    return (unsigned int)Error;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800056a0  push    rbx
0x1800056a2  push    rsi
0x1800056a3  push    rdi
0x1800056a4  push    r14
0x1800056a6  sub     rsp, 38h
0x1800056aa  mov     r14, rdx
0x1800056ad  mov     qword ptr [rdx], 0
0x1800056b4  mov     rsi, rcx
0x1800056b7  mov     [rsp+58h+TokenInformationLength], 0C8h
0x1800056bf  call    cs:__imp_GetProcessHeap
0x1800056c5  mov     edx, 8; dwFlags
0x1800056ca  mov     r8d, 0C8h; dwBytes
0x1800056d0  mov     rcx, rax; hHeap
0x1800056d3  call    cs:__imp_HeapAlloc
0x1800056d9  mov     rdi, rax
0x1800056dc  test    rax, rax
0x1800056df  jz      loc_18000578B
0x1800056e5  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800056ea  lea     rax, [rsp+58h+TokenInformationLength]
0x1800056ef  mov     r8, rdi; TokenInformation
0x1800056f2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800056f7  mov     edx, 1; TokenInformationClass
0x1800056fc  mov     rcx, rsi; TokenHandle
0x1800056ff  call    cs:__imp_GetTokenInformation
0x180005705  test    eax, eax
0x180005707  jz      loc_180005792
0x18000570d  xor     ebx, ebx
0x18000570f  test    ebx, ebx
0x180005711  js      short loc_180005763
0x180005713  mov     rcx, [rdi]; pSid
0x180005716  call    cs:__imp_GetLengthSid
0x18000571c  mov     ebx, eax
0x18000571e  mov     [rsp+58h+TokenInformationLength], ebx
0x180005722  call    cs:__imp_GetProcessHeap
0x180005728  mov     r8d, ebx; dwBytes
0x18000572b  mov     edx, 8; dwFlags
0x180005730  mov     rcx, rax; hHeap
0x180005733  call    cs:__imp_HeapAlloc
0x180005739  mov     rsi, rax
0x18000573c  test    rax, rax
0x18000573f  jz      loc_180005821
0x180005745  mov     r8, [rdi]; pSourceSid
0x180005748  mov     rdx, rax; pDestinationSid
0x18000574b  mov     ecx, [rsp+58h+TokenInformationLength]; nDestinationSidLength
0x18000574f  call    cs:__imp_CopySid
0x180005755  test    eax, eax
0x180005757  jz      short loc_1800057CC
0x180005759  xor     ebx, ebx
0x18000575b  mov     [r14], rsi
0x18000575e  test    rdi, rdi
0x180005761  jz      short loc_18000577F
0x180005763  call    cs:__imp_GetProcessHeap
0x180005769  mov     r8, rdi; lpMem
0x18000576c  xor     edx, edx; dwFlags
0x18000576e  mov     rcx, rax; hHeap
0x180005771  call    cs:__imp_HeapFree
0x180005777  test    eax, eax
0x180005779  jz      loc_18000582B
0x18000577f  mov     eax, ebx
0x180005781  add     rsp, 38h
0x180005785  pop     r14
0x180005787  pop     rdi
0x180005788  pop     rsi
0x180005789  pop     rbx
0x18000578a  retn
0x18000578b  mov     eax, 8007000Eh
0x180005790  jmp     short loc_180005781
0x180005792  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005797  mov     ebx, eax
0x180005799  cmp     eax, 8007007Ah
0x18000579e  jnz     loc_18000570F
0x1800057a4  mov     ebx, [rsp+58h+TokenInformationLength]
0x1800057a8  call    cs:__imp_GetProcessHeap
0x1800057ae  mov     r9d, ebx; dwBytes
0x1800057b1  mov     r8, rdi; lpMem
0x1800057b4  mov     rcx, rax; hHeap
0x1800057b7  mov     edx, 8; dwFlags
0x1800057bc  call    cs:__imp_HeapReAlloc
0x1800057c2  test    rax, rax
0x1800057c5  jz      short loc_1800057E4
0x1800057c7  mov     rdi, rax
0x1800057ca  jmp     short loc_1800057F3
0x1800057cc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800057d1  mov     ebx, eax
0x1800057d3  test    eax, eax
0x1800057d5  jns     short loc_18000575B
0x1800057d7  mov     rcx, rsi; lpMem
0x1800057da  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800057df  jmp     loc_18000575E
0x1800057e4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800057e9  mov     ebx, eax
0x1800057eb  test    eax, eax
0x1800057ed  js      loc_180005763
0x1800057f3  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800057f8  lea     rax, [rsp+58h+TokenInformationLength]
0x1800057fd  mov     r8, rdi; TokenInformation
0x180005800  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180005805  mov     edx, 1; TokenInformationClass
0x18000580a  mov     rcx, rsi; TokenHandle
0x18000580d  call    cs:__imp_GetTokenInformation
0x180005813  mov     ecx, eax; int
0x180005815  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000581a  mov     ebx, eax
0x18000581c  jmp     loc_18000570F
0x180005821  mov     ebx, 8007000Eh
0x180005826  jmp     loc_18000575E
0x18000582b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005830  jmp     loc_18000577F
```
