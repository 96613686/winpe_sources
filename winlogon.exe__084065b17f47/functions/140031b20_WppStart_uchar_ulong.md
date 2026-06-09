# WppStart(uchar,ulong)

- ea: `0x140031b20`
- end: `0x1400320de`
- name: `?WppStart@@YAKEK@Z`
- size: `1470`
- prototype: `unsigned int __fastcall(unsigned __int8, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14005d8a0`
- `0x1400877f0`
- `0x14008e0f0`

## callees

- `0x14001a520`
- `0x140031b20`
- `0x14003fb70`
- `0x14004d554`
- `0x140053720`
- `0x1400544e0`
- `0x14005d9dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140031bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140031bea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031cd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031cd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031ce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031ce2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140031ed7`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140031ed7`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140031ebf`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140031ebf`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031f57`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031fbf`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140032027`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x14003208f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031f57`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031fbf`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140032027`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x14003208f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400320a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009e242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400320a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009e242`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140031ea8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140031ea8`
- `ntdll!NtQuerySystemInformation` at `0x140031ba0`
- `ntdll!NtQuerySystemInformation` at `0x140031ba0`

## pseudocode

```c
__int64 __fastcall WppStart(char a1, unsigned int a2)
{
  PEVENT_TRACE_PROPERTIES v4; // rbx
  char v5; // r12
  bool v6; // r14
  unsigned int v7; // edi
  unsigned int v8; // eax
  char v9; // si
  __int64 Logger; // rax
  __int64 v11; // rcx
  WCHAR *v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // r15
  __int64 v15; // r14
  TRACEHANDLE v16; // rcx
  __int16 SystemInformation; // [rsp+44h] [rbp-A4h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-A0h] BYREF
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+50h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-90h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-80h] BYREF
  __int64 v25; // [rsp+70h] [rbp-78h]
  WCHAR *v26; // [rsp+78h] [rbp-70h]
  __int64 v27; // [rsp+80h] [rbp-68h]
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+88h] [rbp-60h] BYREF

  v4 = 0;
  Properties = 0;
  v5 = 0;
  v6 = 0;
  *(_DWORD *)Data = 0;
  v25 = 259;
  v24 = 0;
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  SystemInformation = 0;
  NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
  if ( (_BYTE)SystemInformation || NtCurrentPeb()->BeingDebugged )
    v5 = 1;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Winlogon", 0, 0x20019u, &hKey);
  if ( !v7 )
  {
    Type = 0;
    cbData = 4;
    v7 = RegQueryValueExW(hKey, L"TracingControlLevel", 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    v6 = v7 == 0;
  }
  if ( !a1 )
  {
    if ( s_WppManualOverride )
    {
LABEL_10:
      v9 = 1;
      goto LABEL_11;
    }
    if ( !v6 )
      goto LABEL_47;
    v8 = *(_DWORD *)Data;
    if ( *(_DWORD *)Data == s_WppControlLevel )
      goto LABEL_47;
LABEL_9:
    s_WppControlLevel = v8;
    goto LABEL_10;
  }
  if ( s_WppManualOverride )
    goto LABEL_10;
  if ( v6 )
  {
    v8 = *(_DWORD *)Data;
    goto LABEL_9;
  }
  if ( a2 )
  {
    s_WppControlLevel = a2;
    goto LABEL_10;
  }
  if ( !v5 )
    goto LABEL_47;
  s_WppControlLevel = 4;
  v9 = 0;
LABEL_11:
  Logger = WppQueryLogger();
  if ( !s_WppLogger )
    s_WppLogger = Logger;
  v11 = 14;
  v27 = 14;
  v12 = s_WppLogFileName;
  v26 = s_WppLogFileName;
  v13 = 0;
  while ( v11 && *v12 )
  {
    v26 = ++v12;
    v27 = --v11;
  }
  if ( !v11 )
    v13 = -2147024809;
  if ( v13 < 0 )
    v25 = 0;
  else
    v25 = 14 - v11;
  if ( v13 < 0 )
  {
    v25 = 0;
    goto LABEL_47;
  }
  if ( (int)StringCchLengthW(s_WppLogSessionName, 0xAu, &v24) >= 0 )
  {
    v14 = v24;
    v24 = (unsigned int)(2 * v24 + 122);
    v15 = v25;
    v7 = WppGrowBuf((void **)&Properties, v24 + 2 * (v25 + 1));
    v4 = Properties;
    if ( !v7 )
    {
      memset_0(Properties, 0, sizeof(struct _EVENT_TRACE_PROPERTIES));
      v4->Wnode.BufferSize = 2 * (v14 + v15) + 124;
      v4->Wnode.Flags = 0x20000;
      v4->Wnode.ClientContext = 2;
      v4->BufferSize = 3;
      v4->MinimumBuffers = 10;
      v4->LogFileMode = 268435458;
      if ( !s_WppLogger )
      {
        v4->MaximumFileSize = 5;
        v4->LogFileNameOffset = 120;
        StringCchCopyW((unsigned __int16 *)&v4[1], v15 + 1, s_WppLogFileName);
      }
      v4->LoggerNameOffset = 2 * v15 + 122;
      StringCchCopyW((unsigned __int16 *)((char *)v4 + (unsigned int)(2 * v15 + 122)), v14 + 1, s_WppLogSessionName);
      if ( v9 && v5 )
      {
        v4->LogFileMode |= 0x80000u;
        v4->FlushTimer = 5;
      }
      v16 = s_WppLogger;
      if ( s_WppLogger )
      {
        ControlTraceW(s_WppLogger, s_WppLogSessionName, v4, 2u);
      }
      else
      {
        if ( !s_WppControlLevel )
          goto LABEL_44;
        MoveFileExW(s_WppLogFileName, s_WppBackupFileName, 1u);
        StartTraceW(&s_WppLogger, s_WppLogSessionName, v4);
      }
      v16 = s_WppLogger;
LABEL_44:
      if ( v16 )
      {
        memset(&EnableParameters, 0, sizeof(EnableParameters));
        EnableParameters.Version = 1;
        EnableTraceEx2(v16, &ProviderId, 1u, s_WppControlLevel, 0xFFFFFFFF, 0, 0, &EnableParameters);
        memset(&EnableParameters, 0, sizeof(EnableParameters));
        EnableParameters.Version = 1;
        EnableTraceEx2(s_WppLogger, &stru_1400B11A0, 1u, s_WppControlLevel, 0xFFFFFFFF, 0, 0, &EnableParameters);
        memset(&EnableParameters, 0, sizeof(EnableParameters));
        EnableParameters.Version = 1;
        EnableTraceEx2(s_WppLogger, &stru_1400B11B0, 1u, s_WppControlLevel, 0xFFFFFFFF, 0, 0, &EnableParameters);
        memset(&EnableParameters, 0, sizeof(EnableParameters));
        EnableParameters.Version = 1;
        EnableTraceEx2(s_WppLogger, &stru_1400B1190, 1u, s_WppControlLevel, 0xFFFFFFFF, 0, 0, &EnableParameters);
        v7 = 0;
      }
      else
      {
        v7 = 13;
      }
    }
  }
LABEL_47:
  if ( v4 )
    LocalFree(v4);
  return v7;
}

