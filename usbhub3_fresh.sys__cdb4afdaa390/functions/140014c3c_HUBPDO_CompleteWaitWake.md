# HUBPDO_CompleteWaitWake

- ea: `0x140014c3c`
- end: `0x140014d02`
- name: `HUBPDO_CompleteWaitWake`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c300`
- `0x14001f220`
- `0x140020cd0`
- `0x1400219d0`
- `0x140025770`

## callees

- `0x1400024b8`
- `0x140014c3c`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140014ca3`
- `ntoskrnl!KeLowerIrql` at `0x140014ca3`
- `ntoskrnl!KfRaiseIrql` at `0x140014c50`
- `ntoskrnl!KfRaiseIrql` at `0x140014c50`

## pseudocode

```c
void __fastcall HUBPDO_CompleteWaitWake(__int64 a1)
{
  KIRQL v2; // bl
  __int64 v3; // rax
  int v4; // esi
  int v5; // edx
  int v6; // [rsp+28h] [rbp-10h]

  v2 = KfRaiseIrql(2u);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(
         WdfDriverGlobals,
         *(_QWORD *)(a1 + 16));
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 688))(
         WdfDriverGlobals,
         v3,
         0);
  KeLowerIrql(v2);
  if ( v4 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = v4;
    LOBYTE(v5) = 3;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v5,
      5,
      151,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v6);
  }
}

```

## disassembly

```asm
0x140014c3c  mov     [rsp+arg_0], rbx
0x140014c41  mov     [rsp+arg_8], rsi
0x140014c46  push    rdi
0x140014c47  sub     rsp, 30h
0x140014c4b  mov     rdi, rcx
0x140014c4e  mov     cl, 2; NewIrql
0x140014c50  call    cs:__imp_KfRaiseIrql
0x140014c57  nop     dword ptr [rax+rax+00h]
0x140014c5c  mov     rdx, cs:WdfFunctions_01015
0x140014c63  mov     bl, al
0x140014c65  mov     rcx, cs:WdfDriverGlobals
0x140014c6c  mov     rax, [rdx+660h]
0x140014c73  mov     rdx, [rdi+10h]
0x140014c77  call    _guard_dispatch_icall
0x140014c7c  mov     rdx, cs:WdfFunctions_01015
0x140014c83  xor     r8d, r8d
0x140014c86  mov     rcx, cs:WdfDriverGlobals
0x140014c8d  mov     r9, [rdx+2B0h]
0x140014c94  mov     rdx, rax
0x140014c97  mov     rax, r9
0x140014c9a  call    _guard_dispatch_icall
0x140014c9f  mov     cl, bl; NewIrql
0x140014ca1  mov     esi, eax
0x140014ca3  call    cs:__imp_KeLowerIrql
0x140014caa  nop     dword ptr [rax+rax+00h]
0x140014caf  test    esi, esi
0x140014cb1  jns     short loc_140014CF1
0x140014cb3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140014cba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014cc1  jz      short loc_140014CF1
0x140014cc3  mov     rcx, [rdi+8]
0x140014cc7  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140014cce  mov     r9d, 97h
0x140014cd4  mov     [rsp+38h+var_10], esi
0x140014cd8  mov     r8d, 5
0x140014cde  mov     [rsp+38h+var_18], rax
0x140014ce3  mov     dl, 3
0x140014ce5  mov     rcx, [rcx+598h]
0x140014cec  call    WPP_RECORDER_SF_d
0x140014cf1  mov     rbx, [rsp+38h+arg_0]
0x140014cf6  mov     rsi, [rsp+38h+arg_8]
0x140014cfb  add     rsp, 30h
0x140014cff  pop     rdi
0x140014d00  retn
```
