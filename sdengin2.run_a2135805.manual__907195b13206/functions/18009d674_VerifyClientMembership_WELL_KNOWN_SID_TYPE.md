# VerifyClientMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x18009d674`
- end: `0x18009d7b0`
- name: `?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18009d554`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009d674`
- `0x18009d7b8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18009d6f5`
- `KERNEL32!GetCurrentThread` at `0x18009d6f5`
- `KERNEL32!CloseHandle` at `0x18009d6e1`
- `KERNEL32!CloseHandle` at `0x18009d77e`
- `KERNEL32!CloseHandle` at `0x18009d6e1`
- `KERNEL32!CloseHandle` at `0x18009d77e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d713`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d713`
- `ole32!CoRevertToSelf` at `0x18009d761`
- `ole32!CoRevertToSelf` at `0x18009d761`
- `ole32!CoImpersonateClient` at `0x18009d6ac`
- `ole32!CoImpersonateClient` at `0x18009d6ac`

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
0x18009d674  mov     [rsp-8+arg_0], rbx
0x18009d679  mov     [rsp-8+arg_10], rdi
0x18009d67e  push    rbp
0x18009d67f  mov     rbp, rsp
0x18009d682  sub     rsp, 60h
0x18009d686  mov     edi, ecx
0x18009d688  lea     rdx, aVerifyclientme; "VerifyClientMembership"
0x18009d68f  lea     rcx, [rbp+var_40]; this
0x18009d693  mov     r9d, 1; unsigned __int16
0x18009d699  mov     r8d, 13Fh; unsigned __int16
0x18009d69f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18009d6a4  mov     [rbp+hObject], 0
0x18009d6ac  call    cs:__imp_CoImpersonateClient
0x18009d6b3  nop     dword ptr [rax+rax+00h]
0x18009d6b8  mov     ebx, eax
0x18009d6ba  mov     [rbp+var_40], eax
0x18009d6bd  test    eax, eax
0x18009d6bf  mov     eax, 144h
0x18009d6c4  jns     short loc_18009D6CF
0x18009d6c6  mov     [rbp+var_3A], ax
0x18009d6ca  jmp     loc_18009D770
0x18009d6cf  mov     rcx, [rbp+hObject]; hObject
0x18009d6d3  mov     [rbp+var_3C], ax
0x18009d6d7  lea     rax, [rcx-1]
0x18009d6db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009d6df  ja      short loc_18009D6F5
0x18009d6e1  call    cs:__imp_CloseHandle
0x18009d6e8  nop     dword ptr [rax+rax+00h]
0x18009d6ed  mov     [rbp+hObject], 0
0x18009d6f5  call    cs:__imp_GetCurrentThread
0x18009d6fc  nop     dword ptr [rax+rax+00h]
0x18009d701  lea     r9, [rbp+hObject]; TokenHandle
0x18009d705  mov     edx, 2000Ch; DesiredAccess
0x18009d70a  mov     rcx, rax; ThreadHandle
0x18009d70d  mov     r8d, 1; OpenAsSelf
0x18009d713  call    cs:__imp_OpenThreadToken
0x18009d71a  nop     dword ptr [rax+rax+00h]
0x18009d71f  test    eax, eax
0x18009d721  jnz     short loc_18009D736
0x18009d723  call    GetLastFailureAsHRESULT
0x18009d728  mov     [rbp+var_40], eax
0x18009d72b  mov     eax, 146h
0x18009d730  mov     [rbp+var_3A], ax
0x18009d734  jmp     short loc_18009D761
0x18009d736  mov     rcx, [rbp+hObject]; TokenHandle
0x18009d73a  mov     eax, 146h
0x18009d73f  mov     edx, edi; WellKnownSidType
0x18009d741  mov     [rbp+var_3C], ax
0x18009d745  mov     [rbp+var_40], 0
0x18009d74c  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x18009d751  mov     [rbp+var_40], eax
0x18009d754  test    eax, eax
0x18009d756  mov     eax, 147h
0x18009d75b  js      short loc_18009D730
0x18009d75d  mov     [rbp+var_3C], ax
0x18009d761  call    cs:__imp_CoRevertToSelf
0x18009d768  nop     dword ptr [rax+rax+00h]
0x18009d76d  mov     ebx, [rbp+var_40]
0x18009d770  mov     rcx, [rbp+hObject]; hObject
0x18009d774  lea     rdx, [rcx-1]
0x18009d778  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18009d77c  ja      short loc_18009D792
0x18009d77e  call    cs:__imp_CloseHandle
0x18009d785  nop     dword ptr [rax+rax+00h]
0x18009d78a  mov     [rbp+hObject], 0
0x18009d792  lea     rcx, [rbp+var_40]; this
0x18009d796  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009d79b  lea     r11, [rsp+60h+var_s0]
0x18009d7a0  mov     eax, ebx
0x18009d7a2  mov     rbx, [r11+10h]
0x18009d7a6  mov     rdi, [r11+20h]
0x18009d7aa  mov     rsp, r11
0x18009d7ad  pop     rbp
0x18009d7ae  retn
```
