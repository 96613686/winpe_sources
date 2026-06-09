# WppCleanupKm

- ea: `0x140017008`
- end: `0x140017084`
- name: `WppCleanupKm`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d690`
- `0x140019078`

## callees

- `0x14000f150`
- `0x140017008`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14001703d`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14001703d`

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
0x140017008  mov     [rsp+arg_0], rbx
0x14001700d  push    rdi
0x14001700e  sub     rsp, 20h
0x140017012  mov     rbx, cs:WPP_GLOBAL_Control
0x140017019  lea     rdi, WPP_GLOBAL_Control
0x140017020  cmp     rbx, rdi
0x140017023  jz      short loc_140017050
0x140017025  mov     eax, cs:WPPTraceSuite
0x14001702b  cmp     eax, 4
0x14001702e  jz      short loc_14001707D
0x140017030  cmp     eax, 2
0x140017033  jnz     short loc_140017049
0x140017035  mov     edx, 80000002h; Action
0x14001703a  mov     rcx, rbx; DeviceObject
0x14001703d  call    cs:__imp_IoWMIRegistrationControl
0x140017044  nop     dword ptr [rax+rax+00h]
0x140017049  mov     cs:WPP_GLOBAL_Control, rdi
0x140017050  mov     rbx, [rsp+28h+arg_0]
0x140017055  add     rsp, 20h
0x140017059  pop     rdi
0x14001705a  retn
0x14001705c  mov     rcx, [rbx+38h]
0x140017060  test    rcx, rcx
0x140017063  jz      short loc_140017079
0x140017065  mov     rax, cs:pfnEtwUnregister
0x14001706c  call    _guard_dispatch_icall
0x140017071  mov     qword ptr [rbx+38h], 0
0x140017079  mov     rbx, [rbx+10h]
0x14001707d  test    rbx, rbx
0x140017080  jnz     short loc_14001705C
0x140017082  jmp     short loc_140017049
```
