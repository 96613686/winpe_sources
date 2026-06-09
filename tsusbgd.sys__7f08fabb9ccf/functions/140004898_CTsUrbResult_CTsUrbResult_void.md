# CTsUrbResult::~CTsUrbResult(void)

- ea: `0x140004898`
- end: `0x140004914`
- name: `??1CTsUrbResult@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(CTsUrbResult *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004040`
- `0x1400049ac`

## callees

- `0x140004898`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400048e3`
- `ntoskrnl!MmUnlockPages` at `0x1400048e3`
- `ntoskrnl!IoFreeMdl` at `0x1400048f6`
- `ntoskrnl!IoFreeMdl` at `0x1400048f6`
- `ntoskrnl!ExFreePool` at `0x1400048c0`
- `ntoskrnl!ExFreePool` at `0x1400048c0`

## pseudocode

```c
void __fastcall CTsUrbResult::~CTsUrbResult(CTsUrbResult *this)
{
  char *v2; // rcx
  struct _MDL *v3; // rcx

  *(_QWORD *)this = &CTsUrbResult::`vftable';
  v2 = (char *)*((_QWORD *)this + 212);
  if ( v2 && v2 != (char *)this + 8 )
  {
    ExFreePool(v2);
    *((_QWORD *)this + 212) = 0;
  }
  v3 = (struct _MDL *)*((_QWORD *)this + 214);
  if ( v3 )
  {
    MmUnlockPages(v3);
    IoFreeMdl(*((PMDL *)this + 214));
    *((_QWORD *)this + 214) = 0;
  }
}

```

## disassembly

```asm
0x140004898  push    rbx
0x14000489a  sub     rsp, 20h
0x14000489e  lea     rax, ??_7CTsUrbResult@@6B@; const CTsUrbResult::`vftable'
0x1400048a5  mov     rbx, rcx
0x1400048a8  mov     [rcx], rax
0x1400048ab  mov     rcx, [rcx+6A0h]; P
0x1400048b2  test    rcx, rcx
0x1400048b5  jz      short loc_1400048D7
0x1400048b7  lea     rax, [rbx+8]
0x1400048bb  cmp     rcx, rax
0x1400048be  jz      short loc_1400048D7
0x1400048c0  call    cs:__imp_ExFreePool
0x1400048c7  nop     dword ptr [rax+rax+00h]
0x1400048cc  mov     qword ptr [rbx+6A0h], 0
0x1400048d7  mov     rcx, [rbx+6B0h]; MemoryDescriptorList
0x1400048de  test    rcx, rcx
0x1400048e1  jz      short loc_14000490D
0x1400048e3  call    cs:__imp_MmUnlockPages
0x1400048ea  nop     dword ptr [rax+rax+00h]
0x1400048ef  mov     rcx, [rbx+6B0h]; Mdl
0x1400048f6  call    cs:__imp_IoFreeMdl
0x1400048fd  nop     dword ptr [rax+rax+00h]
0x140004902  mov     qword ptr [rbx+6B0h], 0
0x14000490d  add     rsp, 20h
0x140004911  pop     rbx
0x140004912  retn
```
