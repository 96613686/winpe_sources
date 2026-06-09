# UmpoPowerPolicyChanged

- ea: `0x18000d080`
- end: `0x18000d2ed`
- name: `UmpoPowerPolicyChanged`
- size: `621`
- prototype: `char __fastcall(void *, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002530`
- `0x18000d9f0`

## callees

- `0x18000b6f4`
- `0x18000bdd4`
- `0x18000bfcc`
- `0x18000c04c`
- `0x18000d080`
- `0x18000d6cc`
- `0x18000f3dc`
- `0x180010070`
- `0x1800100b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d1be`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d1be`
- `ntdll!EtwEventWrite` at `0x18000d1af`
- `ntdll!EtwEventWrite` at `0x18000d1af`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d13f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d13f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2b7`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000d0e2`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000d0e2`

## pseudocode

```c
char __fastcall UmpoPowerPolicyChanged(void *a1, __int64 a2, __int64 a3, char a4)
{
  __int64 *v6; // rdi
  RPC_STATUS ProcessImageName; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  wchar_t *v11; // rax
  __int64 *v12; // rbx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r10
  unsigned __int8 *v16; // rdx
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  int ProcessId; // [rsp+34h] [rbp-CCh] BYREF
  void *ClientProcess; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  wchar_t *v29; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  int *p_ProcessId; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  __int64 v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  wchar_t Str[264]; // [rsp+E0h] [rbp-20h] BYREF

  ProcessId = 0;
  ClientProcess = 0;
  v6 = UMPO_EVT_CURRENTPOWER_SCHEME_CHANGED;
  if ( a4 )
    v6 = UMPO_EVT_CURRENT_OVERLAY_POWER_SCHEME_CHANGED;
  ProcessImageName = I_RpcOpenClientProcess(a1, 0x1000u, &ClientProcess);
  if ( !ProcessImageName )
  {
    v18 = 260;
    ProcessImageName = UmpoQueryProcessImageName(ClientProcess, Str);
    if ( !ProcessImageName )
      goto LABEL_19;
    if ( 2 * (unsigned __int64)v18 >= 0x20A )
      _report_rangecheckfailure();
    Str[v18] = 0;
    ProcessId = GetProcessId(ClientProcess);
    v9 = -1;
    v29 = Str;
    v10 = -1;
    do
      ++v10;
    while ( Str[v10] );
    v30 = 2 * v10 + 2;
    v31 = 0;
    p_ProcessId = &ProcessId;
    v34 = a2;
    v33 = 4;
    v35 = 16;
    v36 = a3;
    v37 = 16;
    EtwEventWrite(UmpoProviderHandle, v6, 4, &v29);
    v11 = wcsrchr(Str, 0x5Cu);
    if ( !v11 )
      goto LABEL_22;
    do
      ++v9;
    while ( v11[v9] );
    if ( v9 )
    {
      v12 = (__int64 *)(v11 + 1);
      UmpoIsInBuiltPowerScheme(a2);
      UmpoIsInBuiltPowerScheme(a3);
      LOBYTE(ProcessImageName) = dword_180024190;
      if ( a4 )
      {
        if ( (unsigned int)dword_180024190 > 5 )
        {
          LOBYTE(ProcessImageName) = tlgKeywordOn();
          if ( (_BYTE)ProcessImageName )
          {
            tlgCreate1Sz_wchar_t((__int64)v22, v12);
            v16 = (unsigned __int8 *)&byte_18001F839;
            goto LABEL_18;
          }
        }
      }
      else if ( (unsigned int)dword_180024190 > 5 )
      {
        LOBYTE(ProcessImageName) = tlgKeywordOn();
        if ( (_BYTE)ProcessImageName )
        {
          tlgCreate1Sz_wchar_t((__int64)v22, v12);
          v16 = (unsigned __int8 *)&unk_18001F890;
LABEL_18:
          v23 = &v18;
          v28 = 16;
          v27 = v14;
          v26 = 16;
          v25 = v15;
          v24 = 4;
          v18 = ProcessId;
          LOBYTE(ProcessImageName) = tlgWriteTransfer_EventWriteTransfer(
                                       (unsigned int)ProcessId,
                                       v16,
                                       v13,
                                       v14,
                                       6u,
                                       &v21);
        }
      }
    }
    else
    {
LABEL_22:
      LOBYTE(ProcessImageName) = MicrosoftTelemetryAssertTriggeredNoArgs();
    }
LABEL_19:
    if ( ClientProcess )
      LOBYTE(ProcessImageName) = CloseHandle(ClientProcess);
  }
  return ProcessImageName;
}

```

