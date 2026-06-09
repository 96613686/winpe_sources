# ScCheckServiceSids(void)

- ea: `0x18000a9f8`
- end: `0x18000ac1a`
- name: `?ScCheckServiceSids@@YAKXZ`
- size: `546`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a780`
- `0x18000bfb0`
- `0x18003aa70`

## callees

- `0x18000a9f8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000ab2d`
- `ntdll!RtlInitUnicodeString` at `0x18000ab2d`
- `ntdll!RtlNtStatusToDosError` at `0x18000abc6`
- `ntdll!RtlNtStatusToDosError` at `0x18000abc6`
- `ntdll!RtlCreateServiceSid` at `0x18000ab3d`
- `ntdll!RtlCreateServiceSid` at `0x18000ab86`
- `ntdll!RtlCreateServiceSid` at `0x18000ab3d`
- `ntdll!RtlCreateServiceSid` at `0x18000ab86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000aa2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000aa2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aa3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aa3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ab65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ab65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac03`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000aae6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000aae6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aaba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aaba`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000aad4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000aad4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000aba3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000aba3`

## pseudocode

```c
__int64 ScCheckServiceSids(void)
{
  unsigned int v0; // ebx
  unsigned int *v1; // rdi
  HLOCAL v2; // r14
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  unsigned int v5; // ebx
  bool v6; // zf
  ULONG v7; // r15d
  int v8; // r12d
  PCWSTR *i; // rbx
  int v10; // eax
  unsigned int j; // esi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG ServiceSidLength; // [rsp+80h] [rbp+40h] BYREF
  DWORD TokenInformationLength; // [rsp+88h] [rbp+48h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp+50h] BYREF

  v0 = 0;
  v1 = 0;
  v2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  ServiceSidLength = 0;
  DestinationString = 0;
  if ( ::TokenHandle )
    goto LABEL_35;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x48u, &TokenHandle) )
  {
LABEL_3:
    LastError = GetLastError();
LABEL_4:
    v0 = LastError;
    goto LABEL_33;
  }
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v1 = (unsigned int *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v1 && GetTokenInformation(TokenHandle, TokenGroups, v1, TokenInformationLength, &TokenInformationLength) )
    {
      v5 = 0;
      v6 = *v1 == 0;
      if ( *v1 )
      {
        do
        {
          if ( *GetSidSubAuthorityCount(*(PSID *)&v1[4 * v5 + 2])
            && *GetSidSubAuthority(*(PSID *)&v1[4 * v5 + 2], 0) == 80 )
          {
            break;
          }
          ++v5;
        }
        while ( v5 < *v1 );
        v6 = v5 == *v1;
      }
      if ( v6 )
      {
        v0 = 0;
      }
      else
      {
        v7 = 0;
        v8 = 0;
        for ( i = (PCWSTR *)((char *)hMem + 8); i[1]; i += 12 )
        {
          ServiceSidLength = 0;
          RtlInitUnicodeString(&DestinationString, i[2]);
          if ( RtlCreateServiceSid(&DestinationString, 0, &ServiceSidLength) != -1073741789 )
            goto LABEL_7;
          if ( v7 < ServiceSidLength )
          {
            LocalFree(v2);
            v2 = LocalAlloc(0x40u, ServiceSidLength);
            if ( !v2 )
              goto LABEL_3;
            v7 = ServiceSidLength;
          }
          v10 = RtlCreateServiceSid(&DestinationString, v2, &ServiceSidLength);
          if ( v10 < 0 )
          {
            LastError = RtlNtStatusToDosError(v10);
            goto LABEL_4;
          }
          for ( j = 0; j < *v1; ++j )
          {
            if ( EqualSid(*(PSID *)&v1[4 * j + 2], v2) )
            {
              *((_DWORD *)i + 14) |= 8u;
              v8 = 1;
              break;
            }
          }
        }
        v0 = 0;
        if ( v8 == 1 )
        {
          ::TokenHandle = TokenHandle;
          TokenHandle = 0;
        }
      }
      goto LABEL_33;
    }
    goto LABEL_3;
  }
LABEL_7:
  v0 = 13;
LABEL_33:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_35:
  LocalFree(v2);
  LocalFree(v1);
  return v0;
}

