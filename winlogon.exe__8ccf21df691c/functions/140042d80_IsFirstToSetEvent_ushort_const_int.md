# _IsFirstToSetEvent(ushort const *,int &)

- ea: `0x140042d80`
- end: `0x140043170`
- name: `?_IsFirstToSetEvent@@YAKPEBGAEAH@Z`
- size: `1008`
- prototype: `unsigned int __fastcall(LPCWSTR lpName, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140034d88`
- `0x140047370`
- `0x1400727a0`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x14000fb30`
- `0x140013050`
- `0x140041c34`
- `0x140042d80`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140042e65`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140042e65`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140042e54`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140042e54`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400430cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400430cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140042fd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140042fd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140043131`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009e8c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140043131`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009e8c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140042eea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004303b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140042eea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004303b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140042e83`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140042e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004301f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400430d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004301f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400430d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004313f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e8b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e8d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004313f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e8b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e8d7`

## pseudocode

```c
__int64 __fastcall _IsFirstToSetEvent(LPCWSTR lpName, int *a2)
{
  HANDLE EventW; // r14
  wchar_t *v5; // rbx
  wchar_t *v6; // rax
  HANDLE MutexW; // rax
  void *v8; // r15
  DWORD LastError; // eax
  DWORD v10; // ebx
  CUser *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // r14d
  CUser *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  BOOL v18; // r12d
  DWORD v19; // eax
  CUser *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  DWORD v23; // eax
  int v25; // [rsp+38h] [rbp-260h]
  wchar_t Str[264]; // [rsp+50h] [rbp-248h] BYREF

  EventW = 0;
  v25 = 0;
  memset_0(Str, 0, 0x208u);
  *a2 = 0;
  if ( (int)StringCchPrintfW(Str, 0x104u, L"Global\\WinLogon-%hs-%ls", "_IsFirstToSetEvent", lpName) < 0
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, Str);
  }
  v5 = wcschr(Str, 0x5Cu);
  while ( 1 )
  {
    v6 = wcsrchr(Str, 0x5Cu);
    if ( v5 == v6 )
      break;
    *v6 = 95;
  }
  MutexW = CreateMutexW(0, 0, Str);
  v8 = MutexW;
  if ( !MutexW )
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_55;
    }
    v12 = 84;
    goto LABEL_14;
  }
  v13 = WaitForSingleObject(MutexW, 0x493E0u);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 == 258 )
    {
      v10 = 258;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v16 = 86;
    }
    else
    {
      if ( v13 == -1 )
      {
        v17 = GetLastError();
        v10 = v17;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v17);
        }
        goto LABEL_31;
      }
      v10 = 1;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_31:
        MicrosoftTelemetryAssertTriggeredArgs("winlogon.exe", v14, v10);
        EventW = 0;
        goto LABEL_55;
      }
      v16 = 87;
    }
    WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
    goto LABEL_31;
  }
  v25 = 1;
  EventW = CreateEventW(0, 1, 0, lpName);
  if ( !EventW )
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_55;
    }
    v12 = 88;
LABEL_14:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, LastError);
LABEL_55:
    v18 = 0;
    goto LABEL_56;
  }
  v18 = GetLastError() == 183;
  v19 = WaitForSingleObject(EventW, 0);
  if ( v19 == -1 )
  {
    v10 = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 89;
      v22 = 0xFFFFFFFFLL;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v22);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  if ( v19 != 258 )
  {
LABEL_54:
    v10 = 0;
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
  }
  if ( SetEvent(EventW) )
  {
    *a2 = 1;
    goto LABEL_54;
  }
  v23 = GetLastError();
  v10 = v23;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 91;
    v22 = v23;
    goto LABEL_42;
  }
LABEL_56:
  if ( v18 )
    CloseHandle(EventW);
  if ( v25 )
    ReleaseMutex(v8);
  if ( v8 )
    CloseHandle(v8);
  return v10;
}

