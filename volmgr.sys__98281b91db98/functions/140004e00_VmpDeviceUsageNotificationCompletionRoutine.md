# VmpDeviceUsageNotificationCompletionRoutine

- ea: `0x140004e00`
- end: `0x140004ec4`
- name: `VmpDeviceUsageNotificationCompletionRoutine`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004e00`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e36`
- `ntoskrnl!IoInvalidateDeviceState` at `0x140004e9a`
- `ntoskrnl!IoInvalidateDeviceState` at `0x140004e9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e86`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004eaa`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004eaa`

## pseudocode

```c
__int64 __fastcall VmpDeviceUsageNotificationCompletionRoutine(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  char v5; // bp
  KIRQL v6; // dl
  int v7; // eax
  int v8; // eax

  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(v4 + 3) |= 1u;
  if ( *(int *)(a2 + 48) >= 0 && *(_DWORD *)(v4 + 16) == 1 )
  {
    v5 = 0;
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 24));
    v7 = *(_DWORD *)(v3 + 148);
    if ( *(_BYTE *)(v4 + 8) )
    {
      *(_DWORD *)(v3 + 148) = v7 + 1;
      if ( v7 )
        goto LABEL_11;
      *(_DWORD *)(a1 + 48) &= ~0x2000u;
    }
    else
    {
      v8 = v7 - 1;
      *(_DWORD *)(v3 + 148) = v8;
      if ( v8 )
        goto LABEL_11;
      *(_DWORD *)(a1 + 48) |= 0x2000u;
    }
    v5 = 1;
LABEL_11:
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), v6);
    if ( v5 )
      IoInvalidateDeviceState(*(PDEVICE_OBJECT *)v3);
  }
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v3 + 112));
  return 0;
}

```

## disassembly

```asm
0x140004e00  push    rbx
0x140004e02  push    rbp
0x140004e03  push    rsi
0x140004e04  push    rdi
0x140004e05  push    r14
0x140004e07  sub     rsp, 20h
0x140004e0b  cmp     byte ptr [rdx+41h], 0
0x140004e0f  mov     rsi, rcx
0x140004e12  mov     rbx, [rcx+40h]
0x140004e16  mov     rdi, [rdx+0B8h]
0x140004e1d  jz      short loc_140004E23
0x140004e1f  or      byte ptr [rdi+3], 1
0x140004e23  cmp     dword ptr [rdx+30h], 0
0x140004e27  jl      short loc_140004EA6
0x140004e29  cmp     dword ptr [rdi+10h], 1
0x140004e2d  jnz     short loc_140004EA6
0x140004e2f  lea     rcx, [rbx+18h]; SpinLock
0x140004e33  xor     bpl, bpl
0x140004e36  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004e3d  nop     dword ptr [rax+rax+00h]
0x140004e42  mov     dl, al; NewIrql
0x140004e44  mov     eax, [rbx+94h]
0x140004e4a  cmp     [rdi+8], bpl
0x140004e4e  jz      short loc_140004E6A
0x140004e50  lea     ecx, [rax+1]
0x140004e53  mov     [rbx+94h], ecx
0x140004e59  cmp     ecx, 1
0x140004e5c  jnz     short loc_140004E82
0x140004e5e  mov     ecx, [rsi+30h]
0x140004e61  btr     ecx, 0Dh
0x140004e65  mov     [rsi+30h], ecx
0x140004e68  jmp     short loc_140004E7F
0x140004e6a  sub     eax, 1
0x140004e6d  mov     [rbx+94h], eax
0x140004e73  jnz     short loc_140004E82
0x140004e75  mov     eax, [rsi+30h]
0x140004e78  bts     eax, 0Dh
0x140004e7c  mov     [rsi+30h], eax
0x140004e7f  mov     bpl, 1
0x140004e82  lea     rcx, [rbx+18h]; SpinLock
0x140004e86  call    cs:__imp_KeReleaseSpinLock
0x140004e8d  nop     dword ptr [rax+rax+00h]
0x140004e92  test    bpl, bpl
0x140004e95  jz      short loc_140004EA6
0x140004e97  mov     rcx, [rbx]; PhysicalDeviceObject
0x140004e9a  call    cs:__imp_IoInvalidateDeviceState
0x140004ea1  nop     dword ptr [rax+rax+00h]
0x140004ea6  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140004eaa  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140004eb1  nop     dword ptr [rax+rax+00h]
0x140004eb6  xor     eax, eax
0x140004eb8  add     rsp, 20h
0x140004ebc  pop     r14
0x140004ebe  pop     rdi
0x140004ebf  pop     rsi
0x140004ec0  pop     rbp
0x140004ec1  pop     rbx
0x140004ec2  retn
```
