# WinNatEnumerateAndDeleteAddressPoolEntries

- ea: `0x140010000`
- end: `0x1400101a3`
- name: `WinNatEnumerateAndDeleteAddressPoolEntries`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010e64`

## callees

- `0x14000a638`
- `0x14000caa0`
- `0x14000f5cc`
- `0x14000f8ac`
- `0x140010000`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400100e5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400100e5`

## pseudocode

```c
__int64 __fastcall WinNatEnumerateAndDeleteAddressPoolEntries(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 v5; // rdx
  __int64 **v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rbx
  __int64 *v10; // r15
  __int64 *v11; // rax
  __int64 **v12; // rcx
  __int64 **v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  char *v17; // rcx
  __int64 *v18; // rax
  PVOID *v19; // rdi
  PVOID *v20; // rbx
  __int64 *v22; // [rsp+20h] [rbp-30h] BYREF
  __int64 ***v23; // [rsp+28h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF

  v23 = (__int64 ***)&v22;
  v22 = (__int64 *)&v22;
  v4 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a2, &LockHandle);
  v9 = *(__int64 **)(a2 + 896);
  if ( v9 != (__int64 *)(a2 + 896) )
  {
    do
    {
      v10 = (__int64 *)*v9;
      if ( *(_QWORD *)(a1 + 528) == v9[3]
        && *(_WORD *)(a1 + 540) == *((_WORD *)v9 + 16)
        && *(_WORD *)(a1 + 542) == *((_WORD *)v9 + 17)
        && (v9[6] & 2) != 0 )
      {
        if ( v9[5] != a2 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7, v8);
        v11 = (__int64 *)*v9;
        if ( *(__int64 **)(*v9 + 8) != v9
          || (v12 = (__int64 **)v9[1], *v12 != v9)
          || (*v12 = v11, v11[1] = (__int64)v12, *((_BYTE *)v9 + 48) |= 4u, v13 = (__int64 **)v23, *v23 != &v22) )
        {
LABEL_18:
          __fastfail(3u);
        }
        v9[1] = (__int64)v23;
        v6 = &v22;
        *v9 = (__int64)&v22;
        ++v4;
        *v13 = v9;
        v23 = (__int64 ***)v9;
      }
      v9 = v10;
    }
    while ( v10 != (__int64 *)(a2 + 896) );
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v17 = (char *)v22;
    if ( v22 == (__int64 *)&v22 )
      break;
    if ( (__int64 **)v22[1] != &v22 )
      goto LABEL_18;
    v18 = (__int64 *)*v22;
    if ( *(__int64 **)(*v22 + 8) != v22 )
      goto LABEL_18;
    v22 = (__int64 *)*v22;
    v18[1] = (__int64)&v22;
    WinNatDeleteAddressPoolEntry(v17 - 24);
  }
  v19 = (PVOID *)qword_140026B08;
  while ( v19 != &qword_140026B08 )
  {
    v20 = v19;
    v19 = (PVOID *)*v19;
    if ( *(PVOID *)(a1 + 528) == v20[2]
      && *(_WORD *)(a1 + 540) == *((_WORD *)v20 + 12)
      && *(_WORD *)(a1 + 542) == *((_WORD *)v20 + 13) )
    {
      if ( (PVOID)a2 != v20[4] )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v14, v15, v16);
      WinNatDeleteUnspecifiedIf(v20);
      ++v4;
    }
  }
  return v4 == 0 ? 0xC0000225 : 0;
}

```

## disassembly

