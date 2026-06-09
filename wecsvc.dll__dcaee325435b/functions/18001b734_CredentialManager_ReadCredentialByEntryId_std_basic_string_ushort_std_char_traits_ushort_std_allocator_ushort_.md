# CredentialManager::ReadCredentialByEntryId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x18001b734`
- end: `0x18001b991`
- name: `?ReadCredentialByEntryId@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@GV?$allocator@G@std@@@3@@Z`
- size: `605`
- prototype: `__int64 __fastcall(struct _CREDENTIALW *, const WCHAR *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180016514`

## callees

- `0x18000195c`
- `0x180001976`
- `0x180002510`
- `0x1800032dc`
- `0x1800112e8`
- `0x18001b560`
- `0x18001b6fc`
- `0x18001b734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b824`
- `ADVAPI32!CredReadW` at `0x18001b785`
- `ADVAPI32!CredReadW` at `0x18001b785`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CredentialManager::ReadCredentialByEntryId(struct _CREDENTIALW *a1, const WCHAR *a2, void **a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD LastError; // ebx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-39h] BYREF
  PCREDENTIALW v12; // [rsp+30h] [rbp-29h]
  _BYTE v13[8]; // [rsp+38h] [rbp-21h] BYREF
  __int64 (__fastcall *v14)(HANDLE); // [rsp+40h] [rbp-19h]
  __int64 CurrentThreadTokenAndRevertToSelf; // [rsp+48h] [rbp-11h]
  void **pExceptionObject; // [rsp+50h] [rbp-9h] BYREF
  char v17; // [rsp+58h] [rbp-1h]
  const char *v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  __int64 v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  int v22; // [rsp+7Ch] [rbp+23h]
  int v23; // [rsp+80h] [rbp+27h]
  PCREDENTIALW Credential; // [rsp+C0h] [rbp+67h] BYREF

  Credential = a1;
  v13[0] = 0;
  v14 = RestoreAndCloseThreadToken;
  CurrentThreadTokenAndRevertToSelf = GetCurrentThreadTokenAndRevertToSelf();
  Credential = 0;
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const WCHAR **)a2;
  if ( !CredReadW(a2, 1u, 0, &Credential) )
  {
    if ( GetLastError() == 1168 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, 15084);
      }
      v17 = 0;
      v18 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
      v19 = 0;
      v20 = 0;
      v21 = 15084;
      v22 = -1;
      v23 = 345;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, LastError);
    }
    v17 = 0;
    v18 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
    v19 = 0;
    v20 = 0;
    v21 = LastError;
    v22 = -1;
    v23 = 346;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LOBYTE(v11) = 0;
  v12 = Credential;
  if ( !(unsigned __int8)IsValidCredentialBlob(Credential, v5, v6, v7, v11, ReleaseCredentialBlob) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, 13);
    }
    v17 = 0;
    v18 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
    v19 = 0;
    v20 = 0;
    v21 = 13;
    v22 = -1;
    v23 = 351;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<unsigned short>::resize(a3, (unsigned __int64)*(unsigned int *)(v9 + 32) >> 1);
  memcpy_0(*a3, Credential->CredentialBlob, Credential->CredentialBlobSize);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(&v11);
  return wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v13);
}

