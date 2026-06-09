# McGenEventWrite_EventWriteTransfer

- ea: `0x1800130d0`
- end: `0x180013122`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ad80`
- `0x18000cf00`
- `0x18000d63c`
- `0x18000fcf0`
- `0x1800101cc`
- `0x180011630`
- `0x180013128`
- `0x1800131a8`
- `0x1800176dc`
- `0x18001e194`
- `0x180021d34`
- `0x180026fa0`

## callees

- `0x1800130d0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180013117`
- `ADVAPI32!EventWriteTransfer` at `0x180013117`

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

  v5 = (unsigned __int16 *)qword_180038008;
  if ( qword_180038008 )
  {
    UserData->Ptr = qword_180038008;
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
  return EventWriteTransfer(SCRIPTED_DIAGNOSTICS_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800130d0  sub     rsp, 38h
0x1800130d4  mov     rcx, cs:qword_180038008
0x1800130db  mov     rax, [rsp+38h+arg_20]
0x1800130e0  test    rcx, rcx
0x1800130e3  jnz     short loc_1800130ED
0x1800130e5  mov     [rax], rcx
0x1800130e8  xor     r8d, r8d
0x1800130eb  jmp     short loc_1800130F9
0x1800130ed  mov     [rax], rcx
0x1800130f0  mov     r8d, 2
0x1800130f6  movzx   ecx, word ptr [rcx]
0x1800130f9  mov     [rax+8], ecx
0x1800130fc  mov     [rax+0Ch], r8d
0x180013100  xor     r8d, r8d; ActivityId
0x180013103  mov     rcx, cs:SCRIPTED_DIAGNOSTICS_PROVIDER_Context; RegHandle
0x18001310a  mov     [rsp+38h+UserData], rax; UserData
0x18001310f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180013114  xor     r9d, r9d; RelatedActivityId
0x180013117  call    cs:__imp_EventWriteTransfer
0x18001311d  add     rsp, 38h
0x180013121  retn
```
