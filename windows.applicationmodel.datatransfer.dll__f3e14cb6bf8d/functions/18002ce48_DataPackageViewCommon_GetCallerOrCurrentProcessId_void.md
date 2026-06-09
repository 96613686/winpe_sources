# DataPackageViewCommon::GetCallerOrCurrentProcessId(void)

- ea: `0x18002ce48`
- end: `0x18002cfc5`
- name: `?GetCallerOrCurrentProcessId@DataPackageViewCommon@@IEAAKXZ`
- size: `381`
- prototype: `unsigned int __fastcall(DataPackageViewCommon *__hidden this)`
- caller_count: `17`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c390`
- `0x18002ca40`
- `0x18002cfcc`
- `0x18002d080`
- `0x18002d610`
- `0x18002dba0`
- `0x18002ded0`
- `0x18002df60`
- `0x18002f9c0`
- `0x180032f40`
- `0x180033650`
- `0x180034480`
- `0x1800349f0`
- `0x180035110`
- `0x180036460`
- `0x18003ea60`
- `0x180048480`

## callees

- `0x180008b68`
- `0x18002ce48`
- `0x18002d19c`
- `0x18007bb34`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cf37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cf37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cf4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cf4d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002ce79`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002ce79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf16`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002cefa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002cefa`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002cf81`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002cf81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfb4`
- `ext-ms-win-edputil-policy-l1-1-0!GetProcessUniqueIdFromToken` at `0x18002cecc`
- `ext-ms-win-edputil-policy-l1-1-0!GetProcessUniqueIdFromToken` at `0x18002cf5f`
- `ext-ms-win-edputil-policy-l1-1-0!GetProcessUniqueIdFromToken` at `0x18002cecc`
- `ext-ms-win-edputil-policy-l1-1-0!GetProcessUniqueIdFromToken` at `0x18002cf5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DataPackageViewCommon::GetCallerOrCurrentProcessId(DataPackageViewCommon *this, __int64 a2)
{
  int CallingProcessHandle; // ebx
  char *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  HANDLE v6; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  __int64 v9; // rcx
  DWORD ProcessId; // [rsp+40h] [rbp+20h] BYREF
  int v12; // [rsp+44h] [rbp+24h]
  HANDLE Process; // [rsp+48h] [rbp+28h] BYREF
  __int64 v14; // [rsp+50h] [rbp+30h] BYREF
  __int64 v15; // [rsp+58h] [rbp+38h] BYREF

  v12 = HIDWORD(this);
  ProcessId = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, a2, &Process);
  if ( CallingProcessHandle >= 0 )
    ProcessId = GetProcessId(Process);
  v3 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  if ( CallingProcessHandle < 0 )
  {
    ProcessId = GetCurrentProcessId();
    v15 = 0;
    Process = 0;
    if ( !byte_1800AAC28 )
    {
      GetProcessUniqueIdFromToken(0, 0);
      byte_1800AAC28 = 1;
    }
    v14 = 0;
    v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v14);
    if ( (int)GetClipboardProtectionServer(v5, v4) >= 0 && CoImpersonateClient() >= 0 )
    {
      v6 = Process;
      if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v6);
        SetLastError(LastError);
      }
      Process = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &Process) && (int)GetProcessUniqueIdFromToken(Process, &v15) >= 0 )
        (*(void (__fastcall **)(__int64, __int64, DWORD *))(*(_QWORD *)v14 + 56LL))(v14, v15, &ProcessId);
      CoRevertToSelf();
    }
    v9 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Process);
  }
  return ProcessId;
}

```

## disassembly