## disassembly

```asm
0x18000d080  push    rbp
0x18000d082  push    rbx
0x18000d083  push    rsi
0x18000d084  push    rdi
0x18000d085  push    r12
0x18000d087  push    r13
0x18000d089  push    r14
0x18000d08b  push    r15
0x18000d08d  lea     rbp, [rsp-208h]
0x18000d095  sub     rsp, 308h
0x18000d09c  mov     rax, cs:__security_cookie
0x18000d0a3  xor     rax, rsp
0x18000d0a6  mov     [rbp+240h+var_50], rax
0x18000d0ad  xor     r12d, r12d
0x18000d0b0  lea     rax, UMPO_EVT_CURRENT_OVERLAY_POWER_SCHEME_CHANGED
0x18000d0b7  test    r9b, r9b
0x18000d0ba  mov     [rsp+340h+var_30C], r12d
0x18000d0bf  mov     rsi, r8
0x18000d0c2  mov     [rsp+340h+ClientProcess], r12
0x18000d0c7  mov     r14, rdx
0x18000d0ca  lea     rdi, UMPO_EVT_CURRENTPOWER_SCHEME_CHANGED
0x18000d0d1  lea     r8, [rsp+340h+ClientProcess]; ClientProcess
0x18000d0d6  mov     edx, 1000h; DesiredAccess
0x18000d0db  cmovnz  rdi, rax
0x18000d0df  mov     r15b, r9b
0x18000d0e2  call    cs:__imp_I_RpcOpenClientProcess
0x18000d0e8  test    eax, eax
0x18000d0ea  jnz     loc_18000D2BD
0x18000d0f0  mov     rcx, [rsp+340h+ClientProcess]; ProcessHandle
0x18000d0f5  lea     r8, [rsp+340h+var_310]
0x18000d0fa  mov     ebx, 104h
0x18000d0ff  lea     rdx, [rbp+240h+Str]; void *
0x18000d103  mov     [rsp+340h+var_310], ebx
0x18000d107  call    UmpoQueryProcessImageName
0x18000d10c  test    eax, eax
0x18000d10e  jz      loc_18000D2AD
0x18000d114  cmp     [rsp+340h+var_310], ebx
0x18000d118  jbe     short loc_18000D11F
0x18000d11a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d11f  mov     eax, [rsp+340h+var_310]
0x18000d123  lea     rcx, [rax+rax]
0x18000d127  cmp     rcx, 20Ah
0x18000d12e  jnb     loc_18000D2E7
0x18000d134  mov     [rbp+rcx+240h+Str], r12w
0x18000d13a  mov     rcx, [rsp+340h+ClientProcess]; Process
0x18000d13f  call    cs:__imp_GetProcessId
0x18000d145  mov     [rsp+340h+var_30C], eax
0x18000d149  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d14d  lea     rcx, [rbp+240h+Str]
0x18000d151  lea     rax, [rbp+240h+Str]
0x18000d155  mov     [rbp+240h+var_2A0], rax
0x18000d159  mov     rax, rbx
0x18000d15c  inc     rax
0x18000d15f  cmp     [rcx+rax*2], r12w
0x18000d164  jnz     short loc_18000D15C
0x18000d166  mov     rcx, cs:UmpoProviderHandle
0x18000d16d  lea     eax, ds:2[rax*2]
0x18000d174  mov     [rbp+240h+var_298], eax
0x18000d177  lea     r9, [rbp+240h+var_2A0]
0x18000d17b  lea     rax, [rsp+340h+var_30C]
0x18000d180  mov     [rbp+240h+var_294], r12d
0x18000d184  mov     [rbp+240h+var_290], rax
0x18000d188  mov     rdx, rdi
0x18000d18b  mov     eax, 4
0x18000d190  mov     [rbp+240h+var_280], r14
0x18000d194  mov     r8d, eax
0x18000d197  mov     [rbp+240h+var_288], rax
0x18000d19b  mov     [rbp+240h+var_278], 10h
0x18000d1a3  mov     [rbp+240h+var_270], rsi
0x18000d1a7  mov     [rbp+240h+var_268], 10h
0x18000d1af  call    cs:__imp_EtwEventWrite
0x18000d1b5  mov     edx, 5Ch ; '\'; Ch
0x18000d1ba  lea     rcx, [rbp+240h+Str]; Str
0x18000d1be  call    cs:__imp_wcsrchr
0x18000d1c4  test    rax, rax
0x18000d1c7  jz      loc_18000D2E0
0x18000d1cd  inc     rbx
0x18000d1d0  cmp     [rax+rbx*2], r12w
0x18000d1d5  jnz     short loc_18000D1CD
0x18000d1d7  test    rbx, rbx
0x18000d1da  jz      loc_18000D2E0
0x18000d1e0  mov     rcx, r14
0x18000d1e3  lea     rbx, [rax+2]
0x18000d1e7  call    UmpoIsInBuiltPowerScheme
0x18000d1ec  test    al, al
0x18000d1ee  lea     r9, GUID_NULL
0x18000d1f5  mov     r10, r9
0x18000d1f8  mov     rcx, rsi
0x18000d1fb  cmovnz  r10, r14
0x18000d1ff  call    UmpoIsInBuiltPowerScheme
0x18000d204  test    al, al
0x18000d206  mov     eax, cs:dword_180024190
0x18000d20c  cmovnz  r9, rsi
0x18000d210  test    r15b, r15b
0x18000d213  jnz     short loc_18000D241
0x18000d215  cmp     eax, 5
0x18000d218  jbe     loc_18000D2AD
0x18000d21e  call    _tlgKeywordOn
0x18000d223  test    al, al
0x18000d225  jz      loc_18000D2AD
0x18000d22b  mov     rdx, rbx
0x18000d22e  lea     rcx, [rsp+340h+var_2E0]
0x18000d233  call    _tlgCreate1Sz_wchar_t
0x18000d238  lea     rdx, unk_18001F890
0x18000d23f  jmp     short loc_18000D263
0x18000d241  cmp     eax, 5
0x18000d244  jbe     short loc_18000D2AD
0x18000d246  call    _tlgKeywordOn
0x18000d24b  test    al, al
0x18000d24d  jz      short loc_18000D2AD
0x18000d24f  mov     rdx, rbx
0x18000d252  lea     rcx, [rsp+340h+var_2E0]
0x18000d257  call    _tlgCreate1Sz_wchar_t
0x18000d25c  lea     rdx, byte_18001F839; int
0x18000d263  mov     ecx, [rsp+340h+var_30C]; int
0x18000d267  lea     rax, [rsp+340h+var_310]
0x18000d26c  mov     [rsp+340h+var_2D0], rax
0x18000d271  lea     rax, [rsp+340h+var_300]
0x18000d276  mov     [rsp+340h+var_318], rax; __int64
0x18000d27b  mov     [rsp+340h+var_320], 6; ULONG
0x18000d283  mov     [rbp+240h+var_2A8], 10h
0x18000d28b  mov     [rbp+240h+var_2B0], r9
0x18000d28f  mov     [rbp+240h+var_2B8], 10h
0x18000d297  mov     [rbp+240h+var_2C0], r10
0x18000d29b  mov     [rsp+340h+var_2C8], 4
0x18000d2a4  mov     [rsp+340h+var_310], ecx
0x18000d2a8  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d2ad  mov     rcx, [rsp+340h+ClientProcess]; hObject
0x18000d2b2  test    rcx, rcx
0x18000d2b5  jz      short loc_18000D2BD
0x18000d2b7  call    cs:__imp_CloseHandle
0x18000d2bd  mov     rcx, [rbp+240h+var_50]
0x18000d2c4  xor     rcx, rsp; StackCookie
0x18000d2c7  call    __security_check_cookie
0x18000d2cc  add     rsp, 308h
0x18000d2d3  pop     r15
0x18000d2d5  pop     r14
0x18000d2d7  pop     r13
0x18000d2d9  pop     r12
0x18000d2db  pop     rdi
0x18000d2dc  pop     rsi
0x18000d2dd  pop     rbx
0x18000d2de  pop     rbp
0x18000d2df  retn
0x18000d2e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d2e5  jmp     short loc_18000D2AD
0x18000d2e7  call    __report_rangecheckfailure
```
