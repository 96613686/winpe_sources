# McGenEventWrite_EventWriteTransfer

- ea: `0x180024290`
- end: `0x1800242e2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800242e8`
- `0x180024368`
- `0x180024408`

## callees

- `0x180024290`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800242d7`
- `ADVAPI32!EventWriteTransfer` at `0x1800242d7`

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

  v5 = (unsigned __int16 *)qword_18002C018;
  if ( qword_18002C018 )
  {
    UserData->Ptr = qword_18002C018;
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
  return EventWriteTransfer(RpcProxyLbsTraceEvents_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180024290  sub     rsp, 38h
0x180024294  mov     rcx, cs:qword_18002C018
0x18002429b  mov     rax, [rsp+38h+arg_20]
0x1800242a0  test    rcx, rcx
0x1800242a3  jnz     short loc_1800242AD
0x1800242a5  mov     [rax], rcx
0x1800242a8  xor     r8d, r8d
0x1800242ab  jmp     short loc_1800242B9
0x1800242ad  mov     [rax], rcx
0x1800242b0  mov     r8d, 2
0x1800242b6  movzx   ecx, word ptr [rcx]
0x1800242b9  mov     [rax+8], ecx
0x1800242bc  mov     [rax+0Ch], r8d
0x1800242c0  xor     r8d, r8d; ActivityId
0x1800242c3  mov     rcx, cs:RpcProxyLbsTraceEvents_Context; RegHandle
0x1800242ca  mov     [rsp+38h+UserData], rax; UserData
0x1800242cf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800242d4  xor     r9d, r9d; RelatedActivityId
0x1800242d7  call    cs:__imp_EventWriteTransfer
0x1800242dd  add     rsp, 38h
0x1800242e1  retn
```
