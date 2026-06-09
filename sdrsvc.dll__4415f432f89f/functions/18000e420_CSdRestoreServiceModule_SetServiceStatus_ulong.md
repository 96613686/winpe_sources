# CSdRestoreServiceModule::_SetServiceStatus(ulong)

- ea: `0x18000e420`
- end: `0x18000e4e7`
- name: `?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z`
- size: `199`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *this, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000d0a0`
- `0x18000e900`

## callees

- `0x18000e420`
- `0x18000ea34`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e4a4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e4a4`

## string_xrefs

- `0x18000e42d`: `CSdRestoreServiceModule::_SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::_SetServiceStatus(CSdRestoreServiceModule *this, DWORD a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v6; // rcx
  unsigned int v8; // [rsp+20h] [rbp-48h] BYREF
  __int16 v9; // [rsp+24h] [rbp-44h]
  __int16 v10; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CSdRestoreServiceModule::_SetServiceStatus", 501, 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, a2);
  if ( !g_Service )
  {
    LastFailureAsHRESULT = -2130706378;
    v10 = 505;
LABEL_9:
    v8 = LastFailureAsHRESULT;
    goto LABEL_10;
  }
  v8 = 0;
  v9 = 505;
  ServiceStatus.dwCurrentState = a2;
  if ( SetServiceStatus(g_Service, &ServiceStatus) )
  {
    LastFailureAsHRESULT = 0;
    v9 = 509;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
  v8 = LastFailureAsHRESULT;
  v10 = 509;
LABEL_10:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000e420  push    rbx
0x18000e422  sub     rsp, 60h
0x18000e426  mov     ebx, edx
0x18000e428  lea     rcx, [rsp+68h+var_48]; this
0x18000e42d  lea     rdx, aCsdrestoreserv_3; "CSdRestoreServiceModule::_SetServiceSta"...
0x18000e434  mov     r9d, 1; unsigned __int16
0x18000e43a  mov     r8d, 1F5h; unsigned __int16
0x18000e440  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e445  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e44c  lea     rax, WPP_GLOBAL_Control
0x18000e453  cmp     rcx, rax
0x18000e456  jz      short loc_18000E46D
0x18000e458  test    dword ptr [rcx+1Ch], 8000000h
0x18000e45f  jz      short loc_18000E46D
0x18000e461  mov     rcx, [rcx+10h]
0x18000e465  mov     r9d, ebx
0x18000e468  call    WPP_SF_L
0x18000e46d  mov     rcx, cs:?g_Service@@3VCSdRestoreServiceModule@@A; hServiceStatus
0x18000e474  mov     eax, 1F9h
0x18000e479  test    rcx, rcx
0x18000e47c  jnz     short loc_18000E48A
0x18000e47e  mov     ebx, 81000036h
0x18000e483  mov     [rsp+68h+var_42], ax
0x18000e488  jmp     short loc_18000E4D1
0x18000e48a  lea     rdx, ServiceStatus; lpServiceStatus
0x18000e491  mov     [rsp+68h+var_48], 0
0x18000e499  mov     [rsp+68h+var_44], ax
0x18000e49e  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000e4a4  call    cs:__imp_SetServiceStatus
0x18000e4aa  test    eax, eax
0x18000e4ac  jnz     short loc_18000E4C5
0x18000e4ae  call    GetLastFailureAsHRESULT
0x18000e4b3  mov     ebx, eax
0x18000e4b5  mov     [rsp+68h+var_48], eax
0x18000e4b9  mov     eax, 1FDh
0x18000e4be  mov     [rsp+68h+var_42], ax
0x18000e4c3  jmp     short loc_18000E4D5
0x18000e4c5  mov     eax, 1FDh
0x18000e4ca  xor     ebx, ebx
0x18000e4cc  mov     [rsp+68h+var_44], ax
0x18000e4d1  mov     [rsp+68h+var_48], ebx
0x18000e4d5  lea     rcx, [rsp+68h+var_48]; this
0x18000e4da  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e4df  mov     eax, ebx
0x18000e4e1  add     rsp, 60h
0x18000e4e5  pop     rbx
0x18000e4e6  retn
```
