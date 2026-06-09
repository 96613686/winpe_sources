# Gre::Base::BaseGlobalsNonPaged::~BaseGlobalsNonPaged(void)

- ea: `0x14017ef90`
- end: `0x14017f0ef`
- name: `??1BaseGlobalsNonPaged@Base@Gre@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14017ef2c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14017efa0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efb3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efc6`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efd9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efec`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efff`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f012`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f025`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f038`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f04b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f05e`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f071`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f084`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f097`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0aa`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0bd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0cd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0dc`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efa0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efb3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efc6`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efd9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efec`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017efff`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f012`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f025`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f038`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f04b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f05e`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f071`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f084`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f097`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0aa`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0bd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0cd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f0dc`

## pseudocode

```c
void __fastcall Gre::Base::BaseGlobalsNonPaged::~BaseGlobalsNonPaged(char *Resource)
{
  ExDeleteResourceLite((PERESOURCE)(Resource + 1824));
  ExDeleteResourceLite((PERESOURCE)(Resource + 1720));
  ExDeleteResourceLite((PERESOURCE)(Resource + 1616));
  ExDeleteResourceLite((PERESOURCE)(Resource + 1512));
  ExDeleteResourceLite((PERESOURCE)Resource + 13);
  ExDeleteResourceLite((PERESOURCE)Resource + 12);
  ExDeleteResourceLite((PERESOURCE)Resource + 11);
  ExDeleteResourceLite((PERESOURCE)Resource + 10);
  ExDeleteResourceLite((PERESOURCE)Resource + 9);
  ExDeleteResourceLite((PERESOURCE)Resource + 8);
  ExDeleteResourceLite((PERESOURCE)Resource + 7);
  ExDeleteResourceLite((PERESOURCE)Resource + 6);
  ExDeleteResourceLite((PERESOURCE)Resource + 5);
  ExDeleteResourceLite((PERESOURCE)Resource + 4);
  ExDeleteResourceLite((PERESOURCE)Resource + 3);
  ExDeleteResourceLite((PERESOURCE)Resource + 2);
  ExDeleteResourceLite((PERESOURCE)Resource + 1);
  ExDeleteResourceLite((PERESOURCE)Resource);
}

```

## disassembly

```asm
0x14017ef90  push    rbx
0x14017ef92  sub     rsp, 20h
0x14017ef96  mov     rbx, rcx
0x14017ef99  add     rcx, 720h; Resource
0x14017efa0  call    cs:__imp_ExDeleteResourceLite
0x14017efa7  nop     dword ptr [rax+rax+00h]
0x14017efac  lea     rcx, [rbx+6B8h]; Resource
0x14017efb3  call    cs:__imp_ExDeleteResourceLite
0x14017efba  nop     dword ptr [rax+rax+00h]
0x14017efbf  lea     rcx, [rbx+650h]; Resource
0x14017efc6  call    cs:__imp_ExDeleteResourceLite
0x14017efcd  nop     dword ptr [rax+rax+00h]
0x14017efd2  lea     rcx, [rbx+5E8h]; Resource
0x14017efd9  call    cs:__imp_ExDeleteResourceLite
0x14017efe0  nop     dword ptr [rax+rax+00h]
0x14017efe5  lea     rcx, [rbx+548h]; Resource
0x14017efec  call    cs:__imp_ExDeleteResourceLite
0x14017eff3  nop     dword ptr [rax+rax+00h]
0x14017eff8  lea     rcx, [rbx+4E0h]; Resource
0x14017efff  call    cs:__imp_ExDeleteResourceLite
0x14017f006  nop     dword ptr [rax+rax+00h]
0x14017f00b  lea     rcx, [rbx+478h]; Resource
0x14017f012  call    cs:__imp_ExDeleteResourceLite
0x14017f019  nop     dword ptr [rax+rax+00h]
0x14017f01e  lea     rcx, [rbx+410h]; Resource
0x14017f025  call    cs:__imp_ExDeleteResourceLite
0x14017f02c  nop     dword ptr [rax+rax+00h]
0x14017f031  lea     rcx, [rbx+3A8h]; Resource
0x14017f038  call    cs:__imp_ExDeleteResourceLite
0x14017f03f  nop     dword ptr [rax+rax+00h]
0x14017f044  lea     rcx, [rbx+340h]; Resource
0x14017f04b  call    cs:__imp_ExDeleteResourceLite
0x14017f052  nop     dword ptr [rax+rax+00h]
0x14017f057  lea     rcx, [rbx+2D8h]; Resource
0x14017f05e  call    cs:__imp_ExDeleteResourceLite
0x14017f065  nop     dword ptr [rax+rax+00h]
0x14017f06a  lea     rcx, [rbx+270h]; Resource
0x14017f071  call    cs:__imp_ExDeleteResourceLite
0x14017f078  nop     dword ptr [rax+rax+00h]
0x14017f07d  lea     rcx, [rbx+208h]; Resource
0x14017f084  call    cs:__imp_ExDeleteResourceLite
0x14017f08b  nop     dword ptr [rax+rax+00h]
0x14017f090  lea     rcx, [rbx+1A0h]; Resource
0x14017f097  call    cs:__imp_ExDeleteResourceLite
0x14017f09e  nop     dword ptr [rax+rax+00h]
0x14017f0a3  lea     rcx, [rbx+138h]; Resource
0x14017f0aa  call    cs:__imp_ExDeleteResourceLite
0x14017f0b1  nop     dword ptr [rax+rax+00h]
0x14017f0b6  lea     rcx, [rbx+0D0h]; Resource
0x14017f0bd  call    cs:__imp_ExDeleteResourceLite
0x14017f0c4  nop     dword ptr [rax+rax+00h]
0x14017f0c9  lea     rcx, [rbx+68h]; Resource
0x14017f0cd  call    cs:__imp_ExDeleteResourceLite
0x14017f0d4  nop     dword ptr [rax+rax+00h]
0x14017f0d9  mov     rcx, rbx; Resource
0x14017f0dc  call    cs:__imp_ExDeleteResourceLite
0x14017f0e3  nop     dword ptr [rax+rax+00h]
0x14017f0e8  add     rsp, 20h
0x14017f0ec  pop     rbx
0x14017f0ed  retn
```
