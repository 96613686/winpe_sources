# WerpCheckSpaceAvailable

- ea: `0x14000d558`
- end: `0x14000d686`
- name: `WerpCheckSpaceAvailable`
- size: `302`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e83c`

## callees

- `0x14000d174`
- `0x14000d558`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d5b0`
- `ntoskrnl!DbgPrintEx` at `0x14000d5df`
- `ntoskrnl!DbgPrintEx` at `0x14000d62c`
- `ntoskrnl!DbgPrintEx` at `0x14000d64f`
- `ntoskrnl!DbgPrintEx` at `0x14000d5b0`
- `ntoskrnl!DbgPrintEx` at `0x14000d5df`
- `ntoskrnl!DbgPrintEx` at `0x14000d62c`
- `ntoskrnl!DbgPrintEx` at `0x14000d64f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d667`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d667`
- `ntoskrnl!ZwQueryKey` at `0x14000d586`
- `ntoskrnl!ZwQueryKey` at `0x14000d60a`
- `ntoskrnl!ZwQueryKey` at `0x14000d586`
- `ntoskrnl!ZwQueryKey` at `0x14000d60a`

## pseudocode

```c
__int64 __fastcall WerpCheckSpaceAvailable(HANDLE KeyHandle)
{
  unsigned int v1; // edi
  NTSTATUS v3; // eax
  __int64 v4; // rdx
  _DWORD *Mem; // rbx
  NTSTATUS v6; // eax
  ULONG Length; // [rsp+48h] [rbp+10h] BYREF

  Length = 0;
  v1 = 0;
  v3 = ZwQueryKey(KeyHandle, KeyFullInformation, 0, 0, &Length);
  if ( v3 == -2147483643 || v3 == -1073741789 )
  {
    Mem = (_DWORD *)WerpAllocateMem(Length, v4);
    if ( Mem )
    {
      v6 = ZwQueryKey(KeyHandle, KeyFullInformation, Mem, Length, &Length);
      if ( v6 >= 0 )
      {
        if ( Mem[5] < 0xAu )
          v1 = 1;
        else
          DbgPrintEx(5u, 1u, "WERKERNELHOST: Live kernel queue size exceeded\n");
      }
      else
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwQueryKey failed with 0x%x\n", v6);
      }
      ExFreePoolWithTag(Mem, 0);
    }
    else
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Out of memory.\n");
    }
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwQueryKey failed while determining the size with 0x%x\n", v3);
  }
  return v1;
}

```

## disassembly

```asm
0x14000d558  mov     rax, rsp
0x14000d55b  mov     [rax+8], rbx
0x14000d55f  mov     [rax+18h], rsi
0x14000d563  push    rdi
0x14000d564  sub     rsp, 30h
0x14000d568  mov     dword ptr [rax+10h], 0
0x14000d56f  lea     rax, [rax+10h]
0x14000d573  xor     edi, edi
0x14000d575  mov     [rsp+38h+ResultLength], rax; ResultLength
0x14000d57a  xor     r9d, r9d; Length
0x14000d57d  xor     r8d, r8d; KeyInformation
0x14000d580  mov     rsi, rcx
0x14000d583  lea     edx, [rdi+2]; KeyInformationClass
0x14000d586  call    cs:__imp_ZwQueryKey
0x14000d58d  nop     dword ptr [rax+rax+00h]
0x14000d592  cmp     eax, 80000005h
0x14000d597  jz      short loc_14000D5C1
0x14000d599  cmp     eax, 0C0000023h
0x14000d59e  jz      short loc_14000D5C1
0x14000d5a0  mov     r9d, eax
0x14000d5a3  lea     r8, aWerkernelhostZ_8; "WERKERNELHOST: ZwQueryKey failed while "...
0x14000d5aa  lea     edx, [rdi+1]; Level
0x14000d5ad  lea     ecx, [rdi+5]; ComponentId
0x14000d5b0  call    cs:__imp_DbgPrintEx
0x14000d5b7  nop     dword ptr [rax+rax+00h]
0x14000d5bc  jmp     loc_14000D673
0x14000d5c1  mov     ecx, [rsp+38h+Length]
0x14000d5c5  call    WerpAllocateMem
0x14000d5ca  mov     rbx, rax
0x14000d5cd  test    rax, rax
0x14000d5d0  jnz     short loc_14000D5F0
0x14000d5d2  lea     r8, aWerkernelhostO_1; "WERKERNELHOST: Out of memory.\n"
0x14000d5d9  lea     edx, [rax+1]; Level
0x14000d5dc  lea     ecx, [rax+5]; ComponentId
0x14000d5df  call    cs:__imp_DbgPrintEx
0x14000d5e6  nop     dword ptr [rax+rax+00h]
0x14000d5eb  jmp     loc_14000D673
0x14000d5f0  mov     r9d, [rsp+38h+Length]; Length
0x14000d5f5  lea     rax, [rsp+38h+Length]
0x14000d5fa  mov     r8, rbx; KeyInformation
0x14000d5fd  mov     [rsp+38h+ResultLength], rax; ResultLength
0x14000d602  mov     edx, 2; KeyInformationClass
0x14000d607  mov     rcx, rsi; KeyHandle
0x14000d60a  call    cs:__imp_ZwQueryKey
0x14000d611  nop     dword ptr [rax+rax+00h]
0x14000d616  test    eax, eax
0x14000d618  jns     short loc_14000D63A
0x14000d61a  mov     edx, 1; Level
0x14000d61f  lea     r8, aWerkernelhostZ_2; "WERKERNELHOST: ZwQueryKey failed with 0"...
0x14000d626  mov     r9d, eax
0x14000d629  lea     ecx, [rdx+4]; ComponentId
0x14000d62c  call    cs:__imp_DbgPrintEx
0x14000d633  nop     dword ptr [rax+rax+00h]
0x14000d638  jmp     short loc_14000D662
0x14000d63a  cmp     dword ptr [rbx+14h], 0Ah
0x14000d63e  jb      short loc_14000D65D
0x14000d640  mov     edx, 1; Level
0x14000d645  lea     r8, aWerkernelhostL; "WERKERNELHOST: Live kernel queue size e"...
0x14000d64c  lea     ecx, [rdx+4]; ComponentId
0x14000d64f  call    cs:__imp_DbgPrintEx
0x14000d656  nop     dword ptr [rax+rax+00h]
0x14000d65b  jmp     short loc_14000D662
0x14000d65d  mov     edi, 1
0x14000d662  xor     edx, edx; Tag
0x14000d664  mov     rcx, rbx; P
0x14000d667  call    cs:__imp_ExFreePoolWithTag
0x14000d66e  nop     dword ptr [rax+rax+00h]
0x14000d673  mov     rbx, [rsp+38h+arg_0]
0x14000d678  mov     eax, edi
0x14000d67a  mov     rsi, [rsp+38h+arg_10]
0x14000d67f  add     rsp, 30h
0x14000d683  pop     rdi
0x14000d684  retn
```
