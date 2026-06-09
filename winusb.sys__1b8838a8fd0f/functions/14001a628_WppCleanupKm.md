# WppCleanupKm

- ea: `0x14001a628`
- end: `0x14001a6d5`
- name: `WppCleanupKm`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a3a0`
- `0x14001e03c`

## callees

- `0x140010700`
- `0x14001a628`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14001a665`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14001a665`
- `WppRecorder!WppAutoLogStop` at `0x14001a67b`
- `WppRecorder!WppAutoLogStop` at `0x14001a67b`

## pseudocode

```c
void __fastcall WppCleanupKm(__int64 a1)
{
  PDEVICE_OBJECT v1; // rbx

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v1 )
      {
        if ( v1->Vpb )
        {
          ((void (*)(void))pfnEtwUnregister)();
          v1->Vpb = 0;
        }
        v1 = v1->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    WppAutoLogStop(WPP_GLOBAL_Control, a1);
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
  }
}

```

## disassembly

```asm
0x14001a628  mov     [rsp+arg_0], rbx
0x14001a62d  mov     [rsp+arg_8], rsi
0x14001a632  push    rdi
0x14001a633  sub     rsp, 20h
0x14001a637  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a63e  lea     rsi, WPP_GLOBAL_Control
0x14001a645  mov     rdi, rcx
0x14001a648  cmp     rbx, rsi
0x14001a64b  jz      short loc_14001A69C
0x14001a64d  mov     eax, cs:WPPTraceSuite
0x14001a653  cmp     eax, 4
0x14001a656  jz      short loc_14001A6CE
0x14001a658  cmp     eax, 2
0x14001a65b  jnz     short loc_14001A671
0x14001a65d  mov     edx, 80000002h; Action
0x14001a662  mov     rcx, rbx; DeviceObject
0x14001a665  call    cs:__imp_IoWMIRegistrationControl
0x14001a66c  nop     dword ptr [rax+rax+00h]
0x14001a671  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a678  mov     rdx, rdi
0x14001a67b  call    cs:__imp_WppAutoLogStop
0x14001a682  nop     dword ptr [rax+rax+00h]
0x14001a687  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a68e  mov     cs:WPP_GLOBAL_Control, rsi
0x14001a695  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a69c  mov     rbx, [rsp+28h+arg_0]
0x14001a6a1  mov     rsi, [rsp+28h+arg_8]
0x14001a6a6  add     rsp, 20h
0x14001a6aa  pop     rdi
0x14001a6ab  retn
0x14001a6ad  mov     rcx, [rbx+38h]
0x14001a6b1  test    rcx, rcx
0x14001a6b4  jz      short loc_14001A6CA
0x14001a6b6  mov     rax, cs:pfnEtwUnregister
0x14001a6bd  call    _guard_dispatch_icall
0x14001a6c2  mov     qword ptr [rbx+38h], 0
0x14001a6ca  mov     rbx, [rbx+10h]
0x14001a6ce  test    rbx, rbx
0x14001a6d1  jnz     short loc_14001A6AD
0x14001a6d3  jmp     short loc_14001A671
```
