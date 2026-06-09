# WcProcessSetLinkInformation

- ea: `0x140028574`
- end: `0x14002861e`
- name: `WcProcessSetLinkInformation`
- size: `170`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140027730`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140006324`
- `0x14001f08c`
- `0x140028574`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400285ed`
- `FLTMGR!FltReleaseContext` at `0x140028601`
- `FLTMGR!FltReleaseContext` at `0x1400285ed`
- `FLTMGR!FltReleaseContext` at `0x140028601`

## pseudocode

```c
__int64 __fastcall WcProcessSetLinkInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int v4; // esi

  v4 = 0;
  if ( (unsigned __int8)WcGetContextFileObject(
                          *(PFLT_INSTANCE *)(a2 + 24),
                          CallbackData->Iopb->Parameters.SetFileInformation.ParentOfTarget)
    && WcIsPlaceHolderDirectory(0, 0)
    && (unsigned __int8)WcIsUnionValid(MEMORY[0x28]) )
  {
    return (unsigned int)WcPrepareTargetDirectoryForRenameOrLink(CallbackData, a2);
  }
  return v4;
}

```

## disassembly

```asm
0x140028574  mov     rax, rsp
0x140028577  mov     [rax+18h], rbx
0x14002857b  push    rbp
0x14002857c  push    rsi
0x14002857d  push    r14
0x14002857f  sub     rsp, 20h
0x140028583  mov     rbp, rdx
0x140028586  lea     r9, [rax+10h]
0x14002858a  mov     rdx, [rcx+10h]
0x14002858e  lea     r8, [rax+8]
0x140028592  mov     r14, rcx
0x140028595  xor     esi, esi
0x140028597  mov     [rax+8], rsi
0x14002859b  mov     rcx, [rbp+18h]; Instance
0x14002859f  mov     rdx, [rdx+28h]; FileObject
0x1400285a3  mov     [rax+10h], rsi
0x1400285a7  call    WcGetContextFileObject
0x1400285ac  mov     rbx, [rsp+38h+arg_8]
0x1400285b1  test    al, al
0x1400285b3  jz      short loc_1400285E0
0x1400285b5  mov     rcx, [rsp+38h+Context]
0x1400285ba  mov     rdx, rbx
0x1400285bd  call    WcIsPlaceHolderDirectory
0x1400285c2  test    al, al
0x1400285c4  jz      short loc_1400285E0
0x1400285c6  mov     rcx, [rbx+28h]
0x1400285ca  call    WcIsUnionValid
0x1400285cf  test    al, al
0x1400285d1  jz      short loc_1400285E0
0x1400285d3  mov     rdx, rbp
0x1400285d6  mov     rcx, r14; CallbackData
0x1400285d9  call    WcPrepareTargetDirectoryForRenameOrLink
0x1400285de  mov     esi, eax
0x1400285e0  cmp     [rsp+38h+Context], 0
0x1400285e6  jz      short loc_1400285F9
0x1400285e8  mov     rcx, [rsp+38h+Context]; Context
0x1400285ed  call    cs:__imp_FltReleaseContext
0x1400285f4  nop     dword ptr [rax+rax+00h]
0x1400285f9  test    rbx, rbx
0x1400285fc  jz      short loc_14002860D
0x1400285fe  mov     rcx, rbx; Context
0x140028601  call    cs:__imp_FltReleaseContext
0x140028608  nop     dword ptr [rax+rax+00h]
0x14002860d  mov     rbx, [rsp+38h+arg_10]
0x140028612  mov     eax, esi
0x140028614  add     rsp, 20h
0x140028618  pop     r14
0x14002861a  pop     rsi
0x14002861b  pop     rbp
0x14002861c  retn
```