```

## disassembly

```asm
0x140031b20  mov     r11, rsp
0x140031b23  mov     [r11+8], rbx
0x140031b27  mov     [r11+18h], rsi
0x140031b2b  push    rdi
0x140031b2c  push    r12
0x140031b2e  push    r13
0x140031b30  push    r14
0x140031b32  push    r15
0x140031b34  sub     rsp, 0C0h
0x140031b3b  mov     rax, cs:__security_cookie
0x140031b42  xor     rax, rsp
0x140031b45  mov     [rsp+0E8h+var_30], rax
0x140031b4d  mov     r15d, edx
0x140031b50  movzx   esi, cl
0x140031b53  xor     r13d, r13d
0x140031b56  mov     ebx, r13d
0x140031b59  mov     [rsp+0E8h+Properties], rbx
0x140031b5e  xor     r12b, r12b
0x140031b61  xor     r14b, r14b
0x140031b64  mov     dword ptr [rsp+0E8h+Data], r13d
0x140031b69  mov     qword ptr [r11-78h], 103h
0x140031b71  mov     [r11-80h], r13
0x140031b75  xorps   xmm0, xmm0
0x140031b78  movups  xmmword ptr [r11-60h], xmm0
0x140031b7d  movups  xmmword ptr [r11-50h], xmm0
0x140031b82  movups  xmmword ptr [r11-40h], xmm0
0x140031b87  mov     [rsp+0E8h+SystemInformation], r13w
0x140031b8d  xor     r9d, r9d; ReturnLength
0x140031b90  mov     r8d, 2; SystemInformationLength
0x140031b96  lea     rdx, [rsp+0E8h+SystemInformation]; SystemInformation
0x140031b9b  mov     ecx, 23h ; '#'; SystemInformationClass
0x140031ba0  call    cs:__imp_NtQuerySystemInformation
0x140031ba6  cmp     byte ptr [rsp+0E8h+SystemInformation], r14b
0x140031bab  jnz     loc_140031D58
0x140031bb1  mov     rax, gs:60h
0x140031bba  cmp     [rax+2], r14b
0x140031bbe  jnz     loc_140031D58
0x140031bc4  mov     [rsp+0E8h+hKey], r13
0x140031bc9  lea     rax, [rsp+0E8h+hKey]
0x140031bce  mov     [rsp+0E8h+phkResult], rax; phkResult
0x140031bd3  mov     r9d, 20019h; samDesired
0x140031bd9  xor     r8d, r8d; ulOptions
0x140031bdc  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Win"...
0x140031be3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140031bea  call    cs:__imp_RegOpenKeyExW
0x140031bf0  mov     edi, eax
0x140031bf2  mov     [rsp+0E8h+var_A8], eax
0x140031bf6  test    eax, eax
0x140031bf8  jz      loc_140031C9C
0x140031bfe  test    sil, sil
0x140031c01  jnz     loc_140031CF4
0x140031c07  cmp     cs:?s_WppManualOverride@@3KA, 0; ulong s_WppManualOverride
0x140031c0e  jnz     short loc_140031C2F
0x140031c10  test    r14b, r14b
0x140031c13  jz      loc_1400320A1
0x140031c19  mov     eax, dword ptr [rsp+0E8h+Data]
0x140031c1d  cmp     eax, cs:?s_WppControlLevel@@3KA; ulong s_WppControlLevel
0x140031c23  jz      loc_1400320A1
0x140031c29  mov     cs:?s_WppControlLevel@@3KA, eax; ulong s_WppControlLevel
0x140031c2f  mov     sil, 1
0x140031c32  call    WppQueryLogger
0x140031c37  cmp     cs:?s_WppLogger@@3_KA, 0; unsigned __int64 s_WppLogger
0x140031c3f  jz      loc_140031D75
0x140031c45  lea     r9, [rsp+0E8h+var_78]
0x140031c4a  mov     r8d, 0Eh
0x140031c50  mov     ecx, r8d
0x140031c53  mov     [rsp+0E8h+var_68], rcx
0x140031c5b  lea     rdx, ?s_WppLogFileName@@3PAGA; "umstartup.etl"
0x140031c62  mov     [rsp+0E8h+var_70], rdx
0x140031c67  mov     eax, r13d
0x140031c6a  test    rcx, rcx
0x140031c6d  jnz     loc_140031D2E
0x140031c73  mov     edx, 80070057h
0x140031c78  test    rcx, rcx
0x140031c7b  cmovz   eax, edx
0x140031c7e  test    eax, eax
0x140031c80  js      loc_140031D50
0x140031c86  sub     r8, rcx
0x140031c89  mov     [r9], r8
0x140031c8c  test    eax, eax
0x140031c8e  jns     loc_140031D81
0x140031c94  mov     [r9], r13
0x140031c97  jmp     loc_1400320A1
0x140031c9c  mov     [rsp+0E8h+Type], r13d
0x140031ca1  mov     [rsp+0E8h+cbData], 4
0x140031ca9  lea     rax, [rsp+0E8h+cbData]
0x140031cae  mov     [rsp+0E8h+lpcbData], rax; lpcbData
0x140031cb3  lea     rax, [rsp+0E8h+Data]
0x140031cb8  mov     [rsp+0E8h+phkResult], rax; lpData
0x140031cbd  lea     r9, [rsp+0E8h+Type]; lpType
0x140031cc2  xor     r8d, r8d; lpReserved
0x140031cc5  lea     rdx, aTracingcontrol; "TracingControlLevel"
0x140031ccc  mov     rcx, [rsp+0E8h+hKey]; hKey
0x140031cd1  call    cs:__imp_RegQueryValueExW
0x140031cd7  mov     edi, eax
0x140031cd9  mov     [rsp+0E8h+var_A8], eax
0x140031cdd  mov     rcx, [rsp+0E8h+hKey]; hKey
0x140031ce2  call    cs:__imp_RegCloseKey
0x140031ce8  test    edi, edi
0x140031cea  jz      short loc_140031D26
0x140031cec  xor     r14b, r14b
0x140031cef  jmp     loc_140031BFE
0x140031cf4  cmp     cs:?s_WppManualOverride@@3KA, 0; ulong s_WppManualOverride
0x140031cfb  jnz     loc_140031C2F
0x140031d01  test    r14b, r14b
0x140031d04  jnz     short loc_140031D60
0x140031d06  test    r15d, r15d
0x140031d09  jnz     short loc_140031D69
0x140031d0b  test    r12b, r12b
0x140031d0e  jz      loc_1400320A1
0x140031d14  mov     cs:?s_WppControlLevel@@3KA, 4; ulong s_WppControlLevel
0x140031d1e  xor     sil, sil
0x140031d21  jmp     loc_140031C32
0x140031d26  mov     r14b, 1
0x140031d29  jmp     loc_140031BFE
0x140031d2e  cmp     [rdx], ax
0x140031d31  jz      loc_140031C73
0x140031d37  add     rdx, 2
0x140031d3b  mov     [rsp+0E8h+var_70], rdx
0x140031d40  dec     rcx
0x140031d43  mov     [rsp+0E8h+var_68], rcx
0x140031d4b  jmp     loc_140031C6A
0x140031d50  mov     [r9], r13
0x140031d53  jmp     loc_140031C8C
0x140031d58  mov     r12b, 1
0x140031d5b  jmp     loc_140031BC4
0x140031d60  mov     eax, dword ptr [rsp+0E8h+Data]
0x140031d64  jmp     loc_140031C29
0x140031d69  mov     cs:?s_WppControlLevel@@3KA, r15d; ulong s_WppControlLevel
0x140031d70  jmp     loc_140031C2F
0x140031d75  mov     cs:?s_WppLogger@@3_KA, rax; unsigned __int64 s_WppLogger
0x140031d7c  jmp     loc_140031C45
0x140031d81  lea     r8, [rsp+0E8h+var_80]; unsigned __int64 *
0x140031d86  mov     edx, 0Ah; unsigned __int64
0x140031d8b  lea     rcx, ?s_WppLogSessionName@@3PAGA; "umstartup"
0x140031d92  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140031d97  test    eax, eax
0x140031d99  js      loc_1400320A1
0x140031d9f  mov     r15, [rsp+0E8h+var_80]
0x140031da4  lea     ecx, ds:7Ah[r15*2]
0x140031dac  mov     eax, ecx
0x140031dae  mov     [rsp+0E8h+var_80], rax
0x140031db3  mov     r14, [rsp+0E8h+var_78]
0x140031db8  lea     edx, [r14+1]
0x140031dbc  lea     edx, [rcx+rdx*2]; unsigned int
0x140031dbf  lea     rcx, [rsp+0E8h+Properties]; void **
0x140031dc4  call    ?WppGrowBuf@@YAKPEAPEAXK@Z; WppGrowBuf(void * *,ulong)
0x140031dc9  mov     edi, eax
0x140031dcb  mov     [rsp+0E8h+var_A8], eax
0x140031dcf  mov     rbx, [rsp+0E8h+Properties]
0x140031dd4  test    eax, eax
0x140031dd6  jnz     loc_1400320A1
0x140031ddc  xor     edx, edx; Val
0x140031dde  mov     r8d, 78h ; 'x'; Size
0x140031de4  mov     rcx, rbx; void *
0x140031de7  call    memset_0
0x140031dec  lea     eax, [r15+r14]
0x140031df0  lea     eax, ds:7Ch[rax*2]
0x140031df7  mov     [rbx], eax
0x140031df9  mov     dword ptr [rbx+2Ch], 20000h
0x140031e00  mov     dword ptr [rbx+28h], 2
0x140031e07  mov     dword ptr [rbx+30h], 3
0x140031e0e  mov     dword ptr [rbx+34h], 0Ah
0x140031e15  mov     dword ptr [rbx+40h], 10000002h
0x140031e1c  cmp     cs:?s_WppLogger@@3_KA, 0; unsigned __int64 s_WppLogger
0x140031e24  jnz     short loc_140031E48
0x140031e26  mov     dword ptr [rbx+3Ch], 5
0x140031e2d  mov     dword ptr [rbx+70h], 78h ; 'x'
0x140031e34  lea     rdx, [r14+1]; unsigned __int64
0x140031e38  lea     rcx, [rbx+78h]; unsigned __int16 *
0x140031e3c  lea     r8, ?s_WppLogFileName@@3PAGA; "umstartup.etl"
0x140031e43  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140031e48  lea     eax, ds:7Ah[r14*2]
0x140031e50  mov     [rbx+74h], eax
0x140031e53  lea     rdx, [r15+1]; unsigned __int64
0x140031e57  mov     ecx, eax
0x140031e59  add     rcx, rbx; unsigned __int16 *
0x140031e5c  lea     r8, ?s_WppLogSessionName@@3PAGA; "umstartup"
0x140031e63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140031e68  test    sil, sil
0x140031e6b  jz      short loc_140031E80
0x140031e6d  test    r12b, r12b
0x140031e70  jz      short loc_140031E80
0x140031e72  or      dword ptr [rbx+40h], 80000h
0x140031e79  mov     dword ptr [rbx+44h], 5
0x140031e80  mov     rcx, cs:?s_WppLogger@@3_KA; TraceHandle
0x140031e87  test    rcx, rcx
0x140031e8a  jnz     short loc_140031EC7
0x140031e8c  cmp     cs:?s_WppControlLevel@@3KA, ecx; ulong s_WppControlLevel
0x140031e92  jz      short loc_140031EE8
0x140031e94  mov     r8d, 1; dwFlags
0x140031e9a  lea     rdx, ?s_WppBackupFileName@@3PAGA; "umstartup000.etl"
0x140031ea1  lea     rcx, ?s_WppLogFileName@@3PAGA; "umstartup.etl"
0x140031ea8  call    cs:__imp_MoveFileExW
0x140031eae  mov     r8, rbx; Properties
0x140031eb1  lea     rdx, ?s_WppLogSessionName@@3PAGA; "umstartup"
0x140031eb8  lea     rcx, ?s_WppLogger@@3_KA; TraceHandle
0x140031ebf  call    cs:__imp_StartTraceW
0x140031ec5  jmp     short loc_140031EDD
0x140031ec7  mov     r9d, 2; ControlCode
0x140031ecd  mov     r8, rbx; Properties
0x140031ed0  lea     rdx, ?s_WppLogSessionName@@3PAGA; "umstartup"
0x140031ed7  call    cs:__imp_ControlTraceW
0x140031edd  mov     [rsp+0E8h+var_A8], eax
0x140031ee1  mov     rcx, cs:?s_WppLogger@@3_KA; TraceHandle
0x140031ee8  test    rcx, rcx
0x140031eeb  jnz     short loc_140031EFB
0x140031eed  mov     edi, 0Dh
0x140031ef2  mov     [rsp+0E8h+var_A8], edi
0x140031ef6  jmp     loc_1400320A1
0x140031efb  xorps   xmm0, xmm0
0x140031efe  movups  xmmword ptr [rsp+0E8h+var_60.Version], xmm0
0x140031f06  movups  xmmword ptr [rsp+0E8h+var_60.SourceId.Data2], xmm0
0x140031f0e  movups  xmmword ptr [rsp+0E8h+var_60.EnableFilterDesc], xmm0
0x140031f16  mov     [rsp+0E8h+var_60.Version], 1
0x140031f21  lea     rax, [rsp+0E8h+var_60]
0x140031f29  mov     [rsp+0E8h+EnableParameters], rax; EnableParameters
0x140031f2e  mov     [rsp+0E8h+Timeout], r13d; Timeout
0x140031f33  mov     [rsp+0E8h+lpcbData], r13; MatchAllKeyword
0x140031f38  mov     edi, 0FFFFFFFFh
0x140031f3d  mov     [rsp+0E8h+phkResult], rdi; MatchAnyKeyword
0x140031f42  movzx   r9d, byte ptr cs:?s_WppControlLevel@@3KA; Level
0x140031f4a  mov     r8d, 1; ControlCode
0x140031f50  lea     rdx, ProviderId; ProviderId
0x140031f57  call    cs:__imp_EnableTraceEx2
0x140031f5d  mov     [rsp+0E8h+var_A8], eax
0x140031f61  xorps   xmm0, xmm0
0x140031f64  movups  xmmword ptr [rsp+0E8h+var_60.Version], xmm0
0x140031f6c  movups  xmmword ptr [rsp+0E8h+var_60.SourceId.Data2], xmm0
0x140031f74  movups  xmmword ptr [rsp+0E8h+var_60.EnableFilterDesc], xmm0
0x140031f7c  mov     [rsp+0E8h+var_60.Version], 1
0x140031f87  lea     rax, [rsp+0E8h+var_60]
0x140031f8f  mov     [rsp+0E8h+EnableParameters], rax; EnableParameters
0x140031f94  mov     [rsp+0E8h+Timeout], r13d; Timeout
0x140031f99  mov     [rsp+0E8h+lpcbData], r13; MatchAllKeyword
0x140031f9e  mov     [rsp+0E8h+phkResult], rdi; MatchAnyKeyword
0x140031fa3  movzx   r9d, byte ptr cs:?s_WppControlLevel@@3KA; Level
0x140031fab  mov     r8d, 1; ControlCode
0x140031fb1  lea     rdx, stru_1400B11A0; ProviderId
0x140031fb8  mov     rcx, cs:?s_WppLogger@@3_KA; TraceHandle
0x140031fbf  call    cs:__imp_EnableTraceEx2
0x140031fc5  mov     [rsp+0E8h+var_A8], eax
0x140031fc9  xorps   xmm0, xmm0
0x140031fcc  movups  xmmword ptr [rsp+0E8h+var_60.Version], xmm0
0x140031fd4  movups  xmmword ptr [rsp+0E8h+var_60.SourceId.Data2], xmm0
0x140031fdc  movups  xmmword ptr [rsp+0E8h+var_60.EnableFilterDesc], xmm0
0x140031fe4  mov     [rsp+0E8h+var_60.Version], 1
0x140031fef  lea     rax, [rsp+0E8h+var_60]
0x140031ff7  mov     [rsp+0E8h+EnableParameters], rax; EnableParameters
0x140031ffc  mov     [rsp+0E8h+Timeout], r13d; Timeout
0x140032001  mov     [rsp+0E8h+lpcbData], r13; MatchAllKeyword
0x140032006  mov     [rsp+0E8h+phkResult], rdi; MatchAnyKeyword
0x14003200b  movzx   r9d, byte ptr cs:?s_WppControlLevel@@3KA; Level
0x140032013  mov     r8d, 1; ControlCode
0x140032019  lea     rdx, stru_1400B11B0; ProviderId
0x140032020  mov     rcx, cs:?s_WppLogger@@3_KA; TraceHandle
0x140032027  call    cs:__imp_EnableTraceEx2
0x14003202d  mov     [rsp+0E8h+var_A8], eax
0x140032031  xorps   xmm0, xmm0
0x140032034  movups  xmmword ptr [rsp+0E8h+var_60.Version], xmm0
0x14003203c  movups  xmmword ptr [rsp+0E8h+var_60.SourceId.Data2], xmm0
0x140032044  movups  xmmword ptr [rsp+0E8h+var_60.EnableFilterDesc], xmm0
0x14003204c  mov     [rsp+0E8h+var_60.Version], 1
0x140032057  lea     rax, [rsp+0E8h+var_60]
0x14003205f  mov     [rsp+0E8h+EnableParameters], rax; EnableParameters
0x140032064  mov     [rsp+0E8h+Timeout], r13d; Timeout
0x140032069  mov     [rsp+0E8h+lpcbData], r13; MatchAllKeyword
0x14003206e  mov     [rsp+0E8h+phkResult], rdi; MatchAnyKeyword
0x140032073  movzx   r9d, byte ptr cs:?s_WppControlLevel@@3KA; Level
0x14003207b  mov     r8d, 1; ControlCode
0x140032081  lea     rdx, stru_1400B1190; ProviderId
0x140032088  mov     rcx, cs:?s_WppLogger@@3_KA; TraceHandle
0x14003208f  call    cs:__imp_EnableTraceEx2
0x140032095  mov     [rsp+0E8h+var_A8], eax
0x140032099  mov     edi, r13d
0x14003209c  mov     [rsp+0E8h+var_A8], r13d
0x1400320a1  test    rbx, rbx
0x1400320a4  jz      short loc_1400320AF
0x1400320a6  mov     rcx, rbx; hMem
0x1400320a9  call    cs:__imp_LocalFree
0x1400320af  mov     eax, edi
0x1400320b1  mov     rcx, [rsp+0E8h+var_30]
0x1400320b9  xor     rcx, rsp; StackCookie
0x1400320bc  call    __security_check_cookie
0x1400320c1  lea     r11, [rsp+0E8h+var_28]
0x1400320c9  mov     rbx, [r11+30h]
0x1400320cd  mov     rsi, [r11+40h]
0x1400320d1  mov     rsp, r11
0x1400320d4  pop     r15
0x1400320d6  pop     r14
0x1400320d8  pop     r13
0x1400320da  pop     r12
0x1400320dc  pop     rdi
0x1400320dd  retn
0x14009e230  push    rbp
0x14009e232  sub     rsp, 40h
0x14009e236  mov     rbp, rdx
0x14009e239  mov     rcx, [rbp+50h]; hMem
0x14009e23d  test    rcx, rcx
0x14009e240  jz      short loc_14009E249
  ... truncated ...
```
