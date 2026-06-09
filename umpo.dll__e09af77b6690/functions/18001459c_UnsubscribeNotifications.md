# UnsubscribeNotifications

- ea: `0x18001459c`
- end: `0x180014608`
- name: `UnsubscribeNotifications`
- size: `108`
- prototype: `BOOLEAN __fastcall(int, _QWORD *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013414`

## callees

- `0x18001459c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800145dd`
- `ntdll!RtlFreeHeap` at `0x1800145dd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800145c2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800145c2`
- `policymanager!SettingsManagerStore_ReleaseWnfNames` at `0x1800145f2`
- `policymanager!SettingsManagerStore_ReleaseWnfNames` at `0x1800145f2`

## pseudocode

```c
BOOLEAN __fastcall UnsubscribeNotifications(int a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  int i; // ebx
  BOOLEAN result; // al
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  for ( i = a1; i; result = RtlUnsubscribeWnfNotificationWaitForCompletion(a2[i]) )
    --i;
  if ( a2 )
    result = RtlFreeHeap(UmpoHeapHandle, 0, a2);
  if ( v8 )
    return SettingsManagerStore_ReleaseWnfNames(&v8, a4);
  return result;
}

```

## disassembly

```asm
0x18001459c  mov     [rsp+arg_0], rbx
0x1800145a1  mov     [rsp+arg_8], rsi
0x1800145a6  mov     [rsp+arg_10], r8
0x1800145ab  push    rdi
0x1800145ac  sub     rsp, 20h
0x1800145b0  mov     esi, r9d
0x1800145b3  mov     rdi, rdx
0x1800145b6  mov     ebx, ecx
0x1800145b8  test    ecx, ecx
0x1800145ba  jz      short loc_1800145CC
0x1800145bc  dec     ebx
0x1800145be  mov     rcx, [rdi+rbx*8]
0x1800145c2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800145c8  test    ebx, ebx
0x1800145ca  jnz     short loc_1800145BC
0x1800145cc  test    rdi, rdi
0x1800145cf  jz      short loc_1800145E3
0x1800145d1  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800145d8  mov     r8, rdi; P
0x1800145db  xor     edx, edx; Flags
0x1800145dd  call    cs:__imp_RtlFreeHeap
0x1800145e3  cmp     [rsp+28h+arg_10], 0
0x1800145e9  jz      short loc_1800145F8
0x1800145eb  mov     edx, esi
0x1800145ed  lea     rcx, [rsp+28h+arg_10]
0x1800145f2  call    cs:__imp_SettingsManagerStore_ReleaseWnfNames
0x1800145f8  mov     rbx, [rsp+28h+arg_0]
0x1800145fd  mov     rsi, [rsp+28h+arg_8]
0x180014602  add     rsp, 20h
0x180014606  pop     rdi
0x180014607  retn
```
