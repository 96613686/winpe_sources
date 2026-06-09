# ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(ushort const *)

- ea: `0x180009ccc`
- end: `0x180009fff`
- name: `??0ImpersonateSelfWithPrivilege@@QEAA@PEBG@Z`
- size: `819`
- prototype: `ImpersonateSelfWithPrivilege *__fastcall(PHANDLE DuplicateTokenHandle, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b218`
- `0x1800130c0`

## callees

- `0x180005094`
- `0x180008c4c`
- `0x180009ccc`
- `0x18001d404`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009d1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009e89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009d1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009e6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009e6d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180009f6e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180009f6e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180009e0f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180009e0f`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180009da9`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180009da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
ImpersonateSelfWithPrivilege *__fastcall ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(
        PHANDLE DuplicateTokenHandle,
        LPCWSTR lpName)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v6; // rcx
  HANDLE v7; // rax
  void **pExceptionObject; // [rsp+30h] [rbp-39h] BYREF
  char v10; // [rsp+38h] [rbp-31h]
  char *v11; // [rsp+40h] [rbp-29h]
  __int64 v12; // [rsp+48h] [rbp-21h]
  __int64 v13; // [rsp+50h] [rbp-19h]
  DWORD v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+5Ch] [rbp-Dh]
  void *TokenHandle; // [rsp+68h] [rbp-1h] BYREF
  HANDLE v17; // [rsp+70h] [rbp+7h] BYREF
  struct _LUID Luid; // [rsp+78h] [rbp+Fh] BYREF
  PHANDLE v19; // [rsp+80h] [rbp+17h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+88h] [rbp+1Fh] BYREF

  v19 = DuplicateTokenHandle;
  *DuplicateTokenHandle = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle) )
  {
    v6 = TokenHandle;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1347 && LastError != 1008 )
    {
      v10 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v11 = byte_180052608;
      v12 = 0;
      v13 = 0;
      v14 = GetLastError();
      v15 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v6 = 0;
    TokenHandle = 0;
    *DuplicateTokenHandle = 0;
  }
  if ( v6 )
  {
    if ( !DuplicateToken(v6, SecurityImpersonation, DuplicateTokenHandle) )
    {
      v10 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v11 = byte_180052608;
      v12 = 0;
      v13 = 0;
      v14 = GetLastError();
      v15 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  else if ( !ImpersonateSelf(SecurityImpersonation) )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = byte_180052608;
    v12 = 0;
    v13 = 0;
    v14 = GetLastError();
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v17 = 0;
  v7 = GetCurrentThread();
  if ( !OpenThreadToken(v7, 0x20u, 1, &v17) )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = byte_180052608;
    v12 = 0;
    v13 = 0;
    v14 = GetLastError();
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  Luid = 0;
  if ( !(unsigned int)User::LookupPrivilege(lpName, &Luid) )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = byte_180052608;
    v12 = 0;
    v13 = 0;
    v14 = GetLastError();
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = Luid;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(v17, 0, &NewState, 0, 0, 0) )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = byte_180052608;
    v12 = 0;
    v13 = 0;
    v14 = GetLastError();
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  wmi::AutoHandle::Close((wmi::AutoHandle *)&v17);
  wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
  return (ImpersonateSelfWithPrivilege *)DuplicateTokenHandle;
}

