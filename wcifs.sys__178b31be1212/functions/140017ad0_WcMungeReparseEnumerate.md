# WcMungeReparseEnumerate

- ea: `0x140017ad0`
- end: `0x140017b40`
- name: `WcMungeReparseEnumerate`
- size: `112`
- prototype: `__int64 __fastcall(int, void *, void *, unsigned int, char, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140029060`

## callees

- `0x140007c90`
- `0x14001439c`
- `0x140017ad0`

## pseudocode

```c
__int64 __fastcall WcMungeReparseEnumerate(int a1, void *a2, void *a3, unsigned int a4, char a5, _DWORD *a6)
{
  if ( a1 != 33 )
    return 3221225659LL;
  if ( a4 < 0x10 )
  {
    *a6 = 0;
  }
  else
  {
    if ( a5 )
      RtlCopyToUser(a3, a2, 0x10u);
    else
      RtlCopyVolatileMemory(a3, a2, 0x10u);
    *a6 = 16;
  }
  return 0;
}

```

## disassembly

```asm
0x140017ad0  push    rbx
0x140017ad2  sub     rsp, 30h
0x140017ad6  mov     rax, r8
0x140017ad9  mov     [rsp+38h+var_18], 0
0x140017ade  xor     ebx, ebx
0x140017ae0  cmp     ecx, 21h ; '!'
0x140017ae3  jz      short loc_140017AEC
0x140017ae5  mov     eax, 0C00000BBh
0x140017aea  jmp     short loc_140017B39
0x140017aec  cmp     r9d, 10h
0x140017af0  jb      short loc_140017B25
0x140017af2  mov     [rsp+38h+var_18], 1
0x140017af7  mov     r8d, 10h; Size
0x140017afd  mov     rcx, rax; void *
0x140017b00  cmp     [rsp+38h+arg_20], 0
0x140017b05  jz      short loc_140017B0E
0x140017b07  call    RtlCopyToUser
0x140017b0c  jmp     short loc_140017B13
0x140017b0e  call    RtlCopyVolatileMemory
0x140017b13  mov     [rsp+38h+var_18], 0
0x140017b18  mov     rax, [rsp+38h+arg_28]
0x140017b1d  mov     dword ptr [rax], 10h
0x140017b23  jmp     short loc_140017B30
0x140017b25  mov     rax, [rsp+38h+arg_28]
0x140017b2a  mov     dword ptr [rax], 0
0x140017b30  jmp     short loc_140017B37
0x140017b32  mov     ebx, 0C00000E8h
0x140017b37  mov     eax, ebx
0x140017b39  add     rsp, 30h
0x140017b3d  pop     rbx
0x140017b3e  retn
0x140034ecb  push    rbp
0x140034ecd  sub     rsp, 20h
0x140034ed1  mov     rbp, rdx
0x140034ed4  xor     eax, eax
0x140034ed6  cmp     [rbp+20h], al
0x140034ed9  setnz   al
0x140034edc  add     rsp, 20h
0x140034ee0  pop     rbp
0x140034ee1  retn
```
