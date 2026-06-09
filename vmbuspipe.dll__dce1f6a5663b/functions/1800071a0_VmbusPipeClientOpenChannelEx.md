# VmbusPipeClientOpenChannelEx

- ea: `0x1800071a0`
- end: `0x1800071e2`
- name: `VmbusPipeClientOpenChannelEx`
- size: `66`
- prototype: `__int64 __fastcall(const struct _VMBUS_PIPE_CHANNEL_INFO *, unsigned int, const struct VMBUS_PIPE_OPEN_PARAMETERS *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007160`

## callees

- `0x180001b84`
- `0x1800071a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071d3`

## pseudocode

```c
__int64 __fastcall VmbusPipeClientOpenChannelEx(
        const struct _VMBUS_PIPE_CHANNEL_INFO *a1,
        unsigned int a2,
        const struct VMBUS_PIPE_OPEN_PARAMETERS *a3)
{
  int v3; // eax
  DWORD v4; // ecx
  void *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v3 = VmbusPipeClientOpenChannelInternal(a1, a2, a3, &v6);
  v4 = v3;
  if ( v3 >= 0 )
    return (__int64)v6;
  if ( (v3 & 0x1FFF0000) == 0x70000 )
    v4 = (unsigned __int16)v3;
  SetLastError(v4);
  return -1;
}

```

## disassembly

```asm
0x1800071a0  sub     rsp, 28h
0x1800071a4  lea     r9, [rsp+28h+arg_18]; void **
0x1800071a9  mov     [rsp+28h+arg_18], 0
0x1800071b2  call    ?VmbusPipeClientOpenChannelInternal@@YAJPEBU_VMBUS_PIPE_CHANNEL_INFO@@IPEBUVMBUS_PIPE_OPEN_PARAMETERS@@PEAPEAX@Z; VmbusPipeClientOpenChannelInternal(_VMBUS_PIPE_CHANNEL_INFO const *,uint,VMBUS_PIPE_OPEN_PARAMETERS const *,void * *)
0x1800071b7  mov     ecx, eax
0x1800071b9  test    eax, eax
0x1800071bb  js      short loc_1800071C4
0x1800071bd  mov     rax, [rsp+28h+arg_18]
0x1800071c2  jmp     short loc_1800071DD
0x1800071c4  and     eax, 1FFF0000h
0x1800071c9  cmp     eax, 70000h
0x1800071ce  jnz     short loc_1800071D3
0x1800071d0  movzx   ecx, cx; dwErrCode
0x1800071d3  call    cs:__imp_SetLastError
0x1800071d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800071dd  add     rsp, 28h
0x1800071e1  retn
```
