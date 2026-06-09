# CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)

- ea: `0x18000f110`
- end: `0x18000f303`
- name: `??0CSpSecurityAttribute@@QEAA@KK@Z`
- size: `499`
- prototype: `CSpSecurityAttribute *__fastcall(CSpSecurityAttribute *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800c869c`
- `0x1800f1b60`
- `0x1800f7a98`

## callees

- `0x18000f080`
- `0x18000f110`
- `0x18007a2dc`
- `0x18007a350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f161`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f174`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f174`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f26f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f26f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f2e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f2e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f1fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f1fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f19f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f1e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f19f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f1e7`

## pseudocode

```c
CSpSecurityAttribute *__fastcall CSpSecurityAttribute::CSpSecurityAttribute(
        CSpSecurityAttribute *this,
        unsigned int a2,
        int a3)
{
  PSID *v4; // rdi
  WCHAR *v6; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v9; // rax
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // kr00_8
  unsigned __int16 *v14; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-58h]
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  *(_OWORD *)this = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  v6 = 0;
  *((_QWORD *)this + 2) = 0;
  TokenHandle = (void *)-1LL;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v4 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v4, &StringSid) )
        {
          v9 = -1;
          while ( StringSid[++v9] != 0 )
            ;
          v11 = v9 + 43;
          v13 = v9 + 43;
          v12 = 2 * (v9 + 43);
          if ( !is_mul_ok(v13, 2u) )
            v12 = -1;
          v14 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
          v6 = v14;
          if ( v14 )
          {
            LODWORD(ReturnLength) = a3;
            StringCchPrintfW(
              v14,
              v11,
              L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;%s)(A;CIOI;GR;;;AC)",
              a2,
              ReturnLength,
              StringSid);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, (PSECURITY_DESCRIPTOR *)this + 1, 0) )
            {
              *(_DWORD *)this = 24;
              *((_DWORD *)this + 4) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v6);
  operator delete(v4);
  LocalFree(StringSid);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return this;
}

