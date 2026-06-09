# RootRemoveDeviceInterfaceLockedAndUnlock

- ea: `0x140005fc8`
- end: `0x1400060d0`
- name: `RootRemoveDeviceInterfaceLockedAndUnlock`
- size: `264`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005f28`
- `0x1400066b0`

## callees

- `0x140005fc8`
- `0x14000fe8c`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000607c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000607c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006098`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006098`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000608c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000608c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400060ac`
- `ntoskrnl!ObfDereferenceObject` at `0x1400060ac`

## pseudocode

```c
void __fastcall RootRemoveDeviceInterfaceLockedAndUnlock(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rdx
  void *v6; // rdi
  _QWORD *v7; // rcx
  void **v8; // rax
  char v9; // [rsp+20h] [rbp-18h]

  if ( !*((_BYTE *)a3 + 72) )
  {
    v9 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD *, char))(WdfFunctions_01033 + 624))(
      WdfDriverGlobals,
      a1,
      a3[4],
      a3 + 12,
      v9);
  }
  v5 = a3[2];
  if ( v5 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3040))(
      WdfDriverGlobals,
      *(_QWORD *)(v5 + 320));
    v6 = (void *)a3[5];
    *((_DWORD *)a3 + 12) = 4;
  }
  else
  {
    ChDereferenceChannelInternal(a3[3], 44, 1491);
    v7 = (_QWORD *)*a3;
    if ( *(_QWORD **)(*a3 + 8LL) != a3 || (v8 = (void **)a3[1], *v8 != a3) )
      __fastfail(3u);
    *v8 = v7;
    v6 = 0;
    v7[1] = v8;
    ExFreePoolWithTag(a3, 0x73756256u);
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 24));
  KeLeaveCriticalRegion();
  if ( v6 )
    ObfDereferenceObject(v6);
}

```

## disassembly

```asm
0x140005fc8  mov     [rsp+arg_0], rbx
0x140005fcd  mov     [rsp+arg_8], rsi
0x140005fd2  push    rdi
0x140005fd3  sub     rsp, 30h
0x140005fd7  cmp     byte ptr [r8+48h], 0
0x140005fdc  mov     rbx, r8
0x140005fdf  mov     rsi, rdx
0x140005fe2  jnz     short loc_14000600E
0x140005fe4  mov     rax, cs:WdfFunctions_01033
0x140005feb  lea     r9, [r8+60h]
0x140005fef  mov     r8, [r8+20h]
0x140005ff3  mov     rdx, rcx
0x140005ff6  mov     rcx, cs:WdfDriverGlobals
0x140005ffd  mov     [rsp+38h+var_18], 0
0x140006002  mov     rax, [rax+270h]
0x140006009  call    _guard_dispatch_icall
0x14000600e  mov     rdx, [rbx+10h]
0x140006012  test    rdx, rdx
0x140006015  jz      short loc_140006045
0x140006017  mov     rax, cs:WdfFunctions_01033
0x14000601e  mov     rdx, [rdx+140h]
0x140006025  mov     rcx, cs:WdfDriverGlobals
0x14000602c  mov     rax, [rax+0BE0h]
0x140006033  call    _guard_dispatch_icall
0x140006038  mov     rdi, [rbx+28h]
0x14000603c  mov     dword ptr [rbx+30h], 4
0x140006043  jmp     short loc_140006088
0x140006045  mov     rcx, [rbx+18h]
0x140006049  mov     edx, 2Ch ; ','
0x14000604e  mov     r8d, 5D3h
0x140006054  call    ChDereferenceChannelInternal
0x140006059  mov     rcx, [rbx]
0x14000605c  cmp     [rcx+8], rbx
0x140006060  jnz     short loc_1400060C9
0x140006062  mov     rax, [rbx+8]
0x140006066  cmp     [rax], rbx
0x140006069  jnz     short loc_1400060C9
0x14000606b  mov     [rax], rcx
0x14000606e  xor     edi, edi
0x140006070  mov     [rcx+8], rax
0x140006074  mov     edx, 73756256h; Tag
0x140006079  mov     rcx, rbx; P
0x14000607c  call    cs:__imp_ExFreePoolWithTag
0x140006083  nop     dword ptr [rax+rax+00h]
0x140006088  lea     rcx, [rsi+18h]; FastMutex
0x14000608c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006093  nop     dword ptr [rax+rax+00h]
0x140006098  call    cs:__imp_KeLeaveCriticalRegion
0x14000609f  nop     dword ptr [rax+rax+00h]
0x1400060a4  test    rdi, rdi
0x1400060a7  jz      short loc_1400060B8
0x1400060a9  mov     rcx, rdi; Object
0x1400060ac  call    cs:__imp_ObfDereferenceObject
0x1400060b3  nop     dword ptr [rax+rax+00h]
0x1400060b8  mov     rbx, [rsp+38h+arg_0]
0x1400060bd  mov     rsi, [rsp+38h+arg_8]
0x1400060c2  add     rsp, 30h
0x1400060c6  pop     rdi
0x1400060c7  retn
0x1400060c9  mov     ecx, 3
0x1400060ce  int     29h; Win8: RtlFailFast(ecx)
```
