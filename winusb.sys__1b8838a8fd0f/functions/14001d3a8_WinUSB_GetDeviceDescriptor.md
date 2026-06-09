# WinUSB_GetDeviceDescriptor

- ea: `0x14001d3a8`
- end: `0x14001d4af`
- name: `WinUSB_GetDeviceDescriptor`
- size: `263`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001b370`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140010700`
- `0x14001d3a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d402`
- `ntoskrnl!ExAllocatePool2` at `0x14001d402`

## pseudocode

```c
__int64 __fastcall WinUSB_GetDeviceDescriptor(__int64 a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  unsigned int v4; // ebx
  int v5; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      10,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  Pool2 = ExAllocatePool2(64, 18, 1112757591);
  *(_QWORD *)(a1 + 48) = Pool2;
  if ( Pool2 )
  {
    v4 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2592))(
      WdfDriverGlobals,
      *(_QWORD *)(a1 + 8),
      Pool2);
  }
  else
  {
    v4 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v4;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      3,
      11,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      154);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      12,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001d3a8  push    rbx
0x14001d3aa  push    rbp
0x14001d3ab  push    rsi
0x14001d3ac  push    rdi
0x14001d3ad  push    r14
0x14001d3af  sub     rsp, 30h
0x14001d3b3  mov     rdi, rcx
0x14001d3b6  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d3bd  xor     esi, esi
0x14001d3bf  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d3c6  lea     r14, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x14001d3cd  jz      short loc_14001D3F4
0x14001d3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3d6  cmp     [rcx+48h], si
0x14001d3da  jz      short loc_14001D3F4
0x14001d3dc  mov     rcx, [rcx+40h]
0x14001d3e0  lea     r9d, [rsi+0Ah]
0x14001d3e4  lea     r8d, [rsi+1]
0x14001d3e8  mov     [rsp+58h+var_38], r14
0x14001d3ed  mov     dl, 5
0x14001d3ef  call    WPP_RECORDER_SF_
0x14001d3f4  mov     edx, 12h
0x14001d3f9  mov     r8d, 42535557h
0x14001d3ff  lea     ecx, [rdx+2Eh]
0x14001d402  call    cs:__imp_ExAllocatePool2
0x14001d409  nop     dword ptr [rax+rax+00h]
0x14001d40e  mov     [rdi+30h], rax
0x14001d412  mov     r8, rax
0x14001d415  test    rax, rax
0x14001d418  jnz     short loc_14001D44D
0x14001d41a  mov     ebx, 0C000009Ah
0x14001d41f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001d426  jz      short loc_14001D4A1
0x14001d428  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d42f  lea     r9d, [rax+0Bh]
0x14001d433  mov     [rsp+58h+var_30], ebx
0x14001d437  lea     r8d, [rax+3]
0x14001d43b  mov     dl, 2
0x14001d43d  mov     [rsp+58h+var_38], r14
0x14001d442  mov     rcx, [rcx+40h]
0x14001d446  call    WPP_RECORDER_SF_d
0x14001d44b  jmp     short loc_14001D46D
0x14001d44d  mov     rax, cs:WdfFunctions_01015
0x14001d454  mov     ebx, esi
0x14001d456  mov     rdx, [rdi+8]
0x14001d45a  mov     rcx, cs:WdfDriverGlobals
0x14001d461  mov     rax, [rax+0A20h]
0x14001d468  call    _guard_dispatch_icall
0x14001d46d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001d474  jz      short loc_14001D4A1
0x14001d476  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d47d  cmp     [rcx+48h], si
0x14001d481  jz      short loc_14001D4A1
0x14001d483  mov     rcx, [rcx+40h]
0x14001d487  mov     r9d, 0Ch
0x14001d48d  mov     [rsp+58h+var_30], ebx
0x14001d491  mov     dl, 5
0x14001d493  mov     [rsp+58h+var_38], r14
0x14001d498  lea     r8d, [r9-0Bh]
0x14001d49c  call    WPP_RECORDER_SF_d
0x14001d4a1  mov     eax, ebx
0x14001d4a3  add     rsp, 30h
0x14001d4a7  pop     r14
0x14001d4a9  pop     rdi
0x14001d4aa  pop     rsi
0x14001d4ab  pop     rbp
0x14001d4ac  pop     rbx
0x14001d4ad  retn
```
