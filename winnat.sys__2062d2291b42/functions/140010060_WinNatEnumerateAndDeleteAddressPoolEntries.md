# WinNatEnumerateAndDeleteAddressPoolEntries

- ea: `0x140010060`
- end: `0x140010203`
- name: `WinNatEnumerateAndDeleteAddressPoolEntries`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010ec4`

## callees

- `0x14000a638`
- `0x14000caa0`
- `0x14000f624`
- `0x14000f904`
- `0x140010060`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010145`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010145`

## pseudocode

```c
__int64 __fastcall WinNatEnumerateAndDeleteAddressPoolEntries(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 v5; // rdx
  __int64 **v6; // rcx
  __int64 v7; // r8
  __int64 *v8; // rbx
  __int64 *v9; // r15
  __int64 *v10; // rax
  __int64 **v11; // rcx
  __int64 **v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  char *v15; // rcx
  __int64 *v16; // rax
  PVOID *v17; // rdi
  PVOID *v18; // rbx
  __int64 *v20; // [rsp+20h] [rbp-30h] BYREF
  __int64 ***v21; // [rsp+28h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF

  v21 = (__int64 ***)&v20;
  v20 = (__int64 *)&v20;
  v4 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a2, &LockHandle);
  v8 = *(__int64 **)(a2 + 896);
  if ( v8 != (__int64 *)(a2 + 896) )
  {
    do
    {
      v9 = (__int64 *)*v8;
      if ( *(_QWORD *)(a1 + 528) == v8[3]
        && *(_WORD *)(a1 + 540) == *((_WORD *)v8 + 16)
        && *(_WORD *)(a1 + 542) == *((_WORD *)v8 + 17)
        && (v8[6] & 2) != 0 )
      {
        if ( v8[5] != a2 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
        v10 = (__int64 *)*v8;
        if ( *(__int64 **)(*v8 + 8) != v8
          || (v11 = (__int64 **)v8[1], *v11 != v8)
          || (*v11 = v10, v10[1] = (__int64)v11, *((_BYTE *)v8 + 48) |= 4u, v12 = (__int64 **)v21, *v21 != &v20) )
        {
LABEL_18:
          __fastfail(3u);
        }
        v8[1] = (__int64)v21;
        v6 = &v20;
        *v8 = (__int64)&v20;
        ++v4;
        *v12 = v8;
        v21 = (__int64 ***)v8;
      }
      v8 = v9;
    }
    while ( v9 != (__int64 *)(a2 + 896) );
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v15 = (char *)v20;
    if ( v20 == (__int64 *)&v20 )
      break;
    if ( (__int64 **)v20[1] != &v20 )
      goto LABEL_18;
    v16 = (__int64 *)*v20;
    if ( *(__int64 **)(*v20 + 8) != v20 )
      goto LABEL_18;
    v20 = (__int64 *)*v20;
    v16[1] = (__int64)&v20;
    WinNatDeleteAddressPoolEntry(v15 - 24);
  }
  v17 = (PVOID *)qword_140027B08;
  while ( v17 != &qword_140027B08 )
  {
    v18 = v17;
    v17 = (PVOID *)*v17;
    if ( *(PVOID *)(a1 + 528) == v18[2]
      && *(_WORD *)(a1 + 540) == *((_WORD *)v18 + 12)
      && *(_WORD *)(a1 + 542) == *((_WORD *)v18 + 13) )
    {
      if ( (PVOID)a2 != v18[4] )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v13, v14);
      WinNatDeleteUnspecifiedIf(v18);
      ++v4;
    }
  }
  return v4 == 0 ? 0xC0000225 : 0;
}

