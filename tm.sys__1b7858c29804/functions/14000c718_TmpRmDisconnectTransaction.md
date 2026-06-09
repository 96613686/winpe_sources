# TmpRmDisconnectTransaction

- ea: `0x14000c718`
- end: `0x14000c7df`
- name: `TmpRmDisconnectTransaction`
- size: `199`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c4a0`
- `0x14001e7c0`
- `0x140020b50`

## callees

- `0x14000c718`
- `0x14001aa8c`
- `0x14001b338`
- `0x140020250`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000c7c0`
- `ntoskrnl!KeReleaseMutex` at `0x140021b29`
- `ntoskrnl!KeReleaseMutex` at `0x14000c7c0`
- `ntoskrnl!KeReleaseMutex` at `0x140021b29`

## pseudocode

```c
__int64 __fastcall TmpRmDisconnectTransaction(_QWORD *Object)
{
  __int64 v2; // rbx
  char v3; // si

  v2 = Object[20];
  v3 = 0;
  TmpAcquireTransactionMutex(v2);
  if ( (*((_DWORD *)Object + 43) & 1) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v2 + 196), 0x80u);
    v3 = 1;
  }
  if ( (*((_DWORD *)Object + 43) & 1) != 0 && (unsigned int)(*(_DWORD *)(v2 + 192) - 3) <= 1 )
  {
    *(_DWORD *)(v2 + 192) = 4;
  }
  else if ( *((_DWORD *)Object + 42) == 264 )
  {
    TmpDelegateDisconnect(Object);
  }
  else
  {
    TmRollbackEnlistmentExt((PKENLISTMENT)Object, 0);
  }
  if ( v3 )
    _InterlockedAnd((volatile signed __int32 *)(v2 + 196), 0xFFFFFF7F);
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v2 + 88) + 32LL), 0);
  return 0;
}

```

## disassembly

```asm
0x14000c718  mov     [rsp+arg_8], rbx
0x14000c71d  mov     [rsp+arg_10], rsi
0x14000c722  push    rdi
0x14000c723  sub     rsp, 30h
0x14000c727  mov     rdi, rcx
0x14000c72a  mov     rbx, [rcx+0A0h]
0x14000c731  mov     [rsp+38h+arg_0], rbx
0x14000c736  xor     sil, sil
0x14000c739  mov     [rsp+38h+var_18], sil
0x14000c73e  mov     rcx, rbx
0x14000c741  call    TmpAcquireTransactionMutex
0x14000c746  nop
0x14000c747  mov     eax, [rdi+0ACh]
0x14000c74d  test    al, 1
0x14000c74f  jz      short loc_14000C764
0x14000c751  lock or dword ptr [rbx+0C4h], 80h
0x14000c75c  mov     sil, 1
0x14000c75f  mov     [rsp+38h+var_18], sil
0x14000c764  mov     eax, [rdi+0ACh]
0x14000c76a  test    al, 1
0x14000c76c  jz      short loc_14000C788
0x14000c76e  mov     eax, [rbx+0C0h]
0x14000c774  sub     eax, 3
0x14000c777  cmp     eax, 1
0x14000c77a  ja      short loc_14000C788
0x14000c77c  mov     dword ptr [rbx+0C0h], 4
0x14000c786  jmp     short loc_14000C7A6
0x14000c788  mov     rcx, rdi; Object
0x14000c78b  cmp     dword ptr [rdi+0A8h], 108h
0x14000c795  jnz     short loc_14000C79E
0x14000c797  call    TmpDelegateDisconnect
0x14000c79c  jmp     short loc_14000C7A6
0x14000c79e  xor     edx, edx; TmVirtualClock
0x14000c7a0  call    TmRollbackEnlistmentExt
0x14000c7a5  nop
0x14000c7a6  test    sil, sil
0x14000c7a9  jz      short loc_14000C7B6
0x14000c7ab  lock and dword ptr [rbx+0C4h], 0FFFFFF7Fh
0x14000c7b6  mov     rcx, [rbx+58h]
0x14000c7ba  add     rcx, 20h ; ' '; Mutex
0x14000c7be  xor     edx, edx; Wait
0x14000c7c0  call    cs:__imp_KeReleaseMutex
0x14000c7c7  nop     dword ptr [rax+rax+00h]
0x14000c7cc  xor     eax, eax
0x14000c7ce  mov     rbx, [rsp+38h+arg_8]
0x14000c7d3  mov     rsi, [rsp+38h+arg_10]
0x14000c7d8  add     rsp, 30h
0x14000c7dc  pop     rdi
0x14000c7dd  retn
0x140021afd  push    rbp
0x140021aff  sub     rsp, 20h
0x140021b03  mov     rbp, rdx
0x140021b06  cmp     byte ptr [rbp+20h], 0
0x140021b0a  jz      short loc_140021B1B
0x140021b0c  mov     rax, [rbp+40h]
0x140021b10  lock and dword ptr [rax+0C4h], 0FFFFFF7Fh
0x140021b1b  mov     rax, [rbp+40h]
0x140021b1f  mov     rcx, [rax+58h]
0x140021b23  add     rcx, 20h ; ' '; Mutex
0x140021b27  xor     edx, edx; Wait
0x140021b29  call    cs:__imp_KeReleaseMutex
0x140021b30  nop     dword ptr [rax+rax+00h]
0x140021b35  nop
0x140021b36  add     rsp, 20h
0x140021b3a  pop     rbp
0x140021b3b  retn
```
