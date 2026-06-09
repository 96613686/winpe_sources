# VidExoBrokerpQueueSendIrp

- ea: `0x140023ee8`
- end: `0x140023faa`
- name: `VidExoBrokerpQueueSendIrp`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140077d7c`
- `0x140083ebc`

## callees

- `0x140023ee8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140023f8d`
- `ntoskrnl!IofCompleteRequest` at `0x140023f8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023f70`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023f70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023f0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023f0b`

## pseudocode

```c
void __fastcall VidExoBrokerpQueueSendIrp(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // r9
  char v6; // di
  __int64 v7; // rcx
  _QWORD *v8; // rdx

  v2 = (KSPIN_LOCK *)(a1 + 12064);
  *(_QWORD *)(a2 + 120) = a1;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 12064));
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&VidExoBrokerpIrpCancelRoutine);
  if ( *(_BYTE *)(a2 + 68) && _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    v6 = 1;
  }
  else
  {
    v7 = a1 + 12072;
    v8 = *(_QWORD **)(a1 + 12080);
    if ( *v8 != a1 + 12072 )
      __fastfail(3u);
    v6 = 0;
    *(_QWORD *)(a2 + 168) = v7;
    *(_QWORD *)(a2 + 176) = v8;
    *v8 = a2 + 168;
    *(_QWORD *)(v7 + 8) = a2 + 168;
  }
  KeReleaseSpinLock(v2, v5);
  if ( v6 )
  {
    *(_DWORD *)(a2 + 48) = -1073741536;
    IofCompleteRequest((PIRP)a2, 0);
  }
}

```

## disassembly

```asm
0x140023ee8  mov     [rsp+arg_0], rbx
0x140023eed  mov     [rsp+arg_8], rsi
0x140023ef2  push    rdi
0x140023ef3  sub     rsp, 20h
0x140023ef7  lea     rsi, [rcx+2F20h]
0x140023efe  mov     [rdx+78h], rcx
0x140023f02  mov     rdi, rcx
0x140023f05  mov     rbx, rdx
0x140023f08  mov     rcx, rsi; SpinLock
0x140023f0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140023f12  nop     dword ptr [rax+rax+00h]
0x140023f17  lea     r8, VidExoBrokerpIrpCancelRoutine
0x140023f1e  mov     r9b, al
0x140023f21  xchg    r8, [rbx+68h]
0x140023f25  cmp     byte ptr [rbx+44h], 0
0x140023f29  jz      short loc_140023F3B
0x140023f2b  xor     ecx, ecx
0x140023f2d  xchg    rcx, [rbx+68h]
0x140023f31  test    rcx, rcx
0x140023f34  jz      short loc_140023F3B
0x140023f36  mov     dil, 1
0x140023f39  jmp     short loc_140023F6A
0x140023f3b  lea     rcx, [rdi+2F28h]
0x140023f42  mov     rdx, [rcx+8]
0x140023f46  cmp     [rdx], rcx
0x140023f49  jz      short loc_140023F52
0x140023f4b  mov     ecx, 3
0x140023f50  int     29h; Win8: RtlFailFast(ecx)
0x140023f52  lea     rax, [rbx+0A8h]
0x140023f59  xor     dil, dil
0x140023f5c  mov     [rax], rcx
0x140023f5f  mov     [rax+8], rdx
0x140023f63  mov     [rdx], rax
0x140023f66  mov     [rcx+8], rax
0x140023f6a  mov     dl, r9b; NewIrql
0x140023f6d  mov     rcx, rsi; SpinLock
0x140023f70  call    cs:__imp_KeReleaseSpinLock
0x140023f77  nop     dword ptr [rax+rax+00h]
0x140023f7c  test    dil, dil
0x140023f7f  jz      short loc_140023F99
0x140023f81  xor     edx, edx; PriorityBoost
0x140023f83  mov     dword ptr [rbx+30h], 0C0000120h
0x140023f8a  mov     rcx, rbx; Irp
0x140023f8d  call    cs:__imp_IofCompleteRequest
0x140023f94  nop     dword ptr [rax+rax+00h]
0x140023f99  mov     rbx, [rsp+28h+arg_0]
0x140023f9e  mov     rsi, [rsp+28h+arg_8]
0x140023fa3  add     rsp, 20h
0x140023fa7  pop     rdi
0x140023fa8  retn
```
