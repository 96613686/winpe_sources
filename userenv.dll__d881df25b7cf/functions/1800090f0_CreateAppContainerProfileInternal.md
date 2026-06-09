# CreateAppContainerProfileInternal

- ea: `0x1800090f0`
- end: `0x18000915a`
- name: `CreateAppContainerProfileInternal`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800090c0`

## callees

- `0x1800090f0`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x18000913d`
- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x18000913d`

## pseudocode

```c
__int64 __fastcall CreateAppContainerProfileInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return CreateAppContainerProfileWorker(a1, a2, a3, a4, a5, a6, a7);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x1800090f0  push    rbx
0x1800090f2  push    rbp
0x1800090f3  push    rsi
0x1800090f4  push    rdi
0x1800090f5  sub     rsp, 48h
0x1800090f9  mov     rbx, r9
0x1800090fc  mov     rdi, r8
0x1800090ff  mov     rsi, rdx
0x180009102  mov     rbp, rcx
0x180009105  call    IsDeleteLinkFileWorkerPresent
0x18000910a  test    al, al
0x18000910c  jz      short loc_180009153
0x18000910e  mov     rax, [rsp+68h+arg_30]
0x180009116  mov     r9, rbx
0x180009119  mov     [rsp+68h+var_38], rax
0x18000911e  mov     r8, rdi
0x180009121  mov     eax, [rsp+68h+arg_28]
0x180009128  mov     rdx, rsi
0x18000912b  mov     [rsp+68h+var_40], eax
0x18000912f  mov     rcx, rbp
0x180009132  mov     eax, [rsp+68h+arg_20]
0x180009139  mov     [rsp+68h+var_48], eax
0x18000913d  call    cs:__imp_CreateAppContainerProfileWorker
0x180009144  nop     dword ptr [rax+rax+00h]
0x180009149  add     rsp, 48h
0x18000914d  pop     rdi
0x18000914e  pop     rsi
0x18000914f  pop     rbp
0x180009150  pop     rbx
0x180009151  retn
0x180009153  mov     eax, 80004001h
0x180009158  jmp     short loc_180009149
```
