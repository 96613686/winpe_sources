# ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(ushort const *)

- ea: `0x1800097dc`
- end: `0x180009aba`
- name: `??0ImpersonateSelfWithPrivilege@@QEAA@PEBG@Z`
- size: `734`
- prototype: `ImpersonateSelfWithPrivilege *__fastcall(PHANDLE DuplicateTokenHandle, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ac28`
- `0x180012560`

## callees

- `0x180004e1c`
- `0x18000878c`
- `0x1800097dc`
- `0x18001bee0`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009825`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009963`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009825`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000994d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000994d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180009a36`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180009a36`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800098fb`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800098fb`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800098a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800098a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000982f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000982f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a40`

## pseudocode

```c
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
      v11 = byte_1800505F8;
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
      v11 = byte_1800505F8;
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
    v11 = byte_1800505F8;
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
    v11 = byte_1800505F8;
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
    v11 = byte_1800505F8;
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
    v11 = byte_1800505F8;
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
0x1800097dc  mov     [rsp-8+arg_10], rbx
0x1800097e1  push    rbp
0x1800097e2  push    rsi
0x1800097e3  push    rdi
0x1800097e4  lea     rbp, [rsp-47h]
0x1800097e9  sub     rsp, 0B0h
0x1800097f0  mov     rax, cs:__security_cookie
0x1800097f7  xor     rax, rsp
0x1800097fa  mov     [rbp+57h+var_18], rax
0x1800097fe  mov     rdi, rdx
0x180009801  mov     rbx, rcx
0x180009804  mov     [rbp+57h+var_40], rcx
0x180009808  xor     esi, esi
0x18000980a  mov     [rcx], rsi
0x18000980d  mov     [rbp+57h+TokenHandle], rsi
0x180009811  call    cs:__imp_GetCurrentThread
0x180009817  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000981b  lea     edx, [rsi+6]; DesiredAccess
0x18000981e  lea     r8d, [rsi+1]; OpenAsSelf
0x180009822  mov     rcx, rax; ThreadHandle
0x180009825  call    cs:__imp_OpenThreadToken
0x18000982b  test    eax, eax
0x18000982d  jnz     short loc_180009893
0x18000982f  call    cs:__imp_GetLastError
0x180009835  cmp     eax, 543h
0x18000983a  jz      short loc_180009887
0x18000983c  cmp     eax, 3F0h
0x180009841  jz      short loc_180009887
0x180009843  call    cs:__imp_GetLastError
0x180009849  mov     [rbp+57h+var_88], sil
0x18000984d  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009854  mov     [rbp+57h+pExceptionObject], rcx
0x180009858  lea     rcx, byte_1800505F8
0x18000985f  mov     [rbp+57h+var_80], rcx
0x180009863  mov     [rbp+57h+var_78], rsi
0x180009867  mov     [rbp+57h+var_70], rsi
0x18000986b  mov     [rbp+57h+var_68], eax
0x18000986e  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009876  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000987d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009881  call    _CxxThrowException_0
0x180009887  mov     rcx, rsi
0x18000988a  mov     [rbp+57h+TokenHandle], rcx
0x18000988e  mov     [rbx], rsi
0x180009891  jmp     short loc_180009897
0x180009893  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180009897  test    rcx, rcx
0x18000989a  jnz     short loc_1800098F3
0x18000989c  mov     ecx, 2; ImpersonationLevel
0x1800098a1  call    cs:__imp_ImpersonateSelf
0x1800098a7  test    eax, eax
0x1800098a9  jnz     loc_180009949
0x1800098af  call    cs:__imp_GetLastError
0x1800098b5  mov     [rbp+57h+var_88], sil
0x1800098b9  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800098c0  mov     [rbp+57h+pExceptionObject], rcx
0x1800098c4  lea     rcx, byte_1800505F8
0x1800098cb  mov     [rbp+57h+var_80], rcx
0x1800098cf  mov     [rbp+57h+var_78], rsi
0x1800098d3  mov     [rbp+57h+var_70], rsi
0x1800098d7  mov     [rbp+57h+var_68], eax
0x1800098da  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x1800098e2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800098e9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800098ed  call    _CxxThrowException_0
0x1800098f3  mov     r8, rbx; DuplicateTokenHandle
0x1800098f6  mov     edx, 2; ImpersonationLevel
0x1800098fb  call    cs:__imp_DuplicateToken
0x180009901  test    eax, eax
0x180009903  jnz     short loc_180009949
0x180009905  call    cs:__imp_GetLastError
0x18000990b  mov     [rbp+57h+var_88], sil
0x18000990f  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009916  mov     [rbp+57h+pExceptionObject], rcx
0x18000991a  lea     rcx, byte_1800505F8
0x180009921  mov     [rbp+57h+var_80], rcx
0x180009925  mov     [rbp+57h+var_78], rsi
0x180009929  mov     [rbp+57h+var_70], rsi
0x18000992d  mov     [rbp+57h+var_68], eax
0x180009930  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009938  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000993f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009943  call    _CxxThrowException_0
0x180009949  mov     [rbp+57h+var_50], rsi
0x18000994d  call    cs:__imp_GetCurrentThread
0x180009953  lea     r9, [rbp+57h+var_50]; TokenHandle
0x180009957  mov     edx, 20h ; ' '; DesiredAccess
0x18000995c  lea     r8d, [rdx-1Fh]; OpenAsSelf
0x180009960  mov     rcx, rax; ThreadHandle
0x180009963  call    cs:__imp_OpenThreadToken
0x180009969  test    eax, eax
0x18000996b  jnz     short loc_1800099B1
0x18000996d  call    cs:__imp_GetLastError
0x180009973  mov     [rbp+57h+var_88], sil
0x180009977  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000997e  mov     [rbp+57h+pExceptionObject], rcx
0x180009982  lea     rcx, byte_1800505F8
0x180009989  mov     [rbp+57h+var_80], rcx
0x18000998d  mov     [rbp+57h+var_78], rsi
0x180009991  mov     [rbp+57h+var_70], rsi
0x180009995  mov     [rbp+57h+var_68], eax
0x180009998  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x1800099a0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800099a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800099ab  call    _CxxThrowException_0
0x1800099b1  mov     qword ptr [rbp+57h+Luid.LowPart], rsi
0x1800099b5  lea     rdx, [rbp+57h+Luid]; lpLuid
0x1800099b9  mov     rcx, rdi; lpName
0x1800099bc  call    ?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z; User::LookupPrivilege(ushort const *,_LUID &)
0x1800099c1  test    eax, eax
0x1800099c3  jnz     short loc_180009A09
0x1800099c5  call    cs:__imp_GetLastError
0x1800099cb  mov     [rbp+57h+var_88], sil
0x1800099cf  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800099d6  mov     [rbp+57h+pExceptionObject], rcx
0x1800099da  lea     rcx, byte_1800505F8
0x1800099e1  mov     [rbp+57h+var_80], rcx
0x1800099e5  mov     [rbp+57h+var_78], rsi
0x1800099e9  mov     [rbp+57h+var_70], rsi
0x1800099ed  mov     [rbp+57h+var_68], eax
0x1800099f0  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x1800099f8  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800099ff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009a03  call    _CxxThrowException_0
0x180009a09  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x180009a10  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180009a14  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x180009a18  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x180009a1f  mov     [rsp+0C0h+ReturnLength], rsi; ReturnLength
0x180009a24  mov     [rsp+0C0h+PreviousState], rsi; PreviousState
0x180009a29  xor     r9d, r9d; BufferLength
0x180009a2c  lea     r8, [rbp+57h+NewState]; NewState
0x180009a30  xor     edx, edx; DisableAllPrivileges
0x180009a32  mov     rcx, [rbp+57h+var_50]; TokenHandle
0x180009a36  call    cs:__imp_AdjustTokenPrivileges
0x180009a3c  test    eax, eax
0x180009a3e  jnz     short loc_180009A84
0x180009a40  call    cs:__imp_GetLastError
0x180009a46  mov     [rbp+57h+var_88], sil
0x180009a4a  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009a51  mov     [rbp+57h+pExceptionObject], rcx
0x180009a55  lea     rcx, byte_1800505F8
0x180009a5c  mov     [rbp+57h+var_80], rcx
0x180009a60  mov     [rbp+57h+var_78], rsi
0x180009a64  mov     [rbp+57h+var_70], rsi
0x180009a68  mov     [rbp+57h+var_68], eax
0x180009a6b  mov     [rbp+57h+var_64], 0FFFFFFFFFFFFFFFFh
0x180009a73  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009a7a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009a7e  call    _CxxThrowException_0
0x180009a84  lea     rcx, [rbp+57h+var_50]; this
0x180009a88  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180009a8d  nop
0x180009a8e  lea     rcx, [rbp+57h+TokenHandle]; this
0x180009a92  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180009a97  nop
0x180009a98  mov     rax, rbx
0x180009a9b  mov     rcx, [rbp+57h+var_18]
0x180009a9f  xor     rcx, rsp; StackCookie
0x180009aa2  call    __security_check_cookie
0x180009aa7  mov     rbx, [rsp+0C0h+arg_10]
0x180009aaf  add     rsp, 0B0h
0x180009ab6  pop     rdi
0x180009ab7  pop     rsi
0x180009ab8  pop     rbp
0x180009ab9  retn
```
