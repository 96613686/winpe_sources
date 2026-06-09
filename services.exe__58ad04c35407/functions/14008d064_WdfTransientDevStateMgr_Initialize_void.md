# WdfTransientDevStateMgr::Initialize(void)

- ea: `0x14008d064`
- end: `0x14008d18e`
- name: `?Initialize@WdfTransientDevStateMgr@@AEAAKXZ`
- size: `298`
- prototype: `unsigned int __fastcall(WdfTransientDevStateMgr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14008cfa4`

## callees

- `0x140004c58`
- `0x14008d064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14008d0ed`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14008d0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d153`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14008d080`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14008d080`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x14008d143`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x14008d143`

## pseudocode

```c
__int64 __fastcall WdfTransientDevStateMgr::Initialize(WdfTransientDevStateMgr *this)
{
  __int64 DeviceInfoList; // rax
  DWORD LastError; // ebx
  PRPC_ASYNC_STATE v4; // rcx
  __int64 v5; // rdx
  HANDLE WaitableTimer; // rax
  __int64 v7; // rax

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *((_QWORD *)this + 2) = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      v5 = 10;
LABEL_6:
      WPP_SF_d(v4->u.APC.hThread, v5, WPP_71af4fcb00c232e63b20c00469bb0744_Traceguids, LastError);
    }
  }
  else
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)this + 3) = WaitableTimer;
    if ( WaitableTimer )
    {
      v7 = RegisterWaitForSingleObjectEx(WaitableTimer, WdfTransientDevStateMgr::TimerCallback, this, 0xFFFFFFFFLL, 0);
      *((_QWORD *)this + 4) = v7;
      if ( v7 != -1 )
        return 0;
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v5 = 12;
        goto LABEL_6;
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v5 = 11;
        goto LABEL_6;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x14008d064  push    rbx
0x14008d066  sub     rsp, 30h
0x14008d06a  mov     rbx, rcx
0x14008d06d  mov     [rsp+38h+var_18], 0
0x14008d076  xor     ecx, ecx
0x14008d078  xor     r9d, r9d
0x14008d07b  xor     r8d, r8d
0x14008d07e  xor     edx, edx
0x14008d080  call    cs:__imp_DevObjCreateDeviceInfoList
0x14008d086  mov     [rbx+10h], rax
0x14008d08a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008d08e  jnz     short loc_14008D0E0
0x14008d090  call    cs:__imp_GetLastError
0x14008d096  mov     ebx, eax
0x14008d098  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d09f  lea     rax, WPP_GLOBAL_Control
0x14008d0a6  cmp     rcx, rax
0x14008d0a9  jz      loc_14008D186
0x14008d0af  test    byte ptr [rcx+44h], 1
0x14008d0b3  jz      loc_14008D186
0x14008d0b9  cmp     byte ptr [rcx+41h], 2
0x14008d0bd  jb      loc_14008D186
0x14008d0c3  mov     edx, 0Ah
0x14008d0c8  mov     rcx, [rcx+38h]
0x14008d0cc  lea     r8, WPP_71af4fcb00c232e63b20c00469bb0744_Traceguids
0x14008d0d3  mov     r9d, ebx
0x14008d0d6  call    WPP_SF_d
0x14008d0db  jmp     loc_14008D186
0x14008d0e0  mov     r9d, 1F0003h; dwDesiredAccess
0x14008d0e6  xor     r8d, r8d; dwFlags
0x14008d0e9  xor     edx, edx; lpTimerName
0x14008d0eb  xor     ecx, ecx; lpTimerAttributes
0x14008d0ed  call    cs:__imp_CreateWaitableTimerExW
0x14008d0f3  mov     [rbx+18h], rax
0x14008d0f7  test    rax, rax
0x14008d0fa  jnz     short loc_14008D12A
0x14008d0fc  call    cs:__imp_GetLastError
0x14008d102  mov     ebx, eax
0x14008d104  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d10b  lea     rax, WPP_GLOBAL_Control
0x14008d112  cmp     rcx, rax
0x14008d115  jz      short loc_14008D186
0x14008d117  test    byte ptr [rcx+44h], 1
0x14008d11b  jz      short loc_14008D186
0x14008d11d  cmp     byte ptr [rcx+41h], 2
0x14008d121  jb      short loc_14008D186
0x14008d123  mov     edx, 0Bh
0x14008d128  jmp     short loc_14008D0C8
0x14008d12a  or      r9d, 0FFFFFFFFh
0x14008d12e  mov     dword ptr [rsp+38h+var_18], 0
0x14008d136  mov     r8, rbx
0x14008d139  lea     rdx, ?TimerCallback@WdfTransientDevStateMgr@@CAXPEAXE@Z; WdfTransientDevStateMgr::TimerCallback(void *,uchar)
0x14008d140  mov     rcx, rax
0x14008d143  call    cs:__imp_RegisterWaitForSingleObjectEx
0x14008d149  mov     [rbx+20h], rax
0x14008d14d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008d151  jnz     short loc_14008D184
0x14008d153  call    cs:__imp_GetLastError
0x14008d159  mov     ebx, eax
0x14008d15b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d162  lea     rax, WPP_GLOBAL_Control
0x14008d169  cmp     rcx, rax
0x14008d16c  jz      short loc_14008D186
0x14008d16e  test    byte ptr [rcx+44h], 1
0x14008d172  jz      short loc_14008D186
0x14008d174  cmp     byte ptr [rcx+41h], 2
0x14008d178  jb      short loc_14008D186
0x14008d17a  mov     edx, 0Ch
0x14008d17f  jmp     loc_14008D0C8
0x14008d184  xor     ebx, ebx
0x14008d186  mov     eax, ebx
0x14008d188  add     rsp, 30h
0x14008d18c  pop     rbx
0x14008d18d  retn
```
