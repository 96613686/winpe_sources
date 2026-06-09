# CSrchAdminSSO::_GetSIDString(ushort * *)

- ea: `0x18002ea48`
- end: `0x18002ebc0`
- name: `?_GetSIDString@CSrchAdminSSO@@AEAAJPEAPEAG@Z`
- size: `376`
- prototype: `int(CSrchAdminSSO *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e480`
- `0x18002e590`

## callees

- `0x18000d4dc`
- `0x180010680`
- `0x18002dc08`
- `0x18002ea48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ea66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ea66`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ea78`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ea78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002eb23`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002eb23`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002eb3b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002eb3b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002eb68`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002eb68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eaaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eb0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eaaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eb0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eba2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eba2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002eb84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002eb84`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::_GetSIDString(CSrchAdminSSO *this, unsigned __int16 **a2)
{
  HANDLE CurrentProcess; // rax
  int Error; // ebx
  unsigned int v5; // edx
  void *v6; // rcx
  int v7; // eax
  PSID *v8; // rdi
  DWORD LengthSid; // eax
  DWORD v10; // r14d
  unsigned int v11; // edx
  void *v12; // rcx
  CSrchAdminSSO *TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = this;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    LODWORD(TokenInformationLength) = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
      || (v7 = ResultFromLastError(), Error = v7, v7 == -2147024774)
      || v7 >= 0 )
    {
      TokenInformation = 0;
      Error = CTLocalAllocPolicy::Alloc(v6, v5, (unsigned int)TokenInformationLength, &TokenInformation);
      if ( Error >= 0 )
      {
        v8 = (PSID *)TokenInformation;
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               TokenInformation,
               (DWORD)TokenInformationLength,
               (PDWORD)&TokenInformationLength)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( IsValidSid(*v8) || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            LengthSid = GetLengthSid(*v8);
            TokenInformation = 0;
            v10 = LengthSid;
            Error = CTLocalAllocPolicy::Alloc(v12, v11, LengthSid, &TokenInformation);
            if ( Error >= 0 )
            {
              if ( CopySid(v10, TokenInformation, *v8) || (Error = ResultFromKnownLastError(), Error >= 0) )
              {
                if ( !ConvertSidToStringSidW(TokenInformation, a2) )
                  Error = ResultFromKnownLastError();
              }
              LocalFree(TokenInformation);
            }
          }
        }
        LocalFree(v8);
      }
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002ea48  mov     [rsp-28h+TokenInformationLength], rcx
0x18002ea4d  push    rbp
0x18002ea4e  push    rbx
0x18002ea4f  push    rdi
0x18002ea50  push    r14
0x18002ea52  push    r15
0x18002ea54  mov     rbp, rsp
0x18002ea57  sub     rsp, 30h
0x18002ea5b  mov     r15, rdx
0x18002ea5e  mov     [rbp+TokenHandle], 0
0x18002ea66  call    cs:__imp_GetCurrentProcess
0x18002ea6c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002ea70  mov     edx, 8; DesiredAccess
0x18002ea75  mov     rcx, rax; ProcessHandle
0x18002ea78  call    cs:__imp_OpenProcessToken
0x18002ea7e  test    eax, eax
0x18002ea80  jnz     short loc_18002EA91
0x18002ea82  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ea87  mov     ebx, eax
0x18002ea89  test    eax, eax
0x18002ea8b  js      loc_18002EBB2
0x18002ea91  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002ea95  lea     rax, [rbp+TokenInformationLength]
0x18002ea99  xor     r9d, r9d; TokenInformationLength
0x18002ea9c  mov     dword ptr [rbp+TokenInformationLength], 0
0x18002eaa3  xor     r8d, r8d; TokenInformation
0x18002eaa6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002eaab  lea     edx, [r9+1]; TokenInformationClass
0x18002eaaf  call    cs:__imp_GetTokenInformation
0x18002eab5  test    eax, eax
0x18002eab7  jnz     short loc_18002EACF
0x18002eab9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002eabe  mov     ebx, eax
0x18002eac0  cmp     eax, 8007007Ah
0x18002eac5  jz      short loc_18002EACF
0x18002eac7  test    eax, eax
0x18002eac9  js      loc_18002EBA8
0x18002eacf  mov     r8d, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x18002ead3  lea     r9, [rbp+TokenInformation]; void **
0x18002ead7  mov     [rbp+TokenInformation], 0
0x18002eadf  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002eae4  mov     ebx, eax
0x18002eae6  test    eax, eax
0x18002eae8  js      loc_18002EBA8
0x18002eaee  mov     rdi, [rbp+TokenInformation]
0x18002eaf2  lea     rax, [rbp+TokenInformationLength]
0x18002eaf6  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x18002eafa  mov     r8, rdi; TokenInformation
0x18002eafd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002eb01  mov     edx, 1; TokenInformationClass
0x18002eb06  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002eb0b  call    cs:__imp_GetTokenInformation
0x18002eb11  test    eax, eax
0x18002eb13  jnz     short loc_18002EB20
0x18002eb15  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002eb1a  mov     ebx, eax
0x18002eb1c  test    eax, eax
0x18002eb1e  js      short loc_18002EB9F
0x18002eb20  mov     rcx, [rdi]; pSid
0x18002eb23  call    cs:__imp_IsValidSid
0x18002eb29  test    eax, eax
0x18002eb2b  jnz     short loc_18002EB38
0x18002eb2d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002eb32  mov     ebx, eax
0x18002eb34  test    eax, eax
0x18002eb36  js      short loc_18002EB9F
0x18002eb38  mov     rcx, [rdi]; pSid
0x18002eb3b  call    cs:__imp_GetLengthSid
0x18002eb41  lea     r9, [rbp+TokenInformation]; void **
0x18002eb45  mov     [rbp+TokenInformation], 0
0x18002eb4d  mov     r8d, eax; unsigned __int64
0x18002eb50  mov     r14d, eax
0x18002eb53  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002eb58  mov     ebx, eax
0x18002eb5a  test    eax, eax
0x18002eb5c  js      short loc_18002EB9F
0x18002eb5e  mov     r8, [rdi]; pSourceSid
0x18002eb61  mov     ecx, r14d; nDestinationSidLength
0x18002eb64  mov     rdx, [rbp+TokenInformation]; pDestinationSid
0x18002eb68  call    cs:__imp_CopySid
0x18002eb6e  test    eax, eax
0x18002eb70  jnz     short loc_18002EB7D
0x18002eb72  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002eb77  mov     ebx, eax
0x18002eb79  test    eax, eax
0x18002eb7b  js      short loc_18002EB95
0x18002eb7d  mov     rcx, [rbp+TokenInformation]; Sid
0x18002eb81  mov     rdx, r15; StringSid
0x18002eb84  call    cs:__imp_ConvertSidToStringSidW
0x18002eb8a  test    eax, eax
0x18002eb8c  jnz     short loc_18002EB95
0x18002eb8e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002eb93  mov     ebx, eax
0x18002eb95  mov     rcx, [rbp+TokenInformation]; hMem
0x18002eb99  call    cs:__imp_LocalFree
0x18002eb9f  mov     rcx, rdi; hMem
0x18002eba2  call    cs:__imp_LocalFree
0x18002eba8  mov     rcx, [rbp+TokenHandle]; hObject
0x18002ebac  call    cs:__imp_CloseHandle
0x18002ebb2  mov     eax, ebx
0x18002ebb4  add     rsp, 30h
0x18002ebb8  pop     r15
0x18002ebba  pop     r14
0x18002ebbc  pop     rdi
0x18002ebbd  pop     rbx
0x18002ebbe  pop     rbp
0x18002ebbf  retn
```
