# PfIuHistoryStoreFileMappingCreate

- ea: `0x1800b173c`
- end: `0x1800b192a`
- name: `PfIuHistoryStoreFileMappingCreate`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180092aa0`

## callees

- `0x1800b173c`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b181f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b181f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b18f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b18ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b18f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b18ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b17da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b17da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b17c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b17c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b18e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b18e2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b1888`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b1888`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b1865`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b1865`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800b17ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800b17ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b18d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b18d3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b1819`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b18c9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b1819`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b18c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b179c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b179c`

## pseudocode

```c
__int64 __fastcall PfIuHistoryStoreFileMappingCreate(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  void *v5; // rdi
  int v6; // esi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v9; // rax
  LPVOID v10; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-19h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+48h] [rbp-11h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+60h] [rbp+7h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+70h] [rbp+17h] BYREF

  ReturnLength = 0;
  SecurityDescriptor = 0;
  TokenHandle = 0;
  memset(&FileMappingAttributes, 0, 20);
  v5 = 0;
  v6 = 0;
  NewState = 0;
  PreviousState = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    goto LABEL_2;
  if ( !ImpersonateSelf(SecurityImpersonation) )
    goto LABEL_2;
  v6 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
    goto LABEL_2;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  NewState.Privileges[0].Luid = (LUID)30LL;
  ReturnLength = 16;
  AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_9;
  FileMappingAttributes.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
  v9 = CreateFileMappingW(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &FileMappingAttributes,
         0x8000004u,
         0,
         0x2BD0u,
         L"Global\\PfIuHistoryStoreSection");
  v5 = v9;
  if ( !v9 || (v10 = MapViewOfFile(v9, 6u, 0, 0, 0x2BD0u)) == 0 )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_9;
  }
  *a2 = v5;
  v5 = 0;
  LastError = 0;
  *a3 = v10;
LABEL_9:
  if ( PreviousState.PrivilegeCount )
    AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, 0x10u, 0, 0);
  if ( v6 )
    RevertToSelf();
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 )
    CloseHandle(v5);
  return LastError;
}

```

## disassembly