```

## disassembly

```asm
0x18000a9f8  push    rbp
0x18000a9fa  push    rbx
0x18000a9fb  push    rsi
0x18000a9fc  push    rdi
0x18000a9fd  push    r12
0x18000a9ff  push    r14
0x18000aa01  push    r15
0x18000aa03  mov     rbp, rsp
0x18000aa06  sub     rsp, 40h
0x18000aa0a  xor     ebx, ebx
0x18000aa0c  xor     edi, edi
0x18000aa0e  xor     r14d, r14d
0x18000aa11  mov     [rbp+TokenHandle], rbx
0x18000aa15  cmp     cs:TokenHandle, rbx
0x18000aa1c  xorps   xmm0, xmm0
0x18000aa1f  mov     [rbp+TokenInformationLength], ebx
0x18000aa22  mov     [rbp+ServiceSidLength], ebx
0x18000aa25  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000aa29  jnz     loc_18000ABF7
0x18000aa2f  call    cs:__imp_GetCurrentProcess
0x18000aa35  mov     rcx, rax; ProcessHandle
0x18000aa38  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000aa3c  lea     edx, [rbx+48h]; DesiredAccess
0x18000aa3f  call    cs:__imp_OpenProcessToken
0x18000aa45  test    eax, eax
0x18000aa47  jnz     short loc_18000AA56
0x18000aa49  call    cs:__imp_GetLastError
0x18000aa4f  mov     ebx, eax
0x18000aa51  jmp     loc_18000ABE8
0x18000aa56  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000aa5a  lea     rax, [rbp+TokenInformationLength]
0x18000aa5e  xor     r9d, r9d; TokenInformationLength
0x18000aa61  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18000aa66  xor     r8d, r8d; TokenInformation
0x18000aa69  lea     ebx, [r9+2]
0x18000aa6d  mov     edx, ebx; TokenInformationClass
0x18000aa6f  call    cs:__imp_GetTokenInformation
0x18000aa75  test    eax, eax
0x18000aa77  jnz     short loc_18000AA8E
0x18000aa79  call    cs:__imp_GetLastError
0x18000aa7f  cmp     eax, 7Ah ; 'z'
0x18000aa82  jz      short loc_18000AA8E
0x18000aa84  mov     ebx, 0Dh
0x18000aa89  jmp     loc_18000ABE8
0x18000aa8e  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18000aa91  mov     ecx, 40h ; '@'; uFlags
0x18000aa96  call    cs:__imp_LocalAlloc
0x18000aa9c  mov     rdi, rax
0x18000aa9f  test    rax, rax
0x18000aaa2  jz      short loc_18000AA49
0x18000aaa4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000aaa8  lea     rax, [rbp+TokenInformationLength]
0x18000aaac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000aab0  mov     r8, rdi; TokenInformation
0x18000aab3  mov     edx, ebx; TokenInformationClass
0x18000aab5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18000aaba  call    cs:__imp_GetTokenInformation
0x18000aac0  test    eax, eax
0x18000aac2  jz      short loc_18000AA49
0x18000aac4  xor     ebx, ebx
0x18000aac6  cmp     ebx, [rdi]
0x18000aac8  jnb     short loc_18000AAF9
0x18000aaca  mov     esi, ebx
0x18000aacc  add     rsi, rsi
0x18000aacf  mov     rcx, [rdi+rsi*8+8]; pSid
0x18000aad4  call    cs:__imp_GetSidSubAuthorityCount
0x18000aada  cmp     [rax], r14b
0x18000aadd  jbe     short loc_18000AAF1
0x18000aadf  mov     rcx, [rdi+rsi*8+8]; pSid
0x18000aae4  xor     edx, edx; nSubAuthority
0x18000aae6  call    cs:__imp_GetSidSubAuthority
0x18000aaec  cmp     dword ptr [rax], 50h ; 'P'
0x18000aaef  jz      short loc_18000AAF7
0x18000aaf1  inc     ebx
0x18000aaf3  cmp     ebx, [rdi]
0x18000aaf5  jb      short loc_18000AACA
0x18000aaf7  cmp     ebx, [rdi]
0x18000aaf9  jnz     short loc_18000AB02
0x18000aafb  xor     ebx, ebx
0x18000aafd  jmp     loc_18000ABE8
0x18000ab02  mov     rbx, cs:hMem
0x18000ab09  xor     r15d, r15d
0x18000ab0c  xor     r12d, r12d
0x18000ab0f  add     rbx, 8
0x18000ab13  cmp     qword ptr [rbx+8], 0
0x18000ab18  jz      loc_18000ABD1
0x18000ab1e  mov     [rbp+ServiceSidLength], 0
0x18000ab25  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000ab29  mov     rdx, [rbx+10h]; SourceString
0x18000ab2d  call    cs:__imp_RtlInitUnicodeString
0x18000ab33  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x18000ab37  xor     edx, edx; ServiceSid
0x18000ab39  lea     rcx, [rbp+DestinationString]; ServiceName
0x18000ab3d  call    cs:__imp_RtlCreateServiceSid
0x18000ab43  cmp     eax, 0C0000023h
0x18000ab48  jnz     loc_18000AA84
0x18000ab4e  cmp     r15d, [rbp+ServiceSidLength]
0x18000ab52  jnb     short loc_18000AB7B
0x18000ab54  mov     rcx, r14; hMem
0x18000ab57  call    cs:__imp_LocalFree
0x18000ab5d  mov     edx, [rbp+ServiceSidLength]; uBytes
0x18000ab60  mov     ecx, 40h ; '@'; uFlags
0x18000ab65  call    cs:__imp_LocalAlloc
0x18000ab6b  mov     r14, rax
0x18000ab6e  test    rax, rax
0x18000ab71  jz      loc_18000AA49
0x18000ab77  mov     r15d, [rbp+ServiceSidLength]
0x18000ab7b  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x18000ab7f  mov     rdx, r14; ServiceSid
0x18000ab82  lea     rcx, [rbp+DestinationString]; ServiceName
0x18000ab86  call    cs:__imp_RtlCreateServiceSid
0x18000ab8c  test    eax, eax
0x18000ab8e  js      short loc_18000ABC4
0x18000ab90  xor     esi, esi
0x18000ab92  cmp     esi, [rdi]
0x18000ab94  jnb     short loc_18000ABBB
0x18000ab96  mov     ecx, esi
0x18000ab98  mov     rdx, r14; pSid2
0x18000ab9b  add     rcx, rcx
0x18000ab9e  mov     rcx, [rdi+rcx*8+8]; pSid1
0x18000aba3  call    cs:__imp_EqualSid
0x18000aba9  test    eax, eax
0x18000abab  jnz     short loc_18000ABB1
0x18000abad  inc     esi
0x18000abaf  jmp     short loc_18000AB92
0x18000abb1  or      dword ptr [rbx+38h], 8
0x18000abb5  mov     r12d, 1
0x18000abbb  add     rbx, 60h ; '`'
0x18000abbf  jmp     loc_18000AB13
0x18000abc4  mov     ecx, eax; Status
0x18000abc6  call    cs:__imp_RtlNtStatusToDosError
0x18000abcc  jmp     loc_18000AA4F
0x18000abd1  xor     ebx, ebx
0x18000abd3  cmp     r12d, 1
0x18000abd7  jnz     short loc_18000ABE8
0x18000abd9  mov     rax, [rbp+TokenHandle]
0x18000abdd  mov     cs:TokenHandle, rax
0x18000abe4  mov     [rbp+TokenHandle], rbx
0x18000abe8  mov     rcx, [rbp+TokenHandle]; hObject
0x18000abec  test    rcx, rcx
0x18000abef  jz      short loc_18000ABF7
0x18000abf1  call    cs:__imp_CloseHandle
0x18000abf7  mov     rcx, r14; hMem
0x18000abfa  call    cs:__imp_LocalFree
0x18000ac00  mov     rcx, rdi; hMem
0x18000ac03  call    cs:__imp_LocalFree
0x18000ac09  mov     eax, ebx
0x18000ac0b  add     rsp, 40h
0x18000ac0f  pop     r15
0x18000ac11  pop     r14
0x18000ac13  pop     r12
0x18000ac15  pop     rdi
0x18000ac16  pop     rsi
0x18000ac17  pop     rbx
0x18000ac18  pop     rbp
0x18000ac19  retn
```
