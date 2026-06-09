# UdfDeleteFcb

- ea: `0x140038644`
- end: `0x1400386ca`
- name: `UdfDeleteFcb`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140009730`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14003866f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14003867f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14003866f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14003867f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038695`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038695`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400386ab`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400386ab`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140038658`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140038658`

## pseudocode

```c
void __fastcall UdfDeleteFcb(__int64 a1, PVOID *a2)
{
  __int64 v3; // rbx

  FsRtlTeardownPerFileContexts((PVOID *)*a2 + 11);
  v3 = *((_QWORD *)*a2 + 10);
  ExDeleteResourceLite((PERESOURCE)(v3 + 112));
  ExDeleteResourceLite((PERESOURCE)(v3 + 8));
  ExFreeToNPagedLookasideList(&UdfFcbNonPagedLookasideList, (PVOID)v3);
  ExFreeToPagedLookasideList(&UdfFcbLookasideList, *a2);
  *a2 = 0;
}

```

## disassembly

```asm
0x140038644  mov     [rsp+arg_0], rbx
0x140038649  push    rdi
0x14003864a  sub     rsp, 20h
0x14003864e  mov     rcx, [rdx]
0x140038651  mov     rdi, rdx
0x140038654  add     rcx, 58h ; 'X'; PerFileContextPointer
0x140038658  call    cs:__imp_FsRtlTeardownPerFileContexts
0x14003865f  nop     dword ptr [rax+rax+00h]
0x140038664  mov     rax, [rdi]
0x140038667  mov     rbx, [rax+50h]
0x14003866b  lea     rcx, [rbx+70h]; Resource
0x14003866f  call    cs:__imp_ExDeleteResourceLite
0x140038676  nop     dword ptr [rax+rax+00h]
0x14003867b  lea     rcx, [rbx+8]; Resource
0x14003867f  call    cs:__imp_ExDeleteResourceLite
0x140038686  nop     dword ptr [rax+rax+00h]
0x14003868b  mov     rdx, rbx; Entry
0x14003868e  lea     rcx, UdfFcbNonPagedLookasideList; Lookaside
0x140038695  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003869c  nop     dword ptr [rax+rax+00h]
0x1400386a1  mov     rdx, [rdi]; Entry
0x1400386a4  lea     rcx, UdfFcbLookasideList; Lookaside
0x1400386ab  call    cs:__imp_ExFreeToPagedLookasideList
0x1400386b2  nop     dword ptr [rax+rax+00h]
0x1400386b7  mov     rbx, [rsp+28h+arg_0]
0x1400386bc  mov     qword ptr [rdi], 0
0x1400386c3  add     rsp, 20h
0x1400386c7  pop     rdi
0x1400386c8  retn
```
