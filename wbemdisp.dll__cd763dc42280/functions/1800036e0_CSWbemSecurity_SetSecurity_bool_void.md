# CSWbemSecurity::SetSecurity(bool &,void * &)

- ea: `0x1800036e0`
- end: `0x1800039fb`
- name: `?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z`
- size: `795`
- prototype: `__int64 __fastcall(CSWbemSecurity *__hidden this, bool *, void **)`
- caller_count: `31`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012b0`
- `0x180001e14`
- `0x180001f70`
- `0x1800023b0`
- `0x180002610`
- `0x1800028b0`
- `0x1800031b0`
- `0x180003420`
- `0x18001710c`
- `0x18001d250`
- `0x18001d490`
- `0x18001d630`
- `0x18001d830`
- `0x18001dc50`
- `0x18001e010`
- `0x18001e260`
- `0x18001f270`
- `0x1800296a0`
- `0x1800298b0`
- `0x180029a70`
- `0x180029c10`
- `0x180029d90`
- `0x180029f10`
- `0x18002a090`
- `0x18002a200`
- `0x18002a4e0`
- `0x18002a6d0`
- `0x18002abf0`
- `0x18002b880`
- `0x18002c860`
- `0x18002cb20`

## callees

- `0x180001b78`
- `0x180001d0c`
- `0x1800036e0`
- `0x180006710`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003819`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003819`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000378b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000378b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000394b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000394b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003960`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003960`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800037be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800037be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000396c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000396c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039b2`

## pseudocode

