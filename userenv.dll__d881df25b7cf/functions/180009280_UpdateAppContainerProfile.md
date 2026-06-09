# UpdateAppContainerProfile

- ea: `0x180009280`
- end: `0x1800092ea`
- name: `UpdateAppContainerProfile`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009280`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x1800092cd`
- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x1800092cd`

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
0x180009280  push    rbx
0x180009282  push    rbp
0x180009283  push    rsi
0x180009284  push    rdi
0x180009285  sub     rsp, 48h
0x180009289  mov     rbx, r9
0x18000928c  mov     rdi, r8
0x18000928f  mov     rsi, rdx
0x180009292  mov     rbp, rcx
0x180009295  call    IsDeleteLinkFileWorkerPresent
0x18000929a  test    al, al
0x18000929c  jz      short loc_1800092E3
0x18000929e  mov     eax, [rsp+68h+arg_30]
0x1800092a5  mov     r9, rbx
0x1800092a8  mov     [rsp+68h+var_38], eax
0x1800092ac  mov     r8, rdi
0x1800092af  mov     eax, [rsp+68h+arg_28]
0x1800092b6  mov     rdx, rsi
0x1800092b9  mov     [rsp+68h+var_40], eax
0x1800092bd  mov     rcx, rbp
0x1800092c0  mov     rax, [rsp+68h+arg_20]
0x1800092c8  mov     [rsp+68h+var_48], rax
0x1800092cd  call    cs:__imp_UpdateAppContainerProfileWorker
0x1800092d4  nop     dword ptr [rax+rax+00h]
0x1800092d9  add     rsp, 48h
0x1800092dd  pop     rdi
0x1800092de  pop     rsi
0x1800092df  pop     rbp
0x1800092e0  pop     rbx
0x1800092e1  retn
0x1800092e3  mov     eax, 80004001h
0x1800092e8  jmp     short loc_1800092D9
```
