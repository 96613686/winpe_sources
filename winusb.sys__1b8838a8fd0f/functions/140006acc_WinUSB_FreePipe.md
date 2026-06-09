# WinUSB_FreePipe

- ea: `0x140006acc`
- end: `0x140006ca8`
- name: `WinUSB_FreePipe`
- size: `476`
- prototype: `void __fastcall(__int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140007694`
- `0x14001b1e0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140006acc`
- `0x14000751c`
- `0x1400075d8`
- `0x14000cfd0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c56`

## pseudocode

```c
void __fastcall WinUSB_FreePipe(__int64 a1, unsigned __int8 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rsi
  char v6; // al
  _QWORD *v7; // rdi

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      23,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v4 = *(_QWORD *)(a1 + 8 * v2 + 24);
  v5 = v2;
  if ( !v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v6 = v2 & 0xF;
      if ( (v2 & 0x10) != 0 )
        v6 += 0x80;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        3,
        24,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        v6);
    }
    goto LABEL_24;
  }
  if ( WinUSB_IsInterruptOrBulkInPipe(*(_QWORD *)(a1 + 8 * v2 + 24)) )
  {
    if ( *(_QWORD *)(v4 + 72) )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
      *(_QWORD *)(v4 + 72) = 0;
    }
    if ( *(_QWORD *)(v4 + 56) )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
      *(_QWORD *)(v4 + 56) = 0;
    }
    goto LABEL_16;
  }
  if ( WinUSB_IsInterruptOrBulkOutPipe(v4) )
  {
LABEL_16:
    v7 = (_QWORD *)(v4 + 48);
    if ( v4 != -48 && *v7 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
      *v7 = 0;
    }
  }
  if ( *(_QWORD *)(v4 + 104) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    *(_QWORD *)(v4 + 104) = 0;
  }
  if ( *(_DWORD *)(v4 + 12) == 2 )
    WinUSB_FreeIsochPipe((_QWORD *)v4);
  ExFreePoolWithTag((PVOID)v4, 0);
LABEL_24:
  *(_QWORD *)(a1 + 8 * v5 + 24) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        25,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  }
}

```

## disassembly

