# CreateAppContainerProfileInternal

- ea: `0x1800088a0`
- end: `0x180008903`
- name: `CreateAppContainerProfileInternal`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x1800088a0`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x1800088ed`
- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x1800088ed`

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
0x1800088a0  push    rbx
0x1800088a2  push    rbp
0x1800088a3  push    rsi
0x1800088a4  push    rdi
0x1800088a5  sub     rsp, 48h
0x1800088a9  mov     rbx, r9
0x1800088ac  mov     rdi, r8
0x1800088af  mov     rsi, rdx
0x1800088b2  mov     rbp, rcx
0x1800088b5  call    IsDeleteLinkFileWorkerPresent
0x1800088ba  test    al, al
0x1800088bc  jz      short loc_1800088FC
0x1800088be  mov     rax, [rsp+68h+arg_30]
0x1800088c6  mov     r9, rbx
0x1800088c9  mov     [rsp+68h+var_38], rax
0x1800088ce  mov     r8, rdi
0x1800088d1  mov     eax, [rsp+68h+arg_28]
0x1800088d8  mov     rdx, rsi
0x1800088db  mov     [rsp+68h+var_40], eax
0x1800088df  mov     rcx, rbp
0x1800088e2  mov     eax, [rsp+68h+arg_20]
0x1800088e9  mov     [rsp+68h+var_48], eax
0x1800088ed  call    cs:__imp_CreateAppContainerProfileWorker
0x1800088f3  add     rsp, 48h
0x1800088f7  pop     rdi
0x1800088f8  pop     rsi
0x1800088f9  pop     rbp
0x1800088fa  pop     rbx
0x1800088fb  retn
0x1800088fc  mov     eax, 80004001h
0x180008901  jmp     short loc_1800088F3
```
