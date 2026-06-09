# CheckElevatedPermissionToShellItem

- ea: `0x1802bf7f0`
- end: `0x1802bfabc`
- name: `CheckElevatedPermissionToShellItem`
- size: `716`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18031d728`
- `0x1804e5fa0`

## callees

- `0x18009d164`
- `0x1802bf7f0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bf957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bf957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802bf844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802bf844`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802bf889`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802bf889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802bf87a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802bf87a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802bf85a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802bf85a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bfa40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bfa4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bfa40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bfa4a`
- `ntdll!RtlMapGenericMask` at `0x1802bf9a1`
- `ntdll!RtlMapGenericMask` at `0x1802bf9a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf8d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf96b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf8d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf96b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bfa54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bfa54`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802bf914`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802bf914`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802bf8bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802bf8bb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802bf8fb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802bf8fb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802bf949`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802bf9d7`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802bf949`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802bf9d7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1802bfa18`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1802bfa18`

## pseudocode

```c
__int64 __fastcall CheckElevatedPermissionToShellItem(__int64 *a1, DWORD a2)
{
  __int64 v2; // rax
  int v3; // ebx
  HANDLE CurrentThread; // rax
  int Error; // eax
  HANDLE CurrentProcess; // rax
  HLOCAL v7; // rax
  void *v8; // rdi
  HLOCAL v9; // rsi
  HANDLE TokenInformation; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-19h] BYREF
  DWORD nLengthNeeded; // [rsp+58h] [rbp-11h] BYREF
  WINBOOL IsMember; // [rsp+5Ch] [rbp-Dh] BYREF
  DWORD AccessMask; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL AccessStatus; // [rsp+68h] [rbp-1h] BYREF
  DWORD ReturnLength; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cbSid; // [rsp+70h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+78h] [rbp+Fh] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+80h] [rbp+17h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp+27h] BYREF

  v2 = *a1;
  AccessMask = a2;
  lpFileName = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPCWSTR *))(v2 + 40))(a1, 2147844096LL, &lpFileName);
  if ( v3 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
      v3 = Error;
      if ( Error < 0 )
      {
        if ( Error != -2147023888 )
          goto LABEL_21;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        {
          v3 = ResultFromKnownLastError();
          if ( v3 < 0 )
            goto LABEL_21;
        }
      }
    }
    TokenInformation = 0;
    ReturnLength = 8;
    if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
    {
      v3 = ResultFromKnownLastError();
      goto LABEL_20;
    }
    cbSid = 68;
    v7 = LocalAlloc(0x40u, 0x44u);
    v8 = v7;
    if ( !v7 )
    {
      v3 = -2147024882;
      goto LABEL_19;
    }
    IsMember = 0;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v7, &cbSid)
      && CheckTokenMembership(TokenInformation, v8, &IsMember) )
    {
      if ( !IsMember )
      {
        v3 = -2147024891;
LABEL_18:
        LocalFree(v8);
LABEL_19:
        CloseHandle(TokenInformation);
LABEL_20:
        CloseHandle(TokenHandle);
LABEL_21:
        CoTaskMemFree((LPVOID)lpFileName);
        return (unsigned int)v3;
      }
      nLengthNeeded = 0;
      if ( !GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
      {
        v9 = LocalAlloc(0x40u, nLengthNeeded);
        if ( v9 )
        {
          GenericMapping.GenericRead = 1179785;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          RtlMapGenericMask(&AccessMask, &GenericMapping);
          AccessStatus = 0;
          GrantedAccess = 0;
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          PrivilegeSetLength = 20;
          if ( GetFileSecurityW(lpFileName, 7u, v9, nLengthNeeded, &nLengthNeeded)
            && AccessCheck(
                 v9,
                 TokenInformation,
                 AccessMask,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            v3 = AccessStatus == 0;
          }
          else
          {
            v3 = ResultFromKnownLastError();
          }
          LocalFree(v9);
        }
        else
        {
          v3 = -2147024882;
        }
        goto LABEL_18;
      }
    }
    v3 = ResultFromKnownLastError();
    goto LABEL_18;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802bf7f0  mov     [rsp-8+arg_10], rbx
0x1802bf7f5  push    rbp
0x1802bf7f6  push    rsi
0x1802bf7f7  push    rdi
0x1802bf7f8  lea     rbp, [rsp-47h]
0x1802bf7fd  sub     rsp, 0B0h
0x1802bf804  mov     rax, cs:__security_cookie
0x1802bf80b  xor     rax, rsp
0x1802bf80e  mov     [rbp+57h+var_18], rax
0x1802bf812  mov     rax, [rcx]
0x1802bf815  lea     r8, [rbp+57h+lpFileName]
0x1802bf819  mov     [rbp+57h+AccessMask], edx
0x1802bf81c  mov     edx, 80058000h
0x1802bf821  mov     [rbp+57h+lpFileName], 0
0x1802bf829  mov     rax, [rax+28h]
0x1802bf82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bf832  mov     ebx, eax
0x1802bf834  test    eax, eax
0x1802bf836  js      loc_1802BFA5A
0x1802bf83c  mov     [rbp+57h+TokenHandle], 0
0x1802bf844  call    cs:__imp_GetCurrentThread
0x1802bf84a  xor     r8d, r8d; OpenAsSelf
0x1802bf84d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1802bf851  mov     rcx, rax; ThreadHandle
0x1802bf854  lea     edi, [r8+8]
0x1802bf858  mov     edx, edi; DesiredAccess
0x1802bf85a  call    cs:__imp_OpenThreadToken
0x1802bf860  test    eax, eax
0x1802bf862  jnz     short loc_1802BF897
0x1802bf864  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802bf869  mov     ebx, eax
0x1802bf86b  test    eax, eax
0x1802bf86d  jns     short loc_1802BF897
0x1802bf86f  cmp     eax, 800703F0h
0x1802bf874  jnz     loc_1802BFA50
0x1802bf87a  call    cs:__imp_GetCurrentProcess
0x1802bf880  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1802bf884  mov     edx, edi; DesiredAccess
0x1802bf886  mov     rcx, rax; ProcessHandle
0x1802bf889  call    cs:__imp_OpenProcessToken
0x1802bf88f  test    eax, eax
0x1802bf891  jz      loc_1802BFA89
0x1802bf897  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1802bf89b  lea     rax, [rbp+57h+var_54]
0x1802bf89f  mov     r9d, edi; TokenInformationLength
0x1802bf8a2  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1802bf8a7  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1802bf8ab  mov     [rbp+57h+TokenInformation], 0
0x1802bf8b3  mov     edx, 13h; TokenInformationClass
0x1802bf8b8  mov     [rbp+57h+var_54], edi
0x1802bf8bb  call    cs:__imp_GetTokenInformation
0x1802bf8c1  test    eax, eax
0x1802bf8c3  jz      loc_1802BFAB3
0x1802bf8c9  mov     edx, 44h ; 'D'; uBytes
0x1802bf8ce  mov     [rbp+57h+cbSid], edx
0x1802bf8d1  lea     ebx, [rdx-4]
0x1802bf8d4  mov     ecx, ebx; uFlags
0x1802bf8d6  call    cs:__imp_LocalAlloc
0x1802bf8dc  mov     rdi, rax
0x1802bf8df  test    rax, rax
0x1802bf8e2  jz      loc_1802BFA82
0x1802bf8e8  lea     r9, [rbp+57h+cbSid]; cbSid
0x1802bf8ec  mov     [rbp+57h+IsMember], 0
0x1802bf8f3  mov     r8, rax; pSid
0x1802bf8f6  lea     ecx, [rbx-26h]; WellKnownSidType
0x1802bf8f9  xor     edx, edx; DomainSid
0x1802bf8fb  call    cs:__imp_CreateWellKnownSid
0x1802bf901  test    eax, eax
0x1802bf903  jz      loc_1802BFAAA
0x1802bf909  mov     rcx, [rbp+57h+TokenInformation]; TokenHandle
0x1802bf90d  lea     r8, [rbp+57h+IsMember]; IsMember
0x1802bf911  mov     rdx, rdi; SidToCheck
0x1802bf914  call    cs:__imp_CheckTokenMembership
0x1802bf91a  test    eax, eax
0x1802bf91c  jz      loc_1802BFAAA
0x1802bf922  cmp     [rbp+57h+IsMember], 0
0x1802bf926  jz      loc_1802BFAA3
0x1802bf92c  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1802bf930  lea     rax, [rbp+57h+nLengthNeeded]
0x1802bf934  xor     r9d, r9d; nLength
0x1802bf937  mov     [rsp+0C0h+ReturnLength], rax; lpnLengthNeeded
0x1802bf93c  xor     r8d, r8d; pSecurityDescriptor
0x1802bf93f  mov     [rbp+57h+nLengthNeeded], 0
0x1802bf946  lea     edx, [rbx-39h]; RequestedInformation
0x1802bf949  call    cs:__imp_GetFileSecurityW
0x1802bf94f  test    eax, eax
0x1802bf951  jnz     loc_1802BFAAA
0x1802bf957  call    cs:__imp_GetLastError
0x1802bf95d  cmp     eax, 7Ah ; 'z'
0x1802bf960  jnz     loc_1802BFAAA
0x1802bf966  mov     edx, [rbp+57h+nLengthNeeded]; uBytes
0x1802bf969  mov     ecx, ebx; uFlags
0x1802bf96b  call    cs:__imp_LocalAlloc
0x1802bf971  mov     rsi, rax
0x1802bf974  test    rax, rax
0x1802bf977  jz      loc_1802BFA7B
0x1802bf97d  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1802bf981  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1802bf988  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1802bf98c  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1802bf993  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1802bf99a  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1802bf9a1  call    cs:__imp_RtlMapGenericMask
0x1802bf9a7  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1802bf9ab  lea     edx, [rbx-39h]; RequestedInformation
0x1802bf9ae  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1802bf9b2  xor     eax, eax
0x1802bf9b4  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x1802bf9b7  xorps   xmm0, xmm0
0x1802bf9ba  mov     [rbp+57h+var_58], eax
0x1802bf9bd  mov     r8, rsi; pSecurityDescriptor
0x1802bf9c0  mov     [rbp+57h+var_4C], eax
0x1802bf9c3  lea     rax, [rbp+57h+nLengthNeeded]
0x1802bf9c7  mov     [rsp+0C0h+ReturnLength], rax; lpnLengthNeeded
0x1802bf9cc  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x1802bf9d0  mov     [rbp+57h+var_48], 14h
0x1802bf9d7  call    cs:__imp_GetFileSecurityW
0x1802bf9dd  test    eax, eax
0x1802bf9df  jz      loc_1802BFA9A
0x1802bf9e5  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1802bf9e9  lea     rax, [rbp+57h+var_58]
0x1802bf9ed  mov     rdx, [rbp+57h+TokenInformation]; ClientToken
0x1802bf9f1  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1802bf9f5  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x1802bf9fa  mov     rcx, rsi; pSecurityDescriptor
0x1802bf9fd  lea     rax, [rbp+57h+var_4C]
0x1802bfa01  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x1802bfa06  lea     rax, [rbp+57h+var_48]
0x1802bfa0a  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1802bfa0f  lea     rax, [rbp+57h+PrivilegeSet]
0x1802bfa13  mov     [rsp+0C0h+ReturnLength], rax; PrivilegeSet
0x1802bfa18  call    cs:__imp_AccessCheck
0x1802bfa1e  test    eax, eax
0x1802bfa20  jz      short loc_1802BFA9A
0x1802bfa22  xor     ebx, ebx
0x1802bfa24  cmp     [rbp+57h+var_58], ebx
0x1802bfa27  setz    bl
0x1802bfa2a  mov     rcx, rsi; hMem
0x1802bfa2d  call    cs:__imp_LocalFree
0x1802bfa33  mov     rcx, rdi; hMem
0x1802bfa36  call    cs:__imp_LocalFree
0x1802bfa3c  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x1802bfa40  call    cs:__imp_CloseHandle
0x1802bfa46  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1802bfa4a  call    cs:__imp_CloseHandle
0x1802bfa50  mov     rcx, [rbp+57h+lpFileName]; pv
0x1802bfa54  call    cs:__imp_CoTaskMemFree
0x1802bfa5a  mov     eax, ebx
0x1802bfa5c  mov     rcx, [rbp+57h+var_18]
0x1802bfa60  xor     rcx, rsp; StackCookie
0x1802bfa63  call    __security_check_cookie
0x1802bfa68  mov     rbx, [rsp+0C0h+arg_10]
0x1802bfa70  add     rsp, 0B0h
0x1802bfa77  pop     rdi
0x1802bfa78  pop     rsi
0x1802bfa79  pop     rbp
0x1802bfa7a  retn
0x1802bfa7b  mov     ebx, 8007000Eh
0x1802bfa80  jmp     short loc_1802BFA33
0x1802bfa82  mov     ebx, 8007000Eh
0x1802bfa87  jmp     short loc_1802BFA3C
0x1802bfa89  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802bfa8e  mov     ebx, eax
0x1802bfa90  test    eax, eax
0x1802bfa92  jns     loc_1802BF897
0x1802bfa98  jmp     short loc_1802BFA50
0x1802bfa9a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802bfa9f  mov     ebx, eax
0x1802bfaa1  jmp     short loc_1802BFA2A
0x1802bfaa3  mov     ebx, 80070005h
0x1802bfaa8  jmp     short loc_1802BFA33
0x1802bfaaa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802bfaaf  mov     ebx, eax
0x1802bfab1  jmp     short loc_1802BFA33
0x1802bfab3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802bfab8  mov     ebx, eax
0x1802bfaba  jmp     short loc_1802BFA46
```
