# VerifyCallerMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x180098fcc`
- end: `0x1800990cc`
- name: `?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180089dc0`
- `0x180089e48`
- `0x180089eec`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180098fcc`
- `0x1800990d4`
- `0x1800991f4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180099006`
- `KERNEL32!GetCurrentThread` at `0x180099006`
- `KERNEL32!GetLastError` at `0x180099044`
- `KERNEL32!GetLastError` at `0x180099044`
- `KERNEL32!CloseHandle` at `0x1800990a1`
- `KERNEL32!CloseHandle` at `0x1800990a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009901b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009901b`

## pseudocode

```c
__int64 __fastcall VerifyCallerMembership(WELL_KNOWN_SID_TYPE WellKnownSidType)
{
  HANDLE CurrentThread; // rax
  signed int v3; // ebx
  bool v4; // sf
  __int16 v5; // ax
  signed int LastError; // eax
  signed int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "VerifyCallerMembership", 349, 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v3 = VerifyTokenMembership(TokenHandle, WellKnownSidType);
    v8 = v3;
    v4 = v3 < 0;
    v5 = 360;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v8 = v3;
      v5 = 365;
      goto LABEL_4;
    }
    v8 = 0;
    v9 = 365;
    v3 = VerifyClientMembership(WellKnownSidType);
    v8 = v3;
    v4 = v3 < 0;
    v5 = 366;
  }
  if ( v4 )
  {
LABEL_4:
    v10 = v5;
    goto LABEL_11;
  }
  v9 = v5;
LABEL_11:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180098fcc  mov     [rsp-8+arg_0], rbx
0x180098fd1  mov     [rsp-8+arg_10], rdi
0x180098fd6  push    rbp
0x180098fd7  mov     rbp, rsp
0x180098fda  sub     rsp, 60h
0x180098fde  mov     edi, ecx
0x180098fe0  lea     rdx, aVerifycallerme; "VerifyCallerMembership"
0x180098fe7  mov     ebx, 1
0x180098fec  lea     rcx, [rbp+var_40]; this
0x180098ff0  mov     r9d, ebx; unsigned __int16
0x180098ff3  mov     r8d, 15Dh; unsigned __int16
0x180098ff9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180098ffe  mov     [rbp+TokenHandle], 0
0x180099006  call    cs:__imp_GetCurrentThread
0x18009900c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180099010  mov     r8d, ebx; OpenAsSelf
0x180099013  mov     rcx, rax; ThreadHandle
0x180099016  mov     edx, 2000Ch; DesiredAccess
0x18009901b  call    cs:__imp_OpenThreadToken
0x180099021  test    eax, eax
0x180099023  jz      short loc_180099044
0x180099025  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180099029  mov     edx, edi; WellKnownSidType
0x18009902b  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x180099030  mov     ebx, eax
0x180099032  mov     [rbp+var_40], eax
0x180099035  test    eax, eax
0x180099037  mov     eax, 168h
0x18009903c  jns     short loc_18009908F
0x18009903e  mov     [rbp+var_3A], ax
0x180099042  jmp     short loc_180099093
0x180099044  call    cs:__imp_GetLastError
0x18009904a  mov     ebx, eax
0x18009904c  cmp     eax, 3F0h
0x180099051  jz      short loc_18009906A
0x180099053  test    eax, eax
0x180099055  jle     short loc_180099060
0x180099057  movzx   ebx, ax
0x18009905a  or      ebx, 80070000h
0x180099060  mov     [rbp+var_40], ebx
0x180099063  mov     eax, 16Dh
0x180099068  jmp     short loc_18009903E
0x18009906a  mov     eax, 16Dh
0x18009906f  mov     [rbp+var_40], 0
0x180099076  mov     ecx, edi; WellKnownSidType
0x180099078  mov     [rbp+var_3C], ax
0x18009907c  call    ?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyClientMembership(WELL_KNOWN_SID_TYPE)
0x180099081  mov     ebx, eax
0x180099083  mov     [rbp+var_40], eax
0x180099086  test    eax, eax
0x180099088  mov     eax, 16Eh
0x18009908d  jmp     short loc_18009903C
0x18009908f  mov     [rbp+var_3C], ax
0x180099093  mov     rcx, [rbp+TokenHandle]; hObject
0x180099097  lea     rdx, [rcx-1]
0x18009909b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18009909f  ja      short loc_1800990AF
0x1800990a1  call    cs:__imp_CloseHandle
0x1800990a7  mov     [rbp+TokenHandle], 0
0x1800990af  lea     rcx, [rbp+var_40]; this
0x1800990b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800990b8  lea     r11, [rsp+60h+var_s0]
0x1800990bd  mov     eax, ebx
0x1800990bf  mov     rbx, [r11+10h]
0x1800990c3  mov     rdi, [r11+20h]
0x1800990c7  mov     rsp, r11
0x1800990ca  pop     rbp
0x1800990cb  retn
```
