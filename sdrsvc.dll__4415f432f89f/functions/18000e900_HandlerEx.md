# HandlerEx

- ea: `0x18000e900`
- end: `0x18000e9f0`
- name: `HandlerEx`
- size: `240`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x18000d2bc`
- `0x18000dffc`
- `0x18000e420`
- `0x18000e900`
- `0x18001586c`
- `0x180015974`
- `0x18001c7a0`

## string_xrefs

- `0x18000e916`: `CSdRestoreServiceModule::Handler`

## pseudocode

```c
__int64 __fastcall HandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  CSdRestoreServiceModule *v6; // rcx
  void *v7; // r8
  DWORD v8; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  int v11; // ebx
  __int16 v12; // ax
  bool v14; // sf
  CSdRestoreServiceModule *v15; // rcx
  int v16; // [rsp+20h] [rbp-40h] BYREF
  __int16 v17; // [rsp+24h] [rbp-3Ch]
  __int16 v18; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CSdRestoreServiceModule::Handler", 386, 1);
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  v8 = dwControl - 1;
  if ( !v8 )
    goto LABEL_12;
  v9 = v8 - 3;
  if ( !v9 )
  {
    v11 = CSdRestoreServiceModule::_SetServiceStatus(v6, ServiceStatus.dwCurrentState);
    v16 = v11;
    v14 = v11 < 0;
    v12 = 402;
    goto LABEL_10;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_12:
    v11 = CSdRestoreServiceModule::_SetServiceStatus(v6, 3u);
    v16 = v11;
    v12 = 407;
    if ( v11 < 0 )
      goto LABEL_11;
    v17 = 407;
    v11 = CSdRestoreServiceModule::SignalShutdown(v15);
    v16 = v11;
    v14 = v11 < 0;
    v12 = 408;
LABEL_10:
    if ( v14 )
      goto LABEL_11;
    goto LABEL_7;
  }
  if ( v10 != 8 )
  {
    v11 = -2147024776;
    v12 = 424;
    v16 = -2147024776;
LABEL_11:
    v18 = v12;
    goto LABEL_8;
  }
  CSdRestoreServiceModule::_HandlePower(v6, dwEventType, v7);
  v12 = 420;
  v16 = 0;
  v11 = 0;
LABEL_7:
  v17 = v12;
LABEL_8:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return Win32FromHRESULT((unsigned int)v11);
}

```

## disassembly

```asm
0x18000e900  mov     [rsp-8+arg_0], rbx
0x18000e905  mov     [rsp-8+arg_8], rdi
0x18000e90a  push    rbp
0x18000e90b  mov     rbp, rsp
0x18000e90e  sub     rsp, 60h
0x18000e912  mov     edi, edx
0x18000e914  mov     ebx, ecx
0x18000e916  lea     rdx, aCsdrestoreserv_10; "CSdRestoreServiceModule::Handler"
0x18000e91d  mov     r9d, 1; unsigned __int16
0x18000e923  lea     rcx, [rbp+var_40]; this
0x18000e927  mov     r8d, 182h; unsigned __int16
0x18000e92d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e932  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000e93d  mov     edx, 3; unsigned int
0x18000e942  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, 0
0x18000e94d  sub     ebx, 1
0x18000e950  jz      short loc_18000E9C6
0x18000e952  sub     ebx, edx
0x18000e954  jz      short loc_18000E9A7
0x18000e956  sub     ebx, 1
0x18000e959  jz      short loc_18000E9C6
0x18000e95b  cmp     ebx, 8
0x18000e95e  jz      short loc_18000E96F
0x18000e960  mov     ebx, 80070078h
0x18000e965  mov     eax, 1A8h
0x18000e96a  mov     [rbp+var_40], ebx
0x18000e96d  jmp     short loc_18000E9C0
0x18000e96f  mov     edx, edi; unsigned int
0x18000e971  call    ?_HandlePower@CSdRestoreServiceModule@@AEAAJKPEAX@Z; CSdRestoreServiceModule::_HandlePower(ulong,void *)
0x18000e976  mov     eax, 1A4h
0x18000e97b  mov     [rbp+var_40], 0
0x18000e982  xor     ebx, ebx
0x18000e984  mov     [rbp+var_3C], ax
0x18000e988  lea     rcx, [rbp+var_40]; this
0x18000e98c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e991  mov     ecx, ebx
0x18000e993  mov     rbx, [rsp+60h+arg_0]
0x18000e998  mov     rdi, [rsp+60h+arg_8]
0x18000e99d  add     rsp, 60h
0x18000e9a1  pop     rbp
0x18000e9a2  jmp     Win32FromHRESULT
0x18000e9a7  mov     edx, cs:ServiceStatus.dwCurrentState; unsigned int
0x18000e9ad  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000e9b2  mov     ebx, eax
0x18000e9b4  mov     [rbp+var_40], eax
0x18000e9b7  test    eax, eax
0x18000e9b9  mov     eax, 192h
0x18000e9be  jns     short loc_18000E984
0x18000e9c0  mov     [rbp+var_3A], ax
0x18000e9c4  jmp     short loc_18000E988
0x18000e9c6  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000e9cb  mov     ebx, eax
0x18000e9cd  mov     [rbp+var_40], eax
0x18000e9d0  test    eax, eax
0x18000e9d2  mov     eax, 197h
0x18000e9d7  js      short loc_18000E9C0
0x18000e9d9  mov     [rbp+var_3C], ax
0x18000e9dd  call    ?SignalShutdown@CSdRestoreServiceModule@@AEAAJXZ; CSdRestoreServiceModule::SignalShutdown(void)
0x18000e9e2  mov     ebx, eax
0x18000e9e4  mov     [rbp+var_40], eax
0x18000e9e7  test    eax, eax
0x18000e9e9  mov     eax, 198h
0x18000e9ee  jmp     short loc_18000E9BE
```
