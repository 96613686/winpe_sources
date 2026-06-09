# NMP_SetSecurity(NMP_ADDRESS *,void *)

- ea: `0x180084d8c`
- end: `0x180084fea`
- name: `?NMP_SetSecurity@@YAJPEAUNMP_ADDRESS@@PEAX@Z`
- size: `606`
- prototype: `int(struct NMP_ADDRESS *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800847b0`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800283bc`
- `0x180084d8c`
- `0x18009bc2c`
- `0x1800ca031`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180084e21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180084e21`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180084e33`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180084e33`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180084f68`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180084fb3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180084f68`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180084fb3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180084eff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180084eff`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180084ec4`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180084ec4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180084f25`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180084f25`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180084ea5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180084ea5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180084dd4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180084dd4`

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
0x180084d8c  mov     [rsp-18h+arg_0], rbx
0x180084d91  push    rbp
0x180084d92  push    rsi
0x180084d93  push    rdi
0x180084d94  mov     rbp, rsp
0x180084d97  sub     rsp, 40h
0x180084d9b  xor     esi, esi
0x180084d9d  mov     rbx, rdx
0x180084da0  mov     [rbp+pControl], si
0x180084da4  mov     rdi, rcx
0x180084da7  mov     [rbp+dwRevision], esi
0x180084daa  mov     dword ptr [rbp+Size], esi
0x180084dad  test    rdx, rdx
0x180084db0  jnz     loc_180084EC1
0x180084db6  lea     ecx, [rdx+28h]; dwBytes
0x180084db9  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180084dbe  mov     [rdi+110h], rax
0x180084dc5  test    rax, rax
0x180084dc8  jz      loc_180084FA2
0x180084dce  lea     edx, [rbx+1]; dwRevision
0x180084dd1  mov     rcx, rax; pSecurityDescriptor
0x180084dd4  call    cs:__imp_InitializeSecurityDescriptor
0x180084dda  test    eax, eax
0x180084ddc  jnz     short loc_180084E1D
0x180084dde  mov     rcx, [rdi+110h]; lpMem
0x180084de5  test    rcx, rcx
0x180084de8  jz      loc_180084FA2
0x180084dee  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180084df3  mov     [rdi+110h], rsi
0x180084dfa  call    cs:__imp_GetLastError
0x180084e00  mov     r8d, 0FE6h; unsigned __int16
0x180084e06  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180084e0b  mov     edx, eax; int
0x180084e0d  lea     ecx, [rbx+2]; unsigned int
0x180084e10  xor     r9d, r9d; int
0x180084e13  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180084e18  jmp     loc_180084FA2
0x180084e1d  mov     [rbp+TokenHandle], rsi
0x180084e21  call    cs:__imp_GetCurrentProcess
0x180084e27  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180084e2b  mov     edx, 20008h; DesiredAccess
0x180084e30  mov     rcx, rax; ProcessHandle
0x180084e33  call    cs:__imp_OpenProcessToken
0x180084e39  test    eax, eax
0x180084e3b  jnz     short loc_180084E67
0x180084e3d  call    cs:__imp_GetLastError
0x180084e43  mov     r8d, 0FE7h; unsigned __int16
0x180084e49  xor     r9d, r9d; int
0x180084e4c  mov     edx, eax; int
0x180084e4e  mov     ecx, 2; unsigned int
0x180084e53  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180084e58  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180084e5d  mov     eax, 6B9h
0x180084e62  jmp     loc_180084F52
0x180084e67  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180084e6b  lea     rdx, [rbp+pDacl]; struct _ACL **
0x180084e6f  mov     [rbp+pDacl], rsi
0x180084e73  call    ?NMP_BuildDefaultDaclForPipe@@YAJPEAXPEAPEAU_ACL@@@Z; NMP_BuildDefaultDaclForPipe(void *,_ACL * *)
0x180084e78  mov     rcx, [rbp+TokenHandle]; hObject
0x180084e7c  mov     ebx, eax
0x180084e7e  call    cs:__imp_CloseHandle
0x180084e84  xor     r9d, r9d; bDaclDefaulted
0x180084e87  test    ebx, ebx
0x180084e89  jz      short loc_180084E95
0x180084e8b  mov     r8d, 0FE8h
0x180084e91  mov     edx, ebx
0x180084e93  jmp     short loc_180084E4E
0x180084e95  mov     r8, [rbp+pDacl]; pDacl
0x180084e99  mov     edx, 1; bDaclPresent
0x180084e9e  mov     rcx, [rdi+110h]; pSecurityDescriptor
0x180084ea5  call    cs:__imp_SetSecurityDescriptorDacl
0x180084eab  test    eax, eax
0x180084ead  jnz     loc_180084F50
0x180084eb3  call    cs:__imp_GetLastError
0x180084eb9  mov     r8d, 0FEAh
0x180084ebf  jmp     short loc_180084E49
0x180084ec1  mov     rcx, rbx; pSecurityDescriptor
0x180084ec4  call    cs:__imp_IsValidSecurityDescriptor
0x180084eca  test    eax, eax
0x180084ecc  jnz     short loc_180084EF4
0x180084ece  call    cs:__imp_GetLastError
0x180084ed4  mov     r8d, 0FEBh; unsigned __int16
0x180084eda  xor     r9d, r9d; int
0x180084edd  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180084ee2  mov     edx, eax; int
0x180084ee4  lea     ecx, [r9+2]; unsigned int
0x180084ee8  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180084eed  mov     eax, 53Ah
0x180084ef2  jmp     short loc_180084F52
0x180084ef4  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180084ef8  mov     rcx, rbx; pSecurityDescriptor
0x180084efb  lea     rdx, [rbp+pControl]; pControl
0x180084eff  call    cs:__imp_GetSecurityDescriptorControl
0x180084f05  test    eax, eax
0x180084f07  jnz     short loc_180084F17
0x180084f09  call    cs:__imp_GetLastError
0x180084f0f  mov     r8d, 0FECh
0x180084f15  jmp     short loc_180084EDA
0x180084f17  mov     eax, 8000h
0x180084f1c  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180084f1f  test    [rbp+pControl], ax
0x180084f23  jz      short loc_180084F5F
0x180084f25  call    cs:__imp_GetSecurityDescriptorLength
0x180084f2b  mov     ecx, eax; dwBytes
0x180084f2d  mov     dword ptr [rbp+Size], ecx
0x180084f30  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180084f35  mov     [rdi+110h], rax
0x180084f3c  test    rax, rax
0x180084f3f  jz      short loc_180084FA2
0x180084f41  mov     r8d, dword ptr [rbp+Size]; Size
0x180084f45  mov     rdx, rbx; Src
0x180084f48  mov     rcx, rax; void *
0x180084f4b  call    memcpy_0
0x180084f50  xor     eax, eax
0x180084f52  mov     rbx, [rsp+40h+arg_0]
0x180084f57  add     rsp, 40h
0x180084f5b  pop     rdi
0x180084f5c  pop     rsi
0x180084f5d  pop     rbp
0x180084f5e  retn
0x180084f5f  lea     r8, [rbp+Size]; lpdwBufferLength
0x180084f63  mov     dword ptr [rbp+Size], esi
0x180084f66  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180084f68  call    cs:__imp_MakeSelfRelativeSD
0x180084f6e  call    cs:__imp_GetLastError
0x180084f74  cmp     eax, 7Ah ; 'z'
0x180084f77  jz      short loc_180084F8A
0x180084f79  call    cs:__imp_GetLastError
0x180084f7f  mov     r8d, 0FEDh
0x180084f85  jmp     loc_180084EDA
0x180084f8a  mov     ecx, dword ptr [rbp+Size]
0x180084f8d  add     rcx, 14h; dwBytes
0x180084f91  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180084f96  mov     [rdi+110h], rax
0x180084f9d  test    rax, rax
0x180084fa0  jnz     short loc_180084FA9
0x180084fa2  mov     eax, 0Eh
0x180084fa7  jmp     short loc_180084F52
0x180084fa9  lea     r8, [rbp+Size]; lpdwBufferLength
0x180084fad  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180084fb0  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180084fb3  call    cs:__imp_MakeSelfRelativeSD
0x180084fb9  test    eax, eax
0x180084fbb  jnz     short loc_180084F50
0x180084fbd  call    cs:__imp_GetLastError
0x180084fc3  xor     r9d, r9d; int
0x180084fc6  mov     [rsp+40h+var_20], rsi; struct tagParam *
0x180084fcb  mov     r8d, 0FEEh; unsigned __int16
0x180084fd1  mov     edx, eax; int
0x180084fd3  lea     ecx, [r9+2]; unsigned int
0x180084fd7  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180084fdc  mov     rcx, [rdi+110h]; lpMem
0x180084fe3  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180084fe8  jmp     short loc_180084FA2
```
