# WinHvDeletePartitionRemote

- ea: `0x140021c40`
- end: `0x140021cfa`
- name: `WinHvDeletePartitionRemote`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140021a10`

## callees

- `0x14000786c`
- `0x1400078dc`
- `0x140021c40`
- `0x1400223e0`
- `0x1400225c0`
- `0x1400231a4`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140021c5d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021c5d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021ce0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021ce0`

## pseudocode

```c
__int64 __fastcall WinHvDeletePartitionRemote(__int64 a1)
{
  int v2; // edi
  int v3; // r9d
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  if ( ExAcquireRundownProtection(&RunRef) )
  {
    v2 = WinHvpLookupRemotePartitionByLocalId(a1, &v5, 0);
    if ( v2 >= 0 )
    {
      WinHvpFinalizePartitionRemote(v5);
      LOBYTE(v3) = 1;
      v6 = 0;
      WinHvpWithdrawMemory(v5, -1, 0x80000000, v3, (__int64)&v6, 0);
      WinHvpDeletePartitionRemote(v5);
      WinHvpRemoveRemotePartitionId(a1);
    }
    ExReleaseRundownProtection(&RunRef);
  }
  else
  {
    return (unsigned int)-1070268408;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140021c40  mov     [rsp+arg_0], rsi
0x140021c45  push    rdi
0x140021c46  sub     rsp, 30h
0x140021c4a  mov     rsi, rcx
0x140021c4d  mov     [rsp+38h+arg_8], 0
0x140021c56  lea     rcx, RunRef; RunRef
0x140021c5d  call    cs:__imp_ExAcquireRundownProtection
0x140021c64  nop     dword ptr [rax+rax+00h]
0x140021c69  test    al, al
0x140021c6b  jnz     short loc_140021C74
0x140021c6d  mov     edi, 0C0350008h
0x140021c72  jmp     short loc_140021CEC
0x140021c74  xor     r8d, r8d
0x140021c77  lea     rdx, [rsp+38h+arg_8]
0x140021c7c  mov     rcx, rsi
0x140021c7f  call    WinHvpLookupRemotePartitionByLocalId
0x140021c84  mov     edi, eax
0x140021c86  test    eax, eax
0x140021c88  js      short loc_140021CD9
0x140021c8a  mov     rcx, [rsp+38h+arg_8]
0x140021c8f  call    WinHvpFinalizePartitionRemote
0x140021c94  mov     rcx, [rsp+38h+arg_8]
0x140021c99  lea     rax, [rsp+38h+arg_10]
0x140021c9e  mov     [rsp+38h+var_10], 0
0x140021ca7  mov     r9b, 1
0x140021caa  mov     r8d, 80000000h
0x140021cb0  mov     [rsp+38h+var_18], rax
0x140021cb5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140021cb9  mov     [rsp+38h+arg_10], 0
0x140021cc2  call    WinHvpWithdrawMemory
0x140021cc7  mov     rcx, [rsp+38h+arg_8]
0x140021ccc  call    WinHvpDeletePartitionRemote
0x140021cd1  mov     rcx, rsi
0x140021cd4  call    WinHvpRemoveRemotePartitionId
0x140021cd9  lea     rcx, RunRef; RunRef
0x140021ce0  call    cs:__imp_ExReleaseRundownProtection
0x140021ce7  nop     dword ptr [rax+rax+00h]
0x140021cec  mov     rsi, [rsp+38h+arg_0]
0x140021cf1  mov     eax, edi
0x140021cf3  add     rsp, 30h
0x140021cf7  pop     rdi
0x140021cf8  retn
```
