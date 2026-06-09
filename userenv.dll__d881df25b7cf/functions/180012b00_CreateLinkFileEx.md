# CreateLinkFileEx

- ea: `0x180012b00`
- end: `0x180012ba4`
- name: `CreateLinkFileEx`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f670`
- `0x180012b00`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateLinkFileExWorker` at `0x180012b8a`
- `ext-ms-win-profile-userenv-l1-1-0!CreateLinkFileExWorker` at `0x180012b8a`

## pseudocode

```c
__int64 __fastcall CreateLinkFileEx(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int16 a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int a12)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return CreateLinkFileExWorker(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12);
  else
    return 0;
}

```

## disassembly

```asm
0x180012b00  push    rbx
0x180012b02  push    rbp
0x180012b03  push    rsi
0x180012b04  push    rdi
0x180012b05  sub     rsp, 68h
0x180012b09  mov     rbx, r9
0x180012b0c  mov     rdi, r8
0x180012b0f  mov     rsi, rdx
0x180012b12  mov     ebp, ecx
0x180012b14  call    IsDeleteLinkFileWorkerPresent
0x180012b19  test    al, al
0x180012b1b  jz      short loc_180012B98
0x180012b1d  mov     eax, [rsp+88h+arg_58]
0x180012b24  mov     r9, rbx
0x180012b27  mov     [rsp+88h+var_30], eax
0x180012b2b  mov     r8, rdi
0x180012b2e  mov     rax, [rsp+88h+arg_50]
0x180012b36  mov     rdx, rsi
0x180012b39  mov     [rsp+88h+var_38], rax
0x180012b3e  mov     ecx, ebp
0x180012b40  mov     rax, [rsp+88h+arg_48]
0x180012b48  mov     [rsp+88h+var_40], rax
0x180012b4d  mov     eax, [rsp+88h+arg_40]
0x180012b54  mov     [rsp+88h+var_48], eax
0x180012b58  movzx   eax, [rsp+88h+arg_38]
0x180012b60  mov     [rsp+88h+var_50], ax
0x180012b65  mov     rax, [rsp+88h+arg_30]
0x180012b6d  mov     [rsp+88h+var_58], rax
0x180012b72  mov     eax, [rsp+88h+arg_28]
0x180012b79  mov     [rsp+88h+var_60], eax
0x180012b7d  mov     rax, [rsp+88h+arg_20]
0x180012b85  mov     [rsp+88h+var_68], rax
0x180012b8a  call    cs:__imp_CreateLinkFileExWorker
0x180012b91  nop     dword ptr [rax+rax+00h]
0x180012b96  jmp     short loc_180012B9A
0x180012b98  xor     eax, eax
0x180012b9a  add     rsp, 68h
0x180012b9e  pop     rdi
0x180012b9f  pop     rsi
0x180012ba0  pop     rbp
0x180012ba1  pop     rbx
0x180012ba2  retn
```
