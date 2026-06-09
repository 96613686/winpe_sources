# CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong,ulong)

- ea: `0x1801a71f4`
- end: `0x1801a739b`
- name: `??0CSpSecurityAttribute@@QEAA@KKK@Z`
- size: `423`
- prototype: `CSpSecurityAttribute *__fastcall(CSpSecurityAttribute *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801acd30`

## callees

- `0x18000f080`
- `0x18007a2dc`
- `0x18007a350`
- `0x1801a71f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801a723a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801a723a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801a724c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801a724c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a7379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a7379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801a736a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801a736a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a7342`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a7342`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801a72c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801a72c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801a7272`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801a72ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801a7272`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801a72ad`

## pseudocode

```c
CSpSecurityAttribute *__fastcall CSpSecurityAttribute::CSpSecurityAttribute(CSpSecurityAttribute *this)
{
  PSID *v2; // rsi
  unsigned __int16 *v3; // rdi
  HANDLE CurrentProcess; // rax
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // kr00_8
  PDWORD ReturnLength; // [rsp+20h] [rbp-30h]
  int v11; // [rsp+28h] [rbp-28h]
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+98h] [rbp+48h] BYREF

  TokenInformationLength = 0;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  TokenHandle = (void *)-1LL;
  v2 = 0;
  StringSid = 0;
  v3 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v2 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v2, &StringSid) )
        {
          v5 = -1;
          do
            ++v5;
          while ( StringSid[v5] );
          v6 = v5 + 63;
          v8 = v5 + 63;
          v7 = 2 * (v5 + 63);
          if ( !is_mul_ok(v8, 2u) )
            v7 = -1;
          v3 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
          if ( v3 )
          {
            v11 = 1048578;
            LODWORD(ReturnLength) = 1048578;
            StringCchPrintfW(
              v3,
              v6,
              L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;BA)(A;CIOI;0x%08X;;;%s)",
              0x100000,
              ReturnLength,
              v11,
              StringSid);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, (PSECURITY_DESCRIPTOR *)this + 1, 0) )
            {
              *(_DWORD *)this = 24;
              *((_DWORD *)this + 4) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v3);
  operator delete(v2);
  LocalFree(StringSid);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return this;
}

```

## disassembly

