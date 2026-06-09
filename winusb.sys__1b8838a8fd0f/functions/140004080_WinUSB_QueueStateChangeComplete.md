# WinUSB_QueueStateChangeComplete

- ea: `0x140004080`
- end: `0x140004127`
- name: `WinUSB_QueueStateChangeComplete`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x140004080`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400040d9`
- `ntoskrnl!KeSetEvent` at `0x1400040d9`

## pseudocode

```c
LONG __fastcall WinUSB_QueueStateChangeComplete(__int64 a1, struct _KEVENT *a2)
{
  struct _KEVENT *v2; // rbx
  LONG result; // eax
  int v4; // edx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      10,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  }
  result = KeSetEvent(v2, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v4) = 5;
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               v4,
               1,
               11,
               (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004080  mov     [rsp+arg_0], rbx
0x140004085  mov     [rsp+arg_8], rbp
0x14000408a  push    rdi
0x14000408b  sub     rsp, 30h
0x14000408f  mov     rbx, rdx
0x140004092  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004099  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400040a0  lea     rbp, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x1400040a7  jz      short loc_1400040D1
0x1400040a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040b0  cmp     word ptr [rcx+48h], 0
0x1400040b5  jz      short loc_1400040D1
0x1400040b7  mov     rcx, [rcx+40h]
0x1400040bb  mov     r9d, 0Ah
0x1400040c1  mov     dl, 5
0x1400040c3  mov     [rsp+38h+var_18], rbp
0x1400040c8  lea     r8d, [r9-9]
0x1400040cc  call    WPP_RECORDER_SF_
0x1400040d1  xor     r8d, r8d; Wait
0x1400040d4  xor     edx, edx; Increment
0x1400040d6  mov     rcx, rbx; Event
0x1400040d9  call    cs:__imp_KeSetEvent
0x1400040e0  nop     dword ptr [rax+rax+00h]
0x1400040e5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400040ec  jz      short loc_140004116
0x1400040ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040f5  cmp     word ptr [rcx+48h], 0
0x1400040fa  jz      short loc_140004116
0x1400040fc  mov     rcx, [rcx+40h]
0x140004100  mov     r9d, 0Bh
0x140004106  mov     dl, 5
0x140004108  mov     [rsp+38h+var_18], rbp
0x14000410d  lea     r8d, [r9-0Ah]
0x140004111  call    WPP_RECORDER_SF_
0x140004116  mov     rbx, [rsp+38h+arg_0]
0x14000411b  mov     rbp, [rsp+38h+arg_8]
0x140004120  add     rsp, 30h
0x140004124  pop     rdi
0x140004125  retn
```
