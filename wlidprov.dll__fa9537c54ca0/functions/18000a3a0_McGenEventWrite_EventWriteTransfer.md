# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a3a0`
- end: `0x18000a3f2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800061a8`
- `0x180007170`
- `0x1800077c0`
- `0x180007e10`
- `0x180008580`
- `0x1800086c0`
- `0x180008c20`
- `0x1800090c0`
- `0x180009630`
- `0x180009e00`
- `0x18000a0e0`
- `0x18000a1d0`
- `0x18000a300`
- `0x18000a7f0`
- `0x18000b1f0`
- `0x18000c090`
- `0x18000c120`
- `0x18000c4f0`
- `0x18000f564`
- `0x1800238ec`
- `0x1800247c0`
- `0x180026a40`

## callees

- `0x18000a3a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a3d9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a3d9`

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

  v5 = (unsigned __int16 *)qword_180084238;
  if ( qword_180084238 )
  {
    UserData->Ptr = qword_180084238;
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
  return EventWriteTransfer(Microsoft_Windows_LiveId_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000a3a0  sub     rsp, 38h
0x18000a3a4  mov     rcx, cs:qword_180084238
0x18000a3ab  mov     rax, [rsp+38h+arg_20]
0x18000a3b0  test    rcx, rcx
0x18000a3b3  jnz     short loc_18000A3E4
0x18000a3b5  mov     [rax], rcx
0x18000a3b8  xor     r8d, r8d
0x18000a3bb  mov     [rax+8], ecx
0x18000a3be  mov     [rax+0Ch], r8d
0x18000a3c2  xor     r8d, r8d; ActivityId
0x18000a3c5  mov     rcx, cs:Microsoft_Windows_LiveId_Context; RegHandle
0x18000a3cc  mov     [rsp+38h+UserData], rax; UserData
0x18000a3d1  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a3d6  xor     r9d, r9d; RelatedActivityId
0x18000a3d9  call    cs:__imp_EventWriteTransfer
0x18000a3df  add     rsp, 38h
0x18000a3e3  retn
0x18000a3e4  mov     [rax], rcx
0x18000a3e7  mov     r8d, 2
0x18000a3ed  movzx   ecx, word ptr [rcx]
0x18000a3f0  jmp     short loc_18000A3BB
```
