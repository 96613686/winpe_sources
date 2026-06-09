# UbpmpUninitializeMaintenanceLevels(void)

- ea: `0x18002a750`
- end: `0x18002a7de`
- name: `?UbpmpUninitializeMaintenanceLevels@@YAXXZ`
- size: `142`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a520`
- `0x1800307f0`
- `0x180036604`

## callees

- `0x18002a750`
- `0x180030cec`

## import_xrefs

- `EventAggregation!EADeleteAggregateEvent` at `0x18002a788`
- `EventAggregation!EADeleteAggregateEvent` at `0x18002a788`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002a778`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002a778`

## pseudocode

```c
void UbpmpUninitializeMaintenanceLevels(void)
{
  unsigned int i; // ebx
  unsigned __int64 v1; // rdi
  int v2; // eax

  for ( i = 0; i < 5; ++i )
  {
    v1 = (unsigned __int64)i << 6;
    if ( *(_QWORD *)((char *)&g_MaintenancePilot + v1 + 104) )
      CrmActivityFree();
    if ( *(_QWORD *)((char *)&g_MaintenancePilot + v1 + 96) )
    {
      v2 = EADeleteAggregateEvent();
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, i, v2);
      }
    }
  }
}

```

## disassembly

```asm
0x18002a750  mov     [rsp+arg_0], rbx
0x18002a755  mov     [rsp+arg_8], rsi
0x18002a75a  push    rdi
0x18002a75b  sub     rsp, 30h
0x18002a75f  xor     ebx, ebx
0x18002a761  lea     rsi, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002a768  mov     edi, ebx
0x18002a76a  shl     rdi, 6
0x18002a76e  mov     rcx, [rdi+rsi+68h]
0x18002a773  test    rcx, rcx
0x18002a776  jz      short loc_18002A77E
0x18002a778  call    cs:__imp_CrmActivityFree
0x18002a77e  mov     rcx, [rdi+rsi+60h]
0x18002a783  test    rcx, rcx
0x18002a786  jz      short loc_18002A7C7
0x18002a788  call    cs:__imp_EADeleteAggregateEvent
0x18002a78e  test    eax, eax
0x18002a790  jz      short loc_18002A7C7
0x18002a792  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a799  lea     rdx, WPP_GLOBAL_Control
0x18002a7a0  cmp     rcx, rdx
0x18002a7a3  jz      short loc_18002A7C7
0x18002a7a5  test    byte ptr [rcx+1Ch], 1
0x18002a7a9  jz      short loc_18002A7C7
0x18002a7ab  mov     rcx, [rcx+10h]
0x18002a7af  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x18002a7b6  mov     edx, 12h
0x18002a7bb  mov     [rsp+38h+var_18], eax
0x18002a7bf  mov     r9d, ebx
0x18002a7c2  call    WPP_SF_dd
0x18002a7c7  inc     ebx
0x18002a7c9  cmp     ebx, 5
0x18002a7cc  jb      short loc_18002A768
0x18002a7ce  mov     rbx, [rsp+38h+arg_0]
0x18002a7d3  mov     rsi, [rsp+38h+arg_8]
0x18002a7d8  add     rsp, 30h
0x18002a7dc  pop     rdi
0x18002a7dd  retn
```
