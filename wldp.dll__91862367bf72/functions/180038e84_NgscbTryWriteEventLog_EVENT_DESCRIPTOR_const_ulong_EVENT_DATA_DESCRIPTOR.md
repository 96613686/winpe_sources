# NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180038e84`
- end: `0x180038ee0`
- name: `?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `92`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180036f9c`
- `0x1800380a4`

## callees

- `0x180038c08`
- `0x180038e84`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180038ea0`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180038ea0`

## pseudocode

```c
void __fastcall NgscbTryWriteEventLog(
        PCEVENT_DESCRIPTOR EventDescriptor,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONG v3; // eax

  if ( g_HstiEventLog )
  {
    v3 = EventWrite(g_HstiEventLog, EventDescriptor, UserDataCount, UserData);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids, v3);
    }
  }
}

```

## disassembly

```asm
0x180038e84  sub     rsp, 28h
0x180038e88  mov     rax, rcx
0x180038e8b  mov     rcx, cs:?g_HstiEventLog@@3_KA; RegHandle
0x180038e92  test    rcx, rcx
0x180038e95  jz      short loc_180038EDB
0x180038e97  mov     r9, r8; UserData
0x180038e9a  mov     r8d, edx; UserDataCount
0x180038e9d  mov     rdx, rax; EventDescriptor
0x180038ea0  call    cs:__imp_EventWrite
0x180038ea6  test    eax, eax
0x180038ea8  jz      short loc_180038EDB
0x180038eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038eb1  lea     rdx, WPP_GLOBAL_Control
0x180038eb8  cmp     rcx, rdx
0x180038ebb  jz      short loc_180038EDB
0x180038ebd  test    byte ptr [rcx+1Ch], 2
0x180038ec1  jz      short loc_180038EDB
0x180038ec3  mov     rcx, [rcx+10h]
0x180038ec7  lea     r8, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids
0x180038ece  mov     edx, 0Bh
0x180038ed3  mov     r9d, eax
0x180038ed6  call    WPP_SF_d
0x180038edb  add     rsp, 28h
0x180038edf  retn
```
