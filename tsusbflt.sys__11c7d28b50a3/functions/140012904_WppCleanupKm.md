# WppCleanupKm

- ea: `0x140012904`
- end: `0x140012980`
- name: `WppCleanupKm`
- size: `124`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012490`
- `0x14001303c`

## callees

- `0x14000aa30`
- `0x140012904`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x140012939`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140012939`

## pseudocode

```c
void WppCleanupKm()
{
  PDEVICE_OBJECT v0; // rbx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v0 )
      {
        if ( v0->Vpb )
        {
          ((void (*)(void))pfnEtwUnregister)();
          v0->Vpb = 0;
        }
        v0 = v0->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x140012904  mov     [rsp+arg_0], rbx
0x140012909  push    rdi
0x14001290a  sub     rsp, 20h
0x14001290e  mov     rbx, cs:WPP_GLOBAL_Control
0x140012915  lea     rdi, WPP_GLOBAL_Control
0x14001291c  cmp     rbx, rdi
0x14001291f  jz      short loc_14001294C
0x140012921  mov     eax, cs:WPPTraceSuite
0x140012927  cmp     eax, 4
0x14001292a  jz      short loc_140012979
0x14001292c  cmp     eax, 2
0x14001292f  jnz     short loc_140012945
0x140012931  mov     edx, 80000002h; Action
0x140012936  mov     rcx, rbx; DeviceObject
0x140012939  call    cs:__imp_IoWMIRegistrationControl
0x140012940  nop     dword ptr [rax+rax+00h]
0x140012945  mov     cs:WPP_GLOBAL_Control, rdi
0x14001294c  mov     rbx, [rsp+28h+arg_0]
0x140012951  add     rsp, 20h
0x140012955  pop     rdi
0x140012956  retn
0x140012958  mov     rcx, [rbx+38h]
0x14001295c  test    rcx, rcx
0x14001295f  jz      short loc_140012975
0x140012961  mov     rax, cs:pfnEtwUnregister
0x140012968  call    _guard_dispatch_icall
0x14001296d  mov     qword ptr [rbx+38h], 0
0x140012975  mov     rbx, [rbx+10h]
0x140012979  test    rbx, rbx
0x14001297c  jnz     short loc_140012958
0x14001297e  jmp     short loc_140012945
```