```asm
0x1801a71f4  mov     [rsp-28h+arg_8], rbx
0x1801a71f9  mov     [rsp-28h+arg_10], rsi
0x1801a71fe  mov     [rsp-28h+TokenInformationLength], r9d
0x1801a7203  push    rbp
0x1801a7204  push    rdi
0x1801a7205  push    r12
0x1801a7207  push    r14
0x1801a7209  push    r15
0x1801a720b  mov     rbp, rsp
0x1801a720e  sub     rsp, 50h
0x1801a7212  xor     r15d, r15d
0x1801a7215  xorps   xmm0, xmm0
0x1801a7218  xor     eax, eax
0x1801a721a  mov     [rbp+TokenInformationLength], r15d
0x1801a721e  movups  xmmword ptr [rcx], xmm0
0x1801a7221  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a7225  mov     [rcx+10h], rax
0x1801a7229  mov     rbx, rcx
0x1801a722c  mov     [rbp+TokenHandle], r12
0x1801a7230  mov     esi, r15d
0x1801a7233  mov     [rbp+StringSid], r15
0x1801a7237  mov     edi, r15d
0x1801a723a  call    cs:__imp_GetCurrentProcess
0x1801a7240  mov     rcx, rax; ProcessHandle
0x1801a7243  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801a7247  lea     edx, [r12+9]; DesiredAccess
0x1801a724c  call    cs:__imp_OpenProcessToken
0x1801a7252  test    eax, eax
0x1801a7254  jz      loc_1801A7356
0x1801a725a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801a725e  lea     rax, [rbp+TokenInformationLength]
0x1801a7262  xor     r9d, r9d; TokenInformationLength
0x1801a7265  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1801a726a  xor     r8d, r8d; TokenInformation
0x1801a726d  lea     edx, [r12+2]; TokenInformationClass
0x1801a7272  call    cs:__imp_GetTokenInformation
0x1801a7278  mov     eax, [rbp+TokenInformationLength]
0x1801a727b  test    eax, eax
0x1801a727d  jz      loc_1801A7356
0x1801a7283  mov     ecx, eax; unsigned __int64
0x1801a7285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801a728c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801a7291  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1801a7295  lea     edx, [r12+2]; TokenInformationClass
0x1801a729a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801a729e  mov     rsi, rax
0x1801a72a1  lea     rax, [rbp+TokenInformationLength]
0x1801a72a5  mov     r8, rsi; TokenInformation
0x1801a72a8  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1801a72ad  call    cs:__imp_GetTokenInformation
0x1801a72b3  test    eax, eax
0x1801a72b5  jz      loc_1801A7356
0x1801a72bb  mov     rcx, [rsi]; Sid
0x1801a72be  lea     rdx, [rbp+StringSid]; StringSid
0x1801a72c2  call    cs:__imp_ConvertSidToStringSidW
0x1801a72c8  test    eax, eax
0x1801a72ca  jz      loc_1801A7356
0x1801a72d0  mov     rcx, [rbp+StringSid]
0x1801a72d4  mov     rax, r12
0x1801a72d7  inc     rax
0x1801a72da  cmp     [rcx+rax*2], r15w
0x1801a72df  jnz     short loc_1801A72D7
0x1801a72e1  lea     r14, [rax+3Fh]
0x1801a72e5  mov     eax, 2
0x1801a72ea  mul     r14
0x1801a72ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801a72f4  cmovb   rax, r12
0x1801a72f8  mov     rcx, rax; unsigned __int64
0x1801a72fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801a7300  mov     rdi, rax
0x1801a7303  test    rax, rax
0x1801a7306  jz      short loc_1801A7356
0x1801a7308  mov     rcx, [rbp+StringSid]
0x1801a730c  lea     r8, aDPACioi0x08xAu; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x1801a7313  mov     eax, 100002h
0x1801a7318  mov     [rsp+50h+var_20], rcx
0x1801a731d  mov     [rsp+50h+var_28], eax
0x1801a7321  mov     rdx, r14; unsigned __int64
0x1801a7324  mov     rcx, rdi; unsigned __int16 *
0x1801a7327  mov     dword ptr [rsp+50h+ReturnLength], eax
0x1801a732b  lea     r9d, [rax-2]
0x1801a732f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a7334  xor     r9d, r9d; SecurityDescriptorSize
0x1801a7337  lea     r8, [rbx+8]; SecurityDescriptor
0x1801a733b  mov     rcx, rdi; StringSecurityDescriptor
0x1801a733e  lea     edx, [r9+1]; StringSDRevision
0x1801a7342  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801a7348  test    eax, eax
0x1801a734a  jz      short loc_1801A7356
0x1801a734c  mov     dword ptr [rbx], 18h
0x1801a7352  mov     [rbx+10h], r15d
0x1801a7356  mov     rcx, rdi; Block
0x1801a7359  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a735e  mov     rcx, rsi; Block
0x1801a7361  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a7366  mov     rcx, [rbp+StringSid]; hMem
0x1801a736a  call    cs:__imp_LocalFree
0x1801a7370  mov     rcx, [rbp+TokenHandle]; hObject
0x1801a7374  cmp     rcx, r12
0x1801a7377  jz      short loc_1801A737F
0x1801a7379  call    cs:__imp_CloseHandle
0x1801a737f  lea     r11, [rsp+50h+var_s0]
0x1801a7384  mov     rax, rbx
0x1801a7387  mov     rbx, [r11+38h]
0x1801a738b  mov     rsi, [r11+40h]
0x1801a738f  mov     rsp, r11
0x1801a7392  pop     r15
0x1801a7394  pop     r14
0x1801a7396  pop     r12
0x1801a7398  pop     rdi
0x1801a7399  pop     rbp
0x1801a739a  retn
```
