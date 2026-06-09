# WcProcessSetLinkInformation

- ea: `0x1400285c4`
- end: `0x14002866e`
- name: `WcProcessSetLinkInformation`
- size: `170`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140027780`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140006324`
- `0x14001f08c`
- `0x1400285c4`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14002863d`
- `FLTMGR!FltReleaseContext` at `0x140028651`
- `FLTMGR!FltReleaseContext` at `0x14002863d`
- `FLTMGR!FltReleaseContext` at `0x140028651`

## pseudocode

```c
__int64 __fastcall WcProcessSetLinkInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int v3; // esi

  v3 = 0;
  if ( (unsigned __int8)WcGetContextFileObject(
                          *(PFLT_INSTANCE *)(a2 + 24),
                          CallbackData->Iopb->Parameters.SetFileInformation.ParentOfTarget)
    && (unsigned __int8)WcIsPlaceHolderDirectory(0, 0)
    && (unsigned __int8)WcIsUnionValid(MEMORY[0x28]) )
  {
    return (unsigned int)WcPrepareTargetDirectoryForRenameOrLink(CallbackData);
  }
  return v3;
}

```

## disassembly

```asm
0x1400285c4  mov     rax, rsp
0x1400285c7  mov     [rax+18h], rbx
0x1400285cb  push    rbp
0x1400285cc  push    rsi
0x1400285cd  push    r14
0x1400285cf  sub     rsp, 20h
0x1400285d3  mov     rbp, rdx
0x1400285d6  lea     r9, [rax+10h]
0x1400285da  mov     rdx, [rcx+10h]
0x1400285de  lea     r8, [rax+8]
0x1400285e2  mov     r14, rcx
0x1400285e5  xor     esi, esi
0x1400285e7  mov     [rax+8], rsi
0x1400285eb  mov     rcx, [rbp+18h]; Instance
0x1400285ef  mov     rdx, [rdx+28h]; FileObject
0x1400285f3  mov     [rax+10h], rsi
0x1400285f7  call    WcGetContextFileObject
0x1400285fc  mov     rbx, [rsp+38h+arg_8]
0x140028601  test    al, al
0x140028603  jz      short loc_140028630
0x140028605  mov     rcx, [rsp+38h+Context]
0x14002860a  mov     rdx, rbx
0x14002860d  call    WcIsPlaceHolderDirectory
0x140028612  test    al, al
0x140028614  jz      short loc_140028630
0x140028616  mov     rcx, [rbx+28h]
0x14002861a  call    WcIsUnionValid
0x14002861f  test    al, al
0x140028621  jz      short loc_140028630
0x140028623  mov     rdx, rbp
0x140028626  mov     rcx, r14; CallbackData
0x140028629  call    WcPrepareTargetDirectoryForRenameOrLink
0x14002862e  mov     esi, eax
0x140028630  cmp     [rsp+38h+Context], 0
0x140028636  jz      short loc_140028649
0x140028638  mov     rcx, [rsp+38h+Context]; Context
0x14002863d  call    cs:__imp_FltReleaseContext
0x140028644  nop     dword ptr [rax+rax+00h]
0x140028649  test    rbx, rbx
0x14002864c  jz      short loc_14002865D
0x14002864e  mov     rcx, rbx; Context
0x140028651  call    cs:__imp_FltReleaseContext
0x140028658  nop     dword ptr [rax+rax+00h]
0x14002865d  mov     rbx, [rsp+38h+arg_10]
0x140028662  mov     eax, esi
0x140028664  add     rsp, 20h
0x140028668  pop     r14
0x14002866a  pop     rsi
0x14002866b  pop     rbp
0x14002866c  retn
```
