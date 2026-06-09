# WppInitKm

- ea: `0x14000c430`
- end: `0x14000c4bd`
- name: `WppInitKm`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d03c`

## callees

- `0x140006370`
- `0x14000c430`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000c4aa`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000c4aa`

## pseudocode

```c
void WppInitKm()
{
  struct _DEVICE_OBJECT *v0; // rbx
  void (__fastcall *v1)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *); // rax

  v0 = &WPP_MAIN_CB;
  if ( WPP_GLOBAL_Control != &WPP_MAIN_CB )
  {
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    if ( WPPTraceSuite == 4 )
    {
      do
      {
        v1 = (void (__fastcall *)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *))pfnEtwRegisterClassicProvider;
        v0->Vpb = 0;
        v1(v0->DriverObject, 0, WppClassicProviderCallback, v0, &v0->Vpb);
        v0 = v0->NextDevice;
      }
      while ( v0 );
    }
    else if ( WPPTraceSuite == 2 )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = &WppTraceCallback;
      IoWMIRegistrationControl(&WPP_MAIN_CB, 0x80010001);
    }
  }
}

```

## disassembly

```asm
0x14000c430  push    rbx
0x14000c432  sub     rsp, 30h
0x14000c436  lea     rbx, WPP_MAIN_CB
0x14000c43d  cmp     cs:WPP_GLOBAL_Control, rbx
0x14000c444  jz      short loc_14000C4B6
0x14000c446  mov     eax, cs:WPPTraceSuite
0x14000c44c  mov     cs:WPP_GLOBAL_Control, rbx
0x14000c453  cmp     eax, 4
0x14000c456  jnz     short loc_14000C48F
0x14000c458  mov     rax, cs:pfnEtwRegisterClassicProvider
0x14000c45f  lea     rcx, [rbx+38h]
0x14000c463  mov     qword ptr [rcx], 0
0x14000c46a  lea     r8, WppClassicProviderCallback
0x14000c471  mov     [rsp+38h+var_18], rcx
0x14000c476  mov     r9, rbx
0x14000c479  mov     rcx, [rbx+8]
0x14000c47d  xor     edx, edx
0x14000c47f  call    _guard_dispatch_icall
0x14000c484  mov     rbx, [rbx+10h]
0x14000c488  test    rbx, rbx
0x14000c48b  jnz     short loc_14000C458
0x14000c48d  jmp     short loc_14000C4B6
0x14000c48f  cmp     eax, 2
0x14000c492  jnz     short loc_14000C4B6
0x14000c494  lea     rax, WppTraceCallback
0x14000c49b  mov     edx, 80010001h; Action
0x14000c4a0  mov     rcx, rbx; DeviceObject
0x14000c4a3  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x14000c4aa  call    cs:__imp_IoWMIRegistrationControl
0x14000c4b1  nop     dword ptr [rax+rax+00h]
0x14000c4b6  add     rsp, 30h
0x14000c4ba  pop     rbx
0x14000c4bb  retn
```