```asm
0x140006acc  push    rbx
0x140006ace  push    rbp
0x140006acf  push    rsi
0x140006ad0  push    rdi
0x140006ad1  push    r12
0x140006ad3  push    r14
0x140006ad5  push    r15
0x140006ad7  sub     rsp, 30h
0x140006adb  movzx   edi, dl
0x140006ade  mov     rbp, rcx
0x140006ae1  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006ae8  xor     r14d, r14d
0x140006aeb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006af2  lea     r12, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006af9  jz      short loc_140006B21
0x140006afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b02  cmp     [rcx+48h], r14w
0x140006b07  jz      short loc_140006B21
0x140006b09  mov     rcx, [rcx+40h]
0x140006b0d  lea     r9d, [r14+17h]
0x140006b11  lea     r8d, [r14+1]
0x140006b15  mov     [rsp+68h+var_48], r12
0x140006b1a  mov     dl, 5
0x140006b1c  call    WPP_RECORDER_SF_
0x140006b21  mov     rbx, [rbp+rdi*8+18h]
0x140006b26  mov     rsi, rdi
0x140006b29  test    rbx, rbx
0x140006b2c  jnz     short loc_140006B7E
0x140006b2e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006b35  jz      loc_140006C62
0x140006b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b42  cmp     [rcx+48h], r14w
0x140006b47  jz      loc_140006C62
0x140006b4d  mov     eax, edi
0x140006b4f  and     eax, 0Fh
0x140006b52  test    dil, 10h
0x140006b56  jz      short loc_140006B5B
0x140006b58  sub     eax, 0FFFFFF80h
0x140006b5b  mov     rcx, [rcx+40h]
0x140006b5f  mov     r9d, 18h
0x140006b65  mov     [rsp+68h+var_40], eax
0x140006b69  mov     dl, 5
0x140006b6b  mov     [rsp+68h+var_48], r12
0x140006b70  lea     r8d, [r9-15h]
0x140006b74  call    WPP_RECORDER_SF_d
0x140006b79  jmp     loc_140006C62
0x140006b7e  mov     rcx, rbx
0x140006b81  call    WinUSB_IsInterruptOrBulkInPipe
0x140006b86  test    al, al
0x140006b88  jz      short loc_140006BDA
0x140006b8a  mov     rdx, [rbx+48h]
0x140006b8e  test    rdx, rdx
0x140006b91  jz      short loc_140006BB1
0x140006b93  mov     rax, cs:WdfFunctions_01015
0x140006b9a  mov     rcx, cs:WdfDriverGlobals
0x140006ba1  mov     rax, [rax+680h]
0x140006ba8  call    _guard_dispatch_icall
0x140006bad  mov     [rbx+48h], r14
0x140006bb1  mov     rdx, [rbx+38h]
0x140006bb5  test    rdx, rdx
0x140006bb8  jz      short loc_140006BE6
0x140006bba  mov     rax, cs:WdfFunctions_01015
0x140006bc1  mov     rcx, cs:WdfDriverGlobals
0x140006bc8  mov     rax, [rax+680h]
0x140006bcf  call    _guard_dispatch_icall
0x140006bd4  mov     [rbx+38h], r14
0x140006bd8  jmp     short loc_140006BE6
0x140006bda  mov     rcx, rbx
0x140006bdd  call    WinUSB_IsInterruptOrBulkOutPipe
0x140006be2  test    al, al
0x140006be4  jz      short loc_140006C1C
0x140006be6  mov     eax, 30h ; '0'
0x140006beb  mov     rcx, rbx
0x140006bee  lea     rdi, [rax+rbx]
0x140006bf2  test    rdi, rdi
0x140006bf5  jz      short loc_140006C1C
0x140006bf7  mov     rdx, [rdi]
0x140006bfa  test    rdx, rdx
0x140006bfd  jz      short loc_140006C1C
0x140006bff  mov     rax, cs:WdfFunctions_01015
0x140006c06  mov     rcx, cs:WdfDriverGlobals
0x140006c0d  mov     rax, [rax+680h]
0x140006c14  call    _guard_dispatch_icall
0x140006c19  mov     [rdi], r14
0x140006c1c  mov     rdx, [rbx+68h]
0x140006c20  test    rdx, rdx
0x140006c23  jz      short loc_140006C43
0x140006c25  mov     rax, cs:WdfFunctions_01015
0x140006c2c  mov     rcx, cs:WdfDriverGlobals
0x140006c33  mov     rax, [rax+680h]
0x140006c3a  call    _guard_dispatch_icall
0x140006c3f  mov     [rbx+68h], r14
0x140006c43  cmp     dword ptr [rbx+0Ch], 2
0x140006c47  jnz     short loc_140006C51
0x140006c49  mov     rcx, rbx
0x140006c4c  call    WinUSB_FreeIsochPipe
0x140006c51  xor     edx, edx; Tag
0x140006c53  mov     rcx, rbx; P
0x140006c56  call    cs:__imp_ExFreePoolWithTag
0x140006c5d  nop     dword ptr [rax+rax+00h]
0x140006c62  mov     [rbp+rsi*8+18h], r14
0x140006c67  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006c6e  jz      short loc_140006C98
0x140006c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c77  cmp     [rcx+48h], r14w
0x140006c7c  jz      short loc_140006C98
0x140006c7e  mov     rcx, [rcx+40h]
0x140006c82  mov     r9d, 19h
0x140006c88  mov     dl, 5
0x140006c8a  mov     [rsp+68h+var_48], r12
0x140006c8f  lea     r8d, [r9-18h]
0x140006c93  call    WPP_RECORDER_SF_
0x140006c98  add     rsp, 30h
0x140006c9c  pop     r15
0x140006c9e  pop     r14
0x140006ca0  pop     r12
0x140006ca2  pop     rdi
0x140006ca3  pop     rsi
0x140006ca4  pop     rbp
0x140006ca5  pop     rbx
0x140006ca6  retn
```