```

## disassembly

```asm
0x140042d80  mov     [rsp+arg_10], rbx
0x140042d85  push    rsi
0x140042d86  push    r12
0x140042d88  push    r13
0x140042d8a  push    r14
0x140042d8c  push    r15
0x140042d8e  sub     rsp, 270h
0x140042d95  mov     rax, cs:__security_cookie
0x140042d9c  xor     rax, rsp
0x140042d9f  mov     [rsp+298h+var_38], rax
0x140042da7  mov     r13, rdx
0x140042daa  mov     r12, rcx
0x140042dad  xor     ebx, ebx
0x140042daf  mov     [rsp+298h+var_250], rbx
0x140042db4  mov     r14d, ebx
0x140042db7  mov     [rsp+298h+var_258], rbx
0x140042dbc  mov     [rsp+298h+var_260], ebx
0x140042dc0  mov     eax, ebx
0x140042dc2  mov     [rsp+298h+var_268], ebx
0x140042dc6  mov     [rsp+298h+var_25C], ebx
0x140042dca  xor     edx, edx; Val
0x140042dcc  mov     r8d, 208h; Size
0x140042dd2  lea     rcx, [rsp+298h+Str]; void *
0x140042dd7  call    memset_0
0x140042ddc  mov     [r13+0], ebx
0x140042de0  mov     [rsp+298h+var_278], r12
0x140042de5  lea     r9, aIsfirsttosetev; "_IsFirstToSetEvent"
0x140042dec  lea     r8, aGlobalWinlogon; "Global\\WinLogon-%hs-%ls"
0x140042df3  mov     edx, 104h; unsigned __int64
0x140042df8  lea     rcx, [rsp+298h+Str]; unsigned __int16 *
0x140042dfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140042e02  test    eax, eax
0x140042e04  jns     short loc_140042E3F
0x140042e06  lea     rsi, WPP_GLOBAL_Control
0x140042e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140042e14  cmp     rcx, rsi
0x140042e17  jz      short loc_140042E46
0x140042e19  test    byte ptr [rcx+1Ch], 10h
0x140042e1d  jz      short loc_140042E46
0x140042e1f  cmp     byte ptr [rcx+19h], 3
0x140042e23  jb      short loc_140042E46
0x140042e25  lea     edx, [rbx+53h]
0x140042e28  lea     r9, [rsp+298h+Str]
0x140042e2d  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140042e34  mov     rcx, [rcx+10h]
0x140042e38  call    WPP_SF_S
0x140042e3d  jmp     short loc_140042E46
0x140042e3f  lea     rsi, WPP_GLOBAL_Control
0x140042e46  mov     r15d, 5Ch ; '\'
0x140042e4c  mov     edx, r15d; Ch
0x140042e4f  lea     rcx, [rsp+298h+Str]; Str
0x140042e54  call    cs:__imp_wcschr
0x140042e5a  mov     rbx, rax
0x140042e5d  mov     edx, r15d; Ch
0x140042e60  lea     rcx, [rsp+298h+Str]; Str
0x140042e65  call    cs:__imp_wcsrchr
0x140042e6b  cmp     rbx, rax
0x140042e6e  jz      short loc_140042E7A
0x140042e70  mov     ecx, 5Fh ; '_'
0x140042e75  mov     [rax], cx
0x140042e78  jmp     short loc_140042E5D
0x140042e7a  lea     r8, [rsp+298h+Str]; lpName
0x140042e7f  xor     edx, edx; bInitialOwner
0x140042e81  xor     ecx, ecx; lpMutexAttributes
0x140042e83  call    cs:__imp_CreateMutexW
0x140042e89  mov     r15, rax
0x140042e8c  mov     [rsp+298h+var_250], rax
0x140042e91  test    rax, rax
0x140042e94  jnz     short loc_140042EE2
0x140042e96  call    cs:__imp_GetLastError
0x140042e9c  mov     ebx, eax
0x140042e9e  mov     [rsp+298h+var_264], eax
0x140042ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x140042ea9  cmp     rcx, rsi
0x140042eac  jz      loc_140043114
0x140042eb2  test    byte ptr [rcx+1Ch], 10h
0x140042eb6  jz      loc_140043114
0x140042ebc  cmp     byte ptr [rcx+19h], 2
0x140042ec0  jb      loc_140043114
0x140042ec6  lea     edx, [r15+54h]
0x140042eca  mov     r9d, eax
0x140042ecd  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140042ed4  mov     rcx, [rcx+10h]
0x140042ed8  call    WPP_SF_d
0x140042edd  jmp     loc_140043114
0x140042ee2  mov     edx, 493E0h; dwMilliseconds
0x140042ee7  mov     rcx, r15; hHandle
0x140042eea  call    cs:__imp_WaitForSingleObject
0x140042ef0  mov     r14d, eax
0x140042ef3  test    eax, eax
0x140042ef5  jz      loc_140042FC0
0x140042efb  mov     ecx, 102h
0x140042f00  cmp     eax, ecx
0x140042f02  jz      short loc_140042F71
0x140042f04  cmp     eax, 0FFFFFFFFh
0x140042f07  jz      short loc_140042F33
0x140042f09  mov     ebx, 1
0x140042f0e  mov     [rsp+298h+var_264], ebx
0x140042f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140042f19  cmp     rcx, rsi
0x140042f1c  jz      loc_140042FA4
0x140042f22  test    byte ptr [rcx+1Ch], 10h
0x140042f26  jz      short loc_140042FA4
0x140042f28  cmp     byte ptr [rcx+19h], 2
0x140042f2c  jb      short loc_140042FA4
0x140042f2e  lea     edx, [rbx+56h]
0x140042f31  jmp     short loc_140042F94
0x140042f33  call    cs:__imp_GetLastError
0x140042f39  mov     ebx, eax
0x140042f3b  mov     [rsp+298h+var_264], eax
0x140042f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140042f46  cmp     rcx, rsi
0x140042f49  jz      short loc_140042FA4
0x140042f4b  test    byte ptr [rcx+1Ch], 10h
0x140042f4f  jz      short loc_140042FA4
0x140042f51  cmp     byte ptr [rcx+19h], 2
0x140042f55  jb      short loc_140042FA4
0x140042f57  mov     edx, 55h ; 'U'
0x140042f5c  mov     r9d, eax
0x140042f5f  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140042f66  mov     rcx, [rcx+10h]
0x140042f6a  call    WPP_SF_d
0x140042f6f  jmp     short loc_140042FA4
0x140042f71  mov     ebx, ecx
0x140042f73  mov     [rsp+298h+var_264], ecx
0x140042f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140042f7e  cmp     rcx, rsi
0x140042f81  jz      short loc_140042FA4
0x140042f83  test    byte ptr [rcx+1Ch], 10h
0x140042f87  jz      short loc_140042FA4
0x140042f89  cmp     byte ptr [rcx+19h], 2
0x140042f8d  jb      short loc_140042FA4
0x140042f8f  mov     edx, 56h ; 'V'
0x140042f94  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140042f9b  mov     rcx, [rcx+10h]
0x140042f9f  call    WPP_SF_
0x140042fa4  mov     r8d, ebx; __annotation("Debug", "TelemetryAssert", "false", "Failed when acquiring shared mutex in _IsFirstToSetEvent")
0x140042fa7  mov     edx, r14d
0x140042faa  lea     rcx, aWinlogonExe; "winlogon.exe"
0x140042fb1  call    MicrosoftTelemetryAssertTriggeredArgs
0x140042fb6  mov     r14, [rsp+298h+var_258]
0x140042fbb  jmp     loc_140043114
0x140042fc0  mov     ebx, 1
0x140042fc5  mov     [rsp+298h+var_260], ebx
0x140042fc9  mov     r9, r12; lpName
0x140042fcc  xor     r8d, r8d; bInitialState
0x140042fcf  mov     edx, ebx; bManualReset
0x140042fd1  xor     ecx, ecx; lpEventAttributes
0x140042fd3  call    cs:__imp_CreateEventW
0x140042fd9  mov     r14, rax
0x140042fdc  mov     [rsp+298h+var_258], rax
0x140042fe1  test    rax, rax
0x140042fe4  jnz     short loc_14004301F
0x140042fe6  call    cs:__imp_GetLastError
0x140042fec  mov     ebx, eax
0x140042fee  mov     [rsp+298h+var_264], eax
0x140042ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140042ff9  cmp     rcx, rsi
0x140042ffc  jz      loc_140043114
0x140043002  test    byte ptr [rcx+1Ch], 10h
0x140043006  jz      loc_140043114
0x14004300c  cmp     byte ptr [rcx+19h], 2
0x140043010  jb      loc_140043114
0x140043016  lea     edx, [r14+58h]
0x14004301a  jmp     loc_140042ECA
0x14004301f  call    cs:__imp_GetLastError
0x140043025  xor     r12d, r12d
0x140043028  cmp     eax, 0B7h
0x14004302d  setz    r12b
0x140043031  mov     [rsp+298h+var_25C], r12d
0x140043036  xor     edx, edx; dwMilliseconds
0x140043038  mov     rcx, r14; hHandle
0x14004303b  call    cs:__imp_WaitForSingleObject
0x140043041  cmp     eax, 0FFFFFFFFh
0x140043044  jnz     short loc_140043094
0x140043046  call    cs:__imp_GetLastError
0x14004304c  mov     ebx, eax
0x14004304e  mov     [rsp+298h+var_264], eax
0x140043052  mov     rcx, cs:WPP_GLOBAL_Control
0x140043059  cmp     rcx, rsi
0x14004305c  jz      loc_140043119
0x140043062  test    byte ptr [rcx+1Ch], 10h
0x140043066  jz      loc_140043119
0x14004306c  cmp     byte ptr [rcx+19h], 2
0x140043070  jb      loc_140043119
0x140043076  mov     edx, 59h ; 'Y'
0x14004307b  or      r9d, 0FFFFFFFFh
0x14004307f  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140043086  mov     rcx, [rcx+10h]
0x14004308a  call    WPP_SF_d
0x14004308f  jmp     loc_140043119
0x140043094  mov     ecx, 102h
0x140043099  cmp     eax, ecx
0x14004309b  jnz     short loc_14004310C
0x14004309d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400430a4  cmp     rcx, rsi
0x1400430a7  jz      short loc_1400430CA
0x1400430a9  test    byte ptr [rcx+1Ch], 10h
0x1400430ad  jz      short loc_1400430CA
0x1400430af  cmp     byte ptr [rcx+19h], 4
0x1400430b3  jb      short loc_1400430CA
0x1400430b5  mov     edx, 5Ah ; 'Z'
0x1400430ba  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400430c1  mov     rcx, [rcx+10h]
0x1400430c5  call    WPP_SF_
0x1400430ca  mov     rcx, r14; hEvent
0x1400430cd  call    cs:__imp_SetEvent
0x1400430d3  test    eax, eax
0x1400430d5  jnz     short loc_140043108
0x1400430d7  call    cs:__imp_GetLastError
0x1400430dd  mov     ebx, eax
0x1400430df  mov     [rsp+298h+var_264], eax
0x1400430e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400430ea  cmp     rcx, rsi
0x1400430ed  jz      short loc_140043119
0x1400430ef  test    byte ptr [rcx+1Ch], 10h
0x1400430f3  jz      short loc_140043119
0x1400430f5  cmp     byte ptr [rcx+19h], 2
0x1400430f9  jb      short loc_140043119
0x1400430fb  mov     edx, 5Bh ; '['
0x140043100  mov     r9d, eax
0x140043103  jmp     loc_14004307F
0x140043108  mov     [r13+0], ebx
0x14004310c  xor     ebx, ebx
0x14004310e  mov     [rsp+298h+var_264], ebx
0x140043112  jmp     short loc_140043119
0x140043114  mov     r12d, [rsp+298h+var_268]
0x140043119  test    r12d, r12d
0x14004311c  jz      short loc_140043127
0x14004311e  mov     rcx, r14; hObject
0x140043121  call    cs:__imp_CloseHandle
0x140043127  cmp     [rsp+298h+var_260], 0
0x14004312c  jz      short loc_140043137
0x14004312e  mov     rcx, r15; hMutex
0x140043131  call    cs:__imp_ReleaseMutex
0x140043137  test    r15, r15
0x14004313a  jz      short loc_140043145
0x14004313c  mov     rcx, r15; hObject
0x14004313f  call    cs:__imp_CloseHandle
0x140043145  mov     eax, ebx
0x140043147  mov     rcx, [rsp+298h+var_38]
0x14004314f  xor     rcx, rsp; StackCookie
0x140043152  call    __security_check_cookie
0x140043157  mov     rbx, [rsp+298h+arg_10]
0x14004315f  add     rsp, 270h
0x140043166  pop     r15
0x140043168  pop     r14
0x14004316a  pop     r13
0x14004316c  pop     r12
0x14004316e  pop     rsi
0x14004316f  retn
0x14009e8a3  push    rbp
0x14009e8a5  sub     rsp, 30h
0x14009e8a9  mov     rbp, rdx
0x14009e8ac  cmp     dword ptr [rbp+3Ch], 0
0x14009e8b0  jz      short loc_14009E8BD
0x14009e8b2  mov     rcx, [rbp+40h]; hObject
0x14009e8b6  call    cs:__imp_CloseHandle
0x14009e8bc  nop
0x14009e8bd  cmp     dword ptr [rbp+38h], 0
0x14009e8c1  jz      short loc_14009E8CE
0x14009e8c3  mov     rcx, [rbp+48h]; hMutex
0x14009e8c7  call    cs:__imp_ReleaseMutex
0x14009e8cd  nop
0x14009e8ce  mov     rcx, [rbp+48h]; hObject
0x14009e8d2  test    rcx, rcx
0x14009e8d5  jz      short loc_14009E8DE
0x14009e8d7  call    cs:__imp_CloseHandle
0x14009e8dd  nop
0x14009e8de  add     rsp, 30h
0x14009e8e2  pop     rbp
0x14009e8e3  retn
```
