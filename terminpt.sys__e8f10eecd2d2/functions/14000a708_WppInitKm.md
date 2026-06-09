# WppInitKm

- ea: `0x14000a708`
- end: `0x14000a7c8`
- name: `WppInitKm`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c1b8`

## callees

- `0x140003130`
- `0x14000a708`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a792`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000a792`
- `WppRecorder!WppAutoLogStart` at `0x14000a7ab`
- `WppRecorder!WppAutoLogStart` at `0x14000a7ab`

## pseudocode

```c
void __fastcall WppInitKm(__int64 a1, __int64 a2)
{
  struct _DEVICE_OBJECT *v4; // rbx
  void (__fastcall *v5)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *); // rax

  if ( WPP_GLOBAL_Control != &WPP_MAIN_CB )
  {
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    if ( WPPTraceSuite == 4 )
    {
      v4 = &WPP_MAIN_CB;
      do
      {
        v5 = (void (__fastcall *)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *))pfnEtwRegisterClassicProvider;
        v4->Vpb = 0;
        v5(v4->DriverObject, 0, WppClassicProviderCallback, v4, &v4->Vpb);
        v4 = v4->NextDevice;
      }
      while ( v4 );
    }
    else if ( WPPTraceSuite == 2 )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = &WppTraceCallback;
      IoWMIRegistrationControl(&WPP_MAIN_CB, 0x80010001);
    }
    WppAutoLogStart(WPP_GLOBAL_Control, a1, a2);
    WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  }
}

```

## disassembly

```asm
0x14000a708  push    rbx
0x14000a70a  push    rbp
0x14000a70b  push    rsi
0x14000a70c  push    rdi
0x14000a70d  sub     rsp, 38h
0x14000a711  lea     rbp, WPP_MAIN_CB
0x14000a718  mov     rdi, rdx
0x14000a71b  cmp     cs:WPP_GLOBAL_Control, rbp
0x14000a722  mov     rsi, rcx
0x14000a725  jz      loc_14000A7BE
0x14000a72b  mov     eax, cs:WPPTraceSuite
0x14000a731  mov     cs:WPP_GLOBAL_Control, rbp
0x14000a738  cmp     eax, 4
0x14000a73b  jnz     short loc_14000A777
0x14000a73d  mov     rbx, rbp
0x14000a740  mov     rax, cs:pfnEtwRegisterClassicProvider
0x14000a747  lea     rcx, [rbx+38h]
0x14000a74b  mov     qword ptr [rcx], 0
0x14000a752  lea     r8, WppClassicProviderCallback
0x14000a759  mov     [rsp+58h+var_38], rcx
0x14000a75e  mov     r9, rbx
0x14000a761  mov     rcx, [rbx+8]
0x14000a765  xor     edx, edx
0x14000a767  call    _guard_dispatch_icall
0x14000a76c  mov     rbx, [rbx+10h]
0x14000a770  test    rbx, rbx
0x14000a773  jnz     short loc_14000A740
0x14000a775  jmp     short loc_14000A79E
0x14000a777  cmp     eax, 2
0x14000a77a  jnz     short loc_14000A79E
0x14000a77c  lea     rax, WppTraceCallback
0x14000a783  mov     edx, 80010001h; Action
0x14000a788  mov     rcx, rbp; DeviceObject
0x14000a78b  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x14000a792  call    cs:__imp_IoWMIRegistrationControl
0x14000a799  nop     dword ptr [rax+rax+00h]
0x14000a79e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7a5  mov     r8, rdi
0x14000a7a8  mov     rdx, rsi
0x14000a7ab  call    cs:__imp_WppAutoLogStart
0x14000a7b2  nop     dword ptr [rax+rax+00h]
0x14000a7b7  mov     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a7be  add     rsp, 38h
0x14000a7c2  pop     rdi
0x14000a7c3  pop     rsi
0x14000a7c4  pop     rbp
0x14000a7c5  pop     rbx
0x14000a7c6  retn
```
