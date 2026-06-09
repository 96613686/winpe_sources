# PtPnPComplete

- ea: `0x140001020`
- end: `0x1400010ad`
- name: `PtPnPComplete`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x14000173c`
- `0x1400019a8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001069`
- `ntoskrnl!KeSetEvent` at `0x140001069`

## pseudocode

```c
__int64 __fastcall PtPnPComplete(__int64 a1, int a2, struct _KEVENT *a3)
{
  int v4; // edx
  int v5; // r8d

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      18,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  KeSetEvent(a3, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      19,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001020  push    rbx
0x140001022  push    rbp
0x140001023  push    rsi
0x140001024  push    rdi
0x140001025  sub     rsp, 48h
0x140001029  mov     rdi, r8
0x14000102c  mov     rbx, rcx
0x14000102f  lea     rbp, WPP_RECORDER_INITIALIZED
0x140001036  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000103d  lea     rsi, WPP_75fd79d40e58354b8c24f648881272a9_Traceguids
0x140001044  jz      short loc_140001061
0x140001046  mov     rcx, cs:WPP_GLOBAL_Control
0x14000104d  mov     r9d, 12h
0x140001053  mov     [rsp+68h+var_48], rsi
0x140001058  mov     rcx, [rcx+40h]
0x14000105c  call    WPP_RECORDER_SF_s
0x140001061  xor     r8d, r8d; Wait
0x140001064  xor     edx, edx; Increment
0x140001066  mov     rcx, rdi; Event
0x140001069  call    cs:__imp_KeSetEvent
0x140001070  nop     dword ptr [rax+rax+00h]
0x140001075  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000107c  jz      short loc_14000109E
0x14000107e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001085  mov     r9d, 13h
0x14000108b  mov     [rsp+68h+var_38], rbx
0x140001090  mov     [rsp+68h+var_48], rsi
0x140001095  mov     rcx, [rcx+40h]
0x140001099  call    WPP_RECORDER_SF_sq
0x14000109e  mov     eax, 0C0000016h
0x1400010a3  add     rsp, 48h
0x1400010a7  pop     rdi
0x1400010a8  pop     rsi
0x1400010a9  pop     rbp
0x1400010aa  pop     rbx
0x1400010ab  retn
```
