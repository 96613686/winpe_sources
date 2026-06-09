# WimFSFAcquireRundownAndRemount

- ea: `0x14003c518`
- end: `0x14003c5c1`
- name: `WimFSFAcquireRundownAndRemount`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140027b90`
- `0x14003c280`
- `0x14003c4e0`

## callees

- `0x14003c518`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14003c540`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003c540`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003c593`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003c593`

## pseudocode

```c
bool __fastcall WimFSFAcquireRundownAndRemount(__int64 a1, __int64 a2, __int64 a3)
{
  struct _EX_RUNDOWN_REF *v4; // rcx
  bool result; // al
  __int128 Parameter; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+40h] [rbp-18h]

  v4 = *(struct _EX_RUNDOWN_REF **)(a3 + 96);
  Parameter = 0;
  v9 = 0;
  result = 1;
  if ( !ExAcquireRundownProtection(v4) )
  {
    if ( !*(_QWORD *)(a3 + 64) )
      return 0;
    if ( (*(_DWORD *)(a3 + 40) & 0x16) != 0 )
      return 0;
    *(_QWORD *)&Parameter = a1;
    *((_QWORD *)&Parameter + 1) = a2;
    *(_QWORD *)&v9 = a3;
    DWORD2(v9) = 0;
    if ( KeExpandKernelStackAndCalloutEx((PEXPAND_STACK_CALLOUT)WimFSFRemountWim, &Parameter, 0x6000u, 0, 0) < 0
      || SDWORD2(v9) < 0 )
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c518  mov     rax, rsp
0x14003c51b  mov     [rax+8], rbx
0x14003c51f  mov     [rax+10h], rsi
0x14003c523  push    rdi
0x14003c524  sub     rsp, 50h
0x14003c528  xorps   xmm0, xmm0
0x14003c52b  mov     rsi, rcx
0x14003c52e  mov     rcx, [r8+60h]; RunRef
0x14003c532  mov     rbx, r8
0x14003c535  movups  xmmword ptr [rax-28h], xmm0
0x14003c539  mov     rdi, rdx
0x14003c53c  movups  xmmword ptr [rax-18h], xmm0
0x14003c540  call    cs:__imp_ExAcquireRundownProtection
0x14003c547  nop     dword ptr [rax+rax+00h]
0x14003c54c  test    al, al
0x14003c54e  jnz     short loc_14003C5AE
0x14003c550  cmp     qword ptr [rbx+40h], 0
0x14003c555  jz      short loc_14003C5AA
0x14003c557  mov     eax, [rbx+28h]
0x14003c55a  test    al, 16h
0x14003c55c  jnz     short loc_14003C5AA
0x14003c55e  xor     r9d, r9d; Wait
0x14003c561  mov     [rsp+58h+Parameter], rsi
0x14003c566  mov     r8d, 6000h; Size
0x14003c56c  mov     [rsp+58h+var_20], rdi
0x14003c571  lea     rdx, [rsp+58h+Parameter]; Parameter
0x14003c576  mov     [rsp+58h+var_18], rbx
0x14003c57b  lea     rcx, WimFSFRemountWim; Callout
0x14003c582  mov     [rsp+58h+var_10], 0
0x14003c58a  mov     [rsp+58h+Context], 0; Context
0x14003c593  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14003c59a  nop     dword ptr [rax+rax+00h]
0x14003c59f  test    eax, eax
0x14003c5a1  js      short loc_14003C5AA
0x14003c5a3  cmp     [rsp+58h+var_10], 0
0x14003c5a8  jge     short loc_14003C5AE
0x14003c5aa  xor     al, al
0x14003c5ac  jmp     short loc_14003C5B0
0x14003c5ae  mov     al, 1
0x14003c5b0  mov     rbx, [rsp+58h+arg_0]
0x14003c5b5  mov     rsi, [rsp+58h+arg_8]
0x14003c5ba  add     rsp, 50h
0x14003c5be  pop     rdi
0x14003c5bf  retn
```
