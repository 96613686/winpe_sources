# UmpoRpcReadFromUserPowerKey

- ea: `0x180004830`
- end: `0x180004b7a`
- name: `UmpoRpcReadFromUserPowerKey`
- size: `842`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *, UUID *, int, unsigned int, __int64, DWORD, DWORD *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800034c0`
- `0x1800037b0`
- `0x180004830`
- `0x180004b80`
- `0x180005cb4`
- `0x18000f3dc`
- `0x180010070`
- `0x1800188bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b34`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800049df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004aab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800049df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800049c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004a95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800049c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004934`
- `RPCRT4!RpcRevertToSelf` at `0x1800049e7`
- `RPCRT4!RpcRevertToSelf` at `0x180004ab3`
- `RPCRT4!RpcRevertToSelf` at `0x1800049e7`
- `RPCRT4!RpcRevertToSelf` at `0x180004ab3`
- `RPCRT4!RpcImpersonateClient` at `0x1800048d9`
- `RPCRT4!RpcImpersonateClient` at `0x18000491a`
- `RPCRT4!RpcImpersonateClient` at `0x1800048d9`
- `RPCRT4!RpcImpersonateClient` at `0x18000491a`

## pseudocode

```c
__int64 __fastcall UmpoRpcReadFromUserPowerKey(
        __int64 a1,
        UUID *a2,
        UUID *a3,
        UUID *a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        DWORD a8,
        DWORD *a9,
        __int64 a10)
{
  char v12; // r12
  unsigned int ActiveScheme; // ebx
  unsigned int LastError; // edi
  DWORD *v15; // rcx
  UUID *v16; // rdx
  HANDLE CurrentThread; // rax
  BOOL v19; // esi
  __int64 v20; // rax
  __int64 v21; // rdx
  HANDLE v22; // rax
  BOOL v23; // edi
  HANDLE hObject; // [rsp+50h] [rbp-39h] BYREF
  LPDWORD v25; // [rsp+58h] [rbp-31h]
  __int64 v26; // [rsp+60h] [rbp-29h]
  __int64 v27; // [rsp+68h] [rbp-21h]
  UUID *v28; // [rsp+70h] [rbp-19h]
  UUID Buf2; // [rsp+78h] [rbp-11h] BYREF

  v27 = a7;
  v25 = a9;
  v26 = a10;
  v28 = a3;
  Buf2 = 0;
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  v12 = 0;
  if ( a6 > 1 )
  {
LABEL_15:
    v15 = v25;
    v16 = v28;
    *v25 = a8;
    ActiveScheme = UmpoReadFromUserPowerKey(a2, v16, a4, a5 != 0, a5 != 0, a6, 0, (BYTE *)v27, v15, (int *)v26);
    if ( !v12 )
      return ActiveScheme;
    goto LABEL_27;
  }
  ActiveScheme = 21;
  hObject = (HANDLE)-1LL;
  if ( UmpoPowerPolicyInitialized )
  {
    LastError = RpcImpersonateClient(0);
    if ( !LastError )
    {
      CurrentThread = GetCurrentThread();
      v19 = OpenThreadToken(CurrentThread, 8u, 1, &hObject);
      LastError = RpcRevertToSelf();
      if ( LastError )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        if ( !v19 )
        {
          LastError = GetLastError();
          goto LABEL_8;
        }
        LastError = UmpoInternalAccessCheck(16, (__int64)a2, hObject, 0x20019u);
      }
    }
  }
  else
  {
    LastError = 21;
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_8:
  if ( LastError && LastError != 1260 )
    return LastError;
  hObject = (HANDLE)-1LL;
  if ( UmpoPowerPolicyInitialized )
  {
    ActiveScheme = RpcImpersonateClient(0);
    if ( !ActiveScheme )
    {
      v22 = GetCurrentThread();
      v23 = OpenThreadToken(v22, 8u, 1, &hObject);
      ActiveScheme = RpcRevertToSelf();
      if ( ActiveScheme )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        if ( !v23 )
        {
          ActiveScheme = GetLastError();
          goto LABEL_13;
        }
        ActiveScheme = UmpoInternalAccessCheck(a6, (__int64)a4, hObject, 0x20019u);
      }
    }
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_13:
  if ( ActiveScheme && ActiveScheme != 1260 )
    return ActiveScheme;
  if ( !a2 )
    goto LABEL_15;
  v20 = *(_QWORD *)&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE.Data1 == *(_QWORD *)&a2->Data1 )
    v20 = *(_QWORD *)GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE.Data4 - *(_QWORD *)a2->Data4;
  if ( v20 || UmpoUltimatePerfSchemeAllowed )
    goto LABEL_15;
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  ActiveScheme = UmpoGetActiveScheme(&Buf2, v21);
  if ( ActiveScheme )
    goto LABEL_27;
  if ( !memcmp_0(&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE, &Buf2, 0x10u) )
  {
    v12 = 1;
    goto LABEL_15;
  }
  ActiveScheme = 50;
LABEL_27:
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
  return ActiveScheme;
}

```

