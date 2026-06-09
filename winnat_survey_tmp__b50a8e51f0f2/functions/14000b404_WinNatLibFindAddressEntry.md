# WinNatLibFindAddressEntry

- ea: `0x14000b404`
- end: `0x14000b5d9`
- name: `WinNatLibFindAddressEntry`
- size: `469`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int16, char, __int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1400085d0`
- `0x140018e40`
- `0x1400191c4`
- `0x1400195fc`
- `0x140019798`
- `0x14001a398`

## callees

- `0x140004d20`
- `0x14000b404`
- `0x14001f020`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b43f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b43f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b565`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b565`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b42d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b42d`

## pseudocode

```c
PKSPIN_LOCK __fastcall WinNatLibFindAddressEntry(
        PKSPIN_LOCK SpinLock,
        const void *a2,
        unsigned __int8 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        char a7,
        _DWORD *a8,
        _BYTE *a9)
{
  PKSPIN_LOCK v9; // rbp
  PKSPIN_LOCK v10; // rbx
  ULONG CurrentProcessorNumber; // eax
  PKSPIN_LOCK v12; // r12
  PKSPIN_LOCK v13; // rsi
  unsigned int v14; // ebp
  PKSPIN_LOCK v15; // rdi
  unsigned __int8 v16; // al
  unsigned __int16 v17; // ax
  KIRQL NewIrql; // [rsp+20h] [rbp-58h]

  v9 = SpinLock;
  v10 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc(SpinLock);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v12 = v9 + 1;
  v13 = (PKSPIN_LOCK)v9[1];
  if ( v13 != v9 + 1 )
  {
    v14 = CurrentProcessorNumber;
    while ( 1 )
    {
      RtlAcquireScalableReadLockAtDpcLevel(v13 - 40, v14);
      v15 = (PKSPIN_LOCK)v13[3];
      if ( v15 == v13 + 3 )
        goto LABEL_16;
      v16 = a3;
      while ( 1 )
      {
        v10 = v15 - 1;
        if ( v16 == *((_BYTE *)v15 + 24) )
          break;
LABEL_26:
        v15 = (PKSPIN_LOCK)*v15;
        v10 = 0;
        if ( v15 == v13 + 3 )
          goto LABEL_16;
      }
      if ( memcmp((const void *)v10[3], a2, v16)
        || a8 && *((_DWORD *)v10 + 30) != *a8
        || a9 && *((_BYTE *)v10 + 207) != *a9 )
      {
        goto LABEL_25;
      }
      v17 = *((_WORD *)v10 + 53);
      if ( a6 )
        break;
      if ( (v17 != a4 || *((_WORD *)v10 + 54) != a5) && (!a7 || a5 < v17 || a4 > *((_WORD *)v10 + 54)) )
        goto LABEL_25;
LABEL_14:
      if ( _InterlockedIncrement64((volatile signed __int64 *)v10) <= 1 )
        __fastfail(0xEu);
LABEL_16:
      _InterlockedDecrement((volatile signed __int32 *)&v13[8 * (v14 & *(_DWORD *)(v13 - 39)) - 32]);
      if ( !v10 )
      {
        v13 = (PKSPIN_LOCK)*v13;
        if ( v13 != v12 )
          continue;
      }
      v9 = SpinLock;
      goto LABEL_19;
    }
    if ( v17 <= a6 && *((_WORD *)v10 + 54) >= a6 )
      goto LABEL_14;
LABEL_25:
    v16 = a3;
    goto LABEL_26;
  }
LABEL_19:
  KeReleaseSpinLock(v9, NewIrql);
  return v10;
}

```

## disassembly

