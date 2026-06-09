# UmpoSetUserConfiguredOverlayScheme

- ea: `0x18000d9f0`
- end: `0x18000db7f`
- name: `UmpoSetUserConfiguredOverlayScheme`
- size: `399`
- prototype: `__int64 __fastcall(void *, __int64, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d880`
- `0x18000d940`

## callees

- `0x1800012a0`
- `0x180002bc0`
- `0x180002d8c`
- `0x18000a990`
- `0x18000d080`
- `0x18000d9f0`
- `0x18000f3dc`
- `0x180010070`
- `0x180014300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dad9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dac6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dac6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db14`
- `RPCRT4!RpcRevertToSelf` at `0x18000db00`
- `RPCRT4!RpcRevertToSelf` at `0x18000db00`
- `RPCRT4!RpcImpersonateClient` at `0x18000daa4`
- `RPCRT4!RpcImpersonateClient` at `0x18000daa4`

## pseudocode

```c
__int64 __fastcall UmpoSetUserConfiguredOverlayScheme(void *a1, __int64 a2, char a3)
{
  _QWORD *v3; // rbp
  char v5; // r15
  char v6; // bl
  bool v8; // si
  unsigned int ActualOverlayScheme; // edi
  __int64 v10; // rax
  HANDLE CurrentThread; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-50h] BYREF

  TokenHandle = 0;
  v3 = (_QWORD *)a2;
  v5 = 0;
  v6 = 0;
  LOBYTE(a2) = a3;
  v8 = a3 == UmpoOnAcPower;
  Uuid = 0;
  ActualOverlayScheme = UmpoGetActualOverlayScheme(&Uuid, a2);
  if ( !ActualOverlayScheme )
  {
    if ( v8 )
    {
      v10 = *(_QWORD *)&Uuid.Data1 - *v3;
      if ( *(_QWORD *)&Uuid.Data1 == *v3 )
        v10 = *(_QWORD *)Uuid.Data4 - v3[1];
      v6 = v10 != 0;
    }
    ActualOverlayScheme = UmpoSetActiveOverlayScheme(v3, v6, a3);
    if ( !ActualOverlayScheme )
    {
      v5 = 1;
      if ( (_DWORD)UmpoOverlaySchemeSuspendMask || !v8 )
      {
        ActualOverlayScheme = 0;
      }
      else
      {
        ActualOverlayScheme = RpcImpersonateClient(0);
        if ( !ActualOverlayScheme )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
          {
            ActualOverlayScheme = UmpoNotifyKernelAllPowerPolicyChanged(TokenHandle, v12);
            if ( !ActualOverlayScheme )
            {
              if ( v6 )
                UmpoNotifyKernelNonDefaultPpmProfileSettings(v14, v13);
              else
                v6 = 0;
            }
          }
          else
          {
            TokenHandle = 0;
            ActualOverlayScheme = GetLastError();
          }
          RpcRevertToSelf();
        }
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !ActualOverlayScheme )
  {
    if ( !v6 || (ActualOverlayScheme = UmpoCheckAndUpdateOverlayNotification(0)) == 0 )
    {
      UmpoPowerPolicyChanged(a1, (__int64)&Uuid, (__int64)v3, 1);
      return ActualOverlayScheme;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( v5 && v6 )
    UmpoSetActiveOverlayScheme(&Uuid, 1, a3);
  return ActualOverlayScheme;
}

```

## disassembly

