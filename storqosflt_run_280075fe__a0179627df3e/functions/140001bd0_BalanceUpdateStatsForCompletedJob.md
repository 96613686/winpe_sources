# BalanceUpdateStatsForCompletedJob

- ea: `0x140001bd0`
- end: `0x140001d02`
- name: `BalanceUpdateStatsForCompletedJob`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001ab0`

## callees

- `0x140001bd0`
- `0x140001d10`
- `0x1400021b0`

## pseudocode

```c
bool __fastcall BalanceUpdateStatsForCompletedJob(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r11
  __int64 v7; // r11

  v1 = *(_QWORD *)(a1 + 168);
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 160);
  }
  else
  {
    v1 = *(_QWORD *)(a1 + 160);
    *(_QWORD *)(a1 + 168) = v1;
    v3 = v1;
  }
  v4 = *(_QWORD *)(a1 + 176);
  if ( v4 )
    v1 = v4;
  else
    *(_QWORD *)(a1 + 176) = v1;
  v5 = *(_QWORD *)(a1 + 40);
  _InterlockedAdd64((volatile signed __int64 *)(v5 + 232), v1 - v3);
  _InterlockedAdd64((volatile signed __int64 *)(v5 + 240), *(_QWORD *)(a1 + 176) - *(_QWORD *)(a1 + 168));
  _InterlockedAdd64(
    (volatile signed __int64 *)(v5 + 216),
    (unsigned __int64)((1LL << dword_14000D2A4) - 1 + *(_QWORD *)(a1 + 144)) >> dword_14000D2A4);
  _InterlockedAdd64((volatile signed __int64 *)(v5 + 224), (unsigned __int64)(*(_QWORD *)(a1 + 144) + 1023LL) >> 10);
  _InterlockedIncrement64((volatile signed __int64 *)(v5 + 208));
  if ( *(_QWORD *)(a1 + 176) >= (unsigned __int64)(qword_14000D318 + *(_QWORD *)(v5 + 328))
    && !_interlockedbittestandset((volatile signed __int32 *)(v5 + 320), 0) )
  {
    BalanceUpdateFlowAverageStats(v5, *(_QWORD *)(a1 + 176));
    _interlockedbittestandreset((volatile signed __int32 *)(v7 + 320), 0);
  }
  BalanceUpdateDeviceStats(**(_QWORD **)(a1 + 40), a1);
  _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 200LL));
  return _InterlockedAdd((volatile signed __int32 *)(**(_QWORD **)(a1 + 40) + 4136LL), 0xFFFFFFFF) == 0;
}

```

## disassembly

```asm
0x140001bd0  push    rbx
0x140001bd2  sub     rsp, 20h
0x140001bd6  mov     rax, [rcx+0A8h]
0x140001bdd  mov     rbx, rcx
0x140001be0  test    rax, rax
0x140001be3  jz      loc_140001CE0
0x140001be9  mov     rdx, [rcx+0A0h]
0x140001bf0  mov     rcx, [rcx+0B0h]
0x140001bf7  test    rcx, rcx
0x140001bfa  jz      loc_140001CF6
0x140001c00  mov     rax, rcx
0x140001c03  mov     r11, [rbx+28h]
0x140001c07  sub     rax, rdx
0x140001c0a  lock add [r11+0E8h], rax
0x140001c12  mov     rcx, [rbx+0B0h]
0x140001c19  sub     rcx, [rbx+0A8h]
0x140001c20  lock add [r11+0F0h], rcx
0x140001c28  mov     ecx, cs:dword_14000D2A4
0x140001c2e  mov     edx, 1
0x140001c33  mov     r8, [rbx+90h]
0x140001c3a  shl     rdx, cl
0x140001c3d  dec     rdx
0x140001c40  add     r8, rdx
0x140001c43  shr     r8, cl
0x140001c46  lock add [r11+0D8h], r8
0x140001c4e  mov     rax, [rbx+90h]
0x140001c55  add     rax, 3FFh
0x140001c5b  shr     rax, 0Ah
0x140001c5f  lock add [r11+0E0h], rax
0x140001c67  lock inc qword ptr [r11+0D0h]
0x140001c6f  mov     rcx, [r11+148h]
0x140001c76  add     rcx, cs:qword_14000D318
0x140001c7d  cmp     [rbx+0B0h], rcx
0x140001c84  jnb     short loc_140001CB9
0x140001c86  mov     rcx, [rbx+28h]
0x140001c8a  mov     rdx, rbx
0x140001c8d  mov     rcx, [rcx]
0x140001c90  call    BalanceUpdateDeviceStats
0x140001c95  mov     rax, [rbx+28h]
0x140001c99  lock dec dword ptr [rax+0C8h]
0x140001ca0  mov     rax, [rbx+28h]
0x140001ca4  mov     rcx, [rax]
0x140001ca7  lock add dword ptr [rcx+1028h], 0FFFFFFFFh
0x140001caf  setz    al
0x140001cb2  add     rsp, 20h
0x140001cb6  pop     rbx
0x140001cb7  retn
0x140001cb9  lock bts dword ptr [r11+140h], 0
0x140001cc3  jb      short loc_140001C86
0x140001cc5  mov     rdx, [rbx+0B0h]
0x140001ccc  mov     rcx, r11
0x140001ccf  call    BalanceUpdateFlowAverageStats
0x140001cd4  lock btr dword ptr [r11+140h], 0
0x140001cde  jmp     short loc_140001C86
0x140001ce0  mov     rax, [rcx+0A0h]
0x140001ce7  mov     [rcx+0A8h], rax
0x140001cee  mov     rdx, rax
0x140001cf1  jmp     loc_140001BF0
0x140001cf6  mov     [rbx+0B0h], rax
0x140001cfd  jmp     loc_140001C03
```
