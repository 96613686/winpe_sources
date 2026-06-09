# McGenEventWrite_EventWriteTransfer

- ea: `0x18000ce80`
- end: `0x18000ceda`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000caa8`

## callees

- `0x18000ce80`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cecf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cecf`

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

  v5 = (unsigned __int16 *)qword_180015008;
  if ( qword_180015008 )
  {
    UserData->Ptr = qword_180015008;
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
  return EventWriteTransfer(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18000ce80  sub     rsp, 38h
0x18000ce84  mov     rcx, cs:qword_180015008
0x18000ce8b  mov     r8d, 2
0x18000ce91  mov     rax, [rsp+38h+arg_20]
0x18000ce96  test    rcx, rcx
0x18000ce99  jnz     short loc_18000CEA2
0x18000ce9b  mov     [rax], rcx
0x18000ce9e  xor     edx, edx
0x18000cea0  jmp     short loc_18000CEAB
0x18000cea2  mov     [rax], rcx
0x18000cea5  mov     edx, r8d
0x18000cea8  movzx   ecx, word ptr [rcx]
0x18000ceab  mov     [rax+8], ecx
0x18000ceae  xor     r9d, r9d; RelatedActivityId
0x18000ceb1  mov     [rax+0Ch], edx
0x18000ceb4  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x18000cebb  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x18000cec2  mov     [rsp+38h+UserData], rax; UserData
0x18000cec7  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x18000cecc  xor     r8d, r8d; ActivityId
0x18000cecf  call    cs:__imp_EventWriteTransfer
0x18000ced5  add     rsp, 38h
0x18000ced9  retn
```
