# UmpoProcessPowerRequestNotifyCreate

- ea: `0x18000be60`
- end: `0x18000bea1`
- name: `UmpoProcessPowerRequestNotifyCreate`
- size: `65`
- prototype: `int __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b39c`

## callees

- `0x18000be60`
- `0x18000bea8`
- `0x18000f3dc`

## pseudocode

```c
int __fastcall UmpoProcessPowerRequestNotifyCreate(_DWORD *a1)
{
  int result; // eax

  if ( *a1 != 15 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = UmpoHvPowerRequestCreate(a1[2], (__int64)(a1 + 4));
  if ( result && result != 50 && result != 1722 )
    return MicrosoftTelemetryAssertTriggeredNoArgs();
  return result;
}

```

## disassembly

```asm
0x18000be60  push    rbx
0x18000be62  sub     rsp, 20h
0x18000be66  cmp     dword ptr [rcx], 0Fh
0x18000be69  mov     rbx, rcx
0x18000be6c  jnz     short loc_18000BE9A
0x18000be6e  mov     ecx, [rbx+8]
0x18000be71  lea     rdx, [rbx+10h]
0x18000be75  call    UmpoHvPowerRequestCreate
0x18000be7a  test    eax, eax
0x18000be7c  jz      short loc_18000BE83
0x18000be7e  cmp     eax, 32h ; '2'
0x18000be81  jnz     short loc_18000BE89
0x18000be83  add     rsp, 20h
0x18000be87  pop     rbx
0x18000be88  retn
0x18000be89  cmp     eax, 6BAh
0x18000be8e  jz      short loc_18000BE83
0x18000be90  add     rsp, 20h
0x18000be94  pop     rbx
0x18000be95  jmp     MicrosoftTelemetryAssertTriggeredNoArgs
0x18000be9a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000be9f  jmp     short loc_18000BE6E
```
