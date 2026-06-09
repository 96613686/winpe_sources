# NMP_SetSecurity(NMP_ADDRESS *,void *)

- ea: `0x180086ca4`
- end: `0x180086f76`
- name: `?NMP_SetSecurity@@YAJPEAUNMP_ADDRESS@@PEAX@Z`
- size: `722`
- prototype: `int(struct NMP_ADDRESS *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086690`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x180086ca4`
- `0x18009f514`
- `0x1800cec91`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086db4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180086d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180086d45`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180086d5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180086d5d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180086ed2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180086f2f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180086ed2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180086f2f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180086e56`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180086e56`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180086e0f`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180086e0f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180086e88`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180086e88`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180086de1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180086de1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180086cec`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180086cec`

## pseudocode

```c
__int64 __fastcall NMP_SetSecurity(struct NMP_ADDRESS *a1, void *a2)
{
  void *v4; // rax
  void *v5; // rcx
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v8; // eax
  unsigned __int16 v9; // r8
  int v10; // edx
  int v12; // ebx
  DWORD v13; // eax
  unsigned __int16 v14; // r8
  void *v15; // rax
  void *v16; // rax
  DWORD v17; // eax
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-8h] BYREF
  WORD pControl; // [rsp+68h] [rbp+28h] BYREF
  size_t Size; // [rsp+70h] [rbp+30h] BYREF
  DWORD dwRevision; // [rsp+78h] [rbp+38h] BYREF

  pControl = 0;
  dwRevision = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
  {
    v4 = AllocWrapper(0x28u);
    *((_QWORD *)a1 + 34) = v4;
    if ( v4 )
    {
      if ( !InitializeSecurityDescriptor(v4, 1u) )
      {
        v5 = (void *)*((_QWORD *)a1 + 34);
        if ( v5 )
        {
          FreeWrapper(v5);
          *((_QWORD *)a1 + 34) = 0;
          LastError = GetLastError();
          RpcpErrorAddRecord(2u, LastError, 0xFE6u, 0, 0);
        }
        return 14;
      }
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
      {
        v8 = GetLastError();
        v9 = 4071;
LABEL_8:
        v10 = v8;
LABEL_9:
        RpcpErrorAddRecord(2u, v10, v9, 0, 0);
        return 1721;
      }
      pDacl = 0;
      v12 = NMP_BuildDefaultDaclForPipe(TokenHandle, &pDacl);
      CloseHandle(TokenHandle);
      if ( v12 )
      {
        v9 = 4072;
        v10 = v12;
        goto LABEL_9;
      }
      if ( !SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)a1 + 34), 1, pDacl, 0) )
      {
        v8 = GetLastError();
        v9 = 4074;
        goto LABEL_8;
      }
      return 0;
    }
    return 14;
  }
  if ( !IsValidSecurityDescriptor(a2) )
  {
    v13 = GetLastError();
    v14 = 4075;
    goto LABEL_16;
  }
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    v13 = GetLastError();
    v14 = 4076;
    goto LABEL_16;
  }
  if ( (pControl & 0x8000u) == 0 )
  {
    LODWORD(Size) = 0;
    MakeSelfRelativeSD(a2, 0, (LPDWORD)&Size);
    if ( GetLastError() == 122 )
    {
      v16 = AllocWrapper((unsigned int)Size + 20LL);
      *((_QWORD *)a1 + 34) = v16;
      if ( v16 )
      {
        if ( MakeSelfRelativeSD(a2, v16, (LPDWORD)&Size) )
          return 0;
        v17 = GetLastError();
        RpcpErrorAddRecord(2u, v17, 0xFEEu, 0, 0);
        FreeWrapper(*((void **)a1 + 34));
      }
      return 14;
    }
    v13 = GetLastError();
    v14 = 4077;
LABEL_16:
    RpcpErrorAddRecord(2u, v13, v14, 0, 0);
    return 1338;
  }
  LODWORD(Size) = GetSecurityDescriptorLength(a2);
  v15 = AllocWrapper((unsigned int)Size);
  *((_QWORD *)a1 + 34) = v15;
  if ( v15 )
  {
    memcpy_0(v15, a2, (unsigned int)Size);
    return 0;
  }
  return 14;
}

