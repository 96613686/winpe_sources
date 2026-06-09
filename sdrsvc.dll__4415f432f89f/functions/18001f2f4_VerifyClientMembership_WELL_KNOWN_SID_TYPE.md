# VerifyClientMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x18001f2f4`
- end: `0x18001f40b`
- name: `?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f1ec`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001f2f4`
- `0x18001f414`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f381`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f381`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f35b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f3e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f35b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f3e0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001f3c9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001f3c9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001f32c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001f32c`

## pseudocode

```c
__int64 __fastcall VerifyClientMembership(WELL_KNOWN_SID_TYPE WellKnownSidType)
{
  HRESULT v2; // ebx
  HANDLE CurrentThread; // rax
  __int64 v4; // rcx
  __int16 v5; // ax
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v8; // [rsp+24h] [rbp-3Ch]
  __int16 v9; // [rsp+26h] [rbp-3Ah]
  HANDLE hObject; // [rsp+78h] [rbp+18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "VerifyClientMembership", 0x13Fu, 1u);
  hObject = 0;
  v2 = CoImpersonateClient();
  LastFailureAsHRESULT = v2;
  if ( v2 < 0 )
  {
    v9 = 324;
    goto LABEL_11;
  }
  v8 = 324;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &hObject) )
  {
    v8 = 326;
    LastFailureAsHRESULT = 0;
    LastFailureAsHRESULT = VerifyTokenMembership(hObject, WellKnownSidType);
    v5 = 327;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v8 = 327;
      goto LABEL_10;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
    v5 = 326;
  }
  v9 = v5;
LABEL_10:
  CoRevertToSelf();
  v2 = LastFailureAsHRESULT;
LABEL_11:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001f2f4  mov     [rsp-8+arg_0], rbx
0x18001f2f9  mov     [rsp-8+arg_10], rdi
0x18001f2fe  push    rbp
0x18001f2ff  mov     rbp, rsp
0x18001f302  sub     rsp, 60h
0x18001f306  mov     edi, ecx
0x18001f308  lea     rdx, aVerifyclientme; "VerifyClientMembership"
0x18001f30f  lea     rcx, [rbp+var_40]; this
0x18001f313  mov     r9d, 1; unsigned __int16
0x18001f319  mov     r8d, 13Fh; unsigned __int16
0x18001f31f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f324  mov     [rbp+hObject], 0
0x18001f32c  call    cs:__imp_CoImpersonateClient
0x18001f332  mov     ebx, eax
0x18001f334  mov     [rbp+var_40], eax
0x18001f337  test    eax, eax
0x18001f339  mov     eax, 144h
0x18001f33e  jns     short loc_18001F349
0x18001f340  mov     [rbp+var_3A], ax
0x18001f344  jmp     loc_18001F3D2
0x18001f349  mov     rcx, [rbp+hObject]; hObject
0x18001f34d  mov     [rbp+var_3C], ax
0x18001f351  lea     rax, [rcx-1]
0x18001f355  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f359  ja      short loc_18001F369
0x18001f35b  call    cs:__imp_CloseHandle
0x18001f361  mov     [rbp+hObject], 0
0x18001f369  call    cs:__imp_GetCurrentThread
0x18001f36f  lea     r9, [rbp+hObject]; TokenHandle
0x18001f373  mov     edx, 2000Ch; DesiredAccess
0x18001f378  mov     rcx, rax; ThreadHandle
0x18001f37b  mov     r8d, 1; OpenAsSelf
0x18001f381  call    cs:__imp_OpenThreadToken
0x18001f387  test    eax, eax
0x18001f389  jnz     short loc_18001F39E
0x18001f38b  call    GetLastFailureAsHRESULT
0x18001f390  mov     [rbp+var_40], eax
0x18001f393  mov     eax, 146h
0x18001f398  mov     [rbp+var_3A], ax
0x18001f39c  jmp     short loc_18001F3C9
0x18001f39e  mov     rcx, [rbp+hObject]; TokenHandle
0x18001f3a2  mov     eax, 146h
0x18001f3a7  mov     edx, edi; WellKnownSidType
0x18001f3a9  mov     [rbp+var_3C], ax
0x18001f3ad  mov     [rbp+var_40], 0
0x18001f3b4  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x18001f3b9  mov     [rbp+var_40], eax
0x18001f3bc  test    eax, eax
0x18001f3be  mov     eax, 147h
0x18001f3c3  js      short loc_18001F398
0x18001f3c5  mov     [rbp+var_3C], ax
0x18001f3c9  call    cs:__imp_CoRevertToSelf
0x18001f3cf  mov     ebx, [rbp+var_40]
0x18001f3d2  mov     rcx, [rbp+hObject]; hObject
0x18001f3d6  lea     rdx, [rcx-1]
0x18001f3da  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001f3de  ja      short loc_18001F3EE
0x18001f3e0  call    cs:__imp_CloseHandle
0x18001f3e6  mov     [rbp+hObject], 0
0x18001f3ee  lea     rcx, [rbp+var_40]; this
0x18001f3f2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f3f7  lea     r11, [rsp+60h+var_s0]
0x18001f3fc  mov     eax, ebx
0x18001f3fe  mov     rbx, [r11+10h]
0x18001f402  mov     rdi, [r11+20h]
0x18001f406  mov     rsp, r11
0x18001f409  pop     rbp
0x18001f40a  retn
```
