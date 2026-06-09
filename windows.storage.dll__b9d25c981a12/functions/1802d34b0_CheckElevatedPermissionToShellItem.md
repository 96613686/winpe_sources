# CheckElevatedPermissionToShellItem

- ea: `0x1802d34b0`
- end: `0x1802d3798`
- name: `CheckElevatedPermissionToShellItem`
- size: `744`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18032fd48`
- `0x1804fa740`

## callees

- `0x18004e06c`
- `0x1801bec64`
- `0x1802d34b0`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d35fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d35fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d3711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d3721`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d3711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d3721`
- `ntdll!RtlMapGenericMask` at `0x1802d3650`
- `ntdll!RtlMapGenericMask` at `0x1802d3650`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d3561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d3614`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d3561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d3614`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d36f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d3701`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d36f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d3701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d3731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d3731`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802d35ab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802d35ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d3540`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d3540`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802d358c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802d358c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802d35e6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802d368c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802d35e6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1802d368c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1802d36d3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1802d36d3`

## pseudocode

```c
__int64 __fastcall CheckElevatedPermissionToShellItem(__int64 *a1, DWORD a2)
{
  __int64 v2; // rax
  unsigned int v3; // ecx
  int Error; // ebx
  HLOCAL v5; // rax
  void *v6; // rdi
  HLOCAL v7; // rsi
  HANDLE TokenInformation; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-21h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-19h] BYREF
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
  Error = (*(__int64 (__fastcall **)(__int64 *, __int64, LPCWSTR *))(v2 + 40))(a1, 2147844096LL, &lpFileName);
  if ( Error >= 0 )
  {
    TokenHandle = 0;
    Error = SHOpenEffectiveToken(v3, 0, &TokenHandle);
    if ( Error < 0 )
    {
LABEL_18:
      CoTaskMemFree((LPVOID)lpFileName);
      return (unsigned int)Error;
    }
    TokenInformation = 0;
    ReturnLength = 8;
    if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
    {
      Error = ResultFromKnownLastError();
      goto LABEL_17;
    }
    cbSid = 68;
    v5 = LocalAlloc(0x40u, 0x44u);
    v6 = v5;
    if ( !v5 )
    {
      Error = -2147024882;
      goto LABEL_16;
    }
    IsMember = 0;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v5, &cbSid)
      && CheckTokenMembership(TokenInformation, v6, &IsMember) )
    {
      if ( !IsMember )
      {
        Error = -2147024891;
LABEL_15:
        LocalFree(v6);
LABEL_16:
        CloseHandle(TokenInformation);
LABEL_17:
        CloseHandle(TokenHandle);
        goto LABEL_18;
      }
      nLengthNeeded = 0;
      if ( !GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
      {
        v7 = LocalAlloc(0x40u, nLengthNeeded);
        if ( v7 )
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
          if ( GetFileSecurityW(lpFileName, 7u, v7, nLengthNeeded, &nLengthNeeded)
            && AccessCheck(
                 v7,
                 TokenInformation,
                 AccessMask,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            Error = AccessStatus == 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
          LocalFree(v7);
        }
        else
        {
          Error = -2147024882;
        }
        goto LABEL_15;
      }
    }
    Error = ResultFromKnownLastError();
    goto LABEL_15;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802d34b0  mov     [rsp-8+arg_10], rbx
0x1802d34b5  push    rbp
0x1802d34b6  push    rsi
0x1802d34b7  push    rdi
0x1802d34b8  lea     rbp, [rsp-47h]
0x1802d34bd  sub     rsp, 0B0h
0x1802d34c4  mov     rax, cs:__security_cookie
0x1802d34cb  xor     rax, rsp
0x1802d34ce  mov     [rbp+57h+var_18], rax
0x1802d34d2  mov     rax, [rcx]
0x1802d34d5  lea     r8, [rbp+57h+lpFileName]
0x1802d34d9  mov     [rbp+57h+AccessMask], edx
0x1802d34dc  mov     edx, 80058000h
0x1802d34e1  mov     [rbp+57h+lpFileName], 0
0x1802d34e9  mov     rax, [rax+28h]
0x1802d34ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d34f2  mov     ebx, eax
0x1802d34f4  test    eax, eax
0x1802d34f6  js      loc_1802D373D
0x1802d34fc  lea     r8, [rbp+57h+TokenHandle]; void **
0x1802d3500  mov     [rbp+57h+TokenHandle], 0
0x1802d3508  xor     edx, edx; int
0x1802d350a  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1802d350f  mov     ebx, eax
0x1802d3511  test    eax, eax
0x1802d3513  js      loc_1802D372D
0x1802d3519  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1802d351d  lea     rax, [rbp+57h+var_54]
0x1802d3521  mov     r9d, 8; TokenInformationLength
0x1802d3527  mov     [rbp+57h+TokenInformation], 0
0x1802d352f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1802d3533  mov     [rbp+57h+var_54], r9d
0x1802d3537  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1802d353c  lea     edx, [r9+0Bh]; TokenInformationClass
0x1802d3540  call    cs:__imp_GetTokenInformation
0x1802d3547  nop     dword ptr [rax+rax+00h]
0x1802d354c  test    eax, eax
0x1802d354e  jz      loc_1802D378F
0x1802d3554  mov     edx, 44h ; 'D'; uBytes
0x1802d3559  mov     [rbp+57h+cbSid], edx
0x1802d355c  lea     ebx, [rdx-4]
0x1802d355f  mov     ecx, ebx; uFlags
0x1802d3561  call    cs:__imp_LocalAlloc
0x1802d3568  nop     dword ptr [rax+rax+00h]
0x1802d356d  mov     rdi, rax
0x1802d3570  test    rax, rax
0x1802d3573  jz      loc_1802D3766
0x1802d3579  lea     r9, [rbp+57h+cbSid]; cbSid
0x1802d357d  mov     [rbp+57h+IsMember], 0
0x1802d3584  mov     r8, rax; pSid
0x1802d3587  lea     ecx, [rbx-26h]; WellKnownSidType
0x1802d358a  xor     edx, edx; DomainSid
0x1802d358c  call    cs:__imp_CreateWellKnownSid
0x1802d3593  nop     dword ptr [rax+rax+00h]
0x1802d3598  test    eax, eax
0x1802d359a  jz      loc_1802D3783
0x1802d35a0  mov     rcx, [rbp+57h+TokenInformation]; TokenHandle
0x1802d35a4  lea     r8, [rbp+57h+IsMember]; IsMember
0x1802d35a8  mov     rdx, rdi; SidToCheck
0x1802d35ab  call    cs:__imp_CheckTokenMembership
0x1802d35b2  nop     dword ptr [rax+rax+00h]
0x1802d35b7  test    eax, eax
0x1802d35b9  jz      loc_1802D3783
0x1802d35bf  cmp     [rbp+57h+IsMember], 0
0x1802d35c3  jz      loc_1802D3779
0x1802d35c9  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1802d35cd  lea     rax, [rbp+57h+nLengthNeeded]
0x1802d35d1  xor     r9d, r9d; nLength
0x1802d35d4  mov     [rsp+0C0h+ReturnLength], rax; lpnLengthNeeded
0x1802d35d9  xor     r8d, r8d; pSecurityDescriptor
0x1802d35dc  mov     [rbp+57h+nLengthNeeded], 0
0x1802d35e3  lea     edx, [rbx-39h]; RequestedInformation
0x1802d35e6  call    cs:__imp_GetFileSecurityW
0x1802d35ed  nop     dword ptr [rax+rax+00h]
0x1802d35f2  test    eax, eax
0x1802d35f4  jnz     loc_1802D3783
0x1802d35fa  call    cs:__imp_GetLastError
0x1802d3601  nop     dword ptr [rax+rax+00h]
0x1802d3606  cmp     eax, 7Ah ; 'z'
0x1802d3609  jnz     loc_1802D3783
0x1802d360f  mov     edx, [rbp+57h+nLengthNeeded]; uBytes
0x1802d3612  mov     ecx, ebx; uFlags
0x1802d3614  call    cs:__imp_LocalAlloc
0x1802d361b  nop     dword ptr [rax+rax+00h]
0x1802d3620  mov     rsi, rax
0x1802d3623  test    rax, rax
0x1802d3626  jz      loc_1802D375F
0x1802d362c  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1802d3630  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1802d3637  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1802d363b  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1802d3642  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1802d3649  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1802d3650  call    cs:__imp_RtlMapGenericMask
0x1802d3657  nop     dword ptr [rax+rax+00h]
0x1802d365c  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1802d3660  lea     edx, [rbx-39h]; RequestedInformation
0x1802d3663  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1802d3667  xor     eax, eax
0x1802d3669  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x1802d366c  xorps   xmm0, xmm0
0x1802d366f  mov     [rbp+57h+var_58], eax
0x1802d3672  mov     r8, rsi; pSecurityDescriptor
0x1802d3675  mov     [rbp+57h+var_4C], eax
0x1802d3678  lea     rax, [rbp+57h+nLengthNeeded]
0x1802d367c  mov     [rsp+0C0h+ReturnLength], rax; lpnLengthNeeded
0x1802d3681  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x1802d3685  mov     [rbp+57h+var_48], 14h
0x1802d368c  call    cs:__imp_GetFileSecurityW
0x1802d3693  nop     dword ptr [rax+rax+00h]
0x1802d3698  test    eax, eax
0x1802d369a  jz      loc_1802D376D
0x1802d36a0  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1802d36a4  lea     rax, [rbp+57h+var_58]
0x1802d36a8  mov     rdx, [rbp+57h+TokenInformation]; ClientToken
0x1802d36ac  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1802d36b0  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x1802d36b5  mov     rcx, rsi; pSecurityDescriptor
0x1802d36b8  lea     rax, [rbp+57h+var_4C]
0x1802d36bc  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x1802d36c1  lea     rax, [rbp+57h+var_48]
0x1802d36c5  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1802d36ca  lea     rax, [rbp+57h+PrivilegeSet]
0x1802d36ce  mov     [rsp+0C0h+ReturnLength], rax; PrivilegeSet
0x1802d36d3  call    cs:__imp_AccessCheck
0x1802d36da  nop     dword ptr [rax+rax+00h]
0x1802d36df  test    eax, eax
0x1802d36e1  jz      loc_1802D376D
0x1802d36e7  xor     ebx, ebx
0x1802d36e9  cmp     [rbp+57h+var_58], ebx
0x1802d36ec  setz    bl
0x1802d36ef  mov     rcx, rsi; hMem
0x1802d36f2  call    cs:__imp_LocalFree
0x1802d36f9  nop     dword ptr [rax+rax+00h]
0x1802d36fe  mov     rcx, rdi; hMem
0x1802d3701  call    cs:__imp_LocalFree
0x1802d3708  nop     dword ptr [rax+rax+00h]
0x1802d370d  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x1802d3711  call    cs:__imp_CloseHandle
0x1802d3718  nop     dword ptr [rax+rax+00h]
0x1802d371d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1802d3721  call    cs:__imp_CloseHandle
0x1802d3728  nop     dword ptr [rax+rax+00h]
0x1802d372d  mov     rcx, [rbp+57h+lpFileName]; pv
0x1802d3731  call    cs:__imp_CoTaskMemFree
0x1802d3738  nop     dword ptr [rax+rax+00h]
0x1802d373d  mov     eax, ebx
0x1802d373f  mov     rcx, [rbp+57h+var_18]
0x1802d3743  xor     rcx, rsp; StackCookie
0x1802d3746  call    __security_check_cookie
0x1802d374b  mov     rbx, [rsp+0C0h+arg_10]
0x1802d3753  add     rsp, 0B0h
0x1802d375a  pop     rdi
0x1802d375b  pop     rsi
0x1802d375c  pop     rbp
0x1802d375d  retn
0x1802d375f  mov     ebx, 8007000Eh
0x1802d3764  jmp     short loc_1802D36FE
0x1802d3766  mov     ebx, 8007000Eh
0x1802d376b  jmp     short loc_1802D370D
0x1802d376d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802d3772  mov     ebx, eax
0x1802d3774  jmp     loc_1802D36EF
0x1802d3779  mov     ebx, 80070005h
0x1802d377e  jmp     loc_1802D36FE
0x1802d3783  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802d3788  mov     ebx, eax
0x1802d378a  jmp     loc_1802D36FE
0x1802d378f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802d3794  mov     ebx, eax
0x1802d3796  jmp     short loc_1802D371D
```