```

## disassembly

```asm
0x18000f110  mov     r11, rsp
0x18000f113  push    rsi
0x18000f114  sub     rsp, 70h
0x18000f118  mov     [r11+10h], rbx
0x18000f11c  xorps   xmm0, xmm0
0x18000f11f  mov     [r11-18h], rdi
0x18000f123  xor     eax, eax
0x18000f125  mov     [r11-20h], r12
0x18000f129  mov     rsi, rcx
0x18000f12c  mov     [r11-28h], r13
0x18000f130  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000f137  xor     r13d, r13d
0x18000f13a  mov     [r11-30h], r14
0x18000f13e  mov     [r11-38h], r15
0x18000f142  mov     edi, r13d
0x18000f145  movups  xmmword ptr [rcx], xmm0
0x18000f148  mov     r15d, edx
0x18000f14b  mov     [r11+8], r13d
0x18000f14f  mov     [r11+20h], r13
0x18000f153  mov     ebx, r13d
0x18000f156  mov     r14d, r8d
0x18000f159  mov     [rcx+10h], rax
0x18000f15d  mov     [r11-48h], r12
0x18000f161  call    cs:__imp_GetCurrentProcess
0x18000f167  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x18000f16c  mov     edx, 8; DesiredAccess
0x18000f171  mov     rcx, rax; ProcessHandle
0x18000f174  call    cs:__imp_OpenProcessToken
0x18000f17a  test    eax, eax
0x18000f17c  jz      loc_18000F257
0x18000f182  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000f187  lea     rax, [rsp+78h+TokenInformationLength]
0x18000f18f  xor     r9d, r9d; TokenInformationLength
0x18000f192  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f197  xor     r8d, r8d; TokenInformation
0x18000f19a  mov     edx, 1; TokenInformationClass
0x18000f19f  call    cs:__imp_GetTokenInformation
0x18000f1a5  mov     eax, [rsp+78h+TokenInformationLength]
0x18000f1ac  test    eax, eax
0x18000f1ae  jz      loc_18000F257
0x18000f1b4  mov     ecx, eax; unsigned __int64
0x18000f1b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f1bd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f1c2  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18000f1ca  mov     rdi, rax
0x18000f1cd  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000f1d2  lea     rax, [rsp+78h+TokenInformationLength]
0x18000f1da  mov     r8, rdi; TokenInformation
0x18000f1dd  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f1e2  mov     edx, 1; TokenInformationClass
0x18000f1e7  call    cs:__imp_GetTokenInformation
0x18000f1ed  test    eax, eax
0x18000f1ef  jz      short loc_18000F257
0x18000f1f1  mov     rcx, [rdi]; Sid
0x18000f1f4  lea     rdx, [rsp+78h+StringSid]; StringSid
0x18000f1fc  call    cs:__imp_ConvertSidToStringSidW
0x18000f202  test    eax, eax
0x18000f204  jz      short loc_18000F257
0x18000f206  mov     rcx, [rsp+78h+StringSid]
0x18000f20e  mov     rax, r12
0x18000f211  mov     [rsp+78h+var_10], rbp
0x18000f216  nop     word ptr [rax+rax+00000000h]
0x18000f220  cmp     [rcx+rax*2+2], bx
0x18000f225  lea     rax, [rax+1]
0x18000f229  jnz     short loc_18000F220
0x18000f22b  lea     rbp, [rax+2Bh]
0x18000f22f  mov     eax, 2
0x18000f234  mul     rbp
0x18000f237  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f23e  cmovb   rax, r12
0x18000f242  mov     rcx, rax; unsigned __int64
0x18000f245  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f24a  mov     rbx, rax
0x18000f24d  test    rax, rax
0x18000f250  jnz     short loc_18000F2B0
0x18000f252  mov     rbp, [rsp+78h+var_10]
0x18000f257  mov     rcx, rbx; Block
0x18000f25a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f25f  mov     rcx, rdi; Block
0x18000f262  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f267  mov     rcx, [rsp+78h+StringSid]; hMem
0x18000f26f  call    cs:__imp_LocalFree
0x18000f275  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18000f27a  mov     r15, [rsp+78h+var_38]
0x18000f27f  mov     r14, [rsp+78h+var_30]
0x18000f284  mov     r13, [rsp+78h+var_28]
0x18000f289  mov     r12, [rsp+78h+var_20]
0x18000f28e  mov     rdi, [rsp+78h+var_18]
0x18000f293  mov     rbx, [rsp+78h+arg_8]
0x18000f29b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f29f  jz      short loc_18000F2A7
0x18000f2a1  call    cs:__imp_CloseHandle
0x18000f2a7  mov     rax, rsi
0x18000f2aa  add     rsp, 70h
0x18000f2ae  pop     rsi
0x18000f2af  retn
0x18000f2b0  mov     rcx, [rsp+78h+StringSid]
0x18000f2b8  lea     r8, aDPACioi0x08xAu_0; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x18000f2bf  mov     [rsp+78h+var_50], rcx
0x18000f2c4  mov     r9d, r15d
0x18000f2c7  mov     rcx, rbx; unsigned __int16 *
0x18000f2ca  mov     dword ptr [rsp+78h+ReturnLength], r14d
0x18000f2cf  mov     rdx, rbp; unsigned __int64
0x18000f2d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f2d7  lea     r8, [rsi+8]; SecurityDescriptor
0x18000f2db  xor     r9d, r9d; SecurityDescriptorSize
0x18000f2de  mov     edx, 1; StringSDRevision
0x18000f2e3  mov     rcx, rbx; StringSecurityDescriptor
0x18000f2e6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000f2ec  test    eax, eax
0x18000f2ee  jz      loc_18000F252
0x18000f2f4  mov     dword ptr [rsi], 18h
0x18000f2fa  mov     [rsi+10h], r13d
0x18000f2fe  jmp     loc_18000F252
```
