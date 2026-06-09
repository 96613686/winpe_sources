# IsThreadLocalSystemOrNetworkService(uchar *)

- ea: `0x1800069b0`
- end: `0x180006b4e`
- name: `?IsThreadLocalSystemOrNetworkService@@YAKPEAE@Z`
- size: `414`
- prototype: `unsigned int __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180006c38`

## callees

- `0x1800069b0`
- `0x180006b54`
- `0x180057c8c`
- `0x1800597b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b41`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006a73`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006ab9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006a73`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006ab9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006a96`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006ad0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006a96`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006a03`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006a03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a27`

## pseudocode

```c
__int64 __fastcall IsThreadLocalSystemOrNetworkService(unsigned __int8 *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  CCipherMill *v5; // rcx
  __int64 v6; // rdx
  DWORD cbSid; // [rsp+20h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-C0h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-B8h] BYREF
  unsigned __int8 pSid2[80]; // [rsp+80h] [rbp-68h] BYREF

  TokenHandle = 0;
  cbSid = 68;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) || !GetTokenUserSid(TokenHandle, pSid2) )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    goto LABEL_8;
  LastError = 0;
  if ( EqualSid(pSid, pSid2) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_21;
    v6 = 10;
    goto LABEL_20;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinNetworkServiceSid, 0, pSid, &cbSid) )
  {
LABEL_8:
    LastError = GetLastError();
    goto LABEL_3;
  }
  if ( EqualSid(pSid, pSid2) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_21;
    v6 = 11;
LABEL_20:
    WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_515891eeb9b1375e41800a5e1897fca1_Traceguids);
LABEL_21:
    *a1 = 1;
  }
LABEL_3:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800069b0  push    rbx
0x1800069b2  sub     rsp, 0E0h
0x1800069b9  mov     rax, cs:__security_cookie
0x1800069c0  xor     rax, rsp
0x1800069c3  mov     [rsp+0E8h+var_18], rax
0x1800069cb  mov     [rsp+0E8h+arg_8], rdi
0x1800069d3  mov     rdi, rcx
0x1800069d6  mov     [rsp+0E8h+TokenHandle], 0
0x1800069df  mov     [rsp+0E8h+cbSid], 44h ; 'D'
0x1800069e7  mov     byte ptr [rcx], 0
0x1800069ea  call    cs:__imp_GetCurrentThread
0x1800069f0  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800069f5  mov     edx, 8; DesiredAccess
0x1800069fa  mov     rcx, rax; ThreadHandle
0x1800069fd  mov     r8d, 1; OpenAsSelf
0x180006a03  call    cs:__imp_OpenThreadToken
0x180006a09  test    eax, eax
0x180006a0b  jnz     short loc_180006A48
0x180006a0d  call    cs:__imp_GetLastError
0x180006a13  mov     ebx, eax
0x180006a15  mov     rcx, [rsp+0E8h+TokenHandle]; hObject
0x180006a1a  mov     rdi, [rsp+0E8h+arg_8]
0x180006a22  test    rcx, rcx
0x180006a25  jz      short loc_180006A2D
0x180006a27  call    cs:__imp_CloseHandle
0x180006a2d  mov     eax, ebx
0x180006a2f  mov     rcx, [rsp+0E8h+var_18]
0x180006a37  xor     rcx, rsp; StackCookie
0x180006a3a  call    __security_check_cookie
0x180006a3f  add     rsp, 0E0h
0x180006a46  pop     rbx
0x180006a47  retn
0x180006a48  mov     rcx, [rsp+0E8h+TokenHandle]; void *
0x180006a4d  lea     rdx, [rsp+0E8h+pSid2]; unsigned __int8 *
0x180006a55  call    ?GetTokenUserSid@@YAHPEAXQEAE@Z; GetTokenUserSid(void *,uchar * const)
0x180006a5a  test    eax, eax
0x180006a5c  jz      loc_180006B09
0x180006a62  lea     r9, [rsp+0E8h+cbSid]; cbSid
0x180006a67  xor     edx, edx; DomainSid
0x180006a69  lea     r8, [rsp+0E8h+pSid]; pSid
0x180006a6e  mov     ecx, 16h; WellKnownSidType
0x180006a73  call    cs:__imp_CreateWellKnownSid
0x180006a79  test    eax, eax
0x180006a7b  jnz     short loc_180006A87
0x180006a7d  call    cs:__imp_GetLastError
0x180006a83  mov     ebx, eax
0x180006a85  jmp     short loc_180006A15
0x180006a87  lea     rdx, [rsp+0E8h+pSid2]; pSid2
0x180006a8f  xor     ebx, ebx
0x180006a91  lea     rcx, [rsp+0E8h+pSid]; pSid1
0x180006a96  call    cs:__imp_EqualSid
0x180006a9c  test    eax, eax
0x180006a9e  jnz     short loc_180006B16
0x180006aa0  lea     r9, [rsp+0E8h+cbSid]; cbSid
0x180006aa5  mov     [rsp+0E8h+cbSid], 44h ; 'D'
0x180006aad  lea     r8, [rsp+0E8h+pSid]; pSid
0x180006ab2  xor     edx, edx; DomainSid
0x180006ab4  mov     ecx, 18h; WellKnownSidType
0x180006ab9  call    cs:__imp_CreateWellKnownSid
0x180006abf  test    eax, eax
0x180006ac1  jz      short loc_180006B41
0x180006ac3  lea     rdx, [rsp+0E8h+pSid2]; pSid2
0x180006acb  lea     rcx, [rsp+0E8h+pSid]; pSid1
0x180006ad0  call    cs:__imp_EqualSid
0x180006ad6  test    eax, eax
0x180006ad8  jz      loc_180006A15
0x180006ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ae5  lea     rax, WPP_GLOBAL_Control
0x180006aec  cmp     rcx, rax
0x180006aef  jz      loc_180089674
0x180006af5  test    byte ptr [rcx+1Ch], 4
0x180006af9  jz      loc_180089674
0x180006aff  mov     edx, 0Bh
0x180006b04  jmp     loc_180089664
0x180006b09  call    cs:__imp_GetLastError
0x180006b0f  mov     ebx, eax
0x180006b11  jmp     loc_180006A15
0x180006b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b1d  lea     rax, WPP_GLOBAL_Control
0x180006b24  cmp     rcx, rax
0x180006b27  jz      loc_180089674
0x180006b2d  test    byte ptr [rcx+1Ch], 4
0x180006b31  jz      loc_180089674
0x180006b37  mov     edx, 0Ah
0x180006b3c  jmp     loc_180089664
0x180006b41  call    cs:__imp_GetLastError
0x180006b47  mov     ebx, eax
0x180006b49  jmp     loc_180006A15
0x180089664  mov     rcx, [rcx+10h]
0x180089668  lea     r8, WPP_515891eeb9b1375e41800a5e1897fca1_Traceguids
0x18008966f  call    WPP_SF_
0x180089674  mov     byte ptr [rdi], 1
0x180089677  jmp     loc_180006A15
```
