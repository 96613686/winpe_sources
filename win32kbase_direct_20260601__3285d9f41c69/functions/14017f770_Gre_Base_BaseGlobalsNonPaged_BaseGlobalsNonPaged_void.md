# Gre::Base::BaseGlobalsNonPaged::~BaseGlobalsNonPaged(void)

- ea: `0x14017f770`
- end: `0x14017f8cf`
- name: `??1BaseGlobalsNonPaged@Base@Gre@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14017f70c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14017f780`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f793`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7a6`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7b9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7cc`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7df`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7f2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f805`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f818`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f82b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f83e`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f851`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f864`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f877`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f88a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f89d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f8ad`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f8bc`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f780`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f793`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7a6`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7b9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7cc`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7df`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f7f2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f805`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f818`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f82b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f83e`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f851`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f864`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f877`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f88a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f89d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f8ad`
- `ntoskrnl!ExDeleteResourceLite` at `0x14017f8bc`

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
0x14017f770  push    rbx
0x14017f772  sub     rsp, 20h
0x14017f776  mov     rbx, rcx
0x14017f779  add     rcx, 720h; Resource
0x14017f780  call    cs:__imp_ExDeleteResourceLite
0x14017f787  nop     dword ptr [rax+rax+00h]
0x14017f78c  lea     rcx, [rbx+6B8h]; Resource
0x14017f793  call    cs:__imp_ExDeleteResourceLite
0x14017f79a  nop     dword ptr [rax+rax+00h]
0x14017f79f  lea     rcx, [rbx+650h]; Resource
0x14017f7a6  call    cs:__imp_ExDeleteResourceLite
0x14017f7ad  nop     dword ptr [rax+rax+00h]
0x14017f7b2  lea     rcx, [rbx+5E8h]; Resource
0x14017f7b9  call    cs:__imp_ExDeleteResourceLite
0x14017f7c0  nop     dword ptr [rax+rax+00h]
0x14017f7c5  lea     rcx, [rbx+548h]; Resource
0x14017f7cc  call    cs:__imp_ExDeleteResourceLite
0x14017f7d3  nop     dword ptr [rax+rax+00h]
0x14017f7d8  lea     rcx, [rbx+4E0h]; Resource
0x14017f7df  call    cs:__imp_ExDeleteResourceLite
0x14017f7e6  nop     dword ptr [rax+rax+00h]
0x14017f7eb  lea     rcx, [rbx+478h]; Resource
0x14017f7f2  call    cs:__imp_ExDeleteResourceLite
0x14017f7f9  nop     dword ptr [rax+rax+00h]
0x14017f7fe  lea     rcx, [rbx+410h]; Resource
0x14017f805  call    cs:__imp_ExDeleteResourceLite
0x14017f80c  nop     dword ptr [rax+rax+00h]
0x14017f811  lea     rcx, [rbx+3A8h]; Resource
0x14017f818  call    cs:__imp_ExDeleteResourceLite
0x14017f81f  nop     dword ptr [rax+rax+00h]
0x14017f824  lea     rcx, [rbx+340h]; Resource
0x14017f82b  call    cs:__imp_ExDeleteResourceLite
0x14017f832  nop     dword ptr [rax+rax+00h]
0x14017f837  lea     rcx, [rbx+2D8h]; Resource
0x14017f83e  call    cs:__imp_ExDeleteResourceLite
0x14017f845  nop     dword ptr [rax+rax+00h]
0x14017f84a  lea     rcx, [rbx+270h]; Resource
0x14017f851  call    cs:__imp_ExDeleteResourceLite
0x14017f858  nop     dword ptr [rax+rax+00h]
0x14017f85d  lea     rcx, [rbx+208h]; Resource
0x14017f864  call    cs:__imp_ExDeleteResourceLite
0x14017f86b  nop     dword ptr [rax+rax+00h]
0x14017f870  lea     rcx, [rbx+1A0h]; Resource
0x14017f877  call    cs:__imp_ExDeleteResourceLite
0x14017f87e  nop     dword ptr [rax+rax+00h]
0x14017f883  lea     rcx, [rbx+138h]; Resource
0x14017f88a  call    cs:__imp_ExDeleteResourceLite
0x14017f891  nop     dword ptr [rax+rax+00h]
0x14017f896  lea     rcx, [rbx+0D0h]; Resource
0x14017f89d  call    cs:__imp_ExDeleteResourceLite
0x14017f8a4  nop     dword ptr [rax+rax+00h]
0x14017f8a9  lea     rcx, [rbx+68h]; Resource
0x14017f8ad  call    cs:__imp_ExDeleteResourceLite
0x14017f8b4  nop     dword ptr [rax+rax+00h]
0x14017f8b9  mov     rcx, rbx; Resource
0x14017f8bc  call    cs:__imp_ExDeleteResourceLite
0x14017f8c3  nop     dword ptr [rax+rax+00h]
0x14017f8c8  add     rsp, 20h
0x14017f8cc  pop     rbx
0x14017f8cd  retn
```
