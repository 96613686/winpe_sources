# McGenEventWrite_EventWriteTransfer

- ea: `0x180007534`
- end: `0x180007581`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007590`
- `0x180007610`

## callees

- `0x180007534`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007576`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007576`

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
0x180007534  sub     rsp, 38h
0x180007538  mov     r8, [rcx+8]
0x18000753c  mov     rax, [rsp+38h+arg_20]
0x180007541  test    r8, r8
0x180007544  jnz     short loc_18000754E
0x180007546  mov     [rax], r8
0x180007549  xor     r10d, r10d
0x18000754c  jmp     short loc_18000755B
0x18000754e  mov     [rax], r8
0x180007551  mov     r10d, 2
0x180007557  movzx   r8d, word ptr [r8]
0x18000755b  mov     [rax+8], r8d
0x18000755f  xor     r8d, r8d; ActivityId
0x180007562  mov     [rsp+38h+UserData], rax; UserData
0x180007567  mov     [rax+0Ch], r10d
0x18000756b  mov     rcx, [rcx]; RegHandle
0x18000756e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180007573  xor     r9d, r9d; RelatedActivityId
0x180007576  call    cs:__imp_EventWriteTransfer
0x18000757c  add     rsp, 38h
0x180007580  retn
```