```

## disassembly

```asm
0x180086ca4  mov     [rsp-18h+arg_0], rbx
0x180086ca9  push    rbp
0x180086caa  push    rsi
0x180086cab  push    rdi
0x180086cac  mov     rbp, rsp
0x180086caf  sub     rsp, 40h
0x180086cb3  xor     esi, esi
0x180086cb5  mov     rbx, rdx
0x180086cb8  mov     [rbp+pControl], si
0x180086cbc  mov     rdi, rcx
0x180086cbf  mov     [rbp+dwRevision], esi
0x180086cc2  mov     dword ptr [rbp+Size], esi
0x180086cc5  test    rdx, rdx
0x180086cc8  jnz     loc_180086E0C
0x180086cce  lea     ecx, [rdx+28h]; dwBytes
0x180086cd1  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180086cd6  mov     [rdi+110h], rax
0x180086cdd  test    rax, rax
0x180086ce0  jz      loc_180086F1E
0x180086ce6  lea     edx, [rbx+1]; dwRevision
0x180086ce9  mov     rcx, rax; pSecurityDescriptor
0x180086cec  call    cs:__imp_InitializeSecurityDescriptor
0x180086cf3  nop     dword ptr [rax+rax+00h]
0x180086cf8  test    eax, eax
0x180086cfa  jnz     short loc_180086D41
0x180086cfc  mov     rcx, [rdi+110h]; lpMem
0x180086d03  test    rcx, rcx
0x180086d06  jz      loc_180086F1E
0x180086d0c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180086d11  mov     [rdi+110h], rsi
0x180086d18  call    cs:__imp_GetLastError
0x180086d1f  nop     dword ptr [rax+rax+00h]
0x180086d24  mov     r8d, 0FE6h; unsigned __int16
0x180086d2a  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180086d2f  mov     edx, eax; int
0x180086d31  lea     ecx, [rbx+2]; unsigned int
0x180086d34  xor     r9d, r9d; int
0x180086d37  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180086d3c  jmp     loc_180086F1E
0x180086d41  mov     [rbp+TokenHandle], rsi
0x180086d45  call    cs:__imp_GetCurrentProcess
0x180086d4c  nop     dword ptr [rax+rax+00h]
0x180086d51  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180086d55  mov     edx, 20008h; DesiredAccess
0x180086d5a  mov     rcx, rax; ProcessHandle
0x180086d5d  call    cs:__imp_OpenProcessToken
0x180086d64  nop     dword ptr [rax+rax+00h]
0x180086d69  test    eax, eax
0x180086d6b  jnz     short loc_180086D9D
0x180086d6d  call    cs:__imp_GetLastError
0x180086d74  nop     dword ptr [rax+rax+00h]
0x180086d79  mov     r8d, 0FE7h; unsigned __int16
0x180086d7f  xor     r9d, r9d; int
0x180086d82  mov     edx, eax; int
0x180086d84  mov     ecx, 2; unsigned int
0x180086d89  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180086d8e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180086d93  mov     eax, 6B9h
0x180086d98  jmp     loc_180086EBB
0x180086d9d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180086da1  lea     rdx, [rbp+pDacl]; struct _ACL **
0x180086da5  mov     [rbp+pDacl], rsi
0x180086da9  call    ?NMP_BuildDefaultDaclForPipe@@YAJPEAXPEAPEAU_ACL@@@Z; NMP_BuildDefaultDaclForPipe(void *,_ACL * *)
0x180086dae  mov     rcx, [rbp+TokenHandle]; hObject
0x180086db2  mov     ebx, eax
0x180086db4  call    cs:__imp_CloseHandle
0x180086dbb  nop     dword ptr [rax+rax+00h]
0x180086dc0  xor     r9d, r9d; bDaclDefaulted
0x180086dc3  test    ebx, ebx
0x180086dc5  jz      short loc_180086DD1
0x180086dc7  mov     r8d, 0FE8h
0x180086dcd  mov     edx, ebx
0x180086dcf  jmp     short loc_180086D84
0x180086dd1  mov     r8, [rbp+pDacl]; pDacl
0x180086dd5  mov     edx, 1; bDaclPresent
0x180086dda  mov     rcx, [rdi+110h]; pSecurityDescriptor
0x180086de1  call    cs:__imp_SetSecurityDescriptorDacl
0x180086de8  nop     dword ptr [rax+rax+00h]
0x180086ded  test    eax, eax
0x180086def  jnz     loc_180086EB9
0x180086df5  call    cs:__imp_GetLastError
0x180086dfc  nop     dword ptr [rax+rax+00h]
0x180086e01  mov     r8d, 0FEAh
0x180086e07  jmp     loc_180086D7F
0x180086e0c  mov     rcx, rbx; pSecurityDescriptor
0x180086e0f  call    cs:__imp_IsValidSecurityDescriptor
0x180086e16  nop     dword ptr [rax+rax+00h]
0x180086e1b  test    eax, eax
0x180086e1d  jnz     short loc_180086E4B
0x180086e1f  call    cs:__imp_GetLastError
0x180086e26  nop     dword ptr [rax+rax+00h]
0x180086e2b  mov     r8d, 0FEBh; unsigned __int16
0x180086e31  xor     r9d, r9d; int
0x180086e34  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180086e39  mov     edx, eax; int
0x180086e3b  lea     ecx, [r9+2]; unsigned int
0x180086e3f  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180086e44  mov     eax, 53Ah
0x180086e49  jmp     short loc_180086EBB
0x180086e4b  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180086e4f  mov     rcx, rbx; pSecurityDescriptor
0x180086e52  lea     rdx, [rbp+pControl]; pControl
0x180086e56  call    cs:__imp_GetSecurityDescriptorControl
0x180086e5d  nop     dword ptr [rax+rax+00h]
0x180086e62  test    eax, eax
0x180086e64  jnz     short loc_180086E7A
0x180086e66  call    cs:__imp_GetLastError
0x180086e6d  nop     dword ptr [rax+rax+00h]
0x180086e72  mov     r8d, 0FECh
0x180086e78  jmp     short loc_180086E31
0x180086e7a  mov     eax, 8000h
0x180086e7f  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180086e82  test    [rbp+pControl], ax
0x180086e86  jz      short loc_180086EC9
0x180086e88  call    cs:__imp_GetSecurityDescriptorLength
0x180086e8f  nop     dword ptr [rax+rax+00h]
0x180086e94  mov     ecx, eax; dwBytes
0x180086e96  mov     dword ptr [rbp+Size], ecx
0x180086e99  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180086e9e  mov     [rdi+110h], rax
0x180086ea5  test    rax, rax
0x180086ea8  jz      short loc_180086F1E
0x180086eaa  mov     r8d, dword ptr [rbp+Size]; Size
0x180086eae  mov     rdx, rbx; Src
0x180086eb1  mov     rcx, rax; void *
0x180086eb4  call    memcpy_0
0x180086eb9  xor     eax, eax
0x180086ebb  mov     rbx, [rsp+40h+arg_0]
0x180086ec0  add     rsp, 40h
0x180086ec4  pop     rdi
0x180086ec5  pop     rsi
0x180086ec6  pop     rbp
0x180086ec7  retn
0x180086ec9  lea     r8, [rbp+Size]; lpdwBufferLength
0x180086ecd  mov     dword ptr [rbp+Size], esi
0x180086ed0  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180086ed2  call    cs:__imp_MakeSelfRelativeSD
0x180086ed9  nop     dword ptr [rax+rax+00h]
0x180086ede  call    cs:__imp_GetLastError
0x180086ee5  nop     dword ptr [rax+rax+00h]
0x180086eea  cmp     eax, 7Ah ; 'z'
0x180086eed  jz      short loc_180086F06
0x180086eef  call    cs:__imp_GetLastError
0x180086ef6  nop     dword ptr [rax+rax+00h]
0x180086efb  mov     r8d, 0FEDh
0x180086f01  jmp     loc_180086E31
0x180086f06  mov     ecx, dword ptr [rbp+Size]
0x180086f09  add     rcx, 14h; dwBytes
0x180086f0d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180086f12  mov     [rdi+110h], rax
0x180086f19  test    rax, rax
0x180086f1c  jnz     short loc_180086F25
0x180086f1e  mov     eax, 0Eh
0x180086f23  jmp     short loc_180086EBB
0x180086f25  lea     r8, [rbp+Size]; lpdwBufferLength
0x180086f29  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180086f2c  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180086f2f  call    cs:__imp_MakeSelfRelativeSD
0x180086f36  nop     dword ptr [rax+rax+00h]
0x180086f3b  test    eax, eax
0x180086f3d  jnz     loc_180086EB9
0x180086f43  call    cs:__imp_GetLastError
0x180086f4a  nop     dword ptr [rax+rax+00h]
0x180086f4f  xor     r9d, r9d; int
0x180086f52  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180086f57  mov     r8d, 0FEEh; unsigned __int16
0x180086f5d  mov     edx, eax; int
0x180086f5f  lea     ecx, [r9+2]; unsigned int
0x180086f63  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180086f68  mov     rcx, [rdi+110h]; lpMem
0x180086f6f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180086f74  jmp     short loc_180086F1E
```
