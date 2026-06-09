# W3_MGD_USER_CONTEXT::DuplicateImpToken(void *,void * &)

- ea: `0x180063b4c`
- end: `0x180063ce7`
- name: `?DuplicateImpToken@W3_MGD_USER_CONTEXT@@CAJPEAXAEAPEAX@Z`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063d30`

## callees

- `0x18004d030`
- `0x180054690`
- `0x180054760`
- `0x180063b4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180063bc0`
- `KERNEL32!GetLastError` at `0x180063c9d`
- `KERNEL32!GetLastError` at `0x180063bc0`
- `KERNEL32!GetLastError` at `0x180063c9d`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c4b`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c6f`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c93`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c4b`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c6f`
- `ADVAPI32!DuplicateTokenEx` at `0x180063c93`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180063bb6`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180063c0f`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180063bb6`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180063c0f`

## pseudocode

```c
__int64 __fastcall W3_MGD_USER_CONTEXT::DuplicateImpToken(HANDLE hExistingToken, PHANDLE phNewToken)
{
  unsigned int v4; // ebx
  _BYTE *v5; // r14
  DWORD v6; // r9d
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-19h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-11h] BYREF
  _BYTE pSecurityDescriptor[32]; // [rsp+50h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR v12; // [rsp+70h] [rbp+27h]
  DWORD v13; // [rsp+78h] [rbp+2Fh]
  unsigned int v14; // [rsp+7Ch] [rbp+33h]

  v4 = 0;
  v12 = pSecurityDescriptor;
  v13 = 32;
  v14 = v14 & 0xFFFFFFFC | 2;
  pSecurityDescriptor[0] = 0;
  nLengthNeeded = 32;
  *phNewToken = 0;
  v5 = pSecurityDescriptor;
  if ( !GetKernelObjectSecurity(hExistingToken, 4u, pSecurityDescriptor, 0x20u, &nLengthNeeded) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_11;
    v6 = nLengthNeeded;
    if ( nLengthNeeded > v13 )
    {
      if ( !BUFFER::ReallocStorage((BUFFER *)pSecurityDescriptor, nLengthNeeded) )
      {
        v4 = -2147024882;
        goto LABEL_13;
      }
      v6 = nLengthNeeded;
    }
    v5 = v12;
    if ( !GetKernelObjectSecurity(hExistingToken, 4u, v12, v6, &nLengthNeeded) )
      goto LABEL_11;
  }
  TokenAttributes.nLength = 24;
  TokenAttributes.lpSecurityDescriptor = v5;
  TokenAttributes.bInheritHandle = 1;
  if ( !DuplicateTokenEx(hExistingToken, 0, &TokenAttributes, SecurityDelegation, TokenImpersonation, phNewToken)
    && !DuplicateTokenEx(hExistingToken, 0, &TokenAttributes, SecurityImpersonation, TokenImpersonation, phNewToken)
    && !DuplicateTokenEx(hExistingToken, 0, &TokenAttributes, SecurityIdentification, TokenImpersonation, phNewToken) )
  {
LABEL_11:
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
  }
LABEL_13:
  if ( (v14 & 1) != 0 )
    BUFFER::FreeMemory((BUFFER *)pSecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x180063b4c  mov     [rsp-8+arg_10], rbx
0x180063b51  mov     [rsp-8+arg_18], rsi
0x180063b56  push    rbp
0x180063b57  push    rdi
0x180063b58  push    r14
0x180063b5a  lea     rbp, [rsp-47h]
0x180063b5f  sub     rsp, 90h
0x180063b66  mov     rax, cs:__security_cookie
0x180063b6d  xor     rax, rsp
0x180063b70  mov     [rbp+57h+var_20], rax
0x180063b74  mov     rsi, rdx
0x180063b77  mov     rdi, rcx
0x180063b7a  xor     ebx, ebx
0x180063b7c  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180063b80  mov     [rbp+57h+var_30], rax
0x180063b84  lea     r9d, [rbx+20h]; nLength
0x180063b88  mov     [rbp+57h+var_28], r9d
0x180063b8c  mov     eax, [rbp+57h+var_24]
0x180063b8f  and     eax, 0FFFFFFFEh
0x180063b92  or      eax, 2
0x180063b95  mov     [rbp+57h+var_24], eax
0x180063b98  mov     [rbp+57h+pSecurityDescriptor], bl
0x180063b9b  mov     [rbp+57h+nLengthNeeded], r9d
0x180063b9f  mov     [rdx], rbx
0x180063ba2  lea     r14, [rbp+57h+pSecurityDescriptor]
0x180063ba6  lea     rax, [rbp+57h+nLengthNeeded]
0x180063baa  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180063baf  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180063bb3  lea     edx, [rbx+4]; RequestedInformation
0x180063bb6  call    cs:__imp_GetKernelObjectSecurity
0x180063bbc  test    eax, eax
0x180063bbe  jnz     short loc_180063C1D
0x180063bc0  call    cs:__imp_GetLastError
0x180063bc6  cmp     eax, 7Ah ; 'z'
0x180063bc9  jnz     loc_180063C9D
0x180063bcf  mov     r9d, [rbp+57h+nLengthNeeded]
0x180063bd3  cmp     r9d, [rbp+57h+var_28]
0x180063bd7  jbe     short loc_180063BF7
0x180063bd9  mov     edx, r9d; unsigned int
0x180063bdc  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x180063be0  call    ?ReallocStorage@BUFFER@@AEAAHI@Z; BUFFER::ReallocStorage(uint)
0x180063be5  test    eax, eax
0x180063be7  jnz     short loc_180063BF3
0x180063be9  mov     ebx, 8007000Eh
0x180063bee  jmp     loc_180063CB1
0x180063bf3  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180063bf7  mov     r14, [rbp+57h+var_30]
0x180063bfb  lea     rax, [rbp+57h+nLengthNeeded]
0x180063bff  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180063c04  mov     r8, r14; pSecurityDescriptor
0x180063c07  mov     edx, 4; RequestedInformation
0x180063c0c  mov     rcx, rdi; Handle
0x180063c0f  call    cs:__imp_GetKernelObjectSecurity
0x180063c15  test    eax, eax
0x180063c17  jz      loc_180063C9D
0x180063c1d  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x180063c24  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r14
0x180063c28  mov     [rbp+57h+TokenAttributes.bInheritHandle], 1
0x180063c2f  mov     [rsp+0A0h+phNewToken], rsi; phNewToken
0x180063c34  mov     dword ptr [rsp+0A0h+lpnLengthNeeded], 2; TokenType
0x180063c3c  mov     r9d, 3; ImpersonationLevel
0x180063c42  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180063c46  xor     edx, edx; dwDesiredAccess
0x180063c48  mov     rcx, rdi; hExistingToken
0x180063c4b  call    cs:__imp_DuplicateTokenEx
0x180063c51  test    eax, eax
0x180063c53  jnz     short loc_180063CB1
0x180063c55  mov     [rsp+0A0h+phNewToken], rsi; phNewToken
0x180063c5a  mov     dword ptr [rsp+0A0h+lpnLengthNeeded], 2; TokenType
0x180063c62  lea     r9d, [rax+2]; ImpersonationLevel
0x180063c66  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180063c6a  xor     edx, edx; dwDesiredAccess
0x180063c6c  mov     rcx, rdi; hExistingToken
0x180063c6f  call    cs:__imp_DuplicateTokenEx
0x180063c75  test    eax, eax
0x180063c77  jnz     short loc_180063CB1
0x180063c79  mov     [rsp+0A0h+phNewToken], rsi; phNewToken
0x180063c7e  mov     dword ptr [rsp+0A0h+lpnLengthNeeded], 2; TokenType
0x180063c86  lea     r9d, [rax+1]; ImpersonationLevel
0x180063c8a  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180063c8e  xor     edx, edx; dwDesiredAccess
0x180063c90  mov     rcx, rdi; hExistingToken
0x180063c93  call    cs:__imp_DuplicateTokenEx
0x180063c99  test    eax, eax
0x180063c9b  jnz     short loc_180063CB1
0x180063c9d  call    cs:__imp_GetLastError
0x180063ca3  movzx   ebx, ax
0x180063ca6  or      ebx, 80070000h
0x180063cac  test    eax, eax
0x180063cae  cmovle  ebx, eax
0x180063cb1  test    byte ptr [rbp+57h+var_24], 1
0x180063cb5  jz      short loc_180063CC1
0x180063cb7  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x180063cbb  call    ?FreeMemory@BUFFER@@QEAAXXZ; BUFFER::FreeMemory(void)
0x180063cc0  nop
0x180063cc1  mov     eax, ebx
0x180063cc3  mov     rcx, [rbp+57h+var_20]
0x180063cc7  xor     rcx, rsp; StackCookie
0x180063cca  call    __security_check_cookie
0x180063ccf  lea     r11, [rsp+0A0h+var_10]
0x180063cd7  mov     rbx, [r11+30h]
0x180063cdb  mov     rsi, [r11+38h]
0x180063cdf  mov     rsp, r11
0x180063ce2  pop     r14
0x180063ce4  pop     rdi
0x180063ce5  pop     rbp
0x180063ce6  retn
```
