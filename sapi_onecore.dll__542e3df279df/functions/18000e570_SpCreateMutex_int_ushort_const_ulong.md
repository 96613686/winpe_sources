# SpCreateMutex(int,ushort const *,ulong)

- ea: `0x18000e570`
- end: `0x18000e87b`
- name: `?SpCreateMutex@@YAPEAXHPEBGK@Z`
- size: `779`
- prototype: `void *__fastcall(int, const unsigned __int16 *, unsigned int)`
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000aaf0`
- `0x18000d780`
- `0x18004e950`
- `0x1800e89e0`
- `0x1800e90b0`
- `0x1800e9140`
- `0x1800f6334`
- `0x1800f71d4`
- `0x1800fc26c`
- `0x1801a9b54`

## callees

- `0x18000e570`
- `0x18000f080`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000e792`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000e792`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000e76d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000e76d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e870`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e828`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e5d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e5d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e5e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e5e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e85e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e85e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e808`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e808`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e65c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e65c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e60b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e64a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e60b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e64a`

## pseudocode

```c
HANDLE __fastcall SpCreateMutex(__int64 a1, const unsigned __int16 *a2)
{
  PSID *v3; // rsi
  WCHAR *v4; // rdi
  HANDLE CurrentProcess; // rax
  __int64 v6; // rax
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  unsigned __int16 *v11; // rax
  int v12; // edx
  HANDLE MutexW; // rbx
  int i; // edi
  unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // r8
  DWORD v18; // ecx
  PDWORD ReturnLength; // [rsp+28h] [rbp-E0h]
  DWORD TokenInformationLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C8h] BYREF
  __int64 TokenHandle; // [rsp+48h] [rbp-C0h] BYREF
  void *TokenHandle_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h]
  unsigned __int16 v25[260]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+270h] [rbp+168h]
  __int64 v27; // [rsp+280h] [rbp+178h]

  TokenInformationLength[0] = 0;
  v24 = 0;
  TokenHandle = -1;
  *(_OWORD *)TokenHandle_8 = 0;
  v3 = 0;
  StringSid = 0;
  v4 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, (PHANDLE)&TokenHandle) )
  {
    GetTokenInformation((HANDLE)TokenHandle, TokenUser, 0, 0, TokenInformationLength);
    if ( TokenInformationLength[0] )
    {
      v3 = (PSID *)operator new[](TokenInformationLength[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation((HANDLE)TokenHandle, TokenUser, v3, TokenInformationLength[0], TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v3, &StringSid) )
        {
          v6 = -1;
          while ( StringSid[++v6] != 0 )
            ;
          v8 = v6 + 43;
          v10 = v6 + 43;
          v9 = 2 * (v6 + 43);
          if ( !is_mul_ok(v10, 2u) )
            v9 = -1;
          v11 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
          v4 = v11;
          if ( v11 )
          {
            LODWORD(ReturnLength) = 1048577;
            StringCchPrintfW(
              v11,
              v8,
              L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;%s)(A;CIOI;GR;;;AC)",
              1048577,
              ReturnLength,
              StringSid);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &TokenHandle_8[1], 0) )
            {
              LODWORD(TokenHandle_8[0]) = 24;
              LODWORD(v24) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v4);
  operator delete(v3);
  LocalFree(StringSid);
  if ( TokenHandle != -1 )
    CloseHandle((HANDLE)TokenHandle);
  v25[0] = 0;
  v12 = 0;
  if ( a2 && *a2 )
    v12 = StringCchPrintfW(v25, 0x104u, L"%s\\%s", L"Local", a2);
  v27 = 0;
  v26 = 0;
  if ( v12 < 0 )
  {
    v18 = (unsigned __int16)v12;
    if ( (v12 & 0xFFFF0000) != 0x80070000 )
      v18 = v12;
    SetLastError(v18);
    LocalFree(TokenHandle_8[1]);
    return 0;
  }
  else
  {
    MutexW = 0;
    for ( i = 0; i < 100; ++i )
    {
      v15 = v25;
      if ( !v25[0] )
        v15 = 0;
      MutexW = OpenMutexW(0x100000u, 0, v15);
      if ( MutexW )
      {
        SetLastError(0xB7u);
        break;
      }
      v16 = v25;
      if ( !v25[0] )
        v16 = 0;
      MutexW = CreateMutexW(0, 0, v16);
      if ( MutexW || GetLastError() != 5 )
        break;
    }
    LocalFree(TokenHandle_8[1]);
    return MutexW;
  }
}

```

## disassembly