```asm
0x18000d9f0  push    rbx
0x18000d9f2  push    rbp
0x18000d9f3  push    rsi
0x18000d9f4  push    rdi
0x18000d9f5  push    r12
0x18000d9f7  push    r14
0x18000d9f9  push    r15
0x18000d9fb  sub     rsp, 40h
0x18000d9ff  mov     rax, cs:__security_cookie
0x18000da06  xor     rax, rsp
0x18000da09  mov     [rsp+78h+var_40], rax
0x18000da0e  xor     al, al
0x18000da10  mov     [rsp+78h+TokenHandle], 0
0x18000da19  movzx   esi, al
0x18000da1c  mov     rbp, rdx
0x18000da1f  mov     eax, 1
0x18000da24  mov     r12, rcx
0x18000da27  xorps   xmm0, xmm0
0x18000da2a  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18000da2f  xor     r15b, r15b
0x18000da32  xor     bl, bl
0x18000da34  cmp     r8b, cs:UmpoOnAcPower
0x18000da3b  mov     dl, r8b
0x18000da3e  mov     r14b, r8b
0x18000da41  cmovz   esi, eax
0x18000da44  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18000da49  call    UmpoGetActualOverlayScheme
0x18000da4e  mov     edi, eax
0x18000da50  test    eax, eax
0x18000da52  jnz     loc_18000DB0A
0x18000da58  test    sil, sil
0x18000da5b  jz      short loc_18000DA7F
0x18000da5d  mov     rax, qword ptr [rsp+78h+Uuid.Data1]
0x18000da62  sub     rax, [rbp+0]
0x18000da66  jnz     short loc_18000DA71
0x18000da68  mov     rax, qword ptr [rsp+78h+Uuid.Data4]
0x18000da6d  sub     rax, [rbp+8]
0x18000da71  test    rax, rax
0x18000da74  movzx   ebx, bl
0x18000da77  mov     eax, 1
0x18000da7c  cmovnz  ebx, eax
0x18000da7f  mov     r8b, r14b
0x18000da82  mov     dl, bl
0x18000da84  mov     rcx, rbp
0x18000da87  call    UmpoSetActiveOverlayScheme
0x18000da8c  mov     edi, eax
0x18000da8e  test    eax, eax
0x18000da90  jnz     short loc_18000DB0A
0x18000da92  cmp     cs:UmpoOverlaySchemeSuspendMask, eax
0x18000da98  mov     r15b, 1
0x18000da9b  jnz     short loc_18000DB08
0x18000da9d  test    sil, sil
0x18000daa0  jz      short loc_18000DB08
0x18000daa2  xor     ecx, ecx; BindingHandle
0x18000daa4  call    cs:__imp_RpcImpersonateClient
0x18000daaa  mov     edi, eax
0x18000daac  test    eax, eax
0x18000daae  jnz     short loc_18000DB0A
0x18000dab0  call    cs:__imp_GetCurrentThread
0x18000dab6  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18000dabb  xor     r8d, r8d; OpenAsSelf
0x18000dabe  mov     rcx, rax; ThreadHandle
0x18000dac1  mov     edx, 2000000h; DesiredAccess
0x18000dac6  call    cs:__imp_OpenThreadToken
0x18000dacc  test    eax, eax
0x18000dace  jnz     short loc_18000DAE3
0x18000dad0  mov     [rsp+78h+TokenHandle], 0
0x18000dad9  call    cs:__imp_GetLastError
0x18000dadf  mov     edi, eax
0x18000dae1  jmp     short loc_18000DB00
0x18000dae3  mov     rcx, [rsp+78h+TokenHandle]
0x18000dae8  call    UmpoNotifyKernelAllPowerPolicyChanged
0x18000daed  mov     edi, eax
0x18000daef  test    eax, eax
0x18000daf1  jnz     short loc_18000DB00
0x18000daf3  test    bl, bl
0x18000daf5  jz      short loc_18000DAFE
0x18000daf7  call    UmpoNotifyKernelNonDefaultPpmProfileSettings
0x18000dafc  jmp     short loc_18000DB00
0x18000dafe  xor     bl, bl
0x18000db00  call    cs:__imp_RpcRevertToSelf
0x18000db06  jmp     short loc_18000DB0A
0x18000db08  xor     edi, edi
0x18000db0a  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18000db0f  test    rcx, rcx
0x18000db12  jz      short loc_18000DB1A
0x18000db14  call    cs:__imp_CloseHandle
0x18000db1a  test    edi, edi
0x18000db1c  jnz     short loc_18000DB34
0x18000db1e  test    bl, bl
0x18000db20  jz      short loc_18000DB6A
0x18000db22  xor     ecx, ecx
0x18000db24  call    UmpoCheckAndUpdateOverlayNotification
0x18000db29  mov     edi, eax
0x18000db2b  test    eax, eax
0x18000db2d  jz      short loc_18000DB6A
0x18000db2f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000db34  test    r15b, r15b
0x18000db37  jz      short loc_18000DB4C
0x18000db39  test    bl, bl
0x18000db3b  jz      short loc_18000DB4C
0x18000db3d  mov     r8b, r14b
0x18000db40  lea     rcx, [rsp+78h+Uuid]
0x18000db45  mov     dl, 1
0x18000db47  call    UmpoSetActiveOverlayScheme
0x18000db4c  mov     eax, edi
0x18000db4e  mov     rcx, [rsp+78h+var_40]
0x18000db53  xor     rcx, rsp; StackCookie
0x18000db56  call    __security_check_cookie
0x18000db5b  add     rsp, 40h
0x18000db5f  pop     r15
0x18000db61  pop     r14
0x18000db63  pop     r12
0x18000db65  pop     rdi
0x18000db66  pop     rsi
0x18000db67  pop     rbp
0x18000db68  pop     rbx
0x18000db69  retn
0x18000db6a  mov     r9b, 1
0x18000db6d  lea     rdx, [rsp+78h+Uuid]
0x18000db72  mov     r8, rbp
0x18000db75  mov     rcx, r12
0x18000db78  call    UmpoPowerPolicyChanged
0x18000db7d  jmp     short loc_18000DB4C
```
