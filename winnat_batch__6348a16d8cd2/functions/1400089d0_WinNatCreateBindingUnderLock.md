# WinNatCreateBindingUnderLock

- ea: `0x1400089d0`
- end: `0x140008a74`
- name: `WinNatCreateBindingUnderLock`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140004648`

## callees

- `0x1400089d0`
- `0x140008a7c`
- `0x140008df0`
- `0x140009034`
- `0x140011b90`

## pseudocode

```c
__int16 *__fastcall WinNatCreateBindingUnderLock(
        __int64 a1,
        __int64 a2,
        __int16 *a3,
        char a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  __int64 *v7; // rdi
  __int16 *Binding; // rbx
  __int64 v12; // rcx

  v7 = (__int64 *)(a1 + 768);
  Binding = WinNatLibCreateBinding((__int64 *)(a1 + 768), a2, a3, a4, a5, a6);
  if ( !Binding )
    return 0;
  if ( (int)WinNatAllocateBinding((_DWORD)v7, (_DWORD)Binding, a5, a6, 1, a7) < 0 )
  {
    if ( *a3 == 2 )
      v12 = v7[1];
    else
      v12 = *v7;
    PplFreeToLookasideList(v12, Binding);
    return 0;
  }
  WinNatInsertBindingToTable(a1, Binding);
  return Binding;
}

```

## disassembly

```asm
0x1400089d0  push    rbx
0x1400089d2  push    rbp
0x1400089d3  push    rsi
0x1400089d4  push    rdi
0x1400089d5  push    r14
0x1400089d7  push    r15
0x1400089d9  sub     rsp, 38h
0x1400089dd  mov     r14d, [rsp+68h+arg_28]
0x1400089e5  lea     rdi, [rcx+300h]
0x1400089ec  mov     r15, [rsp+68h+arg_20]
0x1400089f4  mov     rbp, rcx
0x1400089f7  mov     rcx, rdi
0x1400089fa  mov     dword ptr [rsp+68h+var_40], r14d
0x1400089ff  mov     rsi, r8
0x140008a02  mov     [rsp+68h+var_48], r15
0x140008a07  call    WinNatLibCreateBinding
0x140008a0c  mov     rbx, rax
0x140008a0f  test    rax, rax
0x140008a12  jnz     short loc_140008A18
0x140008a14  xor     eax, eax
0x140008a16  jmp     short loc_140008A66
0x140008a18  mov     rax, [rsp+68h+arg_30]
0x140008a20  mov     r9d, r14d
0x140008a23  mov     [rsp+68h+var_40], rax
0x140008a28  mov     r8, r15
0x140008a2b  mov     rdx, rbx
0x140008a2e  mov     byte ptr [rsp+68h+var_48], 1
0x140008a33  mov     rcx, rdi
0x140008a36  call    WinNatAllocateBinding
0x140008a3b  test    eax, eax
0x140008a3d  jns     short loc_140008A58
0x140008a3f  cmp     word ptr [rsi], 2
0x140008a43  jnz     short loc_140008A4B
0x140008a45  mov     rcx, [rdi+8]
0x140008a49  jmp     short loc_140008A4E
0x140008a4b  mov     rcx, [rdi]
0x140008a4e  mov     rdx, rbx
0x140008a51  call    PplFreeToLookasideList
0x140008a56  jmp     short loc_140008A14
0x140008a58  mov     rdx, rbx
0x140008a5b  mov     rcx, rbp
0x140008a5e  call    WinNatInsertBindingToTable
0x140008a63  mov     rax, rbx
0x140008a66  add     rsp, 38h
0x140008a6a  pop     r15
0x140008a6c  pop     r14
0x140008a6e  pop     rdi
0x140008a6f  pop     rsi
0x140008a70  pop     rbp
0x140008a71  pop     rbx
0x140008a72  retn
```
