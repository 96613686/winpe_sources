# IsLocalCall(void *)

- ea: `0x1400571cc`
- end: `0x1400572d3`
- name: `?IsLocalCall@@YA_NPEAX@Z`
- size: `263`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002a550`

## callees

- `0x14002abc0`
- `0x1400571cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005722e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005722e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005721b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005721b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400572aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400572aa`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1400571fd`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1400571fd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140057273`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140057273`
- `ADVAPI32!CheckTokenMembership` at `0x14005728c`
- `ADVAPI32!CheckTokenMembership` at `0x14005728c`
- `ADVAPI32!FreeSid` at `0x1400572a0`
- `ADVAPI32!FreeSid` at `0x1400572a0`

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
0x1400571cc  mov     [rsp-8+arg_8], rbx
0x1400571d1  mov     [rsp-8+arg_10], rdi
0x1400571d6  push    rbp
0x1400571d7  lea     rbp, [rsp-57h]
0x1400571dc  sub     rsp, 90h
0x1400571e3  mov     rax, cs:__security_cookie
0x1400571ea  xor     rax, rsp
0x1400571ed  mov     [rbp+57h+var_10], rax
0x1400571f1  xor     edi, edi
0x1400571f3  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x1400571f7  mov     bl, dil
0x1400571fa  mov     [rbp+57h+ClientLocalFlag], edi
0x1400571fd  call    cs:__imp_I_RpcBindingIsClientLocal
0x140057203  test    eax, eax
0x140057205  jnz     loc_1400572B0
0x14005720b  cmp     [rbp+57h+ClientLocalFlag], edi
0x14005720e  jz      loc_1400572B0
0x140057214  lea     ebx, [rdi+1]
0x140057217  mov     [rbp+57h+TokenHandle], rdi
0x14005721b  call    cs:__imp_GetCurrentThread
0x140057221  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140057225  mov     r8d, ebx; OpenAsSelf
0x140057228  mov     rcx, rax; ThreadHandle
0x14005722b  lea     edx, [rdi+8]; DesiredAccess
0x14005722e  call    cs:__imp_OpenThreadToken
0x140057234  test    eax, eax
0x140057236  jz      short loc_1400572B0
0x140057238  lea     rax, [rbp+57h+SidToCheck]
0x14005723c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14005723f  mov     [rsp+90h+pSid], rax; pSid
0x140057244  lea     r8d, [rdi+2]; nSubAuthority0
0x140057248  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x14005724c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140057250  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x140057254  xor     r9d, r9d; nSubAuthority1
0x140057257  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x14005725b  mov     dl, bl; nSubAuthorityCount
0x14005725d  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x140057261  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x140057265  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x140057269  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14005726f  mov     [rbp+57h+SidToCheck], rdi
0x140057273  call    cs:__imp_AllocateAndInitializeSid
0x140057279  test    eax, eax
0x14005727b  jz      short loc_1400572A6
0x14005727d  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140057281  lea     r8, [rbp+57h+IsMember]; IsMember
0x140057285  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140057289  mov     [rbp+57h+IsMember], edi
0x14005728c  call    cs:__imp_CheckTokenMembership
0x140057292  test    eax, eax
0x140057294  jz      short loc_14005729C
0x140057296  cmp     [rbp+57h+IsMember], edi
0x140057299  cmovnz  ebx, edi
0x14005729c  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1400572a0  call    cs:__imp_FreeSid
0x1400572a6  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1400572aa  call    cs:__imp_CloseHandle
0x1400572b0  mov     al, bl
0x1400572b2  mov     rcx, [rbp+57h+var_10]
0x1400572b6  xor     rcx, rsp; StackCookie
0x1400572b9  call    __security_check_cookie
0x1400572be  lea     r11, [rsp+90h+var_s0]
0x1400572c6  mov     rbx, [r11+18h]
0x1400572ca  mov     rdi, [r11+20h]
0x1400572ce  mov     rsp, r11
0x1400572d1  pop     rbp
0x1400572d2  retn
```
