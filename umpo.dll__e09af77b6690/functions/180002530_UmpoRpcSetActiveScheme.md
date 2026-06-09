# UmpoRpcSetActiveScheme

- ea: `0x180002530`
- end: `0x1800027ce`
- name: `UmpoRpcSetActiveScheme`
- size: `670`
- prototype: `__int64 __fastcall(void *, UUID *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012a0`
- `0x180001980`
- `0x180002530`
- `0x180002bc0`
- `0x1800034c0`
- `0x1800036f0`
- `0x180004b80`
- `0x18000d080`
- `0x18000f3dc`
- `0x180010070`
- `0x1800188bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002794`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000266f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000266f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000265a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000265a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000273d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000273d`
- `RPCRT4!RpcRevertToSelf` at `0x1800027c3`
- `RPCRT4!RpcRevertToSelf` at `0x1800027c3`
- `RPCRT4!RpcImpersonateClient` at `0x18000264b`
- `RPCRT4!RpcImpersonateClient` at `0x18000264b`

## pseudocode

```c
__int64 __fastcall UmpoRpcSetActiveScheme(void *a1, UUID *a2, int a3)
{
  char v6; // r15
  unsigned int ActiveScheme; // ebx
  __int64 v8; // rdx
  char v9; // di
  char v10; // r14
  DWORD v11; // eax
  __int64 v12; // rdx
  HANDLE CurrentThread; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-40h] BYREF
  UUID Buf2; // [rsp+30h] [rbp-30h] BYREF
  UUID Buf1; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  Buf1 = 0;
  Buf2 = 0;
  v6 = 0;
  if ( UmpoIsClientLocal() )
  {
    if ( a3 )
    {
      if ( a2 )
      {
LABEL_4:
        ActiveScheme = 87;
        goto LABEL_23;
      }
    }
    else if ( !a2 )
    {
      goto LABEL_4;
    }
    if ( UmpoPowerPolicyInitialized )
    {
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      EnterCriticalSection(&UmpoSchemeLock);
      ActiveScheme = UmpoGetActiveScheme(&Buf1, v8);
      if ( !ActiveScheme )
      {
        if ( a3 )
          Buf2 = Buf1;
        else
          Buf2 = *a2;
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          v9 = 1;
          v10 = 0;
        }
        else
        {
          v9 = 0;
          v10 = 1;
        }
        v11 = UmpoRpcSettingAccessCheck(0, 0x13u, 0, 0x20006u);
        ActiveScheme = v11;
        if ( v11 == 1260 )
        {
          if ( v9 && !a3 )
            ActiveScheme = 0;
        }
        else if ( !v11 )
        {
          if ( v9 || memcmp_0(&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE, &Buf2, 0x10u) || UmpoUltimatePerfSchemeAllowed )
          {
            LOBYTE(v12) = v10;
            ActiveScheme = UmpoSetActiveScheme(&Buf2, v12);
            if ( !ActiveScheme )
            {
              ActiveScheme = RpcImpersonateClient(0);
              if ( !ActiveScheme )
              {
                v6 = 1;
                CurrentThread = GetCurrentThread();
                if ( OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
                {
                  ActiveScheme = UmpoNotifyKernelAllPowerPolicyChanged(TokenHandle, v14);
                  if ( !ActiveScheme )
                  {
                    if ( !v9 )
                      UmpoNotifyKernelNonDefaultPpmProfileSettings(v16, v15);
                    UmpoPowerPolicyChanged(a1, (__int64)&Buf1, (__int64)&Buf2, 0);
                  }
                }
                else
                {
                  TokenHandle = 0;
                  ActiveScheme = GetLastError();
                }
              }
            }
          }
          else
          {
            ActiveScheme = 50;
          }
        }
      }
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      LeaveCriticalSection(&UmpoSchemeLock);
    }
    else
    {
      ActiveScheme = 21;
    }
  }
  else
  {
    ActiveScheme = 5;
  }
LABEL_23:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 )
    RpcRevertToSelf();
  return ActiveScheme;
}

