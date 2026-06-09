# Gre::Base::BaseGlobalsNonPaged::~BaseGlobalsNonPaged(void)

- ea: `0x1401814c0`
- end: `0x14018161f`
- name: `??1BaseGlobalsNonPaged@Base@Gre@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(char *Resource)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14018145c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1401814d0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401814e3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401814f6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181509`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018151c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018152f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181542`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181555`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181568`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018157b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018158e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815a1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815b4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815c7`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815da`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815ed`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815fd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018160c`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401814d0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401814e3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401814f6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181509`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018151c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018152f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181542`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181555`
- `ntoskrnl!ExDeleteResourceLite` at `0x140181568`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018157b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018158e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815a1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815b4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815c7`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815da`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815ed`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401815fd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14018160c`

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
0x1401814c0  push    rbx
0x1401814c2  sub     rsp, 20h
0x1401814c6  mov     rbx, rcx
0x1401814c9  add     rcx, 720h; Resource
0x1401814d0  call    cs:__imp_ExDeleteResourceLite
0x1401814d7  nop     dword ptr [rax+rax+00h]
0x1401814dc  lea     rcx, [rbx+6B8h]; Resource
0x1401814e3  call    cs:__imp_ExDeleteResourceLite
0x1401814ea  nop     dword ptr [rax+rax+00h]
0x1401814ef  lea     rcx, [rbx+650h]; Resource
0x1401814f6  call    cs:__imp_ExDeleteResourceLite
0x1401814fd  nop     dword ptr [rax+rax+00h]
0x140181502  lea     rcx, [rbx+5E8h]; Resource
0x140181509  call    cs:__imp_ExDeleteResourceLite
0x140181510  nop     dword ptr [rax+rax+00h]
0x140181515  lea     rcx, [rbx+548h]; Resource
0x14018151c  call    cs:__imp_ExDeleteResourceLite
0x140181523  nop     dword ptr [rax+rax+00h]
0x140181528  lea     rcx, [rbx+4E0h]; Resource
0x14018152f  call    cs:__imp_ExDeleteResourceLite
0x140181536  nop     dword ptr [rax+rax+00h]
0x14018153b  lea     rcx, [rbx+478h]; Resource
0x140181542  call    cs:__imp_ExDeleteResourceLite
0x140181549  nop     dword ptr [rax+rax+00h]
0x14018154e  lea     rcx, [rbx+410h]; Resource
0x140181555  call    cs:__imp_ExDeleteResourceLite
0x14018155c  nop     dword ptr [rax+rax+00h]
0x140181561  lea     rcx, [rbx+3A8h]; Resource
0x140181568  call    cs:__imp_ExDeleteResourceLite
0x14018156f  nop     dword ptr [rax+rax+00h]
0x140181574  lea     rcx, [rbx+340h]; Resource
0x14018157b  call    cs:__imp_ExDeleteResourceLite
0x140181582  nop     dword ptr [rax+rax+00h]
0x140181587  lea     rcx, [rbx+2D8h]; Resource
0x14018158e  call    cs:__imp_ExDeleteResourceLite
0x140181595  nop     dword ptr [rax+rax+00h]
0x14018159a  lea     rcx, [rbx+270h]; Resource
0x1401815a1  call    cs:__imp_ExDeleteResourceLite
0x1401815a8  nop     dword ptr [rax+rax+00h]
0x1401815ad  lea     rcx, [rbx+208h]; Resource
0x1401815b4  call    cs:__imp_ExDeleteResourceLite
0x1401815bb  nop     dword ptr [rax+rax+00h]
0x1401815c0  lea     rcx, [rbx+1A0h]; Resource
0x1401815c7  call    cs:__imp_ExDeleteResourceLite
0x1401815ce  nop     dword ptr [rax+rax+00h]
0x1401815d3  lea     rcx, [rbx+138h]; Resource
0x1401815da  call    cs:__imp_ExDeleteResourceLite
0x1401815e1  nop     dword ptr [rax+rax+00h]
0x1401815e6  lea     rcx, [rbx+0D0h]; Resource
0x1401815ed  call    cs:__imp_ExDeleteResourceLite
0x1401815f4  nop     dword ptr [rax+rax+00h]
0x1401815f9  lea     rcx, [rbx+68h]; Resource
0x1401815fd  call    cs:__imp_ExDeleteResourceLite
0x140181604  nop     dword ptr [rax+rax+00h]
0x140181609  mov     rcx, rbx; Resource
0x14018160c  call    cs:__imp_ExDeleteResourceLite
0x140181613  nop     dword ptr [rax+rax+00h]
0x140181618  add     rsp, 20h
0x14018161c  pop     rbx
0x14018161d  retn
```
