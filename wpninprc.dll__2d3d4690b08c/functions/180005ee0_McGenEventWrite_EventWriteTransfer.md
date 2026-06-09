# McGenEventWrite_EventWriteTransfer

- ea: `0x180005ee0`
- end: `0x180005f35`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b7c`

## callees

- `0x180005ee0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005f2a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005f2a`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_18000B008;
  if ( qword_18000B008 )
  {
    UserData->Ptr = qword_18000B008;
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
  return EventWriteTransfer(WPNINPRC_PROVIDER_GUID_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x180005ee0  sub     rsp, 38h
0x180005ee4  mov     rcx, cs:qword_18000B008
0x180005eeb  mov     rax, [rsp+38h+arg_20]
0x180005ef0  test    rcx, rcx
0x180005ef3  jnz     short loc_180005EFD
0x180005ef5  mov     [rax], rcx
0x180005ef8  xor     r8d, r8d
0x180005efb  jmp     short loc_180005F09
0x180005efd  mov     [rax], rcx
0x180005f00  mov     r8d, 2
0x180005f06  movzx   ecx, word ptr [rcx]
0x180005f09  mov     [rax+8], ecx
0x180005f0c  xor     r9d, r9d; RelatedActivityId
0x180005f0f  mov     [rax+0Ch], r8d
0x180005f13  xor     r8d, r8d; ActivityId
0x180005f16  mov     rcx, cs:WPNINPRC_PROVIDER_GUID_Context; RegHandle
0x180005f1d  mov     [rsp+38h+UserData], rax; UserData
0x180005f22  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x180005f2a  call    cs:__imp_EventWriteTransfer
0x180005f30  add     rsp, 38h
0x180005f34  retn
```
