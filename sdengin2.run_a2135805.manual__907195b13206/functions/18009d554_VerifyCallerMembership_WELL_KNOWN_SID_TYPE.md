# VerifyCallerMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x18009d554`
- end: `0x18009d66d`
- name: `?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18008d9ac`
- `0x18008da40`
- `0x18008daf0`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18009d554`
- `0x18009d674`
- `0x18009d7b8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18009d58e`
- `KERNEL32!GetCurrentThread` at `0x18009d58e`
- `KERNEL32!GetLastError` at `0x18009d5d8`
- `KERNEL32!GetLastError` at `0x18009d5d8`
- `KERNEL32!CloseHandle` at `0x18009d63b`
- `KERNEL32!CloseHandle` at `0x18009d63b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d5a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d5a9`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "VerifyCallerMembership", 0x15Du, 1u);
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
0x18009d554  mov     [rsp-8+arg_0], rbx
0x18009d559  mov     [rsp-8+arg_10], rdi
0x18009d55e  push    rbp
0x18009d55f  mov     rbp, rsp
0x18009d562  sub     rsp, 60h
0x18009d566  mov     edi, ecx
0x18009d568  lea     rdx, aVerifycallerme; "VerifyCallerMembership"
0x18009d56f  mov     ebx, 1
0x18009d574  lea     rcx, [rbp+var_40]; this
0x18009d578  mov     r9d, ebx; unsigned __int16
0x18009d57b  mov     r8d, 15Dh; unsigned __int16
0x18009d581  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18009d586  mov     [rbp+TokenHandle], 0
0x18009d58e  call    cs:__imp_GetCurrentThread
0x18009d595  nop     dword ptr [rax+rax+00h]
0x18009d59a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18009d59e  mov     r8d, ebx; OpenAsSelf
0x18009d5a1  mov     rcx, rax; ThreadHandle
0x18009d5a4  mov     edx, 2000Ch; DesiredAccess
0x18009d5a9  call    cs:__imp_OpenThreadToken
0x18009d5b0  nop     dword ptr [rax+rax+00h]
0x18009d5b5  test    eax, eax
0x18009d5b7  jz      short loc_18009D5D8
0x18009d5b9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18009d5bd  mov     edx, edi; WellKnownSidType
0x18009d5bf  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x18009d5c4  mov     ebx, eax
0x18009d5c6  mov     [rbp+var_40], eax
0x18009d5c9  test    eax, eax
0x18009d5cb  mov     eax, 168h
0x18009d5d0  jns     short loc_18009D629
0x18009d5d2  mov     [rbp+var_3A], ax
0x18009d5d6  jmp     short loc_18009D62D
0x18009d5d8  call    cs:__imp_GetLastError
0x18009d5df  nop     dword ptr [rax+rax+00h]
0x18009d5e4  mov     ebx, eax
0x18009d5e6  cmp     eax, 3F0h
0x18009d5eb  jz      short loc_18009D604
0x18009d5ed  test    eax, eax
0x18009d5ef  jle     short loc_18009D5FA
0x18009d5f1  movzx   ebx, ax
0x18009d5f4  or      ebx, 80070000h
0x18009d5fa  mov     [rbp+var_40], ebx
0x18009d5fd  mov     eax, 16Dh
0x18009d602  jmp     short loc_18009D5D2
0x18009d604  mov     eax, 16Dh
0x18009d609  mov     [rbp+var_40], 0
0x18009d610  mov     ecx, edi; WellKnownSidType
0x18009d612  mov     [rbp+var_3C], ax
0x18009d616  call    ?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyClientMembership(WELL_KNOWN_SID_TYPE)
0x18009d61b  mov     ebx, eax
0x18009d61d  mov     [rbp+var_40], eax
0x18009d620  test    eax, eax
0x18009d622  mov     eax, 16Eh
0x18009d627  jmp     short loc_18009D5D0
0x18009d629  mov     [rbp+var_3C], ax
0x18009d62d  mov     rcx, [rbp+TokenHandle]; hObject
0x18009d631  lea     rdx, [rcx-1]
0x18009d635  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18009d639  ja      short loc_18009D64F
0x18009d63b  call    cs:__imp_CloseHandle
0x18009d642  nop     dword ptr [rax+rax+00h]
0x18009d647  mov     [rbp+TokenHandle], 0
0x18009d64f  lea     rcx, [rbp+var_40]; this
0x18009d653  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009d658  lea     r11, [rsp+60h+var_s0]
0x18009d65d  mov     eax, ebx
0x18009d65f  mov     rbx, [r11+10h]
0x18009d663  mov     rdi, [r11+20h]
0x18009d667  mov     rsp, r11
0x18009d66a  pop     rbp
0x18009d66b  retn
```
