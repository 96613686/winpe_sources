# _anonymous_namespace_::IsWizardUser

- ea: `0x140015e24`
- end: `0x140015fb0`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140014310`

## callees

- `0x140002714`
- `0x14000347c`
- `0x140015b94`
- `0x140015e24`
- `0x140016dc8`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140015e83`
- `ADVAPI32!GetTokenInformation` at `0x140015ed0`
- `ADVAPI32!GetTokenInformation` at `0x140015e83`
- `ADVAPI32!GetTokenInformation` at `0x140015ed0`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140015ef3`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140015ef3`
- `ADVAPI32!OpenProcessToken` at `0x140015e51`
- `ADVAPI32!OpenProcessToken` at `0x140015e51`
- `KERNEL32!GetCurrentProcess` at `0x140015e39`
- `KERNEL32!GetCurrentProcess` at `0x140015e39`
- `KERNEL32!GetLastError` at `0x140015e97`
- `KERNEL32!GetLastError` at `0x140015e97`
- `KERNEL32!CloseHandle` at `0x140015f99`
- `KERNEL32!CloseHandle` at `0x140015f99`
- `KERNEL32!LocalFree` at `0x140015f81`
- `KERNEL32!LocalFree` at `0x140015f81`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  void **v2; // rdi
  void *v3; // rcx
  unsigned int v4; // r9d
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // r9d
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v3 = *v2;
        StringSid = 0;
        if ( ConvertSidToStringSidW(v3, &StringSid) )
        {
          v5 = StringSid;
          v9 = 0;
          SHRegGetBOOLWithREGSAM(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
            L"LaunchUserOOBE",
            v4,
            &v9);
          v0 = 1;
          if ( !v9 )
          {
            v9 = 0;
            SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
              L"LaunchCflScenario",
              v6,
              &v9);
            if ( !v9 && !IsCamCxhOnlyUser(v5) )
              v0 = 0;
          }
          LocalFree(StringSid);
        }
      }
      operator delete(v2);
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x140015e24  push    rbp
0x140015e26  push    rbx
0x140015e27  push    rdi
0x140015e28  mov     rbp, rsp
0x140015e2b  sub     rsp, 30h
0x140015e2f  xor     bl, bl
0x140015e31  mov     [rbp+TokenHandle], 0
0x140015e39  call    cs:__imp_GetCurrentProcess
0x140015e40  nop     dword ptr [rax+rax+00h]
0x140015e45  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140015e49  mov     edx, 8; DesiredAccess
0x140015e4e  mov     rcx, rax; ProcessHandle
0x140015e51  call    cs:__imp_OpenProcessToken
0x140015e58  nop     dword ptr [rax+rax+00h]
0x140015e5d  test    eax, eax
0x140015e5f  jz      loc_140015FA5
0x140015e65  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140015e69  lea     rax, [rbp+TokenInformationLength]
0x140015e6d  xor     r9d, r9d; TokenInformationLength
0x140015e70  mov     [rbp+TokenInformationLength], 0
0x140015e77  xor     r8d, r8d; TokenInformation
0x140015e7a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140015e7f  lea     edx, [r9+1]; TokenInformationClass
0x140015e83  call    cs:__imp_GetTokenInformation
0x140015e8a  nop     dword ptr [rax+rax+00h]
0x140015e8f  test    eax, eax
0x140015e91  jnz     loc_140015F95
0x140015e97  call    cs:__imp_GetLastError
0x140015e9e  nop     dword ptr [rax+rax+00h]
0x140015ea3  cmp     eax, 7Ah ; 'z'
0x140015ea6  jnz     loc_140015F95
0x140015eac  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x140015eaf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140015eb4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140015eb8  mov     rdi, rax
0x140015ebb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140015ebf  lea     rax, [rbp+TokenInformationLength]
0x140015ec3  mov     r8, rdi; TokenInformation
0x140015ec6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140015ecb  mov     edx, 1; TokenInformationClass
0x140015ed0  call    cs:__imp_GetTokenInformation
0x140015ed7  nop     dword ptr [rax+rax+00h]
0x140015edc  test    eax, eax
0x140015ede  jz      loc_140015F8D
0x140015ee4  mov     rcx, [rdi]; Sid
0x140015ee7  lea     rdx, [rbp+StringSid]; StringSid
0x140015eeb  mov     [rbp+StringSid], 0
0x140015ef3  call    cs:__imp_ConvertSidToStringSidW
0x140015efa  nop     dword ptr [rax+rax+00h]
0x140015eff  test    eax, eax
0x140015f01  jz      loc_140015F8D
0x140015f07  mov     rbx, [rbp+StringSid]
0x140015f0b  lea     rax, [rbp+arg_8]
0x140015f0f  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x140015f16  mov     [rsp+30h+ReturnLength], rax; int *
0x140015f1b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140015f22  mov     [rbp+arg_8], 0
0x140015f29  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140015f30  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x140015f35  cmp     [rbp+arg_8], 0
0x140015f39  jnz     short loc_140015F7B
0x140015f3b  lea     rax, [rbp+arg_8]
0x140015f3f  mov     [rbp+arg_8], 0
0x140015f46  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x140015f4d  mov     [rsp+30h+ReturnLength], rax; int *
0x140015f52  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140015f59  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140015f60  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x140015f65  cmp     [rbp+arg_8], 0
0x140015f69  jnz     short loc_140015F7B
0x140015f6b  mov     rcx, rbx; unsigned __int16 *
0x140015f6e  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x140015f73  test    al, al
0x140015f75  jnz     short loc_140015F7B
0x140015f77  xor     bl, bl
0x140015f79  jmp     short loc_140015F7D
0x140015f7b  mov     bl, 1
0x140015f7d  mov     rcx, [rbp+StringSid]; hMem
0x140015f81  call    cs:__imp_LocalFree
0x140015f88  nop     dword ptr [rax+rax+00h]
0x140015f8d  mov     rcx, rdi; Block
0x140015f90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015f95  mov     rcx, [rbp+TokenHandle]; hObject
0x140015f99  call    cs:__imp_CloseHandle
0x140015fa0  nop     dword ptr [rax+rax+00h]
0x140015fa5  mov     al, bl
0x140015fa7  add     rsp, 30h
0x140015fab  pop     rdi
0x140015fac  pop     rbx
0x140015fad  pop     rbp
0x140015fae  retn
```
