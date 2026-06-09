# McGenEventWrite_EventWriteTransfer

- ea: `0x180009570`
- end: `0x1800095c9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800095d0`

## callees

- `0x180009570`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800095be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800095be`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_1800492B8;
  if ( qword_1800492B8 )
  {
    UserData->Ptr = qword_1800492B8;
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
  return EventWriteTransfer(XWIZARDS_PROVIDER_Context, &DlgError, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x180009570  sub     rsp, 38h
0x180009574  mov     rcx, cs:qword_1800492B8
0x18000957b  mov     rax, [rsp+38h+arg_20]
0x180009580  test    rcx, rcx
0x180009583  jnz     short loc_18000958C
0x180009585  mov     [rax], rcx
0x180009588  xor     edx, edx
0x18000958a  jmp     short loc_180009597
0x18000958c  mov     [rax], rcx
0x18000958f  mov     edx, 2
0x180009594  movzx   ecx, word ptr [rcx]
0x180009597  mov     [rax+8], ecx
0x18000959a  xor     r9d, r9d; RelatedActivityId
0x18000959d  mov     [rax+0Ch], edx
0x1800095a0  xor     r8d, r8d; ActivityId
0x1800095a3  mov     rcx, cs:XWIZARDS_PROVIDER_Context; RegHandle
0x1800095aa  lea     rdx, DlgError; EventDescriptor
0x1800095b1  mov     [rsp+38h+UserData], rax; UserData
0x1800095b6  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x1800095be  call    cs:__imp_EventWriteTransfer
0x1800095c4  add     rsp, 38h
0x1800095c8  retn
```
