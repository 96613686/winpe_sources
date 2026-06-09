# CSdRestoreServiceModule::Run(void)

- ea: `0x18000cfb8`
- end: `0x18000d09a`
- name: `?Run@CSdRestoreServiceModule@@AEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000d0a0`

## callees

- `0x18000cfb8`
- `0x18000eabc`
- `0x18001586c`
- `0x180015974`
- `0x18001c454`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d008`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d008`

## string_xrefs

- `0x18000cfc4`: `CSdRestoreServiceModule::Run`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::Run(CSdRestoreServiceModule *this)
{
  int LastFailureAsHRESULT; // ebx
  __int16 v2; // ax
  __int64 v3; // rcx
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-48h] BYREF
  __int16 v7; // [rsp+24h] [rbp-44h]
  __int16 v8; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "CSdRestoreServiceModule::Run", 640, 1);
  LastFailureAsHRESULT = SxSetProcessPriorities();
  v6 = LastFailureAsHRESULT;
  v2 = 643;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_2;
  v7 = 643;
  if ( WaitForSingleObject(hTimer, 0xFFFFFFFF) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v3);
    v6 = LastFailureAsHRESULT;
    v2 = 647;
LABEL_2:
    v8 = v2;
    goto LABEL_10;
  }
  LastFailureAsHRESULT = 0;
  v6 = 0;
  v7 = 647;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v4 = "Shutdown";
    if ( !dword_18002E208 )
      v4 = "Idle timeout";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids, v4);
    LastFailureAsHRESULT = v6;
  }
LABEL_10:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000cfb8  push    rbx
0x18000cfba  sub     rsp, 60h
0x18000cfbe  mov     r9d, 1; unsigned __int16
0x18000cfc4  lea     rdx, aCsdrestoreserv_6; "CSdRestoreServiceModule::Run"
0x18000cfcb  mov     r8d, 280h; unsigned __int16
0x18000cfd1  lea     rcx, [rsp+68h+var_48]; this
0x18000cfd6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000cfdb  call    ?SxSetProcessPriorities@@YAJW4_IO_PRIORITY_HINT@@KE@Z; SxSetProcessPriorities(_IO_PRIORITY_HINT,ulong,uchar)
0x18000cfe0  mov     ebx, eax
0x18000cfe2  mov     [rsp+68h+var_48], eax
0x18000cfe6  test    eax, eax
0x18000cfe8  mov     eax, 283h
0x18000cfed  jns     short loc_18000CFF9
0x18000cfef  mov     [rsp+68h+var_42], ax
0x18000cff4  jmp     loc_18000D088
0x18000cff9  mov     rcx, cs:hTimer; hHandle
0x18000d000  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d003  mov     [rsp+68h+var_44], ax
0x18000d008  call    cs:__imp_WaitForSingleObject
0x18000d00e  test    eax, eax
0x18000d010  jz      short loc_18000D024
0x18000d012  call    GetLastFailureAsHRESULT
0x18000d017  mov     ebx, eax
0x18000d019  mov     [rsp+68h+var_48], eax
0x18000d01d  mov     eax, 287h
0x18000d022  jmp     short loc_18000CFEF
0x18000d024  xor     ebx, ebx
0x18000d026  mov     eax, 287h
0x18000d02b  mov     [rsp+68h+var_48], ebx
0x18000d02f  mov     [rsp+68h+var_44], ax
0x18000d034  mov     rax, cs:WPP_GLOBAL_Control
0x18000d03b  lea     rcx, WPP_GLOBAL_Control
0x18000d042  cmp     rax, rcx
0x18000d045  jz      short loc_18000D088
0x18000d047  test    dword ptr [rax+1Ch], 8000000h
0x18000d04e  jz      short loc_18000D088
0x18000d050  mov     eax, cs:dword_18002E208
0x18000d056  lea     rcx, aIdleTimeout; "Idle timeout"
0x18000d05d  test    eax, eax
0x18000d05f  lea     r9, aShutdown; "Shutdown"
0x18000d066  lea     edx, [rbx+0Bh]
0x18000d069  cmovz   r9, rcx
0x18000d06d  lea     r8, WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids
0x18000d074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d07b  mov     rcx, [rcx+10h]
0x18000d07f  call    WPP_SF_s
0x18000d084  mov     ebx, [rsp+68h+var_48]
0x18000d088  lea     rcx, [rsp+68h+var_48]; this
0x18000d08d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d092  mov     eax, ebx
0x18000d094  add     rsp, 60h
0x18000d098  pop     rbx
0x18000d099  retn
```
