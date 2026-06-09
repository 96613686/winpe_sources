# VerifyClientMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x1800990d4`
- end: `0x1800991eb`
- name: `?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180098fcc`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800990d4`
- `0x1800991f4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180099149`
- `KERNEL32!GetCurrentThread` at `0x180099149`
- `KERNEL32!CloseHandle` at `0x18009913b`
- `KERNEL32!CloseHandle` at `0x1800991c0`
- `KERNEL32!CloseHandle` at `0x18009913b`
- `KERNEL32!CloseHandle` at `0x1800991c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099161`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099161`
- `ole32!CoRevertToSelf` at `0x1800991a9`
- `ole32!CoRevertToSelf` at `0x1800991a9`
- `ole32!CoImpersonateClient` at `0x18009910c`
- `ole32!CoImpersonateClient` at `0x18009910c`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "VerifyClientMembership", 319, 1);
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
0x1800990d4  mov     [rsp-8+arg_0], rbx
0x1800990d9  mov     [rsp-8+arg_10], rdi
0x1800990de  push    rbp
0x1800990df  mov     rbp, rsp
0x1800990e2  sub     rsp, 60h
0x1800990e6  mov     edi, ecx
0x1800990e8  lea     rdx, aVerifyclientme; "VerifyClientMembership"
0x1800990ef  lea     rcx, [rbp+var_40]; this
0x1800990f3  mov     r9d, 1; unsigned __int16
0x1800990f9  mov     r8d, 13Fh; unsigned __int16
0x1800990ff  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180099104  mov     [rbp+hObject], 0
0x18009910c  call    cs:__imp_CoImpersonateClient
0x180099112  mov     ebx, eax
0x180099114  mov     [rbp+var_40], eax
0x180099117  test    eax, eax
0x180099119  mov     eax, 144h
0x18009911e  jns     short loc_180099129
0x180099120  mov     [rbp+var_3A], ax
0x180099124  jmp     loc_1800991B2
0x180099129  mov     rcx, [rbp+hObject]; hObject
0x18009912d  mov     [rbp+var_3C], ax
0x180099131  lea     rax, [rcx-1]
0x180099135  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180099139  ja      short loc_180099149
0x18009913b  call    cs:__imp_CloseHandle
0x180099141  mov     [rbp+hObject], 0
0x180099149  call    cs:__imp_GetCurrentThread
0x18009914f  lea     r9, [rbp+hObject]; TokenHandle
0x180099153  mov     edx, 2000Ch; DesiredAccess
0x180099158  mov     rcx, rax; ThreadHandle
0x18009915b  mov     r8d, 1; OpenAsSelf
0x180099161  call    cs:__imp_OpenThreadToken
0x180099167  test    eax, eax
0x180099169  jnz     short loc_18009917E
0x18009916b  call    GetLastFailureAsHRESULT
0x180099170  mov     [rbp+var_40], eax
0x180099173  mov     eax, 146h
0x180099178  mov     [rbp+var_3A], ax
0x18009917c  jmp     short loc_1800991A9
0x18009917e  mov     rcx, [rbp+hObject]; TokenHandle
0x180099182  mov     eax, 146h
0x180099187  mov     edx, edi; WellKnownSidType
0x180099189  mov     [rbp+var_3C], ax
0x18009918d  mov     [rbp+var_40], 0
0x180099194  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x180099199  mov     [rbp+var_40], eax
0x18009919c  test    eax, eax
0x18009919e  mov     eax, 147h
0x1800991a3  js      short loc_180099178
0x1800991a5  mov     [rbp+var_3C], ax
0x1800991a9  call    cs:__imp_CoRevertToSelf
0x1800991af  mov     ebx, [rbp+var_40]
0x1800991b2  mov     rcx, [rbp+hObject]; hObject
0x1800991b6  lea     rdx, [rcx-1]
0x1800991ba  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800991be  ja      short loc_1800991CE
0x1800991c0  call    cs:__imp_CloseHandle
0x1800991c6  mov     [rbp+hObject], 0
0x1800991ce  lea     rcx, [rbp+var_40]; this
0x1800991d2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800991d7  lea     r11, [rsp+60h+var_s0]
0x1800991dc  mov     eax, ebx
0x1800991de  mov     rbx, [r11+10h]
0x1800991e2  mov     rdi, [r11+20h]
0x1800991e6  mov     rsp, r11
0x1800991e9  pop     rbp
0x1800991ea  retn
```
