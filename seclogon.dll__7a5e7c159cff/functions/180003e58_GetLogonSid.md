# GetLogonSid

- ea: `0x180003e58`
- end: `0x180003fe5`
- name: `GetLogonSid`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001470`

## callees

- `0x180003e58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ec2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ec2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003ee0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003ee0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f16`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f94`
- `ntdll!RtlCopySid` at `0x180003f75`
- `ntdll!RtlCopySid` at `0x180003f75`
- `ntdll!RtlLengthSid` at `0x180003f45`
- `ntdll!RtlLengthSid` at `0x180003f45`

## pseudocode

```c
__int64 __fastcall GetLogonSid(_QWORD *a1)
{
  void *v2; // rbp
  unsigned int *v3; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // edi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int i; // ecx
  __int64 v9; // r14
  ULONG v10; // r15d
  HANDLE v11; // rax
  void *v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  v2 = 0;
  v3 = 0;
  CurrentThread = GetCurrentThread();
  LastError = 8;
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_5;
  GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  if ( !TokenInformationLength )
    goto LABEL_5;
  v6 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned int *)HeapAlloc(ProcessHeap, 0, v6);
  if ( !v3 )
    goto LABEL_13;
  if ( GetTokenInformation(TokenHandle, TokenGroups, v3, TokenInformationLength, &TokenInformationLength) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *v3 )
      {
        LastError = 5;
        goto LABEL_13;
      }
      v9 = 2LL * i;
      if ( (v3[4 * i + 4] & 0xC0000000) == 0xC0000000 )
        break;
    }
    v10 = RtlLengthSid(*(PSID *)&v3[4 * i + 2]);
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 0, v10);
    v2 = v12;
    if ( v12 )
    {
      RtlCopySid(v10, v12, *(PSID *)&v3[2 * v9 + 2]);
      *a1 = v2;
      v2 = 0;
      LastError = 0;
    }
  }
  else
  {
LABEL_5:
    LastError = GetLastError();
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v3);
  }
  if ( v2 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v2);
  }
  return LastError;
}

```

## disassembly

