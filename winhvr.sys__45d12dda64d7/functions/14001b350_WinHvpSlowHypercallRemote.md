# WinHvpSlowHypercallRemote

- ea: `0x14001b350`
- end: `0x14001b43a`
- name: `WinHvpSlowHypercallRemote`
- size: `234`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140001940`
- `0x140001a38`
- `0x140001d00`
- `0x140001ef0`
- `0x140002830`
- `0x140002d60`
- `0x140003610`
- `0x140003b70`

## callees

- `0x140009c90`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b36c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b36c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b420`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b420`

## pseudocode

```c
__int64 __fastcall WinHvpSlowHypercallRemote(unsigned __int16 a1, __int16 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-38h]

  if ( ExAcquireRundownProtection(&RunRef) )
  {
    if ( qword_1400160D8 )
    {
      LODWORD(v12) = a1;
      HIDWORD(v12) = a2 & 0xFFF;
      v10 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64, int))qword_1400160D8)(
              v12,
              a3,
              a3 != 0 ? 0x1000 : 0,
              a4,
              a4 != 0 ? 0x1000 : 0);
      if ( a5 )
        *a5 = HIWORD(v10);
      if ( (_WORD)v10 )
        v9 = (unsigned __int16)v10 | 0xC0350000;
      else
        v9 = 0;
    }
    else
    {
      v9 = -1070268414;
    }
    ExReleaseRundownProtection(&RunRef);
  }
  else
  {
    return (unsigned int)-1070268408;
  }
  return v9;
}

```

## disassembly

```asm
0x14001b350  push    rbx
0x14001b352  push    rbp
0x14001b353  push    rsi
0x14001b354  push    rdi
0x14001b355  push    r14
0x14001b357  sub     rsp, 40h
0x14001b35b  mov     ebp, ecx
0x14001b35d  mov     rdi, r9
0x14001b360  lea     rcx, RunRef; RunRef
0x14001b367  mov     rsi, r8
0x14001b36a  mov     ebx, edx
0x14001b36c  call    cs:__imp_ExAcquireRundownProtection
0x14001b373  nop     dword ptr [rax+rax+00h]
0x14001b378  xor     r14d, r14d
0x14001b37b  test    al, al
0x14001b37d  jnz     short loc_14001B389
0x14001b37f  mov     ebx, 0C0350008h
0x14001b384  jmp     loc_14001B42C
0x14001b389  mov     r10, cs:qword_1400160D8
0x14001b390  test    r10, r10
0x14001b393  jnz     short loc_14001B39C
0x14001b395  mov     ebx, 0C0350002h
0x14001b39a  jmp     short loc_14001B419
0x14001b39c  mov     [rsp+68h+var_38], r14
0x14001b3a1  and     ebx, 0FFFh
0x14001b3a7  movzx   eax, bp
0x14001b3aa  mov     rcx, rsi
0x14001b3ad  mov     dword ptr [rsp+68h+var_38], eax
0x14001b3b1  mov     r9, rdi
0x14001b3b4  mov     eax, dword ptr [rsp+68h+var_38+4]
0x14001b3b8  and     eax, 0FFFFF000h
0x14001b3bd  or      eax, ebx
0x14001b3bf  mov     dword ptr [rsp+68h+var_38+4], eax
0x14001b3c3  mov     rax, rdi
0x14001b3c6  neg     rax
0x14001b3c9  mov     eax, 1000h
0x14001b3ce  sbb     edx, edx
0x14001b3d0  and     edx, eax
0x14001b3d2  neg     rcx
0x14001b3d5  mov     [rsp+68h+var_48], edx
0x14001b3d9  mov     rcx, [rsp+68h+var_38]
0x14001b3de  mov     rdx, rsi
0x14001b3e1  sbb     r8d, r8d
0x14001b3e4  and     r8d, eax
0x14001b3e7  mov     rax, r10
0x14001b3ea  call    _guard_dispatch_icall
0x14001b3ef  mov     rdx, [rsp+68h+arg_20]
0x14001b3f7  test    rdx, rdx
0x14001b3fa  jz      short loc_14001B406
0x14001b3fc  mov     ecx, eax
0x14001b3fe  sar     ecx, 10h
0x14001b401  movzx   ecx, cx
0x14001b404  mov     [rdx], ecx
0x14001b406  test    ax, ax
0x14001b409  jnz     short loc_14001B410
0x14001b40b  mov     ebx, r14d
0x14001b40e  jmp     short loc_14001B419
0x14001b410  movzx   ebx, ax
0x14001b413  or      ebx, 0C0350000h
0x14001b419  lea     rcx, RunRef; RunRef
0x14001b420  call    cs:__imp_ExReleaseRundownProtection
0x14001b427  nop     dword ptr [rax+rax+00h]
0x14001b42c  mov     eax, ebx
0x14001b42e  add     rsp, 40h
0x14001b432  pop     r14
0x14001b434  pop     rdi
0x14001b435  pop     rsi
0x14001b436  pop     rbp
0x14001b437  pop     rbx
0x14001b438  retn
```
