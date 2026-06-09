# PnpServiceSignalStop

- ea: `0x180014248`
- end: `0x1800142a8`
- name: `PnpServiceSignalStop`
- size: `96`
- prototype: `void()`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e890`
- `0x1800140f0`

## callees

- `0x180011964`
- `0x180014248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014262`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001426c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001426c`

## pseudocode

```c
void PnpServiceSignalStop()
{
  DWORD LastError; // eax

  if ( PnpServiceStopEvent )
  {
    PnpServiceStopError = 0;
    if ( !SetEvent(PnpServiceStopEvent) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x180014248  sub     rsp, 28h
0x18001424c  mov     rcx, cs:PnpServiceStopEvent; hEvent
0x180014253  test    rcx, rcx
0x180014256  jz      short loc_1800142A3
0x180014258  mov     cs:PnpServiceStopError, 0
0x180014262  call    cs:__imp_SetEvent
0x180014268  test    eax, eax
0x18001426a  jnz     short loc_1800142A3
0x18001426c  call    cs:__imp_GetLastError
0x180014272  mov     rcx, cs:WPP_GLOBAL_Control
0x180014279  lea     rdx, WPP_GLOBAL_Control
0x180014280  cmp     rcx, rdx
0x180014283  jz      short loc_1800142A3
0x180014285  test    byte ptr [rcx+1Ch], 2
0x180014289  jz      short loc_1800142A3
0x18001428b  mov     rcx, [rcx+10h]
0x18001428f  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x180014296  mov     edx, 11h
0x18001429b  mov     r9d, eax
0x18001429e  call    WPP_SF_d
0x1800142a3  add     rsp, 28h
0x1800142a7  retn
```
