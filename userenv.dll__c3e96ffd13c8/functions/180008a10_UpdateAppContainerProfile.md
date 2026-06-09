# UpdateAppContainerProfile

- ea: `0x180008a10`
- end: `0x180008a73`
- name: `UpdateAppContainerProfile`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008a10`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x180008a5d`
- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x180008a5d`

## pseudocode

```c
__int64 __fastcall UpdateAppContainerProfile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return UpdateAppContainerProfileWorker(a1, a2, a3, a4, a5, a6, a7);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008a10  push    rbx
0x180008a12  push    rbp
0x180008a13  push    rsi
0x180008a14  push    rdi
0x180008a15  sub     rsp, 48h
0x180008a19  mov     rbx, r9
0x180008a1c  mov     rdi, r8
0x180008a1f  mov     rsi, rdx
0x180008a22  mov     rbp, rcx
0x180008a25  call    IsDeleteLinkFileWorkerPresent
0x180008a2a  test    al, al
0x180008a2c  jz      short loc_180008A6C
0x180008a2e  mov     eax, [rsp+68h+arg_30]
0x180008a35  mov     r9, rbx
0x180008a38  mov     [rsp+68h+var_38], eax
0x180008a3c  mov     r8, rdi
0x180008a3f  mov     eax, [rsp+68h+arg_28]
0x180008a46  mov     rdx, rsi
0x180008a49  mov     [rsp+68h+var_40], eax
0x180008a4d  mov     rcx, rbp
0x180008a50  mov     rax, [rsp+68h+arg_20]
0x180008a58  mov     [rsp+68h+var_48], rax
0x180008a5d  call    cs:__imp_UpdateAppContainerProfileWorker
0x180008a63  add     rsp, 48h
0x180008a67  pop     rdi
0x180008a68  pop     rsi
0x180008a69  pop     rbp
0x180008a6a  pop     rbx
0x180008a6b  retn
0x180008a6c  mov     eax, 80004001h
0x180008a71  jmp     short loc_180008A63
```