```

## disassembly

```asm
0x180009ccc  mov     [rsp-8+arg_10], rbx
0x180009cd1  push    rbp
0x180009cd2  push    rsi
0x180009cd3  push    rdi
0x180009cd4  lea     rbp, [rsp-47h]
0x180009cd9  sub     rsp, 0B0h
0x180009ce0  mov     rax, cs:__security_cookie
0x180009ce7  xor     rax, rsp
0x180009cea  mov     [rbp+57h+var_18], rax
0x180009cee  mov     rdi, rdx
0x180009cf1  mov     rbx, rcx
0x180009cf4  mov     [rbp+57h+var_40], rcx
0x180009cf8  xor     esi, esi
0x180009cfa  mov     [rcx], rsi
0x180009cfd  mov     [rbp+57h+TokenHandle], rsi
0x180009d01  call    cs:__imp_GetCurrentThread
0x180009d08  nop     dword ptr [rax+rax+00h]
0x180009d0d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180009d11  lea     edx, [rsi+6]; DesiredAccess
0x180009d14  lea     r8d, [rsi+1]; OpenAsSelf
0x180009d18  mov     rcx, rax; ThreadHandle
0x180009d1b  call    cs:__imp_OpenThreadToken
0x180009d22  nop     dword ptr [rax+rax+00h]
0x180009d27  test    eax, eax
0x180009d29  jnz     short loc_180009D9B
0x180009d2b  call    cs:__imp_GetLastError
0x180009d32  nop     dword ptr [rax+rax+00h]
0x180009d37  cmp     eax, 543h
0x180009d3c  jz      short loc_180009D8F
0x180009d3e  cmp     eax, 3F0h
0x180009d43  jz      short loc_180009D8F
0x180009d45  call    cs:__imp_GetLastError
0x180009d4c  nop     dword ptr [rax+rax+00h]
0x180009d51  mov     [rbp+57h+var_88], sil
0x180009d55  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009d5c  mov     [rbp+57h+pExceptionObject], rcx
0x180009d60  lea     rcx, byte_180052608
0x180009d67  mov     [rbp+57h+var_80], rcx
0x180009d6b  mov     [rbp+57h+var_78], rsi
0x180009d6f  mov     [rbp+57h+var_70], rsi
0x180009d73  mov     [rbp+57h+var_68], eax
0x180009d76  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009d7e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009d85  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009d89  call    _CxxThrowException_0
0x180009d8f  mov     rcx, rsi
0x180009d92  mov     [rbp+57h+TokenHandle], rcx
0x180009d96  mov     [rbx], rsi
0x180009d99  jmp     short loc_180009D9F
0x180009d9b  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180009d9f  test    rcx, rcx
0x180009da2  jnz     short loc_180009E07
0x180009da4  mov     ecx, 2; ImpersonationLevel
0x180009da9  call    cs:__imp_ImpersonateSelf
0x180009db0  nop     dword ptr [rax+rax+00h]
0x180009db5  test    eax, eax
0x180009db7  jnz     loc_180009E69
0x180009dbd  call    cs:__imp_GetLastError
0x180009dc4  nop     dword ptr [rax+rax+00h]
0x180009dc9  mov     [rbp+57h+var_88], sil
0x180009dcd  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009dd4  mov     [rbp+57h+pExceptionObject], rcx
0x180009dd8  lea     rcx, byte_180052608
0x180009ddf  mov     [rbp+57h+var_80], rcx
0x180009de3  mov     [rbp+57h+var_78], rsi
0x180009de7  mov     [rbp+57h+var_70], rsi
0x180009deb  mov     [rbp+57h+var_68], eax
0x180009dee  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009df6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009dfd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009e01  call    _CxxThrowException_0
0x180009e07  mov     r8, rbx; DuplicateTokenHandle
0x180009e0a  mov     edx, 2; ImpersonationLevel
0x180009e0f  call    cs:__imp_DuplicateToken
0x180009e16  nop     dword ptr [rax+rax+00h]
0x180009e1b  test    eax, eax
0x180009e1d  jnz     short loc_180009E69
0x180009e1f  call    cs:__imp_GetLastError
0x180009e26  nop     dword ptr [rax+rax+00h]
0x180009e2b  mov     [rbp+57h+var_88], sil
0x180009e2f  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009e36  mov     [rbp+57h+pExceptionObject], rcx
0x180009e3a  lea     rcx, byte_180052608
0x180009e41  mov     [rbp+57h+var_80], rcx
0x180009e45  mov     [rbp+57h+var_78], rsi
0x180009e49  mov     [rbp+57h+var_70], rsi
0x180009e4d  mov     [rbp+57h+var_68], eax
0x180009e50  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009e58  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009e5f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009e63  call    _CxxThrowException_0
0x180009e69  mov     [rbp+57h+var_50], rsi
0x180009e6d  call    cs:__imp_GetCurrentThread
0x180009e74  nop     dword ptr [rax+rax+00h]
0x180009e79  lea     r9, [rbp+57h+var_50]; TokenHandle
0x180009e7d  mov     edx, 20h ; ' '; DesiredAccess
0x180009e82  lea     r8d, [rdx-1Fh]; OpenAsSelf
0x180009e86  mov     rcx, rax; ThreadHandle
0x180009e89  call    cs:__imp_OpenThreadToken
0x180009e90  nop     dword ptr [rax+rax+00h]
0x180009e95  test    eax, eax
0x180009e97  jnz     short loc_180009EE3
0x180009e99  call    cs:__imp_GetLastError
0x180009ea0  nop     dword ptr [rax+rax+00h]
0x180009ea5  mov     [rbp+57h+var_88], sil
0x180009ea9  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009eb0  mov     [rbp+57h+pExceptionObject], rcx
0x180009eb4  lea     rcx, byte_180052608
0x180009ebb  mov     [rbp+57h+var_80], rcx
0x180009ebf  mov     [rbp+57h+var_78], rsi
0x180009ec3  mov     [rbp+57h+var_70], rsi
0x180009ec7  mov     [rbp+57h+var_68], eax
0x180009eca  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009ed2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009ed9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009edd  call    _CxxThrowException_0
0x180009ee3  mov     qword ptr [rbp+57h+Luid.LowPart], rsi
0x180009ee7  lea     rdx, [rbp+57h+Luid]; lpLuid
0x180009eeb  mov     rcx, rdi; lpName
0x180009eee  call    ?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z; User::LookupPrivilege(ushort const *,_LUID &)
0x180009ef3  test    eax, eax
0x180009ef5  jnz     short loc_180009F41
0x180009ef7  call    cs:__imp_GetLastError
0x180009efe  nop     dword ptr [rax+rax+00h]
0x180009f03  mov     [rbp+57h+var_88], sil
0x180009f07  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009f0e  mov     [rbp+57h+pExceptionObject], rcx
0x180009f12  lea     rcx, byte_180052608
0x180009f19  mov     [rbp+57h+var_80], rcx
0x180009f1d  mov     [rbp+57h+var_78], rsi
0x180009f21  mov     [rbp+57h+var_70], rsi
0x180009f25  mov     [rbp+57h+var_68], eax
0x180009f28  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009f30  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009f37  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009f3b  call    _CxxThrowException_0
0x180009f41  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x180009f48  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180009f4c  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x180009f50  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x180009f57  mov     [rsp+0C0h+ReturnLength], rsi; ReturnLength
0x180009f5c  mov     [rsp+0C0h+PreviousState], rsi; PreviousState
0x180009f61  xor     r9d, r9d; BufferLength
0x180009f64  lea     r8, [rbp+57h+NewState]; NewState
0x180009f68  xor     edx, edx; DisableAllPrivileges
0x180009f6a  mov     rcx, [rbp+57h+var_50]; TokenHandle
0x180009f6e  call    cs:__imp_AdjustTokenPrivileges
0x180009f75  nop     dword ptr [rax+rax+00h]
0x180009f7a  test    eax, eax
0x180009f7c  jnz     short loc_180009FC8
0x180009f7e  call    cs:__imp_GetLastError
0x180009f85  nop     dword ptr [rax+rax+00h]
0x180009f8a  mov     [rbp+57h+var_88], sil
0x180009f8e  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009f95  mov     [rbp+57h+pExceptionObject], rcx
0x180009f99  lea     rcx, byte_180052608
0x180009fa0  mov     [rbp+57h+var_80], rcx
0x180009fa4  mov     [rbp+57h+var_78], rsi
0x180009fa8  mov     [rbp+57h+var_70], rsi
0x180009fac  mov     [rbp+57h+var_68], eax
0x180009faf  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009fb7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009fbe  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009fc2  call    _CxxThrowException_0
0x180009fc8  lea     rcx, [rbp+57h+var_50]; this
0x180009fcc  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180009fd1  nop
0x180009fd2  lea     rcx, [rbp+57h+TokenHandle]; this
0x180009fd6  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180009fdb  nop
0x180009fdc  mov     rax, rbx
0x180009fdf  mov     rcx, [rbp+57h+var_18]
0x180009fe3  xor     rcx, rsp; StackCookie
0x180009fe6  call    __security_check_cookie
0x180009feb  mov     rbx, [rsp+0C0h+arg_10]
0x180009ff3  add     rsp, 0B0h
0x180009ffa  pop     rdi
0x180009ffb  pop     rsi
0x180009ffc  pop     rbp
0x180009ffd  retn
```
