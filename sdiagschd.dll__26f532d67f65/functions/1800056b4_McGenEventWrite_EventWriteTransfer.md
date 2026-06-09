# McGenEventWrite_EventWriteTransfer

- ea: `0x1800056b4`
- end: `0x18000570c`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000440c`
- `0x180005714`
- `0x18000579c`
- `0x18000699c`
- `0x180006a60`
- `0x180007a48`
- `0x180007c60`
- `0x1800081f0`
- `0x18000b13c`

## callees

- `0x1800056b4`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800056fa`
- `ADVAPI32!EventWriteTransfer` at `0x1800056fa`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r10
  int v6; // eax
  ULONG v8; // r9d

  v5 = (unsigned __int16 *)a1[1];
  v6 = 0;
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    v8 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v8 = 0;
  }
  UserData->Size = v8;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, a4, UserData);
}

```

## disassembly

```asm
0x1800056b4  sub     rsp, 38h
0x1800056b8  mov     r10, [rcx+8]
0x1800056bc  xor     eax, eax
0x1800056be  mov     r8, [rsp+38h+arg_20]
0x1800056c3  mov     r11d, r9d
0x1800056c6  test    r10, r10
0x1800056c9  jnz     short loc_1800056D3
0x1800056cb  mov     [r8], rax
0x1800056ce  mov     r9d, eax
0x1800056d1  jmp     short loc_1800056DF
0x1800056d3  mov     [r8], r10
0x1800056d6  mov     eax, 2
0x1800056db  movzx   r9d, word ptr [r10]
0x1800056df  mov     [r8+8], r9d
0x1800056e3  xor     r9d, r9d; RelatedActivityId
0x1800056e6  mov     [r8+0Ch], eax
0x1800056ea  mov     rcx, [rcx]; RegHandle
0x1800056ed  mov     [rsp+38h+UserData], r8; UserData
0x1800056f2  xor     r8d, r8d; ActivityId
0x1800056f5  mov     [rsp+38h+UserDataCount], r11d; UserDataCount
0x1800056fa  call    cs:__imp_EventWriteTransfer
0x180005701  nop     dword ptr [rax+rax+00h]
0x180005706  add     rsp, 38h
0x18000570a  retn
```
