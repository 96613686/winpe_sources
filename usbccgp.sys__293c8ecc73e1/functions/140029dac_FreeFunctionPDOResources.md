# FreeFunctionPDOResources

- ea: `0x140029dac`
- end: `0x140029e63`
- name: `FreeFunctionPDOResources`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a448`

## callees

- `0x14000ad80`
- `0x14000b4bc`
- `0x140029dac`
- `0x14002a0b0`
- `0x14002a1cc`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140029e12`
- `ntoskrnl!IoDeleteDevice` at `0x140029e12`

## string_xrefs

- `0x140029e03`: `removeEvent`

## pseudocode

```c
void __fastcall FreeFunctionPDOResources(__int64 a1)
{
  PDEVICE_OBJECT *v2; // rsi

  v2 = (PDEVICE_OBJECT *)(a1 + 224);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      *(_QWORD *)(a1 + 392),
      4,
      2,
      45,
      (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
      (char)*v2,
      *(_DWORD *)(a1 + 4));
  FreeResourcesForFunctionSuspend(a1);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(a1 + 20);
  *(_DWORD *)(a1 + 20) = 10;
  UsbcDereferencePdo(a1);
  WaitForSignal((PVOID)(a1 + 312));
  IoDeleteDevice(*v2);
}

```

## disassembly

```asm
0x140029dac  mov     [rsp+arg_0], rbx
0x140029db1  mov     [rsp+arg_8], rsi
0x140029db6  push    rdi
0x140029db7  sub     rsp, 40h
0x140029dbb  mov     rbx, rcx
0x140029dbe  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029dc5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029dcc  lea     rsi, [rcx+0E0h]
0x140029dd3  lea     rdi, [rcx+188h]
0x140029dda  jnz     short loc_140029E2F
0x140029ddc  mov     rcx, rbx
0x140029ddf  call    FreeResourcesForFunctionSuspend
0x140029de4  mov     eax, [rbx+14h]
0x140029de7  mov     rcx, rbx
0x140029dea  mov     [rbx+18h], eax
0x140029ded  mov     dword ptr [rbx+14h], 0Ah
0x140029df4  call    UsbcDereferencePdo
0x140029df9  mov     r8, [rdi]
0x140029dfc  lea     rcx, [rbx+138h]; Object
0x140029e03  lea     rdx, aRemoveevent; "removeEvent"
0x140029e0a  call    WaitForSignal
0x140029e0f  mov     rcx, [rsi]; DeviceObject
0x140029e12  call    cs:__imp_IoDeleteDevice
0x140029e19  nop     dword ptr [rax+rax+00h]
0x140029e1e  mov     rbx, [rsp+48h+arg_0]
0x140029e23  mov     rsi, [rsp+48h+arg_8]
0x140029e28  add     rsp, 40h
0x140029e2c  pop     rdi
0x140029e2d  retn
0x140029e2f  mov     eax, [rcx+4]
0x140029e32  mov     r9d, 2Dh ; '-'
0x140029e38  mov     rcx, [rdi]
0x140029e3b  mov     dl, 4
0x140029e3d  mov     [rsp+48h+var_18], eax
0x140029e41  mov     rax, [rsi]
0x140029e44  mov     [rsp+48h+var_20], rax
0x140029e49  lea     r8d, [r9-2Bh]
0x140029e4d  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140029e54  mov     [rsp+48h+var_28], rax
0x140029e59  call    WPP_RECORDER_SF_qD
0x140029e5e  jmp     loc_140029DDC
```
