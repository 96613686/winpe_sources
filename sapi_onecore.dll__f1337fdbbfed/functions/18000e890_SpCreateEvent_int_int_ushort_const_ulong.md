# SpCreateEvent(int,int,ushort const *,ulong)

- ea: `0x18000e890`
- end: `0x18000eb7c`
- name: `?SpCreateEvent@@YAPEAXHHPEBGK@Z`
- size: `748`
- prototype: `void *__fastcall(BOOL bManualReset, BOOL bInitialState, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180018e50`
- `0x1800ee8cc`
- `0x1801add20`

## callees

- `0x18000e890`
- `0x18000f080`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ea93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ea93`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ea6b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ea6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e8f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e8f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e905`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e9f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e9f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000eb1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000eb1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e97e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e97e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e92d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e96c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e92d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e96c`

## pseudocode

```c
HANDLE __fastcall SpCreateEvent(BOOL bManualReset, BOOL bInitialState, const unsigned __int16 *a3, unsigned int a4)
{
  PSID *v8; // r15
  WCHAR *v9; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v11; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  unsigned __int16 *v16; // rax
  int v17; // edx
  DWORD v18; // esi
  HANDLE EventW; // rbx
  int i; // edi
  unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // r9
  DWORD v24; // ecx
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v31[260]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+268h] [rbp+168h]
  __int64 v33; // [rsp+278h] [rbp+178h]

  v30 = 0;
  *(_OWORD *)hMem = 0;
  TokenHandle = (void *)-1LL;
  TokenInformationLength = 0;
  StringSid = 0;
  v8 = 0;
  v9 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v8 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v8, &StringSid) )
        {
          v11 = -1;
          while ( StringSid[++v11] != 0 )
            ;
          v13 = v11 + 43;
          v15 = v11 + 43;
          v14 = 2 * (v11 + 43);
          if ( !is_mul_ok(v15, 2u) )
            v14 = -1;
          v16 = (unsigned __int16 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
          v9 = v16;
          if ( v16 )
          {
            LODWORD(ReturnLength) = a4 | 2;
            StringCchPrintfW(
              v16,
              v13,
              L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;%s)(A;CIOI;GR;;;AC)",
              a4,
              ReturnLength,
              StringSid);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &hMem[1], 0) )
            {
              LODWORD(hMem[0]) = 24;
              LODWORD(v30) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v9);
  operator delete(v8);
  LocalFree(StringSid);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  v17 = 0;
  v31[0] = 0;
  if ( a3 && *a3 )
    v17 = StringCchPrintfW(v31, 0x104u, L"%s\\%s", L"Local", a3);
  v33 = 0;
  v32 = 0;
  if ( v17 < 0 )
  {
    v24 = (unsigned __int16)v17;
    if ( (v17 & 0xFFFF0000) != 0x80070000 )
      v24 = v17;
    SetLastError(v24);
    LocalFree(hMem[1]);
    return 0;
  }
  else
  {
    v18 = a4 & 0xFFFFFFFD;
    EventW = 0;
    for ( i = 0; i < 100; ++i )
    {
      v21 = v31;
      if ( !v31[0] )
        v21 = 0;
      EventW = OpenEventW(v18, 0, v21);
      if ( EventW )
      {
        SetLastError(0xB7u);
        break;
      }
      v22 = v31;
      if ( !v31[0] )
        v22 = 0;
      EventW = CreateEventW(0, bManualReset, bInitialState, v22);
      if ( EventW || GetLastError() != 5 )
        break;
    }
    LocalFree(hMem[1]);
    return EventW;
  }
}

