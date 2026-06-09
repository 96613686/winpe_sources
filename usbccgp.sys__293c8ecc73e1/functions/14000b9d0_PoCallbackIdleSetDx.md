# PoCallbackIdleSetDx

- ea: `0x14000b9d0`
- end: `0x14000ba33`
- name: `PoCallbackIdleSetDx`
- size: `99`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b9d0`
- `0x14000ba3c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b9f1`
- `ntoskrnl!KeSetEvent` at `0x14000b9f1`

## pseudocode

```c
void __fastcall PoCallbackIdleSetDx(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        struct _KEVENT *Context)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      *((_QWORD *)DeviceObject->DeviceExtension + 172),
      4,
      3,
      36,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      PowerState.SystemState);
  KeSetEvent(Context, 0, 0);
}

```

## disassembly

```asm
0x14000b9d0  push    rbx
0x14000b9d2  sub     rsp, 30h
0x14000b9d6  mov     rbx, r9
0x14000b9d9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b9e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b9e7  jnz     short loc_14000BA04
0x14000b9e9  xor     r8d, r8d; Wait
0x14000b9ec  xor     edx, edx; Increment
0x14000b9ee  mov     rcx, rbx; Event
0x14000b9f1  call    cs:__imp_KeSetEvent
0x14000b9f8  nop     dword ptr [rax+rax+00h]
0x14000b9fd  add     rsp, 30h
0x14000ba01  pop     rbx
0x14000ba02  retn
0x14000ba04  mov     rcx, [rcx+40h]
0x14000ba08  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x14000ba0f  mov     [rsp+38h+var_10], r8d
0x14000ba14  mov     r9d, 24h ; '$'
0x14000ba1a  mov     dl, 4
0x14000ba1c  mov     [rsp+38h+var_18], rax
0x14000ba21  mov     rcx, [rcx+560h]
0x14000ba28  lea     r8d, [r9-21h]
0x14000ba2c  call    WPP_RECORDER_SF_D
0x14000ba31  jmp     short loc_14000B9E9
```
