# CThemeManagerService::SignalStartStop(int)

- ea: `0x18000cf20`
- end: `0x18000cf64`
- name: `?SignalStartStop@CThemeManagerService@@MEAAJH@Z`
- size: `68`
- prototype: `__int64 __fastcall(CThemeManagerService *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000ce50`
- `0x18000cf20`
- `0x18000ec90`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000cf3f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000cf3f`

## pseudocode

```c
__int64 __fastcall CThemeManagerService::SignalStartStop(CThemeManagerService *this, int a2)
{
  if ( a2 && !QueueUserWorkItem((LPTHREAD_START_ROUTINE)CThemeManagerService::SignalSessionEvents, 0, 0) )
    CThemeManagerService::SignalSessionEvents(0);
  return CService::SignalStartStop(this, a2);
}

```

## disassembly

```asm
0x18000cf20  mov     [rsp+arg_0], rbx
0x18000cf25  push    rdi
0x18000cf26  sub     rsp, 20h
0x18000cf2a  mov     ebx, edx
0x18000cf2c  mov     rdi, rcx
0x18000cf2f  test    edx, edx
0x18000cf31  jz      short loc_18000CF50
0x18000cf33  xor     r8d, r8d; Flags
0x18000cf36  lea     rcx, ?SignalSessionEvents@CThemeManagerService@@SAKPEAX@Z; Function
0x18000cf3d  xor     edx, edx; Context
0x18000cf3f  call    cs:__imp_QueueUserWorkItem
0x18000cf45  test    eax, eax
0x18000cf47  jnz     short loc_18000CF50
0x18000cf49  xor     ecx, ecx; Parameter
0x18000cf4b  call    ?SignalSessionEvents@CThemeManagerService@@SAKPEAX@Z; CThemeManagerService::SignalSessionEvents(void *)
0x18000cf50  mov     edx, ebx; int
0x18000cf52  mov     rcx, rdi; this
0x18000cf55  mov     rbx, [rsp+28h+arg_0]
0x18000cf5a  add     rsp, 20h
0x18000cf5e  pop     rdi
0x18000cf5f  jmp     ?SignalStartStop@CService@@MEAAJH@Z; CService::SignalStartStop(int)
```
