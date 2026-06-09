# McGenEventWrite_EventWriteTransfer

- ea: `0x1400075f0`
- end: `0x140007649`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005964`

## callees

- `0x1400075f0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000763e`
- `ADVAPI32!EventWriteTransfer` at `0x14000763e`

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

  v5 = (unsigned __int16 *)qword_14000E008;
  if ( qword_14000E008 )
  {
    UserData->Ptr = qword_14000E008;
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
  return EventWriteTransfer(
           SCRIPTED_DIAGNOSTICS_PROVIDER_Context,
           &SCRIPTED_DIAGNOSTICS_EVENT_DEBUG,
           0,
           0,
           4u,
           UserData);
}

```

## disassembly

```asm
0x1400075f0  sub     rsp, 38h
0x1400075f4  mov     rcx, cs:qword_14000E008
0x1400075fb  mov     rax, [rsp+38h+arg_20]
0x140007600  test    rcx, rcx
0x140007603  jnz     short loc_14000760C
0x140007605  mov     [rax], rcx
0x140007608  xor     edx, edx
0x14000760a  jmp     short loc_140007617
0x14000760c  mov     [rax], rcx
0x14000760f  mov     edx, 2
0x140007614  movzx   ecx, word ptr [rcx]
0x140007617  mov     [rax+8], ecx
0x14000761a  xor     r9d, r9d; RelatedActivityId
0x14000761d  mov     [rax+0Ch], edx
0x140007620  xor     r8d, r8d; ActivityId
0x140007623  mov     rcx, cs:SCRIPTED_DIAGNOSTICS_PROVIDER_Context; RegHandle
0x14000762a  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_DEBUG; EventDescriptor
0x140007631  mov     [rsp+38h+UserData], rax; UserData
0x140007636  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x14000763e  call    cs:__imp_EventWriteTransfer
0x140007644  add     rsp, 38h
0x140007648  retn
```