```asm
0x18000e570  mov     r11, rsp
0x18000e573  push    rbp
0x18000e574  push    rbx
0x18000e575  push    rdi
0x18000e576  push    r15
0x18000e578  lea     rbp, [r11-1B8h]
0x18000e57f  sub     rsp, 298h
0x18000e586  mov     rax, cs:__security_cookie
0x18000e58d  xor     rax, rsp
0x18000e590  mov     [rbp+1B0h+var_30], rax
0x18000e597  xor     r15d, r15d
0x18000e59a  mov     [r11+8], rsi
0x18000e59e  mov     [r11+18h], r12
0x18000e5a2  xorps   xmm0, xmm0
0x18000e5a5  xor     eax, eax
0x18000e5a7  mov     [rsp+2B0h+TokenInformationLength], r15d
0x18000e5ac  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000e5b3  mov     [rsp+2B0h+var_258], rax
0x18000e5b8  mov     [rsp+2B0h+TokenHandle], r12
0x18000e5bd  mov     rbx, rdx
0x18000e5c0  movups  xmmword ptr [rsp+2B0h+TokenHandle+8], xmm0
0x18000e5c5  mov     esi, r15d
0x18000e5c8  mov     [rsp+2B0h+StringSid], r15
0x18000e5cd  mov     edi, r15d
0x18000e5d0  call    cs:__imp_GetCurrentProcess
0x18000e5d6  lea     r8, [rsp+2B0h+TokenHandle]; TokenHandle
0x18000e5db  mov     edx, 8; DesiredAccess
0x18000e5e0  mov     rcx, rax; ProcessHandle
0x18000e5e3  call    cs:__imp_OpenProcessToken
0x18000e5e9  test    eax, eax
0x18000e5eb  jz      loc_18000E6BE
0x18000e5f1  mov     rcx, [rsp+2B0h+TokenHandle]; TokenHandle
0x18000e5f6  lea     rax, [rsp+2B0h+TokenInformationLength]
0x18000e5fb  xor     r9d, r9d; TokenInformationLength
0x18000e5fe  mov     [rsp+2B0h+ReturnLength], rax; ReturnLength
0x18000e603  xor     r8d, r8d; TokenInformation
0x18000e606  mov     edx, 1; TokenInformationClass
0x18000e60b  call    cs:__imp_GetTokenInformation
0x18000e611  mov     eax, [rsp+2B0h+TokenInformationLength]
0x18000e615  test    eax, eax
0x18000e617  jz      loc_18000E6BE
0x18000e61d  mov     ecx, eax; unsigned __int64
0x18000e61f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e626  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e62b  mov     r9d, [rsp+2B0h+TokenInformationLength]; TokenInformationLength
0x18000e630  mov     rsi, rax
0x18000e633  mov     rcx, [rsp+2B0h+TokenHandle]; TokenHandle
0x18000e638  lea     rax, [rsp+2B0h+TokenInformationLength]
0x18000e63d  mov     r8, rsi; TokenInformation
0x18000e640  mov     [rsp+2B0h+ReturnLength], rax; ReturnLength
0x18000e645  mov     edx, 1; TokenInformationClass
0x18000e64a  call    cs:__imp_GetTokenInformation
0x18000e650  test    eax, eax
0x18000e652  jz      short loc_18000E6BE
0x18000e654  mov     rcx, [rsi]; Sid
0x18000e657  lea     rdx, [rsp+2B0h+StringSid]; StringSid
0x18000e65c  call    cs:__imp_ConvertSidToStringSidW
0x18000e662  test    eax, eax
0x18000e664  jz      short loc_18000E6BE
0x18000e666  mov     rcx, [rsp+2B0h+StringSid]
0x18000e66b  mov     rax, r12
0x18000e66e  mov     [rsp+290h], r14
0x18000e676  nop     word ptr [rax+rax+00000000h]
0x18000e680  cmp     [rcx+rax*2+2], di
0x18000e685  lea     rax, [rax+1]
0x18000e689  jnz     short loc_18000E680
0x18000e68b  lea     r14, [rax+2Bh]
0x18000e68f  mov     eax, 2
0x18000e694  mul     r14
0x18000e697  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e69e  cmovb   rax, r12
0x18000e6a2  mov     rcx, rax; unsigned __int64
0x18000e6a5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e6aa  mov     rdi, rax
0x18000e6ad  test    rax, rax
0x18000e6b0  jnz     loc_18000E7CE
0x18000e6b6  mov     r14, [rsp+290h]
0x18000e6be  mov     rcx, rdi; Block
0x18000e6c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e6c6  mov     rcx, rsi; Block
0x18000e6c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e6ce  mov     rcx, [rsp+2B0h+StringSid]; hMem
0x18000e6d3  call    cs:__imp_LocalFree
0x18000e6d9  mov     rcx, [rsp+2B0h+TokenHandle]; hObject
0x18000e6de  mov     r12, [rsp+2B0h+arg_10]
0x18000e6e6  mov     rsi, [rsp+2B0h+arg_0]
0x18000e6ee  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e6f2  jz      short loc_18000E6FA
0x18000e6f4  call    cs:__imp_CloseHandle
0x18000e6fa  mov     [rsp+2B0h+var_250], r15w
0x18000e700  mov     edx, r15d
0x18000e703  test    rbx, rbx
0x18000e706  jz      short loc_18000E731
0x18000e708  cmp     [rbx], dx
0x18000e70b  jz      short loc_18000E731
0x18000e70d  lea     r9, aLocal_0; "Local"
0x18000e714  mov     [rsp+2B0h+ReturnLength], rbx
0x18000e719  lea     r8, aSS; "%s\\%s"
0x18000e720  mov     edx, 104h; unsigned __int64
0x18000e725  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18000e72a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e72f  mov     edx, eax
0x18000e731  xor     eax, eax
0x18000e733  xorps   xmm0, xmm0
0x18000e736  mov     [rbp+1B0h+var_38], rax
0x18000e73d  movups  [rbp+1B0h+var_48], xmm0
0x18000e744  test    edx, edx
0x18000e746  js      loc_18000E83E
0x18000e74c  mov     rbx, r15
0x18000e74f  mov     edi, r15d
0x18000e752  cmp     edi, 64h ; 'd'
0x18000e755  jge     short loc_18000E7A4
0x18000e757  cmp     [rsp+2B0h+var_250], r15w
0x18000e75d  lea     r8, [rsp+2B0h+var_250]
0x18000e762  mov     ecx, 100000h; dwDesiredAccess
0x18000e767  cmovz   r8, r15; lpName
0x18000e76b  xor     edx, edx; bInheritHandle
0x18000e76d  call    cs:__imp_OpenMutexW
0x18000e773  mov     rbx, rax
0x18000e776  test    rax, rax
0x18000e779  jnz     loc_18000E86B
0x18000e77f  cmp     [rsp+2B0h+var_250], r15w
0x18000e785  lea     r8, [rsp+2B0h+var_250]
0x18000e78a  cmovz   r8, r15; lpName
0x18000e78e  xor     edx, edx; bInitialOwner
0x18000e790  xor     ecx, ecx; lpMutexAttributes
0x18000e792  call    cs:__imp_CreateMutexW
0x18000e798  mov     rbx, rax
0x18000e79b  test    rax, rax
0x18000e79e  jz      loc_18000E828
0x18000e7a4  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18000e7a9  call    cs:__imp_LocalFree
0x18000e7af  mov     rax, rbx
0x18000e7b2  mov     rcx, [rbp+1B0h+var_30]
0x18000e7b9  xor     rcx, rsp; StackCookie
0x18000e7bc  call    __security_check_cookie
0x18000e7c1  add     rsp, 298h
0x18000e7c8  pop     r15
0x18000e7ca  pop     rdi
0x18000e7cb  pop     rbx
0x18000e7cc  pop     rbp
0x18000e7cd  retn
0x18000e7ce  mov     rcx, [rsp+2B0h+StringSid]
0x18000e7d3  lea     r8, aDPACioi0x08xAu_0; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x18000e7da  mov     qword ptr [rsp+2B0h+var_288], rcx
0x18000e7df  mov     r9d, 100001h
0x18000e7e5  mov     rcx, rdi; unsigned __int16 *
0x18000e7e8  mov     dword ptr [rsp+2B0h+ReturnLength], 100001h
0x18000e7f0  mov     rdx, r14; unsigned __int64
0x18000e7f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e7f8  xor     r9d, r9d; SecurityDescriptorSize
0x18000e7fb  lea     r8, [rsp+2B0h+hMem]; SecurityDescriptor
0x18000e800  mov     edx, 1; StringSDRevision
0x18000e805  mov     rcx, rdi; StringSecurityDescriptor
0x18000e808  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000e80e  test    eax, eax
0x18000e810  jz      loc_18000E6B6
0x18000e816  mov     dword ptr [rsp+2B0h+TokenHandle+8], 18h
0x18000e81e  mov     dword ptr [rsp+2B0h+var_258], r15d
0x18000e823  jmp     loc_18000E6B6
0x18000e828  call    cs:__imp_GetLastError
0x18000e82e  cmp     eax, 5
0x18000e831  jnz     loc_18000E7A4
0x18000e837  inc     edi
0x18000e839  jmp     loc_18000E752
0x18000e83e  mov     ecx, edx
0x18000e840  and     ecx, 0FFFF0000h
0x18000e846  cmp     ecx, 80070000h
0x18000e84c  movzx   ecx, dx
0x18000e84f  jz      short loc_18000E853
0x18000e851  mov     ecx, edx; dwErrCode
0x18000e853  call    cs:__imp_SetLastError
0x18000e859  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18000e85e  call    cs:__imp_LocalFree
0x18000e864  xor     eax, eax
0x18000e866  jmp     loc_18000E7B2
0x18000e86b  mov     ecx, 0B7h; dwErrCode
0x18000e870  call    cs:__imp_SetLastError
0x18000e876  jmp     loc_18000E7A4
```
