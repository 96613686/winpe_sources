# McGenEventWrite_EventWriteTransfer

- ea: `0x1800097bc`
- end: `0x180009815`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000981c`
- `0x180009890`
- `0x180009f68`
- `0x180009fc0`

## callees

- `0x1800097bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009803`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009803`

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

  v5 = (unsigned __int16 *)qword_180010008;
  if ( qword_180010008 )
  {
    UserData->Ptr = qword_180010008;
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
  return EventWriteTransfer(VIRTDISK_PROVIDER_ID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800097bc  sub     rsp, 38h
0x1800097c0  mov     rcx, cs:qword_180010008
0x1800097c7  mov     rax, [rsp+38h+arg_20]
0x1800097cc  test    rcx, rcx
0x1800097cf  jnz     short loc_1800097D9
0x1800097d1  mov     [rax], rcx
0x1800097d4  xor     r8d, r8d
0x1800097d7  jmp     short loc_1800097E5
0x1800097d9  mov     [rax], rcx
0x1800097dc  mov     r8d, 2
0x1800097e2  movzx   ecx, word ptr [rcx]
0x1800097e5  mov     [rax+8], ecx
0x1800097e8  mov     [rax+0Ch], r8d
0x1800097ec  xor     r8d, r8d; ActivityId
0x1800097ef  mov     rcx, cs:VIRTDISK_PROVIDER_ID_Context; RegHandle
0x1800097f6  mov     [rsp+38h+UserData], rax; UserData
0x1800097fb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180009800  xor     r9d, r9d; RelatedActivityId
0x180009803  call    cs:__imp_EventWriteTransfer
0x18000980a  nop     dword ptr [rax+rax+00h]
0x18000980f  add     rsp, 38h
0x180009813  retn
```