```

## disassembly

```asm
0x140010060  push    rbp
0x140010062  push    rbx
0x140010063  push    rsi
0x140010064  push    rdi
0x140010065  push    r13
0x140010067  push    r14
0x140010069  push    r15
0x14001006b  mov     rbp, rsp
0x14001006e  sub     rsp, 50h
0x140010072  xor     eax, eax
0x140010074  mov     r13, rdx
0x140010077  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14001007b  lea     rdx, [rbp+LockHandle]
0x14001007f  lea     rax, [rbp+var_30]
0x140010083  mov     r14, rcx
0x140010086  mov     [rbp+var_28], rax
0x14001008a  xorps   xmm0, xmm0
0x14001008d  lea     rax, [rbp+var_30]
0x140010091  mov     rcx, r13
0x140010094  mov     [rbp+var_30], rax
0x140010098  xor     esi, esi
0x14001009a  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14001009e  call    RtlAcquireScalableWriteLock
0x1400100a3  lea     rdi, [r13+380h]
0x1400100aa  mov     rbx, [rdi]
0x1400100ad  cmp     rbx, rdi
0x1400100b0  jz      loc_140010141
0x1400100b6  mov     rax, [rbx+18h]
0x1400100ba  mov     r15, [rbx]
0x1400100bd  cmp     [r14+210h], rax
0x1400100c4  jnz     short loc_140010135
0x1400100c6  movzx   eax, word ptr [rbx+20h]
0x1400100ca  cmp     [r14+21Ch], ax
0x1400100d2  jnz     short loc_140010135
0x1400100d4  movzx   eax, word ptr [rbx+22h]
0x1400100d8  cmp     [r14+21Eh], ax
0x1400100e0  jnz     short loc_140010135
0x1400100e2  test    byte ptr [rbx+30h], 2
0x1400100e6  jz      short loc_140010135
0x1400100e8  cmp     [rbx+28h], r13
0x1400100ec  jz      short loc_1400100F3
0x1400100ee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400100f3  mov     rax, [rbx]
0x1400100f6  cmp     [rax+8], rbx
0x1400100fa  jnz     loc_140010188
0x140010100  mov     rcx, [rbx+8]
0x140010104  cmp     [rcx], rbx
0x140010107  jnz     short loc_140010188
0x140010109  mov     [rcx], rax
0x14001010c  mov     [rax+8], rcx
0x140010110  lea     rcx, [rbp+var_30]
0x140010114  or      byte ptr [rbx+30h], 4
0x140010118  mov     rax, [rbp+var_28]
0x14001011c  cmp     [rax], rcx
0x14001011f  jnz     short loc_140010188
0x140010121  mov     [rbx+8], rax
0x140010125  lea     rcx, [rbp+var_30]
0x140010129  mov     [rbx], rcx
0x14001012c  inc     esi
0x14001012e  mov     [rax], rbx
0x140010131  mov     [rbp+var_28], rbx
0x140010135  mov     rbx, r15
0x140010138  cmp     r15, rdi
0x14001013b  jnz     loc_1400100B6
0x140010141  lea     rcx, [rbp+LockHandle]; LockHandle
0x140010145  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001014c  nop     dword ptr [rax+rax+00h]
0x140010151  mov     rcx, [rbp+var_30]
0x140010155  lea     rax, [rbp+var_30]
0x140010159  cmp     rcx, rax
0x14001015c  jz      short loc_14001018F
0x14001015e  lea     rax, [rbp+var_30]
0x140010162  cmp     [rcx+8], rax
0x140010166  jnz     short loc_140010188
0x140010168  mov     rax, [rcx]
0x14001016b  cmp     [rax+8], rcx
0x14001016f  jnz     short loc_140010188
0x140010171  lea     rdx, [rbp+var_30]
0x140010175  mov     [rbp+var_30], rax
0x140010179  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x14001017d  mov     [rax+8], rdx
0x140010181  call    WinNatDeleteAddressPoolEntry
0x140010186  jmp     short loc_140010151
0x140010188  mov     ecx, 3
0x14001018d  int     29h; Win8: RtlFailFast(ecx)
0x14001018f  mov     rdi, cs:qword_140027B08
0x140010196  lea     r15, qword_140027B08
0x14001019d  jmp     short loc_1400101E3
0x14001019f  mov     rbx, rdi
0x1400101a2  mov     rdi, [rdi]
0x1400101a5  mov     rax, [rbx+10h]
0x1400101a9  cmp     [r14+210h], rax
0x1400101b0  jnz     short loc_1400101E3
0x1400101b2  movzx   eax, word ptr [rbx+18h]
0x1400101b6  cmp     [r14+21Ch], ax
0x1400101be  jnz     short loc_1400101E3
0x1400101c0  movzx   eax, word ptr [rbx+1Ah]
0x1400101c4  cmp     [r14+21Eh], ax
0x1400101cc  jnz     short loc_1400101E3
0x1400101ce  cmp     r13, [rbx+20h]
0x1400101d2  jz      short loc_1400101D9
0x1400101d4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400101d9  mov     rcx, rbx; P
0x1400101dc  call    WinNatDeleteUnspecifiedIf
0x1400101e1  inc     esi
0x1400101e3  cmp     rdi, r15
0x1400101e6  jnz     short loc_14001019F
0x1400101e8  neg     esi
0x1400101ea  sbb     eax, eax
0x1400101ec  not     eax
0x1400101ee  and     eax, 0C0000225h
0x1400101f3  add     rsp, 50h
0x1400101f7  pop     r15
0x1400101f9  pop     r14
0x1400101fb  pop     r13
0x1400101fd  pop     rdi
0x1400101fe  pop     rsi
0x1400101ff  pop     rbx
0x140010200  pop     rbp
0x140010201  retn
```
