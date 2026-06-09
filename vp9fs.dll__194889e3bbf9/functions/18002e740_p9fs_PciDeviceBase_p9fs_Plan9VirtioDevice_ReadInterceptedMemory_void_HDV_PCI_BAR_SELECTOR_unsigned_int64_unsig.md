# p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::ReadInterceptedMemory(void *,HDV_PCI_BAR_SELECTOR,unsigned __int64,unsigned __int64,uchar *)

- ea: `0x18002e740`
- end: `0x18002e828`
- name: `?ReadInterceptedMemory@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@SAJPEAXW4HDV_PCI_BAR_SELECTOR@@_K2PEAE@Z`
- size: `232`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004c74`
- `0x180004c80`
- `0x18001c93c`
- `0x18002e740`

## import_xrefs

- `vmvirtio!VirtioReadInterceptedBar` at `0x18002e80d`
- `vmvirtio!VirtioReadInterceptedBar` at `0x18002e80d`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::ReadInterceptedMemory(
        gsl::details *a1,
        int a2,
        unsigned __int64 a3,
        size_t a4,
        char *a5)
{
  unsigned __int64 v7; // rax
  size_t v8; // rdi
  size_t v9; // rax
  size_t v10; // rbx

  if ( a4 == -1 || !a5 && a4 )
    goto LABEL_22;
  if ( (a2 & 0xFFFFFFFD) != 0 )
  {
    if ( a2 != 4 )
      return 2147500037LL;
    if ( a5 || !a4 )
    {
      a1 = (gsl::details *)*((_QWORD *)a1 + 10);
      if ( a1 )
      {
        v7 = *(unsigned __int16 *)a1 + 2LL;
        v8 = 0;
        if ( a3 < v7 )
        {
          v9 = v7 - a3;
          if ( v9 == -1 )
            goto LABEL_22;
          v8 = a4;
          if ( a4 >= v9 )
            v8 = v9;
          if ( a4 < v8 )
            goto LABEL_22;
          if ( v8 )
            memmove_0(a5, (char *)a1 + a3, v8);
        }
        if ( v8 >= a4 )
          return 0;
        v10 = a4 - v8;
        if ( v10 != -1 )
        {
          memset_0(&a5[v8], 0, v10);
          return 0;
        }
      }
    }
LABEL_22:
    gsl::details::terminate(a1);
  }
  return VirtioReadInterceptedBar(*((_QWORD *)a1 + 17));
}

```

## disassembly

```asm
0x18002e740  push    rbx
0x18002e742  push    rsi
0x18002e743  push    rdi
0x18002e744  sub     rsp, 40h
0x18002e748  mov     rbx, r9
0x18002e74b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002e74f  jz      loc_18002E821
0x18002e755  mov     rsi, [rsp+58h+arg_20]
0x18002e75d  test    rsi, rsi
0x18002e760  jnz     short loc_18002E76B
0x18002e762  test    rbx, rbx
0x18002e765  jnz     loc_18002E821
0x18002e76b  test    edx, 0FFFFFFFDh
0x18002e771  jz      loc_18002E801
0x18002e777  cmp     edx, 4
0x18002e77a  jz      short loc_18002E786
0x18002e77c  mov     eax, 80004005h
0x18002e781  jmp     loc_18002E813
0x18002e786  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002e78a  jnb     loc_18002E821
0x18002e790  test    rsi, rsi
0x18002e793  jnz     short loc_18002E79E
0x18002e795  test    rbx, rbx
0x18002e798  jnz     loc_18002E821
0x18002e79e  mov     rcx, [rcx+50h]
0x18002e7a2  test    rcx, rcx
0x18002e7a5  jz      short loc_18002E821
0x18002e7a7  movzx   eax, word ptr [rcx]
0x18002e7aa  add     rax, 2
0x18002e7ae  xor     edi, edi
0x18002e7b0  cmp     r8, rax
0x18002e7b3  jnb     short loc_18002E7E1
0x18002e7b5  sub     rax, r8
0x18002e7b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e7bc  jz      short loc_18002E821
0x18002e7be  mov     rdi, rbx
0x18002e7c1  cmp     rbx, rax
0x18002e7c4  cmovnb  rdi, rax
0x18002e7c8  cmp     rbx, rdi
0x18002e7cb  jb      short loc_18002E821
0x18002e7cd  test    rdi, rdi
0x18002e7d0  jz      short loc_18002E7E1
0x18002e7d2  lea     rdx, [rcx+r8]; Src
0x18002e7d6  mov     r8, rdi; Size
0x18002e7d9  mov     rcx, rsi; void *
0x18002e7dc  call    memmove_0
0x18002e7e1  cmp     rdi, rbx
0x18002e7e4  jnb     short loc_18002E7FD
0x18002e7e6  sub     rbx, rdi
0x18002e7e9  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x18002e7ed  ja      short loc_18002E821
0x18002e7ef  lea     rcx, [rdi+rsi]; void *
0x18002e7f3  mov     r8, rbx; Size
0x18002e7f6  xor     edx, edx; Val
0x18002e7f8  call    memset_0
0x18002e7fd  xor     eax, eax
0x18002e7ff  jmp     short loc_18002E813
0x18002e801  mov     [rsp+58h+var_38], rsi
0x18002e806  mov     rcx, [rcx+88h]
0x18002e80d  call    cs:__imp_VirtioReadInterceptedBar
0x18002e813  jmp     short loc_18002E819
0x18002e815  mov     eax, [rsp+58h+var_28]
0x18002e819  add     rsp, 40h
0x18002e81d  pop     rdi
0x18002e81e  pop     rsi
0x18002e81f  pop     rbx
0x18002e820  retn
0x18002e821  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
