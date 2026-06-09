# TdxDeleteControlChannel

- ea: `0x140010b90`
- end: `0x140010c24`
- name: `TdxDeleteControlChannel`
- size: `148`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fbf0`

## callees

- `0x1400036b0`
- `0x14000a908`
- `0x140010b90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ba9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ba9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c04`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c04`

## pseudocode

```c
__int64 __fastcall TdxDeleteControlChannel(KSPIN_LOCK *P)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // dl
  KSPIN_LOCK v4; // rsi

  v1 = P + 1;
  v3 = KeAcquireSpinLockRaiseToDpc(P + 1);
  if ( (*(_DWORD *)P & 1) != 0 )
  {
    KeReleaseSpinLock(v1, v3);
    return 3221225558LL;
  }
  else
  {
    v4 = P[5];
    *(_DWORD *)P |= 1u;
    KeReleaseSpinLock(v1, v3);
    P[6] = 0;
    if ( v4 )
      TdxDetachObjectFromTransport(v4, P);
    TdxDereferenceControlChannel(P);
    return 259;
  }
}

```

## disassembly

```asm
0x140010b90  mov     [rsp+arg_0], rbx
0x140010b95  mov     [rsp+arg_8], rsi
0x140010b9a  push    rdi
0x140010b9b  sub     rsp, 20h
0x140010b9f  lea     rdi, [rcx+8]
0x140010ba3  mov     rbx, rcx
0x140010ba6  mov     rcx, rdi; SpinLock
0x140010ba9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010bb0  nop     dword ptr [rax+rax+00h]
0x140010bb5  mov     ecx, [rbx]
0x140010bb7  mov     dl, al; NewIrql
0x140010bb9  test    cl, 1
0x140010bbc  jnz     short loc_140010C01
0x140010bbe  mov     rsi, [rbx+28h]
0x140010bc2  or      ecx, 1
0x140010bc5  mov     [rbx], ecx
0x140010bc7  mov     rcx, rdi; SpinLock
0x140010bca  call    cs:__imp_KeReleaseSpinLock
0x140010bd1  nop     dword ptr [rax+rax+00h]
0x140010bd6  mov     qword ptr [rbx+30h], 0
0x140010bde  test    rsi, rsi
0x140010be1  jnz     short loc_140010C17
0x140010be3  mov     rcx, rbx; P
0x140010be6  call    TdxDereferenceControlChannel
0x140010beb  mov     eax, 103h
0x140010bf0  mov     rbx, [rsp+28h+arg_0]
0x140010bf5  mov     rsi, [rsp+28h+arg_8]
0x140010bfa  add     rsp, 20h
0x140010bfe  pop     rdi
0x140010bff  retn
0x140010c01  mov     rcx, rdi; SpinLock
0x140010c04  call    cs:__imp_KeReleaseSpinLock
0x140010c0b  nop     dword ptr [rax+rax+00h]
0x140010c10  mov     eax, 0C0000056h
0x140010c15  jmp     short loc_140010BF0
0x140010c17  mov     rdx, rbx
0x140010c1a  mov     rcx, rsi
0x140010c1d  call    TdxDetachObjectFromTransport
0x140010c22  jmp     short loc_140010BE3
```
