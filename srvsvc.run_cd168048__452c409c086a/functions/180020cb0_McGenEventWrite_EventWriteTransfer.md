# McGenEventWrite_EventWriteTransfer

- ea: `0x180020cb0`
- end: `0x180020d02`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180014880`
- `0x180015500`
- `0x180020d08`
- `0x180026db4`
- `0x18002842c`
- `0x18002a560`
- `0x18002a5fc`
- `0x18002b5d8`
- `0x18002c610`
- `0x18002c698`
- `0x180033474`
- `0x18003356c`
- `0x18003a140`
- `0x18003a2bc`

## callees

- `0x180020cb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020cf7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020cf7`

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

  v5 = (unsigned __int16 *)qword_18005C008;
  if ( qword_18005C008 )
  {
    UserData->Ptr = qword_18005C008;
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
  return EventWriteTransfer(PROV_SRV2_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180020cb0  sub     rsp, 38h
0x180020cb4  mov     rcx, cs:qword_18005C008
0x180020cbb  mov     rax, [rsp+38h+arg_20]
0x180020cc0  test    rcx, rcx
0x180020cc3  jnz     short loc_180020CCD
0x180020cc5  mov     [rax], rcx
0x180020cc8  xor     r8d, r8d
0x180020ccb  jmp     short loc_180020CD9
0x180020ccd  mov     [rax], rcx
0x180020cd0  mov     r8d, 2
0x180020cd6  movzx   ecx, word ptr [rcx]
0x180020cd9  mov     [rax+8], ecx
0x180020cdc  mov     [rax+0Ch], r8d
0x180020ce0  xor     r8d, r8d; ActivityId
0x180020ce3  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x180020cea  mov     [rsp+38h+UserData], rax; UserData
0x180020cef  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180020cf4  xor     r9d, r9d; RelatedActivityId
0x180020cf7  call    cs:__imp_EventWriteTransfer
0x180020cfd  add     rsp, 38h
0x180020d01  retn
```
