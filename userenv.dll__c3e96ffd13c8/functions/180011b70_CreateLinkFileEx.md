# CreateLinkFileEx

- ea: `0x180011b70`
- end: `0x180011c0d`
- name: `CreateLinkFileEx`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e9c0`
- `0x180011b70`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateLinkFileExWorker` at `0x180011bfa`
- `ext-ms-win-profile-userenv-l1-1-0!CreateLinkFileExWorker` at `0x180011bfa`

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
0x180011b70  push    rbx
0x180011b72  push    rbp
0x180011b73  push    rsi
0x180011b74  push    rdi
0x180011b75  sub     rsp, 68h
0x180011b79  mov     rbx, r9
0x180011b7c  mov     rdi, r8
0x180011b7f  mov     rsi, rdx
0x180011b82  mov     ebp, ecx
0x180011b84  call    IsDeleteLinkFileWorkerPresent
0x180011b89  test    al, al
0x180011b8b  jz      short loc_180011C02
0x180011b8d  mov     eax, [rsp+88h+arg_58]
0x180011b94  mov     r9, rbx
0x180011b97  mov     [rsp+88h+var_30], eax
0x180011b9b  mov     r8, rdi
0x180011b9e  mov     rax, [rsp+88h+arg_50]
0x180011ba6  mov     rdx, rsi
0x180011ba9  mov     [rsp+88h+var_38], rax
0x180011bae  mov     ecx, ebp
0x180011bb0  mov     rax, [rsp+88h+arg_48]
0x180011bb8  mov     [rsp+88h+var_40], rax
0x180011bbd  mov     eax, [rsp+88h+arg_40]
0x180011bc4  mov     [rsp+88h+var_48], eax
0x180011bc8  movzx   eax, [rsp+88h+arg_38]
0x180011bd0  mov     [rsp+88h+var_50], ax
0x180011bd5  mov     rax, [rsp+88h+arg_30]
0x180011bdd  mov     [rsp+88h+var_58], rax
0x180011be2  mov     eax, [rsp+88h+arg_28]
0x180011be9  mov     [rsp+88h+var_60], eax
0x180011bed  mov     rax, [rsp+88h+arg_20]
0x180011bf5  mov     [rsp+88h+var_68], rax
0x180011bfa  call    cs:__imp_CreateLinkFileExWorker
0x180011c00  jmp     short loc_180011C04
0x180011c02  xor     eax, eax
0x180011c04  add     rsp, 68h
0x180011c08  pop     rdi
0x180011c09  pop     rsi
0x180011c0a  pop     rbp
0x180011c0b  pop     rbx
0x180011c0c  retn
```