```asm
0x18002ce48  mov     [rsp-18h+arg_0], rcx
0x18002ce4d  push    rbp
0x18002ce4e  push    rbx
0x18002ce4f  push    rdi
0x18002ce50  mov     rbp, rsp
0x18002ce53  sub     rsp, 20h
0x18002ce57  mov     dword ptr [rbp+arg_0], 0
0x18002ce5e  mov     [rbp+Process], 0
0x18002ce66  lea     r8, [rbp+Process]
0x18002ce6a  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18002ce6f  mov     ebx, eax
0x18002ce71  test    eax, eax
0x18002ce73  js      short loc_18002CE82
0x18002ce75  mov     rcx, [rbp+Process]; Process
0x18002ce79  call    cs:__imp_GetProcessId
0x18002ce7f  mov     dword ptr [rbp+arg_0], eax
0x18002ce82  mov     rcx, [rbp+Process]; hObject
0x18002ce86  mov     [rbp+Process], 0
0x18002ce8e  lea     rdx, [rcx-1]
0x18002ce92  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002ce96  ja      short loc_18002CE9E
0x18002ce98  call    cs:__imp_CloseHandle
0x18002ce9e  test    ebx, ebx
0x18002cea0  jns     loc_18002CFBA
0x18002cea6  call    cs:__imp_GetCurrentProcessId
0x18002ceac  mov     dword ptr [rbp+arg_0], eax
0x18002ceaf  mov     [rbp+arg_18], 0
0x18002ceb7  mov     [rbp+Process], 0
0x18002cebf  cmp     cs:byte_1800AAC28, 0
0x18002cec6  jnz     short loc_18002CED9
0x18002cec8  xor     edx, edx
0x18002ceca  xor     ecx, ecx
0x18002cecc  call    cs:__imp_GetProcessUniqueIdFromToken
0x18002ced2  mov     cs:byte_1800AAC28, 1
0x18002ced9  mov     [rbp+arg_10], 0
0x18002cee1  lea     rcx, [rbp+arg_10]
0x18002cee5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18002ceea  mov     rdx, rax
0x18002ceed  call    GetClipboardProtectionServer
0x18002cef2  test    eax, eax
0x18002cef4  js      loc_18002CF88
0x18002cefa  call    cs:__imp_CoImpersonateClient
0x18002cf00  test    eax, eax
0x18002cf02  js      loc_18002CF88
0x18002cf08  mov     rdi, [rbp+Process]
0x18002cf0c  lea     rax, [rdi-1]
0x18002cf10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cf14  ja      short loc_18002CF2F
0x18002cf16  call    cs:__imp_GetLastError
0x18002cf1c  mov     ebx, eax
0x18002cf1e  mov     rcx, rdi; hObject
0x18002cf21  call    cs:__imp_CloseHandle
0x18002cf27  mov     ecx, ebx; dwErrCode
0x18002cf29  call    cs:__imp_SetLastError
0x18002cf2f  mov     [rbp+Process], 0
0x18002cf37  call    cs:__imp_GetCurrentThread
0x18002cf3d  lea     r9, [rbp+Process]; TokenHandle
0x18002cf41  mov     edx, 8; DesiredAccess
0x18002cf46  lea     r8d, [rdx-7]; OpenAsSelf
0x18002cf4a  mov     rcx, rax; ThreadHandle
0x18002cf4d  call    cs:__imp_OpenThreadToken
0x18002cf53  test    eax, eax
0x18002cf55  jz      short loc_18002CF81
0x18002cf57  lea     rdx, [rbp+arg_18]
0x18002cf5b  mov     rcx, [rbp+Process]
0x18002cf5f  call    cs:__imp_GetProcessUniqueIdFromToken
0x18002cf65  test    eax, eax
0x18002cf67  js      short loc_18002CF81
0x18002cf69  mov     rcx, [rbp+arg_10]
0x18002cf6d  mov     rax, [rcx]
0x18002cf70  lea     r8, [rbp+arg_0]
0x18002cf74  mov     rdx, [rbp+arg_18]
0x18002cf78  mov     rax, [rax+38h]
0x18002cf7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf81  call    cs:__imp_CoRevertToSelf
0x18002cf87  nop
0x18002cf88  mov     rcx, [rbp+arg_10]
0x18002cf8c  test    rcx, rcx
0x18002cf8f  jz      short loc_18002CFA6
0x18002cf91  mov     [rbp+arg_10], 0
0x18002cf99  mov     rax, [rcx]
0x18002cf9c  mov     rax, [rax+10h]
0x18002cfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfa5  nop
0x18002cfa6  mov     rcx, [rbp+Process]; hObject
0x18002cfaa  lea     rax, [rcx-1]
0x18002cfae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cfb2  ja      short loc_18002CFBA
0x18002cfb4  call    cs:__imp_CloseHandle
0x18002cfba  mov     eax, dword ptr [rbp+arg_0]
0x18002cfbd  add     rsp, 20h
0x18002cfc1  pop     rdi
0x18002cfc2  pop     rbx
0x18002cfc3  pop     rbp
0x18002cfc4  retn
```
