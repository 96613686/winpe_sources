# GetServiceWaitTimeout

- ea: `0x180023e3c`
- end: `0x180023f79`
- name: `GetServiceWaitTimeout`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005920`

## callees

- `0x180005d00`
- `0x180023e3c`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023e70`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023e81`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f53`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023f48`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023f48`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023eee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023eee`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023f3b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023f3b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023f28`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023f28`

## pseudocode

```c
__int64 GetServiceWaitTimeout()
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  unsigned __int16 *v3; // rcx
  unsigned int v4; // r8d
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-D8h]
  DWORD v7; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid1; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[64]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v7 = 512;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    pSid1 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &v7) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
      {
        v0 = EqualSid(pSid1, TokenInformation[0]);
        FreeSid(pSid1);
LABEL_6:
        CloseHandle(TokenHandle);
        return v0 ? 900 : 120;
      }
      v4 = 126;
    }
    else
    {
      v4 = 116;
    }
    ErrLog_LogError(v3, 4u, v4, 0, ReturnLength, nSubAuthority3);
    goto LABEL_6;
  }
  return v0 ? 900 : 120;
}

```

## disassembly

```asm
0x180023e3c  mov     [rsp-8+arg_0], rbx
0x180023e41  mov     [rsp-8+arg_8], rdi
0x180023e46  push    rbp
0x180023e47  lea     rbp, [rsp-190h]
0x180023e4f  sub     rsp, 290h
0x180023e56  mov     rax, cs:__security_cookie
0x180023e5d  xor     rax, rsp
0x180023e60  mov     [rbp+190h+var_10], rax
0x180023e67  xor     edi, edi
0x180023e69  mov     [rsp+290h+TokenHandle], rdi
0x180023e6e  mov     ebx, edi
0x180023e70  call    cs:__imp_GetCurrentProcess
0x180023e76  mov     rcx, rax; ProcessHandle
0x180023e79  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180023e7e  lea     edx, [rdi+8]; DesiredAccess
0x180023e81  call    cs:__imp_OpenProcessToken
0x180023e87  test    eax, eax
0x180023e89  jnz     short loc_180023EBB
0x180023e8b  neg     ebx
0x180023e8d  sbb     eax, eax
0x180023e8f  and     eax, 30Ch
0x180023e94  add     eax, 78h ; 'x'
0x180023e97  mov     rcx, [rbp+190h+var_10]
0x180023e9e  xor     rcx, rsp; StackCookie
0x180023ea1  call    __security_check_cookie
0x180023ea6  lea     r11, [rsp+290h+var_s0]
0x180023eae  mov     rbx, [r11+10h]
0x180023eb2  mov     rdi, [r11+18h]
0x180023eb6  mov     rsp, r11
0x180023eb9  pop     rbp
0x180023eba  retn
0x180023ebb  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180023ec0  lea     rax, [rsp+290h+var_230]
0x180023ec5  mov     r9d, 200h; TokenInformationLength
0x180023ecb  mov     [rsp+290h+ReturnLength], rax; int
0x180023ed0  lea     r8, [rbp+190h+TokenInformation]; TokenInformation
0x180023ed4  mov     [rsp+290h+var_230], r9d
0x180023ed9  mov     edx, 1; TokenInformationClass
0x180023ede  mov     dword ptr [rsp+290h+pIdentifierAuthority.Value], edi
0x180023ee2  mov     word ptr [rsp+290h+pIdentifierAuthority.Value+4], 500h
0x180023ee9  mov     [rsp+290h+pSid1], rdi
0x180023eee  call    cs:__imp_GetTokenInformation
0x180023ef4  xor     r9d, r9d; unsigned int
0x180023ef7  test    eax, eax
0x180023ef9  jz      short loc_180023F5E
0x180023efb  lea     rax, [rsp+290h+pSid1]
0x180023f00  mov     dl, 1; nSubAuthorityCount
0x180023f02  mov     [rsp+290h+pSid], rax; pSid
0x180023f07  lea     r8d, [r9+12h]; nSubAuthority0
0x180023f0b  mov     [rsp+290h+nSubAuthority7], edi; nSubAuthority7
0x180023f0f  lea     rcx, [rsp+290h+pIdentifierAuthority]; pIdentifierAuthority
0x180023f14  mov     [rsp+290h+nSubAuthority6], edi; nSubAuthority6
0x180023f18  mov     [rsp+290h+nSubAuthority5], edi; nSubAuthority5
0x180023f1c  mov     [rsp+290h+nSubAuthority4], edi; nSubAuthority4
0x180023f20  mov     [rsp+290h+nSubAuthority3], edi; nSubAuthority3
0x180023f24  mov     dword ptr [rsp+290h+ReturnLength], edi; nSubAuthority2
0x180023f28  call    cs:__imp_AllocateAndInitializeSid
0x180023f2e  test    eax, eax
0x180023f30  jz      short loc_180023F70
0x180023f32  mov     rdx, [rbp+190h+TokenInformation]; pSid2
0x180023f36  mov     rcx, [rsp+290h+pSid1]; pSid1
0x180023f3b  call    cs:__imp_EqualSid
0x180023f41  mov     rcx, [rsp+290h+pSid1]; pSid
0x180023f46  mov     ebx, eax
0x180023f48  call    cs:__imp_FreeSid
0x180023f4e  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x180023f53  call    cs:__imp_CloseHandle
0x180023f59  jmp     loc_180023E8B
0x180023f5e  mov     r8d, 74h ; 't'; unsigned int
0x180023f64  mov     edx, 4; unsigned int
0x180023f69  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180023f6e  jmp     short loc_180023F4E
0x180023f70  xor     r9d, r9d
0x180023f73  lea     r8d, [r9+7Eh]
0x180023f77  jmp     short loc_180023F64
```
