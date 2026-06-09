# GetCurrentUserAndDomain(ushort *,ulong *,ushort *,ulong *)

- ea: `0x180021224`
- end: `0x180021386`
- name: `?GetCurrentUserAndDomain@@YAHPEAGPEAK01@Z`
- size: `354`
- prototype: `__int64 __fastcall(LPWSTR Name, LPDWORD cchName, LPWSTR ReferencedDomainName, LPDWORD cchReferencedDomainName)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023288`

## callees

- `0x180021224`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180021370`
- `KERNEL32!HeapFree` at `0x1800776f0`
- `KERNEL32!HeapFree` at `0x180021370`
- `KERNEL32!HeapFree` at `0x1800776f0`
- `KERNEL32!GetProcessHeap` at `0x1800212d7`
- `KERNEL32!GetProcessHeap` at `0x180021362`
- `KERNEL32!GetProcessHeap` at `0x1800776e2`
- `KERNEL32!GetProcessHeap` at `0x1800212d7`
- `KERNEL32!GetProcessHeap` at `0x180021362`
- `KERNEL32!GetProcessHeap` at `0x1800776e2`
- `KERNEL32!GetLastError` at `0x180021271`
- `KERNEL32!GetLastError` at `0x1800212c8`
- `KERNEL32!GetLastError` at `0x180021271`
- `KERNEL32!GetLastError` at `0x1800212c8`
- `KERNEL32!CloseHandle` at `0x180021357`
- `KERNEL32!CloseHandle` at `0x1800776d2`
- `KERNEL32!CloseHandle` at `0x180021357`
- `KERNEL32!CloseHandle` at `0x1800776d2`
- `KERNEL32!HeapAlloc` at `0x1800212e5`
- `KERNEL32!HeapAlloc` at `0x1800212e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021293`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021282`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021267`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021252`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800212ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021314`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800212ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021314`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002133d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002133d`

## pseudocode

```c
__int64 __fastcall GetCurrentUserAndDomain(
        LPWSTR Name,
        LPDWORD cchName,
        LPWSTR ReferencedDomainName,
        LPDWORD cchReferencedDomainName)
{
  unsigned int v8; // edi
  PSID *v9; // rbx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-58h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-54h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-50h] BYREF
  PSID *v19; // [rsp+50h] [rbp-48h]

  v8 = 0;
  TokenHandle = 0;
  v9 = 0;
  v19 = 0;
  TokenInformationLength = 0;
  peUse = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v12 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v9 = (PSID *)HeapAlloc(ProcessHeap, 0, v12);
      v19 = v9;
      if ( v9 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength)
          && LookupAccountSidW(0, *v9, Name, cchName, ReferencedDomainName, cchReferencedDomainName, &peUse) )
        {
          v8 = 1;
        }
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v9 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180021224  mov     rax, rsp
0x180021227  push    rbx
0x180021228  push    rsi
0x180021229  push    rdi
0x18002122a  push    r12
0x18002122c  push    r14
0x18002122e  push    r15
0x180021230  sub     rsp, 68h
0x180021234  mov     rsi, r9
0x180021237  mov     r14, r8
0x18002123a  mov     r15, rdx
0x18002123d  mov     r12, rcx
0x180021240  xor     edi, edi
0x180021242  mov     [rax-50h], rdi
0x180021246  xor     ebx, ebx
0x180021248  mov     [rax-48h], rbx
0x18002124c  mov     [rax-58h], ebx
0x18002124f  mov     [rax-54h], ebx
0x180021252  call    cs:__imp_GetCurrentThread
0x180021258  mov     rcx, rax; ThreadHandle
0x18002125b  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180021260  lea     edx, [rdi+8]; DesiredAccess
0x180021263  lea     r8d, [rdi+1]; OpenAsSelf
0x180021267  call    cs:__imp_OpenThreadToken
0x18002126d  test    eax, eax
0x18002126f  jnz     short loc_1800212A1
0x180021271  call    cs:__imp_GetLastError
0x180021277  cmp     eax, 3F0h
0x18002127c  jnz     loc_18002134D
0x180021282  call    cs:__imp_GetCurrentProcess
0x180021288  mov     rcx, rax; ProcessHandle
0x18002128b  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x180021290  lea     edx, [rdi+8]; DesiredAccess
0x180021293  call    cs:__imp_OpenProcessToken
0x180021299  test    eax, eax
0x18002129b  jz      loc_18002134D
0x1800212a1  lea     rax, [rsp+98h+TokenInformationLength]
0x1800212a6  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x1800212ab  xor     r9d, r9d; TokenInformationLength
0x1800212ae  xor     r8d, r8d; TokenInformation
0x1800212b1  lea     edx, [r9+1]; TokenInformationClass
0x1800212b5  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800212ba  call    cs:__imp_GetTokenInformation
0x1800212c0  test    eax, eax
0x1800212c2  jnz     loc_18002134D
0x1800212c8  call    cs:__imp_GetLastError
0x1800212ce  cmp     eax, 7Ah ; 'z'
0x1800212d1  jnz     short loc_18002134D
0x1800212d3  mov     ebx, [rsp+98h+TokenInformationLength]
0x1800212d7  call    cs:__imp_GetProcessHeap
0x1800212dd  mov     r8d, ebx; dwBytes
0x1800212e0  xor     edx, edx; dwFlags
0x1800212e2  mov     rcx, rax; hHeap
0x1800212e5  call    cs:__imp_HeapAlloc
0x1800212eb  mov     rbx, rax
0x1800212ee  mov     [rsp+98h+var_48], rax
0x1800212f3  test    rax, rax
0x1800212f6  jz      short loc_18002134D
0x1800212f8  lea     rax, [rsp+98h+TokenInformationLength]
0x1800212fd  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180021302  mov     r9d, [rsp+98h+TokenInformationLength]; TokenInformationLength
0x180021307  mov     r8, rbx; TokenInformation
0x18002130a  mov     edx, 1; TokenInformationClass
0x18002130f  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180021314  call    cs:__imp_GetTokenInformation
0x18002131a  test    eax, eax
0x18002131c  jz      short loc_18002134D
0x18002131e  lea     rax, [rsp+98h+var_54]
0x180021323  mov     [rsp+98h+peUse], rax; peUse
0x180021328  mov     [rsp+98h+cchReferencedDomainName], rsi; cchReferencedDomainName
0x18002132d  mov     [rsp+98h+ReturnLength], r14; ReferencedDomainName
0x180021332  mov     r9, r15; cchName
0x180021335  mov     r8, r12; Name
0x180021338  mov     rdx, [rbx]; Sid
0x18002133b  xor     ecx, ecx; lpSystemName
0x18002133d  call    cs:__imp_LookupAccountSidW
0x180021343  test    eax, eax
0x180021345  mov     eax, 1
0x18002134a  cmovnz  edi, eax
0x18002134d  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180021352  test    rcx, rcx
0x180021355  jz      short loc_18002135D
0x180021357  call    cs:__imp_CloseHandle
0x18002135d  test    rbx, rbx
0x180021360  jz      short loc_180021376
0x180021362  call    cs:__imp_GetProcessHeap
0x180021368  mov     rcx, rax; hHeap
0x18002136b  mov     r8, rbx; lpMem
0x18002136e  xor     edx, edx; dwFlags
0x180021370  call    cs:__imp_HeapFree
0x180021376  mov     eax, edi
0x180021378  add     rsp, 68h
0x18002137c  pop     r15
0x18002137e  pop     r14
0x180021380  pop     r12
0x180021382  pop     rdi
0x180021383  pop     rsi
0x180021384  pop     rbx
0x180021385  retn
0x1800776bf  push    rbx
0x1800776c1  push    rbp
0x1800776c2  sub     rsp, 48h
0x1800776c6  mov     rbp, rdx
0x1800776c9  mov     rcx, [rbp+48h]; hObject
0x1800776cd  test    rcx, rcx
0x1800776d0  jz      short loc_1800776D9
0x1800776d2  call    cs:__imp_CloseHandle
0x1800776d8  nop
0x1800776d9  mov     rbx, [rbp+50h]
0x1800776dd  test    rbx, rbx
0x1800776e0  jz      short loc_1800776F7
0x1800776e2  call    cs:__imp_GetProcessHeap
0x1800776e8  mov     rcx, rax; hHeap
0x1800776eb  mov     r8, rbx; lpMem
0x1800776ee  xor     edx, edx; dwFlags
0x1800776f0  call    cs:__imp_HeapFree
0x1800776f6  nop
0x1800776f7  add     rsp, 48h
0x1800776fb  pop     rbp
0x1800776fc  pop     rbx
0x1800776fd  retn
```
