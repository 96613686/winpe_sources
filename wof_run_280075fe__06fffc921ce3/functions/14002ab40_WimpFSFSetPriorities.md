# WimpFSFSetPriorities

- ea: `0x14002ab40`
- end: `0x14002abe2`
- name: `WimpFSFSetPriorities`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140028ef4`
- `0x14002aa38`

## callees

- `0x14002ab40`

## import_xrefs

- `ntoskrnl!ZwSetInformationThread` at `0x14002ab8f`
- `ntoskrnl!ZwSetInformationThread` at `0x14002abc1`
- `ntoskrnl!ZwSetInformationThread` at `0x14002ab8f`
- `ntoskrnl!ZwSetInformationThread` at `0x14002abc1`
- `ntoskrnl!KeSetPriorityThread` at `0x14002ab69`
- `ntoskrnl!KeSetPriorityThread` at `0x14002ab69`

## pseudocode

```c
__int64 __fastcall WimpFSFSetPriorities(_DWORD *a1, char a2)
{
  NTSTATUS v2; // edi

  v2 = 0;
  if ( (*a1 & 4) != 0 )
    KeSetPriorityThread(KeGetCurrentThread(), a1[3]);
  if ( (*a1 & 2) == 0
    || (v2 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, a1 + 2, 4u), v2 >= 0)
    || a2 )
  {
    if ( (*a1 & 1) != 0 )
      return (unsigned int)ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, a1 + 1, 4u);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002ab40  mov     [rsp+arg_0], rbx
0x14002ab45  mov     [rsp+arg_8], rsi
0x14002ab4a  push    rdi
0x14002ab4b  sub     rsp, 20h
0x14002ab4f  mov     eax, [rcx]
0x14002ab51  xor     edi, edi
0x14002ab53  mov     sil, dl
0x14002ab56  mov     rbx, rcx
0x14002ab59  test    al, 4
0x14002ab5b  jz      short loc_14002AB75
0x14002ab5d  mov     rcx, gs:188h; Thread
0x14002ab66  mov     edx, [rbx+0Ch]; Priority
0x14002ab69  call    cs:__imp_KeSetPriorityThread
0x14002ab70  nop     dword ptr [rax+rax+00h]
0x14002ab75  mov     eax, [rbx]
0x14002ab77  test    al, 2
0x14002ab79  jz      short loc_14002ABA6
0x14002ab7b  mov     edx, 18h; ThreadInformationClass
0x14002ab80  lea     r8, [rbx+8]; ThreadInformation
0x14002ab84  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002ab8b  lea     r9d, [rdx-14h]; ThreadInformationLength
0x14002ab8f  call    cs:__imp_ZwSetInformationThread
0x14002ab96  nop     dword ptr [rax+rax+00h]
0x14002ab9b  mov     edi, eax
0x14002ab9d  test    eax, eax
0x14002ab9f  jns     short loc_14002ABA6
0x14002aba1  test    sil, sil
0x14002aba4  jz      short loc_14002ABCF
0x14002aba6  mov     edx, [rbx]
0x14002aba8  test    dl, 1
0x14002abab  jz      short loc_14002ABCF
0x14002abad  mov     edx, 16h; ThreadInformationClass
0x14002abb2  lea     r8, [rbx+4]; ThreadInformation
0x14002abb6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002abbd  lea     r9d, [rdx-12h]; ThreadInformationLength
0x14002abc1  call    cs:__imp_ZwSetInformationThread
0x14002abc8  nop     dword ptr [rax+rax+00h]
0x14002abcd  mov     edi, eax
0x14002abcf  mov     rbx, [rsp+28h+arg_0]
0x14002abd4  mov     eax, edi
0x14002abd6  mov     rsi, [rsp+28h+arg_8]
0x14002abdb  add     rsp, 20h
0x14002abdf  pop     rdi
0x14002abe0  retn
```
