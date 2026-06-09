# WaitOnReadyForConnectionsEvent(void)

- ea: `0x100428c60`
- end: `0x100428d2c`
- name: `?WaitOnReadyForConnectionsEvent@@YAXXZ`
- size: `204`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x100428d40`
- `0x100428d70`

## callees

- `0x100428c60`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100428cd0`
- `KERNEL32!WaitForSingleObject` at `0x100428cd0`
- `KERNEL32!Sleep` at `0x100428c99`
- `KERNEL32!Sleep` at `0x100428c99`
- `sqlmin!?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ` at `0x100428c7f`
- `sqlmin!?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ` at `0x100428c9f`
- `sqlmin!?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ` at `0x100428c7f`
- `sqlmin!?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ` at `0x100428c9f`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428c70`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428cc0`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428c70`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428cc0`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428cf1`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428d0b`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428d25`

## string_xrefs

- `0x100428c67`: `Waiting for ready-for-connections event to be initialized.`
- `0x100428d1a`: `Ready-for-connections event signalled.`
- `0x100428cb7`: `Waiting for ready-for-connections event to be signalled.`
- `0x100428ce6`: `Failed to wait on ready-for-connections event.`
- `0x100428d00`: `Ready-for-connections event timed out.`

## pseudocode

```c
void __fastcall WaitOnReadyForConnectionsEvent(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE hHandle; // [rsp+30h] [rbp+8h]

  LOBYTE(a3) = 1;
  LOBYTE(a2) = 4;
  RgClient_WriteETWTrace(L"Waiting for ready-for-connections event to be initialized.", a2, a3);
  for ( hHandle = (HANDLE)StartUp::GetReadyForConnectionsEventNodeLevelHandle();
        !hHandle;
        hHandle = (HANDLE)StartUp::GetReadyForConnectionsEventNodeLevelHandle() )
  {
    Sleep(0x3E8u);
  }
  LOBYTE(v4) = 1;
  LOBYTE(v3) = 4;
  RgClient_WriteETWTrace(L"Waiting for ready-for-connections event to be signalled.", v3, v4);
  v5 = WaitForSingleObject(hHandle, 0xFFFFFFFF);
  LOBYTE(v7) = 1;
  if ( v5 )
  {
    if ( v5 == 258 )
    {
      LOBYTE(v6) = 3;
      RgClient_WriteETWTrace(L"Ready-for-connections event timed out.", v6, v7);
    }
    else
    {
      LOBYTE(v6) = 2;
      RgClient_WriteETWTrace(L"Failed to wait on ready-for-connections event.", v6, v7);
    }
  }
  else
  {
    LOBYTE(v6) = 4;
    RgClient_WriteETWTrace(L"Ready-for-connections event signalled.", v6, v7);
  }
}

```

## disassembly

```asm
0x100428c60  sub     rsp, 28h
0x100428c64  mov     r8b, 1
0x100428c67  lea     rcx, aWaitingForRead; "Waiting for ready-for-connections event"...
0x100428c6e  mov     dl, 4
0x100428c70  call    cs:__imp_RgClient_WriteETWTrace
0x100428c76  mov     [rsp+28h+hHandle], 0
0x100428c7f  call    cs:__imp_?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ; StartUp::GetReadyForConnectionsEventNodeLevelHandle(void)
0x100428c85  mov     [rsp+28h+hHandle], rax
0x100428c8a  mov     rax, [rsp+28h+hHandle]
0x100428c8f  test    rax, rax
0x100428c92  jnz     short loc_100428CB4
0x100428c94  mov     ecx, 3E8h; dwMilliseconds
0x100428c99  call    cs:__imp_Sleep
0x100428c9f  call    cs:__imp_?GetReadyForConnectionsEventNodeLevelHandle@StartUp@@SAREAXXZ; StartUp::GetReadyForConnectionsEventNodeLevelHandle(void)
0x100428ca5  mov     [rsp+28h+hHandle], rax
0x100428caa  mov     rax, [rsp+28h+hHandle]
0x100428caf  test    rax, rax
0x100428cb2  jz      short loc_100428C94
0x100428cb4  mov     r8b, 1
0x100428cb7  lea     rcx, aWaitingForRead_0; "Waiting for ready-for-connections event"...
0x100428cbe  mov     dl, 4
0x100428cc0  call    cs:__imp_RgClient_WriteETWTrace
0x100428cc6  mov     rcx, [rsp+28h+hHandle]; hHandle
0x100428ccb  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x100428cd0  call    cs:__imp_WaitForSingleObject
0x100428cd6  mov     r8b, 1
0x100428cd9  test    eax, eax
0x100428cdb  jz      short loc_100428D18
0x100428cdd  cmp     eax, 102h
0x100428ce2  jz      short loc_100428CFE
0x100428ce4  mov     dl, 2
0x100428ce6  lea     rcx, aFailedToWaitOn_0; "Failed to wait on ready-for-connections"...
0x100428ced  add     rsp, 28h
0x100428cf1  jmp     cs:__imp_RgClient_WriteETWTrace
0x100428cfe  mov     dl, 3
0x100428d00  lea     rcx, aReadyForConnec_0; "Ready-for-connections event timed out."
0x100428d07  add     rsp, 28h
0x100428d0b  jmp     cs:__imp_RgClient_WriteETWTrace
0x100428d18  mov     dl, 4
0x100428d1a  lea     rcx, aReadyForConnec; "Ready-for-connections event signalled."
0x100428d21  add     rsp, 28h
0x100428d25  jmp     cs:__imp_RgClient_WriteETWTrace
```
