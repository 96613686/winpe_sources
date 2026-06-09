# MyService::Stop(int)

- ea: `0x18000aab0`
- end: `0x18000aaee`
- name: `?Stop@MyService@@UEAAXH@Z`
- size: `62`
- prototype: `void __fastcall(HANDLE *this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000aae7`
- `wbemcomn!WbemSetMachineShutdown` at `0x18000aac2`
- `wbemcomn!WbemSetMachineShutdown` at `0x18000aac2`

## pseudocode

```c
void __fastcall MyService::Stop(HANDLE *this, int a2)
{
  if ( a2 )
  {
    WbemSetMachineShutdown(1);
    dword_180032CC8 = 0x80000000;
  }
  else
  {
    dword_180032CC8 = 1;
  }
  SetEvent(this[8]);
}

```

## disassembly

```asm
0x18000aab0  push    rbx
0x18000aab2  sub     rsp, 20h
0x18000aab6  mov     rbx, rcx
0x18000aab9  test    edx, edx
0x18000aabb  jz      short loc_18000AAD4
0x18000aabd  mov     ecx, 1
0x18000aac2  call    cs:__imp_?WbemSetMachineShutdown@@YAHH@Z; WbemSetMachineShutdown(int)
0x18000aac8  mov     cs:dword_180032CC8, 80000000h
0x18000aad2  jmp     short loc_18000AADE
0x18000aad4  mov     cs:dword_180032CC8, 1
0x18000aade  mov     rcx, [rbx+40h]
0x18000aae2  add     rsp, 20h
0x18000aae6  pop     rbx
0x18000aae7  jmp     cs:__imp_SetEvent
```
