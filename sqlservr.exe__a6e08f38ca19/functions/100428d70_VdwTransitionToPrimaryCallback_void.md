# VdwTransitionToPrimaryCallback(void)

- ea: `0x100428d70`
- end: `0x100428e06`
- name: `?VdwTransitionToPrimaryCallback@@YAXXZ`
- size: `150`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x100428c60`
- `0x100428d70`

## import_xrefs

- `KERNEL32!SetEvent` at `0x100428dc8`
- `KERNEL32!SetEvent` at `0x100428dc8`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x100428dae`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x100428dae`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428d80`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428d80`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428de2`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100428dff`

## string_xrefs

- `0x100428da7`: `SQL.Config`
- `0x100428df1`: `Failed to create and signal transition to primary event.`

## pseudocode

```c
void __fastcall VdwTransitionToPrimaryCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE hEvent; // [rsp+40h] [rbp+8h]

  LOBYTE(a3) = 1;
  LOBYTE(a2) = 4;
  RgClient_WriteETWTrace(L"Entering transition to primary callback.", a2, a3);
  WaitOnReadyForConnectionsEvent(v4, v3, v5);
  hEvent = StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(
             L"SQL.Config",
             L"SQL",
             L"TransitionToPrimaryEventName",
             1,
             0);
  if ( hEvent && SetEvent(hEvent) )
  {
    LOBYTE(v6) = 4;
    LOBYTE(v7) = 1;
    RgClient_WriteETWTrace(L"Transition to primary event signalled.", v6, v7);
  }
  else
  {
    LOBYTE(v6) = 2;
    LOBYTE(v7) = 1;
    RgClient_WriteETWTrace(L"Failed to create and signal transition to primary event.", v6, v7);
  }
}

```

## disassembly

```asm
0x100428d70  sub     rsp, 38h
0x100428d74  mov     r8b, 1
0x100428d77  lea     rcx, aEnteringTransi; "Entering transition to primary callback"...
0x100428d7e  mov     dl, 4
0x100428d80  call    cs:__imp_RgClient_WriteETWTrace
0x100428d86  call    ?WaitOnReadyForConnectionsEvent@@YAXXZ; WaitOnReadyForConnectionsEvent(void)
0x100428d8b  mov     r9d, 1
0x100428d91  mov     [rsp+38h+var_18], 0
0x100428d99  lea     r8, aTransitiontopr; "TransitionToPrimaryEventName"
0x100428da0  lea     rdx, aSql; "SQL"
0x100428da7  lea     rcx, aSqlConfig; "SQL.Config"
0x100428dae  call    cs:__imp_?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z; StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(wchar_t const *,wchar_t const *,wchar_t const *,int,int)
0x100428db4  mov     [rsp+38h+hEvent], rax
0x100428db9  mov     rax, [rsp+38h+hEvent]
0x100428dbe  test    rax, rax
0x100428dc1  jz      short loc_100428DEF
0x100428dc3  mov     rcx, [rsp+38h+hEvent]; hEvent
0x100428dc8  call    cs:__imp_SetEvent
0x100428dce  test    eax, eax
0x100428dd0  jz      short loc_100428DEF
0x100428dd2  mov     dl, 4
0x100428dd4  lea     rcx, aTransitionToPr; "Transition to primary event signalled."
0x100428ddb  mov     r8b, 1
0x100428dde  add     rsp, 38h
0x100428de2  jmp     cs:__imp_RgClient_WriteETWTrace
0x100428def  mov     dl, 2
0x100428df1  lea     rcx, aFailedToCreate_0; "Failed to create and signal transition "...
0x100428df8  mov     r8b, 1
0x100428dfb  add     rsp, 38h
0x100428dff  jmp     cs:__imp_RgClient_WriteETWTrace
```