```asm
0x180003e58  mov     rax, rsp
0x180003e5b  mov     [rax+8], rbx
0x180003e5f  mov     [rax+20h], rbp
0x180003e63  push    rsi
0x180003e64  push    rdi
0x180003e65  push    r12
0x180003e67  push    r14
0x180003e69  push    r15
0x180003e6b  sub     rsp, 30h
0x180003e6f  mov     r12, rcx
0x180003e72  mov     dword ptr [rax+10h], 0
0x180003e79  mov     qword ptr [rax+18h], 0
0x180003e81  xor     ebp, ebp
0x180003e83  xor     esi, esi
0x180003e85  call    cs:__imp_GetCurrentThread
0x180003e8b  lea     edi, [rbp+8]
0x180003e8e  mov     rcx, rax; ThreadHandle
0x180003e91  mov     edx, edi; DesiredAccess
0x180003e93  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180003e98  lea     r8d, [rbp+1]; OpenAsSelf
0x180003e9c  call    cs:__imp_OpenThreadToken
0x180003ea2  test    eax, eax
0x180003ea4  jz      short loc_180003F16
0x180003ea6  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180003eab  lea     rax, [rsp+58h+TokenInformationLength]
0x180003eb0  lea     r14d, [rbp+2]
0x180003eb4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180003eb9  mov     edx, r14d; TokenInformationClass
0x180003ebc  xor     r9d, r9d; TokenInformationLength
0x180003ebf  xor     r8d, r8d; TokenInformation
0x180003ec2  call    cs:__imp_GetTokenInformation
0x180003ec8  mov     eax, [rsp+58h+TokenInformationLength]
0x180003ecc  test    eax, eax
0x180003ece  jz      short loc_180003F16
0x180003ed0  mov     ebx, eax
0x180003ed2  call    cs:__imp_GetProcessHeap
0x180003ed8  mov     r8d, ebx; dwBytes
0x180003edb  xor     edx, edx; dwFlags
0x180003edd  mov     rcx, rax; hHeap
0x180003ee0  call    cs:__imp_HeapAlloc
0x180003ee6  mov     rsi, rax
0x180003ee9  test    rax, rax
0x180003eec  jz      loc_180003F8A
0x180003ef2  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180003ef7  lea     rax, [rsp+58h+TokenInformationLength]
0x180003efc  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180003f01  mov     r8, rsi; TokenInformation
0x180003f04  mov     edx, r14d; TokenInformationClass
0x180003f07  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180003f0c  call    cs:__imp_GetTokenInformation
0x180003f12  test    eax, eax
0x180003f14  jnz     short loc_180003F20
0x180003f16  call    cs:__imp_GetLastError
0x180003f1c  mov     edi, eax
0x180003f1e  jmp     short loc_180003F8A
0x180003f20  xor     ecx, ecx
0x180003f22  mov     edx, 0C0000000h
0x180003f27  cmp     ecx, [rsi]
0x180003f29  jnb     short loc_180003F85
0x180003f2b  mov     r14d, ecx
0x180003f2e  add     r14, r14
0x180003f31  mov     eax, [rsi+r14*8+10h]
0x180003f36  and     eax, edx
0x180003f38  cmp     eax, edx
0x180003f3a  jz      short loc_180003F40
0x180003f3c  inc     ecx
0x180003f3e  jmp     short loc_180003F27
0x180003f40  mov     rcx, [rsi+r14*8+8]; Sid
0x180003f45  call    cs:__imp_RtlLengthSid
0x180003f4b  mov     r15d, eax
0x180003f4e  call    cs:__imp_GetProcessHeap
0x180003f54  mov     r8d, r15d; dwBytes
0x180003f57  xor     edx, edx; dwFlags
0x180003f59  mov     rcx, rax; hHeap
0x180003f5c  call    cs:__imp_HeapAlloc
0x180003f62  mov     rbp, rax
0x180003f65  test    rax, rax
0x180003f68  jz      short loc_180003F8A
0x180003f6a  mov     r8, [rsi+r14*8+8]; SourceSid
0x180003f6f  mov     rdx, rax; DestinationSid
0x180003f72  mov     ecx, r15d; DestinationSidLength
0x180003f75  call    cs:__imp_RtlCopySid
0x180003f7b  mov     [r12], rbp
0x180003f7f  xor     ebp, ebp
0x180003f81  xor     edi, edi
0x180003f83  jmp     short loc_180003F8A
0x180003f85  mov     edi, 5
0x180003f8a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180003f8f  test    rcx, rcx
0x180003f92  jz      short loc_180003F9A
0x180003f94  call    cs:__imp_CloseHandle
0x180003f9a  test    rsi, rsi
0x180003f9d  jz      short loc_180003FB3
0x180003f9f  call    cs:__imp_GetProcessHeap
0x180003fa5  mov     r8, rsi; lpMem
0x180003fa8  xor     edx, edx; dwFlags
0x180003faa  mov     rcx, rax; hHeap
0x180003fad  call    cs:__imp_HeapFree
0x180003fb3  test    rbp, rbp
0x180003fb6  jz      short loc_180003FCC
0x180003fb8  call    cs:__imp_GetProcessHeap
0x180003fbe  mov     r8, rbp; lpMem
0x180003fc1  xor     edx, edx; dwFlags
0x180003fc3  mov     rcx, rax; hHeap
0x180003fc6  call    cs:__imp_HeapFree
0x180003fcc  mov     rbx, [rsp+58h+arg_0]
0x180003fd1  mov     eax, edi
0x180003fd3  mov     rbp, [rsp+58h+arg_18]
0x180003fd8  add     rsp, 30h
0x180003fdc  pop     r15
0x180003fde  pop     r14
0x180003fe0  pop     r12
0x180003fe2  pop     rdi
0x180003fe3  pop     rsi
0x180003fe4  retn
```