```asm
0x1800b173c  mov     [rsp-8+arg_0], rbx
0x1800b1741  push    rbp
0x1800b1742  push    rsi
0x1800b1743  push    rdi
0x1800b1744  push    r14
0x1800b1746  push    r15
0x1800b1748  lea     rbp, [rsp-37h]
0x1800b174d  sub     rsp, 90h
0x1800b1754  mov     rax, cs:__security_cookie
0x1800b175b  xor     rax, rsp
0x1800b175e  mov     [rbp+57h+var_30], rax
0x1800b1762  xor     eax, eax
0x1800b1764  lea     rcx, aDAGaSy; "D:(A;;GA;;;SY)"
0x1800b176b  xorps   xmm0, xmm0
0x1800b176e  mov     [rbp+57h+FileMappingAttributes.bInheritHandle], eax
0x1800b1771  mov     r15, r8
0x1800b1774  mov     [rbp+57h+var_80], eax
0x1800b1777  mov     r14, rdx
0x1800b177a  mov     [rbp+57h+SecurityDescriptor], rax
0x1800b177e  lea     edx, [rax+1]; StringSDRevision
0x1800b1781  mov     [rbp+57h+TokenHandle], rax
0x1800b1785  xor     r9d, r9d; SecurityDescriptorSize
0x1800b1788  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800b178c  movups  xmmword ptr [rbp+57h+FileMappingAttributes.nLength], xmm0
0x1800b1790  xor     edi, edi
0x1800b1792  xor     esi, esi
0x1800b1794  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x1800b1798  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x1800b179c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b17a2  test    eax, eax
0x1800b17a4  jnz     short loc_1800B17B3
0x1800b17a6  call    cs:__imp_GetLastError
0x1800b17ac  mov     ebx, eax
0x1800b17ae  jmp     loc_1800B18A1
0x1800b17b3  mov     ebx, 2
0x1800b17b8  mov     ecx, ebx; ImpersonationLevel
0x1800b17ba  call    cs:__imp_ImpersonateSelf
0x1800b17c0  test    eax, eax
0x1800b17c2  jz      short loc_1800B17A6
0x1800b17c4  lea     esi, [rbx-1]
0x1800b17c7  call    cs:__imp_GetCurrentThread
0x1800b17cd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800b17d1  xor     r8d, r8d; OpenAsSelf
0x1800b17d4  mov     rcx, rax; ThreadHandle
0x1800b17d7  lea     edx, [rbx+26h]; DesiredAccess
0x1800b17da  call    cs:__imp_OpenThreadToken
0x1800b17e0  test    eax, eax
0x1800b17e2  jz      short loc_1800B17A6
0x1800b17e4  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b17e8  lea     rax, [rbp+57h+var_80]
0x1800b17ec  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800b17f1  lea     r9d, [rbx+0Eh]; BufferLength
0x1800b17f5  lea     rax, [rbp+57h+var_40]
0x1800b17f9  mov     [rbp+57h+NewState.PrivilegeCount], esi
0x1800b17fc  lea     r8, [rbp+57h+NewState]; NewState
0x1800b1800  mov     [rsp+0B0h+PreviousState], rax; PreviousState
0x1800b1805  xor     edx, edx; DisableAllPrivileges
0x1800b1807  mov     [rbp+57h+NewState.Privileges.Attributes], ebx
0x1800b180a  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 1Eh
0x1800b1812  mov     [rbp+57h+var_80], 10h
0x1800b1819  call    cs:__imp_AdjustTokenPrivileges
0x1800b181f  call    cs:__imp_GetLastError
0x1800b1825  mov     ebx, eax
0x1800b1827  test    eax, eax
0x1800b1829  jnz     short loc_1800B18A1
0x1800b182b  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800b182f  lea     rdx, [rbp+57h+FileMappingAttributes]; lpFileMappingAttributes
0x1800b1833  mov     [rbp+57h+FileMappingAttributes.lpSecurityDescriptor], rax
0x1800b1837  mov     ebx, 2BD0h
0x1800b183c  lea     rax, Name; "Global\\PfIuHistoryStoreSection"
0x1800b1843  mov     qword ptr [rbp+57h+FileMappingAttributes.nLength], 18h
0x1800b184b  mov     [rsp+0B0h+ReturnLength], rax; lpName
0x1800b1850  xor     r9d, r9d; dwMaximumSizeHigh
0x1800b1853  mov     r8d, 8000004h; flProtect
0x1800b1859  mov     dword ptr [rsp+0B0h+PreviousState], ebx; dwMaximumSizeLow
0x1800b185d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800b1861  mov     qword ptr [rbp+57h+FileMappingAttributes.bInheritHandle], rdi
0x1800b1865  call    cs:__imp_CreateFileMappingW
0x1800b186b  mov     rdi, rax
0x1800b186e  test    rax, rax
0x1800b1871  jz      loc_1800B17A6
0x1800b1877  xor     r9d, r9d; dwFileOffsetLow
0x1800b187a  mov     [rsp+0B0h+PreviousState], rbx; dwNumberOfBytesToMap
0x1800b187f  xor     r8d, r8d; dwFileOffsetHigh
0x1800b1882  lea     edx, [rsi+5]; dwDesiredAccess
0x1800b1885  mov     rcx, rax; hFileMappingObject
0x1800b1888  call    cs:__imp_MapViewOfFile
0x1800b188e  test    rax, rax
0x1800b1891  jz      loc_1800B17A6
0x1800b1897  mov     [r14], rdi
0x1800b189a  xor     edi, edi
0x1800b189c  xor     ebx, ebx
0x1800b189e  mov     [r15], rax
0x1800b18a1  cmp     [rbp+57h+var_40.PrivilegeCount], 0
0x1800b18a5  jz      short loc_1800B18CF
0x1800b18a7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b18ab  lea     r8, [rbp+57h+var_40]; NewState
0x1800b18af  mov     [rsp+0B0h+ReturnLength], 0; ReturnLength
0x1800b18b8  mov     r9d, 10h; BufferLength
0x1800b18be  xor     edx, edx; DisableAllPrivileges
0x1800b18c0  mov     [rsp+0B0h+PreviousState], 0; PreviousState
0x1800b18c9  call    cs:__imp_AdjustTokenPrivileges
0x1800b18cf  test    esi, esi
0x1800b18d1  jz      short loc_1800B18D9
0x1800b18d3  call    cs:__imp_RevertToSelf
0x1800b18d9  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800b18dd  test    rcx, rcx
0x1800b18e0  jz      short loc_1800B18E8
0x1800b18e2  call    cs:__imp_LocalFree
0x1800b18e8  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800b18ec  test    rcx, rcx
0x1800b18ef  jz      short loc_1800B18F7
0x1800b18f1  call    cs:__imp_CloseHandle
0x1800b18f7  test    rdi, rdi
0x1800b18fa  jz      short loc_1800B1905
0x1800b18fc  mov     rcx, rdi; hObject
0x1800b18ff  call    cs:__imp_CloseHandle
0x1800b1905  mov     eax, ebx
0x1800b1907  mov     rcx, [rbp+57h+var_30]
0x1800b190b  xor     rcx, rsp; StackCookie
0x1800b190e  call    __security_check_cookie
0x1800b1913  mov     rbx, [rsp+0B0h+arg_0]
0x1800b191b  add     rsp, 90h
0x1800b1922  pop     r15
0x1800b1924  pop     r14
0x1800b1926  pop     rdi
0x1800b1927  pop     rsi
0x1800b1928  pop     rbp
0x1800b1929  retn
```
