# McGenEventWrite_EventWriteTransfer

- ea: `0x1800137bc`
- end: `0x18001380e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013814`
- `0x180013948`

## callees

- `0x1800137bc`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180013803`
- `ADVAPI32!EventWriteTransfer` at `0x180013803`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180022078;
  if ( qword_180022078 )
  {
    UserData->Ptr = qword_180022078;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(S_Microsoft_Windows_ProcessExitMonitor_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800137bc  sub     rsp, 38h
0x1800137c0  mov     rcx, cs:qword_180022078
0x1800137c7  mov     rax, [rsp+38h+arg_20]
0x1800137cc  test    rcx, rcx
0x1800137cf  jnz     short loc_1800137D9
0x1800137d1  mov     [rax], rcx
0x1800137d4  xor     r8d, r8d
0x1800137d7  jmp     short loc_1800137E5
0x1800137d9  mov     [rax], rcx
0x1800137dc  mov     r8d, 2
0x1800137e2  movzx   ecx, word ptr [rcx]
0x1800137e5  mov     [rax+8], ecx
0x1800137e8  mov     [rax+0Ch], r8d
0x1800137ec  xor     r8d, r8d; ActivityId
0x1800137ef  mov     rcx, cs:S_Microsoft_Windows_ProcessExitMonitor_Context; RegHandle
0x1800137f6  mov     [rsp+38h+UserData], rax; UserData
0x1800137fb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180013800  xor     r9d, r9d; RelatedActivityId
0x180013803  call    cs:__imp_EventWriteTransfer
0x180013809  add     rsp, 38h
0x18001380d  retn
```
