# GetProcessIntegrityLevel(void)

- ea: `0x180085ef0`
- end: `0x180085fde`
- name: `?GetProcessIntegrityLevel@@YAKXZ`
- size: `238`
- prototype: `unsigned int(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070c30`
- `0x180073b48`
- `0x1800754a4`
- `0x180085fe4`

## callees

- `0x180085ef0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180085fcc`
- `KERNEL32!CloseHandle` at `0x180085fcc`
- `KERNEL32!GetLastError` at `0x180085f58`
- `KERNEL32!GetLastError` at `0x180085f58`
- `KERNEL32!GetCurrentProcess` at `0x180085f14`
- `KERNEL32!GetCurrentProcess` at `0x180085f14`
- `KERNEL32!LocalFree` at `0x180085fc1`
- `KERNEL32!LocalFree` at `0x180085fc1`
- `KERNEL32!LocalAlloc` at `0x180085f69`
- `KERNEL32!LocalAlloc` at `0x180085f69`
- `ADVAPI32!GetTokenInformation` at `0x180085f4e`
- `ADVAPI32!GetTokenInformation` at `0x180085f93`
- `ADVAPI32!GetTokenInformation` at `0x180085f4e`
- `ADVAPI32!GetTokenInformation` at `0x180085f93`
- `ADVAPI32!OpenProcessToken` at `0x180085f27`
- `ADVAPI32!OpenProcessToken` at `0x180085f27`
- `ADVAPI32!GetSidSubAuthority` at `0x180085fb0`
- `ADVAPI32!GetSidSubAuthority` at `0x180085fb0`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180085fa0`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180085fa0`

## pseudocode

```c
__int64 GetProcessIntegrityLevel(void)
{
  HANDLE CurrentProcess; // rax
  PSID *v1; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  if ( !dword_1800D6F54 )
  {
    TokenHandle = 0;
    TokenInformationLength = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
        && GetLastError() == 122 )
      {
        v1 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v1 )
        {
          if ( GetTokenInformation(
                 TokenHandle,
                 TokenIntegrityLevel,
                 v1,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            SidSubAuthorityCount = GetSidSubAuthorityCount(*v1);
            dword_1800D6F54 = *GetSidSubAuthority(*v1, (unsigned __int8)(*SidSubAuthorityCount - 1));
          }
          LocalFree(v1);
        }
      }
      CloseHandle(TokenHandle);
    }
  }
  return (unsigned int)dword_1800D6F54;
}

```

## disassembly

```asm
0x180085ef0  push    rbx
0x180085ef2  sub     rsp, 30h
0x180085ef6  cmp     cs:dword_1800D6F54, 0
0x180085efd  jnz     loc_180085FD2
0x180085f03  mov     [rsp+38h+TokenHandle], 0
0x180085f0c  mov     [rsp+38h+TokenInformationLength], 0
0x180085f14  call    cs:__imp_GetCurrentProcess
0x180085f1a  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180085f1f  mov     edx, 8; DesiredAccess
0x180085f24  mov     rcx, rax; ProcessHandle
0x180085f27  call    cs:__imp_OpenProcessToken
0x180085f2d  test    eax, eax
0x180085f2f  jz      loc_180085FD2
0x180085f35  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180085f3a  lea     rax, [rsp+38h+TokenInformationLength]
0x180085f3f  xor     r9d, r9d; TokenInformationLength
0x180085f42  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180085f47  xor     r8d, r8d; TokenInformation
0x180085f4a  lea     edx, [r9+19h]; TokenInformationClass
0x180085f4e  call    cs:__imp_GetTokenInformation
0x180085f54  test    eax, eax
0x180085f56  jnz     short loc_180085FC7
0x180085f58  call    cs:__imp_GetLastError
0x180085f5e  cmp     eax, 7Ah ; 'z'
0x180085f61  jnz     short loc_180085FC7
0x180085f63  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180085f67  xor     ecx, ecx; uFlags
0x180085f69  call    cs:__imp_LocalAlloc
0x180085f6f  mov     rbx, rax
0x180085f72  test    rax, rax
0x180085f75  jz      short loc_180085FC7
0x180085f77  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180085f7c  lea     rax, [rsp+38h+TokenInformationLength]
0x180085f81  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180085f86  mov     r8, rbx; TokenInformation
0x180085f89  mov     edx, 19h; TokenInformationClass
0x180085f8e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180085f93  call    cs:__imp_GetTokenInformation
0x180085f99  test    eax, eax
0x180085f9b  jz      short loc_180085FBE
0x180085f9d  mov     rcx, [rbx]; pSid
0x180085fa0  call    cs:__imp_GetSidSubAuthorityCount
0x180085fa6  mov     cl, [rax]
0x180085fa8  dec     cl
0x180085faa  movzx   edx, cl; nSubAuthority
0x180085fad  mov     rcx, [rbx]; pSid
0x180085fb0  call    cs:__imp_GetSidSubAuthority
0x180085fb6  mov     ecx, [rax]
0x180085fb8  mov     cs:dword_1800D6F54, ecx
0x180085fbe  mov     rcx, rbx; hMem
0x180085fc1  call    cs:__imp_LocalFree
0x180085fc7  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180085fcc  call    cs:__imp_CloseHandle
0x180085fd2  mov     eax, cs:dword_1800D6F54
0x180085fd8  add     rsp, 30h
0x180085fdc  pop     rbx
0x180085fdd  retn
```
