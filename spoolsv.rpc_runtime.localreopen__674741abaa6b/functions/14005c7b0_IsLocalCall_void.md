# IsLocalCall(void *)

- ea: `0x14005c7b0`
- end: `0x14005c8e6`
- name: `?IsLocalCall@@YA_NPEAX@Z`
- size: `310`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002ca60`

## callees

- `0x14002d0a0`
- `0x14005c7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005c81e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005c81e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005c805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005c805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005c8b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005c8b6`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x14005c7e1`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x14005c7e1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14005c86d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14005c86d`
- `ADVAPI32!CheckTokenMembership` at `0x14005c88c`
- `ADVAPI32!CheckTokenMembership` at `0x14005c88c`
- `ADVAPI32!FreeSid` at `0x14005c8a6`
- `ADVAPI32!FreeSid` at `0x14005c8a6`

## pseudocode

```c
bool __fastcall IsLocalCall(void *a1)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp+27h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp+2Bh] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+2Fh] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+37h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF

  v1 = 0;
  ClientLocalFlag = 0;
  if ( !I_RpcBindingIsClientLocal(a1, &ClientLocalFlag) )
  {
    if ( ClientLocalFlag )
    {
      v1 = 1;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        SidToCheck = 0;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
        {
          IsMember = 0;
          if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
            v1 = IsMember == 0;
          FreeSid(SidToCheck);
        }
        CloseHandle(TokenHandle);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14005c7b0  mov     [rsp-8+arg_8], rbx
0x14005c7b5  mov     [rsp-8+arg_10], rdi
0x14005c7ba  push    rbp
0x14005c7bb  lea     rbp, [rsp-57h]
0x14005c7c0  sub     rsp, 90h
0x14005c7c7  mov     rax, cs:__security_cookie
0x14005c7ce  xor     rax, rsp
0x14005c7d1  mov     [rbp+57h+var_10], rax
0x14005c7d5  xor     edi, edi
0x14005c7d7  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x14005c7db  mov     bl, dil
0x14005c7de  mov     [rbp+57h+ClientLocalFlag], edi
0x14005c7e1  call    cs:__imp_I_RpcBindingIsClientLocal
0x14005c7e8  nop     dword ptr [rax+rax+00h]
0x14005c7ed  test    eax, eax
0x14005c7ef  jnz     loc_14005C8C2
0x14005c7f5  cmp     [rbp+57h+ClientLocalFlag], edi
0x14005c7f8  jz      loc_14005C8C2
0x14005c7fe  lea     ebx, [rdi+1]
0x14005c801  mov     [rbp+57h+TokenHandle], rdi
0x14005c805  call    cs:__imp_GetCurrentThread
0x14005c80c  nop     dword ptr [rax+rax+00h]
0x14005c811  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14005c815  mov     r8d, ebx; OpenAsSelf
0x14005c818  mov     rcx, rax; ThreadHandle
0x14005c81b  lea     edx, [rdi+8]; DesiredAccess
0x14005c81e  call    cs:__imp_OpenThreadToken
0x14005c825  nop     dword ptr [rax+rax+00h]
0x14005c82a  test    eax, eax
0x14005c82c  jz      loc_14005C8C2
0x14005c832  lea     rax, [rbp+57h+SidToCheck]
0x14005c836  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14005c839  mov     [rsp+90h+pSid], rax; pSid
0x14005c83e  lea     r8d, [rdi+2]; nSubAuthority0
0x14005c842  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x14005c846  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14005c84a  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x14005c84e  xor     r9d, r9d; nSubAuthority1
0x14005c851  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x14005c855  mov     dl, bl; nSubAuthorityCount
0x14005c857  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x14005c85b  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x14005c85f  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x14005c863  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14005c869  mov     [rbp+57h+SidToCheck], rdi
0x14005c86d  call    cs:__imp_AllocateAndInitializeSid
0x14005c874  nop     dword ptr [rax+rax+00h]
0x14005c879  test    eax, eax
0x14005c87b  jz      short loc_14005C8B2
0x14005c87d  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14005c881  lea     r8, [rbp+57h+IsMember]; IsMember
0x14005c885  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14005c889  mov     [rbp+57h+IsMember], edi
0x14005c88c  call    cs:__imp_CheckTokenMembership
0x14005c893  nop     dword ptr [rax+rax+00h]
0x14005c898  test    eax, eax
0x14005c89a  jz      short loc_14005C8A2
0x14005c89c  cmp     [rbp+57h+IsMember], edi
0x14005c89f  cmovnz  ebx, edi
0x14005c8a2  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14005c8a6  call    cs:__imp_FreeSid
0x14005c8ad  nop     dword ptr [rax+rax+00h]
0x14005c8b2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14005c8b6  call    cs:__imp_CloseHandle
0x14005c8bd  nop     dword ptr [rax+rax+00h]
0x14005c8c2  mov     al, bl
0x14005c8c4  mov     rcx, [rbp+57h+var_10]
0x14005c8c8  xor     rcx, rsp; StackCookie
0x14005c8cb  call    __security_check_cookie
0x14005c8d0  lea     r11, [rsp+90h+var_s0]
0x14005c8d8  mov     rbx, [r11+18h]
0x14005c8dc  mov     rdi, [r11+20h]
0x14005c8e0  mov     rsp, r11
0x14005c8e3  pop     rbp
0x14005c8e4  retn
```
