# GetAdapterFromDeviceGuid

- ea: `0x14000d090`
- end: `0x14000d1b7`
- name: `GetAdapterFromDeviceGuid`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc5c`
- `0x14000df30`

## callees

- `0x14000d090`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d0ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d0ad`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d0ec`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d0ec`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d0d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d0d9`
- `ntoskrnl!KeLowerIrql` at `0x14000d196`
- `ntoskrnl!KeLowerIrql` at `0x14000d196`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d185`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d185`

## pseudocode

```c
char __fastcall GetAdapterFromDeviceGuid(_QWORD *a1, __int64 **a2)
{
  __int64 *v3; // rdi
  KIRQL v5; // bp
  __int64 *i; // rcx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  char v9; // bl
  __int64 v10; // rdx

  v3 = 0;
  *a2 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
  KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
  for ( i = (__int64 *)g_leMappedAdapterList; i != &g_leMappedAdapterList; i = (__int64 *)*i )
  {
    v3 = i;
    v7 = i[19] - *a1;
    if ( !v7 )
      v7 = i[20] - a1[1];
    if ( !v7 )
    {
LABEL_15:
      v9 = 1;
      goto LABEL_16;
    }
  }
  v8 = (__int64 *)g_leDialInAdapterList;
  v9 = 0;
  while ( v8 != &g_leDialInAdapterList )
  {
    v3 = v8 - 4;
    v10 = v8[15] - *a1;
    if ( !v10 )
      v10 = v3[20] - a1[1];
    if ( !v10 )
      goto LABEL_15;
    v8 = (__int64 *)*v8;
  }
LABEL_16:
  if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
    KeReleaseSpinLock(&SpinLock, v5);
  else
    KeLowerIrql(v5);
  if ( v9 )
    *a2 = v3;
  return v9;
}

```

## disassembly

```asm
0x14000d090  push    rbx
0x14000d092  push    rbp
0x14000d093  push    rsi
0x14000d094  push    rdi
0x14000d095  push    r14
0x14000d097  sub     rsp, 20h
0x14000d09b  mov     rsi, rcx
0x14000d09e  xor     edi, edi
0x14000d0a0  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000d0a7  mov     [rdx], rdi
0x14000d0aa  mov     r14, rdx
0x14000d0ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d0b4  nop     dword ptr [rax+rax+00h]
0x14000d0b9  mov     bpl, al
0x14000d0bc  lea     r8d, [rdi+1]
0x14000d0c0  lock xadd cs:dword_140009CB0, r8d
0x14000d0c9  inc     r8d
0x14000d0cc  cmp     r8d, 1
0x14000d0d0  jnz     short loc_14000D0E5
0x14000d0d2  lea     rcx, SpinLock; SpinLock
0x14000d0d9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d0e0  nop     dword ptr [rax+rax+00h]
0x14000d0e5  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000d0ec  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d0f3  nop     dword ptr [rax+rax+00h]
0x14000d0f8  mov     rcx, cs:g_leMappedAdapterList
0x14000d0ff  lea     rax, g_leMappedAdapterList
0x14000d106  cmp     rcx, rax
0x14000d109  jz      short loc_14000D12F
0x14000d10b  mov     rdx, [rcx+98h]
0x14000d112  mov     rdi, rcx
0x14000d115  sub     rdx, [rsi]
0x14000d118  jnz     short loc_14000D125
0x14000d11a  mov     rdx, [rcx+0A0h]
0x14000d121  sub     rdx, [rsi+8]
0x14000d125  test    rdx, rdx
0x14000d128  jz      short loc_14000D169
0x14000d12a  mov     rcx, [rcx]
0x14000d12d  jmp     short loc_14000D0FF
0x14000d12f  mov     rcx, cs:g_leDialInAdapterList
0x14000d136  xor     bl, bl
0x14000d138  lea     rax, g_leDialInAdapterList
0x14000d13f  cmp     rcx, rax
0x14000d142  jz      short loc_14000D16B
0x14000d144  lea     rdi, [rcx-20h]
0x14000d148  mov     rdx, [rdi+98h]
0x14000d14f  sub     rdx, [rsi]
0x14000d152  jnz     short loc_14000D15F
0x14000d154  mov     rdx, [rdi+0A0h]
0x14000d15b  sub     rdx, [rsi+8]
0x14000d15f  test    rdx, rdx
0x14000d162  jz      short loc_14000D169
0x14000d164  mov     rcx, [rcx]
0x14000d167  jmp     short loc_14000D138
0x14000d169  mov     bl, 1
0x14000d16b  or      eax, 0FFFFFFFFh
0x14000d16e  lock xadd cs:dword_140009CB0, eax
0x14000d176  cmp     eax, 1
0x14000d179  jnz     short loc_14000D193
0x14000d17b  mov     dl, bpl; NewIrql
0x14000d17e  lea     rcx, SpinLock; SpinLock
0x14000d185  call    cs:__imp_KeReleaseSpinLock
0x14000d18c  nop     dword ptr [rax+rax+00h]
0x14000d191  jmp     short loc_14000D1A2
0x14000d193  mov     cl, bpl; NewIrql
0x14000d196  call    cs:__imp_KeLowerIrql
0x14000d19d  nop     dword ptr [rax+rax+00h]
0x14000d1a2  test    bl, bl
0x14000d1a4  jz      short loc_14000D1A9
0x14000d1a6  mov     [r14], rdi
0x14000d1a9  mov     al, bl
0x14000d1ab  add     rsp, 20h
0x14000d1af  pop     r14
0x14000d1b1  pop     rdi
0x14000d1b2  pop     rsi
0x14000d1b3  pop     rbp
0x14000d1b4  pop     rbx
0x14000d1b5  retn
```