```asm
0x14000b404  mov     rax, rsp
0x14000b407  mov     [rax+20h], r9w
0x14000b40c  mov     [rax+18h], r8b
0x14000b410  mov     [rax+10h], rdx
0x14000b414  mov     [rax+8], rcx
0x14000b418  push    rbx
0x14000b419  push    rbp
0x14000b41a  push    rsi
0x14000b41b  push    rdi
0x14000b41c  push    r12
0x14000b41e  push    r13
0x14000b420  push    r14
0x14000b422  push    r15
0x14000b424  sub     rsp, 38h
0x14000b428  mov     rbp, rcx
0x14000b42b  xor     ebx, ebx
0x14000b42d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b434  nop     dword ptr [rax+rax+00h]
0x14000b439  xor     ecx, ecx; ProcNumber
0x14000b43b  mov     [rsp+78h+NewIrql], al
0x14000b43f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b446  nop     dword ptr [rax+rax+00h]
0x14000b44b  lea     r12, [rbp+8]
0x14000b44f  mov     rsi, [r12]
0x14000b453  cmp     rsi, r12
0x14000b456  jz      loc_14000B55E
0x14000b45c  movzx   r15d, [rsp+78h+arg_28]
0x14000b465  mov     ebp, eax
0x14000b467  lea     r13, [rsi-140h]
0x14000b46e  mov     edx, ebp
0x14000b470  mov     rcx, r13; SpinLock
0x14000b473  call    RtlAcquireScalableReadLockAtDpcLevel
0x14000b478  lea     r14, [r13+158h]
0x14000b47f  mov     rdi, [r14]
0x14000b482  cmp     rdi, r14
0x14000b485  jz      loc_14000B532
0x14000b48b  mov     al, [rsp+78h+arg_10]
0x14000b492  xor     r8d, r8d
0x14000b495  lea     rbx, [rdi-8]
0x14000b499  cmp     al, [rbx+20h]
0x14000b49c  jnz     loc_14000B5C5
0x14000b4a2  mov     rdx, [rsp+78h+Buf2]; Buf2
0x14000b4aa  mov     rcx, [rbx+18h]; Buf1
0x14000b4ae  movzx   r8d, al; Size
0x14000b4b2  call    memcmp
0x14000b4b7  xor     r8d, r8d
0x14000b4ba  test    eax, eax
0x14000b4bc  jnz     loc_14000B5BE
0x14000b4c2  mov     rax, [rsp+78h+arg_38]
0x14000b4ca  test    rax, rax
0x14000b4cd  jz      short loc_14000B4DA
0x14000b4cf  mov     eax, [rax]
0x14000b4d1  cmp     [rbx+78h], eax
0x14000b4d4  jnz     loc_14000B5BE
0x14000b4da  mov     rax, [rsp+78h+arg_40]
0x14000b4e2  test    rax, rax
0x14000b4e5  jz      short loc_14000B4F5
0x14000b4e7  mov     al, [rax]
0x14000b4e9  cmp     [rbx+0CFh], al
0x14000b4ef  jnz     loc_14000B5BE
0x14000b4f5  movzx   eax, word ptr [rbx+6Ah]
0x14000b4f9  test    r15w, r15w
0x14000b4fd  jz      loc_14000B586
0x14000b503  cmp     ax, r15w
0x14000b507  ja      loc_14000B5BE
0x14000b50d  cmp     [rbx+6Ch], r15w
0x14000b512  jb      loc_14000B5BE
0x14000b518  mov     eax, 1
0x14000b51d  lock xadd [rbx], rax
0x14000b522  inc     rax
0x14000b525  cmp     rax, 1
0x14000b529  jg      short loc_14000B532
0x14000b52b  mov     ecx, 0Eh
0x14000b530  int     29h; Win8: RtlFailFast(ecx)
0x14000b532  mov     ecx, [r13+8]
0x14000b536  and     rcx, rbp
0x14000b539  inc     rcx
0x14000b53c  shl     rcx, 6
0x14000b540  lock dec dword ptr [rcx+r13]
0x14000b545  test    rbx, rbx
0x14000b548  jnz     short loc_14000B556
0x14000b54a  mov     rsi, [rsi]
0x14000b54d  cmp     rsi, r12
0x14000b550  jnz     loc_14000B467
0x14000b556  mov     rbp, [rsp+78h+arg_0]
0x14000b55e  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x14000b562  mov     rcx, rbp; SpinLock
0x14000b565  call    cs:__imp_KeReleaseSpinLock
0x14000b56c  nop     dword ptr [rax+rax+00h]
0x14000b571  mov     rax, rbx
0x14000b574  add     rsp, 38h
0x14000b578  pop     r15
0x14000b57a  pop     r14
0x14000b57c  pop     r13
0x14000b57e  pop     r12
0x14000b580  pop     rdi
0x14000b581  pop     rsi
0x14000b582  pop     rbp
0x14000b583  pop     rbx
0x14000b584  retn
0x14000b586  movzx   edx, [rsp+78h+arg_18]
0x14000b58e  movzx   ecx, [rsp+78h+arg_20]
0x14000b596  cmp     ax, dx
0x14000b599  jnz     short loc_14000B5A5
0x14000b59b  cmp     [rbx+6Ch], cx
0x14000b59f  jz      loc_14000B518
0x14000b5a5  cmp     [rsp+78h+arg_30], r8b
0x14000b5ad  jz      short loc_14000B5BE
0x14000b5af  cmp     cx, ax
0x14000b5b2  jb      short loc_14000B5BE
0x14000b5b4  cmp     dx, [rbx+6Ch]
0x14000b5b8  jbe     loc_14000B518
0x14000b5be  mov     al, [rsp+78h+arg_10]
0x14000b5c5  mov     rdi, [rdi]
0x14000b5c8  mov     rbx, r8
0x14000b5cb  cmp     rdi, r14
0x14000b5ce  jnz     loc_14000B495
0x14000b5d4  jmp     loc_14000B532
```
