# CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)

- ea: `0x1800067d4`
- end: `0x180006974`
- name: `??0CSpSecurityAttribute@@QEAA@KK@Z`
- size: `416`
- prototype: `CSpSecurityAttribute *__fastcall(CSpSecurityAttribute *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800136ec`
- `0x1800fdf04`

## callees

- `0x180002e00`
- `0x180003650`
- `0x1800060c0`
- `0x1800067d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006943`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000691b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000691b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800068a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800068a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006852`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000688b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006852`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000688b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000682a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000682a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006819`

## pseudocode

```c
CSpSecurityAttribute *__fastcall CSpSecurityAttribute::CSpSecurityAttribute(
        CSpSecurityAttribute *this,
        unsigned int a2,
        int a3)
{
  PSID *v6; // rsi
  WCHAR *v7; // rdi
  HANDLE CurrentProcess; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // kr00_8
  unsigned __int16 *v13; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-20h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp+58h] BYREF

  TokenHandle = (HANDLE)-1LL;
  TokenInformationLength = 0;
  StringSid = 0;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  v6 = 0;
  v7 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v6 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v6, &StringSid) )
        {
          v9 = -1;
          do
            ++v9;
          while ( StringSid[v9] );
          v10 = v9 + 43;
          v12 = v9 + 43;
          v11 = 2 * (v9 + 43);
          if ( !is_mul_ok(v12, 2u) )
            v11 = -1;
          v13 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
          v7 = v13;
          if ( v13 )
          {
            LODWORD(ReturnLength) = a3;
            StringCchPrintfW(
              v13,
              v10,
              L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;%s)(A;CIOI;GR;;;AC)",
              a2,
              ReturnLength,
              StringSid);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, (PSECURITY_DESCRIPTOR *)this + 1, 0) )
            {
              *(_DWORD *)this = 24;
              *((_DWORD *)this + 4) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v7);
  operator delete(v6);
  LocalFree(StringSid);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return this;
}

```

## disassembly

```asm
0x1800067d4  mov     [rsp-38h+arg_8], rbx
0x1800067d9  push    rbp
0x1800067da  push    rsi
0x1800067db  push    rdi
0x1800067dc  push    r12
0x1800067de  push    r13
0x1800067e0  push    r14
0x1800067e2  push    r15
0x1800067e4  mov     rbp, rsp
0x1800067e7  sub     rsp, 40h
0x1800067eb  xor     r13d, r13d
0x1800067ee  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800067f6  xorps   xmm0, xmm0
0x1800067f9  mov     [rbp+TokenInformationLength], r13d
0x1800067fd  xor     eax, eax
0x1800067ff  mov     [rbp+StringSid], r13
0x180006803  movups  xmmword ptr [rcx], xmm0
0x180006806  mov     [rcx+10h], rax
0x18000680a  mov     r15d, r8d
0x18000680d  mov     r12d, edx
0x180006810  mov     rbx, rcx
0x180006813  mov     esi, r13d
0x180006816  mov     edi, r13d
0x180006819  call    cs:__imp_GetCurrentProcess
0x18000681f  mov     rcx, rax; ProcessHandle
0x180006822  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180006826  lea     edx, [r13+8]; DesiredAccess
0x18000682a  call    cs:__imp_OpenProcessToken
0x180006830  test    eax, eax
0x180006832  jz      loc_18000692F
0x180006838  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000683c  lea     rax, [rbp+TokenInformationLength]
0x180006840  lea     r14d, [r13+1]
0x180006844  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180006849  mov     edx, r14d; TokenInformationClass
0x18000684c  xor     r9d, r9d; TokenInformationLength
0x18000684f  xor     r8d, r8d; TokenInformation
0x180006852  call    cs:__imp_GetTokenInformation
0x180006858  mov     eax, [rbp+TokenInformationLength]
0x18000685b  test    eax, eax
0x18000685d  jz      loc_18000692F
0x180006863  mov     ecx, eax; unsigned __int64
0x180006865  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000686c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006871  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180006875  mov     rsi, rax
0x180006878  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000687c  lea     rax, [rbp+TokenInformationLength]
0x180006880  mov     r8, rsi; TokenInformation
0x180006883  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180006888  mov     edx, r14d; TokenInformationClass
0x18000688b  call    cs:__imp_GetTokenInformation
0x180006891  test    eax, eax
0x180006893  jz      loc_18000692F
0x180006899  mov     rcx, [rsi]; Sid
0x18000689c  lea     rdx, [rbp+StringSid]; StringSid
0x1800068a0  call    cs:__imp_ConvertSidToStringSidW
0x1800068a6  test    eax, eax
0x1800068a8  jz      loc_18000692F
0x1800068ae  mov     rcx, [rbp+StringSid]
0x1800068b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800068b6  mov     rax, r8
0x1800068b9  inc     rax
0x1800068bc  cmp     [rcx+rax*2], r13w
0x1800068c1  jnz     short loc_1800068B9
0x1800068c3  lea     r14, [rax+2Bh]
0x1800068c7  mov     eax, 2
0x1800068cc  mul     r14
0x1800068cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800068d6  cmovb   rax, r8
0x1800068da  mov     rcx, rax; unsigned __int64
0x1800068dd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800068e2  mov     rdi, rax
0x1800068e5  test    rax, rax
0x1800068e8  jz      short loc_18000692F
0x1800068ea  mov     rcx, [rbp+StringSid]
0x1800068ee  lea     r8, aDPACioi0x08xAu; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x1800068f5  mov     [rsp+40h+var_18], rcx
0x1800068fa  mov     r9d, r12d
0x1800068fd  mov     rcx, rax; unsigned __int16 *
0x180006900  mov     dword ptr [rsp+40h+ReturnLength], r15d
0x180006905  mov     rdx, r14; unsigned __int64
0x180006908  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000690d  xor     r9d, r9d; SecurityDescriptorSize
0x180006910  lea     r8, [rbx+8]; SecurityDescriptor
0x180006914  mov     rcx, rdi; StringSecurityDescriptor
0x180006917  lea     edx, [r9+1]; StringSDRevision
0x18000691b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006921  test    eax, eax
0x180006923  jz      short loc_18000692F
0x180006925  mov     dword ptr [rbx], 18h
0x18000692b  mov     [rbx+10h], r13d
0x18000692f  mov     rcx, rdi; void *
0x180006932  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006937  mov     rcx, rsi; void *
0x18000693a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000693f  mov     rcx, [rbp+StringSid]; hMem
0x180006943  call    cs:__imp_LocalFree
0x180006949  mov     rcx, [rbp+TokenHandle]; hObject
0x18000694d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006951  jz      short loc_180006959
0x180006953  call    cs:__imp_CloseHandle
0x180006959  mov     rax, rbx
0x18000695c  mov     rbx, [rsp+40h+arg_8]
0x180006964  add     rsp, 40h
0x180006968  pop     r15
0x18000696a  pop     r14
0x18000696c  pop     r13
0x18000696e  pop     r12
0x180006970  pop     rdi
0x180006971  pop     rsi
0x180006972  pop     rbp
0x180006973  retn
```
