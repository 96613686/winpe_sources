# CreateAppContainer

- ea: `0x180012980`
- end: `0x1800129ce`
- name: `CreateAppContainer`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f61c`
- `0x180012980`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerWorker` at `0x1800129aa`
- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerWorker` at `0x1800129aa`

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
0x180012980  mov     [rsp+arg_0], rbx
0x180012985  mov     [rsp+arg_8], rsi
0x18001298a  push    rdi
0x18001298b  sub     rsp, 20h
0x18001298f  mov     rbx, r8
0x180012992  mov     rdi, rdx
0x180012995  mov     rsi, rcx
0x180012998  call    IsAddAppContainerAccessWorkerPresent
0x18001299d  test    al, al
0x18001299f  jz      short loc_1800129B8
0x1800129a1  mov     r8, rbx
0x1800129a4  mov     rdx, rdi
0x1800129a7  mov     rcx, rsi
0x1800129aa  call    cs:__imp_CreateAppContainerWorker
0x1800129b1  nop     dword ptr [rax+rax+00h]
0x1800129b6  jmp     short loc_1800129BD
0x1800129b8  mov     eax, 80004001h
0x1800129bd  mov     rbx, [rsp+28h+arg_0]
0x1800129c2  mov     rsi, [rsp+28h+arg_8]
0x1800129c7  add     rsp, 20h
0x1800129cb  pop     rdi
0x1800129cc  retn
```
