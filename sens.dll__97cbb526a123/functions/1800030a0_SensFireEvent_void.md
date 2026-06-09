# SensFireEvent(void *)

- ea: `0x1800030a0`
- end: `0x180003180`
- name: `?SensFireEvent@@YAXPEAX@Z`
- size: `224`
- prototype: `void __fastcall(int *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180001040`
- `0x180001350`
- `0x180001850`
- `0x180002060`
- `0x180002c10`
- `0x180002e60`

## callees

- `0x1800030a0`
- `0x180003190`
- `0x180003aa0`
- `0x180008300`
- `0x1800093b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003131`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800030c3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800030c3`

## pseudocode

```c
void __fastcall SensFireEvent(int *a1)
{
  _QWORD *EventData; // rax
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  DWORD LastError; // eax

  EventData = AllocateEventData(a1);
  v2 = EventData;
  if ( EventData )
  {
    if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)SensFireEventHelper, EventData, 0x10u) )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v4 = 17;
        goto LABEL_17;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, LastError);
      }
      FreeEventData(v2);
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 15;
LABEL_17:
      WPP_SF_(v3[2], v4, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1800030a0  push    rbx
0x1800030a2  sub     rsp, 20h
0x1800030a6  call    ?AllocateEventData@@YAPEAXPEAX@Z; AllocateEventData(void *)
0x1800030ab  mov     rbx, rax
0x1800030ae  test    rax, rax
0x1800030b1  jz      short loc_1800030EC
0x1800030b3  mov     r8d, 10h; Flags
0x1800030b9  lea     rcx, ?SensFireEventHelper@@YAKPEAX@Z; Function
0x1800030c0  mov     rdx, rax; Context
0x1800030c3  call    cs:__imp_QueueUserWorkItem
0x1800030c9  test    eax, eax
0x1800030cb  jz      short loc_180003112
0x1800030cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030d4  lea     rax, WPP_GLOBAL_Control
0x1800030db  cmp     rcx, rax
0x1800030de  jz      short loc_1800030E6
0x1800030e0  test    byte ptr [rcx+1Ch], 1
0x1800030e4  jnz     short loc_180003160
0x1800030e6  add     rsp, 20h
0x1800030ea  pop     rbx
0x1800030eb  retn
0x1800030ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f3  lea     rax, WPP_GLOBAL_Control
0x1800030fa  cmp     rcx, rax
0x1800030fd  jz      short loc_1800030E6
0x1800030ff  test    byte ptr [rcx+1Ch], 1
0x180003103  jz      short loc_1800030E6
0x180003105  cmp     byte ptr [rcx+19h], 2
0x180003109  jb      short loc_1800030E6
0x18000310b  mov     edx, 0Fh
0x180003110  jmp     short loc_18000316B
0x180003112  mov     rcx, cs:WPP_GLOBAL_Control
0x180003119  lea     rax, WPP_GLOBAL_Control
0x180003120  cmp     rcx, rax
0x180003123  jz      short loc_180003156
0x180003125  test    byte ptr [rcx+1Ch], 1
0x180003129  jz      short loc_180003156
0x18000312b  cmp     byte ptr [rcx+19h], 2
0x18000312f  jb      short loc_180003156
0x180003131  call    cs:__imp_GetLastError
0x180003137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000313e  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003145  mov     edx, 10h
0x18000314a  mov     r9d, eax
0x18000314d  mov     rcx, [rcx+10h]
0x180003151  call    WPP_SF_d
0x180003156  mov     rcx, rbx; lpMem
0x180003159  call    ?FreeEventData@@YAXPEAX@Z; FreeEventData(void *)
0x18000315e  jmp     short loc_1800030E6
0x180003160  cmp     byte ptr [rcx+19h], 5
0x180003164  jb      short loc_1800030E6
0x180003166  mov     edx, 11h
0x18000316b  mov     rcx, [rcx+10h]
0x18000316f  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003176  call    WPP_SF_
0x18000317b  jmp     loc_1800030E6
```