```asm
0x140010000  push    rbp
0x140010002  push    rbx
0x140010003  push    rsi
0x140010004  push    rdi
0x140010005  push    r13
0x140010007  push    r14
0x140010009  push    r15
0x14001000b  mov     rbp, rsp
0x14001000e  sub     rsp, 50h
0x140010012  xor     eax, eax
0x140010014  mov     r13, rdx
0x140010017  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14001001b  lea     rdx, [rbp+LockHandle]
0x14001001f  lea     rax, [rbp+var_30]
0x140010023  mov     r14, rcx
0x140010026  mov     [rbp+var_28], rax
0x14001002a  xorps   xmm0, xmm0
0x14001002d  lea     rax, [rbp+var_30]
0x140010031  mov     rcx, r13
0x140010034  mov     [rbp+var_30], rax
0x140010038  xor     esi, esi
0x14001003a  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14001003e  call    RtlAcquireScalableWriteLock
0x140010043  lea     rdi, [r13+380h]
0x14001004a  mov     rbx, [rdi]
0x14001004d  cmp     rbx, rdi
0x140010050  jz      loc_1400100E1
0x140010056  mov     rax, [rbx+18h]
0x14001005a  mov     r15, [rbx]
0x14001005d  cmp     [r14+210h], rax
0x140010064  jnz     short loc_1400100D5
0x140010066  movzx   eax, word ptr [rbx+20h]
0x14001006a  cmp     [r14+21Ch], ax
0x140010072  jnz     short loc_1400100D5
0x140010074  movzx   eax, word ptr [rbx+22h]
0x140010078  cmp     [r14+21Eh], ax
0x140010080  jnz     short loc_1400100D5
0x140010082  test    byte ptr [rbx+30h], 2
0x140010086  jz      short loc_1400100D5
0x140010088  cmp     [rbx+28h], r13
0x14001008c  jz      short loc_140010093
0x14001008e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140010093  mov     rax, [rbx]
0x140010096  cmp     [rax+8], rbx
0x14001009a  jnz     loc_140010128
0x1400100a0  mov     rcx, [rbx+8]
0x1400100a4  cmp     [rcx], rbx
0x1400100a7  jnz     short loc_140010128
0x1400100a9  mov     [rcx], rax
0x1400100ac  mov     [rax+8], rcx
0x1400100b0  lea     rcx, [rbp+var_30]
0x1400100b4  or      byte ptr [rbx+30h], 4
0x1400100b8  mov     rax, [rbp+var_28]
0x1400100bc  cmp     [rax], rcx
0x1400100bf  jnz     short loc_140010128
0x1400100c1  mov     [rbx+8], rax
0x1400100c5  lea     rcx, [rbp+var_30]
0x1400100c9  mov     [rbx], rcx
0x1400100cc  inc     esi
0x1400100ce  mov     [rax], rbx
0x1400100d1  mov     [rbp+var_28], rbx
0x1400100d5  mov     rbx, r15
0x1400100d8  cmp     r15, rdi
0x1400100db  jnz     loc_140010056
0x1400100e1  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400100e5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400100ec  nop     dword ptr [rax+rax+00h]
0x1400100f1  mov     rcx, [rbp+var_30]
0x1400100f5  lea     rax, [rbp+var_30]
0x1400100f9  cmp     rcx, rax
0x1400100fc  jz      short loc_14001012F
0x1400100fe  lea     rax, [rbp+var_30]
0x140010102  cmp     [rcx+8], rax
0x140010106  jnz     short loc_140010128
0x140010108  mov     rax, [rcx]
0x14001010b  cmp     [rax+8], rcx
0x14001010f  jnz     short loc_140010128
0x140010111  lea     rdx, [rbp+var_30]
0x140010115  mov     [rbp+var_30], rax
0x140010119  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x14001011d  mov     [rax+8], rdx
0x140010121  call    WinNatDeleteAddressPoolEntry
0x140010126  jmp     short loc_1400100F1
0x140010128  mov     ecx, 3
0x14001012d  int     29h; Win8: RtlFailFast(ecx)
0x14001012f  mov     rdi, cs:qword_140026B08
0x140010136  lea     r15, qword_140026B08
0x14001013d  jmp     short loc_140010183
0x14001013f  mov     rbx, rdi
0x140010142  mov     rdi, [rdi]
0x140010145  mov     rax, [rbx+10h]
0x140010149  cmp     [r14+210h], rax
0x140010150  jnz     short loc_140010183
0x140010152  movzx   eax, word ptr [rbx+18h]
0x140010156  cmp     [r14+21Ch], ax
0x14001015e  jnz     short loc_140010183
0x140010160  movzx   eax, word ptr [rbx+1Ah]
0x140010164  cmp     [r14+21Eh], ax
0x14001016c  jnz     short loc_140010183
0x14001016e  cmp     r13, [rbx+20h]
0x140010172  jz      short loc_140010179
0x140010174  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140010179  mov     rcx, rbx; P
0x14001017c  call    WinNatDeleteUnspecifiedIf
0x140010181  inc     esi
0x140010183  cmp     rdi, r15
0x140010186  jnz     short loc_14001013F
0x140010188  neg     esi
0x14001018a  sbb     eax, eax
0x14001018c  not     eax
0x14001018e  and     eax, 0C0000225h
0x140010193  add     rsp, 50h
0x140010197  pop     r15
0x140010199  pop     r14
0x14001019b  pop     r13
0x14001019d  pop     rdi
0x14001019e  pop     rsi
0x14001019f  pop     rbx
0x1400101a0  pop     rbp
0x1400101a1  retn
```
