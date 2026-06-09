# WinUSB_HandlePipeError

- ea: `0x140006cb0`
- end: `0x140006de6`
- name: `WinUSB_HandlePipeError`
- size: `310`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400093e0`
- `0x1400099d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140006cb0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006d71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006d71`

## pseudocode

```c
__int64 __fastcall WinUSB_HandlePipeError(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  KIRQL v6; // al
  _QWORD *v7; // rdx
  int v8; // ebx
  int v9; // edx

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      55,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  }
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a3,
         off_140015040);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 120));
  v7 = *(_QWORD **)(v4 + 144);
  if ( *v7 != v4 + 136 )
    __fastfail(3u);
  *(_QWORD *)(v5 + 32) = v4 + 136;
  *(_QWORD *)(v5 + 40) = v7;
  *v7 = v5 + 32;
  *(_QWORD *)(v4 + 144) = v5 + 32;
  v8 = *(_DWORD *)(v4 + 128);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 120), v6);
  if ( !v8 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 3040))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 152));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      56,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x140006cb0  push    rbx
0x140006cb2  push    rbp
0x140006cb3  push    rsi
0x140006cb4  push    rdi
0x140006cb5  push    r12
0x140006cb7  push    r14
0x140006cb9  sub     rsp, 38h
0x140006cbd  mov     rbx, r8
0x140006cc0  mov     rdi, rdx
0x140006cc3  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006cca  xor     ebp, ebp
0x140006ccc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140006cd3  lea     r12, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006cda  jz      short loc_140006D01
0x140006cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ce3  cmp     [rcx+48h], bp
0x140006ce7  jz      short loc_140006D01
0x140006ce9  mov     rcx, [rcx+40h]
0x140006ced  lea     r9d, [rbp+37h]
0x140006cf1  lea     r8d, [rbp+1]
0x140006cf5  mov     [rsp+68h+var_48], r12
0x140006cfa  mov     dl, 5
0x140006cfc  call    WPP_RECORDER_SF_
0x140006d01  mov     rax, cs:WdfFunctions_01015
0x140006d08  mov     rdx, rbx
0x140006d0b  mov     r8, cs:off_140015040
0x140006d12  mov     rcx, cs:WdfDriverGlobals
0x140006d19  mov     rax, [rax+650h]
0x140006d20  call    _guard_dispatch_icall
0x140006d25  lea     rcx, [rdi+78h]; SpinLock
0x140006d29  mov     rbx, rax
0x140006d2c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006d33  nop     dword ptr [rax+rax+00h]
0x140006d38  lea     rcx, [rdi+88h]
0x140006d3f  mov     r8b, al
0x140006d42  mov     rdx, [rcx+8]
0x140006d46  cmp     [rdx], rcx
0x140006d49  jz      short loc_140006D52
0x140006d4b  mov     ecx, 3
0x140006d50  int     29h; Win8: RtlFailFast(ecx)
0x140006d52  lea     rax, [rbx+20h]
0x140006d56  mov     [rax], rcx
0x140006d59  mov     [rax+8], rdx
0x140006d5d  mov     [rdx], rax
0x140006d60  mov     dl, r8b; NewIrql
0x140006d63  mov     [rcx+8], rax
0x140006d67  lea     rcx, [rdi+78h]; SpinLock
0x140006d6b  mov     ebx, [rdi+80h]
0x140006d71  call    cs:__imp_KeReleaseSpinLock
0x140006d78  nop     dword ptr [rax+rax+00h]
0x140006d7d  test    ebx, ebx
0x140006d7f  jnz     short loc_140006DA2
0x140006d81  mov     rax, cs:WdfFunctions_01015
0x140006d88  mov     rdx, [rdi+98h]
0x140006d8f  mov     rcx, cs:WdfDriverGlobals
0x140006d96  mov     rax, [rax+0BE0h]
0x140006d9d  call    _guard_dispatch_icall
0x140006da2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140006da9  jz      short loc_140006DD6
0x140006dab  mov     rcx, cs:WPP_GLOBAL_Control
0x140006db2  cmp     [rcx+48h], bp
0x140006db6  jz      short loc_140006DD6
0x140006db8  mov     rcx, [rcx+40h]
0x140006dbc  mov     r9d, 38h ; '8'
0x140006dc2  mov     [rsp+68h+var_40], ebp
0x140006dc6  mov     dl, 5
0x140006dc8  mov     [rsp+68h+var_48], r12
0x140006dcd  lea     r8d, [r9-37h]
0x140006dd1  call    WPP_RECORDER_SF_d
0x140006dd6  xor     eax, eax
0x140006dd8  add     rsp, 38h
0x140006ddc  pop     r14
0x140006dde  pop     r12
0x140006de0  pop     rdi
0x140006de1  pop     rsi
0x140006de2  pop     rbp
0x140006de3  pop     rbx
0x140006de4  retn
```