```

## disassembly

```asm
0x18001b734  mov     [rsp-8+Credential], rcx
0x18001b739  push    rbp
0x18001b73a  push    rbx
0x18001b73b  push    rsi
0x18001b73c  push    rdi
0x18001b73d  lea     rbp, [rsp-3Fh]
0x18001b742  sub     rsp, 98h
0x18001b749  mov     rdi, r8
0x18001b74c  mov     rbx, rdx
0x18001b74f  call    GetCurrentThreadTokenAndRevertToSelf
0x18001b754  xor     esi, esi
0x18001b756  mov     [rbp+57h+var_78], sil
0x18001b75a  lea     rcx, RestoreAndCloseThreadToken
0x18001b761  mov     [rbp+57h+var_70], rcx
0x18001b765  mov     [rbp+57h+var_68], rax
0x18001b769  mov     [rbp+57h+Credential], rsi
0x18001b76d  cmp     qword ptr [rbx+18h], 8
0x18001b772  jb      short loc_18001B777
0x18001b774  mov     rbx, [rbx]
0x18001b777  lea     r9, [rbp+57h+Credential]; Credential
0x18001b77b  xor     r8d, r8d; Flags
0x18001b77e  lea     edx, [r8+1]; Type
0x18001b782  mov     rcx, rbx; TargetName
0x18001b785  call    cs:__imp_CredReadW
0x18001b78b  test    eax, eax
0x18001b78d  jnz     loc_18001B8B1
0x18001b793  call    cs:__imp_GetLastError
0x18001b799  cmp     eax, 490h
0x18001b79e  jnz     loc_18001B824
0x18001b7a4  lea     rax, WPP_GLOBAL_Control
0x18001b7ab  mov     ebx, 3AECh
0x18001b7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7b7  cmp     rcx, rax
0x18001b7ba  jz      short loc_18001B7E0
0x18001b7bc  test    byte ptr [rcx+1Ch], 40h
0x18001b7c0  jz      short loc_18001B7E0
0x18001b7c2  cmp     byte ptr [rcx+19h], 2
0x18001b7c6  jb      short loc_18001B7E0
0x18001b7c8  mov     edx, 17h
0x18001b7cd  mov     r9d, ebx
0x18001b7d0  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b7d7  mov     rcx, [rcx+10h]
0x18001b7db  call    WPP_SF_D
0x18001b7e0  mov     [rbp+57h+var_58], sil
0x18001b7e4  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b7eb  mov     [rbp+57h+var_50], rax
0x18001b7ef  mov     [rbp+57h+var_48], rsi
0x18001b7f3  mov     [rbp+57h+var_40], rsi
0x18001b7f7  mov     [rbp+57h+var_38], ebx
0x18001b7fa  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001b801  mov     [rbp+57h+var_30], 159h
0x18001b808  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b80f  mov     [rbp+57h+pExceptionObject], rax
0x18001b813  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b81a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001b81e  call    _CxxThrowException_0
0x18001b824  call    cs:__imp_GetLastError
0x18001b82a  mov     ebx, eax
0x18001b82c  mov     eax, 507h
0x18001b831  test    ebx, ebx
0x18001b833  cmovz   ebx, eax
0x18001b836  lea     rax, WPP_GLOBAL_Control
0x18001b83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b844  cmp     rcx, rax
0x18001b847  jz      short loc_18001B86D
0x18001b849  test    byte ptr [rcx+1Ch], 40h
0x18001b84d  jz      short loc_18001B86D
0x18001b84f  cmp     byte ptr [rcx+19h], 2
0x18001b853  jb      short loc_18001B86D
0x18001b855  mov     edx, 18h
0x18001b85a  mov     r9d, ebx
0x18001b85d  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b864  mov     rcx, [rcx+10h]
0x18001b868  call    WPP_SF_D
0x18001b86d  mov     [rbp+57h+var_58], sil
0x18001b871  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b878  mov     [rbp+57h+var_50], rax
0x18001b87c  mov     [rbp+57h+var_48], rsi
0x18001b880  mov     [rbp+57h+var_40], rsi
0x18001b884  mov     [rbp+57h+var_38], ebx
0x18001b887  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001b88e  mov     [rbp+57h+var_30], 15Ah
0x18001b895  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b89c  mov     [rbp+57h+pExceptionObject], rax
0x18001b8a0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b8a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001b8ab  call    _CxxThrowException_0
0x18001b8b1  mov     rcx, [rbp+57h+Credential]
0x18001b8b5  mov     byte ptr [rbp+57h+var_90], sil
0x18001b8b9  lea     rax, ReleaseCredentialBlob
0x18001b8c0  mov     [rbp+57h+var_88], rax
0x18001b8c4  mov     [rbp+57h+var_80], rcx
0x18001b8c8  call    IsValidCredentialBlob
0x18001b8cd  test    al, al
0x18001b8cf  jnz     short loc_18001B94F
0x18001b8d1  lea     rax, WPP_GLOBAL_Control
0x18001b8d8  mov     ebx, 0Dh
0x18001b8dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8e4  cmp     rcx, rax
0x18001b8e7  jz      short loc_18001B90B
0x18001b8e9  test    byte ptr [rcx+1Ch], 40h
0x18001b8ed  jz      short loc_18001B90B
0x18001b8ef  cmp     byte ptr [rcx+19h], 2
0x18001b8f3  jb      short loc_18001B90B
0x18001b8f5  lea     edx, [rbx+0Ch]
0x18001b8f8  mov     r9d, ebx
0x18001b8fb  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b902  mov     rcx, [rcx+10h]
0x18001b906  call    WPP_SF_D
0x18001b90b  mov     [rbp+57h+var_58], sil
0x18001b90f  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b916  mov     [rbp+57h+var_50], rax
0x18001b91a  mov     [rbp+57h+var_48], rsi
0x18001b91e  mov     [rbp+57h+var_40], rsi
0x18001b922  mov     [rbp+57h+var_38], ebx
0x18001b925  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001b92c  mov     [rbp+57h+var_30], 15Fh
0x18001b933  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b93a  mov     [rbp+57h+pExceptionObject], rax
0x18001b93e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b945  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001b949  call    _CxxThrowException_0
0x18001b94f  mov     edx, [rcx+20h]
0x18001b952  shr     rdx, 1
0x18001b955  mov     rcx, rdi
0x18001b958  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001b95d  mov     rdx, [rbp+57h+Credential]
0x18001b961  mov     r8d, [rdx+20h]; Size
0x18001b965  mov     rdx, [rdx+28h]; Src
0x18001b969  mov     rcx, [rdi]; void *
0x18001b96c  call    memcpy_0
0x18001b971  nop
0x18001b972  lea     rcx, [rbp+57h+var_90]
0x18001b976  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001b97b  nop
0x18001b97c  lea     rcx, [rbp+57h+var_78]
0x18001b980  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001b985  add     rsp, 98h
0x18001b98c  pop     rdi
0x18001b98d  pop     rsi
0x18001b98e  pop     rbx
0x18001b98f  pop     rbp
0x18001b990  retn
```
