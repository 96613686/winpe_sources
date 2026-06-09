# TdxDeleteTransportAddress

- ea: `0x1400042e0`
- end: `0x1400043a2`
- name: `TdxDeleteTransportAddress`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400034f0`

## callees

- `0x1400036b0`
- `0x140003c9c`
- `0x1400042e0`
- `0x1400054ec`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400042f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400042f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004321`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004373`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004321`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004373`

## pseudocode

```c
__int64 __fastcall TdxDeleteTransportAddress(__int64 a1, __int64 a2)
{
  KIRQL v4; // dl
  __int64 v5; // rbp

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  if ( (*(_DWORD *)a1 & 1) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v4);
    return 3221225558LL;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 40);
    *(_DWORD *)a1 |= 1u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v4);
    if ( a2 )
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_QWORD *)(a1 + 48) = a2;
    TdxDeactivateTransportAddress((int *)a1);
    if ( v5 )
      TdxDetachObjectFromTransport(v5, a1);
    DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 1407);
    return 259;
  }
}

```

## disassembly

```asm
0x1400042e0  mov     [rsp+arg_8], rbx
0x1400042e5  mov     [rsp+arg_10], rsi
0x1400042ea  push    rdi
0x1400042eb  sub     rsp, 20h
0x1400042ef  mov     rbx, rcx
0x1400042f2  mov     rsi, rdx
0x1400042f5  add     rcx, 8; SpinLock
0x1400042f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004300  nop     dword ptr [rax+rax+00h]
0x140004305  mov     ecx, [rbx]
0x140004307  movzx   edx, al; NewIrql
0x14000430a  test    cl, 1
0x14000430d  jnz     short loc_14000436F
0x14000430f  or      ecx, 1
0x140004312  mov     [rsp+28h+arg_0], rbp
0x140004317  mov     rbp, [rbx+28h]
0x14000431b  mov     [rbx], ecx
0x14000431d  lea     rcx, [rbx+8]; SpinLock
0x140004321  call    cs:__imp_KeReleaseSpinLock
0x140004328  nop     dword ptr [rax+rax+00h]
0x14000432d  test    rsi, rsi
0x140004330  jz      short loc_14000433D
0x140004332  mov     rax, [rsi+0B8h]
0x140004339  or      byte ptr [rax+3], 1
0x14000433d  mov     rcx, rbx
0x140004340  mov     [rbx+30h], rsi
0x140004344  call    TdxDeactivateTransportAddress
0x140004349  test    rbp, rbp
0x14000434c  jnz     short loc_140004395
0x14000434e  mov     r8d, 57Fh
0x140004354  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000435b  mov     rcx, rbx
0x14000435e  call    DbgTdxDereferenceTransportAddress
0x140004363  mov     rbp, [rsp+28h+arg_0]
0x140004368  mov     eax, 103h
0x14000436d  jmp     short loc_140004384
0x14000436f  lea     rcx, [rbx+8]; SpinLock
0x140004373  call    cs:__imp_KeReleaseSpinLock
0x14000437a  nop     dword ptr [rax+rax+00h]
0x14000437f  mov     eax, 0C0000056h
0x140004384  mov     rbx, [rsp+28h+arg_8]
0x140004389  mov     rsi, [rsp+28h+arg_10]
0x14000438e  add     rsp, 20h
0x140004392  pop     rdi
0x140004393  retn
0x140004395  mov     rdx, rbx
0x140004398  mov     rcx, rbp
0x14000439b  call    TdxDetachObjectFromTransport
0x1400043a0  jmp     short loc_14000434E
```
