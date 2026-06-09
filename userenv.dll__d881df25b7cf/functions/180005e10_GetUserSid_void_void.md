# GetUserSid(void *,void * *)

- ea: `0x180005e10`
- end: `0x180005fdb`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `459`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a508`
- `0x18001c16c`

## callees

- `0x180005690`
- `0x180005900`
- `0x180005b30`
- `0x180005e10`
- `0x18001408c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ec9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005f91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005f91`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005ea0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005ea0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005eeb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005eeb`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rbx
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  int v13; // eax
  BOOL v14; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  TokenInformation = HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = (PSID *)TokenInformation;
  if ( !TokenInformation )
    return 2147942414LL;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v13 = ResultFromHeapReAlloc(v5, TokenInformationLength, &TokenInformation);
      v5 = (PSID *)TokenInformation;
      Error = v13;
      if ( v13 < 0 )
        goto LABEL_9;
      v14 = GetTokenInformation(
              TokenHandle,
              TokenUser,
              TokenInformation,
              TokenInformationLength,
              &TokenInformationLength);
      Error = ResultFromWin32Bool(v14);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, LengthSid);
    v10 = v9;
    if ( !v9 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v9, *v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v10);
        goto LABEL_9;
      }
    }
    *a2 = v10;
  }
LABEL_9:
  if ( v5 )
  {
    v11 = GetProcessHeap();
    if ( !HeapFree(v11, 0, v5) )
      ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180005e10  mov     [rsp+arg_0], rbx
0x180005e15  push    rsi
0x180005e16  push    rdi
0x180005e17  push    r14
0x180005e19  sub     rsp, 30h
0x180005e1d  mov     r14, rdx
0x180005e20  mov     qword ptr [rdx], 0
0x180005e27  mov     rsi, rcx
0x180005e2a  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180005e32  call    cs:__imp_GetProcessHeap
0x180005e39  nop     dword ptr [rax+rax+00h]
0x180005e3e  mov     edx, 8; dwFlags
0x180005e43  mov     r8d, 0C8h; dwBytes
0x180005e49  mov     rcx, rax; hHeap
0x180005e4c  call    cs:__imp_HeapAlloc
0x180005e53  nop     dword ptr [rax+rax+00h]
0x180005e58  mov     [rsp+48h+TokenInformation], rax
0x180005e5d  mov     rbx, rax
0x180005e60  test    rax, rax
0x180005e63  jz      loc_180005F42
0x180005e69  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180005e6e  lea     rax, [rsp+48h+TokenInformationLength]
0x180005e73  mov     r8, rbx; TokenInformation
0x180005e76  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005e7b  mov     edx, 1; TokenInformationClass
0x180005e80  mov     rcx, rsi; TokenHandle
0x180005e83  call    cs:__imp_GetTokenInformation
0x180005e8a  nop     dword ptr [rax+rax+00h]
0x180005e8f  test    eax, eax
0x180005e91  jz      loc_180005F49
0x180005e97  xor     edi, edi
0x180005e99  test    edi, edi
0x180005e9b  js      short loc_180005F04
0x180005e9d  mov     rcx, [rbx]; pSid
0x180005ea0  call    cs:__imp_GetLengthSid
0x180005ea7  nop     dword ptr [rax+rax+00h]
0x180005eac  mov     edi, eax
0x180005eae  mov     [rsp+48h+TokenInformationLength], edi
0x180005eb2  call    cs:__imp_GetProcessHeap
0x180005eb9  nop     dword ptr [rax+rax+00h]
0x180005ebe  mov     r8d, edi; dwBytes
0x180005ec1  mov     edx, 8; dwFlags
0x180005ec6  mov     rcx, rax; hHeap
0x180005ec9  call    cs:__imp_HeapAlloc
0x180005ed0  nop     dword ptr [rax+rax+00h]
0x180005ed5  mov     rsi, rax
0x180005ed8  test    rax, rax
0x180005edb  jz      loc_180005FC7
0x180005ee1  mov     r8, [rbx]; pSourceSid
0x180005ee4  mov     rdx, rax; pDestinationSid
0x180005ee7  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180005eeb  call    cs:__imp_CopySid
0x180005ef2  nop     dword ptr [rax+rax+00h]
0x180005ef7  test    eax, eax
0x180005ef9  jz      loc_180005FAB
0x180005eff  xor     edi, edi
0x180005f01  mov     [r14], rsi
0x180005f04  test    rbx, rbx
0x180005f07  jz      short loc_180005F31
0x180005f09  call    cs:__imp_GetProcessHeap
0x180005f10  nop     dword ptr [rax+rax+00h]
0x180005f15  mov     r8, rbx; lpMem
0x180005f18  xor     edx, edx; dwFlags
0x180005f1a  mov     rcx, rax; hHeap
0x180005f1d  call    cs:__imp_HeapFree
0x180005f24  nop     dword ptr [rax+rax+00h]
0x180005f29  test    eax, eax
0x180005f2b  jz      loc_180005FD1
0x180005f31  mov     eax, edi
0x180005f33  mov     rbx, [rsp+48h+arg_0]
0x180005f38  add     rsp, 30h
0x180005f3c  pop     r14
0x180005f3e  pop     rdi
0x180005f3f  pop     rsi
0x180005f40  retn
0x180005f42  mov     eax, 8007000Eh
0x180005f47  jmp     short loc_180005F33
0x180005f49  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005f4e  mov     edi, eax
0x180005f50  cmp     eax, 8007007Ah
0x180005f55  jnz     loc_180005E99
0x180005f5b  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180005f5f  lea     r8, [rsp+48h+TokenInformation]; void **
0x180005f64  mov     rcx, rbx; lpMem
0x180005f67  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180005f6c  mov     rbx, [rsp+48h+TokenInformation]
0x180005f71  mov     edi, eax
0x180005f73  test    eax, eax
0x180005f75  js      short loc_180005F04
0x180005f77  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180005f7c  lea     rax, [rsp+48h+TokenInformationLength]
0x180005f81  mov     r8, rbx; TokenInformation
0x180005f84  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005f89  mov     edx, 1; TokenInformationClass
0x180005f8e  mov     rcx, rsi; TokenHandle
0x180005f91  call    cs:__imp_GetTokenInformation
0x180005f98  nop     dword ptr [rax+rax+00h]
0x180005f9d  mov     ecx, eax; int
0x180005f9f  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180005fa4  mov     edi, eax
0x180005fa6  jmp     loc_180005E99
0x180005fab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005fb0  mov     edi, eax
0x180005fb2  test    eax, eax
0x180005fb4  jns     loc_180005F01
0x180005fba  mov     rcx, rsi; lpMem
0x180005fbd  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005fc2  jmp     loc_180005F04
0x180005fc7  mov     edi, 8007000Eh
0x180005fcc  jmp     loc_180005F04
0x180005fd1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005fd6  jmp     loc_180005F31
```
