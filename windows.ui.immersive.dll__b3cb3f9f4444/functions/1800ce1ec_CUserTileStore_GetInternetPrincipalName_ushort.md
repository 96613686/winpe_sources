# CUserTileStore::_GetInternetPrincipalName(ushort * *)

- ea: `0x1800ce1ec`
- end: `0x1800ce3c4`
- name: `?_GetInternetPrincipalName@CUserTileStore@@AEAAJPEAPEAG@Z`
- size: `472`
- prototype: `int(CUserTileStore *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800068e0`

## callees

- `0x180006b40`
- `0x180032e68`
- `0x18003d244`
- `0x1800ce1ec`
- `0x1800ce3cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce22e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce22e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce210`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ce261`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ce261`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ce24c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ce24c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce3aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce3aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ce39a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ce39a`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800ce364`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800ce364`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce2c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce327`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce2c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce327`

## pseudocode

```c
__int64 __fastcall CUserTileStore::_GetInternetPrincipalName(CUserTileStore *this, unsigned __int16 **a2)
{
  HANDLE CurrentThread; // rax
  CUserTileStore *v4; // rcx
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  CUserTileStore *v7; // rcx
  void *v8; // rcx
  unsigned int *v9; // rsi
  unsigned int i; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  unsigned __int64 v12; // rcx
  CUserTileStore *TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  TokenInformationLength = this;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_4;
  Error = ResultFromKnownLastError();
  if ( Error != -2147023888 )
    goto LABEL_6;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
LABEL_4:
    Error = 0;
  else
    Error = ResultFromKnownLastError();
LABEL_6:
  if ( Error >= 0 )
  {
    if ( CUserTileStore::_IsDomainUser(v4) )
    {
      LODWORD(TokenInformationLength) = 0;
      if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, (PDWORD)&TokenInformationLength) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error == -2147024774 )
        {
          TokenInformation = 0;
          Error = CTLocalAllocPolicy::Alloc(v8, 0x40u, (unsigned int)TokenInformationLength, &TokenInformation);
          if ( Error >= 0 )
          {
            v9 = (unsigned int *)TokenInformation;
            if ( GetTokenInformation(
                   TokenHandle,
                   TokenGroups,
                   TokenInformation,
                   (DWORD)TokenInformationLength,
                   (PDWORD)&TokenInformationLength)
              || (Error = ResultFromKnownLastError(), Error >= 0) )
            {
              Error = -2147467259;
              LODWORD(TokenInformation) = 0;
              WORD2(TokenInformation) = 2816;
              for ( i = 0; i < *v9; ++i )
              {
                SidIdentifierAuthority = GetSidIdentifierAuthority(*(PSID *)&v9[4 * i + 2]);
                v12 = (unsigned int)(*(_DWORD *)SidIdentifierAuthority->Value - (_DWORD)TokenInformation);
                if ( *(_DWORD *)SidIdentifierAuthority->Value == (_DWORD)TokenInformation )
                  v12 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - (unsigned int)WORD2(TokenInformation);
                if ( !(_DWORD)v12 )
                {
                  Error = CUserTileStore::_GetInternetPrincipalNameFromUserToken((CUserTileStore *)v12, TokenHandle, a2);
                  break;
                }
              }
            }
            LocalFree(v9);
          }
        }
      }
    }
    else
    {
      Error = CUserTileStore::_GetInternetPrincipalNameFromUserToken(v7, TokenHandle, a2);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800ce1ec  mov     [rsp-28h+TokenInformationLength], rcx
0x1800ce1f1  push    rbp
0x1800ce1f2  push    rbx
0x1800ce1f3  push    rsi
0x1800ce1f4  push    rdi
0x1800ce1f5  push    r14
0x1800ce1f7  mov     rbp, rsp
0x1800ce1fa  sub     rsp, 30h
0x1800ce1fe  mov     r14, rdx
0x1800ce201  mov     qword ptr [rdx], 0
0x1800ce208  mov     [rbp+TokenHandle], 0
0x1800ce210  call    cs:__imp_GetCurrentThread
0x1800ce217  nop     dword ptr [rax+rax+00h]
0x1800ce21c  mov     edi, 8
0x1800ce221  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ce225  mov     rcx, rax; ThreadHandle
0x1800ce228  mov     edx, edi; DesiredAccess
0x1800ce22a  lea     r8d, [rdi-7]; OpenAsSelf
0x1800ce22e  call    cs:__imp_OpenThreadToken
0x1800ce235  nop     dword ptr [rax+rax+00h]
0x1800ce23a  test    eax, eax
0x1800ce23c  jnz     short loc_1800CE271
0x1800ce23e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce243  mov     ebx, eax
0x1800ce245  cmp     eax, 800703F0h
0x1800ce24a  jnz     short loc_1800CE27C
0x1800ce24c  call    cs:__imp_GetCurrentProcess
0x1800ce253  nop     dword ptr [rax+rax+00h]
0x1800ce258  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ce25c  mov     edx, edi; DesiredAccess
0x1800ce25e  mov     rcx, rax; ProcessHandle
0x1800ce261  call    cs:__imp_OpenProcessToken
0x1800ce268  nop     dword ptr [rax+rax+00h]
0x1800ce26d  test    eax, eax
0x1800ce26f  jz      short loc_1800CE275
0x1800ce271  xor     ebx, ebx
0x1800ce273  jmp     short loc_1800CE27C
0x1800ce275  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce27a  mov     ebx, eax
0x1800ce27c  test    ebx, ebx
0x1800ce27e  js      loc_1800CE3B6
0x1800ce284  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x1800ce289  test    al, al
0x1800ce28b  jnz     short loc_1800CE2A0
0x1800ce28d  mov     rdx, [rbp+TokenHandle]; void *
0x1800ce291  mov     r8, r14; unsigned __int16 **
0x1800ce294  call    ?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)
0x1800ce299  mov     ebx, eax
0x1800ce29b  jmp     loc_1800CE3A6
0x1800ce2a0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ce2a4  lea     rax, [rbp+TokenInformationLength]
0x1800ce2a8  xor     r9d, r9d; TokenInformationLength
0x1800ce2ab  mov     dword ptr [rbp+TokenInformationLength], 0
0x1800ce2b2  xor     r8d, r8d; TokenInformation
0x1800ce2b5  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800ce2ba  lea     edi, [r9+2]
0x1800ce2be  mov     edx, edi; TokenInformationClass
0x1800ce2c0  call    cs:__imp_GetTokenInformation
0x1800ce2c7  nop     dword ptr [rax+rax+00h]
0x1800ce2cc  test    eax, eax
0x1800ce2ce  jz      short loc_1800CE2D7
0x1800ce2d0  xor     ebx, ebx
0x1800ce2d2  jmp     loc_1800CE3A6
0x1800ce2d7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce2dc  mov     ebx, eax
0x1800ce2de  cmp     eax, 8007007Ah
0x1800ce2e3  jnz     loc_1800CE3A6
0x1800ce2e9  mov     r8d, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x1800ce2ed  lea     r9, [rbp+TokenInformation]; void **
0x1800ce2f1  mov     edx, 40h ; '@'; unsigned int
0x1800ce2f6  mov     [rbp+TokenInformation], 0
0x1800ce2fe  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800ce303  mov     ebx, eax
0x1800ce305  test    eax, eax
0x1800ce307  js      loc_1800CE3A6
0x1800ce30d  mov     rsi, [rbp+TokenInformation]
0x1800ce311  lea     rax, [rbp+TokenInformationLength]
0x1800ce315  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x1800ce319  mov     r8, rsi; TokenInformation
0x1800ce31c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ce320  mov     edx, edi; TokenInformationClass
0x1800ce322  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800ce327  call    cs:__imp_GetTokenInformation
0x1800ce32e  nop     dword ptr [rax+rax+00h]
0x1800ce333  test    eax, eax
0x1800ce335  jnz     short loc_1800CE342
0x1800ce337  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce33c  mov     ebx, eax
0x1800ce33e  test    eax, eax
0x1800ce340  js      short loc_1800CE397
0x1800ce342  mov     ebx, 80004005h
0x1800ce347  mov     dword ptr [rbp+TokenInformation], 0
0x1800ce34e  mov     word ptr [rbp+TokenInformation+4], 0B00h
0x1800ce354  xor     edi, edi
0x1800ce356  cmp     edi, [rsi]
0x1800ce358  jnb     short loc_1800CE397
0x1800ce35a  mov     ecx, edi
0x1800ce35c  add     rcx, rcx
0x1800ce35f  mov     rcx, [rsi+rcx*8+8]; pSid
0x1800ce364  call    cs:__imp_GetSidIdentifierAuthority
0x1800ce36b  nop     dword ptr [rax+rax+00h]
0x1800ce370  mov     ecx, [rax]
0x1800ce372  sub     ecx, dword ptr [rbp+TokenInformation]
0x1800ce375  jnz     short loc_1800CE381
0x1800ce377  movzx   ecx, word ptr [rax+4]
0x1800ce37b  movzx   eax, word ptr [rbp+TokenInformation+4]
0x1800ce37f  sub     ecx, eax; this
0x1800ce381  test    ecx, ecx
0x1800ce383  jz      short loc_1800CE389
0x1800ce385  inc     edi
0x1800ce387  jmp     short loc_1800CE356
0x1800ce389  mov     rdx, [rbp+TokenHandle]; void *
0x1800ce38d  mov     r8, r14; unsigned __int16 **
0x1800ce390  call    ?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)
0x1800ce395  mov     ebx, eax
0x1800ce397  mov     rcx, rsi; hMem
0x1800ce39a  call    cs:__imp_LocalFree
0x1800ce3a1  nop     dword ptr [rax+rax+00h]
0x1800ce3a6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ce3aa  call    cs:__imp_CloseHandle
0x1800ce3b1  nop     dword ptr [rax+rax+00h]
0x1800ce3b6  mov     eax, ebx
0x1800ce3b8  add     rsp, 30h
0x1800ce3bc  pop     r14
0x1800ce3be  pop     rdi
0x1800ce3bf  pop     rsi
0x1800ce3c0  pop     rbx
0x1800ce3c1  pop     rbp
0x1800ce3c2  retn
```