```

## disassembly

```asm
0x180002530  mov     [rsp-28h+arg_10], rbx
0x180002535  mov     [rsp-28h+arg_18], rsi
0x18000253a  push    rbp
0x18000253b  push    rdi
0x18000253c  push    r12
0x18000253e  push    r14
0x180002540  push    r15
0x180002542  mov     rbp, rsp
0x180002545  sub     rsp, 60h
0x180002549  mov     rax, cs:__security_cookie
0x180002550  xor     rax, rsp
0x180002553  mov     [rbp+var_10], rax
0x180002557  xorps   xmm0, xmm0
0x18000255a  mov     [rbp+TokenHandle], 0
0x180002562  xorps   xmm1, xmm1
0x180002565  mov     esi, r8d
0x180002568  movups  [rbp+Buf1], xmm0
0x18000256c  mov     rdi, rdx
0x18000256f  mov     r12, rcx
0x180002572  movups  [rbp+Buf2], xmm1
0x180002576  xor     r15b, r15b
0x180002579  call    UmpoIsClientLocal
0x18000257e  test    eax, eax
0x180002580  jz      loc_180002752
0x180002586  test    esi, esi
0x180002588  jz      loc_18000275C
0x18000258e  test    rdi, rdi
0x180002591  jz      short loc_18000259D
0x180002593  mov     ebx, 57h ; 'W'
0x180002598  jmp     loc_1800026AA
0x18000259d  mov     al, cs:UmpoPowerPolicyInitialized
0x1800025a3  test    al, al
0x1800025a5  jz      loc_18000276A
0x1800025ab  cmp     cs:byte_180024FA8, 1
0x1800025b2  jnz     loc_180002748
0x1800025b8  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x1800025bf  call    cs:__imp_EnterCriticalSection
0x1800025c5  lea     rcx, [rbp+Buf1]; Uuid
0x1800025c9  call    UmpoGetActiveScheme
0x1800025ce  mov     ebx, eax
0x1800025d0  test    eax, eax
0x1800025d2  jnz     loc_180002690
0x1800025d8  test    esi, esi
0x1800025da  jnz     loc_1800026F2
0x1800025e0  movups  xmm0, xmmword ptr [rdi]
0x1800025e3  movdqu  [rbp+Buf2], xmm0
0x1800025e8  mov     r8d, 10h; Size
0x1800025ee  lea     rdx, [rbp+Buf2]; Buf2
0x1800025f2  lea     rcx, [rbp+Buf1]; Buf1
0x1800025f6  call    memcmp_0
0x1800025fb  test    eax, eax
0x1800025fd  jnz     loc_1800026E7
0x180002603  mov     dil, 1
0x180002606  xor     r14b, r14b
0x180002609  xor     r8d, r8d
0x18000260c  mov     r9d, 20006h
0x180002612  xor     ecx, ecx
0x180002614  lea     edx, [r8+13h]
0x180002618  call    UmpoRpcSettingAccessCheck
0x18000261d  mov     ebx, eax
0x18000261f  cmp     eax, 4ECh
0x180002624  jz      loc_180002774
0x18000262a  test    eax, eax
0x18000262c  jnz     short loc_180002690
0x18000262e  test    dil, dil
0x180002631  jz      loc_180002700
0x180002637  mov     dl, r14b
0x18000263a  lea     rcx, [rbp+Buf2]
0x18000263e  call    UmpoSetActiveScheme
0x180002643  mov     ebx, eax
0x180002645  test    eax, eax
0x180002647  jnz     short loc_180002690
0x180002649  xor     ecx, ecx; BindingHandle
0x18000264b  call    cs:__imp_RpcImpersonateClient
0x180002651  mov     ebx, eax
0x180002653  test    eax, eax
0x180002655  jnz     short loc_180002690
0x180002657  mov     r15b, 1
0x18000265a  call    cs:__imp_GetCurrentThread
0x180002660  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180002664  xor     r8d, r8d; OpenAsSelf
0x180002667  mov     rcx, rax; ThreadHandle
0x18000266a  mov     edx, 2000000h; DesiredAccess
0x18000266f  call    cs:__imp_OpenThreadToken
0x180002675  test    eax, eax
0x180002677  jz      loc_18000278C
0x18000267d  mov     rcx, [rbp+TokenHandle]
0x180002681  call    UmpoNotifyKernelAllPowerPolicyChanged
0x180002686  mov     ebx, eax
0x180002688  test    eax, eax
0x18000268a  jz      loc_1800027A1
0x180002690  cmp     cs:byte_180024FA8, 1
0x180002697  jnz     loc_180002733
0x18000269d  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x1800026a4  call    cs:__imp_LeaveCriticalSection
0x1800026aa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800026ae  test    rcx, rcx
0x1800026b1  jnz     loc_18000273D
0x1800026b7  test    r15b, r15b
0x1800026ba  jnz     loc_1800027C3
0x1800026c0  mov     eax, ebx
0x1800026c2  mov     rcx, [rbp+var_10]
0x1800026c6  xor     rcx, rsp; StackCookie
0x1800026c9  call    __security_check_cookie
0x1800026ce  lea     r11, [rsp+60h+var_s0]
0x1800026d3  mov     rbx, [r11+40h]
0x1800026d7  mov     rsi, [r11+48h]
0x1800026db  mov     rsp, r11
0x1800026de  pop     r15
0x1800026e0  pop     r14
0x1800026e2  pop     r12
0x1800026e4  pop     rdi
0x1800026e5  pop     rbp
0x1800026e6  retn
0x1800026e7  xor     dil, dil
0x1800026ea  mov     r14b, 1
0x1800026ed  jmp     loc_180002609
0x1800026f2  movaps  xmm0, [rbp+Buf1]
0x1800026f6  movdqa  [rbp+Buf2], xmm0
0x1800026fb  jmp     loc_1800025E8
0x180002700  mov     r8d, 10h; Size
0x180002706  lea     rdx, [rbp+Buf2]; Buf2
0x18000270a  lea     rcx, GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE; Buf1
0x180002711  call    memcmp_0
0x180002716  test    eax, eax
0x180002718  jnz     loc_180002637
0x18000271e  cmp     cs:UmpoUltimatePerfSchemeAllowed, r15b
0x180002725  jnz     loc_180002637
0x18000272b  lea     ebx, [rax+32h]
0x18000272e  jmp     loc_180002690
0x180002733  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002738  jmp     loc_18000269D
0x18000273d  call    cs:__imp_CloseHandle
0x180002743  jmp     loc_1800026B7
0x180002748  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000274d  jmp     loc_1800025B8
0x180002752  mov     ebx, 5
0x180002757  jmp     loc_1800026AA
0x18000275c  test    rdi, rdi
0x18000275f  jz      loc_180002593
0x180002765  jmp     loc_18000259D
0x18000276a  mov     ebx, 15h
0x18000276f  jmp     loc_1800026AA
0x180002774  test    dil, dil
0x180002777  jz      loc_180002690
0x18000277d  test    esi, esi
0x18000277f  jnz     loc_180002690
0x180002785  xor     ebx, ebx
0x180002787  jmp     loc_180002690
0x18000278c  mov     [rbp+TokenHandle], 0
0x180002794  call    cs:__imp_GetLastError
0x18000279a  mov     ebx, eax
0x18000279c  jmp     loc_180002690
0x1800027a1  test    dil, dil
0x1800027a4  jnz     short loc_1800027AB
0x1800027a6  call    UmpoNotifyKernelNonDefaultPpmProfileSettings
0x1800027ab  xor     r9d, r9d
0x1800027ae  lea     r8, [rbp+Buf2]
0x1800027b2  lea     rdx, [rbp+Buf1]
0x1800027b6  mov     rcx, r12
0x1800027b9  call    UmpoPowerPolicyChanged
0x1800027be  jmp     loc_180002690
0x1800027c3  call    cs:__imp_RpcRevertToSelf
0x1800027c9  jmp     loc_1800026C0
```
