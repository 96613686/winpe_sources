# WimFSFAcquireRundownAndRemount

- ea: `0x14003c4c8`
- end: `0x14003c571`
- name: `WimFSFAcquireRundownAndRemount`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140027b40`
- `0x14003c230`
- `0x14003c490`

## callees

- `0x14003c4c8`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14003c4f0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003c4f0`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003c543`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003c543`

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
0x14003c4c8  mov     rax, rsp
0x14003c4cb  mov     [rax+8], rbx
0x14003c4cf  mov     [rax+10h], rsi
0x14003c4d3  push    rdi
0x14003c4d4  sub     rsp, 50h
0x14003c4d8  xorps   xmm0, xmm0
0x14003c4db  mov     rsi, rcx
0x14003c4de  mov     rcx, [r8+60h]; RunRef
0x14003c4e2  mov     rbx, r8
0x14003c4e5  movups  xmmword ptr [rax-28h], xmm0
0x14003c4e9  mov     rdi, rdx
0x14003c4ec  movups  xmmword ptr [rax-18h], xmm0
0x14003c4f0  call    cs:__imp_ExAcquireRundownProtection
0x14003c4f7  nop     dword ptr [rax+rax+00h]
0x14003c4fc  test    al, al
0x14003c4fe  jnz     short loc_14003C55E
0x14003c500  cmp     qword ptr [rbx+40h], 0
0x14003c505  jz      short loc_14003C55A
0x14003c507  mov     eax, [rbx+28h]
0x14003c50a  test    al, 16h
0x14003c50c  jnz     short loc_14003C55A
0x14003c50e  xor     r9d, r9d; Wait
0x14003c511  mov     [rsp+58h+Parameter], rsi
0x14003c516  mov     r8d, 6000h; Size
0x14003c51c  mov     [rsp+58h+var_20], rdi
0x14003c521  lea     rdx, [rsp+58h+Parameter]; Parameter
0x14003c526  mov     [rsp+58h+var_18], rbx
0x14003c52b  lea     rcx, WimFSFRemountWim; Callout
0x14003c532  mov     [rsp+58h+var_10], 0
0x14003c53a  mov     [rsp+58h+Context], 0; Context
0x14003c543  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14003c54a  nop     dword ptr [rax+rax+00h]
0x14003c54f  test    eax, eax
0x14003c551  js      short loc_14003C55A
0x14003c553  cmp     [rsp+58h+var_10], 0
0x14003c558  jge     short loc_14003C55E
0x14003c55a  xor     al, al
0x14003c55c  jmp     short loc_14003C560
0x14003c55e  mov     al, 1
0x14003c560  mov     rbx, [rsp+58h+arg_0]
0x14003c565  mov     rsi, [rsp+58h+arg_8]
0x14003c56a  add     rsp, 50h
0x14003c56e  pop     rdi
0x14003c56f  retn
```
