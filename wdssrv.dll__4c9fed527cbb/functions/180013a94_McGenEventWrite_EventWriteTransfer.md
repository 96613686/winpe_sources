# McGenEventWrite_EventWriteTransfer

- ea: `0x180013a94`
- end: `0x180013af2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `94`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013af8`

## callees

- `0x180013a94`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180013ae0`
- `ADVAPI32!EventWriteTransfer` at `0x180013ae0`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  ULONG v6; // eax
  ULONG v7; // r8d

  v5 = (unsigned __int16 *)qword_180028008;
  v6 = 0;
  if ( qword_180028008 )
  {
    UserData->Ptr = qword_180028008;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v6;
  return EventWriteTransfer(MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS_Context, a2, 0, 0, 4u, UserData);
}

```

## disassembly

```asm
0x180013a94  sub     rsp, 38h
0x180013a98  mov     r8, cs:qword_180028008
0x180013a9f  xor     eax, eax
0x180013aa1  mov     rcx, [rsp+38h+arg_20]
0x180013aa6  test    r8, r8
0x180013aa9  jnz     short loc_180013AB3
0x180013aab  mov     [rcx], rax
0x180013aae  mov     r8d, eax
0x180013ab1  jmp     short loc_180013ABF
0x180013ab3  mov     [rcx], r8
0x180013ab6  mov     eax, 2
0x180013abb  movzx   r8d, word ptr [r8]
0x180013abf  mov     [rcx+8], r8d
0x180013ac3  xor     r9d, r9d; RelatedActivityId
0x180013ac6  mov     [rsp+38h+UserData], rcx; UserData
0x180013acb  xor     r8d, r8d; ActivityId
0x180013ace  mov     [rcx+0Ch], eax
0x180013ad1  mov     rcx, cs:MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS_Context; RegHandle
0x180013ad8  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x180013ae0  call    cs:__imp_EventWriteTransfer
0x180013ae7  nop     dword ptr [rax+rax+00h]
0x180013aec  add     rsp, 38h
0x180013af0  retn
```
