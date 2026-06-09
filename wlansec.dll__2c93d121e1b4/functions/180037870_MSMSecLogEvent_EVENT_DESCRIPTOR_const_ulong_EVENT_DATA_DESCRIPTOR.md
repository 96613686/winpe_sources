# MSMSecLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180037870`
- end: `0x1800378d5`
- name: `?MSMSecLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `101`
- prototype: `unsigned int __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003f1cc`

## callees

- `0x180037870`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180037891`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180037891`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800378b1`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800378b1`

## pseudocode

```c
ULONG __fastcall MSMSecLogEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  if ( EventEnabled(WLANSVC_EVT_GUID_Context, EventDescriptor) )
    return EventWrite(WLANSVC_EVT_GUID_Context, EventDescriptor, UserDataCount, UserData);
  else
    return 5023;
}

```

## disassembly

```asm
0x180037870  mov     [rsp+arg_0], rbx
0x180037875  mov     [rsp+arg_8], rsi
0x18003787a  push    rdi
0x18003787b  sub     rsp, 20h
0x18003787f  mov     esi, edx
0x180037881  mov     rbx, rcx
0x180037884  mov     rdx, rcx; EventDescriptor
0x180037887  mov     rdi, r8
0x18003788a  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180037891  call    cs:__imp_EventEnabled
0x180037898  nop     dword ptr [rax+rax+00h]
0x18003789d  test    al, al
0x18003789f  jz      short loc_1800378CE
0x1800378a1  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x1800378a8  mov     r9, rdi; UserData
0x1800378ab  mov     r8d, esi; UserDataCount
0x1800378ae  mov     rdx, rbx; EventDescriptor
0x1800378b1  call    cs:__imp_EventWrite
0x1800378b8  nop     dword ptr [rax+rax+00h]
0x1800378bd  mov     rbx, [rsp+28h+arg_0]
0x1800378c2  mov     rsi, [rsp+28h+arg_8]
0x1800378c7  add     rsp, 20h
0x1800378cb  pop     rdi
0x1800378cc  retn
0x1800378ce  mov     eax, 139Fh
0x1800378d3  jmp     short loc_1800378BD
```