```c
__int64 __fastcall CSWbemSecurity::SetSecurity(CSWbemSecurity *this, bool *a2, void **a3)
{
  bool v4; // zf
  __int64 v7; // rcx
  __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  unsigned int v11; // edi
  HANDLE v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall **v14)(_QWORD, GUID *, __int64 *); // rax
  int v15; // r15d
  struct IUnknown *Proxy; // rsi
  __int64 v17; // rcx
  HANDLE CurrentProcess; // rdi
  BOOL v19; // r15d
  __int64 v20; // rax
  int v21; // ecx
  int v22; // [rsp+50h] [rbp-9h] BYREF
  int v23; // [rsp+54h] [rbp-5h] BYREF
  int v24; // [rsp+58h] [rbp-1h] BYREF
  int v25; // [rsp+5Ch] [rbp+3h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+7h] BYREF
  HANDLE Token; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+70h] [rbp+17h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL TokenInformation; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD ReturnLength; // [rsp+D0h] [rbp+77h] BYREF
  enum WbemAuthenticationLevelEnum v31; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = !CSWbemSecurity::s_bIsNT;
  *a3 = 0;
  *a2 = 0;
  if ( v4 )
    return 1;
  v7 = *((_QWORD *)this + 15);
  if ( v7 )
  {
    if ( *(_BYTE *)(v7 + 321) )
      return 1;
  }
  v8 = *((_QWORD *)this + 4);
  if ( !v8 )
    return 1;
  v22 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 72LL))(v8, &v22);
  if ( v22 <= 0 )
    return 1;
  TokenHandle = 0;
  TokenInformation = SecurityImpersonation;
  CurrentThread = GetCurrentThread();
  v11 = OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle);
  if ( v11 )
  {
    v12 = TokenHandle;
    *a3 = TokenHandle;
    ReturnLength = 0;
    GetTokenInformation(v12, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
LABEL_9:
    Token = 0;
    EnterCriticalSection(&g_csSecurity);
    v11 = DuplicateTokenSameAcl(TokenHandle, TokenInformation, &Token);
    LeaveCriticalSection(&g_csSecurity);
    if ( v11 && (v11 = CSWbemSecurity::AdjustTokenPrivileges(Token, *((struct CSWbemPrivilegeSet **)this + 4))) != 0 )
    {
      if ( SetThreadToken(0, Token) )
      {
        *a2 = 1;
        v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 16);
        v31 = wbemAuthenticationLevelDefault;
        ReturnLength = 0;
        if ( v13 )
        {
          v14 = *v13;
          v28 = 0;
          v15 = (*v14)(v13, &IID_IClientSecurity, &v28);
          if ( !v15 )
          {
            v25 = 0;
            v24 = 0;
            v23 = 0;
            v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int *, int *, _QWORD, enum WbemAuthenticationLevelEnum *, DWORD *, _QWORD, int *))(*(_QWORD *)v28 + 24LL))(
                    v28,
                    v13,
                    &v25,
                    &v24,
                    0,
                    &v31,
                    &ReturnLength,
                    0,
                    &v23);
            if ( v15 == -2147023150 )
            {
              v31 = wbemAuthenticationLevelNone;
              v15 = 0;
              ReturnLength = 2;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          if ( !v15 )
          {
            Proxy = CSWbemProxyCache::GetProxy(
                      *((CSWbemProxyCache **)this + 15),
                      v31,
                      (enum WbemImpersonationLevelEnum)ReturnLength,
                      1);
            if ( Proxy )
            {
              v17 = *((_QWORD *)this + 16);
              if ( v17 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              *((_QWORD *)this + 16) = Proxy;
            }
          }
        }
      }
      else
      {
        v11 = 0;
      }
      CloseHandle(Token);
    }
    else
    {
      GetLastError();
    }
    if ( !*a3 )
      CloseHandle(TokenHandle);
    return v11;
  }
  if ( GetLastError() != 1008 )
    return v11;
  CurrentProcess = GetCurrentProcess();
  v19 = OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle);
  CloseHandle(CurrentProcess);
  if ( v19 )
  {
    v20 = *(_QWORD *)this;
    ReturnLength = 0;
    (*(void (__fastcall **)(CSWbemSecurity *, DWORD *))(v20 + 56))(this, &ReturnLength);
    if ( ReturnLength == 3 )
    {
      v21 = 2;
    }
    else
    {
      v21 = 0;
      if ( ReturnLength != 1 )
      {
        if ( ReturnLength == 2 )
        {
          v21 = 1;
        }
        else if ( ReturnLength == 4 )
        {
          v21 = 3;
        }
      }
    }
    TokenInformation = v21;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800036e0  push    rbp
0x1800036e2  push    rbx
0x1800036e3  push    rsi
0x1800036e4  push    r12
0x1800036e6  push    r14
0x1800036e8  lea     rbp, [rsp-37h]
0x1800036ed  sub     rsp, 90h
0x1800036f4  xor     r12d, r12d
0x1800036f7  mov     rbx, r8
0x1800036fa  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, r12b; bool CSWbemSecurity::s_bIsNT
0x180003701  mov     rsi, rdx
0x180003704  mov     [r8], r12
0x180003707  mov     r14, rcx
0x18000370a  mov     [rdx], r12b
0x18000370d  jz      short loc_180003744
0x18000370f  mov     rcx, [rcx+78h]
0x180003713  test    rcx, rcx
0x180003716  jz      short loc_180003721
0x180003718  cmp     [rcx+141h], r12b
0x18000371f  jnz     short loc_180003744
0x180003721  mov     rcx, [r14+20h]
0x180003725  test    rcx, rcx
0x180003728  jz      short loc_180003744
0x18000372a  mov     [rbp+57h+var_60], r12d
0x18000372e  lea     rdx, [rbp+57h+var_60]
0x180003732  mov     rax, [rcx]
0x180003735  mov     rax, [rax+48h]
0x180003739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373e  cmp     [rbp+57h+var_60], r12d
0x180003742  jg      short loc_180003758
0x180003744  mov     eax, 1
0x180003749  add     rsp, 90h
0x180003750  pop     r14
0x180003752  pop     r12
0x180003754  pop     rsi
0x180003755  pop     rbx
0x180003756  pop     rbp
0x180003757  retn
0x180003758  mov     [rsp+0B0h+var_28], rdi
0x180003760  mov     [rsp+0B0h+var_30], r15
0x180003768  mov     [rbp+57h+TokenHandle], r12
0x18000376c  mov     [rbp+57h+TokenInformation], 2
0x180003773  call    cs:__imp_GetCurrentThread
0x180003779  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000377d  mov     edx, 2000Eh; DesiredAccess
0x180003782  mov     rcx, rax; ThreadHandle
0x180003785  mov     r8d, 1; OpenAsSelf
0x18000378b  call    cs:__imp_OpenThreadToken
0x180003791  mov     edi, eax
0x180003793  test    eax, eax
0x180003795  jz      loc_18000393E
0x18000379b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000379f  lea     rax, [rbp+57h+arg_10]
0x1800037a3  mov     r9d, 4; TokenInformationLength
0x1800037a9  mov     [rbx], rcx
0x1800037ac  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800037b0  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800037b5  mov     edx, 9; TokenInformationClass
0x1800037ba  mov     [rbp+57h+arg_10], r12d
0x1800037be  call    cs:__imp_GetTokenInformation
0x1800037c4  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800037cb  mov     [rbp+57h+Token], r12
0x1800037cf  call    cs:__imp_EnterCriticalSection
0x1800037d5  mov     edx, [rbp+57h+TokenInformation]; enum _SECURITY_IMPERSONATION_LEVEL
0x1800037d8  lea     r8, [rbp+57h+Token]; void **
0x1800037dc  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800037e0  call    ?DuplicateTokenSameAcl@@YAHPEAXW4_SECURITY_IMPERSONATION_LEVEL@@PEAPEAX@Z; DuplicateTokenSameAcl(void *,_SECURITY_IMPERSONATION_LEVEL,void * *)
0x1800037e5  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800037ec  mov     edi, eax
0x1800037ee  call    cs:__imp_LeaveCriticalSection
0x1800037f4  test    edi, edi
0x1800037f6  jz      loc_1800039A3
0x1800037fc  mov     rdx, [r14+20h]; struct CSWbemPrivilegeSet *
0x180003800  mov     rcx, [rbp+57h+Token]; TokenHandle
0x180003804  call    ?AdjustTokenPrivileges@CSWbemSecurity@@SAHPEAXPEAVCSWbemPrivilegeSet@@@Z; CSWbemSecurity::AdjustTokenPrivileges(void *,CSWbemPrivilegeSet *)
0x180003809  mov     edi, eax
0x18000380b  test    eax, eax
0x18000380d  jz      loc_1800039A3
0x180003813  mov     rdx, [rbp+57h+Token]; Token
0x180003817  xor     ecx, ecx; Thread
0x180003819  call    cs:__imp_SetThreadToken
0x18000381f  test    eax, eax
0x180003821  jz      loc_180003939
0x180003827  mov     byte ptr [rsi], 1
0x18000382a  mov     rsi, [r14+80h]
0x180003831  mov     [rbp+57h+arg_18], r12d
0x180003835  mov     [rbp+57h+arg_10], r12d
0x180003839  test    rsi, rsi
0x18000383c  jz      loc_18000390F
0x180003842  mov     rax, [rsi]
0x180003845  lea     r8, [rbp+57h+var_40]
0x180003849  lea     rdx, IID_IClientSecurity
0x180003850  mov     [rbp+57h+var_40], r12
0x180003854  mov     rcx, rsi
0x180003857  mov     rax, [rax]
0x18000385a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385f  mov     r15d, eax
0x180003862  test    eax, eax
0x180003864  jnz     short loc_1800038D0
0x180003866  mov     rcx, [rbp+57h+var_40]
0x18000386a  lea     rdx, [rbp+57h+var_5C]
0x18000386e  mov     [rsp+0B0h+var_70], rdx
0x180003873  lea     r9, [rbp+57h+var_58]
0x180003877  mov     [rsp+0B0h+var_78], r12
0x18000387c  lea     rdx, [rbp+57h+arg_10]
0x180003880  mov     [rsp+0B0h+var_80], rdx
0x180003885  lea     r8, [rbp+57h+var_54]
0x180003889  mov     [rbp+57h+var_54], r12d
0x18000388d  lea     rdx, [rbp+57h+arg_18]
0x180003891  mov     [rsp+0B0h+var_88], rdx
0x180003896  mov     rdx, rsi
0x180003899  mov     [rbp+57h+var_58], r12d
0x18000389d  mov     [rbp+57h+var_5C], r12d
0x1800038a1  mov     rax, [rcx]
0x1800038a4  mov     [rsp+0B0h+ReturnLength], r12
0x1800038a9  mov     rax, [rax+18h]
0x1800038ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b2  mov     r15d, eax
0x1800038b5  cmp     eax, 800706D2h
0x1800038ba  jz      loc_1800039E5
0x1800038c0  mov     rcx, [rbp+57h+var_40]
0x1800038c4  mov     rax, [rcx]
0x1800038c7  mov     rax, [rax+10h]
0x1800038cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d0  test    r15d, r15d
0x1800038d3  jnz     short loc_18000390F
0x1800038d5  mov     r8d, [rbp+57h+arg_10]; enum WbemImpersonationLevelEnum
0x1800038d9  mov     r9b, 1; bool
0x1800038dc  mov     edx, [rbp+57h+arg_18]; enum WbemAuthenticationLevelEnum
0x1800038df  mov     rcx, [r14+78h]; this
0x1800038e3  call    ?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z; CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)
0x1800038e8  mov     rsi, rax
0x1800038eb  test    rax, rax
0x1800038ee  jz      short loc_18000390F
0x1800038f0  mov     rcx, [r14+80h]
0x1800038f7  test    rcx, rcx
0x1800038fa  jz      short loc_180003908
0x1800038fc  mov     rdx, [rcx]
0x1800038ff  mov     rax, [rdx+10h]
0x180003903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003908  mov     [r14+80h], rsi
0x18000390f  mov     rcx, [rbp+57h+Token]; hObject
0x180003913  call    cs:__imp_CloseHandle
0x180003919  cmp     [rbx], r12
0x18000391c  jz      loc_1800039AE
0x180003922  mov     eax, edi
0x180003924  mov     r15, [rsp+0B0h+var_30]
0x18000392c  mov     rdi, [rsp+0B0h+var_28]
0x180003934  jmp     loc_180003749
0x180003939  mov     edi, r12d
0x18000393c  jmp     short loc_18000390F
0x18000393e  call    cs:__imp_GetLastError
0x180003944  cmp     eax, 3F0h
0x180003949  jnz     short loc_180003922
0x18000394b  call    cs:__imp_GetCurrentProcess
0x180003951  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180003955  mov     edx, 2000Ah; DesiredAccess
0x18000395a  mov     rcx, rax; ProcessHandle
0x18000395d  mov     rdi, rax
0x180003960  call    cs:__imp_OpenProcessToken
0x180003966  mov     rcx, rdi; hObject
0x180003969  mov     r15d, eax
0x18000396c  call    cs:__imp_CloseHandle
0x180003972  test    r15d, r15d
0x180003975  jz      short loc_1800039DD
0x180003977  mov     rax, [r14]
0x18000397a  lea     rdx, [rbp+57h+arg_10]
0x18000397e  mov     rcx, r14
0x180003981  mov     [rbp+57h+arg_10], r12d
0x180003985  mov     rax, [rax+38h]
0x180003989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398e  mov     edx, [rbp+57h+arg_10]
0x180003991  cmp     edx, 3
0x180003994  jnz     short loc_1800039BD
0x180003996  mov     ecx, 2
0x18000399b  mov     [rbp+57h+TokenInformation], ecx
0x18000399e  jmp     loc_1800037C4
0x1800039a3  call    cs:__imp_GetLastError
0x1800039a9  jmp     loc_180003919
0x1800039ae  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800039b2  call    cs:__imp_CloseHandle
0x1800039b8  jmp     loc_180003922
0x1800039bd  mov     ecx, r12d
0x1800039c0  sub     edx, 1
0x1800039c3  jz      short loc_18000399B
0x1800039c5  sub     edx, 1
0x1800039c8  jz      short loc_1800039D6
0x1800039ca  cmp     edx, 2
0x1800039cd  jnz     short loc_18000399B
0x1800039cf  mov     ecx, 3
0x1800039d4  jmp     short loc_18000399B
0x1800039d6  mov     ecx, 1
0x1800039db  jmp     short loc_18000399B
0x1800039dd  mov     eax, r15d
0x1800039e0  jmp     loc_180003924
0x1800039e5  mov     [rbp+57h+arg_18], 1
0x1800039ec  mov     r15d, r12d
0x1800039ef  mov     [rbp+57h+arg_10], 2
0x1800039f6  jmp     loc_1800038C0
```
