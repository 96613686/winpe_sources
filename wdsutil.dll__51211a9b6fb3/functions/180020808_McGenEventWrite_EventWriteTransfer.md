# McGenEventWrite_EventWriteTransfer

- ea: `0x180020808`
- end: `0x180020861`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001eb64`
- `0x18001ef34`
- `0x18001f284`
- `0x18001f970`
- `0x180020868`
- `0x1800208ec`

## callees

- `0x180020808`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18002084f`
- `ADVAPI32!EventWriteTransfer` at `0x18002084f`

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

  v5 = (unsigned __int16 *)qword_18004C878;
  if ( qword_18004C878 )
  {
    UserData->Ptr = qword_18004C878;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180020808  sub     rsp, 38h
0x18002080c  mov     rcx, cs:qword_18004C878
0x180020813  mov     rax, [rsp+38h+arg_20]
0x180020818  test    rcx, rcx
0x18002081b  jnz     short loc_180020825
0x18002081d  mov     [rax], rcx
0x180020820  xor     r8d, r8d
0x180020823  jmp     short loc_180020831
0x180020825  mov     [rax], rcx
0x180020828  mov     r8d, 2
0x18002082e  movzx   ecx, word ptr [rcx]
0x180020831  mov     [rax+8], ecx
0x180020834  mov     [rax+0Ch], r8d
0x180020838  xor     r8d, r8d; ActivityId
0x18002083b  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x180020842  mov     [rsp+38h+UserData], rax; UserData
0x180020847  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002084c  xor     r9d, r9d; RelatedActivityId
0x18002084f  call    cs:__imp_EventWriteTransfer
0x180020856  nop     dword ptr [rax+rax+00h]
0x18002085b  add     rsp, 38h
0x18002085f  retn
```
