# CreateAppContainer

- ea: `0x180011a10`
- end: `0x180011a57`
- name: `CreateAppContainer`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e96c`
- `0x180011a10`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerWorker` at `0x180011a3a`
- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerWorker` at `0x180011a3a`

## pseudocode

```c
__int64 __fastcall CreateAppContainer(__int64 a1, __int64 a2, __int64 a3)
{
  if ( (unsigned __int8)IsAddAppContainerAccessWorkerPresent() )
    return CreateAppContainerWorker(a1, a2, a3);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180011a10  mov     [rsp+arg_0], rbx
0x180011a15  mov     [rsp+arg_8], rsi
0x180011a1a  push    rdi
0x180011a1b  sub     rsp, 20h
0x180011a1f  mov     rbx, r8
0x180011a22  mov     rdi, rdx
0x180011a25  mov     rsi, rcx
0x180011a28  call    IsAddAppContainerAccessWorkerPresent
0x180011a2d  test    al, al
0x180011a2f  jz      short loc_180011A42
0x180011a31  mov     r8, rbx
0x180011a34  mov     rdx, rdi
0x180011a37  mov     rcx, rsi
0x180011a3a  call    cs:__imp_CreateAppContainerWorker
0x180011a40  jmp     short loc_180011A47
0x180011a42  mov     eax, 80004001h
0x180011a47  mov     rbx, [rsp+28h+arg_0]
0x180011a4c  mov     rsi, [rsp+28h+arg_8]
0x180011a51  add     rsp, 20h
0x180011a55  pop     rdi
0x180011a56  retn
```
