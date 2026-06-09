# VmCleanup

- ea: `0x140002ba0`
- end: `0x140002c0f`
- name: `VmCleanup`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400029e0`
- `0x140002a30`
- `0x140002ba0`
- `0x140013ba0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002bd9`
- `ntoskrnl!IofCompleteRequest` at `0x140002bd9`

## pseudocode

```c
__int64 __fastcall VmCleanup(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi

  v2 = *(_QWORD *)(a1 + 64);
  if ( *(_DWORD *)(v2 + 16) == 1 && *(PFILE_OBJECT *)(v2 + 320) == a2->Tail.Overlay.CurrentStackLocation->FileObject )
  {
    VmpAcquireAll(*(struct VM_ROOT_EXTENSION **)(v2 + 8));
    VmpRevertGptAttributes((struct VM_VOLUME_EXTENSION *)v2);
    VmpReleaseAll(*(struct VM_ROOT_EXTENSION **)(v2 + 8));
  }
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140002ba0  mov     [rsp+arg_0], rbx
0x140002ba5  push    rdi
0x140002ba6  sub     rsp, 20h
0x140002baa  mov     rdi, [rcx+40h]
0x140002bae  mov     rbx, rdx
0x140002bb1  cmp     dword ptr [rdi+10h], 1
0x140002bb5  jnz     short loc_140002BCB
0x140002bb7  mov     rax, [rdx+0B8h]
0x140002bbe  mov     rcx, [rax+30h]
0x140002bc2  cmp     [rdi+140h], rcx
0x140002bc9  jz      short loc_140002BF3
0x140002bcb  xor     eax, eax
0x140002bcd  xor     edx, edx; PriorityBoost
0x140002bcf  mov     rcx, rbx; Irp
0x140002bd2  mov     [rbx+30h], eax
0x140002bd5  mov     [rbx+38h], rax
0x140002bd9  call    cs:__imp_IofCompleteRequest
0x140002be0  nop     dword ptr [rax+rax+00h]
0x140002be5  mov     rbx, [rsp+28h+arg_0]
0x140002bea  xor     eax, eax
0x140002bec  add     rsp, 20h
0x140002bf0  pop     rdi
0x140002bf1  retn
0x140002bf3  mov     rcx, [rdi+8]; struct VM_ROOT_EXTENSION *
0x140002bf7  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140002bfc  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140002bff  call    ?VmpRevertGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpRevertGptAttributes(VM_VOLUME_EXTENSION *)
0x140002c04  mov     rcx, [rdi+8]; struct VM_ROOT_EXTENSION *
0x140002c08  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140002c0d  jmp     short loc_140002BCB
```
