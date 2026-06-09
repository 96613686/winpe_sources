# TdxDeleteTransport

- ea: `0x140017cdc`
- end: `0x140017dc5`
- name: `TdxDeleteTransport`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140017530`
- `0x140017590`

## callees

- `0x14000ccfc`
- `0x140017ad0`
- `0x140017cdc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017cf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017d45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017cf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017d45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017d7e`

## pseudocode

```c
__int64 __fastcall TdxDeleteTransport(KSPIN_LOCK *a1, KSPIN_LOCK a2)
{
  KIRQL v4; // al
  __int64 *v5; // r9
  __int64 **v6; // r8
  KIRQL v7; // al
  int v8; // ecx
  int v9; // edi

  v4 = KeAcquireSpinLockRaiseToDpc(&TdxTransportSpinLock);
  v5 = (__int64 *)*a1;
  if ( *(KSPIN_LOCK **)(*a1 + 8) != a1 || (v6 = (__int64 **)a1[1], *v6 != (__int64 *)a1) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = (__int64)v6;
  a1[1] = (KSPIN_LOCK)a1;
  *a1 = (KSPIN_LOCK)a1;
  KeReleaseSpinLock(&TdxTransportSpinLock, v4);
  v7 = KeAcquireSpinLockRaiseToDpc(a1 + 2);
  v8 = *((_DWORD *)a1 + 42);
  if ( (v8 & 1) != 0 )
  {
    v9 = -1073741738;
  }
  else
  {
    a1[19] = a2;
    *((_DWORD *)a1 + 42) = v8 | 1;
    v9 = 259;
  }
  KeReleaseSpinLock(a1 + 2, v7);
  if ( v9 >= 0 )
  {
    TdxDeactivateTransport(a1);
    DbgTdxDereferenceTransport(a1, "minio\\netio\\session\\tdi\\transport.c", 511);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140017cdc  mov     [rsp+arg_0], rbx
0x140017ce1  mov     [rsp+arg_8], rsi
0x140017ce6  push    rdi
0x140017ce7  sub     rsp, 20h
0x140017ceb  mov     rbx, rcx
0x140017cee  mov     rdi, rdx
0x140017cf1  lea     rcx, TdxTransportSpinLock; SpinLock
0x140017cf8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017cff  nop     dword ptr [rax+rax+00h]
0x140017d04  mov     r9, [rbx]
0x140017d07  cmp     [r9+8], rbx
0x140017d0b  jnz     loc_140017DBE
0x140017d11  mov     r8, [rbx+8]
0x140017d15  cmp     [r8], rbx
0x140017d18  jnz     loc_140017DBE
0x140017d1e  mov     [r8], r9
0x140017d21  lea     rcx, TdxTransportSpinLock; SpinLock
0x140017d28  mov     [r9+8], r8
0x140017d2c  mov     dl, al; NewIrql
0x140017d2e  mov     [rbx+8], rbx
0x140017d32  mov     [rbx], rbx
0x140017d35  call    cs:__imp_KeReleaseSpinLock
0x140017d3c  nop     dword ptr [rax+rax+00h]
0x140017d41  lea     rcx, [rbx+10h]; SpinLock
0x140017d45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017d4c  nop     dword ptr [rax+rax+00h]
0x140017d51  mov     ecx, [rbx+0A8h]
0x140017d57  test    cl, 1
0x140017d5a  jz      short loc_140017D63
0x140017d5c  mov     edi, 0C0000056h
0x140017d61  jmp     short loc_140017D78
0x140017d63  or      ecx, 1
0x140017d66  mov     [rbx+98h], rdi
0x140017d6d  mov     [rbx+0A8h], ecx
0x140017d73  mov     edi, 103h
0x140017d78  mov     dl, al; NewIrql
0x140017d7a  lea     rcx, [rbx+10h]; SpinLock
0x140017d7e  call    cs:__imp_KeReleaseSpinLock
0x140017d85  nop     dword ptr [rax+rax+00h]
0x140017d8a  test    edi, edi
0x140017d8c  js      short loc_140017DAB
0x140017d8e  mov     rcx, rbx
0x140017d91  call    TdxDeactivateTransport
0x140017d96  mov     r8d, 1FFh
0x140017d9c  lea     rdx, aMinioNetioSess_4; "minio\\netio\\session\\tdi\\transport.c"
0x140017da3  mov     rcx, rbx
0x140017da6  call    DbgTdxDereferenceTransport
0x140017dab  mov     rbx, [rsp+28h+arg_0]
0x140017db0  mov     eax, edi
0x140017db2  mov     rsi, [rsp+28h+arg_8]
0x140017db7  add     rsp, 20h
0x140017dbb  pop     rdi
0x140017dbc  retn
0x140017dbe  mov     ecx, 3
0x140017dc3  int     29h; Win8: RtlFailFast(ecx)
```
