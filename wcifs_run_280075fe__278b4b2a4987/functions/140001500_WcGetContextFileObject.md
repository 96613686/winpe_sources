# WcGetContextFileObject

- ea: `0x140001500`
- end: `0x14000156f`
- name: `WcGetContextFileObject`
- size: `111`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x140014c90`
- `0x1400184f0`
- `0x1400198a0`
- `0x140019f1c`
- `0x14001ce88`
- `0x140023150`
- `0x140023840`
- `0x140023a54`
- `0x140023c40`
- `0x140024040`
- `0x140024bf0`
- `0x140024e60`
- `0x140024f60`
- `0x140026080`
- `0x140027854`
- `0x140027f24`
- `0x140028574`
- `0x1400287d0`
- `0x14002893c`
- `0x140029608`
- `0x14002bd20`
- `0x14002ef40`
- `0x14002f21c`
- `0x140030a70`
- `0x140030d54`
- `0x140032500`
- `0x1400328d8`
- `0x1400343c0`
- `0x140034bb0`

## callees

- `0x140001500`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x140001527`
- `FLTMGR!FltGetFileContext` at `0x140001527`
- `FLTMGR!FltGetStreamContext` at `0x14000154f`
- `FLTMGR!FltGetStreamContext` at `0x14000154f`

## pseudocode

```c
char __fastcall WcGetContextFileObject(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *a3,
        PFLT_CONTEXT *a4)
{
  PFLT_CONTEXT Context; // [rsp+20h] [rbp-38h] BYREF
  PFLT_CONTEXT v10; // [rsp+28h] [rbp-30h] BYREF

  Context = 0;
  v10 = 0;
  if ( FltGetFileContext(Instance, FileObject, &Context) < 0 )
    return 0;
  FltGetStreamContext(Instance, FileObject, &v10);
  *a3 = Context;
  *a4 = v10;
  return 1;
}

```

## disassembly

```asm
0x140001500  push    rbx
0x140001502  push    rsi
0x140001503  push    rdi
0x140001504  push    r14
0x140001506  sub     rsp, 38h
0x14000150a  xor     eax, eax
0x14000150c  mov     r14, r8
0x14000150f  lea     r8, [rsp+58h+Context]; Context
0x140001514  mov     [rsp+58h+Context], rax
0x140001519  mov     [rsp+58h+var_30], rax
0x14000151e  mov     rsi, r9
0x140001521  mov     rdi, rdx
0x140001524  mov     rbx, rcx
0x140001527  call    cs:__imp_FltGetFileContext
0x14000152e  nop     dword ptr [rax+rax+00h]
0x140001533  test    eax, eax
0x140001535  jns     short loc_140001544
0x140001537  xor     al, al
0x140001539  add     rsp, 38h
0x14000153d  pop     r14
0x14000153f  pop     rdi
0x140001540  pop     rsi
0x140001541  pop     rbx
0x140001542  retn
0x140001544  lea     r8, [rsp+58h+var_30]; Context
0x140001549  mov     rdx, rdi; FileObject
0x14000154c  mov     rcx, rbx; Instance
0x14000154f  call    cs:__imp_FltGetStreamContext
0x140001556  nop     dword ptr [rax+rax+00h]
0x14000155b  mov     rax, [rsp+58h+Context]
0x140001560  mov     [r14], rax
0x140001563  mov     rax, [rsp+58h+var_30]
0x140001568  mov     [rsi], rax
0x14000156b  mov     al, 1
0x14000156d  jmp     short loc_140001539
```
