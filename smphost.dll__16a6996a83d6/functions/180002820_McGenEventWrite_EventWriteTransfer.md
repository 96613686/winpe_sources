# McGenEventWrite_EventWriteTransfer

- ea: `0x180002820`
- end: `0x180002879`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bc8`
- `0x1800024f0`

## callees

- `0x180002820`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002867`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002867`

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

  v5 = (unsigned __int16 *)qword_180006008;
  if ( qword_180006008 )
  {
    UserData->Ptr = qword_180006008;
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
  return EventWriteTransfer(LOG_SMPHOSTPROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180002820  sub     rsp, 38h
0x180002824  mov     rcx, cs:qword_180006008
0x18000282b  mov     rax, [rsp+38h+arg_20]
0x180002830  test    rcx, rcx
0x180002833  jnz     short loc_18000283D
0x180002835  mov     [rax], rcx
0x180002838  xor     r8d, r8d
0x18000283b  jmp     short loc_180002849
0x18000283d  mov     [rax], rcx
0x180002840  mov     r8d, 2
0x180002846  movzx   ecx, word ptr [rcx]
0x180002849  mov     [rax+8], ecx
0x18000284c  mov     [rax+0Ch], r8d
0x180002850  xor     r8d, r8d; ActivityId
0x180002853  mov     rcx, cs:LOG_SMPHOSTPROVIDER_GUID_Context; RegHandle
0x18000285a  mov     [rsp+38h+UserData], rax; UserData
0x18000285f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180002864  xor     r9d, r9d; RelatedActivityId
0x180002867  call    cs:__imp_EventWriteTransfer
0x18000286e  nop     dword ptr [rax+rax+00h]
0x180002873  add     rsp, 38h
0x180002877  retn
```
