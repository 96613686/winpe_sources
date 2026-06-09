# TmpStartKtmRm

- ea: `0x140001b84`
- end: `0x140001beb`
- name: `TmpStartKtmRm`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001cfc`
- `0x14001ec00`

## callees

- `0x1400024e0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140001bcc`
- `ntoskrnl!EtwWrite` at `0x140001bcc`

## pseudocode

```c
NTSTATUS TmpStartKtmRm()
{
  struct _EVENT_DATA_DESCRIPTOR v1; // [rsp+30h] [rbp-28h] BYREF

  v1.Ptr = (ULONGLONG)TmpKtmRmServiceStartGuid;
  *(_QWORD *)&v1.Size = 16;
  return EtwWrite(TmpTriggerHandle, &KTM_ETW_EVENT_TRIGGER_SVC_START, 0, 1u, &v1);
}

```

## disassembly

```asm
0x140001b84  mov     r11, rsp
0x140001b87  sub     rsp, 58h
0x140001b8b  mov     rax, cs:__security_cookie
0x140001b92  xor     rax, rsp
0x140001b95  mov     [rsp+58h+var_18], rax
0x140001b9a  mov     rcx, cs:TmpTriggerHandle; RegHandle
0x140001ba1  lea     rax, TmpKtmRmServiceStartGuid
0x140001ba8  mov     [r11-28h], rax
0x140001bac  lea     rdx, KTM_ETW_EVENT_TRIGGER_SVC_START; EventDescriptor
0x140001bb3  lea     rax, [r11-28h]
0x140001bb7  mov     qword ptr [r11-20h], 10h
0x140001bbf  mov     r9d, 1; UserDataCount
0x140001bc5  mov     [r11-38h], rax
0x140001bc9  xor     r8d, r8d; ActivityId
0x140001bcc  call    cs:__imp_EtwWrite
0x140001bd3  nop     dword ptr [rax+rax+00h]
0x140001bd8  mov     rcx, [rsp+58h+var_18]
0x140001bdd  xor     rcx, rsp; StackCookie
0x140001be0  call    __security_check_cookie
0x140001be5  add     rsp, 58h
0x140001be9  retn
```
