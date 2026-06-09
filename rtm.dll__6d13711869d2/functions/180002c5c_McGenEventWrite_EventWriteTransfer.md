# McGenEventWrite_EventWriteTransfer

- ea: `0x180002c5c`
- end: `0x180002ca9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002cb0`
- `0x180004280`
- `0x180004920`
- `0x180004b50`
- `0x1800052d0`
- `0x180005530`
- `0x180007a34`
- `0x180008230`
- `0x1800084c0`
- `0x180008710`
- `0x18000a820`
- `0x18000aa60`
- `0x18000ac20`
- `0x18000aef0`

## callees

- `0x180002c5c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180002c9e`
- `ADVAPI32!EventWriteTransfer` at `0x180002c9e`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180002c5c  sub     rsp, 38h
0x180002c60  mov     r8, [rcx+8]
0x180002c64  mov     rax, [rsp+38h+arg_20]
0x180002c69  test    r8, r8
0x180002c6c  jnz     short loc_180002C76
0x180002c6e  mov     [rax], r8
0x180002c71  xor     r10d, r10d
0x180002c74  jmp     short loc_180002C83
0x180002c76  mov     [rax], r8
0x180002c79  mov     r10d, 2
0x180002c7f  movzx   r8d, word ptr [r8]
0x180002c83  mov     [rax+8], r8d
0x180002c87  xor     r8d, r8d; ActivityId
0x180002c8a  mov     [rsp+38h+UserData], rax; UserData
0x180002c8f  mov     [rax+0Ch], r10d
0x180002c93  mov     rcx, [rcx]; RegHandle
0x180002c96  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180002c9b  xor     r9d, r9d; RelatedActivityId
0x180002c9e  call    cs:__imp_EventWriteTransfer
0x180002ca4  add     rsp, 38h
0x180002ca8  retn
```
