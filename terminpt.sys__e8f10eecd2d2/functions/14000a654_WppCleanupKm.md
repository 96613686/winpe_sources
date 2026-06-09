# WppCleanupKm

- ea: `0x14000a654`
- end: `0x14000a701`
- name: `WppCleanupKm`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a500`

## callees

- `0x140003130`
- `0x14000a654`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a691`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a691`
- `WppRecorder!WppAutoLogStop` at `0x14000a6a7`
- `WppRecorder!WppAutoLogStop` at `0x14000a6a7`

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
0x14000a654  mov     [rsp+arg_0], rbx
0x14000a659  mov     [rsp+arg_8], rsi
0x14000a65e  push    rdi
0x14000a65f  sub     rsp, 20h
0x14000a663  mov     rbx, cs:WPP_GLOBAL_Control
0x14000a66a  lea     rsi, WPP_GLOBAL_Control
0x14000a671  mov     rdi, rcx
0x14000a674  cmp     rbx, rsi
0x14000a677  jz      short loc_14000A6C8
0x14000a679  mov     eax, cs:WPPTraceSuite
0x14000a67f  cmp     eax, 4
0x14000a682  jz      short loc_14000A6FA
0x14000a684  cmp     eax, 2
0x14000a687  jnz     short loc_14000A69D
0x14000a689  mov     edx, 80000002h; Action
0x14000a68e  mov     rcx, rbx; DeviceObject
0x14000a691  call    cs:__imp_IoWMIRegistrationControl
0x14000a698  nop     dword ptr [rax+rax+00h]
0x14000a69d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6a4  mov     rdx, rdi
0x14000a6a7  call    cs:__imp_WppAutoLogStop
0x14000a6ae  nop     dword ptr [rax+rax+00h]
0x14000a6b3  lea     rax, WPP_RECORDER_INITIALIZED
0x14000a6ba  mov     cs:WPP_GLOBAL_Control, rsi
0x14000a6c1  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a6c8  mov     rbx, [rsp+28h+arg_0]
0x14000a6cd  mov     rsi, [rsp+28h+arg_8]
0x14000a6d2  add     rsp, 20h
0x14000a6d6  pop     rdi
0x14000a6d7  retn
0x14000a6d9  mov     rcx, [rbx+38h]
0x14000a6dd  test    rcx, rcx
0x14000a6e0  jz      short loc_14000A6F6
0x14000a6e2  mov     rax, cs:pfnEtwUnregister
0x14000a6e9  call    _guard_dispatch_icall
0x14000a6ee  mov     qword ptr [rbx+38h], 0
0x14000a6f6  mov     rbx, [rbx+10h]
0x14000a6fa  test    rbx, rbx
0x14000a6fd  jnz     short loc_14000A6D9
0x14000a6ff  jmp     short loc_14000A69D
```
