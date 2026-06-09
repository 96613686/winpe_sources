# McGenEventWrite_EtwWriteTransfer

- ea: `0x14001f420`
- end: `0x14001f476`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `66`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f330`
- `0x14002bff4`
- `0x14002c048`
- `0x14002c2b4`
- `0x14002c32c`
- `0x14002c460`
- `0x14002c5b0`
- `0x14002c710`
- `0x14002c874`
- `0x14002c9f4`
- `0x14002cb68`
- `0x14002cd48`
- `0x14002e158`
- `0x14002e25c`
- `0x14002e30c`
- `0x14002e364`
- `0x14002e3cc`
- `0x14002fa18`
- `0x14002fa80`
- `0x14002faf8`
- `0x14002fbac`
- `0x14002fc40`
- `0x14002fcec`
- `0x14002fdb0`
- `0x14002fe10`
- `0x14002fed0`
- `0x14002ff44`
- `0x14002ffd0`
- `0x14003005c`
- `0x140030100`
- `0x1400301b4`
- `0x1400302c0`
- `0x140030380`
- `0x140030410`
- `0x1400304c4`
- `0x140030578`
- `0x140030634`
- `0x14003072c`
- `0x1400307c0`
- `0x140030864`
- `0x140030918`
- `0x14003098c`
- `0x140030a30`
- `0x140030acc`
- `0x140030b70`
- `0x140030c2c`
- `0x140030ce4`
- `0x140030d5c`
- `0x140030e10`
- `0x140030e8c`

## callees

- `0x14001f420`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001f464`
- `ntoskrnl!EtwWriteTransfer` at `0x14001f464`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_14007F008;
  if ( qword_14007F008 )
  {
    UserData->Ptr = qword_14007F008;
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
  return EtwWriteTransfer(SpaceportProvider_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14001f420  sub     rsp, 38h
0x14001f424  mov     rcx, cs:qword_14007F008
0x14001f42b  mov     rax, [rsp+38h+arg_20]
0x14001f430  test    rcx, rcx
0x14001f433  jnz     short loc_14001F43D
0x14001f435  mov     [rax], rcx
0x14001f438  xor     r10d, r10d
0x14001f43b  jmp     short loc_14001F449
0x14001f43d  mov     [rax], rcx
0x14001f440  mov     r10d, 2
0x14001f446  movzx   ecx, word ptr [rcx]
0x14001f449  mov     [rax+8], ecx
0x14001f44c  mov     [rsp+38h+UserData], rax; UserData
0x14001f451  mov     [rax+0Ch], r10d
0x14001f455  mov     rcx, cs:SpaceportProvider_Context; RegHandle
0x14001f45c  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14001f461  xor     r9d, r9d; RelatedActivityId
0x14001f464  call    cs:__imp_EtwWriteTransfer
0x14001f46b  nop     dword ptr [rax+rax+00h]
0x14001f470  add     rsp, 38h
0x14001f474  retn
```
