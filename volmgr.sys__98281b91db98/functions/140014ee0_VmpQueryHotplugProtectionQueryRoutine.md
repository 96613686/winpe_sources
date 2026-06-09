# VmpQueryHotplugProtectionQueryRoutine

- ea: `0x140014ee0`
- end: `0x140014f5f`
- name: `VmpQueryHotplugProtectionQueryRoutine`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005240`
- `0x140014ee0`

## import_xrefs

- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140014eff`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140014eff`
- `ntoskrnl!ExAllocatePool2` at `0x140014f20`
- `ntoskrnl!ExAllocatePool2` at `0x140014f20`

## pseudocode

```c
__int64 __fastcall VmpQueryHotplugProtectionQueryRoutine(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *a6)
{
  size_t v6; // rbx
  unsigned int v8; // ebx
  size_t v9; // rbp
  void *Pool2; // rax
  void *v11; // rsi

  v6 = a4;
  if ( a4 >= 0x28 && RtlValidSecurityDescriptor(a3) )
  {
    v9 = v6;
    Pool2 = (void *)ExAllocatePool2(258, v6, 538987862);
    v11 = Pool2;
    if ( Pool2 )
    {
      v8 = 0;
      memmove(Pool2, a3, v9);
      *a6 = v11;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741703;
  }
  return v8;
}

```

## disassembly

```asm
0x140014ee0  push    rbx
0x140014ee2  push    rbp
0x140014ee3  push    rsi
0x140014ee4  push    rdi
0x140014ee5  sub     rsp, 28h
0x140014ee9  mov     ebx, r9d
0x140014eec  mov     rdi, r8
0x140014eef  cmp     r9d, 28h ; '('
0x140014ef3  jnb     short loc_140014EFC
0x140014ef5  mov     ebx, 0C0000079h
0x140014efa  jmp     short loc_140014F53
0x140014efc  mov     rcx, rdi; SecurityDescriptor
0x140014eff  call    cs:__imp_RtlValidSecurityDescriptor
0x140014f06  nop     dword ptr [rax+rax+00h]
0x140014f0b  test    al, al
0x140014f0d  jz      short loc_140014EF5
0x140014f0f  mov     r8d, 20204D56h
0x140014f15  mov     rdx, rbx
0x140014f18  mov     ecx, 102h
0x140014f1d  mov     rbp, rbx
0x140014f20  call    cs:__imp_ExAllocatePool2
0x140014f27  nop     dword ptr [rax+rax+00h]
0x140014f2c  mov     rsi, rax
0x140014f2f  test    rax, rax
0x140014f32  jnz     short loc_140014F3B
0x140014f34  mov     ebx, 0C000009Ah
0x140014f39  jmp     short loc_140014F53
0x140014f3b  xor     ebx, ebx
0x140014f3d  mov     r8, rbp; Size
0x140014f40  mov     rdx, rdi; Src
0x140014f43  mov     rcx, rsi; void *
0x140014f46  call    memmove
0x140014f4b  mov     rcx, [rsp+48h+arg_28]
0x140014f50  mov     [rcx], rsi
0x140014f53  mov     eax, ebx
0x140014f55  add     rsp, 28h
0x140014f59  pop     rdi
0x140014f5a  pop     rsi
0x140014f5b  pop     rbp
0x140014f5c  pop     rbx
0x140014f5d  retn
```
