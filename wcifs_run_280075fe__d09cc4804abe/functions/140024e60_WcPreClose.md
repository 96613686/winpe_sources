# WcPreClose

- ea: `0x140024e60`
- end: `0x140024f4b`
- name: `WcPreClose`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140002264`
- `0x140024e60`

## import_xrefs

- `FLTMGR!FltDeleteContext` at `0x140024eed`
- `FLTMGR!FltDeleteContext` at `0x140024eed`
- `FLTMGR!FltReleaseContext` at `0x140024ec0`
- `FLTMGR!FltReleaseContext` at `0x140024f3a`
- `FLTMGR!FltReleaseContext` at `0x140024ec0`
- `FLTMGR!FltReleaseContext` at `0x140024f3a`

## pseudocode

```c
__int64 __fastcall WcPreClose(__int64 a1, __int64 a2)
{
  WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  return 1;
}

```

## disassembly

```asm
0x140024e60  mov     [rsp+arg_0], rbx
0x140024e65  push    rsi
0x140024e66  sub     rsp, 20h
0x140024e6a  mov     rsi, rdx
0x140024e6d  lea     r9, [rsp+28h+arg_18]
0x140024e72  mov     rdx, [rdx+20h]; FileObject
0x140024e76  lea     r8, [rsp+28h+Context]
0x140024e7b  xor     eax, eax
0x140024e7d  mov     [rsp+28h+Context], rax
0x140024e82  mov     rcx, [rsi+18h]; Instance
0x140024e86  mov     [rsp+28h+arg_18], rax
0x140024e8b  call    WcGetContextFileObject
0x140024e90  mov     rbx, [rsp+28h+arg_18]
0x140024e95  test    al, al
0x140024e97  jnz     short loc_140024ECE
0x140024e99  cmp     [rsp+28h+Context], 0
0x140024e9f  jnz     short loc_140024EBB
0x140024ea1  test    rbx, rbx
0x140024ea4  jnz     loc_140024F37
0x140024eaa  mov     rbx, [rsp+28h+arg_0]
0x140024eaf  mov     eax, 1
0x140024eb4  add     rsp, 20h
0x140024eb8  pop     rsi
0x140024eb9  retn
0x140024ebb  mov     rcx, [rsp+28h+Context]; Context
0x140024ec0  call    cs:__imp_FltReleaseContext
0x140024ec7  nop     dword ptr [rax+rax+00h]
0x140024ecc  jmp     short loc_140024EA1
0x140024ece  test    rbx, rbx
0x140024ed1  jz      short loc_140024E99
0x140024ed3  mov     rcx, [rsp+28h+Context]
0x140024ed8  mov     rdx, rbx
0x140024edb  call    WcIsPlaceHolderDirectory
0x140024ee0  test    al, al
0x140024ee2  jz      short loc_140024EFB
0x140024ee4  cmp     byte ptr [rbx+1Dh], 0
0x140024ee8  jz      short loc_140024E99
0x140024eea  mov     rcx, rbx; Context
0x140024eed  call    cs:__imp_FltDeleteContext
0x140024ef4  nop     dword ptr [rax+rax+00h]
0x140024ef9  jmp     short loc_140024E99
0x140024efb  mov     rcx, [rsi+20h]
0x140024eff  mov     rdx, rbx
0x140024f02  call    WcUsesSourceSectionObjectPointers
0x140024f07  test    al, al
0x140024f09  jz      short loc_140024EE4
0x140024f0b  mov     rax, [rbx+30h]
0x140024f0f  mov     [rcx+28h], rax
0x140024f13  mov     rax, [rbx+20h]
0x140024f17  mov     rcx, [rax]
0x140024f1a  lock dec dword ptr [rcx+18h]
0x140024f1e  cmp     cs:byte_14000E680, 0
0x140024f25  jz      short loc_140024EE4
0x140024f27  mov     rax, [rbx+20h]
0x140024f2b  mov     rdx, [rax]
0x140024f2e  mov     rax, [rdx+20h]
0x140024f32  lock inc dword ptr [rax]
0x140024f35  jmp     short loc_140024EE4
0x140024f37  mov     rcx, rbx; Context
0x140024f3a  call    cs:__imp_FltReleaseContext
0x140024f41  nop     dword ptr [rax+rax+00h]
0x140024f46  jmp     loc_140024EAA
```
