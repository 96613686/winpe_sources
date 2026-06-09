# VerifyCallerMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x18001f1ec`
- end: `0x18001f2ec`
- name: `?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180017e08`
- `0x180017e90`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001f1ec`
- `0x18001f2f4`
- `0x18001f414`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f264`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f23b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f2c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f2c1`

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
0x18001f1ec  mov     [rsp-8+arg_0], rbx
0x18001f1f1  mov     [rsp-8+arg_10], rdi
0x18001f1f6  push    rbp
0x18001f1f7  mov     rbp, rsp
0x18001f1fa  sub     rsp, 60h
0x18001f1fe  mov     edi, ecx
0x18001f200  lea     rdx, aVerifycallerme; "VerifyCallerMembership"
0x18001f207  mov     ebx, 1
0x18001f20c  lea     rcx, [rbp+var_40]; this
0x18001f210  mov     r9d, ebx; unsigned __int16
0x18001f213  mov     r8d, 15Dh; unsigned __int16
0x18001f219  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f21e  mov     [rbp+TokenHandle], 0
0x18001f226  call    cs:__imp_GetCurrentThread
0x18001f22c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001f230  mov     r8d, ebx; OpenAsSelf
0x18001f233  mov     rcx, rax; ThreadHandle
0x18001f236  mov     edx, 2000Ch; DesiredAccess
0x18001f23b  call    cs:__imp_OpenThreadToken
0x18001f241  test    eax, eax
0x18001f243  jz      short loc_18001F264
0x18001f245  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f249  mov     edx, edi; WellKnownSidType
0x18001f24b  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x18001f250  mov     ebx, eax
0x18001f252  mov     [rbp+var_40], eax
0x18001f255  test    eax, eax
0x18001f257  mov     eax, 168h
0x18001f25c  jns     short loc_18001F2AF
0x18001f25e  mov     [rbp+var_3A], ax
0x18001f262  jmp     short loc_18001F2B3
0x18001f264  call    cs:__imp_GetLastError
0x18001f26a  mov     ebx, eax
0x18001f26c  cmp     eax, 3F0h
0x18001f271  jz      short loc_18001F28A
0x18001f273  test    eax, eax
0x18001f275  jle     short loc_18001F280
0x18001f277  movzx   ebx, ax
0x18001f27a  or      ebx, 80070000h
0x18001f280  mov     [rbp+var_40], ebx
0x18001f283  mov     eax, 16Dh
0x18001f288  jmp     short loc_18001F25E
0x18001f28a  mov     eax, 16Dh
0x18001f28f  mov     [rbp+var_40], 0
0x18001f296  mov     ecx, edi; WellKnownSidType
0x18001f298  mov     [rbp+var_3C], ax
0x18001f29c  call    ?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyClientMembership(WELL_KNOWN_SID_TYPE)
0x18001f2a1  mov     ebx, eax
0x18001f2a3  mov     [rbp+var_40], eax
0x18001f2a6  test    eax, eax
0x18001f2a8  mov     eax, 16Eh
0x18001f2ad  jmp     short loc_18001F25C
0x18001f2af  mov     [rbp+var_3C], ax
0x18001f2b3  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f2b7  lea     rdx, [rcx-1]
0x18001f2bb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001f2bf  ja      short loc_18001F2CF
0x18001f2c1  call    cs:__imp_CloseHandle
0x18001f2c7  mov     [rbp+TokenHandle], 0
0x18001f2cf  lea     rcx, [rbp+var_40]; this
0x18001f2d3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f2d8  lea     r11, [rsp+60h+var_s0]
0x18001f2dd  mov     eax, ebx
0x18001f2df  mov     rbx, [r11+10h]
0x18001f2e3  mov     rdi, [r11+20h]
0x18001f2e7  mov     rsp, r11
0x18001f2ea  pop     rbp
0x18001f2eb  retn
```
