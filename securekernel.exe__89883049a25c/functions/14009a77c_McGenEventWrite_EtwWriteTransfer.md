# McGenEventWrite_EtwWriteTransfer

- ea: `0x14009a77c`
- end: `0x14009a7c9`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14009a7d0`
- `0x1400ad564`
- `0x1400b3820`
- `0x1400b4750`
- `0x1400b47d4`
- `0x1400b50e0`
- `0x1400b5174`
- `0x1400bb150`
- `0x1400bb1a8`

## callees

- `0x14003fe40`
- `0x14009a77c`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
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
  return SkEtwWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14009a77c  sub     rsp, 38h
0x14009a780  mov     r8, [rcx+8]
0x14009a784  mov     rax, [rsp+38h+arg_20]
0x14009a789  test    r8, r8
0x14009a78c  jnz     short loc_14009A796
0x14009a78e  mov     [rax], r8
0x14009a791  xor     r10d, r10d
0x14009a794  jmp     short loc_14009A7A3
0x14009a796  mov     [rax], r8
0x14009a799  mov     r10d, 2
0x14009a79f  movzx   r8d, word ptr [r8]
0x14009a7a3  mov     [rax+8], r8d
0x14009a7a7  xor     r8d, r8d; ActivityId
0x14009a7aa  mov     [rsp+38h+UserData], rax; UserData
0x14009a7af  mov     [rax+0Ch], r10d
0x14009a7b3  mov     rcx, [rcx]; RegHandle
0x14009a7b6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14009a7bb  xor     r9d, r9d; RelatedActivityId
0x14009a7be  call    SkEtwWriteTransfer
0x14009a7c3  add     rsp, 38h
0x14009a7c7  retn
```