```

## disassembly

```asm
0x18000e890  push    rbp
0x18000e892  push    rbx
0x18000e893  push    rsi
0x18000e894  push    rdi
0x18000e895  push    r12
0x18000e897  push    r13
0x18000e899  push    r14
0x18000e89b  push    r15
0x18000e89d  lea     rbp, [rsp-198h]
0x18000e8a5  sub     rsp, 298h
0x18000e8ac  mov     rax, cs:__security_cookie
0x18000e8b3  xor     rax, rsp
0x18000e8b6  mov     [rbp+1D0h+var_50], rax
0x18000e8bd  xor     eax, eax
0x18000e8bf  xorps   xmm0, xmm0
0x18000e8c2  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000e8c9  mov     [rsp+2D0h+var_278], rax
0x18000e8ce  movups  xmmword ptr [rsp+2D0h+hMem], xmm0
0x18000e8d3  mov     [rsp+2D0h+TokenHandle], r14
0x18000e8d8  mov     esi, r9d
0x18000e8db  mov     [rsp+2D0h+TokenInformationLength], eax
0x18000e8df  mov     rdi, r8
0x18000e8e2  mov     [rsp+2D0h+StringSid], rax
0x18000e8e7  mov     r13d, edx
0x18000e8ea  mov     r12d, ecx
0x18000e8ed  xor     r15d, r15d
0x18000e8f0  xor     ebx, ebx
0x18000e8f2  call    cs:__imp_GetCurrentProcess
0x18000e8f8  lea     r8, [rsp+2D0h+TokenHandle]; TokenHandle
0x18000e8fd  mov     edx, 8; DesiredAccess
0x18000e902  mov     rcx, rax; ProcessHandle
0x18000e905  call    cs:__imp_OpenProcessToken
0x18000e90b  test    eax, eax
0x18000e90d  jz      loc_18000E9CD
0x18000e913  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x18000e918  lea     rax, [rsp+2D0h+TokenInformationLength]
0x18000e91d  xor     r9d, r9d; TokenInformationLength
0x18000e920  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x18000e925  xor     r8d, r8d; TokenInformation
0x18000e928  mov     edx, 1; TokenInformationClass
0x18000e92d  call    cs:__imp_GetTokenInformation
0x18000e933  mov     eax, [rsp+2D0h+TokenInformationLength]
0x18000e937  test    eax, eax
0x18000e939  jz      loc_18000E9CD
0x18000e93f  mov     ecx, eax; unsigned __int64
0x18000e941  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e948  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e94d  mov     r9d, [rsp+2D0h+TokenInformationLength]; TokenInformationLength
0x18000e952  mov     r15, rax
0x18000e955  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x18000e95a  lea     rax, [rsp+2D0h+TokenInformationLength]
0x18000e95f  mov     r8, r15; TokenInformation
0x18000e962  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x18000e967  mov     edx, 1; TokenInformationClass
0x18000e96c  call    cs:__imp_GetTokenInformation
0x18000e972  test    eax, eax
0x18000e974  jz      short loc_18000E9CD
0x18000e976  mov     rcx, [r15]; Sid
0x18000e979  lea     rdx, [rsp+2D0h+StringSid]; StringSid
0x18000e97e  call    cs:__imp_ConvertSidToStringSidW
0x18000e984  test    eax, eax
0x18000e986  jz      short loc_18000E9CD
0x18000e988  mov     rcx, [rsp+2D0h+StringSid]
0x18000e98d  mov     rax, r14
0x18000e990  cmp     [rcx+rax*2+2], bx
0x18000e995  lea     rax, [rax+1]
0x18000e999  jnz     short loc_18000E990
0x18000e99b  lea     r14, [rax+2Bh]
0x18000e99f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e9a6  mov     eax, 2
0x18000e9ab  mul     r14
0x18000e9ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e9b5  cmovb   rax, rcx
0x18000e9b9  mov     rcx, rax; unsigned __int64
0x18000e9bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e9c1  mov     rbx, rax
0x18000e9c4  test    rax, rax
0x18000e9c7  jnz     loc_18000EAE1
0x18000e9cd  mov     rcx, rbx; Block
0x18000e9d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e9d5  mov     rcx, r15; Block
0x18000e9d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e9dd  mov     rcx, [rsp+2D0h+StringSid]; hMem
0x18000e9e2  call    cs:__imp_LocalFree
0x18000e9e8  mov     rcx, [rsp+2D0h+TokenHandle]; hObject
0x18000e9ed  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e9f1  jz      short loc_18000E9F9
0x18000e9f3  call    cs:__imp_CloseHandle
0x18000e9f9  xor     eax, eax
0x18000e9fb  xor     edx, edx
0x18000e9fd  mov     [rsp+2D0h+var_270], ax
0x18000ea02  test    rdi, rdi
0x18000ea05  jz      short loc_18000EA30
0x18000ea07  cmp     [rdi], ax
0x18000ea0a  jz      short loc_18000EA30
0x18000ea0c  lea     r9, aLocal_0; "Local"
0x18000ea13  mov     [rsp+2D0h+ReturnLength], rdi
0x18000ea18  lea     r8, aSS; "%s\\%s"
0x18000ea1f  mov     edx, 104h; unsigned __int64
0x18000ea24  lea     rcx, [rsp+2D0h+var_270]; unsigned __int16 *
0x18000ea29  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ea2e  mov     edx, eax
0x18000ea30  xor     eax, eax
0x18000ea32  xorps   xmm0, xmm0
0x18000ea35  mov     [rbp+1D0h+var_58], rax
0x18000ea3c  movups  [rbp+1D0h+var_68], xmm0
0x18000ea43  test    edx, edx
0x18000ea45  js      loc_18000EB3F
0x18000ea4b  and     esi, 0FFFFFFFDh
0x18000ea4e  xor     ebx, ebx
0x18000ea50  xor     edi, edi
0x18000ea52  cmp     edi, 64h ; 'd'
0x18000ea55  jge     short loc_18000EAB0
0x18000ea57  xor     eax, eax
0x18000ea59  lea     r8, [rsp+2D0h+var_270]
0x18000ea5e  cmp     [rsp+2D0h+var_270], ax
0x18000ea63  mov     ecx, esi; dwDesiredAccess
0x18000ea65  cmovz   r8, rax; lpName
0x18000ea69  xor     edx, edx; bInheritHandle
0x18000ea6b  call    cs:__imp_OpenEventW
0x18000ea71  mov     rbx, rax
0x18000ea74  test    rax, rax
0x18000ea77  jnz     loc_18000EB6C
0x18000ea7d  cmp     [rsp+2D0h+var_270], ax
0x18000ea82  lea     r9, [rsp+2D0h+var_270]
0x18000ea87  mov     r8d, r13d; bInitialState
0x18000ea8a  mov     edx, r12d; bManualReset
0x18000ea8d  cmovz   r9, rax; lpName
0x18000ea91  xor     ecx, ecx; lpEventAttributes
0x18000ea93  call    cs:__imp_CreateEventW
0x18000ea99  mov     rbx, rax
0x18000ea9c  test    rax, rax
0x18000ea9f  jnz     short loc_18000EAB0
0x18000eaa1  call    cs:__imp_GetLastError
0x18000eaa7  cmp     eax, 5
0x18000eaaa  jnz     short loc_18000EAB0
0x18000eaac  inc     edi
0x18000eaae  jmp     short loc_18000EA52
0x18000eab0  mov     rcx, [rsp+2D0h+hMem+8]; hMem
0x18000eab5  call    cs:__imp_LocalFree
0x18000eabb  mov     rax, rbx
0x18000eabe  mov     rcx, [rbp+1D0h+var_50]
0x18000eac5  xor     rcx, rsp; StackCookie
0x18000eac8  call    __security_check_cookie
0x18000eacd  add     rsp, 298h
0x18000ead4  pop     r15
0x18000ead6  pop     r14
0x18000ead8  pop     r13
0x18000eada  pop     r12
0x18000eadc  pop     rdi
0x18000eadd  pop     rsi
0x18000eade  pop     rbx
0x18000eadf  pop     rbp
0x18000eae0  retn
0x18000eae1  mov     rcx, [rsp+2D0h+StringSid]
0x18000eae6  mov     r8d, esi
0x18000eae9  or      r8d, 2
0x18000eaed  mov     [rsp+2D0h+var_2A8], rcx
0x18000eaf2  mov     dword ptr [rsp+2D0h+ReturnLength], r8d
0x18000eaf7  mov     r9d, esi
0x18000eafa  lea     r8, aDPACioi0x08xAu_0; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x18000eb01  mov     rdx, r14; unsigned __int64
0x18000eb04  mov     rcx, rbx; unsigned __int16 *
0x18000eb07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eb0c  xor     r9d, r9d; SecurityDescriptorSize
0x18000eb0f  lea     r8, [rsp+2D0h+hMem+8]; SecurityDescriptor
0x18000eb14  mov     edx, 1; StringSDRevision
0x18000eb19  mov     rcx, rbx; StringSecurityDescriptor
0x18000eb1c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000eb22  test    eax, eax
0x18000eb24  jz      loc_18000E9CD
0x18000eb2a  mov     dword ptr [rsp+2D0h+hMem], 18h
0x18000eb32  mov     dword ptr [rsp+2D0h+var_278], 0
0x18000eb3a  jmp     loc_18000E9CD
0x18000eb3f  mov     ecx, edx
0x18000eb41  and     ecx, 0FFFF0000h
0x18000eb47  cmp     ecx, 80070000h
0x18000eb4d  movzx   ecx, dx
0x18000eb50  jz      short loc_18000EB54
0x18000eb52  mov     ecx, edx; dwErrCode
0x18000eb54  call    cs:__imp_SetLastError
0x18000eb5a  mov     rcx, [rsp+2D0h+hMem+8]; hMem
0x18000eb5f  call    cs:__imp_LocalFree
0x18000eb65  xor     eax, eax
0x18000eb67  jmp     loc_18000EABE
0x18000eb6c  mov     ecx, 0B7h; dwErrCode
0x18000eb71  call    cs:__imp_SetLastError
0x18000eb77  jmp     loc_18000EAB0
```
