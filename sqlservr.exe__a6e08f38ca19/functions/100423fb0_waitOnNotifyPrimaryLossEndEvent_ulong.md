# waitOnNotifyPrimaryLossEndEvent(ulong)

- ea: `0x100423fb0`
- end: `0x100424079`
- name: `?waitOnNotifyPrimaryLossEndEvent@@YA_NK@Z`
- size: `201`
- prototype: `bool __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100424110`

## callees

- `0x100423fb0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100424020`
- `KERNEL32!WaitForSingleObject` at `0x100424020`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x100423fdb`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x100423fdb`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100423ffc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424013`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042403d`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424054`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042406b`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100423ffc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424013`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042403d`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424054`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042406b`

## string_xrefs

- `0x100423fc0`: `SQL.Config`
- `0x100423ff5`: `Failed to create the ending notify primary loss event.`

## pseudocode

```c
char __fastcall waitOnNotifyPrimaryLossEndEvent(DWORD dwMilliseconds)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE hHandle; // [rsp+48h] [rbp+10h]

  hHandle = StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(
              L"SQL.Config",
              L"SQL",
              L"NotifyPrimaryLossEndEventName",
              1,
              0);
  LOBYTE(v3) = 1;
  if ( hHandle )
  {
    LOBYTE(v2) = 4;
    RgClient_WriteETWTrace(L"Waiting for the ending notify primary loss event to be signalled.", v2, v3);
    v5 = WaitForSingleObject(hHandle, dwMilliseconds);
    LOBYTE(v7) = 1;
    if ( v5 )
    {
      if ( v5 == 258 )
      {
        LOBYTE(v6) = 3;
        RgClient_WriteETWTrace(L"The ending notify primary loss event timed out.", v6, v7);
        return 1;
      }
      else
      {
        LOBYTE(v6) = 2;
        RgClient_WriteETWTrace(L"Failed to wait on ending notify primary loss event.", v6, v7);
        return 0;
      }
    }
    else
    {
      LOBYTE(v6) = 4;
      RgClient_WriteETWTrace(L"The ending notify primary loss event signalled.", v6, v7);
      return 1;
    }
  }
  else
  {
    LOBYTE(v2) = 2;
    RgClient_WriteETWTrace(L"Failed to create the ending notify primary loss event.", v2, v3);
    return 0;
  }
}

```

## disassembly

```asm
0x100423fb0  push    rbx
0x100423fb2  sub     rsp, 30h
0x100423fb6  mov     ebx, ecx
0x100423fb8  mov     [rsp+38h+var_18], 0
0x100423fc0  lea     rcx, aSqlConfig; "SQL.Config"
0x100423fc7  mov     r9d, 1
0x100423fcd  lea     r8, aNotifyprimaryl_1; "NotifyPrimaryLossEndEventName"
0x100423fd4  lea     rdx, aSql; "SQL"
0x100423fdb  call    cs:__imp_?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z; StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(wchar_t const *,wchar_t const *,wchar_t const *,int,int)
0x100423fe1  mov     [rsp+38h+hHandle], rax
0x100423fe6  mov     r8b, 1
0x100423fe9  mov     rax, [rsp+38h+hHandle]
0x100423fee  test    rax, rax
0x100423ff1  jnz     short loc_10042400A
0x100423ff3  mov     dl, 2
0x100423ff5  lea     rcx, aFailedToCreate_1; "Failed to create the ending notify prim"...
0x100423ffc  call    cs:__imp_RgClient_WriteETWTrace
0x100424002  xor     al, al
0x100424004  add     rsp, 30h
0x100424008  pop     rbx
0x100424009  retn
0x10042400a  mov     dl, 4
0x10042400c  lea     rcx, aWaitingForTheE; "Waiting for the ending notify primary l"...
0x100424013  call    cs:__imp_RgClient_WriteETWTrace
0x100424019  mov     rcx, [rsp+38h+hHandle]; hHandle
0x10042401e  mov     edx, ebx; dwMilliseconds
0x100424020  call    cs:__imp_WaitForSingleObject
0x100424026  mov     r8b, 1
0x100424029  test    eax, eax
0x10042402b  jz      short loc_100424062
0x10042402d  cmp     eax, 102h
0x100424032  jz      short loc_10042404B
0x100424034  mov     dl, 2
0x100424036  lea     rcx, aFailedToWaitOn; "Failed to wait on ending notify primary"...
0x10042403d  call    cs:__imp_RgClient_WriteETWTrace
0x100424043  xor     al, al
0x100424045  add     rsp, 30h
0x100424049  pop     rbx
0x10042404a  retn
0x10042404b  mov     dl, 3
0x10042404d  lea     rcx, aTheEndingNotif; "The ending notify primary loss event ti"...
0x100424054  call    cs:__imp_RgClient_WriteETWTrace
0x10042405a  mov     al, 1
0x10042405c  add     rsp, 30h
0x100424060  pop     rbx
0x100424061  retn
0x100424062  mov     dl, 4
0x100424064  lea     rcx, aTheEndingNotif_0; "The ending notify primary loss event si"...
0x10042406b  call    cs:__imp_RgClient_WriteETWTrace
0x100424071  mov     al, 1
0x100424073  add     rsp, 30h
0x100424077  pop     rbx
0x100424078  retn
```
