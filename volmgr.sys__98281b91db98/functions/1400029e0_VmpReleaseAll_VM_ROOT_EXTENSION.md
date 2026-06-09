# VmpReleaseAll(VM_ROOT_EXTENSION *)

- ea: `0x1400029e0`
- end: `0x140002a25`
- name: `?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `69`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`
- `0x140002ba0`
- `0x140004b40`
- `0x14000fba0`
- `0x140010814`
- `0x140011e00`
- `0x140012eac`
- `0x140014b30`
- `0x140014b80`
- `0x140014e90`
- `0x140016760`

## callees

- `0x1400029e0`
- `0x14000e300`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140002a00`
- `ntoskrnl!KeReleaseMutex` at `0x140002a12`
- `ntoskrnl!KeReleaseMutex` at `0x140002a00`
- `ntoskrnl!KeReleaseMutex` at `0x140002a12`

## pseudocode

```c
void __fastcall VmpReleaseAll(struct VM_ROOT_EXTENSION *a1)
{
  if ( *((struct VM_ROOT_EXTENSION **)a1 + 23) != (struct VM_ROOT_EXTENSION *)((char *)a1 + 184) )
    VmpProcessDiskNotifications(a1);
  KeReleaseMutex((PRKMUTEX)a1 + 2, 0);
  KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
}

```

## disassembly

```asm
0x1400029e0  push    rbx
0x1400029e2  sub     rsp, 20h
0x1400029e6  lea     rax, [rcx+0B8h]
0x1400029ed  mov     rbx, rcx
0x1400029f0  cmp     [rax], rax
0x1400029f3  jz      short loc_1400029FA
0x1400029f5  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x1400029fa  lea     rcx, [rbx+70h]; Mutex
0x1400029fe  xor     edx, edx; Wait
0x140002a00  call    cs:__imp_KeReleaseMutex
0x140002a07  nop     dword ptr [rax+rax+00h]
0x140002a0c  lea     rcx, [rbx+38h]; Mutex
0x140002a10  xor     edx, edx; Wait
0x140002a12  call    cs:__imp_KeReleaseMutex
0x140002a19  nop     dword ptr [rax+rax+00h]
0x140002a1e  add     rsp, 20h
0x140002a22  pop     rbx
0x140002a23  retn
```