## disassembly

```asm
0x180004830  mov     [rsp-8+arg_0], rbx
0x180004835  push    rbp
0x180004836  push    rsi
0x180004837  push    rdi
0x180004838  push    r12
0x18000483a  push    r13
0x18000483c  push    r14
0x18000483e  push    r15
0x180004840  lea     rbp, [rsp-7]
0x180004845  sub     rsp, 90h
0x18000484c  mov     rax, cs:__security_cookie
0x180004853  xor     rax, rsp
0x180004856  mov     [rbp+37h+var_38], rax
0x18000485a  mov     rax, [rbp+37h+arg_30]
0x18000485e  xorps   xmm0, xmm0
0x180004861  mov     [rbp+37h+var_58], rax
0x180004865  mov     r13, r9
0x180004868  mov     rax, [rbp+37h+arg_40]
0x18000486f  mov     r14, rdx
0x180004872  mov     [rbp+37h+var_68], rax
0x180004876  mov     rax, [rbp+37h+arg_48]
0x18000487d  mov     [rbp+37h+var_60], rax
0x180004881  mov     [rbp+37h+var_50], r8
0x180004885  movups  [rbp+37h+Buf2], xmm0
0x180004889  call    UmpoIsClientLocal
0x18000488e  test    eax, eax
0x180004890  jz      loc_180004AEE
0x180004896  mov     al, cs:UmpoPowerPolicyInitialized
0x18000489c  test    al, al
0x18000489e  jz      loc_180004AF8
0x1800048a4  mov     r15d, [rbp+37h+arg_28]
0x1800048a8  xor     r12b, r12b
0x1800048ab  mov     eax, r15d
0x1800048ae  test    r15d, r15d
0x1800048b1  jz      short loc_1800048BC
0x1800048b3  cmp     eax, 1
0x1800048b6  jnz     loc_18000494B
0x1800048bc  mov     al, cs:UmpoPowerPolicyInitialized
0x1800048c2  mov     ebx, 15h
0x1800048c7  mov     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800048cf  test    al, al
0x1800048d1  jz      loc_180004B20
0x1800048d7  xor     ecx, ecx; BindingHandle
0x1800048d9  call    cs:__imp_RpcImpersonateClient
0x1800048df  mov     edi, eax
0x1800048e1  test    eax, eax
0x1800048e3  jz      loc_1800049C9
0x1800048e9  mov     rcx, [rbp+37h+hObject]; hObject
0x1800048ed  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048f1  jz      short loc_1800048F9
0x1800048f3  call    cs:__imp_CloseHandle
0x1800048f9  mov     esi, 4ECh
0x1800048fe  test    edi, edi
0x180004900  jnz     loc_180004ADF
0x180004906  mov     al, cs:UmpoPowerPolicyInitialized
0x18000490c  mov     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x180004914  test    al, al
0x180004916  jz      short loc_18000492A
0x180004918  xor     ecx, ecx; BindingHandle
0x18000491a  call    cs:__imp_RpcImpersonateClient
0x180004920  mov     ebx, eax
0x180004922  test    eax, eax
0x180004924  jz      loc_180004A95
0x18000492a  mov     rcx, [rbp+37h+hObject]; hObject
0x18000492e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004932  jz      short loc_18000493A
0x180004934  call    cs:__imp_CloseHandle
0x18000493a  test    ebx, ebx
0x18000493c  jnz     loc_180004B41
0x180004942  test    r14, r14
0x180004945  jnz     loc_180004A1B
0x18000494b  mov     rcx, [rbp+37h+var_68]
0x18000494f  mov     r8, r13
0x180004952  mov     eax, [rbp+37h+arg_38]
0x180004955  cmp     [rbp+37h+arg_20], 0
0x180004959  mov     rdx, [rbp+37h+var_50]
0x18000495d  mov     [rcx], eax
0x18000495f  setnz   r9b
0x180004963  mov     rax, [rbp+37h+var_60]
0x180004967  mov     [rsp+0C0h+var_78], rax; __int64
0x18000496c  mov     rax, [rbp+37h+var_58]
0x180004970  mov     [rsp+0C0h+var_80], rcx; LPDWORD
0x180004975  mov     rcx, r14; Uuid2
0x180004978  mov     [rsp+0C0h+var_88], rax; __int64
0x18000497d  mov     [rsp+0C0h+lpType], 0; lpType
0x180004986  mov     [rsp+0C0h+var_98], r15d; int
0x18000498b  mov     [rsp+0C0h+var_A0], r9b; char
0x180004990  call    UmpoReadFromUserPowerKey
0x180004995  mov     ebx, eax
0x180004997  test    r12b, r12b
0x18000499a  jnz     loc_180004A75
0x1800049a0  mov     eax, ebx
0x1800049a2  mov     rcx, [rbp+37h+var_38]
0x1800049a6  xor     rcx, rsp; StackCookie
0x1800049a9  call    __security_check_cookie
0x1800049ae  mov     rbx, [rsp+0C0h+arg_0]
0x1800049b6  add     rsp, 90h
0x1800049bd  pop     r15
0x1800049bf  pop     r14
0x1800049c1  pop     r13
0x1800049c3  pop     r12
0x1800049c5  pop     rdi
0x1800049c6  pop     rsi
0x1800049c7  pop     rbp
0x1800049c8  retn
0x1800049c9  call    cs:__imp_GetCurrentThread
0x1800049cf  mov     edx, 8; DesiredAccess
0x1800049d4  lea     r9, [rbp+37h+hObject]; TokenHandle
0x1800049d8  mov     rcx, rax; ThreadHandle
0x1800049db  lea     r8d, [rdx-7]; OpenAsSelf
0x1800049df  call    cs:__imp_OpenThreadToken
0x1800049e5  mov     esi, eax
0x1800049e7  call    cs:__imp_RpcRevertToSelf
0x1800049ed  mov     edi, eax
0x1800049ef  test    eax, eax
0x1800049f1  jnz     loc_180004B02
0x1800049f7  test    esi, esi
0x1800049f9  jz      loc_180004B27
0x1800049ff  mov     r8, [rbp+37h+hObject]
0x180004a03  lea     ecx, [rax+10h]
0x180004a06  mov     r9d, 20019h
0x180004a0c  mov     rdx, r14
0x180004a0f  call    UmpoInternalAccessCheck
0x180004a14  mov     edi, eax
0x180004a16  jmp     loc_1800048E9
0x180004a1b  mov     rax, qword ptr cs:GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE.Data1
0x180004a22  sub     rax, [r14]
0x180004a25  jnz     short loc_180004A32
0x180004a27  mov     rax, qword ptr cs:GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE.Data4
0x180004a2e  sub     rax, [r14+8]
0x180004a32  test    rax, rax
0x180004a35  jnz     loc_18000494B
0x180004a3b  cmp     cs:UmpoUltimatePerfSchemeAllowed, r12b
0x180004a42  jnz     loc_18000494B
0x180004a48  cmp     cs:byte_180024FA8, 1
0x180004a4f  jnz     loc_180004B16
0x180004a55  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180004a5c  call    cs:__imp_EnterCriticalSection
0x180004a62  lea     rcx, [rbp+37h+Buf2]; Uuid
0x180004a66  call    UmpoGetActiveScheme
0x180004a6b  mov     ebx, eax
0x180004a6d  test    eax, eax
0x180004a6f  jz      loc_180004B4E
0x180004a75  cmp     cs:byte_180024FA8, 1
0x180004a7c  jz      short loc_180004A83
0x180004a7e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004a83  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180004a8a  call    cs:__imp_LeaveCriticalSection
0x180004a90  jmp     loc_1800049A0
0x180004a95  call    cs:__imp_GetCurrentThread
0x180004a9b  mov     edx, 8; DesiredAccess
0x180004aa0  lea     r9, [rbp+37h+hObject]; TokenHandle
0x180004aa4  mov     rcx, rax; ThreadHandle
0x180004aa7  lea     r8d, [rdx-7]; OpenAsSelf
0x180004aab  call    cs:__imp_OpenThreadToken
0x180004ab1  mov     edi, eax
0x180004ab3  call    cs:__imp_RpcRevertToSelf
0x180004ab9  mov     ebx, eax
0x180004abb  test    eax, eax
0x180004abd  jnz     short loc_180004B0C
0x180004abf  test    edi, edi
0x180004ac1  jz      short loc_180004B34
0x180004ac3  mov     r8, [rbp+37h+hObject]
0x180004ac7  mov     r9d, 20019h
0x180004acd  mov     rdx, r13
0x180004ad0  mov     ecx, r15d
0x180004ad3  call    UmpoInternalAccessCheck
0x180004ad8  mov     ebx, eax
0x180004ada  jmp     loc_18000492A
0x180004adf  cmp     edi, esi
0x180004ae1  jz      loc_180004906
0x180004ae7  mov     ebx, edi
0x180004ae9  jmp     loc_1800049A0
0x180004aee  mov     ebx, 5
0x180004af3  jmp     loc_1800049A0
0x180004af8  mov     ebx, 15h
0x180004afd  jmp     loc_1800049A0
0x180004b02  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004b07  jmp     loc_1800048E9
0x180004b0c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004b11  jmp     loc_18000492A
0x180004b16  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004b1b  jmp     loc_180004A55
0x180004b20  mov     edi, ebx
0x180004b22  jmp     loc_1800048E9
0x180004b27  call    cs:__imp_GetLastError
0x180004b2d  mov     edi, eax
0x180004b2f  jmp     loc_1800048F9
0x180004b34  call    cs:__imp_GetLastError
0x180004b3a  mov     ebx, eax
0x180004b3c  jmp     loc_18000493A
0x180004b41  cmp     ebx, esi
0x180004b43  jnz     loc_1800049A0
0x180004b49  jmp     loc_180004942
0x180004b4e  mov     r8d, 10h; Size
0x180004b54  lea     rdx, [rbp+37h+Buf2]; Buf2
0x180004b58  lea     rcx, GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE; Buf1
0x180004b5f  call    memcmp_0
0x180004b64  test    eax, eax
0x180004b66  jnz     short loc_180004B70
0x180004b68  mov     r12b, 1
0x180004b6b  jmp     loc_18000494B
0x180004b70  mov     ebx, 32h ; '2'
0x180004b75  jmp     loc_180004A75
```
